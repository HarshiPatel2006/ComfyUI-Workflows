# ComfyUI Workflows: 568 Free FLUX, Qwen-Image, Wan, LTX-2, MiniMax H3 and Krea 2 Workflows

[![Workflows](https://img.shields.io/badge/workflows-568-blue)](#workflow-categories) [![ComfyUI](https://img.shields.io/badge/ComfyUI-workflows-green)](https://github.com/Comfy-Org/ComfyUI) [![Format](https://img.shields.io/badge/format-JSON-lightgrey)](#how-to-use) [![License](https://img.shields.io/badge/license-MIT%20%2B%20original%20terms-purple)](#license)

A categorized library of **568 ready-to-use ComfyUI workflows** (`.json`) for **FLUX.2 / FLUX.3 Klein, Qwen-Image, Krea 2, Z-Image Turbo, Wan 2.1 / 2.2, LTX-2, MiniMax H3, SeedVR2** and more. It covers **text-to-image (txt2img)**, **image editing (img2img)**, **inpainting and outpainting**, **background removal**, **image and video upscaling**, **text-to-video and image-to-video**, **lip-sync and talking avatars**, **face swap and character swap**, **text-to-speech and music**, **image-to-3D**, **batch automation** and a complete **AI short-film pipeline**.

Every workflow is a standalone ComfyUI file: drag it onto the ComfyUI canvas, install any missing custom nodes with ComfyUI-Manager, add the models, and press **Run**.

## Table of contents

- [Quick start](#quick-start)
- [Workflow categories](#workflow-categories)
- [Supported models and tasks](#supported-models-and-tasks)
- [How to use](#how-to-use)
- [Requirements](#requirements)
- [Repository structure and naming](#repository-structure-and-naming)
- [Contributing](#contributing)
- [Credits](#credits)
- [License](#license)

## Quick start

1. Install [ComfyUI](https://github.com/Comfy-Org/ComfyUI) (or the [Desktop app](https://www.comfy.org/download)) and make sure [ComfyUI-Manager](https://github.com/Comfy-Org/ComfyUI-Manager) is available.
2. Pick a workflow from a [category README](#workflow-categories) (or clone this repo) and **drag the `.json` onto the ComfyUI canvas**.
3. Open **Manager → Install Missing Custom Nodes**, restart ComfyUI, download the listed models into `ComfyUI/models/…`, then click **Run**.

## Workflow categories

568 workflows: 528 in the normal UI format and 40 in API format (filenames ending in `-api`). Each category README lists every workflow in that folder with what it does, the models it loads and the custom nodes it needs; the version-conflicts folder lists the models and what differs from the library copy. For one flat list of all files, see [`00-LIBRARY-INDEX.md`](00-LIBRARY-INDEX.md).

| Category | What is inside | Workflows |
|---|---|---|
| [01 · Image Generation](01-Image-Generation/README.md) | Text-to-image with FLUX.2 / FLUX.3 Klein, Qwen-Image 2.1, Krea 2, Z-Image Turbo, Ming Image, MOSS, SD 1.5; ControlNet, LLM prompt enhancers, logos, posters, text in images, transparent PNGs, prompt batches | 113 |
| [02 · Image Editing](02-Image-Editing/README.md) | Instruction-based editing, multi-image edits, inpainting, outpainting, object removal, background removal, outfit transfer, sketch-to-image | 113 |
| [03 · Image Upscaling and Enhancement](03-Image-Enhancement/README.md) | Image upscaling (SeedVR2, tiled diffusion, creative upscale), filters and color grading | 13 |
| [04 · AI Video](04-Video/README.md) | Text-to-video, image-to-video, first/last frame, reference-to-video, lip-sync, video dubbing, character animation and swap, video upscaling | 125 |
| [05 · Audio](05-Audio/README.md) | Text-to-speech, voice cloning, voice design, music and sound effects | 17 |
| [06 · 3D Generation](06-3D-Generation/README.md) | Image-to-3D and multi-view-to-3D with Trellis 2, Pixal3D, SAM3D Body | 13 |
| [07 · Batch Processing and Automation](07-Batch-and-Automation/README.md) | Batch-process a folder of images, loops, switches, logic and math | 44 |
| [08 · Testing and Comparison](08-Testing-and-Comparison/README.md) | XY plots, sampler and LoRA comparisons, image compare | 8 |
| [09 · AI Short Film Pipeline](09-Movie/README.md) | Krea 2 storyboard + MiniMax H3 short-film director pipeline and real project files | 48 |
| [10 · LLM and Prompt Tools](10-LLM-and-Prompt-Tools/README.md) | Prompt enhancers and image / video / audio to prompt with Gemma 4, Qwen 3.5, Qwen3-VL | 15 |
| [90 · Docs and Resources](90-Docs-and-Resources/README.md) | Learning workflows, node demos, LoRA conversion, tutorial episode resources | 15 |
| [91 · Version Conflicts](91-Review-Version-Conflicts/README.md) | Original versions of workflows whose library copy differs, kept for comparison | 44 |

## Supported models and tasks

| Model family | Tasks covered | Folders |
|---|---|---|
| **FLUX.2 Klein** (4B / 9B, FP8, INT8, KV) | txt2img, image edit, multi-image edit, inpainting, outpainting, batch edits, XY plots | [01](01-Image-Generation) · [02](02-Image-Editing) · [07](07-Batch-and-Automation) · [08](08-Testing-and-Comparison) |
| **FLUX.3 Klein** | txt2img, text in images, image editing, prompt upsampling | [01](01-Image-Generation) · [02](02-Image-Editing) |
| **FLUX.1 dev / Qwen-Image / Z-Image (Nunchaku)** | fast 4-bit txt2img, tiled diffusion upscale | [01](01-Image-Generation) · [03](03-Image-Enhancement) |
| **Qwen-Image 2.1** | txt2img, image editing, transparent PNG, image-to-prompt | [01](01-Image-Generation) · [02](02-Image-Editing) |
| **Krea 2** (FP8 / INT8) | txt2img, edit LoRA, outfit transfer, storyboards, LoRA XY plot | [01](01-Image-Generation) · [02](02-Image-Editing) · [09](09-Movie) |
| **Z-Image Turbo** | fast txt2img, ControlNet Union, LoRA, text overlay, character sheets | [01](01-Image-Generation) |
| **Ming Image 0.1** | logos, posters, infographics, thumbnails, app screens | [01](01-Image-Generation) · [02](02-Image-Editing) |
| **MOSS Image** | txt2img, text in images, layout with boxes, image-to-prompt, text editing, upscale | [01](01-Image-Generation) · [02](02-Image-Editing) · [03](03-Image-Enhancement) |
| **P-H3 Image** (MiniMax H3 image LoRA) | txt2img, text in images, character sheets, single- and multi-image edits, outpainting, relight, restore, creative upscale | [01](01-Image-Generation) · [02](02-Image-Editing) · [03](03-Image-Enhancement) |
| **Stable Diffusion 1.5** (Juggernaut Reborn), Anima, Boogu, ERNIE Image | txt2img, img2img, ControlNet Canny, LoRA, anime | [01](01-Image-Generation) · [02](02-Image-Editing) |
| **Wan 2.1 / Wan 2.2** (SCAIL 2, InfiniteTalk, Animate) | img2video, character animation, character replacement, talking video, video dubbing | [04](04-Video) |
| **LTX-2** | img2video with audio, lip-sync to your audio, voice dubbing | [04](04-Video) |
| **MiniMax H3 / FastH3** | txt2video, img2video (first / last frame), reference-to-video with audio, character swap, short films | [04](04-Video) · [09](09-Movie) · [10](10-LLM-and-Prompt-Tools) |
| **SeedVR2** | image upscale, video upscale | [03](03-Image-Enhancement) · [04](04-Video) |
| **Trellis 2, Pixal3D, SAM3D Body** | image-to-3D, multi-view-to-3D, PBR textures, 3D body | [06](06-3D-Generation) |
| **Qwen3-TTS, Fish S2, ChatterBox** | text-to-speech, voice cloning, voice design, dialogue | [05](05-Audio) |
| **Stable Audio 3, ACE-Step 1.5, MiniMax Music 3** | music generation, lyrics | [05](05-Audio) |
| **Gemma 4, Qwen 3.5, Qwen3-VL** | prompt enhancer, image / video / audio to prompt | [10](10-LLM-and-Prompt-Tools) |
| **BiRefNet, SAM3, RMBG, LaMa, ReActor** | background removal, segmentation, object removal, face swap | [02](02-Image-Editing) · [04](04-Video) |

## How to use

### 1. Install ComfyUI

- **Windows, easiest:** the [ComfyUI Desktop app](https://www.comfy.org/download) or the portable [ComfyUI-Easy-Install](https://github.com/Tavris1/ComfyUI-Easy-Install).
- **Any OS / cloud GPU (RunPod etc.):** clone [ComfyUI](https://github.com/Comfy-Org/ComfyUI) and follow its install guide, or see the [official docs](https://docs.comfy.org).
- Update to a recent ComfyUI version. Many workflows use subgraphs and newer core nodes that older versions cannot open.

### 2. Load a workflow

- Download a single file (open it on GitHub → **Download raw file**) or clone everything:

  ```bash
  git clone https://github.com/HarshiPatel2006/ComfyUI-Workflows.git
  ```

- **Drag the `.json` file onto the ComfyUI canvas**, or use **Workflow → Open**.
- Tip: copy the folders into `ComfyUI/user/default/workflows/` to browse them from the ComfyUI workflow sidebar.

### 3. Install missing custom nodes

Open **Manager → Install Missing Custom Nodes**, install everything listed, then restart ComfyUI. The [custom node packs](#custom-node-packs) table links every pack used in this repo. Workflows marked **Core only** need no extra nodes.

### 4. Download the models and put them in the right folder

The **Models used** column in each [category README](#workflow-categories) shows the exact filenames each workflow loads. Most workflows include download links in a note on the canvas, and ComfyUI offers to download embedded model links when it detects missing models.

| Model type | Folder |
|---|---|
| Diffusion models / UNet (FLUX, Qwen-Image, Krea 2, Wan, LTX-2, MiniMax H3, Z-Image) | `ComfyUI/models/diffusion_models/` |
| GGUF models (ComfyUI-GGUF) | `ComfyUI/models/diffusion_models/` (or `models/unet/`) |
| All-in-one checkpoints (SD 1.5, Z-Image AIO) | `ComfyUI/models/checkpoints/` |
| Text encoders (Qwen3, Qwen3-VL, T5, UMT5, Gemma) | `ComfyUI/models/text_encoders/` |
| VAE | `ComfyUI/models/vae/` |
| LoRA | `ComfyUI/models/loras/` |
| CLIP Vision | `ComfyUI/models/clip_vision/` |
| ControlNet / model patches | `ComfyUI/models/controlnet/`, `ComfyUI/models/model_patches/` |
| Upscale models (4x ESRGAN-style) | `ComfyUI/models/upscale_models/` |
| Audio encoders | `ComfyUI/models/audio_encoders/` |
| Models used by a specific custom node (SeedVR2, InfiniteTalk, ReActor, LatentSync, TTS…) | the folder that node's README specifies |

If a loader shows a subfolder (for example `h3\` or `sd15\`), either create that subfolder or simply re-select the model in the loader node.

### 5. Run

Set your inputs (images, video, audio, prompt) in the input nodes, which are usually green or grouped as **Inputs**, and click **Run**. Variants named *Low VRAM*, *INT8*, *FP8*, *GGUF* or *8-Step* trade some quality for speed and memory.

### API-format workflows (`-api.json`)

Files ending in `-api` are exported in ComfyUI's API (prompt) format from real runs. They can be opened in ComfyUI like any workflow (the graph is auto-laid-out) or sent to the ComfyUI HTTP API (`POST /prompt`). They contain the input filenames and settings of the original run, so replace those before running.

### Paid API nodes

Workflows marked *PAID API* use ComfyUI partner nodes (for example Nano Banana Pro, Recraft, Seedream) and need a Comfy account with credits.

## Requirements

- **ComfyUI**: a current build (2026). Older builds may not load subgraph-based workflows.
- **ComfyUI-Manager**: to install the custom node packs below.
- **GPU**: an NVIDIA GPU is recommended. Image workflows have *Low VRAM*, *FP8*, *INT8* and *GGUF* variants for 8–12 GB cards; video workflows (Wan, LTX-2, MiniMax H3) generally need 16–24 GB+ or a cloud GPU.
- **Disk space**: models range from a few hundred MB to 20+ GB each.
- **Python**: whatever your ComfyUI install ships with. Some custom nodes have extra requirements, which ComfyUI-Manager installs.

### Custom node packs


| Custom node pack | Used by | Link |
|---|---|---|
| ComfyUI-Pixaroma | 355 workflows | [github.com/pixaroma/ComfyUI-Pixaroma](https://github.com/pixaroma/ComfyUI-Pixaroma) |
| ComfyUI-VideoHelperSuite | 55 workflows | [github.com/Kosinkadink/ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite) |
| rgthree-comfy | 59 workflows | [github.com/rgthree/rgthree-comfy](https://github.com/rgthree/rgthree-comfy) |
| ComfyUI-KJNodes | 50 workflows | [github.com/kijai/ComfyUI-KJNodes](https://github.com/kijai/ComfyUI-KJNodes) |
| comfyui-krea2edit | 38 workflows | [github.com/lbouaraba/comfyui-krea2edit](https://github.com/lbouaraba/comfyui-krea2edit) |
| ComfyUI-MiniMaxH3-Context-Loop | 31 workflows | [github.com/ethanfel/ComfyUI-MiniMaxH3-Context-Loop](https://github.com/ethanfel/ComfyUI-MiniMaxH3-Context-Loop) |
| ComfyUI-Krea2T-Enhancer | 30 workflows | [github.com/capitan01R/ComfyUI-Krea2T-Enhancer](https://github.com/capitan01R/ComfyUI-Krea2T-Enhancer) |
| ComfyUI-Spectrum-MiniMax-H3 | 30 workflows | [github.com/xmarre/ComfyUI-Spectrum-MiniMax-H3](https://github.com/xmarre/ComfyUI-Spectrum-MiniMax-H3) |
| ComfyUI-MultiShot-Plan | 28 workflows | [github.com/CodingWithShahzaib/ComfyUI-MultiShot-Plan](https://github.com/CodingWithShahzaib/ComfyUI-MultiShot-Plan) |
| ComfyUI_LayerStyle | 27 workflows | [github.com/chflame163/ComfyUI_LayerStyle](https://github.com/chflame163/ComfyUI_LayerStyle) |
| ComfyUI-Easy-Use | 27 workflows | [github.com/yolain/ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) |
| ComfyUI-WanVideoWrapper | 14 workflows | [github.com/kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper) |
| ComfyUI-RMBG | 13 workflows | [github.com/1038lab/ComfyUI-RMBG](https://github.com/1038lab/ComfyUI-RMBG) |
| ComfyUI-SeedVR2_VideoUpscaler | 11 workflows | [github.com/numz/ComfyUI-SeedVR2_VideoUpscaler](https://github.com/numz/ComfyUI-SeedVR2_VideoUpscaler) |
| ComfyUI-GGUF | 10 workflows | [github.com/city96/ComfyUI-GGUF](https://github.com/city96/ComfyUI-GGUF) |
| ComfyUI-Qwen-TTS | 11 workflows | [github.com/flybirdxx/ComfyUI-Qwen-TTS](https://github.com/flybirdxx/ComfyUI-Qwen-TTS) |
| ComfyUI-DubSync (local) | 7 workflows | Local pack, not published |
| ComfyUI-WanAnimatePreprocess | 7 workflows | [github.com/kijai/ComfyUI-WanAnimatePreprocess](https://github.com/kijai/ComfyUI-WanAnimatePreprocess) |
| wan-scail2-gap | 7 workflows | [github.com/GeekatplayStudio/wan-scail2-gap](https://github.com/GeekatplayStudio/wan-scail2-gap) |
| ComfyUI-Easy-Sam3 | 5 workflows | [github.com/yolain/ComfyUI-Easy-Sam3](https://github.com/yolain/ComfyUI-Easy-Sam3) |
| ComfyUI-MelBandRoFormer | 5 workflows | [github.com/kijai/ComfyUI-MelBandRoFormer](https://github.com/kijai/ComfyUI-MelBandRoFormer) |
| ComfyUI-nunchaku | 5 workflows | [github.com/nunchaku-ai/ComfyUI-nunchaku](https://github.com/nunchaku-ai/ComfyUI-nunchaku) |
| ComfyUI-ChatterboxTTS | 4 workflows | [github.com/Yuan-ManX/ComfyUI-ChatterboxTTS](https://github.com/Yuan-ManX/ComfyUI-ChatterboxTTS) |
| comfy_mtb | 3 workflows | [github.com/melMass/comfy_mtb](https://github.com/melMass/comfy_mtb) |
| ComfyUI-Custom-Scripts | 3 workflows | [github.com/pythongosssss/ComfyUI-Custom-Scripts](https://github.com/pythongosssss/ComfyUI-Custom-Scripts) |
| comfyui-fish-audio-s2 | 5 workflows | [registry.comfy.org/nodes/comfyui-fish-audio-s2](https://registry.comfy.org/nodes/comfyui-fish-audio-s2) |
| ComfyUI-Inpaint-CropAndStitch | 3 workflows | [github.com/lquesada/ComfyUI-Inpaint-CropAndStitch](https://github.com/lquesada/ComfyUI-Inpaint-CropAndStitch) |
| comfyui_controlnet_aux | 3 workflows | [github.com/Fannovel16/comfyui_controlnet_aux](https://github.com/Fannovel16/comfyui_controlnet_aux) |
| ComfyUI-QwenVL | 2 workflows | [github.com/1038lab/ComfyUI-QwenVL](https://github.com/1038lab/ComfyUI-QwenVL) |
| ComfyUI-SCAIL-Pose | 2 workflows | [github.com/kijai/ComfyUI-SCAIL-Pose](https://github.com/kijai/ComfyUI-SCAIL-Pose) |
| comfyui-yaser-nodes | 2 workflows | [github.com/YaserJaradeh/comfyui-yaser-nodes](https://github.com/YaserJaradeh/comfyui-yaser-nodes) |
| audio-separation-nodes-comfyui | 1 workflow | [github.com/christian-byrne/audio-separation-nodes-comfyui](https://github.com/christian-byrne/audio-separation-nodes-comfyui) |
| ComfyUI-iTools | 1 workflow | [github.com/MohammadAboulEla/ComfyUI-iTools](https://github.com/MohammadAboulEla/ComfyUI-iTools) |
| ComfyUI-MemoryCleaner | 1 workflow | [github.com/eddyhhlure1Eddy/ComfyUI-MemoryCleaner](https://github.com/eddyhhlure1Eddy/ComfyUI-MemoryCleaner) |
| ComfyUI-MiniMaxH3-TimelineDirector | 1 workflow | [github.com/Songssx/ComfyUI-MiniMaxH3-TimelineDirector](https://github.com/Songssx/ComfyUI-MiniMaxH3-TimelineDirector) |
| ComfyUI-MiniMaxH3-Unified | 1 workflow | [github.com/yusu-02/ComfyUI-MiniMaxH3-Unified](https://github.com/yusu-02/ComfyUI-MiniMaxH3-Unified) |
| ComfyUI-ReActor | 1 workflow | [github.com/Gourieff/ComfyUI-ReActor](https://github.com/Gourieff/ComfyUI-ReActor) |
| ComfyUI-SeedVR2_VideoUpscaler | 1 workflow | [github.com/ainvfx/ComfyUI-SeedVR2_VideoUpscaler](https://github.com/ainvfx/ComfyUI-SeedVR2_VideoUpscaler) |
| ComfyUI-Unload-Model | 1 workflow | [github.com/SeanScripts/ComfyUI-Unload-Model](https://github.com/SeanScripts/ComfyUI-Unload-Model) |
| ComfyUI_ChatterBox_SRT_Voice | 1 workflow | [github.com/diodiogod/ComfyUI_ChatterBox_SRT_Voice](https://github.com/diodiogod/ComfyUI_ChatterBox_SRT_Voice) |
| ComfyUI_Comfyroll_CustomNodes | 1 workflow | [github.com/Suzie1/ComfyUI_Comfyroll_CustomNodes](https://github.com/Suzie1/ComfyUI_Comfyroll_CustomNodes) |

`H3SigmaRefiner` and `RH_DLSS5Enhance` (used by one MiniMax H3 4K workflow) come from a pack that could not be identified.

## Repository structure and naming

```text
ComfyUI-Workflows/
├── 01-Image-Generation/                  # Image Generation
├── 02-Image-Editing/                     # Image Editing
├── 03-Image-Enhancement/                 # Image Upscaling and Enhancement
├── 04-Video/                             # AI Video
├── 05-Audio/                             # Audio
├── 06-3D-Generation/                     # 3D Generation
├── 07-Batch-and-Automation/              # Batch Processing and Automation
├── 08-Testing-and-Comparison/            # Testing and Comparison
├── 09-Movie/                             # AI Short Film Pipeline
├── 10-LLM-and-Prompt-Tools/              # LLM and Prompt Tools
├── 90-Docs-and-Resources/                # Docs and Resources
├── 91-Review-Version-Conflicts/          # Version Conflicts
├── 00-LIBRARY-INDEX.md                    # plain list of every workflow
└── README.md
```

Filenames follow `model-task-variant.json` in lowercase kebab-case, for example `krea-2-txt2img-extra-pass-lora.json` or `wan-2.2-img2video-gguf-lightx2v-4-step.json`. Common abbreviations: `txt2img` (text-to-image), `img2img` (image-to-image), `img2video` (image-to-video), `txt2video` (text-to-video), `video2video` (video-to-video). A trailing `-api` means API format; `epNN` marks the tutorial episode a variant came from; `-starter` marks a beginner version.

Each category folder has its own `README.md` listing every workflow with what it does, the models it loads and the custom nodes it needs. The version-conflicts folder lists the models and what differs from the library copy instead.

## Contributing

Contributions are welcome: new workflows, fixes, better descriptions and model links.

1. Fork the repo and create a branch.
2. Put the workflow in the folder that matches its main job, and name it `model-task-variant.json` in kebab-case.
3. Before committing, open the JSON and remove anything private: API keys or tokens in node inputs, and personal file paths (for example `C:\Users\<you>\…`).
4. Add a note inside the workflow with model download links, and add a row to the table in that folder's `README.md` and to [`00-LIBRARY-INDEX.md`](00-LIBRARY-INDEX.md).
5. Open a pull request describing what the workflow does and what it needs.

Found a broken workflow or a missing model link? Please [open an issue](https://github.com/HarshiPatel2006/ComfyUI-Workflows/issues).

## Credits

Workflows in this collection come from several creators. Original authors, where known:

- **Pixaroma** ([YouTube](https://www.youtube.com/@pixaroma)): about two-thirds of the library, from the Pixaroma ComfyUI tutorial series: most of the image generation, image editing, audio, 3D, batch, testing and LLM-tool workflows, many of the video workflows, the `pixaroma-nodes-*` demos, and the originals in `91-Review-Version-Conflicts`.
- **Geekatplay Studio** ([YouTube](https://www.youtube.com/@geekatplay)): the Wan 2.1 SCAIL 2 GAP character-animation workflows.
- **Benji's AI Playground** ([YouTube](https://www.youtube.com/@benjisaiplayground)): the Wan InfiniteTalk avatar generator, which the InfiniteTalk video-dubbing workflows build on.
- **MDMZ**: the MiniMax H3 character-swap method (`minimax-h3-character-swap-sam3-mdmz-v1`).
- **Comfy Org**: official ComfyUI templates (Z-Image Turbo character sheets).
- **ComfyUI-Easy-Install** by [Tavris1](https://github.com/Tavris1/ComfyUI-Easy-Install): the `-starter` workflows.
- **Harshit Patel** ([@HarshiPatel2006](https://github.com/HarshiPatel2006)): the Short Film Director pipeline and short-film projects, DubSync / LatentSync lip-sync workflows, API-format runs, and the curation and organization of this library.

Thanks also to the authors of every [custom node pack](#custom-node-packs) and to the teams behind the models (Black Forest Labs, Alibaba Qwen, Krea, MiniMax, Wan, Lightricks, ByteDance and others). If you are the author of a workflow here and want a credit added, changed or removed, please open an issue.

## License

- Workflows created for this repository (see [Credits](#credits)) are released under the **MIT License**.
- Workflows from other creators remain under their original authors' terms. Check the notes inside each workflow and the creator links above before redistributing.
- Models and custom nodes are **not** included and are covered by their own licenses (several models are non-commercial). Check each model's license before commercial use.
