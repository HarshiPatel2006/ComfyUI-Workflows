# Image Editing — ComfyUI workflows

Workflows that change or analyse an existing image: instruction edits, multi-image edits, inpaint / outpaint / object removal, outfit and pose changes, sketch- and 3D-to-image, relighting, identity and reference adapters, restoration (face, denoise, low-light, colorization), filters, background removal, segmentation, depth, pose, captioning / OCR, LayerDiffusion layers and virtual try-on.

[← 01-Image overview](../README.md) · [Library index](../../00-LIBRARY-INDEX.md)

**243 workflows** in **56 model folders**. Each model folder holds only workflow files; the file name says the task first, then the variant: `<task>[-<variant>][-<size>][-<precision>][-<feature>].json`. `Other/` holds generic or multi-model workflows.

## Model folders

| Model | Workflows | Tasks |
|---|---|---|
| [Anima](#anima) | 1 | `inpaint` |
| [AnyDoor](#anydoor) | 1 | `object-insertion` |
| [BiRefNet](#birefnet) | 1 | `remove-background` |
| [Boogu](#boogu) | 3 | `edit` |
| [CatVTON](#catvton) | 3 | `try-on` |
| [CodeFormer](#codeformer) | 1 | `face-restore` |
| [DDColor](#ddcolor) | 1 | `colorize` |
| [Depth-Anything](#depth-anything) | 4 | `depth-map`, `point-cloud` |
| [DiffBIR](#diffbir) | 2 | `denoise`, `face-restore` |
| [DWPose](#dwpose) | 1 | `pose-keypoints` |
| [FIBO](#fibo) | 2 | `edit` |
| [Florence-2](#florence-2) | 5 | `caption`, `document-vqa`, `object-detection`, `ocr`, `segment` |
| [FLUX-1](#flux-1) | 4 | `edit`, `inpaint`, `outpaint`, `variation` |
| [FLUX-2](#flux-2) | 37 | `3d-to-image`, `character-sheet`, `character-turnaround`, `edit`, `inpaint`, `multi-edit`, `outpaint`, `paint-guided-edit`, `paint-to-image` |
| [FLUX-3](#flux-3) | 14 | `character-sheet`, `edit`, `inpaint`, `multi-edit`, `outfit-change`, `outpaint`, `relight`, `restore`, `restyle`, `text-edit` |
| [GFPGAN](#gfpgan) | 1 | `face-restore` |
| [GPEN](#gpen) | 1 | `face-restore` |
| [Grounding-DINO](#grounding-dino) | 3 | `segment` |
| [HiDream](#hidream) | 4 | `edit` |
| [IC-Light](#ic-light) | 5 | `relight` |
| [IDM-VTON](#idm-vton) | 1 | `try-on` |
| [InstantID](#instantid) | 5 | `identity` |
| [InstructPix2Pix](#instructpix2pix) | 1 | `edit` |
| [IP-Adapter](#ip-adapter) | 11 | `identity`, `reference` |
| [Kolors](#kolors) | 2 | `img2img`, `inpaint` |
| [Krea-2](#krea-2) | 6 | `edit`, `outfit-change`, `outfit-transfer`, `style-reference` |
| [LaMa](#lama) | 1 | `object-removal` |
| [LayerDiffusion](#layerdiffusion) | 4 | `layers` |
| [Leffa](#leffa) | 1 | `try-on` |
| [LongCat-Image](#longcat-image) | 1 | `edit` |
| [MagicQuill](#magicquill) | 1 | `edit` |
| [Marigold](#marigold) | 2 | `depth-map` |
| [MiDaS](#midas) | 1 | `depth-map` |
| [Ming-Image](#ming-image) | 5 | `edit`, `multi-edit`, `restyle`, `sketch-to-image` |
| [MiniMax-H3](#minimax-h3) | 3 | `edit`, `multi-edit` |
| [MOSS-Image](#moss-image) | 2 | `edit`, `text-edit` |
| [NAFNet](#nafnet) | 1 | `denoise` |
| [OmniGen](#omnigen) | 5 | `edit`, `multi-edit` |
| [OOTDiffusion](#ootdiffusion) | 1 | `try-on` |
| [P-H3](#p-h3) | 13 | `character-sheet`, `edit`, `inpaint`, `multi-edit`, `outfit-change`, `outpaint`, `relight`, `restore-and-colorize`, `restyle`, `text-edit` |
| [Paint-by-Example](#paint-by-example) | 2 | `object-insertion` |
| [PhotoMaker](#photomaker) | 4 | `identity` |
| [PowerPaint](#powerpaint) | 2 | `object-removal`, `outpaint` |
| [PuLID](#pulid) | 4 | `identity` |
| [Qwen-Image](#qwen-image) | 26 | `character-sheet`, `edit`, `inpaint`, `multi-edit`, `outfit-change`, `outpaint`, `pose-change`, `relight`, `remove-background`, `sketch-to-image` |
| [Restormer](#restormer) | 1 | `denoise` |
| [Retinexformer](#retinexformer) | 1 | `low-light-enhance` |
| [RMBG](#rmbg) | 1 | `remove-background` |
| [SAM-3](#sam-3) | 2 | `remove-background`, `segment` |
| [SCUNet](#scunet) | 1 | `denoise` |
| [SD15](#sd15) | 8 | `img2img`, `inpaint`, `outpaint` |
| [SDXL](#sdxl) | 4 | `inpaint`, `variation` |
| [Stable-Cascade](#stable-cascade) | 4 | `img2img`, `inpaint`, `variation` |
| [StoryMaker](#storymaker) | 1 | `identity` |
| [WD14-Tagger](#wd14-tagger) | 1 | `tag` |
| [Other](#other) | 20 | `filters`, `image-blend`, `image-combiner`, `image-scale`, `image-stitch`, `image-transformation`, `pixaroma`, `remove-background` |

## Anima

Folder: [`Anima/`](Anima) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [inpaint-lllite](Anima/inpaint-lllite.json) | Anime inpainting with LLLite inpaint control | [link](https://huggingface.co/circlestone-labs/Anima) | — | Model: Anima; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_anima_lllite_image_inpainting.json); Licence: Check Anima model card (non-commercial terms); Tested: not runtime-tested |

## AnyDoor

Folder: [`AnyDoor/`](AnyDoor) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [object-insertion](AnyDoor/object-insertion.json) | Teleport a reference object into a masked region of a scene | [weights](https://huggingface.co/xichenhku/AnyDoor) | ComfyUI_AnyDoor | Model: AnyDoor; Source: [source](https://github.com/smthemex/ComfyUI_AnyDoor/blob/main/examples/img2img.json); Licence: Code MIT; review AnyDoor weight terms; Tested: not runtime-tested |

## BiRefNet

Folder: [`BiRefNet/`](BiRefNet) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [remove-background](BiRefNet/remove-background.json) | Remove Background | `birefnet.safetensors` | ComfyUI-Pixaroma | — |

## Boogu

Folder: [`Boogu/`](Boogu) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [edit-fp8](Boogu/edit-fp8.json) | Single-reference editing with the full (non-Turbo) Edit model | [link](https://huggingface.co/Comfy-Org/Boogu-Image/resolve/main/diffusion_models/boogu_image_edit_fp8_scaled.safetensors) | — | Model: Boogu Image 0.1 Edit; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_boogu_image_0_1_edit.json); Licence: Check Boogu model card; Tested: not runtime-tested |
| [edit-int8-low-vram](Boogu/edit-int8-low-vram.json) | Low-VRAM INT8 variant of Boogu Edit | [link](https://huggingface.co/Comfy-Org/Boogu-Image/resolve/main/diffusion_models/boogu_image_edit_int8_convrot.safetensors) | — | Model: Boogu Image 0.1 Edit; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_boogu_image_0_1_edit_int8.json); Licence: Check Boogu model card; Tested: not runtime-tested |
| [edit](Boogu/edit.json) | One Image Edit | `qwen3vl_8b_fp8_scaled.safetensors`, `ae.safetensors`, `boogu_image_edit_turbo_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |

## CatVTON

Folder: [`CatVTON/`](CatVTON) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [try-on-automask](CatVTON/try-on-automask.json) | Try-on with automatic upper/lower/overall clothing mask | [zhengchong/CatVTON](https://huggingface.co/zhengchong/CatVTON) | Comfyui-CatVTON | Model: CatVTON; Source: [pzc163/Comfyui-CatVTON](https://github.com/pzc163/Comfyui-CatVTON); Licence: Weights CC BY-NC-SA 4.0 (non-commercial) |
| [try-on-flux-lora-auto-mask](CatVTON/try-on-flux-lora-auto-mask.json) | Try-on with FLUX.1 Fill + CatVTON LoRA, core sampler nodes, auto clothes mask | [xiaozaa/catvton-flux-lora-alpha](https://huggingface.co/xiaozaa/catvton-flux-lora-alpha), [FLUX.1-Fill-dev](https://huggingface.co/black-forest-labs/FLUX.1-Fill-dev) | Comfyui_segformer_b2_clothes, comfyui-in-context-lora-utils | Model: CatVTON-FLUX (LoRA); Source: [nomadoor/Comfy-with-ComfyUI](https://github.com/nomadoor/Comfy-with-ComfyUI/tree/main/src/workflows/ai-capabilities/virtual-try-on); Licence: LoRA CC BY-NC-SA 4.0; FLUX.1 [dev] non-commercial licence |
| [try-on-flux-sam2-point-mask](CatVTON/try-on-flux-sam2-point-mask.json) | Try-on with the full CatVTON-FLUX model, garment mask drawn with SAM 2 points | [xiaozaa/catvton-flux-alpha](https://huggingface.co/xiaozaa/catvton-flux-alpha) | ComfyUI-CatvtonFluxWrapper, ComfyUI-segment-anything-2, ComfyUI-KJNodes, comfyui-inpaint-nodes | Model: CatVTON-FLUX (full model); Source: [lujiazho/ComfyUI-CatvtonFluxWrapper](https://github.com/lujiazho/ComfyUI-CatvtonFluxWrapper); Licence: CC BY-NC-SA 4.0; FLUX.1 [dev] non-commercial licence |

## CodeFormer

Folder: [`CodeFormer/`](CodeFormer) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [face-restore](CodeFormer/face-restore.json) | Detect and restore faces, fidelity slider | [codeformer.pth](https://github.com/sczhou/CodeFormer/releases/download/v0.1.0/codeformer.pth) | facerestore_cf | Model: CodeFormer; Source: [AI Horde hordelib pipeline](https://github.com/Haidra-Org/hordelib/blob/main/hordelib/pipeline_designs/pipeline_image_facefix.json) (model file renamed to `codeformer.pth`); Licence: S-Lab licence (non-commercial) |

## DDColor

Folder: [`DDColor/`](DDColor) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [colorize-bw-photo](DDColor/colorize-bw-photo.json) | Colorize B&W photos (API-format graph) | [piddnad/ddcolor_artistic](https://huggingface.co/piddnad/ddcolor_artistic) | ComfyUI-DDColor | Model: DDColor (artistic; paper / modelscope / tiny selectable); Source: [Intel AI Playground preset](https://github.com/intel/AI-Playground/blob/main/modes/base/presets/Colorize.json); Licence: Apache-2.0 |

## Depth-Anything

Folder: [`Depth-Anything/`](Depth-Anything) — 4 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [depth-map-v2-large](Depth-Anything/depth-map-v2-large.json) | Depth map (ControlNet input); switch the checkpoint to `vitb` for Base | [depth-anything/Depth-Anything-V2-Large](https://huggingface.co/depth-anything/Depth-Anything-V2-Large) (auto-download) | comfyui_controlnet_aux | Model: Depth Anything V2 Large; Source: [Fannovel16/comfyui_controlnet_aux](https://github.com/Fannovel16/comfyui_controlnet_aux/tree/main/examples) (example_depth_anything_v2.png); Licence: CC BY-NC 4.0 (Large); Base/Small Apache-2.0 |
| [depth-map-v2-small-low-vram](Depth-Anything/depth-map-v2-small-low-vram.json) | Low-VRAM depth map (checkpoint changed from the source) | [depth-anything/Depth-Anything-V2-Small](https://huggingface.co/depth-anything/Depth-Anything-V2-Small) (auto-download) | comfyui_controlnet_aux | Model: Depth Anything V2 Small; Source: adapted from the row above; Licence: Apache-2.0 |
| [depth-map-v3](Depth-Anything/depth-map-v3.json) | Depth map | [depth-anything](https://huggingface.co/depth-anything) DA3 models (auto-download) | ComfyUI-DepthAnythingV3 | Model: Depth Anything 3; Source: [PozzettiAndrea/ComfyUI-DepthAnythingV3](https://github.com/PozzettiAndrea/ComfyUI-DepthAnythingV3/tree/main/workflows); Licence: Check per checkpoint (Large/Giant non-commercial) |
| [point-cloud-v3](Depth-Anything/point-cloud-v3.json) | Depth to 3D point cloud (preview and save) | same | ComfyUI-DepthAnythingV3 | Model: Depth Anything 3; Source: same; Licence: same |

## DiffBIR

Folder: [`DiffBIR/`](DiffBIR) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [denoise-blind](DiffBIR/denoise-blind.json) | Blind denoise | DiffBIR-v2 + scunet_color_real_psnr | ComfyUI-DiffBIR | Model: DiffBIR v2; Source: jtscmw01 example; Licence: Apache-2.0 |
| [face-restore-blind](DiffBIR/face-restore-blind.json) | Blind face restoration | DiffBIR-v2 + face_swinir_v1 | ComfyUI-DiffBIR | Model: DiffBIR v2; Source: jtscmw01 example; Licence: Apache-2.0 |

## DWPose

Folder: [`DWPose/`](DWPose) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [pose-keypoints-openpose](DWPose/pose-keypoints-openpose.json) | Body/hand/face pose skeletons side by side (ControlNet input) | [yzd-v/DWPose](https://huggingface.co/yzd-v/DWPose), [lllyasviel/Annotators](https://huggingface.co/lllyasviel/Annotators) (auto-download) | comfyui_controlnet_aux | Model: DWPose, OpenPose; Source: [nomadoor/Comfy-with-ComfyUI](https://github.com/nomadoor/Comfy-with-ComfyUI/tree/main/src/workflows/basic-workflows/controlnet-prep); Licence: DWPose Apache-2.0; OpenPose models non-commercial (CMU licence) |

## FIBO

Folder: [`FIBO/`](FIBO) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [edit-dev-prompt-enhancer](FIBO/edit-dev-prompt-enhancer.json) | Structured (JSON-prompt) editing with VLM prompt enhancer | [link](https://huggingface.co/Comfy-Org/Fibo-2.0/resolve/main/diffusion_models/fibo2_dev_int8_convrot.safetensors) | — | Model: Fibo 2.0 Dev; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_fibo2_edit_dev_pe.json); Licence: Check Bria Fibo licence; Tested: not runtime-tested |
| [edit-turbo-prompt-enhancer](FIBO/edit-turbo-prompt-enhancer.json) | Fast structured editing with VLM prompt enhancer | [link](https://huggingface.co/Comfy-Org/Fibo-2.0/resolve/main/diffusion_models/fibo2_edit_turbo_int8_convrot.safetensors) | — | Model: Fibo 2.0 Edit Turbo; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_fibo2_edit_turbo_pe.json); Licence: Check Bria Fibo licence; Tested: not runtime-tested |

## Florence-2

Folder: [`Florence-2/`](Florence-2) — 5 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [caption-detailed](Florence-2/caption-detailed.json) | Detailed image caption (for prompts / datasets) | [microsoft/Florence-2-base-ft](https://huggingface.co/microsoft/Florence-2-base-ft) (auto-download) | ComfyUI-Florence2 | Model: Florence-2; Source: [nomadoor/Comfy-with-ComfyUI](https://github.com/nomadoor/Comfy-with-ComfyUI/tree/main/src/workflows/basic-workflows/florence2); Licence: MIT |
| [document-vqa](Florence-2/document-vqa.json) | Ask questions about a document image | same | ComfyUI-Florence2 | Model: Florence-2; Source: same; Licence: MIT |
| [object-detection](Florence-2/object-detection.json) | Detect and box objects | same | ComfyUI-Florence2 | Model: Florence-2; Source: [nomadoor/Comfy-with-ComfyUI](https://github.com/nomadoor/Comfy-with-ComfyUI/tree/main/src/workflows/ai-capabilities/object-detection); Licence: MIT |
| [ocr](Florence-2/ocr.json) | Read text in an image | same | ComfyUI-Florence2 | Model: Florence-2; Source: same; Licence: MIT |
| [segment-sam2-caption-grounded](Florence-2/segment-sam2-caption-grounded.json) | Ground a phrase with Florence-2, then mask it with SAM 2 | [Kijai/sam2-safetensors](https://huggingface.co/Kijai/sam2-safetensors), [microsoft/Florence-2-base](https://huggingface.co/microsoft/Florence-2-base) (auto-download) | ComfyUI-segment-anything-2, ComfyUI-Florence2, ComfyUI-KJNodes | Model: Florence-2 + SAM 2; Source: [kijai/ComfyUI-segment-anything-2](https://github.com/kijai/ComfyUI-segment-anything-2/tree/main/example_workflows); Licence: Apache-2.0 (SAM 2); MIT (Florence-2) |

## FLUX-1

Folder: [`FLUX-1/`](FLUX-1) — 4 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [edit-kontext-dev](FLUX-1/edit-kontext-dev.json) | Instruction edit keeping identity/layout (FP8) | [link](https://huggingface.co/Comfy-Org/flux1-kontext-dev_ComfyUI) | — | Model: FLUX.1 Kontext [dev]; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/flux_kontext_dev_basic.json); Licence: FLUX.1 [dev] Non-Commercial; Tested: not runtime-tested |
| [inpaint-fill-dev](FLUX-1/inpaint-fill-dev.json) | Mask inpainting with FLUX.1 Fill | [link](https://huggingface.co/black-forest-labs/FLUX.1-Fill-dev) | — | Model: FLUX.1 Fill [dev]; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/flux_fill_inpaint_example.json); Licence: FLUX.1 [dev] Non-Commercial; Tested: not runtime-tested |
| [outpaint-fill-dev](FLUX-1/outpaint-fill-dev.json) | Outpainting / canvas extension with FLUX.1 Fill | [link](https://huggingface.co/black-forest-labs/FLUX.1-Fill-dev) | — | Model: FLUX.1 Fill [dev]; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/flux_fill_outpaint_example.json); Licence: FLUX.1 [dev] Non-Commercial; Tested: not runtime-tested |
| [variation-dev-redux](FLUX-1/variation-dev-redux.json) | Image variation / reference prompting with Redux + SigCLIP | [link](https://huggingface.co/black-forest-labs/FLUX.1-Redux-dev) | — | Model: FLUX.1 [dev] (Redux); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/flux_redux_model_example.json); Licence: FLUX.1 [dev] Non-Commercial; Tested: not runtime-tested |

## FLUX-2

Folder: [`FLUX-2/`](FLUX-2) — 37 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [3d-to-image-klein-9b-ep33](FLUX-2/3d-to-image-klein-9b-ep33.json) | 3D Model to Image (Ep33) | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma | — |
| [3d-to-image-klein-9b-keep-the-angle-ep33](FLUX-2/3d-to-image-klein-9b-keep-the-angle-ep33.json) | 3D Model to Image — Keep the Angle (Ep33) | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma | — |
| [3d-to-image-klein-9b-keep-the-angle-ep34](FLUX-2/3d-to-image-klein-9b-keep-the-angle-ep34.json) | 3D Model to Image — Keep the Angle (Ep34) | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma | — |
| [3d-to-image-klein-9b-scene-builder](FLUX-2/3d-to-image-klein-9b-scene-builder.json) | 3D Scene Builder to Image | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma | — |
| [3d-to-image-klein-9b](FLUX-2/3d-to-image-klein-9b.json) | 3D Model to Image | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma | — |
| [character-sheet-klein-9b](FLUX-2/character-sheet-klein-9b.json) | Flux Klein - Character Sheet from One Picture (Ep41) | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [character-turnaround-klein-9b-from-one-image](FLUX-2/character-turnaround-klein-9b-from-one-image.json) | Character Turnaround Sheet from One Image | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [edit-dev-reference](FLUX-2/edit-dev-reference.json) | Text to image / edit with one reference image (Turbo LoRA) | [link](https://huggingface.co/Comfy-Org/flux2-dev) | — | Model: FLUX.2 [dev]; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_flux2.json); Licence: FLUX.2 [dev] Non-Commercial; Tested: not runtime-tested |
| [edit-klein-4b-base](FLUX-2/edit-klein-4b-base.json) | Image edit with the tunable 4B Base (FP8) | [link](https://huggingface.co/black-forest-labs/FLUX.2-klein-base-4b-fp8) | — | Model: FLUX.2 [klein] 4B Base; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_flux2_klein_image_edit_4b_base.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [edit-klein-4b-fp8-distill](FLUX-2/edit-klein-4b-fp8-distill.json) | One Image Edit | `flux-2-klein-4b-fp8.safetensors`, `qwen_3_4b.safetensors`, `flux2-vae.safetensors` | rgthree-comfy | — |
| [edit-klein-9b-base](FLUX-2/edit-klein-9b-base.json) | Image edit with the tunable 9B Base (FP8) | [link](https://huggingface.co/black-forest-labs/FLUX.2-klein-base-9b-fp8) | — | Model: FLUX.2 [klein] 9B Base; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_flux2_klein_image_edit_9b_base.json); Licence: FLUX Non-Commercial (9B); Tested: not runtime-tested |
| [edit-klein-9b-fp8-distill](FLUX-2/edit-klein-9b-fp8-distill.json) | One Image Edit | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | rgthree-comfy | — |
| [edit-klein-9b-int8](FLUX-2/edit-klein-9b-int8.json) | One Image Edit | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma | — |
| [edit-klein-9b-kv-fp8-custom-ratio](FLUX-2/edit-klein-9b-kv-fp8-custom-ratio.json) | One Image Edit (Custom Ratio) | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | rgthree-comfy | — |
| [edit-klein-9b-kv-fp8-same-ratio](FLUX-2/edit-klein-9b-kv-fp8-same-ratio.json) | One Image Edit (Same Ratio) | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | rgthree-comfy | — |
| [edit-klein-9b-one-image-many-edits](FLUX-2/edit-klein-9b-one-image-many-edits.json) | One Image, Many Edits | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [edit-klein-9b-one-image-prompts-from-list](FLUX-2/edit-klein-9b-one-image-prompts-from-list.json) | One Image, Prompts from List | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma | — |
| [edit-klein-9b-v2-notify-switch](FLUX-2/edit-klein-9b-v2-notify-switch.json) | One Image Edit V2 + Notify and Switch | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma | — |
| [edit-klein-9b-v3-dated-folder](FLUX-2/edit-klein-9b-v3-dated-folder.json) | One Image Edit V3 + Keep Filename + Save to Dated Folder | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma | — |
| [edit-klein-9b](FLUX-2/edit-klein-9b.json) | One Image Edit V1 | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma | — |
| [inpaint-klein-4b-fp8-distill](FLUX-2/inpaint-klein-4b-fp8-distill.json) | Inpaint | `flux-2-klein-4b-fp8.safetensors`, `qwen_3_4b.safetensors`, `flux2-vae.safetensors` | ComfyUI-Inpaint-CropAndStitch, rgthree-comfy | — |
| [inpaint-klein-9b-fp8-distill](FLUX-2/inpaint-klein-9b-fp8-distill.json) | Inpaint | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Inpaint-CropAndStitch, rgthree-comfy | — |
| [inpaint-klein-9b-fp8](FLUX-2/inpaint-klein-9b-fp8.json) | Inpaint (Ep22) | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma | — |
| [inpaint-klein-9b-int8](FLUX-2/inpaint-klein-9b-int8.json) | Inpaint | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma | — |
| [inpaint-klein-9b-kv-fp8](FLUX-2/inpaint-klein-9b-kv-fp8.json) | Inpaint | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | ComfyUI-Inpaint-CropAndStitch, rgthree-comfy | — |
| [multi-edit-dev-fp8-low-vram](FLUX-2/multi-edit-dev-fp8-low-vram.json) | Two-reference editing with FP8 Mistral encoder (lower VRAM) | [link](https://huggingface.co/Comfy-Org/flux2-dev) | — | Model: FLUX.2 [dev]; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_flux2_fp8.json); Licence: FLUX.2 [dev] Non-Commercial; Tested: not runtime-tested |
| [multi-edit-klein-4b-fp8-distill-2-images](FLUX-2/multi-edit-klein-4b-fp8-distill-2-images.json) | Multi-Image Edit — 2 Images | `flux-2-klein-4b-fp8.safetensors`, `qwen_3_4b.safetensors`, `flux2-vae.safetensors` | Core only | — |
| [multi-edit-klein-9b-fp8-distill-2-images](FLUX-2/multi-edit-klein-9b-fp8-distill-2-images.json) | Multi-Image Edit — 2 Images | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | Core only | — |
| [multi-edit-klein-9b-image-composer-to-image](FLUX-2/multi-edit-klein-9b-image-composer-to-image.json) | Image Composer to Image | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma | — |
| [multi-edit-klein-9b-kv-fp8-2-images](FLUX-2/multi-edit-klein-9b-kv-fp8-2-images.json) | Multi-Image Edit — 2 Images | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | Core only | — |
| [multi-edit-klein-9b-kv-fp8-3-images](FLUX-2/multi-edit-klein-9b-kv-fp8-3-images.json) | Multi-Image Edit — 3 Images | `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors`, `flux2-vae.safetensors` | Core only | — |
| [multi-edit-klein-9b-kv-fp8-4-images](FLUX-2/multi-edit-klein-9b-kv-fp8-4-images.json) | Multi-Image Edit — 4 Images | `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors`, `flux2-vae.safetensors` | Core only | — |
| [multi-edit-klein-9b-kv-fp8-image-blend](FLUX-2/multi-edit-klein-9b-kv-fp8-image-blend.json) | Image Blend | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | ComfyUI-RMBG, ComfyUI_LayerStyle, rgthree-comfy | — |
| [outpaint-klein-9b-kv-fp8-custom-ratio](FLUX-2/outpaint-klein-9b-kv-fp8-custom-ratio.json) | Outpaint (Custom Ratio) | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | ComfyUI-KJNodes, rgthree-comfy | — |
| [outpaint-klein-9b](FLUX-2/outpaint-klein-9b.json) | Outpaint | `flux-2-klein-9b-int8-convrot.safetensors`, `pixaoutpaint.safetensors`, `qwen_3_8b_fp8mixed.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [paint-guided-edit-klein-9b-fp8-distill](FLUX-2/paint-guided-edit-klein-9b-fp8-distill.json) | Paint-Guided Edit | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma | — |
| [paint-to-image-klein-9b](FLUX-2/paint-to-image-klein-9b.json) | Paint to Image | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma | — |

## FLUX-3

Folder: [`FLUX-3/`](FLUX-3) — 14 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [character-sheet-klein](FLUX-3/character-sheet-klein.json) | Character Sheet | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [edit-klein-base](FLUX-3/edit-klein-base.json) | Image edit with the tunable Base checkpoint (INT8) | [link](https://huggingface.co/black-forest-labs/flux-3-image-klein-comfy) | — | Model: FLUX.3 Image Klein Base; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_flux3_klein_image_edit.json); Licence: Check FLUX.3 Klein licence on model card; Tested: not runtime-tested |
| [edit-klein](FLUX-3/edit-klein.json) | One Image Edit | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [inpaint-klein-edit-inside-a-box](FLUX-3/inpaint-klein-edit-inside-a-box.json) | Edit inside a Box | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [multi-edit-klein-character-in-a-scene](FLUX-3/multi-edit-klein-character-in-a-scene.json) | Character in a Scene | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [multi-edit-klein-group-photo](FLUX-3/multi-edit-klein-group-photo.json) | Group Photo | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [multi-edit-klein-logo-on-a-product](FLUX-3/multi-edit-klein-logo-on-a-product.json) | Logo on a Product | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [multi-edit-klein-product-ad](FLUX-3/multi-edit-klein-product-ad.json) | Product Ad | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [outfit-change-klein](FLUX-3/outfit-change-klein.json) | Outfit Change | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [outpaint-klein](FLUX-3/outpaint-klein.json) | Outpaint | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [relight-klein-and-seasons](FLUX-3/relight-klein-and-seasons.json) | Relight and Seasons | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [restore-klein-and-colorize](FLUX-3/restore-klein-and-colorize.json) | Restore and Colorize | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [restyle-klein](FLUX-3/restyle-klein.json) | Restyle | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [text-edit-klein-text-in-a-picture](FLUX-3/text-edit-klein-text-in-a-picture.json) | Edit Text in a Picture | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |

## GFPGAN

Folder: [`GFPGAN/`](GFPGAN) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [face-restore-v14](GFPGAN/face-restore-v14.json) | Detect and restore faces | [GFPGANv1.4.pth](https://github.com/TencentARC/GFPGAN/releases/download/v1.3.0/GFPGANv1.4.pth) | facerestore_cf | Model: GFPGAN v1.4; Source: Same pipeline, model set to GFPGAN; Licence: Apache-2.0 (see repo for bundled parts) |

## GPEN

Folder: [`GPEN/`](GPEN) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [face-restore-bfr-512-face-swap](GPEN/face-restore-bfr-512-face-swap.json) | ReActor face swap, then GPEN restore | [GPEN-BFR-512.onnx](https://huggingface.co/datasets/Gourieff/ReActor/resolve/main/models/facerestore_models/GPEN-BFR-512.onnx) | ComfyUI-GPENO, ComfyUI-ReActor | Model: GPEN-BFR-512; Source: [GPENO example](https://github.com/SparknightLLC/ComfyUI-GPENO/tree/main/workflows); Licence: GPEN non-commercial; inswapper non-commercial |

## Grounding-DINO

Folder: [`Grounding-DINO/`](Grounding-DINO) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [segment-hq-sam-text-prompt](Grounding-DINO/segment-hq-sam-text-prompt.json) | Text-prompted high-quality masks for fine edges | auto-download ([1038lab/sam](https://huggingface.co/1038lab/sam)) | ComfyUI-RMBG | Model: Grounding DINO + HQ-SAM; Source: [nomadoor/Comfy-with-ComfyUI](https://github.com/nomadoor/Comfy-with-ComfyUI/tree/main/src/workflows/data-utilities/ai-mask-generation); Licence: Apache-2.0 |
| [segment-sam-vit-h-text-prompt](Grounding-DINO/segment-sam-vit-h-text-prompt.json) | Same as above with the original SAM ViT-H (model choice changed from the source) | auto-download ([1038lab/sam](https://huggingface.co/1038lab/sam)) | ComfyUI-RMBG | Model: Grounding DINO + SAM (ViT-H); Source: adapted from the row above; Licence: Apache-2.0 |
| [segment-sam2-text-prompt](Grounding-DINO/segment-sam2-text-prompt.json) | Segment objects named in a text prompt | [facebook/sam2.1-hiera-base-plus](https://huggingface.co/facebook/sam2.1-hiera-base-plus), [ShilongLiu/GroundingDINO](https://huggingface.co/ShilongLiu/GroundingDINO) | ComfyUI-SAM2 | Model: Grounding DINO + SAM 2.1; Source: [neverbiasu/ComfyUI-SAM2](https://github.com/neverbiasu/ComfyUI-SAM2) (assets/workflow.png); Licence: Apache-2.0 |

## HiDream

Folder: [`HiDream/`](HiDream) — 4 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [edit-e1](HiDream/edit-e1.json) | Instruction image editing (E1 Full) | [link](https://huggingface.co/Comfy-Org/HiDream-I1_ComfyUI) | — | Model: HiDream-E1; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/hidream_e1_full.json); Licence: MIT (Llama 3.1 encoder: Llama licence); Tested: not runtime-tested |
| [edit-e11](HiDream/edit-e11.json) | Improved instruction editing (E1.1) | [link](https://huggingface.co/Comfy-Org/HiDream-I1_ComfyUI) | — | Model: HiDream-E1.1; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/hidream_e1_1.json); Licence: MIT (Llama 3.1 encoder: Llama licence); Tested: not runtime-tested |
| [edit-o1-dev-fp8-personalize](HiDream/edit-o1-dev-fp8-personalize.json) | Faster FP8 Dev variant of O1 editing/personalization | [link](https://huggingface.co/Comfy-Org/HiDream-O1-Image/resolve/main/checkpoints/hidream_o1_image_dev_fp8_scaled.safetensors) | — | Model: HiDream-O1 (Dev); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_hidream_o1_dev.json); Licence: Check HiDream-O1 model card; Tested: not runtime-tested |
| [edit-o1-personalize](HiDream/edit-o1-personalize.json) | Editing + subject personalization from a reference | [link](https://huggingface.co/Comfy-Org/HiDream-O1-Image/resolve/main/checkpoints/hidream_o1_image_bf16.safetensors) | — | Model: HiDream-O1; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_hidream_o1.json); Licence: Check HiDream-O1 model card; Tested: not runtime-tested |

## IC-Light

Folder: [`IC-Light/`](IC-Light) — 5 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [relight-fbc-background](IC-Light/relight-fbc-background.json) | Matte the subject and relight it to match a background image | [weights](https://huggingface.co/lllyasviel/ic-light) | ComfyUI-IC-Light, ComfyUI-KJNodes, ComfyUI-BRIA_AI-RMBG | Model: IC-Light FBC (SD 1.5); Source: [source](https://github.com/kijai/ComfyUI-IC-Light/blob/main/example_workflows/ic_light_fbc_example_02.png); Licence: Apache-2.0; Tested: not runtime-tested |
| [relight-fbc-normal-map](IC-Light/relight-fbc-normal-map.json) | Estimate a normal map from multi-light relights | [weights](https://huggingface.co/lllyasviel/ic-light) | ComfyUI-IC-Light, ComfyUI-KJNodes, ComfyUI_essentials, ComfyUI-BRIA_AI-RMBG | Model: IC-Light FBC (SD 1.5); Source: [source](https://github.com/kijai/ComfyUI-IC-Light/blob/main/example_workflows/iclight_normals_example_01.png); Licence: Apache-2.0; Tested: not runtime-tested |
| [relight-fc-gradient](IC-Light/relight-fc-gradient.json) | Relight with a spline-controlled light gradient | [weights](https://huggingface.co/lllyasviel/ic-light) | ComfyUI-IC-Light, ComfyUI-KJNodes, ComfyUI_essentials | Model: IC-Light FC (SD 1.5); Source: [source](https://github.com/kijai/ComfyUI-IC-Light/blob/main/example_workflows/iclight_example_fc_controlled_gradient_01.png); Licence: Apache-2.0; Tested: not runtime-tested |
| [relight-fc-light-sources](IC-Light/relight-fc-light-sources.json) | Relight from several preset light-source directions in one batch | [weights](https://huggingface.co/lllyasviel/ic-light) | ComfyUI-IC-Light, ComfyUI-KJNodes, ComfyUI_essentials | Model: IC-Light FC (SD 1.5); Source: [source](https://github.com/kijai/ComfyUI-IC-Light/blob/main/example_workflows/ic_light_simple_light_multi_02.png); Licence: Apache-2.0; Tested: not runtime-tested |
| [relight-fc-shaped-light](IC-Light/relight-fc-shaped-light.json) | Relight a foreground subject from a text prompt and a drawn light-shape mask | [weights](https://huggingface.co/lllyasviel/ic-light) | ComfyUI-IC-Light, ComfyUI-KJNodes | Model: IC-Light FC (SD 1.5); Source: [source](https://github.com/kijai/ComfyUI-IC-Light/blob/main/example_workflows/ic_light_example_02.png); Licence: Apache-2.0; Tested: not runtime-tested |

## IDM-VTON

Folder: [`IDM-VTON/`](IDM-VTON) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [try-on](IDM-VTON/try-on.json) | Try a garment image on a person; mask from Grounding DINO + HQ-SAM, pose from DensePose | [yisol/IDM-VTON](https://huggingface.co/yisol/IDM-VTON) | ComfyUI-IDM-VTON, comfyui_segment_anything, comfyui_controlnet_aux | Model: IDM-VTON; Source: [TemryL/ComfyUI-IDM-VTON](https://github.com/TemryL/ComfyUI-IDM-VTON) (workflow.png); Licence: Weights CC BY-NC-SA 4.0 (non-commercial) |

## InstantID

Folder: [`InstantID/`](InstantID) — 5 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [identity-sdxl-basic](InstantID/identity-sdxl-basic.json) | Identity-preserving SDXL image from one face | [weights](https://huggingface.co/InstantX/InstantID) | ComfyUI_InstantID (+ insightface antelopev2) | Model: InstantID; Source: [source](https://github.com/cubiq/ComfyUI_InstantID/blob/main/examples/InstantID_basic.json); Licence: Apache-2.0; InsightFace models non-commercial; Tested: not runtime-tested |
| [identity-sdxl-depth](InstantID/identity-sdxl-depth.json) | Identity plus depth ControlNet for body/scene layout | [weights](https://huggingface.co/InstantX/InstantID) | ComfyUI_InstantID, comfyui_controlnet_aux | Model: InstantID; Source: [source](https://github.com/cubiq/ComfyUI_InstantID/blob/main/examples/InstantID_depth.json); Licence: Apache-2.0; InsightFace models non-commercial; Tested: not runtime-tested |
| [identity-sdxl-ip-adapter](InstantID/identity-sdxl-ip-adapter.json) | Identity reinforced with IP-Adapter Plus SDXL | [weights](https://huggingface.co/InstantX/InstantID) | ComfyUI_InstantID, ComfyUI_IPAdapter_plus | Model: InstantID + IP-Adapter; Source: [source](https://github.com/cubiq/ComfyUI_InstantID/blob/main/examples/InstantID_IPAdapter.json); Licence: Apache-2.0; InsightFace models non-commercial; Tested: not runtime-tested |
| [identity-sdxl-posed](InstantID/identity-sdxl-posed.json) | Identity with the head pose taken from a second picture | [weights](https://huggingface.co/InstantX/InstantID) | ComfyUI_InstantID (+ insightface antelopev2) | Model: InstantID; Source: [source](https://github.com/cubiq/ComfyUI_InstantID/blob/main/examples/InstantID_posed.json); Licence: Apache-2.0; InsightFace models non-commercial; Tested: not runtime-tested |
| [identity-sdxl-two-people](InstantID/identity-sdxl-two-people.json) | Two identities in one picture via masks | [weights](https://huggingface.co/InstantX/InstantID) | ComfyUI_InstantID, ComfyUI_essentials | Model: InstantID; Source: [source](https://github.com/cubiq/ComfyUI_InstantID/blob/main/examples/InstantID_multi_id.json); Licence: Apache-2.0; InsightFace models non-commercial; Tested: not runtime-tested |

## InstructPix2Pix

Folder: [`InstructPix2Pix/`](InstructPix2Pix) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [edit-instruction](InstructPix2Pix/edit-instruction.json) | Text-instruction edit using core InstructPixToPix conditioning (official CosXL-edit example with the checkpoint switched to InstructPix2Pix) | [weights](https://huggingface.co/timbrooks/instruct-pix2pix) | — (core) | Model: InstructPix2Pix; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/edit_models/sdxl_edit_model.png); Licence: MIT (weights); review base SD terms; Tested: not runtime-tested |

## IP-Adapter

Folder: [`IP-Adapter/`](IP-Adapter) — 11 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [identity-faceid-plus-v2-plus-face](IP-Adapter/identity-faceid-plus-v2-plus-face.json) | Author-recommended FaceID Plus v2 + Plus Face stack for stronger likeness | [weights](https://huggingface.co/h94/IP-Adapter-FaceID) | ComfyUI_IPAdapter_plus (+ insightface) | Model: IP-Adapter FaceID Plus v2; Source: [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_ideal_faceid_config.json); Licence: Non-commercial research (InsightFace); Tested: not runtime-tested |
| [identity-faceid-sd15](IP-Adapter/identity-faceid-sd15.json) | Identity from one face photo (SD 1.5) | [weights](https://huggingface.co/h94/IP-Adapter-FaceID) | ComfyUI_IPAdapter_plus (+ insightface) | Model: IP-Adapter FaceID; Source: [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_faceid.json); Licence: Non-commercial research (InsightFace); Tested: not runtime-tested |
| [identity-faceid-sdxl-portrait](IP-Adapter/identity-faceid-sdxl-portrait.json) | SDXL portrait from a face photo | [weights](https://huggingface.co/h94/IP-Adapter-FaceID) | ComfyUI_IPAdapter_plus (+ insightface) | Model: IP-Adapter FaceID (SDXL); Source: [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_portrait.json); Licence: Non-commercial research (InsightFace); Tested: not runtime-tested |
| [reference-sd15-multiple-references](IP-Adapter/reference-sd15-multiple-references.json) | Blend several reference images | [weights](https://huggingface.co/h94/IP-Adapter) | ComfyUI_IPAdapter_plus | Model: IP-Adapter SD1.5 Plus; Source: [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_combine_embeds.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [reference-sd15-plus-advanced](IP-Adapter/reference-sd15-plus-advanced.json) | Explicit model/CLIP-vision loaders with weight and timing controls | [weights](https://huggingface.co/h94/IP-Adapter) | ComfyUI_IPAdapter_plus | Model: IP-Adapter SD1.5 Plus; Source: [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_advanced.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [reference-sd15-regional](IP-Adapter/reference-sd15-regional.json) | Different references for different colour-mask regions | [weights](https://huggingface.co/h94/IP-Adapter) | ComfyUI_IPAdapter_plus, ComfyUI_essentials | Model: IP-Adapter SD1.5; Source: [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_regional_conditioning.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [reference-sd15-simple](IP-Adapter/reference-sd15-simple.json) | Generate from a reference image with the unified loader | [weights](https://huggingface.co/h94/IP-Adapter) | ComfyUI_IPAdapter_plus | Model: IP-Adapter SD1.5; Source: [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_simple.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [reference-sd15-tiled-wide](IP-Adapter/reference-sd15-tiled-wide.json) | Use non-square / wide references without cropping (tiled) | [weights](https://huggingface.co/h94/IP-Adapter) | ComfyUI_IPAdapter_plus | Model: IP-Adapter SD1.5 Plus; Source: [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_tiled.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [reference-sdxl-cosxl-edit](IP-Adapter/reference-sdxl-cosxl-edit.json) | Instruction edit steered by a reference image | [weights](https://huggingface.co/h94/IP-Adapter) | ComfyUI_IPAdapter_plus | Model: IP-Adapter SDXL + CosXL Edit; Source: [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_cosxl_edit.json); Licence: IP-Adapter Apache-2.0; CosXL non-commercial; Tested: not runtime-tested |
| [reference-sdxl-precise-composition](IP-Adapter/reference-sdxl-precise-composition.json) | Precise composition transfer with mid-block style control | [weights](https://huggingface.co/h94/IP-Adapter) | ComfyUI_IPAdapter_plus | Model: IP-Adapter SDXL; Source: [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_precise_composition.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [reference-sdxl-style-and-composition](IP-Adapter/reference-sdxl-style-and-composition.json) | Take style from one image and composition from another | [weights](https://huggingface.co/h94/IP-Adapter) | ComfyUI_IPAdapter_plus | Model: IP-Adapter SDXL; Source: [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_style_composition.json); Licence: Apache-2.0; Tested: not runtime-tested |

## Kolors

Folder: [`Kolors/`](Kolors) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2img](Kolors/img2img.json) | Image to image with Kolors | [link](https://huggingface.co/Kwai-Kolors/Kolors) | ComfyUI-KwaiKolorsWrapper | Model: Kolors; Source: [source](https://github.com/kijai/ComfyUI-KwaiKolorsWrapper/tree/main/examples); Licence: Kolors licence (commercial use needs registration); Tested: not runtime-tested |
| [inpaint](Kolors/inpaint.json) | Mask inpainting with Kolors-Inpainting UNet | [link](https://huggingface.co/Kwai-Kolors/Kolors-Inpainting) | ComfyUI-Kolors-MZ | Model: Kolors Inpainting; Source: [source](https://github.com/MinusZoneAI/ComfyUI-Kolors-MZ/tree/main/examples); Licence: Kolors licence (commercial use needs registration); Tested: not runtime-tested |

## Krea-2

Folder: [`Krea-2/`](Krea-2) — 6 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [edit-lora-character-and-background](Krea-2/edit-lora-character-and-background.json) | Edit LoRA — Character and Background | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma | — |
| [edit-lora-custom-ratio](Krea-2/edit-lora-custom-ratio.json) | Edit LoRA — Custom Ratio | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma | — |
| [edit-lora](Krea-2/edit-lora.json) | Edit LoRA | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma | — |
| [outfit-change-outfit-lora](Krea-2/outfit-change-outfit-lora.json) | Outfit Change + Outfit LoRA | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma | — |
| [outfit-transfer-v2](Krea-2/outfit-transfer-v2.json) | Outfit Transfer v2 | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma | — |
| [style-reference-turbo-int8](Krea-2/style-reference-turbo-int8.json) | Style transfer from a reference image (style LoRA) | [link](https://huggingface.co/Comfy-Org/Krea-2/resolve/main/diffusion_models/krea2_turbo_int8_convrot.safetensors) | — | Model: Krea 2 Turbo; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_krea2_turbo_int8_image_style_reference.json); Licence: Check Krea 2 licence; Tested: not runtime-tested |

## LaMa

Folder: [`LaMa/`](LaMa) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [object-removal](LaMa/object-removal.json) | Object Remover | — | ComfyUI-RMBG | — |

## LayerDiffusion

Folder: [`LayerDiffusion/`](LayerDiffusion) — 4 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [layers-bg-from-fg](LayerDiffusion/layers-bg-from-fg.json) | Generate a matching background for a given foreground | same | ComfyUI-layerdiffuse, ComfyUI_essentials | Model: LayerDiffusion (SDXL); Source: same; Licence: Check model card |
| [layers-extract-bg-from-blend](LayerDiffusion/layers-extract-bg-from-blend.json) | Recover the background layer from a blended image and its foreground | same | ComfyUI-layerdiffuse | Model: LayerDiffusion (SDXL); Source: same; Licence: Check model card |
| [layers-extract-fg-from-blend](LayerDiffusion/layers-extract-fg-from-blend.json) | Recover the foreground layer from a blended image and its background | same | ComfyUI-layerdiffuse | Model: LayerDiffusion (SDXL); Source: same; Licence: Check model card |
| [layers-fg-from-bg-joint](LayerDiffusion/layers-fg-from-bg-joint.json) | Generate a foreground and blend for a given background | same | ComfyUI-layerdiffuse, ComfyUI_essentials | Model: LayerDiffusion (SD 1.5); Source: same; Licence: Check model card |

## Leffa

Folder: [`Leffa/`](Leffa) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [try-on](Leffa/try-on.json) | Flow-based try-on with DensePose and auto clothes mask | [franciszzj/Leffa](https://huggingface.co/franciszzj/Leffa) | Comfyui_leffa, comfyui_controlnet_aux, ComfyUI_LayerStyle_Advance, ComfyUI_essentials | Model: Leffa; Source: [StartHua/Comfyui_leffa](https://github.com/StartHua/Comfyui_leffa) (workflow.png); Licence: Check model card |

## LongCat-Image

Folder: [`LongCat-Image/`](LongCat-Image) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [edit](LongCat-Image/edit.json) | Bilingual instruction editing | [link](https://huggingface.co/TalmajM/LongCat-Image-Edit_ComfyUI_repackaged/resolve/main/split_files/diffusion_models/longcat_image_edit_bf16.safetensors) | — | Model: LongCat Image Edit; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_longcat_image_edit.json); Licence: Check LongCat-Image model card; Tested: not runtime-tested |

## MagicQuill

Folder: [`MagicQuill/`](MagicQuill) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [edit-brush-guided](MagicQuill/edit-brush-guided.json) | Interactive brush/sketch-guided edit (add, remove, colour strokes) | [weights](https://huggingface.co/LiuZichen/MagicQuill-models) | ComfyUI_MagicQuill | Model: MagicQuill; Source: [source](https://github.com/magic-quill/ComfyUI_MagicQuill/blob/main/MagicQuill.json); Licence: CC BY-NC-SA 4.0 (non-commercial); review; Tested: not runtime-tested |

## Marigold

Folder: [`Marigold/`](Marigold) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [depth-map-lcm-fast](Marigold/depth-map-lcm-fast.json) | Faster few-step Marigold depth | [prs-eth/marigold-lcm-v1-0](https://huggingface.co/prs-eth/marigold-lcm-v1-0) | ComfyUI-Marigold, ComfyUI_essentials | Model: Marigold LCM; Source: same; Licence: Apache-2.0 |
| [depth-map](Marigold/depth-map.json) | Diffusion-based high-detail depth | [prs-eth/marigold-v1-0](https://huggingface.co/prs-eth/marigold-v1-0) | ComfyUI-Marigold, ComfyUI_essentials | Model: Marigold; Source: [kijai/ComfyUI-Marigold](https://github.com/kijai/ComfyUI-Marigold/tree/main/examples); Licence: Apache-2.0 |

## MiDaS

Folder: [`MiDaS/`](MiDaS) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [depth-map-and-normal-map](MiDaS/depth-map-and-normal-map.json) | Depth and normal maps (ControlNet input) | [lllyasviel/Annotators](https://huggingface.co/lllyasviel/Annotators) (auto-download) | comfyui_controlnet_aux | Model: MiDaS; Source: [nomadoor/Comfy-with-ComfyUI](https://github.com/nomadoor/Comfy-with-ComfyUI/tree/main/src/workflows/ai-capabilities/depth-normal-map); Licence: MIT |

## Ming-Image

Folder: [`Ming-Image/`](Ming-Image) — 5 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [edit-social-media-pack-from-one-image](Ming-Image/edit-social-media-pack-from-one-image.json) | Social Media Pack from One Image | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [edit](Ming-Image/edit.json) | One Image Edit | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [multi-edit-product-ad-from-two-pictures](Ming-Image/multi-edit-product-ad-from-two-pictures.json) | Product Ad from Two Pictures | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [restyle-design-to-3d](Ming-Image/restyle-design-to-3d.json) | Restyle a Design to 3D | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [sketch-to-image-photo](Ming-Image/sketch-to-image-photo.json) | Sketch to Photo | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |

## MiniMax-H3

Folder: [`MiniMax-H3/`](MiniMax-H3) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [edit-single-frame](MiniMax-H3/edit-single-frame.json) | One Image Edit (Single Frame) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `minimax_h3_video_vae_fp16.safetensors` | ComfyUI-Pixaroma | — |
| [edit](MiniMax-H3/edit.json) | MiniMax H3 Image — One Image Edit (official ComfyUI template) | `minimax_h3_image_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_int8_convrot.safetensors`, `minimax_h3_image_vae_fp16.safetensors` +1 more | Core only | — |
| [multi-edit-bbox-refs](MiniMax-H3/multi-edit-bbox-refs.json) | H3 Image Edit - BBox Layout + 4 Reference Images ([how to use](MiniMax-H3-multi-edit-bbox-refs-notes.md)) | `minimax_h3_image_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_int8_convrot.safetensors`, `minimax_h3_image_vae_fp16.safetensors` +1 more | ComfyUI-H3Image-LayoutKit, ComfyUI-KJNodes | — |

## MOSS-Image

Folder: [`MOSS-Image/`](MOSS-Image) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [edit-lora](MOSS-Image/edit-lora.json) | General image editing with the MOSS edit LoRA | [link](https://huggingface.co/Comfy-Org/MOSS-Image/resolve/main/diffusion_models/moss_image_sft_int8_convrot.safetensors) | — | Model: MOSS-Image SFT; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_moss_image_edit.json); Licence: Check MOSS-Image model card; Tested: not runtime-tested |
| [text-edit-text-in-a-picture](MOSS-Image/text-edit-text-in-a-picture.json) | MOSS Image - Same Picture, New Words (Ep40) | `moss_image_sft_int8_convrot.safetensors`, `qwen3.5_9b_w4a8_gptq.safetensors`, `flux2-vae_small.safetensors` | ComfyUI-Pixaroma | — |

## NAFNet

Folder: [`NAFNet/`](NAFNet) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [denoise-sidd-1x](NAFNet/denoise-sidd-1x.json) | Denoise / deblur | [NAFNet weights](https://github.com/megvii-research/NAFNet#results-and-pre-trained-models) | none | Model: NAFNet (SIDD; GoPro for deblur); Source: ComfyUI example (adapted); Licence: See repo |

## OmniGen

Folder: [`OmniGen/`](OmniGen) — 5 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [edit-depth-map-to-image](OmniGen/edit-depth-map-to-image.json) | Generate a new picture that follows the depth of an input image | [weights](https://huggingface.co/Shitao/OmniGen-v1) | ComfyUI-OmniGen (1038lab) | Model: OmniGen v1; Source: [source](https://github.com/1038lab/ComfyUI-OmniGen/blob/main/Examples/depthmap2image.json); Licence: MIT; Tested: not runtime-tested |
| [edit-instruction](OmniGen/edit-instruction.json) | Instruction edit / text-to-image with up to three reference images | [weights](https://huggingface.co/Shitao/OmniGen-v1) | ComfyUI-OmniGen (1038lab), rgthree-comfy, ComfyUI_essentials, comfyui-various, sdxl_prompt_styler, ComfyUI-Custom-Scripts | Model: OmniGen v1; Source: [source](https://github.com/1038lab/ComfyUI-OmniGen/blob/main/Examples/OmniGen_wf.json); Licence: MIT; Tested: not runtime-tested |
| [edit-v2](OmniGen/edit-v2.json) | Official native instruction edit of one picture | [weights](https://huggingface.co/Comfy-Org/Omnigen2_ComfyUI_repackaged) | — (core) | Model: OmniGen2; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_omnigen2_image_edit.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [multi-edit-combine](OmniGen/multi-edit-combine.json) | Combine subjects from several input images by instruction | [weights](https://huggingface.co/Shitao/OmniGen-v1) | ComfyUI-OmniGen (1038lab) | Model: OmniGen v1; Source: [source](https://github.com/1038lab/ComfyUI-OmniGen/blob/main/Examples/omnigen_combine.json); Licence: MIT; Tested: not runtime-tested |
| [multi-edit-v2-two-image](OmniGen/multi-edit-v2-two-image.json) | Official example: edit with one or two reference pictures via ReferenceLatent | [weights](https://huggingface.co/Comfy-Org/Omnigen2_ComfyUI_repackaged) | — (core) | Model: OmniGen2; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/omnigen/omnigen2_example.png); Licence: Apache-2.0; Tested: not runtime-tested |

## OOTDiffusion

Folder: [`OOTDiffusion/`](OOTDiffusion) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [try-on](OOTDiffusion/try-on.json) | Half-body / full-body garment try-on | [levihsu/OOTDiffusion](https://huggingface.co/levihsu/OOTDiffusion) | ComfyUI-OOTDiffusion | Model: OOTDiffusion; Source: [AuroBit/ComfyUI-OOTDiffusion](https://github.com/AuroBit/ComfyUI-OOTDiffusion); Licence: CC BY-NC-SA 4.0 (non-commercial) |

## P-H3

Folder: [`P-H3/`](P-H3) — 13 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [character-sheet](P-H3/character-sheet.json) | P-H3 Image - Character Sheet (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |
| [edit-new-place](P-H3/edit-new-place.json) | P-H3 Image - Image Edit New Place (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |
| [inpaint-edit-inside-box](P-H3/inpaint-edit-inside-box.json) | P-H3 Image - Edit inside a Box (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |
| [multi-edit-character-in-a-scene](P-H3/multi-edit-character-in-a-scene.json) | P-H3 Image - Character in a Scene (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |
| [multi-edit-group-photo](P-H3/multi-edit-group-photo.json) | P-H3 Image - Group Photo (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |
| [multi-edit-logo-on-product](P-H3/multi-edit-logo-on-product.json) | P-H3 Image - Logo on a Product (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |
| [multi-edit-style-from-second-picture](P-H3/multi-edit-style-from-second-picture.json) | P-H3 Image - Style from a Second Picture (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `minimax_h3_style_transfer_v1.0_r64.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |
| [outfit-change-from-second-picture](P-H3/outfit-change-from-second-picture.json) | P-H3 Image - Outfit from a Second Picture (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |
| [outpaint](P-H3/outpaint.json) | P-H3 Image - Outpaint (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |
| [relight-day-to-night](P-H3/relight-day-to-night.json) | P-H3 Image - Relight Day to Night (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |
| [restore-and-colorize](P-H3/restore-and-colorize.json) | P-H3 Image - Restore and Colorize (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |
| [restyle-picture](P-H3/restyle-picture.json) | P-H3 Image - Restyle a Picture (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |
| [text-edit-text-in-a-picture](P-H3/text-edit-text-in-a-picture.json) | P-H3 Image - Edit Text in a Picture (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |

## Paint-by-Example

Folder: [`Paint-by-Example/`](Paint-by-Example) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [object-insertion-generate-example-then-insert](Paint-by-Example/object-insertion-generate-example-then-insert.json) | Generate the example object with an SD checkpoint, then insert it (API-format graph) | [weights](https://huggingface.co/Fantasy-Studio/Paint-by-Example) | paint-by-example_comfyui (auto-downloads weights) | Model: Paint-by-Example; Source: [source](https://github.com/phyblas/ironna_comfyui_workflow/tree/master/stable_diffusion/paint-by-example); Licence: CreativeML OpenRAIL-M; Tested: not runtime-tested |
| [object-insertion-two-examples](Paint-by-Example/object-insertion-two-examples.json) | Paste two example objects into masked regions, no prompt (API-format graph) | [weights](https://huggingface.co/Fantasy-Studio/Paint-by-Example) | paint-by-example_comfyui (auto-downloads weights) | Model: Paint-by-Example; Source: [source](https://github.com/phyblas/ironna_comfyui_workflow/tree/master/stable_diffusion/paint-by-example); Licence: CreativeML OpenRAIL-M; Tested: not runtime-tested |

## PhotoMaker

Folder: [`PhotoMaker/`](PhotoMaker) — 4 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [identity-sdxl](PhotoMaker/identity-sdxl.json) | Stacked-ID personalisation from several photos of one person | [weights](https://huggingface.co/TencentARC/PhotoMaker) | ComfyUI-PhotoMaker-Plus, ComfyUI-Custom-Scripts | Model: PhotoMaker v1; Source: [source](https://github.com/shiimizu/ComfyUI-PhotoMaker-Plus/blob/main/examples/v1-workflow.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [identity-v2-sdxl-auto-crop-faces](PhotoMaker/identity-v2-sdxl-auto-crop-faces.json) | Auto-detect and crop faces from input photos first | [weights](https://huggingface.co/TencentARC/PhotoMaker-V2) | ComfyUI-PhotoMaker-Plus, ComfyUI-AutoCropFaces, ComfyUI-Custom-Scripts | Model: PhotoMaker v2; Source: [source](https://github.com/shiimizu/ComfyUI-PhotoMaker-Plus/blob/main/examples/v2-autodetect-faces-workflow.json); Licence: Apache-2.0; InsightFace models non-commercial; Tested: not runtime-tested |
| [identity-v2-sdxl-simple](PhotoMaker/identity-v2-sdxl-simple.json) | Minimal PhotoMaker v2 personalisation | [weights](https://huggingface.co/TencentARC/PhotoMaker-V2) | ComfyUI-PhotoMaker-Plus (+ insightface) | Model: PhotoMaker v2; Source: [source](https://github.com/shiimizu/ComfyUI-PhotoMaker-Plus/blob/main/examples/v2-simple-workflow.json); Licence: Apache-2.0; InsightFace models non-commercial; Tested: not runtime-tested |
| [identity-v2-sdxl-styles](PhotoMaker/identity-v2-sdxl-styles.json) | PhotoMaker v2 with style templates and delayed ID merge | [weights](https://huggingface.co/TencentARC/PhotoMaker-V2) | ComfyUI-PhotoMaker-Plus, ComfyUI-Custom-Scripts (+ insightface) | Model: PhotoMaker v2; Source: [source](https://github.com/shiimizu/ComfyUI-PhotoMaker-Plus/blob/main/examples/v2-workflow.json); Licence: Apache-2.0; InsightFace models non-commercial; Tested: not runtime-tested |

## PowerPaint

Folder: [`PowerPaint/`](PowerPaint) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [object-removal](PowerPaint/object-removal.json) | Text-selected object removal (GroundingDINO+SAM mask, PowerPaint remove task) | [weights](https://huggingface.co/JunhaoZhuang/PowerPaint-v2-1) | ComfyUI-BrushNet, comfyui_segment_anything | Model: PowerPaint v2; Source: [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/PowerPaint_object_removal.json); Licence: Review PowerPaint weight terms; Tested: not runtime-tested |
| [outpaint](PowerPaint/outpaint.json) | Outpaint with the PowerPaint outpainting task | [weights](https://huggingface.co/JunhaoZhuang/PowerPaint-v2-1) | ComfyUI-BrushNet | Model: PowerPaint v2; Source: [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/PowerPaint_outpaint.json); Licence: Review PowerPaint weight terms; Tested: not runtime-tested |

## PuLID

Folder: [`PuLID/`](PuLID) — 4 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [identity-sdxl-ip-adapter-style](PuLID/identity-sdxl-ip-adapter-style.json) | Identity plus style taken from a reference image | [weights](https://huggingface.co/huchenlei/ipadapter_pulid) | PuLID_ComfyUI, ComfyUI_IPAdapter_plus | Model: PuLID (SDXL) + IP-Adapter; Source: [source](https://github.com/cubiq/PuLID_ComfyUI/blob/main/examples/PuLID_IPAdapter_style_transfer.json); Licence: Apache-2.0; InsightFace models non-commercial; Tested: not runtime-tested |
| [identity-sdxl-lightning-4-step](PuLID/identity-sdxl-lightning-4-step.json) | Fast 4-step identity generation with the SDXL Lightning UNet | [weights](https://huggingface.co/huchenlei/ipadapter_pulid) | PuLID_ComfyUI (+ insightface, EVA-CLIP) | Model: PuLID (SDXL Lightning); Source: [source](https://github.com/cubiq/PuLID_ComfyUI/blob/main/examples/PuLID_4-Step_lightning.json); Licence: Apache-2.0; InsightFace models non-commercial; Tested: not runtime-tested |
| [identity-sdxl-simple](PuLID/identity-sdxl-simple.json) | Identity-preserving generation from a face photo | [weights](https://huggingface.co/huchenlei/ipadapter_pulid) | PuLID_ComfyUI (+ insightface, EVA-CLIP) | Model: PuLID (SDXL); Source: [source](https://github.com/cubiq/PuLID_ComfyUI/blob/main/examples/PuLID_simple.json); Licence: Apache-2.0; InsightFace models non-commercial; Tested: not runtime-tested |
| [identity-sdxl-two-people-attention-mask](PuLID/identity-sdxl-two-people-attention-mask.json) | Two identities placed with attention masks | [weights](https://huggingface.co/huchenlei/ipadapter_pulid) | PuLID_ComfyUI (+ insightface, EVA-CLIP) | Model: PuLID (SDXL); Source: [source](https://github.com/cubiq/PuLID_ComfyUI/blob/main/examples/PuLID_attention_mask.json); Licence: Apache-2.0; InsightFace models non-commercial; Tested: not runtime-tested |

## Qwen-Image

Folder: [`Qwen-Image/`](Qwen-Image) — 26 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [character-sheet-v21](Qwen-Image/character-sheet-v21.json) | Character Sheet | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [edit-2509](Qwen-Image/edit-2509.json) | Multi-image instruction editing + Lightning 4-step | [link](https://huggingface.co/Comfy-Org/Qwen-Image-Edit_ComfyUI) | — | Model: Qwen-Image-Edit-2509; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_qwen_image_edit_2509.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [edit-2511-int8-low-vram](Qwen-Image/edit-2511-int8-low-vram.json) | Low-VRAM INT8 instruction editing | [link](https://huggingface.co/Comfy-Org/Qwen-Image-Edit_ComfyUI) | — | Model: Qwen-Image-Edit-2511; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_qwen_image_edit_2511_int8.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [edit-2511](Qwen-Image/edit-2511.json) | Instruction editing (FP8-mixed) + Lightning 4-step | [link](https://huggingface.co/Comfy-Org/Qwen-Image-Edit_ComfyUI) | — | Model: Qwen-Image-Edit-2511; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_qwen_image_edit_2511.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [edit-v21-consistency-lora](Qwen-Image/edit-v21-consistency-lora.json) | One Image Edit + Consistency LoRA | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [edit-v21-low-vram](Qwen-Image/edit-v21-low-vram.json) | One Image Edit — Low VRAM | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [edit-v21-prompt-enhancer](Qwen-Image/edit-v21-prompt-enhancer.json) | One Image Edit + Prompt Enhancer | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [edit-v21-turbo](Qwen-Image/edit-v21-turbo.json) | One Image Edit — Turbo | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [edit-v21](Qwen-Image/edit-v21.json) | One Image Edit | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [edit](Qwen-Image/edit.json) | Original Qwen-Image-Edit instruction editing + Lightning 4-step | [link](https://huggingface.co/Comfy-Org/Qwen-Image-Edit_ComfyUI) | — | Model: Qwen-Image-Edit; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_qwen_image_edit.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [inpaint-instantx-controlnet](Qwen-Image/inpaint-instantx-controlnet.json) | Mask inpainting with InstantX Inpainting ControlNet | [link](https://huggingface.co/InstantX/Qwen-Image-ControlNet-Inpainting) | — | Model: Qwen-Image; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_qwen_image_instantx_inpainting_controlnet.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [inpaint-v21](Qwen-Image/inpaint-v21.json) | Inpaint | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [multi-edit-v21-2-images-prompt-enhancer](Qwen-Image/multi-edit-v21-2-images-prompt-enhancer.json) | Multi-Image Edit — 2 Images + Prompt Enhancer | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [multi-edit-v21-3-images](Qwen-Image/multi-edit-v21-3-images.json) | Multi-Image Edit — 3 Images | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [multi-edit-v21-4-images](Qwen-Image/multi-edit-v21-4-images.json) | Multi-Image Edit — 4 Images | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [multi-edit-v21-character-in-a-scene](Qwen-Image/multi-edit-v21-character-in-a-scene.json) | Character in a Scene | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [multi-edit-v21-group-photo-6-images](Qwen-Image/multi-edit-v21-group-photo-6-images.json) | Multi-Image Edit — Group Photo from 6 Images | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [multi-edit-v21-logo-on-a-product](Qwen-Image/multi-edit-v21-logo-on-a-product.json) | Logo on a Product | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [outfit-change-v21-turbo](Qwen-Image/outfit-change-v21-turbo.json) | Outfit Change — Turbo | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [outfit-change-v21](Qwen-Image/outfit-change-v21.json) | Outfit Change | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [outpaint-v21](Qwen-Image/outpaint-v21.json) | Outpaint | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [pose-change-v21-from-a-picture](Qwen-Image/pose-change-v21-from-a-picture.json) | Pose from a Picture | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [relight-edit-2509-lora](Qwen-Image/relight-edit-2509-lora.json) | Relighting with the Relight LoRA | [link](https://huggingface.co/Comfy-Org/Qwen-Image-Edit_ComfyUI) | — | Model: Qwen-Image-Edit-2509; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_qwen_image_edit_2509_relight.json); Licence: Apache-2.0 (check LoRA card); Tested: not runtime-tested |
| [remove-background-v21](Qwen-Image/remove-background-v21.json) | Remove Background | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [sketch-to-image-v21-consistency-lora](Qwen-Image/sketch-to-image-v21-consistency-lora.json) | Sketch to Image + Consistency LoRA | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [sketch-to-image-v21](Qwen-Image/sketch-to-image-v21.json) | Sketch to Image | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |

## Restormer

Folder: [`Restormer/`](Restormer) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [denoise-real-1x](Restormer/denoise-real-1x.json) | Denoise (deblur / derain checkpoints too) | [Restormer v1.0 release](https://github.com/swz30/Restormer/releases/tag/v1.0) | spandrel_extra_arches (pip) | Model: Restormer ⁺; Source: ComfyUI example (adapted); Licence: Code MIT; non-commercial arch in spandrel |

## Retinexformer

Folder: [`Retinexformer/`](Retinexformer) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [low-light-enhance-1x](Retinexformer/low-light-enhance-1x.json) | Low-light enhancement | [CaiYuanhao/Retinexformer](https://huggingface.co/CaiYuanhao/Retinexformer) | none | Model: Retinexformer (LOL-v2-real); Source: ComfyUI example (adapted); Licence: MIT |

## RMBG

Folder: [`RMBG/`](RMBG) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [remove-background-v14-bria](RMBG/remove-background-v14-bria.json) | Remove background, save RGBA | [briaai/RMBG-1.4](https://huggingface.co/briaai/RMBG-1.4) | ComfyUI-BRIA_AI-RMBG | Model: BRIA RMBG 1.4; Source: [602387193c/ComfyUI-wiki](https://github.com/602387193c/ComfyUI-wiki/tree/main/workflows); Licence: Non-commercial (BRIA RMBG-1.4 licence) |

## SAM-3

Folder: [`SAM-3/`](SAM-3) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [remove-background-crop-object](SAM-3/remove-background-crop-object.json) | Remove Background (Segment + Crop Object) | — | ComfyUI-RMBG | — |
| [segment-v31-concept-cutout](SAM-3/segment-v31-concept-cutout.json) | Segment all instances of a text concept and cut them out (native ComfyUI nodes) | `sam3.1_multiplex_fp16.safetensors` (ComfyUI repack of [facebook/sam3.1](https://huggingface.co/facebook/sam3.1)) | — (core nodes) | Model: SAM 3.1; Source: [nomadoor/Comfy-with-ComfyUI](https://github.com/nomadoor/Comfy-with-ComfyUI/tree/main/src/workflows/data-utilities/sam3); Licence: SAM License (gated, check terms) |

## SCUNet

Folder: [`SCUNet/`](SCUNet) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [denoise-real-1x](SCUNet/denoise-real-1x.json) | Blind real-photo denoise | [scunet_color_real_psnr.pth](https://github.com/cszn/KAIR/releases/download/v1.0/scunet_color_real_psnr.pth) | none | Model: SCUNet; Source: ComfyUI example (adapted); Licence: Apache-2.0 |

## SD15

Folder: [`SD15/`](SD15) — 8 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2img-juggernaut](SD15/img2img-juggernaut.json) | Image to Image | `juggernaut_reborn.safetensors` | Core only | — |
| [inpaint-controlnet](SD15/inpaint-controlnet.json) | Inpaint guided by a scribble ControlNet inside the mask | [weights](https://huggingface.co/TencentARC/BrushNet) | ComfyUI-BrushNet | Model: BrushNet (SD 1.5) + ControlNet; Source: [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/BrushNet_with_CN.json); Licence: Code Apache-2.0; review BrushNet weight terms; Tested: not runtime-tested |
| [inpaint-inpainting-model](SD15/inpaint-inpainting-model.json) | Masked inpaint with the dedicated SD 1.5 inpainting checkpoint (checkpoint name changed from the SD2 512-inpainting example) | [weights](https://huggingface.co/stable-diffusion-v1-5/stable-diffusion-inpainting) | — (core) | Model: SD 1.5 Inpainting; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/inpaint/inpaint_example.png); Licence: CreativeML OpenRAIL-M; Tested: not runtime-tested |
| [inpaint-ip-adapter-reference](SD15/inpaint-ip-adapter-reference.json) | Fill the mask with content taken from a reference picture | [weights](https://huggingface.co/TencentARC/BrushNet) | ComfyUI-BrushNet, ComfyUI_IPAdapter_plus | Model: BrushNet (SD 1.5) + IP-Adapter; Source: [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/BrushNet_with_IPA.json); Licence: Code Apache-2.0; review BrushNet weight terms; Tested: not runtime-tested |
| [inpaint-small-area-crop](SD15/inpaint-small-area-crop.json) | Crop around a small mask, inpaint at full resolution and blend back | [weights](https://huggingface.co/TencentARC/BrushNet) | ComfyUI-BrushNet | Model: BrushNet (SD 1.5); Source: [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/BrushNet_cut_for_inpaint.json); Licence: Code Apache-2.0; review BrushNet weight terms; Tested: not runtime-tested |
| [inpaint-text-masked-batch](SD15/inpaint-text-masked-batch.json) | Batch inpaint where GroundingDINO+SAM build the mask from a text prompt | [weights](https://huggingface.co/TencentARC/BrushNet) | ComfyUI-BrushNet, comfyui_segment_anything, ComfyUI-VideoHelperSuite | Model: BrushNet (SD 1.5); Source: [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/BrushNet_image_batch.json); Licence: Code Apache-2.0; review BrushNet weight terms; Tested: not runtime-tested |
| [inpaint](SD15/inpaint.json) | Dual-branch BrushNet inpaint on any SD 1.5 checkpoint | [weights](https://huggingface.co/TencentARC/BrushNet) | ComfyUI-BrushNet | Model: BrushNet (SD 1.5); Source: [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/BrushNet_basic.json); Licence: Code Apache-2.0; review BrushNet weight terms; Tested: not runtime-tested |
| [outpaint-inpainting-model](SD15/outpaint-inpainting-model.json) | Outpaint (pad canvas then fill) with the SD 1.5 inpainting checkpoint (checkpoint name changed from the SD2 example) | [weights](https://huggingface.co/stable-diffusion-v1-5/stable-diffusion-inpainting) | — (core) | Model: SD 1.5 Inpainting; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/inpaint/inpain_model_outpainting.png); Licence: CreativeML OpenRAIL-M; Tested: not runtime-tested |

## SDXL

Folder: [`SDXL/`](SDXL) — 4 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [inpaint-brushnet-ultimate-upscale](SDXL/inpaint-brushnet-ultimate-upscale.json) | High-resolution inpaint through Ultimate SD Upscale tiles | [weights](https://huggingface.co/TencentARC/BrushNet) | ComfyUI-BrushNet, ComfyUI_UltimateSDUpscale | Model: BrushNet (SDXL); Source: [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/BrushNet_SDXL_upscale.json); Licence: Code Apache-2.0; review BrushNet weight terms; Tested: not runtime-tested |
| [inpaint-brushnet](SDXL/inpaint-brushnet.json) | BrushNet inpaint on an SDXL checkpoint | [weights](https://huggingface.co/TencentARC/BrushNet) | ComfyUI-BrushNet | Model: BrushNet (SDXL); Source: [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/BrushNet_SDXL_basic.json); Licence: Code Apache-2.0; review BrushNet weight terms; Tested: not runtime-tested |
| [inpaint-mat-prefill-fooocus](SDXL/inpaint-mat-prefill-fooocus.json) | MAT pre-fills the hole, then SDXL + Fooocus inpaint patch refines it (inpaint and outpaint branches) | [weights](https://github.com/Sanster/models/releases/tag/add_mat) | comfyui-inpaint-nodes | Model: MAT (Places512) + Fooocus inpaint (SDXL); Source: [source](https://github.com/Acly/comfyui-inpaint-nodes/blob/main/workflows/inpaint-preprocess.json); Licence: MAT weights CC BY-NC 4.0 (non-commercial); Fooocus patch: review; Tested: not runtime-tested |
| [variation-revision-image-prompt](SDXL/variation-revision-image-prompt.json) | Revision: image prompt via CLIP-Vision G mixed with text | [link](https://huggingface.co/comfyanonymous/clip_vision_g) | — | Model: SDXL Base 1.0; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/sdxl_revision_text_prompts.json); Licence: CreativeML OpenRAIL++-M; Tested: not runtime-tested |

## Stable-Cascade

Folder: [`Stable-Cascade/`](Stable-Cascade) — 4 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2img](Stable-Cascade/img2img.json) | Image to image | [link](https://huggingface.co/stabilityai/stable-cascade) | — | Model: Stable Cascade; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/tree/master/stable_cascade); Licence: Stability non-commercial research; Tested: not runtime-tested |
| [inpaint-controlnet](Stable-Cascade/inpaint-controlnet.json) | Inpainting ControlNet for Stable Cascade | [link](https://huggingface.co/stabilityai/stable-cascade) | — | Model: Stable Cascade; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/tree/master/stable_cascade); Licence: Stability non-commercial research; Tested: not runtime-tested |
| [variation-image-remix-multiple](Stable-Cascade/variation-image-remix-multiple.json) | Mix several images into one | [link](https://huggingface.co/stabilityai/stable-cascade) | — | Model: Stable Cascade; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/tree/master/stable_cascade); Licence: Stability non-commercial research; Tested: not runtime-tested |
| [variation-image-remix](Stable-Cascade/variation-image-remix.json) | Image variations/remix from one image (unCLIP) | [link](https://huggingface.co/stabilityai/stable-cascade) | — | Model: Stable Cascade; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/tree/master/stable_cascade); Licence: Stability non-commercial research; Tested: not runtime-tested |

## StoryMaker

Folder: [`StoryMaker/`](StoryMaker) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [identity-single-portrait](StoryMaker/identity-single-portrait.json) | Keep face, hair and clothing of a masked person in a new scene | [weights](https://huggingface.co/RED-AIGC/StoryMaker) | ComfyUI-StoryMaker (+ insightface) | Model: StoryMaker; Source: [source](https://github.com/tanglaoya321/ComfyUI-StoryMaker/blob/main/workflows/workflow.json); Licence: Review StoryMaker terms; InsightFace models non-commercial; Tested: not runtime-tested |

## WD14-Tagger

Folder: [`WD14-Tagger/`](WD14-Tagger) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tag-v3-anime](WD14-Tagger/tag-v3-anime.json) | Danbooru-style tags from an image | [SmilingWolf/wd-swinv2-tagger-v3](https://huggingface.co/SmilingWolf/wd-swinv2-tagger-v3) (auto-download) | ComfyUI-WD14-Tagger | Model: WD14 Tagger (SwinV2 v3); Source: [nomadoor/Comfy-with-ComfyUI](https://github.com/nomadoor/Comfy-with-ComfyUI/tree/main/src/workflows/ai-capabilities/tag-caption-generation); Licence: Apache-2.0 |

## Other

Folder: [`Other/`](Other) — 20 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [filters-example](Other/filters-example.json) | Image Filters Example | — | ComfyUI-RMBG, ComfyUI_LayerStyle, rgthree-comfy | — |
| [filters-layerstyle-color-adjust](Other/filters-layerstyle-color-adjust.json) | Image Filters and Color Adjustments | — | ComfyUI_LayerStyle, rgthree-comfy | — |
| [image-blend](Other/image-blend.json) | Image Blend | — | ComfyUI-RMBG, ComfyUI_LayerStyle | — |
| [image-combiner-transparent-items](Other/image-combiner-transparent-items.json) | Image Combiner for Transparent Items | — | ComfyUI-RMBG | — |
| [image-combiner](Other/image-combiner.json) | Image Combiner | — | ComfyUI-RMBG | — |
| [image-scale](Other/image-scale.json) | Image Scale | — | ComfyUI-KJNodes | — |
| [image-stitch](Other/image-stitch.json) | Image Stitch | — | ComfyUI-RMBG, rgthree-comfy | — |
| [image-transformation](Other/image-transformation.json) | Image Transformation | — | ComfyUI_LayerStyle, rgthree-comfy | — |
| [pixaroma-3d-builder-ep11](Other/pixaroma-3d-builder-ep11.json) | 3D Builder (Ep11) | — | ComfyUI-Pixaroma | — |
| [pixaroma-3d-builder-ep13](Other/pixaroma-3d-builder-ep13.json) | 3D Builder (Ep13) | — | ComfyUI-Pixaroma | — |
| [pixaroma-combine-join-two-images](Other/pixaroma-combine-join-two-images.json) | Combine — Join Two Images | — | ComfyUI-Pixaroma | — |
| [pixaroma-crop-ep11](Other/pixaroma-crop-ep11.json) | Crop (Ep11) | — | ComfyUI-Pixaroma | — |
| [pixaroma-crop-ep13](Other/pixaroma-crop-ep13.json) | Crop (Ep13) | — | ComfyUI-Pixaroma | — |
| [pixaroma-image-composer-ep11](Other/pixaroma-image-composer-ep11.json) | Image Composer (Ep11) | — | ComfyUI-Pixaroma | — |
| [pixaroma-image-composer-ep13](Other/pixaroma-image-composer-ep13.json) | Image Composer (Ep13) | — | ComfyUI-Pixaroma | — |
| [pixaroma-paint-ep11](Other/pixaroma-paint-ep11.json) | Paint (Ep11) | — | ComfyUI-Pixaroma | — |
| [pixaroma-paint-ep13](Other/pixaroma-paint-ep13.json) | Paint (Ep13) | — | ComfyUI-Pixaroma | — |
| [pixaroma-text-overlay](Other/pixaroma-text-overlay.json) | Text Overlay | — | ComfyUI-Pixaroma | — |
| [remove-background-transparent-items](Other/remove-background-transparent-items.json) | Remove Background from Transparent Items | — | ComfyUI-RMBG | — |
| [remove-background](Other/remove-background.json) | Remove Background | — | ComfyUI-RMBG, ComfyUI_LayerStyle, rgthree-comfy | — |

## Notes carried over from the previous folder layout

Setup notes, licences, test results and "not available in ComfyUI" lists from the former task-folder READMEs. Links point to the new locations.

### From the former "Image Editing" README

Image-to-image (img2img) and instruction editing: single- and multi-image edits, inpainting, outpainting, object removal, background removal, outfit and pose changes, sketch-to-image and compositing tools.

#### Editing and control models from the Open-Source Image Model Atlas (Nov 2026)

Collected for the "Image Editing and Control" entries of the Open-Source Image Model Atlas. Each file is an existing workflow from the linked source, copied as published unless the purpose column says a model file name was changed. None of them has been run here: every row is **not runtime-tested**. Base checkpoints (SD 1.5, SDXL and others named in the graphs) carry their own licences; check them as well.

##### Already covered elsewhere in `01-Image` (skipped as duplicates)

- ControlNet v1.1 Canny: [`sd15-juggernaut-reborn-txt2img-controlnet-canny`](../Generation/SD15/controlnet-canny-juggernaut.json)
- Z-Image ControlNet Union: [`controlnet-union-turbo-fp8-aio`](../Generation/Z-Image/controlnet-union-turbo-fp8-aio.json)
- LaMa: [`object-removal`](LaMa/object-removal.json)

##### Not available in ComfyUI

No authentic, published ComfyUI workflow was found for these entries, so none was made up:

- SDXL Inpainting 0.1 (diffusers UNet checkpoint) — for SDXL inpainting use the BrushNet SDXL or MAT + Fooocus workflows above
- DiffEdit — no ComfyUI node or workflow
- DragDiffusion — no ComfyUI node or workflow
- DragGAN — GAN-based, no ComfyUI node or workflow
- ControlNet v1.1 Tile — no published example workflow found

### From the former "Image Specialized and Supporting" README

Supporting image models from the "Specialized and Supporting Image Models" section of the open-source image model research (IMG-151 to IMG-183): virtual try-on, transparent layer generation, background removal, segmentation and detection, captioning/OCR/tagging, depth estimation and pose estimation.

All workflows were collected from official model repos, custom-node repos and reputable community repos. Each file was checked to be valid ComfyUI workflow JSON for its model and task. **None of them has been runtime-tested in this library.** Models are not included; download them from the links below (many nodes download them automatically on first run).

Every row is **not runtime-tested**.

#### Already in the library (skipped as duplicates)

- RMBG 2.0 background removal — `01-Image/Editing/Other/remove-background.json`
- BiRefNet background removal — `01-Image/Editing/BiRefNet/remove-background.json`
- SAM 3 text-prompt segmentation — `01-Image/Editing/SAM-3/remove-background-crop-object.json`

#### Not available in ComfyUI

No authentic standalone ComfyUI image workflow was found for these entries, so none was added:

- **CatV2TON** — no ComfyUI node or workflow.
- **StableVITON** — no ComfyUI node or workflow.
- **OutfitAnyone** — weights not released.
- **Grounding DINO 1.5** — API-only, no open weights.
- **ZoeDepth** — node exists in comfyui_controlnet_aux, but only found inside larger ControlNet/InstantID generation graphs, not a standalone workflow.
- **CLIP ViT-L/14**, **SigLIP** — encoders used inside other workflows (unCLIP, IP-Adapter, Redux), no standalone image workflow.
- **BLIP-2** — no maintained ComfyUI node or workflow found.

## Extra guide

- [MiniMax H3 multi-edit with bbox layout and 4 references](MiniMax-H3-multi-edit-bbox-refs-notes.md) — agent guide for [`MiniMax-H3/multi-edit-bbox-refs.json`](MiniMax-H3/multi-edit-bbox-refs.json).

See the [01-Image overview](../README.md) for the other categories, the [main README](../../README.md) for setup, or [`00-LIBRARY-INDEX.md`](../../00-LIBRARY-INDEX.md) for the full list.
