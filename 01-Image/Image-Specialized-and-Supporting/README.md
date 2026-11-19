# Image Specialized and Supporting — ComfyUI workflows

Supporting image models from the "Specialized and Supporting Image Models" section of the open-source image model research (IMG-151 to IMG-183): virtual try-on, transparent layer generation, background removal, segmentation and detection, captioning/OCR/tagging, depth estimation and pose estimation.

All workflows were collected from official model repos, custom-node repos and reputable community repos. Each file was checked to be valid ComfyUI workflow JSON for its model and task. **None of them has been runtime-tested in this library.** Models are not included; download them from the links below (many nodes download them automatically on first run).

| Subfolder | What is inside | Workflows |
|---|---|---|
| [`Virtual-Try-On/`](Virtual-Try-On) | Garment-to-person try-on | 6 |
| [`Transparent-Layers/`](Transparent-Layers) | LayerDiffusion transparent RGBA and layer blending | 6 |
| [`Background-Removal/`](Background-Removal) | BRIA RMBG 1.4 background removal | 1 |
| [`Segmentation-and-Detection/`](Segmentation-and-Detection) | Text-prompted and concept segmentation (Grounding DINO, SAM, HQ-SAM, SAM 2, SAM 3.1) | 5 |
| [`Captioning-OCR-and-Tagging/`](Captioning-OCR-and-Tagging) | Florence-2 caption/OCR/VQA/detection and WD14 tags | 5 |
| [`Depth-Estimation/`](Depth-Estimation) | Depth Anything V2/3, MiDaS, Marigold | 7 |
| [`Pose-Estimation/`](Pose-Estimation) | DWPose and OpenPose keypoints | 1 |

## Workflows (31)

Every row is **not runtime-tested**.

### Virtual try-on

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence |
|---|---|---|---|---|---|---|
| [idm-vton-virtual-try-on](Virtual-Try-On/idm-vton-virtual-try-on.json) | IDM-VTON | Try a garment image on a person; mask from Grounding DINO + HQ-SAM, pose from DensePose | [TemryL/ComfyUI-IDM-VTON](https://github.com/TemryL/ComfyUI-IDM-VTON) (workflow.png) | [yisol/IDM-VTON](https://huggingface.co/yisol/IDM-VTON) | ComfyUI-IDM-VTON, comfyui_segment_anything, comfyui_controlnet_aux | Weights CC BY-NC-SA 4.0 (non-commercial) |
| [catvton-virtual-try-on-automask](Virtual-Try-On/catvton-virtual-try-on-automask.json) | CatVTON | Try-on with automatic upper/lower/overall clothing mask | [pzc163/Comfyui-CatVTON](https://github.com/pzc163/Comfyui-CatVTON) | [zhengchong/CatVTON](https://huggingface.co/zhengchong/CatVTON) | Comfyui-CatVTON | Weights CC BY-NC-SA 4.0 (non-commercial) |
| [catvton-flux-lora-try-on-auto-clothes-mask](Virtual-Try-On/catvton-flux-lora-try-on-auto-clothes-mask.json) | CatVTON-FLUX (LoRA) | Try-on with FLUX.1 Fill + CatVTON LoRA, core sampler nodes, auto clothes mask | [nomadoor/Comfy-with-ComfyUI](https://github.com/nomadoor/Comfy-with-ComfyUI/tree/main/src/workflows/ai-capabilities/virtual-try-on) | [xiaozaa/catvton-flux-lora-alpha](https://huggingface.co/xiaozaa/catvton-flux-lora-alpha), [FLUX.1-Fill-dev](https://huggingface.co/black-forest-labs/FLUX.1-Fill-dev) | Comfyui_segformer_b2_clothes, comfyui-in-context-lora-utils | LoRA CC BY-NC-SA 4.0; FLUX.1 [dev] non-commercial licence |
| [catvton-flux-full-try-on-sam2-point-mask](Virtual-Try-On/catvton-flux-full-try-on-sam2-point-mask.json) | CatVTON-FLUX (full model) | Try-on with the full CatVTON-FLUX model, garment mask drawn with SAM 2 points | [lujiazho/ComfyUI-CatvtonFluxWrapper](https://github.com/lujiazho/ComfyUI-CatvtonFluxWrapper) | [xiaozaa/catvton-flux-alpha](https://huggingface.co/xiaozaa/catvton-flux-alpha) | ComfyUI-CatvtonFluxWrapper, ComfyUI-segment-anything-2, ComfyUI-KJNodes, comfyui-inpaint-nodes | CC BY-NC-SA 4.0; FLUX.1 [dev] non-commercial licence |
| [ootdiffusion-virtual-try-on](Virtual-Try-On/ootdiffusion-virtual-try-on.json) | OOTDiffusion | Half-body / full-body garment try-on | [AuroBit/ComfyUI-OOTDiffusion](https://github.com/AuroBit/ComfyUI-OOTDiffusion) | [levihsu/OOTDiffusion](https://huggingface.co/levihsu/OOTDiffusion) | ComfyUI-OOTDiffusion | CC BY-NC-SA 4.0 (non-commercial) |
| [leffa-virtual-try-on](Virtual-Try-On/leffa-virtual-try-on.json) | Leffa | Flow-based try-on with DensePose and auto clothes mask | [StartHua/Comfyui_leffa](https://github.com/StartHua/Comfyui_leffa) (workflow.png) | [franciszzj/Leffa](https://huggingface.co/franciszzj/Leffa) | Comfyui_leffa, comfyui_controlnet_aux, ComfyUI_LayerStyle_Advance, ComfyUI_essentials | Check model card |

### Transparent layers (LayerDiffusion)

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence |
|---|---|---|---|---|---|---|
| [layerdiffusion-txt2img-transparent-foreground](Transparent-Layers/layerdiffusion-txt2img-transparent-foreground.json) | LayerDiffusion (SDXL) | Text-to-image with a transparent RGBA foreground | [huchenlei/ComfyUI-layerdiffuse](https://github.com/huchenlei/ComfyUI-layerdiffuse/tree/main/example_workflows) | [LayerDiffusion/layerdiffusion-v1](https://huggingface.co/LayerDiffusion/layerdiffusion-v1) (auto-download) + any SDXL checkpoint | ComfyUI-layerdiffuse | Check model card; base checkpoint licence applies |
| [layerdiffusion-txt2img-joint-foreground-background-blend](Transparent-Layers/layerdiffusion-txt2img-joint-foreground-background-blend.json) | LayerDiffusion (SD 1.5) | Generate foreground, background and blended image together | same | same + any SD 1.5 checkpoint | ComfyUI-layerdiffuse | Check model card |
| [layerdiffusion-background-from-foreground](Transparent-Layers/layerdiffusion-background-from-foreground.json) | LayerDiffusion (SDXL) | Generate a matching background for a given foreground | same | same | ComfyUI-layerdiffuse, ComfyUI_essentials | Check model card |
| [layerdiffusion-foreground-from-background-joint](Transparent-Layers/layerdiffusion-foreground-from-background-joint.json) | LayerDiffusion (SD 1.5) | Generate a foreground and blend for a given background | same | same | ComfyUI-layerdiffuse, ComfyUI_essentials | Check model card |
| [layerdiffusion-extract-foreground-from-blend](Transparent-Layers/layerdiffusion-extract-foreground-from-blend.json) | LayerDiffusion (SDXL) | Recover the foreground layer from a blended image and its background | same | same | ComfyUI-layerdiffuse | Check model card |
| [layerdiffusion-extract-background-from-blend](Transparent-Layers/layerdiffusion-extract-background-from-blend.json) | LayerDiffusion (SDXL) | Recover the background layer from a blended image and its foreground | same | same | ComfyUI-layerdiffuse | Check model card |

### Background removal

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence |
|---|---|---|---|---|---|---|
| [rmbg-1.4-bria-remove-background](Background-Removal/rmbg-1.4-bria-remove-background.json) | BRIA RMBG 1.4 | Remove background, save RGBA | [602387193c/ComfyUI-wiki](https://github.com/602387193c/ComfyUI-wiki/tree/main/workflows) | [briaai/RMBG-1.4](https://huggingface.co/briaai/RMBG-1.4) | ComfyUI-BRIA_AI-RMBG | Non-commercial (BRIA RMBG-1.4 licence) |

### Segmentation and detection

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence |
|---|---|---|---|---|---|---|
| [grounding-dino-sam2-text-prompt-segment](Segmentation-and-Detection/grounding-dino-sam2-text-prompt-segment.json) | Grounding DINO + SAM 2.1 | Segment objects named in a text prompt | [neverbiasu/ComfyUI-SAM2](https://github.com/neverbiasu/ComfyUI-SAM2) (assets/workflow.png) | [facebook/sam2.1-hiera-base-plus](https://huggingface.co/facebook/sam2.1-hiera-base-plus), [ShilongLiu/GroundingDINO](https://huggingface.co/ShilongLiu/GroundingDINO) | ComfyUI-SAM2 | Apache-2.0 |
| [florence-2-sam2-caption-grounded-segment](Segmentation-and-Detection/florence-2-sam2-caption-grounded-segment.json) | Florence-2 + SAM 2 | Ground a phrase with Florence-2, then mask it with SAM 2 | [kijai/ComfyUI-segment-anything-2](https://github.com/kijai/ComfyUI-segment-anything-2/tree/main/example_workflows) | [Kijai/sam2-safetensors](https://huggingface.co/Kijai/sam2-safetensors), [microsoft/Florence-2-base](https://huggingface.co/microsoft/Florence-2-base) (auto-download) | ComfyUI-segment-anything-2, ComfyUI-Florence2, ComfyUI-KJNodes | Apache-2.0 (SAM 2); MIT (Florence-2) |
| [grounding-dino-hq-sam-text-prompt-segment](Segmentation-and-Detection/grounding-dino-hq-sam-text-prompt-segment.json) | Grounding DINO + HQ-SAM | Text-prompted high-quality masks for fine edges | [nomadoor/Comfy-with-ComfyUI](https://github.com/nomadoor/Comfy-with-ComfyUI/tree/main/src/workflows/data-utilities/ai-mask-generation) | auto-download ([1038lab/sam](https://huggingface.co/1038lab/sam)) | ComfyUI-RMBG | Apache-2.0 |
| [grounding-dino-sam-vit-h-text-prompt-segment](Segmentation-and-Detection/grounding-dino-sam-vit-h-text-prompt-segment.json) | Grounding DINO + SAM (ViT-H) | Same as above with the original SAM ViT-H (model choice changed from the source) | adapted from the row above | auto-download ([1038lab/sam](https://huggingface.co/1038lab/sam)) | ComfyUI-RMBG | Apache-2.0 |
| [sam-3.1-concept-segment-cutout](Segmentation-and-Detection/sam-3.1-concept-segment-cutout.json) | SAM 3.1 | Segment all instances of a text concept and cut them out (native ComfyUI nodes) | [nomadoor/Comfy-with-ComfyUI](https://github.com/nomadoor/Comfy-with-ComfyUI/tree/main/src/workflows/data-utilities/sam3) | `sam3.1_multiplex_fp16.safetensors` (ComfyUI repack of [facebook/sam3.1](https://huggingface.co/facebook/sam3.1)) | — (core nodes) | SAM License (gated, check terms) |

### Captioning, OCR and tagging

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence |
|---|---|---|---|---|---|---|
| [florence-2-detailed-caption](Captioning-OCR-and-Tagging/florence-2-detailed-caption.json) | Florence-2 | Detailed image caption (for prompts / datasets) | [nomadoor/Comfy-with-ComfyUI](https://github.com/nomadoor/Comfy-with-ComfyUI/tree/main/src/workflows/basic-workflows/florence2) | [microsoft/Florence-2-base-ft](https://huggingface.co/microsoft/Florence-2-base-ft) (auto-download) | ComfyUI-Florence2 | MIT |
| [florence-2-ocr](Captioning-OCR-and-Tagging/florence-2-ocr.json) | Florence-2 | Read text in an image | same | same | ComfyUI-Florence2 | MIT |
| [florence-2-document-vqa](Captioning-OCR-and-Tagging/florence-2-document-vqa.json) | Florence-2 | Ask questions about a document image | same | same | ComfyUI-Florence2 | MIT |
| [florence-2-object-detection](Captioning-OCR-and-Tagging/florence-2-object-detection.json) | Florence-2 | Detect and box objects | [nomadoor/Comfy-with-ComfyUI](https://github.com/nomadoor/Comfy-with-ComfyUI/tree/main/src/workflows/ai-capabilities/object-detection) | same | ComfyUI-Florence2 | MIT |
| [wd14-tagger-v3-anime-tags](Captioning-OCR-and-Tagging/wd14-tagger-v3-anime-tags.json) | WD14 Tagger (SwinV2 v3) | Danbooru-style tags from an image | [nomadoor/Comfy-with-ComfyUI](https://github.com/nomadoor/Comfy-with-ComfyUI/tree/main/src/workflows/ai-capabilities/tag-caption-generation) | [SmilingWolf/wd-swinv2-tagger-v3](https://huggingface.co/SmilingWolf/wd-swinv2-tagger-v3) (auto-download) | ComfyUI-WD14-Tagger | Apache-2.0 |

### Depth estimation

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence |
|---|---|---|---|---|---|---|
| [depth-anything-v2-large-depth-map](Depth-Estimation/depth-anything-v2-large-depth-map.json) | Depth Anything V2 Large | Depth map (ControlNet input); switch the checkpoint to `vitb` for Base | [Fannovel16/comfyui_controlnet_aux](https://github.com/Fannovel16/comfyui_controlnet_aux/tree/main/examples) (example_depth_anything_v2.png) | [depth-anything/Depth-Anything-V2-Large](https://huggingface.co/depth-anything/Depth-Anything-V2-Large) (auto-download) | comfyui_controlnet_aux | CC BY-NC 4.0 (Large); Base/Small Apache-2.0 |
| [depth-anything-v2-small-depth-map-low-vram](Depth-Estimation/depth-anything-v2-small-depth-map-low-vram.json) | Depth Anything V2 Small | Low-VRAM depth map (checkpoint changed from the source) | adapted from the row above | [depth-anything/Depth-Anything-V2-Small](https://huggingface.co/depth-anything/Depth-Anything-V2-Small) (auto-download) | comfyui_controlnet_aux | Apache-2.0 |
| [depth-anything-3-depth-map](Depth-Estimation/depth-anything-3-depth-map.json) | Depth Anything 3 | Depth map | [PozzettiAndrea/ComfyUI-DepthAnythingV3](https://github.com/PozzettiAndrea/ComfyUI-DepthAnythingV3/tree/main/workflows) | [depth-anything](https://huggingface.co/depth-anything) DA3 models (auto-download) | ComfyUI-DepthAnythingV3 | Check per checkpoint (Large/Giant non-commercial) |
| [depth-anything-3-point-cloud](Depth-Estimation/depth-anything-3-point-cloud.json) | Depth Anything 3 | Depth to 3D point cloud (preview and save) | same | same | ComfyUI-DepthAnythingV3 | same |
| [midas-depth-and-normal-map](Depth-Estimation/midas-depth-and-normal-map.json) | MiDaS | Depth and normal maps (ControlNet input) | [nomadoor/Comfy-with-ComfyUI](https://github.com/nomadoor/Comfy-with-ComfyUI/tree/main/src/workflows/ai-capabilities/depth-normal-map) | [lllyasviel/Annotators](https://huggingface.co/lllyasviel/Annotators) (auto-download) | comfyui_controlnet_aux | MIT |
| [marigold-depth-estimation](Depth-Estimation/marigold-depth-estimation.json) | Marigold | Diffusion-based high-detail depth | [kijai/ComfyUI-Marigold](https://github.com/kijai/ComfyUI-Marigold/tree/main/examples) | [prs-eth/marigold-v1-0](https://huggingface.co/prs-eth/marigold-v1-0) | ComfyUI-Marigold, ComfyUI_essentials | Apache-2.0 |
| [marigold-lcm-fast-depth-estimation](Depth-Estimation/marigold-lcm-fast-depth-estimation.json) | Marigold LCM | Faster few-step Marigold depth | same | [prs-eth/marigold-lcm-v1-0](https://huggingface.co/prs-eth/marigold-lcm-v1-0) | ComfyUI-Marigold, ComfyUI_essentials | Apache-2.0 |

### Pose estimation

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence |
|---|---|---|---|---|---|---|
| [dwpose-and-openpose-keypoints](Pose-Estimation/dwpose-and-openpose-keypoints.json) | DWPose, OpenPose | Body/hand/face pose skeletons side by side (ControlNet input) | [nomadoor/Comfy-with-ComfyUI](https://github.com/nomadoor/Comfy-with-ComfyUI/tree/main/src/workflows/basic-workflows/controlnet-prep) | [yzd-v/DWPose](https://huggingface.co/yzd-v/DWPose), [lllyasviel/Annotators](https://huggingface.co/lllyasviel/Annotators) (auto-download) | comfyui_controlnet_aux | DWPose Apache-2.0; OpenPose models non-commercial (CMU licence) |

## Already in the library (skipped as duplicates)

- RMBG 2.0 background removal — `01-Image/Image-Editing/Background-Removal/utility-remove-background.json`
- BiRefNet background removal — `01-Image/Image-Editing/Background-Removal/birefnet-remove-background.json`
- SAM 3 text-prompt segmentation — `01-Image/Image-Editing/Background-Removal/sam3-remove-background-segment-crop-object.json`

## Not available in ComfyUI

No authentic standalone ComfyUI image workflow was found for these entries, so none was added:

- **CatV2TON** — no ComfyUI node or workflow.
- **StableVITON** — no ComfyUI node or workflow.
- **OutfitAnyone** — weights not released.
- **Grounding DINO 1.5** — API-only, no open weights.
- **ZoeDepth** — node exists in comfyui_controlnet_aux, but only found inside larger ControlNet/InstantID generation graphs, not a standalone workflow.
- **CLIP ViT-L/14**, **SigLIP** — encoders used inside other workflows (unCLIP, IP-Adapter, Redux), no standalone image workflow.
- **BLIP-2** — no maintained ComfyUI node or workflow found.
