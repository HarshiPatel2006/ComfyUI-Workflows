# H3 Image Edit - BBox Layout + 4 Reference Images (`h3-image-edit-bbox-refs.json`)

Agent guide. Read it fully before touching the graph or calling the API.

## What it does

MiniMax-H3-Image multi-reference composition with **drawn placement boxes**. You draw boxes on a canvas over a clean scene; each box says where one reference person goes and what they are doing. A prompt builder turns the boxes into model-clean placement language (no "box", no coordinates by default), and H3 renders one photograph that puts the people from the reference pictures into that scene.

Typical use: environment photo + person A + person B -> one picture of both people in that environment, at the places you drew, doing what the box descriptions say.

Graph (groups in the file: Models, Conditioning, Sampling & Decoding, ref 1-4, Input Prompt):

```
LoadImage (ref 4 = CLEAN scene) --> H3BBoxCanvas.background
H3BBoxCanvas.preview (scene, no boxes drawn) --> resize --> img-ref1 --> H3 image_0 = <Picture 1>
LoadImage (ref 2, person A)  --> resize --> img-ref2 --> H3 image_1 = <Picture 2>
LoadImage (ref 3, person B)  --> resize --> img-ref3 --> H3 image_2 = <Picture 3>
LoadImage (ref 4, clean scene) --> resize --> img-ref4 --> H3 image_3 = <Picture 4>
H3BBoxCanvas.boxes --> H3LayoutPrompt.boxes (+ optional Qwen3.5 CLIP rephrase) --> PreviewAny (shows prompt) --> Set_Prompt
Get_Prompt --> MiniMaxH3ImageConditioning.prompt --> KSampler --> VAEDecode --> PreviewImage (result)
```

The Set/Get names `img-ref1..4` match the file's "ref 1-4" groups. Group "ref 1" has no Load Image: ref 1 is the canvas preview. `LoadImage` ids: 100 (person A), 104 (person B), 108 (clean scene).

## Required custom nodes

| Pack | Provides | Install |
|---|---|---|
| **ComfyUI-H3Image-LayoutKit** (https://github.com/benjiyaya/ComfyUI-H3Image-LayoutKit) | `H3BBoxCanvas`, `H3LayoutPrompt` | `cd ComfyUI/custom_nodes && git clone https://github.com/benjiyaya/ComfyUI-H3Image-LayoutKit`, restart ComfyUI, hard-refresh the browser (Ctrl+F5). No pip dependencies. Classic (Nodes 1.0) LiteGraph frontend only. |
| ComfyUI-KJNodes | `SetNode` / `GetNode` (frontend-only wiring helpers) | Manager, or clone https://github.com/kijai/ComfyUI-KJNodes |
| ComfyUI-VideoHelperSuite | `VHS_LoadImagePath` (node 151) | Optional. Node 151 is an unconnected leftover with a Windows path; **delete it** instead of installing the pack. |

Everything else (`UNETLoader`, `CLIPLoader`, `VAELoader`, `MiniMaxH3ImageConditioning`, `KSampler`, `ResizeImageMaskNode`, `ResolutionSelector`, ...) is ComfyUI core (needs a ComfyUI recent enough to have the MiniMax H3 image nodes).

## Required models

| Node | Widget value in the file | Folder | Download (from the file's embedded `models`) |
|---|---|---|---|
| UNETLoader (29) | `minimax-h3\minimax_h3_image_pruned_int8_convrot.safetensors` | `models/diffusion_models/minimax-h3/` | https://huggingface.co/Comfy-Org/MiniMax-H3-Image/resolve/main/diffusion_models/minimax_h3_image_pruned_int8_convrot.safetensors |
| CLIPLoader (30), type `minimax` | `minimax-h3\qwen3vl_32b_h3_ultra_uncensored_heretic_int8_convrot.safetensors` | `models/text_encoders/minimax-h3/` | The embedded entry is `qwen3vl_32b_minimax_h3_int8_convrot.safetensors` from https://huggingface.co/Comfy-Org/MiniMax-H3/resolve/main/text_encoders/qwen3vl_32b_minimax_h3_int8_convrot.safetensors. The widget names a different (heretic/uncensored) file; use whichever you have and re-select it in the node. |
| VAELoader (31) | `minimax_h3_image_vae_fp16.safetensors` | `models/vae/` | https://huggingface.co/Comfy-Org/MiniMax-H3-Image/resolve/main/vae/minimax_h3_image_vae_fp16.safetensors |
| CLIPLoader (35), type `minimax`, feeds H3LayoutPrompt LLM rephrase | `qwen3.5_9b_int8_convrot.safetensors` | `models/text_encoders/` | The embedded entry is `qwen3.5_9b_w4a8_gptq.safetensors` from https://huggingface.co/Comfy-Org/Qwen3.5/resolve/main/text_encoders/qwen3.5_9b_w4a8_gptq.safetensors. Again the widget names another quant; re-select what you have. |

The `\` in widget values is the Windows subfolder separator. On Linux, ComfyUI lists the same files with `/`; if the file lives in the subfolder, select it from the dropdown, and in API JSON send exactly the string the server lists in `/object_info/UNETLoader`.

## Inputs: what to set

1. **Load Image nodes (100, 104, 108).** The saved names (`ComfyUI_temp_*.png`) are placeholders that will not exist on your server. Upload with `POST /upload/image` (multipart `image`, `overwrite=true`) and set the returned `name`.
   - 108 = **clean environment** photo (no people, no overlay). It feeds both the canvas `background` and `<Picture 4>`.
   - 100 = person A -> `<Picture 2>`; 104 = person B -> `<Picture 3>`.
   - The resize chain scales each to 2 megapixels, then to a multiple of 32. Do not feed pre-drawn boxes into any of them.
2. **H3BBoxCanvas (158)**, widgets `width, height, editor_state, (blank)`. Saved `1376, 768`. Set width/height to the scene's aspect. `editor_state` is a JSON string of normalized boxes (0-1 of the canvas):
   ```json
   [{"x":0.15,"y":0.22,"w":0.21,"h":0.54,"label":1,"color":"#e53935","desc":"picture 2 a young Asian man lay down on the sofa, relax and chill.","fill":false},
    {"x":0.60,"y":0.02,"w":0.16,"h":0.56,"label":2,"color":"#43a047","desc":"picture 3, the young Asian woman with blue hair, looking out the window, watching the sunset.","fill":false}]
   ```
   Rules: boxes are resolved **left-to-right**; box 1 binds to `<Picture 2>`, box 2 to `<Picture 3>`, so keep box order and image order consistent. `desc` becomes that subject verbatim: put the action/pose there, start it with `picture N` to bind explicitly. An empty `desc` auto-binds to "the exact subject shown in `<Picture i+1>`". In the UI: drag to draw, drag edges to resize, right-click deletes, `Esc` deselects. The canvas `preview` renders the background without boxes and is already wired as Picture 1; never feed a box-overlay image into an H3 image slot.
3. **H3LayoutPrompt (168)**, widgets saved as `extra_brief='', '', max_length=1024`.
   - `extra_brief`: scene-level text only (lighting, mood, background). Never put per-person verbs here; they override the per-box poses.
   - **Check `env_picture` and `coord_mode` after loading.** The file stores only three widget values, so a newer node version may fill `env_picture` with its default **1**. Here the clean scene is `<Picture 4>` (Picture 1 is the canvas preview), so set `env_picture = 4`. Leave `coord_mode = relational` (default; raw numbers can be drawn as axis ticks by H3).
   - `clip` is wired to Qwen3.5 (node 35), so LLM rephrase is on; if the model's output contains guide words or fails, the node silently falls back to its deterministic template. Disconnect `clip` for fully deterministic prompts.
   - Read the result in **PreviewAny (37)** before sampling; it must not contain "box", "rectangle", "outline", "map" or color names.
4. **Size.** `PrimitiveFloat` "Megapixels" (65) = `3` drives `ResolutionSelector` (95: `16:9 (Widescreen)`, multiple of 32) which sets `width`/`height` into `MiniMaxH3ImageConditioning` (its own saved `3104`x`3104` is overridden by those links). Library rule: do the first pass at **1280x736** (about 0.94 MP): set Megapixels to `0.94` (verify the printed width/height are 1280x736) before using the 3 MP setting. Keep canvas aspect 16:9 to match.
5. **Seed / sampler (KSampler 38):** `seed 42, fixed, steps 8, cfg 1, euler, beta, denoise 1`. Change only the seed (use `randomize` or an explicit int) for variations. Keep steps/cfg unless you swap the H3 model.
6. `MiniMaxH3ImageConditioning (32)` main `prompt` is linked from Get_Prompt; its widget text is unused.

## Driving it through the ComfyUI API

The file is **UI format**. `POST /prompt` needs **API format**.

1. Fix everything above in the UI (delete node 151, set `env_picture`, pick installed model files), then *Workflow -> Export (API)* (enable Dev mode options if the menu entry is missing). Save the result as `h3-image-edit-bbox-refs-api.json`.
2. The export resolves `SetNode`/`GetNode` into direct links. Widgets converted to inputs (`prompt`, `width`, `height`, `boxes`, `megapixels`) become links in API JSON; to override a value, change the **source node** (`PrimitiveFloat` 65, `LoadImage` filename, canvas `editor_state`), not the linked input.
3. Fields to patch per run in the API JSON (node ids as in this file, re-check after export): `100/104/108.inputs.image` (uploaded filenames), `158.inputs.editor_state` (boxes JSON string), `158.inputs.width/height`, `168.inputs.extra_brief`, `168.inputs.env_picture`, `65.inputs.value`, `38.inputs.seed`.
4. Flow: upload images via `/upload/image`; `POST /prompt {"prompt": <api json>, "client_id": "<uuid>"}`; poll `GET /history/<prompt_id>` or listen on `/ws`; fetch images with `GET /view?filename=&subfolder=&type=`.
5. The result node is `PreviewImage (63)` (type `temp`). For a saved file, add a `SaveImage` fed from `VAEDecode (42)` in the UI before exporting.
6. `H3BBoxCanvas` stores boxes in its `editor_state` widget; if the API run ignores your boxes, confirm the key name in `/object_info/H3BBoxCanvas` for the installed version.

## Outputs

- `PreviewImage 63`: final composed image (one picture, people at drawn places).
- `PreviewImage 157`: canvas preview (background only; for your eyes, also feeds Picture 1).
- `PreviewAny 37`: the final text prompt sent to H3. Save it with the result for reproducibility.

## Common failures

| Symptom | Cause / fix |
|---|---|
| Red nodes `H3BBoxCanvas` / `H3LayoutPrompt` | LayoutKit not installed or browser not hard-refreshed. Install, restart, Ctrl+F5. Nodes 2.0 frontend is not supported. |
| `SetNode`/`GetNode` missing | Install ComfyUI-KJNodes. |
| `VHS_LoadImagePath` missing | Delete node 151 (unused). |
| Validation error "value not in list" for a model | Widget names a Windows-subfolder or another quant; select the installed file in the node. |
| Load Image error / blank | Placeholder `ComfyUI_temp_*.png` names; upload your own images. |
| Output is split panels, a collage or has axis numbers | `coord_mode` not `relational`, or the boxes were drawn into an image slot. Check PreviewAny for guide words. |
| People swapped or generic | Box order does not match `image_N` order, or `desc` lacks `picture N`. Boxes bind left-to-right. |
| Wrong environment / new room | `env_picture` is 1 instead of 4, or ref 4 is not a clean scene. |
| Stiff standing figures | Per-person verbs placed in `extra_brief`; move them into box `desc`. |
| Out of memory | Reduce Megapixels (use 0.94 for 1280x736), use the int8 files shown above. |
| LLM rephrase empty/odd | CLIPLoader 35 file missing or not generation-capable; disconnect `clip` on node 168 to use the template. |
