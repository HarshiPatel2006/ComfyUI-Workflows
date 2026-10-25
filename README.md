# ComfyUI Workflows Collection: FLUX, Qwen-Image, Wan, LTX-2, MiniMax H3, Krea 2 and more

[![Workflows](https://img.shields.io/badge/workflows-461-blue)](#workflow-catalog) [![ComfyUI](https://img.shields.io/badge/ComfyUI-workflows-green)](https://github.com/Comfy-Org/ComfyUI) [![Format](https://img.shields.io/badge/format-JSON-lightgrey)](#how-to-use) [![License](https://img.shields.io/badge/license-see%20below-purple)](#license)

A categorized library of **461 ready-to-use ComfyUI workflows** (`.json`) for **text-to-image (txt2img)**, **image-to-image (img2img) editing**, **inpainting and outpainting**, **background removal**, **upscaling**, **text-to-video and image-to-video (img2video)**, **lip-sync and talking avatars**, **face swap and character swap**, **text-to-speech and music**, **3D generation**, **batch automation** and a complete **AI short-film pipeline**.

Every workflow is a standalone ComfyUI file: drag it onto the ComfyUI canvas, install any missing custom nodes with ComfyUI-Manager, add the models, and press **Run**. The catalog below lists what each workflow does, which models it loads and which custom node packs it needs.

## Table of contents

- [Supported models and tasks](#supported-models-and-tasks)
- [Quick start](#quick-start)
- [Workflow catalog](#workflow-catalog)
  - [01 · Image Generation](#01--image-generation)
  - [02 · Image Editing](#02--image-editing)
  - [03 · Image Upscaling and Enhancement](#03--image-upscaling-and-enhancement)
  - [04 · AI Video](#04--ai-video)
  - [05 · Audio](#05--audio)
  - [06 · 3D Generation](#06--3d-generation)
  - [07 · Batch Processing and Automation](#07--batch-processing-and-automation)
  - [08 · Testing and Comparison](#08--testing-and-comparison)
  - [09 · AI Short Film Pipeline](#09--ai-short-film-pipeline)
  - [10 · LLM and Prompt Tools](#10--llm-and-prompt-tools)
  - [90 · Docs and Resources](#90--docs-and-resources)
  - [91 · Version Conflicts](#91--version-conflicts)
- [How to use](#how-to-use)
- [Requirements](#requirements)
- [Repository structure and naming](#repository-structure-and-naming)
- [Contributing](#contributing)
- [Credits](#credits)
- [License](#license)

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

## Quick start

1. Install [ComfyUI](https://github.com/Comfy-Org/ComfyUI) (or the [Desktop app](https://www.comfy.org/download)) and make sure [ComfyUI-Manager](https://github.com/Comfy-Org/ComfyUI-Manager) is available.
2. Download a workflow `.json` from the [catalog](#workflow-catalog) (or clone this repo) and **drag it onto the ComfyUI canvas**.
3. Open **Manager → Install Missing Custom Nodes**, restart ComfyUI, download the listed models into `ComfyUI/models/…`, then click **Run**.

## Workflow catalog

461 workflows: 421 in the normal UI format and 40 in API format (filenames ending in `-api`). Model names are the files each workflow loads; download links are usually in the notes inside the workflow.

### 01 · Image Generation

Text-to-image (txt2img) workflows for FLUX.2 / FLUX.3 Klein, Qwen-Image 2.1, Krea 2, Z-Image Turbo, Ming Image, SD 1.5 and more — plus ControlNet, LLM prompt enhancers, typography / logo / transparent PNG design and prompt batching. Folder: [`01-Image-Generation/`](01-Image-Generation) — 104 workflows.

#### ControlNet-guided generation (Canny, Union) (2)

Folder: [`01-Image-Generation/ControlNet-Guided/`](01-Image-Generation/ControlNet-Guided)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [sd15-juggernaut-reborn-txt2img-controlnet-canny](01-Image-Generation/ControlNet-Guided/sd15-juggernaut-reborn-txt2img-controlnet-canny.json) | Text to Image + ControlNet Canny | `juggernaut_reborn.safetensors`, `control_v11p_sd15_canny_fp16.safetensors` | comfyui_controlnet_aux |
| [z-image-turbo-txt2img-fp8-aio-controlnet-union](01-Image-Generation/ControlNet-Guided/z-image-turbo-txt2img-fp8-aio-controlnet-union.json) | Text to Image — FP8 AIO + ControlNet Union | `Z-Image-Turbo-Fun-Controlnet-Union.safetensors`, `z-image-turbo-fp8-aio.safetensors` | comfyui_controlnet_aux, rgthree-comfy |

#### Logos, posters, text in images, UI screens and transparent PNGs (14)

Folder: [`01-Image-Generation/Design-Typography-and-Transparent/`](01-Image-Generation/Design-Typography-and-Transparent)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [flux-3-klein-text-in-images](01-Image-Generation/Design-Typography-and-Transparent/flux-3-klein-text-in-images.json) | Text in Images | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-3d-lettering](01-Image-Generation/Design-Typography-and-Transparent/ming-image-0.1-3d-lettering.json) | 3D Lettering | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-app-and-website-screens](01-Image-Generation/Design-Typography-and-Transparent/ming-image-0.1-app-and-website-screens.json) | App and Website Screens | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-event-poster](01-Image-Generation/Design-Typography-and-Transparent/ming-image-0.1-event-poster.json) | Event Poster | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-game-screens-and-icons](01-Image-Generation/Design-Typography-and-Transparent/ming-image-0.1-game-screens-and-icons.json) | Game Screens and Icons | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-infographic](01-Image-Generation/Design-Typography-and-Transparent/ming-image-0.1-infographic.json) | Infographic | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-logo-design](01-Image-Generation/Design-Typography-and-Transparent/ming-image-0.1-logo-design.json) | Logo Design | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-logo-variations](01-Image-Generation/Design-Typography-and-Transparent/ming-image-0.1-logo-variations.json) | Logo Variations | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-social-media-post](01-Image-Generation/Design-Typography-and-Transparent/ming-image-0.1-social-media-post.json) | Social Media Post | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-transparent-png](01-Image-Generation/Design-Typography-and-Transparent/ming-image-0.1-transparent-png.json) | Transparent PNG | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-youtube-thumbnail](01-Image-Generation/Design-Typography-and-Transparent/ming-image-0.1-youtube-thumbnail.json) | YouTube Thumbnail | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [pixaroma-nodes-text-overlay](01-Image-Generation/Design-Typography-and-Transparent/pixaroma-nodes-text-overlay.json) | Text Overlay | — | ComfyUI-Pixaroma |
| [qwen-image-2.1-transparent-png](01-Image-Generation/Design-Typography-and-Transparent/qwen-image-2.1-transparent-png.json) | Transparent PNG | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [z-image-turbo-txt2img-text-overlay](01-Image-Generation/Design-Typography-and-Transparent/z-image-turbo-txt2img-text-overlay.json) | Text to Image + Text Overlay | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | ComfyUI-Pixaroma |

#### Text-to-image with LLM prompt enhancers and image-to-prompt-to-image (26)

Folder: [`01-Image-Generation/LLM-Prompt-Assisted/`](01-Image-Generation/LLM-Prompt-Assisted)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [anima-base-v1.0-anime-txt2img-gemma-4-prompt-enhancer](01-Image-Generation/LLM-Prompt-Assisted/anima-base-v1.0-anime-txt2img-gemma-4-prompt-enhancer.json) | Anime Text to Image + Gemma 4 Prompt Enhancer | `qwen_image_vae.safetensors`, `qwen_3_06b_base.safetensors`, `gemma4_e4b_it_fp8_scaled.safetensors` +1 more | ComfyUI-Pixaroma |
| [boogu-image-txt2img-prompt-enhancer](01-Image-Generation/LLM-Prompt-Assisted/boogu-image-txt2img-prompt-enhancer.json) | Text to Image + Prompt Enhancer | `ae.safetensors`, `boogu_image_turbo_hotfix_int8_convrot.safetensors`, `qwen3vl_8b_fp8_scaled.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-image-to-prompt-to-image-qwen-3.5](01-Image-Generation/LLM-Prompt-Assisted/flux-2-klein-9b-image-to-prompt-to-image-qwen-3.5.json) | Image to Prompt to Image (Qwen 3.5) | `flux-2-klein-9b-fp8mixed.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma |
| [flux-2-klein-9b-txt2img-qwen-3.5-prompt-enhancer](01-Image-Generation/LLM-Prompt-Assisted/flux-2-klein-9b-txt2img-qwen-3.5-prompt-enhancer.json) | Text to Image + Qwen 3.5 Prompt Enhancer | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `qwen3.5_4b_bf16.safetensors` +1 more | ComfyUI-Pixaroma |
| [flux-3-klein-image-to-prompt-to-image](01-Image-Generation/LLM-Prompt-Assisted/flux-3-klein-image-to-prompt-to-image.json) | Image to Prompt to Image | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma |
| [flux-3-klein-txt2img-prompt-upsampler](01-Image-Generation/LLM-Prompt-Assisted/flux-3-klein-txt2img-prompt-upsampler.json) | Text to Image + Prompt Upsampler | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma |
| [krea-2-image-to-prompt-to-image-ep31-ai-prompt-node](01-Image-Generation/LLM-Prompt-Assisted/krea-2-image-to-prompt-to-image-ep31-ai-prompt-node.json) | Image to Prompt to Image (Ep31 AI Prompt Node) | `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-image-to-prompt-to-image](01-Image-Generation/LLM-Prompt-Assisted/krea-2-image-to-prompt-to-image.json) | Image to Prompt to Image | `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-int8-image-to-prompt-to-image](01-Image-Generation/LLM-Prompt-Assisted/krea-2-int8-image-to-prompt-to-image.json) | Image to Prompt to Image | `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors`, `Huihui-Qwen3-VL-4B-Instruct-abliterated-fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-int8-txt2img-extra-pass-image-to-prompt](01-Image-Generation/LLM-Prompt-Assisted/krea-2-int8-txt2img-extra-pass-image-to-prompt.json) | Text to Image + Extra Pass + Image to Prompt | `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors`, `Huihui-Qwen3-VL-4B-Instruct-abliterated-fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-int8-txt2img-extra-pass-prompt-enhancer](01-Image-Generation/LLM-Prompt-Assisted/krea-2-int8-txt2img-extra-pass-prompt-enhancer.json) | Text to Image + Extra Pass + Prompt Enhancer | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2_turbo_int8_convrot.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-int8-txt2img-prompt-enhancer](01-Image-Generation/LLM-Prompt-Assisted/krea-2-int8-txt2img-prompt-enhancer.json) | Text to Image + Prompt Enhancer | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2_turbo_int8_convrot.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-ai-prompt-enhancer-ep31](01-Image-Generation/LLM-Prompt-Assisted/krea-2-txt2img-ai-prompt-enhancer-ep31.json) | Text to Image + AI Prompt Enhancer (Ep31) | `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-extra-pass-prompt-enhancer-uncensored](01-Image-Generation/LLM-Prompt-Assisted/krea-2-txt2img-extra-pass-prompt-enhancer-uncensored.json) | Text to Image + Extra Pass + Prompt Enhancer (Uncensored) | `krea2_turbo_fp8_scaled.safetensors`, `Huihui-Qwen3-VL-4B-Instruct-abliterated-fp8_scaled.safetensors`, `qwen_image_vae.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-extra-pass-prompt-enhancer](01-Image-Generation/LLM-Prompt-Assisted/krea-2-txt2img-extra-pass-prompt-enhancer.json) | Text to Image + Extra Pass + Prompt Enhancer | `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-prompt-enhancer-ep28](01-Image-Generation/LLM-Prompt-Assisted/krea-2-txt2img-prompt-enhancer-ep28.json) | Text to Image + Prompt Enhancer (Ep28) | `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-prompt-enhancer-uncensored](01-Image-Generation/LLM-Prompt-Assisted/krea-2-txt2img-prompt-enhancer-uncensored.json) | Text to Image + Prompt Enhancer (Uncensored) | `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors`, `Huihui-Qwen3-VL-4B-Instruct-abliterated-fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-prompt-enhancer](01-Image-Generation/LLM-Prompt-Assisted/krea-2-txt2img-prompt-enhancer.json) | Text to Image + Prompt Enhancer | `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [ming-image-0.1-txt2img-prompt-enhancer](01-Image-Generation/LLM-Prompt-Assisted/ming-image-0.1-txt2img-prompt-enhancer.json) | Text to Image + Prompt Enhancer | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma |
| [nunchaku-z-image-turbo-txt2img-qwenvl-gguf-prompt-enhancer](01-Image-Generation/LLM-Prompt-Assisted/nunchaku-z-image-turbo-txt2img-qwenvl-gguf-prompt-enhancer.json) | Z-Image Turbo — Text to Image + QwenVL GGUF Prompt Enhancer | `Qwen3VL-8B-Instruct-Q8_0.gguf`, `svdq-int4_r256-z-image-turbo.safetensors`, `Huihui-Qwen3-4B-abliterated-v2_fp8mixed.safetensors` +1 more | ComfyUI-QwenVL, ComfyUI-nunchaku |
| [qwen-image-2.1-image-to-prompt-to-image](01-Image-Generation/LLM-Prompt-Assisted/qwen-image-2.1-image-to-prompt-to-image.json) | Image to Prompt to Image | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-txt2img-prompt-enhancer](01-Image-Generation/LLM-Prompt-Assisted/qwen-image-2.1-txt2img-prompt-enhancer.json) | Text to Image + Prompt Enhancer | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [z-image-turbo-image-to-prompt-to-image-gemma-4](01-Image-Generation/LLM-Prompt-Assisted/z-image-turbo-image-to-prompt-to-image-gemma-4.json) | Image to Prompt to Image (Gemma 4) | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` +1 more | ComfyUI-Pixaroma |
| [z-image-turbo-int8-txt2img-ai-prompt-enhancer](01-Image-Generation/LLM-Prompt-Assisted/z-image-turbo-int8-txt2img-ai-prompt-enhancer.json) | Text to Image + AI Prompt Enhancer | `ae.safetensors`, `z_image_turbo_int8_convrot.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | ComfyUI-Pixaroma |
| [z-image-turbo-txt2img-gemma-4-prompt-enhancer-find-and-replace](01-Image-Generation/LLM-Prompt-Assisted/z-image-turbo-txt2img-gemma-4-prompt-enhancer-find-and-replace.json) | Text to Image + Gemma 4 Prompt Enhancer + Find and Replace | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` +1 more | ComfyUI-Pixaroma |
| [z-image-turbo-txt2img-gemma-4-prompt-enhancer](01-Image-Generation/LLM-Prompt-Assisted/z-image-turbo-txt2img-gemma-4-prompt-enhancer.json) | Text to Image + Gemma 4 Prompt Enhancer | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` +1 more | ComfyUI-Pixaroma |

#### Prompt lists, styles and batch variations (17)

Folder: [`01-Image-Generation/Prompt-Batching-and-Variations/`](01-Image-Generation/Prompt-Batching-and-Variations)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [flux-2-klein-9b-build-a-prompt-from-switches](01-Image-Generation/Prompt-Batching-and-Variations/flux-2-klein-9b-build-a-prompt-from-switches.json) | Build a Prompt from Switches | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-every-prompt-combination-with-brackets](01-Image-Generation/Prompt-Batching-and-Variations/flux-2-klein-9b-every-prompt-combination-with-brackets.json) | Every Prompt Combination with Brackets | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-image-per-prompt](01-Image-Generation/Prompt-Batching-and-Variations/flux-2-klein-9b-one-image-per-prompt.json) | One Image per Prompt | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-subject-in-many-styles](01-Image-Generation/Prompt-Batching-and-Variations/flux-2-klein-9b-one-subject-in-many-styles.json) | One Subject in Many Styles | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-queue-a-list-of-prompts](01-Image-Generation/Prompt-Batching-and-Variations/flux-2-klein-9b-queue-a-list-of-prompts.json) | Queue a List of Prompts | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-random-prompts-every-run](01-Image-Generation/Prompt-Batching-and-Variations/flux-2-klein-9b-random-prompts-every-run.json) | Random Prompts Every Run | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-short-ideas-into-finished-images-qwen-3.5-ai-prompt](01-Image-Generation/Prompt-Batching-and-Variations/flux-2-klein-9b-short-ideas-into-finished-images-qwen-3.5-ai-prompt.json) | Short Ideas into Finished Images (Qwen 3.5 AI Prompt) | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma |
| [flux-2-klein-9b-short-story-to-storyboard-qwen-3.5-ai-prompt](01-Image-Generation/Prompt-Batching-and-Variations/flux-2-klein-9b-short-story-to-storyboard-qwen-3.5-ai-prompt.json) | Short Story to Storyboard (Qwen 3.5 AI Prompt) | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma |
| [pixaroma-nodes-prompt-multi-from-list](01-Image-Generation/Prompt-Batching-and-Variations/pixaroma-nodes-prompt-multi-from-list.json) | Prompt Multi — From List | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-prompt-multi-queue-text](01-Image-Generation/Prompt-Batching-and-Variations/pixaroma-nodes-prompt-multi-queue-text.json) | Prompt Multi — Queue Text | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-prompt-pack-line](01-Image-Generation/Prompt-Batching-and-Variations/pixaroma-nodes-prompt-pack-line.json) | Prompt Pack — Line | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-prompt-pack-paragraph](01-Image-Generation/Prompt-Batching-and-Variations/pixaroma-nodes-prompt-pack-paragraph.json) | Prompt Pack — Paragraph | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-prompt-stack](01-Image-Generation/Prompt-Batching-and-Variations/pixaroma-nodes-prompt-stack.json) | Prompt Stack | — | ComfyUI-Pixaroma |
| [z-image-turbo-prompt-multi-queue-text](01-Image-Generation/Prompt-Batching-and-Variations/z-image-turbo-prompt-multi-queue-text.json) | Prompt Multi — Queue Text | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | ComfyUI-Pixaroma |
| [z-image-turbo-prompt-pack-line](01-Image-Generation/Prompt-Batching-and-Variations/z-image-turbo-prompt-pack-line.json) | Prompt Pack — Line | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | ComfyUI-Pixaroma |
| [z-image-turbo-prompt-pack-paragraph](01-Image-Generation/Prompt-Batching-and-Variations/z-image-turbo-prompt-pack-paragraph.json) | Prompt Pack — Paragraph | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | ComfyUI-Pixaroma |
| [z-image-turbo-prompt-stack](01-Image-Generation/Prompt-Batching-and-Variations/z-image-turbo-prompt-stack.json) | Prompt Stack | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | ComfyUI-Pixaroma |

#### Text-to-image (txt2img) generation (45)

Folder: [`01-Image-Generation/Text-to-Image/`](01-Image-Generation/Text-to-Image)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [anima-base-v1.0-anime-txt2img-seedvr2-upscale](01-Image-Generation/Text-to-Image/anima-base-v1.0-anime-txt2img-seedvr2-upscale.json) | Anime Text to Image + SeedVR2 Upscale | `anima-base-v1.0.safetensors`, `qwen_3_06b_base.safetensors`, `qwen_image_vae.safetensors` +2 more | ComfyUI-SeedVR2_VideoUpscaler, ComfyUI-Pixaroma |
| [anima-base-v1.0-anime-txt2img](01-Image-Generation/Text-to-Image/anima-base-v1.0-anime-txt2img.json) | Anime Text to Image | `anima-base-v1.0.safetensors`, `qwen_3_06b_base.safetensors`, `qwen_image_vae.safetensors` | ComfyUI-Pixaroma |
| [boogu-image-txt2img](01-Image-Generation/Text-to-Image/boogu-image-txt2img.json) | Text to Image | `ae.safetensors`, `qwen3vl_8b_fp8_scaled.safetensors`, `boogu_image_turbo_hotfix_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [ernie-image-turbo-txt2img-gguf](01-Image-Generation/Text-to-Image/ernie-image-turbo-txt2img-gguf.json) | Text to Image — GGUF | `ministral-3-3b.safetensors`, `flux2-vae.safetensors`, `ernie-image-turbo-Q8_0.gguf` | ComfyUI-GGUF, ComfyUI-Pixaroma |
| [flux-2-klein-4b-fp8-distilled-txt2img-basic](01-Image-Generation/Text-to-Image/flux-2-klein-4b-fp8-distilled-txt2img-basic.json) | Text to Image — Basic | `flux-2-klein-4b-fp8.safetensors`, `qwen_3_4b.safetensors`, `flux2-vae.safetensors` | Core only |
| [flux-2-klein-9b-fp8-distilled-txt2img-basic](01-Image-Generation/Text-to-Image/flux-2-klein-9b-fp8-distilled-txt2img-basic.json) | Text to Image — Basic | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | Core only |
| [flux-2-klein-9b-fp8-txt2img-ep16](01-Image-Generation/Text-to-Image/flux-2-klein-9b-fp8-txt2img-ep16.json) | Text to Image (Ep16) | `flux-2-klein-9b-fp8mixed.safetensors`, `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-txt2img](01-Image-Generation/Text-to-Image/flux-2-klein-9b-txt2img.json) | Text to Image | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-layout-with-boxes](01-Image-Generation/Text-to-Image/flux-3-klein-layout-with-boxes.json) | Layout with Boxes | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-txt2img-z-image-realism-pass](01-Image-Generation/Text-to-Image/flux-3-klein-txt2img-z-image-realism-pass.json) | Text to Image + Z-Image Realism Pass | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` +4 more | ComfyUI-Pixaroma |
| [flux-3-klein-txt2img](01-Image-Generation/Text-to-Image/flux-3-klein-txt2img.json) | Text to Image | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [krea-2-int8-txt2img-extra-pass-lora](01-Image-Generation/Text-to-Image/krea-2-int8-txt2img-extra-pass-lora.json) | Text to Image + Extra Pass + LoRA | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2-questpaint26_comfyui.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma, rgthree-comfy |
| [krea-2-int8-txt2img-extra-pass](01-Image-Generation/Text-to-Image/krea-2-int8-txt2img-extra-pass.json) | Text to Image + Extra Pass | `qwen3vl_4b_fp8_scaled.safetensors`, `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-int8-txt2img-simple-lora](01-Image-Generation/Text-to-Image/krea-2-int8-txt2img-simple-lora.json) | Text to Image — Simple + LoRA | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2_turbo_int8_convrot.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma, rgthree-comfy |
| [krea-2-int8-txt2img-simple](01-Image-Generation/Text-to-Image/krea-2-int8-txt2img-simple.json) | Text to Image — Simple | `qwen3vl_4b_fp8_scaled.safetensors`, `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-2k-hi-res-prompt-enhancer-uncensored](01-Image-Generation/Text-to-Image/krea-2-txt2img-2k-hi-res-prompt-enhancer-uncensored.json) | Text to Image — 2K Hi-Res + Prompt Enhancer (Uncensored) | `krea2_turbo_fp8_scaled.safetensors`, `Huihui-Qwen3-VL-4B-Instruct-abliterated-fp8_scaled.safetensors`, `qwen_image_vae.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-2k-hi-res-prompt-enhancer](01-Image-Generation/Text-to-Image/krea-2-txt2img-2k-hi-res-prompt-enhancer.json) | Text to Image — 2K Hi-Res + Prompt Enhancer | `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-ep28](01-Image-Generation/Text-to-Image/krea-2-txt2img-ep28.json) | Text to Image (Ep28) | `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-extra-pass-lora](01-Image-Generation/Text-to-Image/krea-2-txt2img-extra-pass-lora.json) | Text to Image + Extra Pass + LoRA | `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma, rgthree-comfy |
| [krea-2-txt2img-extra-pass](01-Image-Generation/Text-to-Image/krea-2-txt2img-extra-pass.json) | Text to Image + Extra Pass | `qwen3vl_4b_fp8_scaled.safetensors`, `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-simple-lora](01-Image-Generation/Text-to-Image/krea-2-txt2img-simple-lora.json) | Text to Image — Simple + LoRA | `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma, rgthree-comfy |
| [krea-2-txt2img-simple-low-vram](01-Image-Generation/Text-to-Image/krea-2-txt2img-simple-low-vram.json) | Text to Image — Simple — Low VRAM | `qwen3vl_4b_fp8_scaled.safetensors`, `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-simple](01-Image-Generation/Text-to-Image/krea-2-txt2img-simple.json) | Text to Image — Simple | `qwen3vl_4b_fp8_scaled.safetensors`, `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [lens-txt2img](01-Image-Generation/Text-to-Image/lens-txt2img.json) | Text to Image | `lens_bf16.safetensors`, `gpt_oss_20b_nvfp4.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-txt2img](01-Image-Generation/Text-to-Image/ming-image-0.1-txt2img.json) | Text to Image | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [minimax-h3-txt2img-single-frame](01-Image-Generation/Text-to-Image/minimax-h3-txt2img-single-frame.json) | Text to Image (Single Frame) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `minimax_h3_video_vae_fp16.safetensors` | ComfyUI-Pixaroma |
| [nunchaku-flux.1-dev-txt2img](01-Image-Generation/Text-to-Image/nunchaku-flux.1-dev-txt2img.json) | Flux.1 Dev — Text to Image | `t5-v1_1-xxl-encoder-Q8_0.gguf`, `clip_l.safetensors`, `ae.safetensors` +1 more | ComfyUI-GGUF, ComfyUI-nunchaku |
| [nunchaku-qwen-image-lightning-txt2img](01-Image-Generation/Text-to-Image/nunchaku-qwen-image-lightning-txt2img.json) | Qwen Image Lightning — Text to Image | `svdq-int4_r128-qwen-image-lightningv1.1-8steps.safetensors`, `qwen_2.5_vl_7b_fp8_scaled.safetensors`, `qwen_image_vae.safetensors` | ComfyUI-nunchaku |
| [nunchaku-z-image-turbo-txt2img](01-Image-Generation/Text-to-Image/nunchaku-z-image-turbo-txt2img.json) | Z-Image Turbo — Text to Image | `ae.safetensors`, `svdq-int4_r256-z-image-turbo.safetensors`, `Huihui-Qwen3-4B-abliterated-v2_fp8mixed.safetensors` | ComfyUI-nunchaku |
| [qwen-image-2.1-txt2img-low-vram](01-Image-Generation/Text-to-Image/qwen-image-2.1-txt2img-low-vram.json) | Text to Image — Low VRAM | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-txt2img-turbo](01-Image-Generation/Text-to-Image/qwen-image-2.1-txt2img-turbo.json) | Text to Image — Turbo | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma |
| [qwen-image-2.1-txt2img](01-Image-Generation/Text-to-Image/qwen-image-2.1-txt2img.json) | Text to Image | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [sd15-juggernaut-reborn-txt2img-lora-starter](01-Image-Generation/Text-to-Image/sd15-juggernaut-reborn-txt2img-lora-starter.json) | SD 1.5 text-to-image with Juggernaut Reborn plus a style LoRA (ComfyUI-Easy-Install starter version) | `juggernaut_reborn.safetensors`, `CakeStyle.safetensors` | Core only |
| [sd15-juggernaut-reborn-txt2img-lora](01-Image-Generation/Text-to-Image/sd15-juggernaut-reborn-txt2img-lora.json) | Text to Image + LoRA | `juggernaut_reborn.safetensors`, `CakeStyle.safetensors` | Core only |
| [sd15-juggernaut-reborn-txt2img](01-Image-Generation/Text-to-Image/sd15-juggernaut-reborn-txt2img.json) | Text to Image | `juggernaut_reborn.safetensors` | Core only |
| [z-image-turbo-int8-txt2img](01-Image-Generation/Text-to-Image/z-image-turbo-int8-txt2img.json) | Text to Image | `qwen_3_4b_fp8_mixed.safetensors`, `z_image_turbo_int8_convrot.safetensors`, `ae.safetensors` | ComfyUI-Pixaroma |
| [z-image-turbo-txt2img-character-sheet-alt-1](01-Image-Generation/Text-to-Image/z-image-turbo-txt2img-character-sheet-alt-1.json) | Z-Image Turbo character sheet, alternate prompt/settings | `z_image_turbo_bf16.safetensors`, `qwen_3_4b.safetensors`, `ae.safetensors` | Core only |
| [z-image-turbo-txt2img-character-sheet-alt-2](01-Image-Generation/Text-to-Image/z-image-turbo-txt2img-character-sheet-alt-2.json) | Z-Image Turbo character sheet, alternate prompt/settings | `z_image_turbo_bf16.safetensors`, `qwen_3_4b.safetensors`, `ae.safetensors` | Core only |
| [z-image-turbo-txt2img-character-sheet](01-Image-Generation/Text-to-Image/z-image-turbo-txt2img-character-sheet.json) | Z-Image Turbo character sheet (based on the official ComfyUI Z-Image template) | `qwen_3_4b.safetensors`, `ae.safetensors`, `z_image_turbo_bf16.safetensors` | Core only |
| [z-image-turbo-txt2img-fp8-aio-checkpoint](01-Image-Generation/Text-to-Image/z-image-turbo-txt2img-fp8-aio-checkpoint.json) | Text to Image — FP8 AIO Checkpoint | `z-image-turbo-fp8-aio.safetensors` | Core only |
| [z-image-turbo-txt2img-fp8-aio-lora](01-Image-Generation/Text-to-Image/z-image-turbo-txt2img-fp8-aio-lora.json) | Text to Image — FP8 AIO + LoRA | `pixag1rlwh1t3.safetensors`, `z-image-turbo-fp8-aio.safetensors` | Core only |
| [z-image-turbo-txt2img-fp8-aio-starter](01-Image-Generation/Text-to-Image/z-image-turbo-txt2img-fp8-aio-starter.json) | Z-Image Turbo text-to-image from one FP8 all-in-one checkpoint (ComfyUI-Easy-Install starter version) | `z-image-turbo-fp8-aio.safetensors` | Core only |
| [z-image-turbo-txt2img-fp8-ep18](01-Image-Generation/Text-to-Image/z-image-turbo-txt2img-fp8-ep18.json) | Text to Image — FP8 (Ep18) | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | ComfyUI-Pixaroma |
| [z-image-turbo-txt2img-fp8](01-Image-Generation/Text-to-Image/z-image-turbo-txt2img-fp8.json) | Text to Image — FP8 | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | Core only |
| [z-image-turbo-txt2img-gguf](01-Image-Generation/Text-to-Image/z-image-turbo-txt2img-gguf.json) | Text to Image — GGUF | `z-image-turbo-q4_k_s.gguf`, `qwen-4b-zimage-heretic-q8.gguf`, `ae.safetensors` | ComfyUI-GGUF |

### 02 · Image Editing

Image-to-image (img2img) and instruction editing: single- and multi-image edits, inpainting, outpainting, object removal, background removal, outfit and pose changes, sketch-to-image and compositing tools. Folder: [`02-Image-Editing/`](02-Image-Editing) — 98 workflows.

#### Background removal and segmentation (5)

Folder: [`02-Image-Editing/Background-Removal/`](02-Image-Editing/Background-Removal)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [birefnet-remove-background](02-Image-Editing/Background-Removal/birefnet-remove-background.json) | Remove Background | `birefnet.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-remove-background](02-Image-Editing/Background-Removal/qwen-image-2.1-remove-background.json) | Remove Background | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [sam3-remove-background-segment-crop-object](02-Image-Editing/Background-Removal/sam3-remove-background-segment-crop-object.json) | Remove Background (Segment + Crop Object) | — | ComfyUI-RMBG |
| [utility-remove-background-from-transparent-items](02-Image-Editing/Background-Removal/utility-remove-background-from-transparent-items.json) | Remove Background from Transparent Items | — | ComfyUI-RMBG |
| [utility-remove-background](02-Image-Editing/Background-Removal/utility-remove-background.json) | Remove Background | — | ComfyUI-RMBG, ComfyUI_LayerStyle, rgthree-comfy |

#### Outfit transfer, pose and character edits (9)

Folder: [`02-Image-Editing/Character-Outfit-and-Pose/`](02-Image-Editing/Character-Outfit-and-Pose)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [flux-2-klein-9b-character-turnaround-sheet-from-one-image](02-Image-Editing/Character-Outfit-and-Pose/flux-2-klein-9b-character-turnaround-sheet-from-one-image.json) | Character Turnaround Sheet from One Image | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-character-sheet](02-Image-Editing/Character-Outfit-and-Pose/flux-3-klein-character-sheet.json) | Character Sheet | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-outfit-change](02-Image-Editing/Character-Outfit-and-Pose/flux-3-klein-outfit-change.json) | Outfit Change | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [krea-2-outfit-change-outfit-lora](02-Image-Editing/Character-Outfit-and-Pose/krea-2-outfit-change-outfit-lora.json) | Outfit Change + Outfit LoRA | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [krea-2-outfit-transfer-v2](02-Image-Editing/Character-Outfit-and-Pose/krea-2-outfit-transfer-v2.json) | Outfit Transfer v2 | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [qwen-image-2.1-character-sheet](02-Image-Editing/Character-Outfit-and-Pose/qwen-image-2.1-character-sheet.json) | Character Sheet | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-outfit-change-turbo](02-Image-Editing/Character-Outfit-and-Pose/qwen-image-2.1-outfit-change-turbo.json) | Outfit Change — Turbo | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma |
| [qwen-image-2.1-outfit-change](02-Image-Editing/Character-Outfit-and-Pose/qwen-image-2.1-outfit-change.json) | Outfit Change | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-pose-from-a-picture](02-Image-Editing/Character-Outfit-and-Pose/qwen-image-2.1-pose-from-a-picture.json) | Pose from a Picture | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |

#### Crop, compose, paint, stitch and other image tools (15)

Folder: [`02-Image-Editing/Compositing-and-Image-Tools/`](02-Image-Editing/Compositing-and-Image-Tools)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [pixaroma-nodes-3d-builder-ep11](02-Image-Editing/Compositing-and-Image-Tools/pixaroma-nodes-3d-builder-ep11.json) | 3D Builder (Ep11) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-3d-builder-ep13](02-Image-Editing/Compositing-and-Image-Tools/pixaroma-nodes-3d-builder-ep13.json) | 3D Builder (Ep13) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-combine-join-two-images](02-Image-Editing/Compositing-and-Image-Tools/pixaroma-nodes-combine-join-two-images.json) | Combine — Join Two Images | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-crop-ep11](02-Image-Editing/Compositing-and-Image-Tools/pixaroma-nodes-crop-ep11.json) | Crop (Ep11) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-crop-ep13](02-Image-Editing/Compositing-and-Image-Tools/pixaroma-nodes-crop-ep13.json) | Crop (Ep13) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-image-composer-ep11](02-Image-Editing/Compositing-and-Image-Tools/pixaroma-nodes-image-composer-ep11.json) | Image Composer (Ep11) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-image-composer-ep13](02-Image-Editing/Compositing-and-Image-Tools/pixaroma-nodes-image-composer-ep13.json) | Image Composer (Ep13) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-paint-ep11](02-Image-Editing/Compositing-and-Image-Tools/pixaroma-nodes-paint-ep11.json) | Paint (Ep11) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-paint-ep13](02-Image-Editing/Compositing-and-Image-Tools/pixaroma-nodes-paint-ep13.json) | Paint (Ep13) | — | ComfyUI-Pixaroma |
| [utility-image-blend](02-Image-Editing/Compositing-and-Image-Tools/utility-image-blend.json) | Image Blend | — | ComfyUI-RMBG, ComfyUI_LayerStyle |
| [utility-image-combiner-for-transparent-items](02-Image-Editing/Compositing-and-Image-Tools/utility-image-combiner-for-transparent-items.json) | Image Combiner for Transparent Items | — | ComfyUI-RMBG |
| [utility-image-combiner](02-Image-Editing/Compositing-and-Image-Tools/utility-image-combiner.json) | Image Combiner | — | ComfyUI-RMBG |
| [utility-image-scale](02-Image-Editing/Compositing-and-Image-Tools/utility-image-scale.json) | Image Scale | — | ComfyUI-KJNodes |
| [utility-image-stitch](02-Image-Editing/Compositing-and-Image-Tools/utility-image-stitch.json) | Image Stitch | — | ComfyUI-RMBG, rgthree-comfy |
| [utility-image-transformation](02-Image-Editing/Compositing-and-Image-Tools/utility-image-transformation.json) | Image Transformation | — | ComfyUI_LayerStyle, rgthree-comfy |

#### Inpainting, outpainting and object removal (14)

Folder: [`02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/`](02-Image-Editing/Inpaint-Outpaint-and-Object-Removal)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [flux-2-klein-4b-fp8-distilled-inpaint](02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/flux-2-klein-4b-fp8-distilled-inpaint.json) | Inpaint | `flux-2-klein-4b-fp8.safetensors`, `qwen_3_4b.safetensors`, `flux2-vae.safetensors` | ComfyUI-Inpaint-CropAndStitch, rgthree-comfy |
| [flux-2-klein-9b-fp8-distilled-inpaint](02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-fp8-distilled-inpaint.json) | Inpaint | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Inpaint-CropAndStitch, rgthree-comfy |
| [flux-2-klein-9b-fp8-distilled-paint-guided-edit](02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-fp8-distilled-paint-guided-edit.json) | Paint-Guided Edit | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-fp8-inpaint-ep22](02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-fp8-inpaint-ep22.json) | Inpaint (Ep22) | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-int8-inpaint](02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-int8-inpaint.json) | Inpaint | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-kv-fp8-inpaint](02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-kv-fp8-inpaint.json) | Inpaint | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | ComfyUI-Inpaint-CropAndStitch, rgthree-comfy |
| [flux-2-klein-9b-kv-fp8-outpaint-custom-ratio](02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-kv-fp8-outpaint-custom-ratio.json) | Outpaint (Custom Ratio) | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | ComfyUI-KJNodes, rgthree-comfy |
| [flux-2-klein-9b-outpaint](02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-outpaint.json) | Outpaint | `flux-2-klein-9b-int8-convrot.safetensors`, `pixaoutpaint.safetensors`, `qwen_3_8b_fp8mixed.safetensors` +1 more | ComfyUI-Pixaroma |
| [flux-2-klein-9b-paint-to-image](02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-paint-to-image.json) | Paint to Image | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-edit-inside-a-box](02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/flux-3-klein-edit-inside-a-box.json) | Edit inside a Box | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-outpaint](02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/flux-3-klein-outpaint.json) | Outpaint | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma |
| [lama-object-remover](02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/lama-object-remover.json) | Object Remover | — | ComfyUI-RMBG |
| [qwen-image-2.1-inpaint](02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/qwen-image-2.1-inpaint.json) | Inpaint | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-outpaint](02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/qwen-image-2.1-outpaint.json) | Outpaint | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma |

#### Multi-image edits and composition (18)

Folder: [`02-Image-Editing/Multi-Image-Composition/`](02-Image-Editing/Multi-Image-Composition)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [flux-2-klein-4b-fp8-distilled-multi-image-edit-2-images](02-Image-Editing/Multi-Image-Composition/flux-2-klein-4b-fp8-distilled-multi-image-edit-2-images.json) | Multi-Image Edit — 2 Images | `flux-2-klein-4b-fp8.safetensors`, `qwen_3_4b.safetensors`, `flux2-vae.safetensors` | Core only |
| [flux-2-klein-9b-fp8-distilled-multi-image-edit-2-images](02-Image-Editing/Multi-Image-Composition/flux-2-klein-9b-fp8-distilled-multi-image-edit-2-images.json) | Multi-Image Edit — 2 Images | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | Core only |
| [flux-2-klein-9b-image-composer-to-image](02-Image-Editing/Multi-Image-Composition/flux-2-klein-9b-image-composer-to-image.json) | Image Composer to Image | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-kv-fp8-image-blend](02-Image-Editing/Multi-Image-Composition/flux-2-klein-9b-kv-fp8-image-blend.json) | Image Blend | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | ComfyUI-RMBG, ComfyUI_LayerStyle, rgthree-comfy |
| [flux-2-klein-9b-kv-fp8-multi-image-edit-2-images](02-Image-Editing/Multi-Image-Composition/flux-2-klein-9b-kv-fp8-multi-image-edit-2-images.json) | Multi-Image Edit — 2 Images | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | Core only |
| [flux-2-klein-9b-kv-fp8-multi-image-edit-3-images](02-Image-Editing/Multi-Image-Composition/flux-2-klein-9b-kv-fp8-multi-image-edit-3-images.json) | Multi-Image Edit — 3 Images | `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors`, `flux2-vae.safetensors` | Core only |
| [flux-2-klein-9b-kv-fp8-multi-image-edit-4-images](02-Image-Editing/Multi-Image-Composition/flux-2-klein-9b-kv-fp8-multi-image-edit-4-images.json) | Multi-Image Edit — 4 Images | `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors`, `flux2-vae.safetensors` | Core only |
| [flux-3-klein-character-in-a-scene](02-Image-Editing/Multi-Image-Composition/flux-3-klein-character-in-a-scene.json) | Character in a Scene | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-group-photo](02-Image-Editing/Multi-Image-Composition/flux-3-klein-group-photo.json) | Group Photo | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-logo-on-a-product](02-Image-Editing/Multi-Image-Composition/flux-3-klein-logo-on-a-product.json) | Logo on a Product | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-product-ad](02-Image-Editing/Multi-Image-Composition/flux-3-klein-product-ad.json) | Product Ad | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-product-ad-from-two-pictures](02-Image-Editing/Multi-Image-Composition/ming-image-0.1-product-ad-from-two-pictures.json) | Product Ad from Two Pictures | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-character-in-a-scene](02-Image-Editing/Multi-Image-Composition/qwen-image-2.1-character-in-a-scene.json) | Character in a Scene | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-logo-on-a-product](02-Image-Editing/Multi-Image-Composition/qwen-image-2.1-logo-on-a-product.json) | Logo on a Product | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-multi-image-edit-2-images-prompt-enhancer](02-Image-Editing/Multi-Image-Composition/qwen-image-2.1-multi-image-edit-2-images-prompt-enhancer.json) | Multi-Image Edit — 2 Images + Prompt Enhancer | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-multi-image-edit-3-images](02-Image-Editing/Multi-Image-Composition/qwen-image-2.1-multi-image-edit-3-images.json) | Multi-Image Edit — 3 Images | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-multi-image-edit-4-images](02-Image-Editing/Multi-Image-Composition/qwen-image-2.1-multi-image-edit-4-images.json) | Multi-Image Edit — 4 Images | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-multi-image-edit-group-photo-from-6-images](02-Image-Editing/Multi-Image-Composition/qwen-image-2.1-multi-image-edit-group-photo-from-6-images.json) | Multi-Image Edit — Group Photo from 6 Images | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |

#### Instruction-based single-image editing (img2img) (28)

Folder: [`02-Image-Editing/Single-Image-Edit/`](02-Image-Editing/Single-Image-Edit)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [boogu-edit-one-image-edit](02-Image-Editing/Single-Image-Edit/boogu-edit-one-image-edit.json) | One Image Edit | `qwen3vl_8b_fp8_scaled.safetensors`, `ae.safetensors`, `boogu_image_edit_turbo_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-4b-fp8-distilled-one-image-edit](02-Image-Editing/Single-Image-Edit/flux-2-klein-4b-fp8-distilled-one-image-edit.json) | One Image Edit | `flux-2-klein-4b-fp8.safetensors`, `qwen_3_4b.safetensors`, `flux2-vae.safetensors` | rgthree-comfy |
| [flux-2-klein-9b-fp8-distilled-one-image-edit](02-Image-Editing/Single-Image-Edit/flux-2-klein-9b-fp8-distilled-one-image-edit.json) | One Image Edit | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | rgthree-comfy |
| [flux-2-klein-9b-int8-one-image-edit](02-Image-Editing/Single-Image-Edit/flux-2-klein-9b-int8-one-image-edit.json) | One Image Edit | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-kv-fp8-one-image-edit-custom-ratio](02-Image-Editing/Single-Image-Edit/flux-2-klein-9b-kv-fp8-one-image-edit-custom-ratio.json) | One Image Edit (Custom Ratio) | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | rgthree-comfy |
| [flux-2-klein-9b-kv-fp8-one-image-edit-same-ratio](02-Image-Editing/Single-Image-Edit/flux-2-klein-9b-kv-fp8-one-image-edit-same-ratio.json) | One Image Edit (Same Ratio) | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | rgthree-comfy |
| [flux-2-klein-9b-one-image-edit-v1](02-Image-Editing/Single-Image-Edit/flux-2-klein-9b-one-image-edit-v1.json) | One Image Edit V1 | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-image-edit-v2-notify-and-switch](02-Image-Editing/Single-Image-Edit/flux-2-klein-9b-one-image-edit-v2-notify-and-switch.json) | One Image Edit V2 + Notify and Switch | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-image-edit-v3-keep-filename-save-to-dated-folder](02-Image-Editing/Single-Image-Edit/flux-2-klein-9b-one-image-edit-v3-keep-filename-save-to-dated-folder.json) | One Image Edit V3 + Keep Filename + Save to Dated Folder | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-image-many-edits](02-Image-Editing/Single-Image-Edit/flux-2-klein-9b-one-image-many-edits.json) | One Image, Many Edits | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-image-prompts-from-list](02-Image-Editing/Single-Image-Edit/flux-2-klein-9b-one-image-prompts-from-list.json) | One Image, Prompts from List | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-edit-text-in-a-picture](02-Image-Editing/Single-Image-Edit/flux-3-klein-edit-text-in-a-picture.json) | Edit Text in a Picture | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-one-image-edit](02-Image-Editing/Single-Image-Edit/flux-3-klein-one-image-edit.json) | One Image Edit | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-relight-and-seasons](02-Image-Editing/Single-Image-Edit/flux-3-klein-relight-and-seasons.json) | Relight and Seasons | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-restore-and-colorize](02-Image-Editing/Single-Image-Edit/flux-3-klein-restore-and-colorize.json) | Restore and Colorize | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-restyle](02-Image-Editing/Single-Image-Edit/flux-3-klein-restyle.json) | Restyle | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [krea-2-edit-lora-character-and-background](02-Image-Editing/Single-Image-Edit/krea-2-edit-lora-character-and-background.json) | Edit LoRA — Character and Background | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [krea-2-edit-lora-custom-ratio](02-Image-Editing/Single-Image-Edit/krea-2-edit-lora-custom-ratio.json) | Edit LoRA — Custom Ratio | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [krea-2-edit-lora](02-Image-Editing/Single-Image-Edit/krea-2-edit-lora.json) | Edit LoRA | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [ming-image-0.1-one-image-edit](02-Image-Editing/Single-Image-Edit/ming-image-0.1-one-image-edit.json) | One Image Edit | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-social-media-pack-from-one-image](02-Image-Editing/Single-Image-Edit/ming-image-0.1-social-media-pack-from-one-image.json) | Social Media Pack from One Image | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [minimax-h3-one-image-edit-single-frame](02-Image-Editing/Single-Image-Edit/minimax-h3-one-image-edit-single-frame.json) | One Image Edit (Single Frame) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `minimax_h3_video_vae_fp16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-one-image-edit-consistency-lora](02-Image-Editing/Single-Image-Edit/qwen-image-2.1-one-image-edit-consistency-lora.json) | One Image Edit + Consistency LoRA | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma |
| [qwen-image-2.1-one-image-edit-low-vram](02-Image-Editing/Single-Image-Edit/qwen-image-2.1-one-image-edit-low-vram.json) | One Image Edit — Low VRAM | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-one-image-edit-prompt-enhancer](02-Image-Editing/Single-Image-Edit/qwen-image-2.1-one-image-edit-prompt-enhancer.json) | One Image Edit + Prompt Enhancer | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-one-image-edit-turbo](02-Image-Editing/Single-Image-Edit/qwen-image-2.1-one-image-edit-turbo.json) | One Image Edit — Turbo | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma |
| [qwen-image-2.1-one-image-edit](02-Image-Editing/Single-Image-Edit/qwen-image-2.1-one-image-edit.json) | One Image Edit | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [sd15-juggernaut-reborn-img2img](02-Image-Editing/Single-Image-Edit/sd15-juggernaut-reborn-img2img.json) | Image to Image | `juggernaut_reborn.safetensors` | Core only |

#### Sketch-to-image and 3D-render-to-image (9)

Folder: [`02-Image-Editing/Sketch-and-3D-to-Image/`](02-Image-Editing/Sketch-and-3D-to-Image)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [flux-2-klein-9b-3d-model-to-image-ep33](02-Image-Editing/Sketch-and-3D-to-Image/flux-2-klein-9b-3d-model-to-image-ep33.json) | 3D Model to Image (Ep33) | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-3d-model-to-image-keep-the-angle-ep33](02-Image-Editing/Sketch-and-3D-to-Image/flux-2-klein-9b-3d-model-to-image-keep-the-angle-ep33.json) | 3D Model to Image — Keep the Angle (Ep33) | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-3d-model-to-image-keep-the-angle-ep34](02-Image-Editing/Sketch-and-3D-to-Image/flux-2-klein-9b-3d-model-to-image-keep-the-angle-ep34.json) | 3D Model to Image — Keep the Angle (Ep34) | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-3d-model-to-image](02-Image-Editing/Sketch-and-3D-to-Image/flux-2-klein-9b-3d-model-to-image.json) | 3D Model to Image | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-3d-scene-builder-to-image](02-Image-Editing/Sketch-and-3D-to-Image/flux-2-klein-9b-3d-scene-builder-to-image.json) | 3D Scene Builder to Image | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-restyle-a-design-to-3d](02-Image-Editing/Sketch-and-3D-to-Image/ming-image-0.1-restyle-a-design-to-3d.json) | Restyle a Design to 3D | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-sketch-to-photo](02-Image-Editing/Sketch-and-3D-to-Image/ming-image-0.1-sketch-to-photo.json) | Sketch to Photo | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-sketch-to-image-consistency-lora](02-Image-Editing/Sketch-and-3D-to-Image/qwen-image-2.1-sketch-to-image-consistency-lora.json) | Sketch to Image + Consistency LoRA | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma |
| [qwen-image-2.1-sketch-to-image](02-Image-Editing/Sketch-and-3D-to-Image/qwen-image-2.1-sketch-to-image.json) | Sketch to Image | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |

### 03 · Image Upscaling and Enhancement

Image upscaling (SeedVR2, tiled diffusion, 4x ESRGAN-style models, paid API upscalers) and filters / color grading. Folder: [`03-Image-Enhancement/`](03-Image-Enhancement) — 10 workflows.

#### Filters and color grading (2)

Folder: [`03-Image-Enhancement/Filters-and-Color-Grading/`](03-Image-Enhancement/Filters-and-Color-Grading)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [layerstyle-image-filters-and-color-adjustments](03-Image-Enhancement/Filters-and-Color-Grading/layerstyle-image-filters-and-color-adjustments.json) | Image Filters and Color Adjustments | — | ComfyUI_LayerStyle, rgthree-comfy |
| [utility-image-filters-example](03-Image-Enhancement/Filters-and-Color-Grading/utility-image-filters-example.json) | Image Filters Example | — | ComfyUI-RMBG, ComfyUI_LayerStyle, rgthree-comfy |

#### Image upscaling (8)

Folder: [`03-Image-Enhancement/Upscaling/`](03-Image-Enhancement/Upscaling)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [1-universal-upscale-simple-no-model](03-Image-Enhancement/Upscaling/1-universal-upscale-simple-no-model.json) | Upscale Simple (No Model) | — | rgthree-comfy |
| [2-universal-upscale-with-4x-model-nmkd-siax](03-Image-Enhancement/Upscaling/2-universal-upscale-with-4x-model-nmkd-siax.json) | Upscale with 4x Model (NMKD-Siax) | `4x_NMKD-Siax_200k.pth` | rgthree-comfy |
| [3-z-image-turbo-tiled-diffusion-upscaler](03-Image-Enhancement/Upscaling/3-z-image-turbo-tiled-diffusion-upscaler.json) | Tiled Diffusion Upscaler | `4x_NMKD-Siax_200k.pth`, `ae.safetensors`, `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors` +1 more | rgthree-comfy, comfyui-yaser-nodes |
| [4-nunchaku-fluxmania-tiled-diffusion-upscaler](03-Image-Enhancement/Upscaling/4-nunchaku-fluxmania-tiled-diffusion-upscaler.json) | Fluxmania — Tiled Diffusion Upscaler | `t5-v1_1-xxl-encoder-Q8_0.gguf`, `clip_l.safetensors`, `ae.safetensors` +2 more | ComfyUI-GGUF, ComfyUI-nunchaku, rgthree-comfy, comfyui-yaser-nodes |
| [5-seedvr2-upscale](03-Image-Enhancement/Upscaling/5-seedvr2-upscale.json) | Upscale | `ema_vae_fp16.safetensors`, `seedvr2_ema_7b_fp8_e4m3fn_mixed_block35_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler, rgthree-comfy |
| [6-paid-api-51-credits-nano-banana-pro-upscale](03-Image-Enhancement/Upscaling/6-paid-api-51-credits-nano-banana-pro-upscale.json) | Nano Banana Pro — Upscale | — | rgthree-comfy |
| [7-paid-api-53-credits-recraft-creative-upscale](03-Image-Enhancement/Upscaling/7-paid-api-53-credits-recraft-creative-upscale.json) | Recraft — Creative Upscale | — | rgthree-comfy |
| [8-paid-api-8.5-credits-seedream-4.5-upscale](03-Image-Enhancement/Upscaling/8-paid-api-8.5-credits-seedream-4.5-upscale.json) | SeeDream 4.5 — Upscale | — | rgthree-comfy |

### 04 · AI Video

Text-to-video (txt2video), image-to-video (img2video), video-to-video, talking video and lip-sync, character animation and character swap, video upscaling and audio-reactive video — Wan 2.1 / 2.2, LTX-2, MiniMax H3, SeedVR2, InfiniteTalk, SCAIL. Folder: [`04-Video/`](04-Video) — 90 workflows.

#### Audio-reactive visuals (1)

Folder: [`04-Video/Audio-Reactive/`](04-Video/Audio-Reactive)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [utility-images-react-to-music-audio-reactive](04-Video/Audio-Reactive/utility-images-react-to-music-audio-reactive.json) | Images React to Music (Audio Reactive) | — | ComfyUI-Pixaroma |

#### Character animation, character replacement, character swap and face swap (video2video) (37)

Folder: [`04-Video/Character-Animation-Video-to-Video/`](04-Video/Character-Animation-Video-to-Video)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [minimax-h3-character-swap-motion-guide-check-run08-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-motion-guide-check-run08-api.json) | SAM3 motion-guide preview for the H3 character swap (API format) | `sam3.1_multiplex_fp16.safetensors` | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-motion-guide-check-run08-v2-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-motion-guide-check-run08-v2-api.json) | SAM3 motion-guide preview for the H3 character swap (v2) (API format) | `sam3.1_multiplex_fp16.safetensors` | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-mdmz-v1](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-mdmz-v1.json) | Character swap / motion transfer: SAM3 masks the person, MiniMax H3 regenerates the shot with your character (Gemini prompt helper) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +3 more | ComfyUI-VideoHelperSuite, rgthree-comfy, ComfyUI-Unload-Model |
| [minimax-h3-character-swap-sam3-run01-480p-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run01-480p-api.json) | MiniMax H3 character swap run 01 (480p): SAM3 mask + reference-to-video (API format) | `sam3.1_multiplex_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +2 more | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run02-480p-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run02-480p-api.json) | MiniMax H3 character swap run 02 (480p): SAM3 mask + reference-to-video (API format) | `sam3.1_multiplex_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +2 more | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run03-480p-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run03-480p-api.json) | MiniMax H3 character swap run 03 (480p): SAM3 mask + reference-to-video (API format) | `sam3.1_multiplex_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +2 more | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run04-480p-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run04-480p-api.json) | MiniMax H3 character swap run 04 (480p): SAM3 mask + reference-to-video (API format) | `sam3.1_multiplex_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +2 more | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run05-480p-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run05-480p-api.json) | MiniMax H3 character swap run 05 (480p): SAM3 mask + reference-to-video (API format) | `sam3.1_multiplex_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +2 more | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run05-720p-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run05-720p-api.json) | MiniMax H3 character swap run 05 (720p): SAM3 mask + reference-to-video (API format) | `sam3.1_multiplex_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +2 more | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run06-720p-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run06-720p-api.json) | MiniMax H3 character swap run 06 (720p): SAM3 mask + reference-to-video (API format) | `sam3.1_multiplex_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +2 more | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run07a-dance-720p-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run07a-dance-720p-api.json) | MiniMax H3 character swap run 07A (dance 720p): SAM3 mask + reference-to-video (API format) | `sam3.1_multiplex_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +2 more | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run07b-talk-720p-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run07b-talk-720p-api.json) | MiniMax H3 character swap run 07B (talk 720p): SAM3 mask + reference-to-video (API format) | `sam3.1_multiplex_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +2 more | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run08-duo-720p-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run08-duo-720p-api.json) | MiniMax H3 character swap run 08 (duo 720p): SAM3 mask + reference-to-video (API format) | `sam3.1_multiplex_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +2 more | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run09-toons-720p-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run09-toons-720p-api.json) | MiniMax H3 character swap run 09 (toons 720p): SAM3 mask + reference-to-video (API format) | `sam3.1_multiplex_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +2 more | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run10-faceswap-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run10-faceswap-api.json) | MiniMax H3 character swap run 10 (faceswap): SAM3 mask + reference-to-video (API format) | `sam3.1_multiplex_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +2 more | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run11a-480p-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run11a-480p-api.json) | MiniMax H3 character swap run 11A (480p): SAM3 mask + reference-to-video (API format) | `sam3.1_multiplex_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +2 more | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run11b-480p-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run11b-480p-api.json) | MiniMax H3 character swap run 11B (480p): SAM3 mask + reference-to-video (API format) | `sam3.1_multiplex_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +2 more | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run11c-480p-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run11c-480p-api.json) | MiniMax H3 character swap run 11C (480p): SAM3 mask + reference-to-video (API format) | `sam3.1_multiplex_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +2 more | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run11c-720p-api](04-Video/Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run11c-720p-api.json) | MiniMax H3 character swap run 11C (720p): SAM3 mask + reference-to-video (API format) | `sam3.1_multiplex_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +2 more | ComfyUI-VideoHelperSuite |
| [reactor-video-face-swap-api](04-Video/Character-Animation-Video-to-Video/reactor-video-face-swap-api.json) | Face swap on every frame of a video with ReActor + CodeFormer restore (API format) | `inswapper_128.onnx`, `codeformer-v0.1.0.pth` | ComfyUI-ReActor, ComfyUI-VideoHelperSuite |
| [wan-2.1-scail-2-character-animation-from-driving-video-compact](04-Video/Character-Animation-Video-to-Video/wan-2.1-scail-2-character-animation-from-driving-video-compact.json) | Character Animation from Driving Video — Compact | `clip_vision_h.safetensors`, `umt5_xxl_fp8_e4m3fn_scaled.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank128_bf16.safetensors` +2 more | ComfyUI-KJNodes, ComfyUI-Pixaroma |
| [wan-2.1-scail-2-character-animation-from-driving-video-long](04-Video/Character-Animation-Video-to-Video/wan-2.1-scail-2-character-animation-from-driving-video-long.json) | Character Animation from Driving Video — Long | `clip_vision_h.safetensors`, `Wan2_1_VAE_bf16.safetensors`, `umt5_xxl_fp8_e4m3fn_scaled.safetensors` +2 more | ComfyUI-KJNodes, ComfyUI-Pixaroma |
| [wan-2.1-scail-2-character-replacement](04-Video/Character-Animation-Video-to-Video/wan-2.1-scail-2-character-replacement.json) | Character Replacement | `wan2.1_14B_SCAIL_2_fp16.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more | Core only |
| [wan-2.1-scail-2-gap-hi-woman](04-Video/Character-Animation-Video-to-Video/wan-2.1-scail-2-gap-hi-woman.json) | GAP — Hi Woman | `sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more | wan-scail2-gap |
| [wan-2.1-scail-2-gap-multi-character-long](04-Video/Character-Animation-Video-to-Video/wan-2.1-scail-2-gap-multi-character-long.json) | GAP Multi Character — Long | `sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more | wan-scail2-gap |
| [wan-2.1-scail-2-gap-video-2](04-Video/Character-Animation-Video-to-Video/wan-2.1-scail-2-gap-video-2.json) | GAP — Video 2 | `sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more | wan-scail2-gap |
| [wan-2.1-scail-2-gap-video-3-man](04-Video/Character-Animation-Video-to-Video/wan-2.1-scail-2-gap-video-3-man.json) | GAP — Video 3 Man | `sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more | wan-scail2-gap |
| [wan-2.1-scail-2-gap-video-4-man-closeup](04-Video/Character-Animation-Video-to-Video/wan-2.1-scail-2-gap-video-4-man-closeup.json) | GAP — Video 4 Man Closeup | `sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more | wan-scail2-gap |
| [wan-2.1-scail-2-gap-video-5-man-head](04-Video/Character-Animation-Video-to-Video/wan-2.1-scail-2-gap-video-5-man-head.json) | GAP — Video 5 Man Head | `sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more | wan-scail2-gap |
| [wan-2.1-scail-2-gap-video-6-man-head-fix](04-Video/Character-Animation-Video-to-Video/wan-2.1-scail-2-gap-video-6-man-head-fix.json) | GAP — Video 6 Man Head Fix | `sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more | wan-scail2-gap |
| [wan-2.1-scail-img2video-multi-character-9-16-ratio-only](04-Video/Character-Animation-Video-to-Video/wan-2.1-scail-img2video-multi-character-9-16-ratio-only.json) | Image to Video — Multi Character (9-16 Ratio Only) | `Wan21-14B-SCAIL-preview_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan_2.1_vae.safetensors` +7 more | comfyui_controlnet_aux, ComfyUI-KJNodes, ComfyUI-SCAIL-Pose, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use |
| [wan-2.1-scail-img2video-single-character](04-Video/Character-Animation-Video-to-Video/wan-2.1-scail-img2video-single-character.json) | Image to Video — Single Character | `Wan21-14B-SCAIL-preview_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan_2.1_vae.safetensors` +5 more | ComfyUI-KJNodes, ComfyUI-SCAIL-Pose, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use |
| [wan-2.2-animate-replace-character-and-background-16fps](04-Video/Character-Animation-Video-to-Video/wan-2.2-animate-replace-character-and-background-16fps.json) | Replace Character and Background — 16FPS | `sam3.pt`, `vitpose_h_wholebody_model.onnx`, `yolov10m.onnx` +9 more | ComfyUI_LayerStyle, ComfyUI-KJNodes, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Sam3, ComfyUI-Easy-Use |
| [wan-2.2-animate-replace-character-and-background-24fps-hd](04-Video/Character-Animation-Video-to-Video/wan-2.2-animate-replace-character-and-background-24fps-hd.json) | Replace Character and Background — 24FPS HD | `sam3.pt`, `vitpose_h_wholebody_model.onnx`, `yolov10m.onnx` +9 more | ComfyUI_LayerStyle, ComfyUI-KJNodes, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Sam3, ComfyUI-Easy-Use |
| [wan-2.2-animate-replace-character-and-background-24fps](04-Video/Character-Animation-Video-to-Video/wan-2.2-animate-replace-character-and-background-24fps.json) | Replace Character and Background — 24FPS | `sam3.pt`, `vitpose_h_wholebody_model.onnx`, `yolov10m.onnx` +9 more | ComfyUI_LayerStyle, ComfyUI-KJNodes, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Sam3, ComfyUI-Easy-Use |
| [wan-2.2-animate-replace-only-character-16fps](04-Video/Character-Animation-Video-to-Video/wan-2.2-animate-replace-only-character-16fps.json) | Replace Only Character — 16FPS | `sam3.pt`, `vitpose_h_wholebody_model.onnx`, `yolov10m.onnx` +9 more | ComfyUI_LayerStyle, ComfyUI-KJNodes, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Sam3, ComfyUI-Easy-Use |
| [wan-2.2-animate-replace-only-character-24fps](04-Video/Character-Animation-Video-to-Video/wan-2.2-animate-replace-only-character-24fps.json) | Replace Only Character — 24FPS | `sam3.pt`, `vitpose_h_wholebody_model.onnx`, `yolov10m.onnx` +9 more | ComfyUI_LayerStyle, ComfyUI-KJNodes, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Sam3, ComfyUI-Easy-Use |

#### Image-to-video (img2video), first/last frame (11)

Folder: [`04-Video/Image-to-Video/`](04-Video/Image-to-Video)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [ltx-2-img2video-with-audio](04-Video/Image-to-Video/ltx-2-img2video-with-audio.json) | Image to Video with Audio | `ltx-2-19b-distilled-fp8.safetensors`, `ltx-2-19b-distilled.safetensors`, `ltx-2-spatial-upscaler-x2-1.0.safetensors` +1 more | ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use |
| [ltx-2-img2video-with-custom-audio](04-Video/Image-to-Video/ltx-2-img2video-with-custom-audio.json) | Image to Video with Custom Audio | `ltx-2-19b-dev-fp8.safetensors`, `gemma_3_12B_it_fp8_e4m3fn.safetensors`, `gemma_3_12B_it.safetensors` +6 more | ComfyUI_LayerStyle, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use |
| [minimax-fasth3-img2video-first-frame-8-step](04-Video/Image-to-Video/minimax-fasth3-img2video-first-frame-8-step.json) | Image to Video — First Frame (8-Step) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-fasth3-img2video-first-last-frame-8-step](04-Video/Image-to-Video/minimax-fasth3-img2video-first-last-frame-8-step.json) | Image to Video — First + Last Frame (8-Step) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-img2video-first-frame-speed-lora](04-Video/Image-to-Video/minimax-h3-img2video-first-frame-speed-lora.json) | Image to Video — First Frame + Speed LoRA | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +2 more | ComfyUI-Pixaroma |
| [minimax-h3-img2video-first-frame](04-Video/Image-to-Video/minimax-h3-img2video-first-frame.json) | Image to Video — First Frame | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-img2video-first-last-frame-speed-lora](04-Video/Image-to-Video/minimax-h3-img2video-first-last-frame-speed-lora.json) | Image to Video — First + Last Frame + Speed LoRA | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +2 more | ComfyUI-Pixaroma |
| [minimax-h3-img2video-first-last-frame](04-Video/Image-to-Video/minimax-h3-img2video-first-last-frame.json) | Image to Video — First + Last Frame | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-img2video-last-frame](04-Video/Image-to-Video/minimax-h3-img2video-last-frame.json) | Image to Video — Last Frame | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more | ComfyUI-Pixaroma |
| [wan-2.2-img2video-gguf-lightx2v-4-step-lora](04-Video/Image-to-Video/wan-2.2-img2video-gguf-lightx2v-4-step-lora.json) | Image to Video — GGUF Lightx2v 4-Step + LoRA | `umt5_xxl_fp8_e4m3fn_scaled.safetensors`, `wan_2.1_vae.safetensors`, `wan2.2_i2v_A14b_high_noise_lightx2v_4step-Q6_K.gguf` +2 more | ComfyUI-GGUF, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use |
| [wan-2.2-img2video-gguf-lightx2v-4-step](04-Video/Image-to-Video/wan-2.2-img2video-gguf-lightx2v-4-step.json) | Image to Video — GGUF Lightx2v 4-Step | `umt5_xxl_fp8_e4m3fn_scaled.safetensors`, `wan_2.1_vae.safetensors`, `wan2.2_i2v_A14b_high_noise_lightx2v_4step-Q6_K.gguf` +1 more | ComfyUI-GGUF, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use |

#### Reference-to-video, talking video, lip-sync and video dubbing (26)

Folder: [`04-Video/Reference-and-Audio-Sync/`](04-Video/Reference-and-Audio-Sync)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [dubsync-hindi-lip-sync-simple-api](04-Video/Reference-and-Audio-Sync/dubsync-hindi-lip-sync-simple-api.json) | One-node DubSync lip-sync (API format) | — | ComfyUI-DubSync (local) |
| [dubsync-hindi-lip-sync-simple](04-Video/Reference-and-Audio-Sync/dubsync-hindi-lip-sync-simple.json) | One-node DubSync lip-sync: video + dubbed audio in, lip-synced video out | — | ComfyUI-DubSync (local) |
| [dubsync-latentsync-lip-sync-api](04-Video/Reference-and-Audio-Sync/dubsync-latentsync-lip-sync-api.json) | DubSync + LatentSync lip-sync (API format) | — | ComfyUI-DubSync (local) |
| [dubsync-latentsync-lip-sync-single-shot](04-Video/Reference-and-Audio-Sync/dubsync-latentsync-lip-sync-single-shot.json) | DubSync + LatentSync lip-sync for a single shot (load video and audio, sync, save) | — | ComfyUI-DubSync (local) |
| [dubsync-tbdub-teacher-lip-sync-api](04-Video/Reference-and-Audio-Sync/dubsync-tbdub-teacher-lip-sync-api.json) | TBDub Teacher lip-sync (API format) | — | ComfyUI-DubSync (local) |
| [dubsync-tbdub-teacher-lip-sync-single-shot](04-Video/Reference-and-Audio-Sync/dubsync-tbdub-teacher-lip-sync-single-shot.json) | Best-quality 30-step TBDub Teacher lip-sync for one shot with one visible speaker | — | ComfyUI-DubSync (local) |
| [latentsync-hindi-lip-sync-dubbing](04-Video/Reference-and-Audio-Sync/latentsync-hindi-lip-sync-dubbing.json) | Lip-sync an existing video to a new dubbed voice track (e.g. Hindi) with LatentSync | — | ComfyUI-DubSync (local) |
| [ltx-2-lip-sync-to-your-audio-r01-sc007-0037](04-Video/Reference-and-Audio-Sync/ltx-2-lip-sync-to-your-audio-r01-sc007-0037.json) | R01_SC007_0037 | `LTX2_video_vae_bf16_KJ.safetensors`, `LTX2_audio_vae_bf16_KJ.safetensors`, `ltx-2-spatial-upscaler-x2-1.0.safetensors` +8 more | ComfyUI-GGUF, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, rgthree-comfy, ComfyUI-ChatterboxTTS |
| [ltx-2-video2video-voice-dubbing-compact](04-Video/Reference-and-Audio-Sync/ltx-2-video2video-voice-dubbing-compact.json) | Video to Video — Voice Dubbing — Compact | `LTX2_video_vae_bf16_KJ.safetensors`, `LTX2_audio_vae_bf16_KJ.safetensors`, `ltx-2-spatial-upscaler-x2-1.0.safetensors` +11 more | ComfyUI-GGUF, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, rgthree-comfy, ComfyUI-ChatterboxTTS |
| [ltx-2-video2video-voice-dubbing-runpod-1080p](04-Video/Reference-and-Audio-Sync/ltx-2-video2video-voice-dubbing-runpod-1080p.json) | Video to Video — Voice Dubbing — RunPod 1080p | `LTX2_video_vae_bf16_KJ.safetensors`, `LTX2_audio_vae_bf16_KJ.safetensors`, `ltx-2-spatial-upscaler-x2-1.0.safetensors` +11 more | ComfyUI-GGUF, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, rgthree-comfy, ComfyUI-ChatterboxTTS |
| [ltx-2-video2video-voice-dubbing](04-Video/Reference-and-Audio-Sync/ltx-2-video2video-voice-dubbing.json) | Video to Video — Voice Dubbing | `LTX2_video_vae_bf16_KJ.safetensors`, `LTX2_audio_vae_bf16_KJ.safetensors`, `ltx-2-spatial-upscaler-x2-1.0.safetensors` +11 more | ComfyUI-GGUF, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, rgthree-comfy, ComfyUI-ChatterboxTTS |
| [minimax-h3-reference-image-audio-sync-sing-speed-lora](04-Video/Reference-and-Audio-Sync/minimax-h3-reference-image-audio-sync-sing-speed-lora.json) | Reference Image + Audio Sync — Sing + Speed LoRA | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +2 more | ComfyUI-Pixaroma |
| [minimax-h3-reference-image-audio-sync-sing](04-Video/Reference-and-Audio-Sync/minimax-h3-reference-image-audio-sync-sing.json) | Reference Image + Audio Sync — Sing | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-reference-image-audio-sync-speak-speed-lora](04-Video/Reference-and-Audio-Sync/minimax-h3-reference-image-audio-sync-speak-speed-lora.json) | Reference Image + Audio Sync — Speak + Speed LoRA | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +2 more | ComfyUI-Pixaroma |
| [minimax-h3-reference-image-audio-sync-speak](04-Video/Reference-and-Audio-Sync/minimax-h3-reference-image-audio-sync-speak.json) | Reference Image + Audio Sync — Speak | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-reference-to-video-2-images](04-Video/Reference-and-Audio-Sync/minimax-h3-reference-to-video-2-images.json) | Reference to Video — 2 Images | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-reference-to-video-3-images](04-Video/Reference-and-Audio-Sync/minimax-h3-reference-to-video-3-images.json) | Reference to Video — 3 Images | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-reference-to-video-audio-character-swap](04-Video/Reference-and-Audio-Sync/minimax-h3-reference-to-video-audio-character-swap.json) | Reference to Video + Audio — Character Swap | `minimax_h3_audio_vae_fp32.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +5 more | Core only |
| [wan-2.1-infinitetalk-avatar-generator-video2video-basic-single](04-Video/Reference-and-Audio-Sync/wan-2.1-infinitetalk-avatar-generator-video2video-basic-single.json) | Talking avatar generator: drive a video with an audio file, TTS or typed text using Wan 2.1 InfiniteTalk | `clip_vision_h.safetensors`, `Wan2_1-I2V-14B-720P_fp8_e4m3fn.safetensors`, `Wan21_I2V_14B_lightx2v_cfg_step_distill_lora_rank64.safetensors` +3 more | ComfyUI_LayerStyle, audio-separation-nodes-comfyui, ComfyUI_ChatterBox_SRT_Voice, ComfyUI-KJNodes, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, comfy_mtb, ComfyUI-Custom-Scripts, rgthree-comfy |
| [wan-2.1-infinitetalk-talking-video-easy-extend-3-to-34-seconds](04-Video/Reference-and-Audio-Sync/wan-2.1-infinitetalk-talking-video-easy-extend-3-to-34-seconds.json) | Talking Video — Easy Extend 3 to 34 Seconds | `Wan2_1-I2V-14B-480p_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_infiniteTalk_single_fp16.safetensors` +4 more | ComfyUI-VideoHelperSuite, rgthree-comfy |
| [wan-2.1-infinitetalk-talking-video-from-audio-10-11-seconds](04-Video/Reference-and-Audio-Sync/wan-2.1-infinitetalk-talking-video-from-audio-10-11-seconds.json) | Talking Video from Audio — 10-11 Seconds | `Wan2_1-I2V-14B-480p_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_infiniteTalk_single_fp16.safetensors` +4 more | ComfyUI-VideoHelperSuite |
| [wan-2.1-infinitetalk-talking-video-from-audio-4-6-seconds](04-Video/Reference-and-Audio-Sync/wan-2.1-infinitetalk-talking-video-from-audio-4-6-seconds.json) | Talking Video from Audio — 4-6 Seconds | `Wan2_1-I2V-14B-480p_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_infiniteTalk_single_fp16.safetensors` +4 more | ComfyUI-VideoHelperSuite |
| [wan-2.1-infinitetalk-talking-video-from-audio-7-9-seconds](04-Video/Reference-and-Audio-Sync/wan-2.1-infinitetalk-talking-video-from-audio-7-9-seconds.json) | Talking Video from Audio — 7-9 Seconds | `Wan2_1-I2V-14B-480p_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_infiniteTalk_single_fp16.safetensors` +4 more | ComfyUI-VideoHelperSuite |
| [wan-2.1-infinitetalk-talking-video-manual-extend-3-to-34-seconds](04-Video/Reference-and-Audio-Sync/wan-2.1-infinitetalk-talking-video-manual-extend-3-to-34-seconds.json) | Talking Video — Manual Extend 3 to 34 Seconds | `Wan2_1-I2V-14B-480p_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_infiniteTalk_single_fp16.safetensors` +4 more | ComfyUI-VideoHelperSuite, rgthree-comfy |
| [wan-2.1-infinitetalk-video-dubbing-video2video-flat](04-Video/Reference-and-Audio-Sync/wan-2.1-infinitetalk-video-dubbing-video2video-flat.json) | Flattened single-path version of the InfiniteTalk video dubbing workflow | `clip_vision_h.safetensors`, `Wan2_1-I2V-14B-720P_fp8_e4m3fn.safetensors`, `Wan21_I2V_14B_lightx2v_cfg_step_distill_lora_rank64.safetensors` +3 more | ComfyUI_LayerStyle, ComfyUI-KJNodes, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, comfy_mtb, ComfyUI-Custom-Scripts |
| [wan-2.1-infinitetalk-video-dubbing-video2video](04-Video/Reference-and-Audio-Sync/wan-2.1-infinitetalk-video-dubbing-video2video.json) | Video dubbing (video2video): Wan 2.1 InfiniteTalk re-animates the speaker to a new audio track, TTS or text | `clip_vision_h.safetensors`, `Wan2_1-I2V-14B-720P_fp8_e4m3fn.safetensors`, `Wan21_I2V_14B_lightx2v_cfg_step_distill_lora_rank64.safetensors` +3 more | ComfyUI_LayerStyle, ComfyUI-KJNodes, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, comfy_mtb, ComfyUI-Custom-Scripts, rgthree-comfy |

#### Text-to-video (txt2video) (5)

Folder: [`04-Video/Text-to-Video/`](04-Video/Text-to-Video)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [minimax-fasth3-txt2video-8-step](04-Video/Text-to-Video/minimax-fasth3-txt2video-8-step.json) | Text to Video (8-Step) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `fastvideo_fasth3_8step_v2_pruned_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-txt2video-low-vram-8gb](04-Video/Text-to-Video/minimax-h3-txt2video-low-vram-8gb.json) | Text to Video — Low VRAM 8GB | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_fl2va_pruned_int8_convrot.safetensors` +1 more | ComfyUI_LayerStyle, ComfyUI-Pixaroma |
| [minimax-h3-txt2video-secret-sauce-4k-direct-output](04-Video/Text-to-Video/minimax-h3-txt2video-secret-sauce-4k-direct-output.json) | Text to Video — Secret Sauce 4K Direct Output | `qwen3vl_32b_minimax_h3_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `taeh3.safetensors` +9 more | ComfyUI-MemoryCleaner, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, rgthree-comfy, ComfyUI-MiniMaxH3-TimelineDirector, ComfyUI_Comfyroll_CustomNodes, ComfyUI-MiniMaxH3-Unified, H3SigmaRefiner (unknown source), RH_DLSS5Enhance (unknown source) |
| [minimax-h3-txt2video-speed-lora](04-Video/Text-to-Video/minimax-h3-txt2video-speed-lora.json) | Text to Video + Speed LoRA | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +2 more | ComfyUI-Pixaroma |
| [minimax-h3-txt2video](04-Video/Text-to-Video/minimax-h3-txt2video.json) | Text to Video | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_fl2va_pruned_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |

#### Video upscaling (10)

Folder: [`04-Video/Video-Upscaling/`](04-Video/Video-Upscaling)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [seedvr2-hd-video-upscale](04-Video/Video-Upscaling/seedvr2-hd-video-upscale.json) | HD Video Upscale | `ema_vae_fp16.safetensors`, `seedvr2_ema_3b_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-1080p-api](04-Video/Video-Upscaling/seedvr2-video-upscale-1080p-api.json) | SeedVR2 7B video upscale of one clip to 1080p (API format) | `seedvr2_ema_7b_fp8_e4m3fn_mixed_block35_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-api-run](04-Video/Video-Upscaling/seedvr2-video-upscale-api-run.json) | Video Upscale — API Run | `seedvr2_ema_7b_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-cartoon-dance-api](04-Video/Video-Upscaling/seedvr2-video-upscale-cartoon-dance-api.json) | SeedVR2 7B video upscale run (cartoon dance clip) (API format) | `seedvr2_ema_7b_fp8_e4m3fn_mixed_block35_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-VideoHelperSuite, ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-cartoon-talk-api](04-Video/Video-Upscaling/seedvr2-video-upscale-cartoon-talk-api.json) | SeedVR2 7B video upscale run (cartoon talk clip) (API format) | `seedvr2_ema_7b_fp8_e4m3fn_mixed_block35_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-VideoHelperSuite, ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-curly-dance-api](04-Video/Video-Upscaling/seedvr2-video-upscale-curly-dance-api.json) | SeedVR2 7B video upscale run (curly dance clip) (API format) | `seedvr2_ema_7b_fp8_e4m3fn_mixed_block35_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-VideoHelperSuite, ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-curly-talk-api](04-Video/Video-Upscaling/seedvr2-video-upscale-curly-talk-api.json) | SeedVR2 7B video upscale run (curly talk clip) (API format) | `seedvr2_ema_7b_fp8_e4m3fn_mixed_block35_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-VideoHelperSuite, ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-duo-api](04-Video/Video-Upscaling/seedvr2-video-upscale-duo-api.json) | SeedVR2 7B video upscale run (duo clip) (API format) | `seedvr2_ema_7b_fp8_e4m3fn_mixed_block35_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-VideoHelperSuite, ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-toons-api](04-Video/Video-Upscaling/seedvr2-video-upscale-toons-api.json) | SeedVR2 7B video upscale run (toons clip) (API format) | `seedvr2_ema_7b_fp8_e4m3fn_mixed_block35_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-VideoHelperSuite, ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale](04-Video/Video-Upscaling/seedvr2-video-upscale.json) | Video Upscale | `ema_vae_fp16.safetensors`, `seedvr2_ema_3b_fp16.safetensors` | ComfyUI-VideoHelperSuite, ComfyUI-SeedVR2_VideoUpscaler |

### 05 · Audio

Text-to-speech, voice cloning and voice design (Qwen3-TTS, Fish S2, ChatterBox) and music generation (Stable Audio 3, ACE-Step, MiniMax Music 3). Folder: [`05-Audio/`](05-Audio) — 17 workflows.

#### Music generation (6)

Folder: [`05-Audio/Music-Generation/`](05-Audio/Music-Generation)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [ace-step-v1.5-xl-turbo-text-to-music](05-Audio/Music-Generation/ace-step-v1.5-xl-turbo-text-to-music.json) | Text to Music | `qwen_0.6b_ace15.safetensors`, `qwen_4b_ace15.safetensors`, `ace_1.5_vae.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-music-3-text-to-music](05-Audio/Music-Generation/minimax-music-3-text-to-music.json) | Text to Music | `minimax_music3_dit_int8_convrot.safetensors`, `minimax_music3_text_encoder_pruned_int8_convrot.safetensors`, `minimax_music3_dav.safetensors` | ComfyUI-Pixaroma |
| [stable-audio-3-image-to-music-gemma-4](05-Audio/Music-Generation/stable-audio-3-image-to-music-gemma-4.json) | Image to Music + Gemma 4 | `stable_audio_3_medium.safetensors`, `t5gemma_b_b_ul2.safetensors`, `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma |
| [stable-audio-3-text-to-music-gemma-4-prompt-enhancer](05-Audio/Music-Generation/stable-audio-3-text-to-music-gemma-4-prompt-enhancer.json) | Text to Music + Gemma 4 Prompt Enhancer | `stable_audio_3_medium.safetensors`, `t5gemma_b_b_ul2.safetensors`, `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma |
| [stable-audio-3-text-to-music](05-Audio/Music-Generation/stable-audio-3-text-to-music.json) | Text to Music | `t5gemma_b_b_ul2.safetensors`, `stable_audio_3_medium.safetensors` | ComfyUI-Pixaroma |
| [stable-audio-3-text-to-sound-effects-gemma-4](05-Audio/Music-Generation/stable-audio-3-text-to-sound-effects-gemma-4.json) | Text to Sound Effects + Gemma 4 | `stable_audio_3_medium.safetensors`, `t5gemma_b_b_ul2.safetensors`, `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma |

#### Text-to-speech and voice cloning (11)

Folder: [`05-Audio/Speech-and-Voice-Cloning/`](05-Audio/Speech-and-Voice-Cloning)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [fish-s2-multi-speaker-dialogue-tts](05-Audio/Speech-and-Voice-Cloning/fish-s2-multi-speaker-dialogue-tts.json) | Multi-Speaker Dialogue TTS | — | ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use, comfyui-fish-audio-s2 |
| [fish-s2-text-to-speech](05-Audio/Speech-and-Voice-Cloning/fish-s2-text-to-speech.json) | Text to Speech | — | ComfyUI-Easy-Use, comfyui-fish-audio-s2 |
| [fish-s2-voice-clone-tts](05-Audio/Speech-and-Voice-Cloning/fish-s2-voice-clone-tts.json) | Voice Clone TTS | — | ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use, comfyui-fish-audio-s2 |
| [qwen3-tts-custom-voice](05-Audio/Speech-and-Voice-Cloning/qwen3-tts-custom-voice.json) | Custom Voice | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-clone-load-saved-voice](05-Audio/Speech-and-Voice-Cloning/qwen3-tts-voice-clone-load-saved-voice.json) | Voice Clone + Load Saved Voice | — | ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-clone-save-voice](05-Audio/Speech-and-Voice-Cloning/qwen3-tts-voice-clone-save-voice.json) | Voice Clone + Save Voice | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-clone-saved-multi-voice-dialogue](05-Audio/Speech-and-Voice-Cloning/qwen3-tts-voice-clone-saved-multi-voice-dialogue.json) | Voice Clone + Saved Multi Voice + Dialogue | — | ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-clone](05-Audio/Speech-and-Voice-Cloning/qwen3-tts-voice-clone.json) | Voice Clone | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-design-dialogue](05-Audio/Speech-and-Voice-Cloning/qwen3-tts-voice-design-dialogue.json) | Voice Design + Dialogue | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-design-save-voice](05-Audio/Speech-and-Voice-Cloning/qwen3-tts-voice-design-save-voice.json) | Voice Design + Save Voice | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-design](05-Audio/Speech-and-Voice-Cloning/qwen3-tts-voice-design.json) | Voice Design | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |

### 06 · 3D Generation

Image-to-3D and multi-view-to-3D mesh generation with Trellis 2, Pixal3D and SAM3D Body, including PBR textures. Folder: [`06-3D-Generation/`](06-3D-Generation) — 13 workflows.

#### Image-to-3D (8)

Folder: [`06-3D-Generation/Image-to-3D/`](06-3D-Generation/Image-to-3D)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [pixal3d-image-to-3d-model-hq-pbr-textures](06-3D-Generation/Image-to-3D/pixal3d-image-to-3d-model-hq-pbr-textures.json) | Image to 3D Model — HQ + PBR Textures | `trellis_2_texture_vae_bf16.safetensors`, `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors` +3 more | ComfyUI-Pixaroma |
| [pixal3d-image-to-3d-model-low-vram](06-3D-Generation/Image-to-3D/pixal3d-image-to-3d-model-low-vram.json) | Image to 3D Model — Low VRAM | `trellis_2_texture_vae_bf16.safetensors`, `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors` +3 more | ComfyUI-Pixaroma |
| [sam3d-body-3d-viewer](06-3D-Generation/Image-to-3D/sam3d-body-3d-viewer.json) | 3D Viewer | — | Core only |
| [sam3d-body-utility](06-3D-Generation/Image-to-3D/sam3d-body-utility.json) | Utility | `sam3.1_multiplex_fp16.safetensors`, `sam_3d_body_dinov3_bf16.safetensors`, `moge_2_vitl_normal_fp16.safetensors` +1 more | Core only |
| [sam3d-body-video-to-3d-body-multi-r01-sc008](06-3D-Generation/Image-to-3D/sam3d-body-video-to-3d-body-multi-r01-sc008.json) | Video to 3D Body — Multi (R01_SC008) | `sam3.1_multiplex_fp16.safetensors`, `sam_3d_body_dinov3_bf16.safetensors`, `moge_2_vitl_normal_fp16.safetensors` +1 more | Core only |
| [trellis-2-image-to-3d-model-high-vram](06-3D-Generation/Image-to-3D/trellis-2-image-to-3d-model-high-vram.json) | Image to 3D Model — High VRAM | `trellis_2_texture_vae_bf16.safetensors`, `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors` +2 more | ComfyUI-Pixaroma |
| [trellis-2-image-to-3d-model-hq-pbr-textures](06-3D-Generation/Image-to-3D/trellis-2-image-to-3d-model-hq-pbr-textures.json) | Image to 3D Model — HQ + PBR Textures | `birefnet.safetensors`, `dino_v3_L_naf_fp32.safetensors`, `trellis_2_int8_convrot.safetensors` +2 more | ComfyUI-Pixaroma |
| [trellis-2-image-to-3d-model-low-vram](06-3D-Generation/Image-to-3D/trellis-2-image-to-3d-model-low-vram.json) | Image to 3D Model — Low VRAM | `trellis_2_texture_vae_bf16.safetensors`, `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors` +2 more | ComfyUI-Pixaroma |

#### Multi-view-to-3D (5)

Folder: [`06-3D-Generation/Multi-View-to-3D/`](06-3D-Generation/Multi-View-to-3D)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [pixal3d-multi-view-1-shape-only-no-colours-hq](06-3D-Generation/Multi-View-to-3D/pixal3d-multi-view-1-shape-only-no-colours-hq.json) | 1 Shape Only (No Colours) — HQ | `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors`, `pixal3d_multiview_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [pixal3d-multi-view-1-shape-only-no-colours](06-3D-Generation/Multi-View-to-3D/pixal3d-multi-view-1-shape-only-no-colours.json) | 1 Shape Only (No Colours) | `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors`, `pixal3d_multiview_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [pixal3d-multi-view-2-model-colours](06-3D-Generation/Multi-View-to-3D/pixal3d-multi-view-2-model-colours.json) | 2 Model + Colours | `trellis_2_texture_vae_bf16.safetensors`, `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors` +2 more | ComfyUI-Pixaroma |
| [pixal3d-multi-view-3-model-pbr-textures-lq](06-3D-Generation/Multi-View-to-3D/pixal3d-multi-view-3-model-pbr-textures-lq.json) | 3 Model + PBR Textures — LQ | `trellis_2_texture_vae_bf16.safetensors`, `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors` +2 more | ComfyUI-Pixaroma |
| [pixal3d-multi-view-4-model-pbr-textures-hq](06-3D-Generation/Multi-View-to-3D/pixal3d-multi-view-4-model-pbr-textures-hq.json) | 4 Model + PBR Textures — HQ | `trellis_2_texture_vae_bf16.safetensors`, `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors` +2 more | ComfyUI-Pixaroma |

### 07 · Batch Processing and Automation

Process whole folders of images, loops, switches, logic and math nodes for automated ComfyUI pipelines. Folder: [`07-Batch-and-Automation/`](07-Batch-and-Automation) — 44 workflows.

#### Switches, logic and math (7)

Folder: [`07-Batch-and-Automation/Control-Logic-and-Math/`](07-Batch-and-Automation/Control-Logic-and-Math)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [birefnet-turn-steps-on-and-off](07-Batch-and-Automation/Control-Logic-and-Math/birefnet-turn-steps-on-and-off.json) | Turn Steps On and Off | `birefnet.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-control-panel-for-the-whole-workflow](07-Batch-and-Automation/Control-Logic-and-Math/flux-2-klein-9b-one-control-panel-for-the-whole-workflow.json) | One Control Panel for the Whole Workflow | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-workflow-two-jobs](07-Batch-and-Automation/Control-Logic-and-Math/flux-2-klein-9b-one-workflow-two-jobs.json) | One Workflow, Two Jobs | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-set-and-get-no-long-wires](07-Batch-and-Automation/Control-Logic-and-Math/flux-2-klein-9b-set-and-get-no-long-wires.json) | Set and Get — No Long Wires | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-style-presets-from-a-dropdown](07-Batch-and-Automation/Control-Logic-and-Math/flux-2-klein-9b-style-presets-from-a-dropdown.json) | Style Presets from a Dropdown | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [free-vram-utility-api](07-Batch-and-Automation/Control-Logic-and-Math/free-vram-utility-api.json) | One-node utility that frees VRAM between runs (API format) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-switch-node](07-Batch-and-Automation/Control-Logic-and-Math/pixaroma-nodes-switch-node.json) | Switch Node | — | ComfyUI-Pixaroma |

#### Batch-process a folder of images (30)

Folder: [`07-Batch-and-Automation/Folder-Batch-Processing/`](07-Batch-and-Automation/Folder-Batch-Processing)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [birefnet-remove-the-background-from-all-images-in-a-folder](07-Batch-and-Automation/Folder-Batch-Processing/birefnet-remove-the-background-from-all-images-in-a-folder.json) | Remove the Background from All Images in a Folder | `birefnet.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-before-and-after-grid-for-all-images-in-a-folder](07-Batch-and-Automation/Folder-Batch-Processing/flux-2-klein-9b-before-and-after-grid-for-all-images-in-a-folder.json) | Before and After Grid for All Images in a Folder | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-coloring-pages-from-all-images-in-a-folder](07-Batch-and-Automation/Folder-Batch-Processing/flux-2-klein-9b-coloring-pages-from-all-images-in-a-folder.json) | Coloring Pages from All Images in a Folder | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-do-a-big-image-folder-in-parts](07-Batch-and-Automation/Folder-Batch-Processing/flux-2-klein-9b-do-a-big-image-folder-in-parts.json) | Do a Big Image Folder in Parts | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-edit-all-images-in-a-folder-with-one-prompt](07-Batch-and-Automation/Folder-Batch-Processing/flux-2-klein-9b-edit-all-images-in-a-folder-with-one-prompt.json) | Edit All Images in a Folder with One Prompt | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-edit-each-image-with-its-own-prompt](07-Batch-and-Automation/Folder-Batch-Processing/flux-2-klein-9b-edit-each-image-with-its-own-prompt.json) | Edit Each Image with Its Own Prompt | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-edit-images-from-folder-simple](07-Batch-and-Automation/Folder-Batch-Processing/flux-2-klein-9b-edit-images-from-folder-simple.json) | Edit Images from Folder (Simple) | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-fix-the-caption-text-files-then-make-the-images-again](07-Batch-and-Automation/Folder-Batch-Processing/flux-2-klein-9b-fix-the-caption-text-files-then-make-the-images-again.json) | Fix the Caption Text Files, Then Make the Images Again | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-make-all-images-in-a-folder-wide-outpaint](07-Batch-and-Automation/Folder-Batch-Processing/flux-2-klein-9b-make-all-images-in-a-folder-wide-outpaint.json) | Make All Images in a Folder Wide (Outpaint) | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-image-per-text-file](07-Batch-and-Automation/Folder-Batch-Processing/flux-2-klein-9b-one-image-per-text-file.json) | One Image per Text File | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-product-photos-from-all-images-in-a-folder](07-Batch-and-Automation/Folder-Batch-Processing/flux-2-klein-9b-product-photos-from-all-images-in-a-folder.json) | Product Photos from All Images in a Folder | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-qwen3-vl-ai-writes-an-edit-for-every-image](07-Batch-and-Automation/Folder-Batch-Processing/flux-2-klein-9b-qwen3-vl-ai-writes-an-edit-for-every-image.json) | AI Writes an Edit for Every Image | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma |
| [flux-2-klein-9b-qwen3-vl-re-imagine-all-images-in-a-folder-in-another-style](07-Batch-and-Automation/Folder-Batch-Processing/flux-2-klein-9b-qwen3-vl-re-imagine-all-images-in-a-folder-in-another-style.json) | Re-imagine All Images in a Folder in Another Style | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma |
| [flux-2-klein-9b-re-create-old-images-from-their-prompts](07-Batch-and-Automation/Folder-Batch-Processing/flux-2-klein-9b-re-create-old-images-from-their-prompts.json) | Re-create Old Images from Their Prompts | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-restore-and-colorize-old-photos-in-a-folder](07-Batch-and-Automation/Folder-Batch-Processing/flux-2-klein-9b-restore-and-colorize-old-photos-in-a-folder.json) | Restore and Colorize Old Photos in a Folder | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [nmkd-siax-4x-upscale-all-images-in-a-folder](07-Batch-and-Automation/Folder-Batch-Processing/nmkd-siax-4x-upscale-all-images-in-a-folder.json) | Upscale All Images in a Folder | `4x_NMKD-Siax_200k.pth` | ComfyUI-Pixaroma |
| [qwen3-vl-caption-all-images-in-a-folder-for-lora-training](07-Batch-and-Automation/Folder-Batch-Processing/qwen3-vl-caption-all-images-in-a-folder-for-lora-training.json) | Caption All Images in a Folder for LoRA Training | `qwen3vl_8b_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [qwen3-vl-keep-only-the-images-the-ai-says-yes-to](07-Batch-and-Automation/Folder-Batch-Processing/qwen3-vl-keep-only-the-images-the-ai-says-yes-to.json) | Keep Only the Images the AI Says Yes To | `qwen3vl_8b_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [qwen3-vl-rename-every-image-by-what-is-in-it](07-Batch-and-Automation/Folder-Batch-Processing/qwen3-vl-rename-every-image-by-what-is-in-it.json) | Rename Every Image by What Is in It | `qwen3vl_8b_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [qwen3-vl-sort-all-images-in-a-folder-into-subfolders-by-what-is-in-them](07-Batch-and-Automation/Folder-Batch-Processing/qwen3-vl-sort-all-images-in-a-folder-into-subfolders-by-what-is-in-them.json) | Sort All Images in a Folder into Subfolders by What Is in Them | `qwen3vl_8b_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [utility-add-your-logo-to-all-images-in-a-folder](07-Batch-and-Automation/Folder-Batch-Processing/utility-add-your-logo-to-all-images-in-a-folder.json) | Add Your Logo to All Images in a Folder | — | ComfyUI-Pixaroma |
| [utility-collect-the-prompts-from-all-images-in-a-folder](07-Batch-and-Automation/Folder-Batch-Processing/utility-collect-the-prompts-from-all-images-in-a-folder.json) | Collect the Prompts from All Images in a Folder | — | ComfyUI-Pixaroma |
| [utility-contact-sheet-of-all-images-in-a-folder](07-Batch-and-Automation/Folder-Batch-Processing/utility-contact-sheet-of-all-images-in-a-folder.json) | Contact Sheet of All Images in a Folder | — | ComfyUI-Pixaroma |
| [utility-load-images-from-folder-crop](07-Batch-and-Automation/Folder-Batch-Processing/utility-load-images-from-folder-crop.json) | Load Images from Folder + Crop | — | ComfyUI-Pixaroma |
| [utility-math-scale-all-images-in-a-folder-by-percent](07-Batch-and-Automation/Folder-Batch-Processing/utility-math-scale-all-images-in-a-folder-by-percent.json) | Math — Scale All Images in a Folder by Percent | — | ComfyUI-Pixaroma |
| [utility-rename-and-convert-all-images-in-a-folder](07-Batch-and-Automation/Folder-Batch-Processing/utility-rename-and-convert-all-images-in-a-folder.json) | Rename and Convert All Images in a Folder | — | ComfyUI-Pixaroma |
| [utility-resize-all-images-in-a-folder](07-Batch-and-Automation/Folder-Batch-Processing/utility-resize-all-images-in-a-folder.json) | Resize All Images in a Folder | — | ComfyUI-Pixaroma |
| [utility-slideshow-video-from-all-images-in-a-folder](07-Batch-and-Automation/Folder-Batch-Processing/utility-slideshow-video-from-all-images-in-a-folder.json) | Slideshow Video from All Images in a Folder | — | ComfyUI-Pixaroma |
| [utility-social-media-sizes-for-all-images-in-a-folder](07-Batch-and-Automation/Folder-Batch-Processing/utility-social-media-sizes-for-all-images-in-a-folder.json) | Social Media Sizes for All Images in a Folder | — | ComfyUI-Pixaroma |
| [utility-watermark-all-images-in-a-folder](07-Batch-and-Automation/Folder-Batch-Processing/utility-watermark-all-images-in-a-folder.json) | Watermark All Images in a Folder | — | ComfyUI-Pixaroma |

#### Loops (7)

Folder: [`07-Batch-and-Automation/Loops/`](07-Batch-and-Automation/Loops)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [1.-flux-2-klein-9b-loop-basics-four-versions-of-one-prompt](07-Batch-and-Automation/Loops/1.-flux-2-klein-9b-loop-basics-four-versions-of-one-prompt.json) | Loop Basics — Four Versions of One Prompt | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [2.-flux-2-klein-9b-loop-build-up-an-image-step-by-step](07-Batch-and-Automation/Loops/2.-flux-2-klein-9b-loop-build-up-an-image-step-by-step.json) | Loop — Build Up an Image Step by Step | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [3.-utility-loop-photo-strip-from-all-images-in-a-folder](07-Batch-and-Automation/Loops/3.-utility-loop-photo-strip-from-all-images-in-a-folder.json) | Loop — Photo Strip from All Images in a Folder | — | ComfyUI-Pixaroma |
| [4.-flux-2-klein-9b-loop-comic-strip-with-the-same-character](07-Batch-and-Automation/Loops/4.-flux-2-klein-9b-loop-comic-strip-with-the-same-character.json) | Loop — Comic Strip with the Same Character | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [pixaroma-nodes-loop-build-a-list](07-Batch-and-Automation/Loops/pixaroma-nodes-loop-build-a-list.json) | Loop — Build a List | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-loop-build-an-image-batch](07-Batch-and-Automation/Loops/pixaroma-nodes-loop-build-an-image-batch.json) | Loop — Build an Image Batch | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-loop-carry-two-values](07-Batch-and-Automation/Loops/pixaroma-nodes-loop-carry-two-values.json) | Loop — Carry Two Values | — | ComfyUI-Pixaroma |

### 08 · Testing and Comparison

XY plots for samplers, steps, styles and LoRAs, draft-then-finish preview gates and side-by-side image comparison. Folder: [`08-Testing-and-Comparison/`](08-Testing-and-Comparison) — 8 workflows.

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [flux-2-klein-9b-draft-first-then-finish-preview-gate](08-Testing-and-Comparison/flux-2-klein-9b-draft-first-then-finish-preview-gate.json) | Draft First, Then Finish (Preview Gate) | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-xy-plot-steps-and-samplers](08-Testing-and-Comparison/flux-2-klein-9b-xy-plot-steps-and-samplers.json) | XY Plot — Steps and Samplers | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-xy-plot-styles-and-subjects](08-Testing-and-Comparison/flux-2-klein-9b-xy-plot-styles-and-subjects.json) | XY Plot — Styles and Subjects | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [krea-2-int8-lora-xy-plot](08-Testing-and-Comparison/krea-2-int8-lora-xy-plot.json) | LoRA XY Plot | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2_turbo_int8_convrot.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma, rgthree-comfy |
| [pixaroma-nodes-group-compare-comfyui-vs-pixaroma](08-Testing-and-Comparison/pixaroma-nodes-group-compare-comfyui-vs-pixaroma.json) | Group Compare (ComfyUI vs Pixaroma) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-image-compare](08-Testing-and-Comparison/pixaroma-nodes-image-compare.json) | Image Compare | — | ComfyUI-Pixaroma |
| [utility-image-compare-side-by-side](08-Testing-and-Comparison/utility-image-compare-side-by-side.json) | Image Compare (Side by Side) | — | ComfyUI-RMBG, ComfyUI-iTools, rgthree-comfy |
| [z-image-turbo-xy-plot](08-Testing-and-Comparison/z-image-turbo-xy-plot.json) | XY Plot | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | ComfyUI-Pixaroma |

### 09 · AI Short Film Pipeline

An end-to-end AI short-film pipeline: Krea 2 storyboards and character sheets feed a MiniMax H3 reference-to-video chain that renders a multi-scene film. Folder: [`09-Movie/`](09-Movie) — 48 workflows.

#### Main workflows (13)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [short-film-director-pipeline-krea-minimax-h3-0.7-fixed-storyboard-prompts](09-Movie/short-film-director-pipeline-krea-minimax-h3-0.7-fixed-storyboard-prompts.json) | H3 0.7 Fixed — Storyboard Prompts | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +7 more | ComfyUI-MultiShot-Plan, ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, comfyui-krea2edit, rgthree-comfy, ComfyUI-Spectrum-MiniMax-H3 |
| [short-film-director-pipeline-krea-minimax-h3-0.7-fixed](09-Movie/short-film-director-pipeline-krea-minimax-h3-0.7-fixed.json) | H3 0.7 Fixed | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +7 more | ComfyUI-MultiShot-Plan, ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, comfyui-krea2edit, rgthree-comfy, ComfyUI-Spectrum-MiniMax-H3 |
| [short-film-director-pipeline-krea-minimax-h3-0.7-hires-16-scenes-heroine](09-Movie/short-film-director-pipeline-krea-minimax-h3-0.7-hires-16-scenes-heroine.json) | H3 0.7 HiRes 16 Scenes — Heroine | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +7 more | ComfyUI-MultiShot-Plan, ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, comfyui-krea2edit, rgthree-comfy, ComfyUI-Spectrum-MiniMax-H3 |
| [short-film-director-pipeline-krea-minimax-h3-0.7-hires-3-scenes](09-Movie/short-film-director-pipeline-krea-minimax-h3-0.7-hires-3-scenes.json) | H3 0.7 HiRes 3 Scenes | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +7 more | ComfyUI-MultiShot-Plan, ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, comfyui-krea2edit, rgthree-comfy, ComfyUI-Spectrum-MiniMax-H3 |
| [short-film-director-pipeline-krea-minimax-h3-0.7-hires-full-16-scenes](09-Movie/short-film-director-pipeline-krea-minimax-h3-0.7-hires-full-16-scenes.json) | H3 0.7 HiRes Full 16 Scenes | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +7 more | ComfyUI-MultiShot-Plan, ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, comfyui-krea2edit, rgthree-comfy, ComfyUI-Spectrum-MiniMax-H3 |
| [short-film-director-pipeline-krea-minimax-h3-0.7-overnight](09-Movie/short-film-director-pipeline-krea-minimax-h3-0.7-overnight.json) | H3 0.7 Overnight | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +7 more | ComfyUI-MultiShot-Plan, ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, comfyui-krea2edit, rgthree-comfy, ComfyUI-Spectrum-MiniMax-H3 |
| [short-film-director-pipeline-krea-minimax-h3-0.7-test-5-scenes-morning-departure](09-Movie/short-film-director-pipeline-krea-minimax-h3-0.7-test-5-scenes-morning-departure.json) | 5-scene test run of the Short Film Director pipeline (Krea 2 storyboard → MiniMax H3 video) | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +7 more | ComfyUI-MultiShot-Plan, ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, comfyui-krea2edit, rgthree-comfy, ComfyUI-Spectrum-MiniMax-H3 |
| [short-film-director-pipeline-krea-minimax-h3-0.7-test-scene-1](09-Movie/short-film-director-pipeline-krea-minimax-h3-0.7-test-scene-1.json) | H3 0.7 Test Scene 1 | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +7 more | ComfyUI-MultiShot-Plan, ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, comfyui-krea2edit, rgthree-comfy, ComfyUI-Spectrum-MiniMax-H3 |
| [short-film-director-pipeline-krea-minimax-h3-0.7-trial-5-scenes-mcp-run](09-Movie/short-film-director-pipeline-krea-minimax-h3-0.7-trial-5-scenes-mcp-run.json) | H3 0.7 Trial 5 Scenes — MCP Run | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +7 more | ComfyUI-MultiShot-Plan, ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, comfyui-krea2edit, ComfyUI-Spectrum-MiniMax-H3 |
| [short-film-director-pipeline-krea-minimax-h3-0.7-trial-5-scenes](09-Movie/short-film-director-pipeline-krea-minimax-h3-0.7-trial-5-scenes.json) | H3 0.7 Trial 5 Scenes | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +7 more | ComfyUI-MultiShot-Plan, ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, comfyui-krea2edit, rgthree-comfy, ComfyUI-Spectrum-MiniMax-H3 |
| [short-film-director-pipeline-krea-minimax-h3-no-review-v2](09-Movie/short-film-director-pipeline-krea-minimax-h3-no-review-v2.json) | No Review v2 | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +7 more | ComfyUI-MultiShot-Plan, ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, comfyui-krea2edit, rgthree-comfy, ComfyUI-Spectrum-MiniMax-H3 |
| [short-film-director-pipeline-krea-minimax-h3-no-review](09-Movie/short-film-director-pipeline-krea-minimax-h3-no-review.json) | No Review | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +7 more | ComfyUI-MultiShot-Plan, ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, comfyui-krea2edit, rgthree-comfy, ComfyUI-Spectrum-MiniMax-H3 |
| [short-film-director-pipeline-krea-minimax-h3](09-Movie/short-film-director-pipeline-krea-minimax-h3.json) | Short Film Director Pipeline (Krea + MiniMax H3) | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +7 more | ComfyUI-MultiShot-Plan, ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, comfyui-krea2edit, rgthree-comfy, ComfyUI-Spectrum-MiniMax-H3 |

#### Project files from real short films made with the pipeline (storyboard and film passes) (35)

Folder: [`09-Movie/Short-Film-Projects/`](09-Movie/Short-Film-Projects)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [backyard-goal-0-set-plate-krea-2-api](09-Movie/Short-Film-Projects/backyard-goal-0-set-plate-krea-2-api.json) | Background plate render with Krea 2 for the "Backyard Goal" short (API format) | `krea2_turbo_fp8_scaled.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `qwen_image_vae.safetensors` | Core only |
| [backyard-goal-1-storyboard-krea-2-fix](09-Movie/Short-Film-Projects/backyard-goal-1-storyboard-krea-2-fix.json) | Storyboard stills for the "Backyard Goal" short: Krea 2 identity edit + multi-shot scene board (fix) | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2_identity_edit_v1_2.safetensors` +1 more | ComfyUI-MultiShot-Plan, comfyui-krea2edit |
| [backyard-goal-1-storyboard-krea-2](09-Movie/Short-Film-Projects/backyard-goal-1-storyboard-krea-2.json) | Storyboard stills for the "Backyard Goal" short: Krea 2 identity edit + multi-shot scene board | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2_identity_edit_v1_2.safetensors` +1 more | ComfyUI-MultiShot-Plan, comfyui-krea2edit |
| [backyard-goal-2-film-minimax-h3-fix7](09-Movie/Short-Film-Projects/backyard-goal-2-film-minimax-h3-fix7.json) | Scene-by-scene film render for the "Backyard Goal" short with the MiniMax H3 reference-to-video chain (fix7) | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +3 more | ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, ComfyUI-Spectrum-MiniMax-H3 |
| [backyard-goal-2-film-minimax-h3-run](09-Movie/Short-Film-Projects/backyard-goal-2-film-minimax-h3-run.json) | Scene-by-scene film render for the "Backyard Goal" short with the MiniMax H3 reference-to-video chain (run) | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +3 more | ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, ComfyUI-Spectrum-MiniMax-H3 |
| [backyard-goal-2-film-minimax-h3](09-Movie/Short-Film-Projects/backyard-goal-2-film-minimax-h3.json) | Scene-by-scene film render for the "Backyard Goal" short with the MiniMax H3 reference-to-video chain | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +3 more | ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, ComfyUI-Spectrum-MiniMax-H3 |
| [backyard-goal-v2-0-set-plate-krea-2-api](09-Movie/Short-Film-Projects/backyard-goal-v2-0-set-plate-krea-2-api.json) | Background plate render with Krea 2 for the "Backyard Goal v2" short (API format) | `krea2_turbo_fp8_scaled.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `qwen_image_vae.safetensors` | Core only |
| [backyard-goal-v2-1-storyboard-krea-2](09-Movie/Short-Film-Projects/backyard-goal-v2-1-storyboard-krea-2.json) | Storyboard stills for the "Backyard Goal v2" short: Krea 2 identity edit + multi-shot scene board | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2_identity_edit_v1_2.safetensors` +1 more | ComfyUI-MultiShot-Plan, comfyui-krea2edit |
| [backyard-goal-v2-2-film-minimax-h3](09-Movie/Short-Film-Projects/backyard-goal-v2-2-film-minimax-h3.json) | Scene-by-scene film render for the "Backyard Goal v2" short with the MiniMax H3 reference-to-video chain | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +3 more | ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, ComfyUI-Spectrum-MiniMax-H3 |
| [golden-hour-0-set-plate-krea-2-api](09-Movie/Short-Film-Projects/golden-hour-0-set-plate-krea-2-api.json) | Background plate render with Krea 2 for the "Golden Hour" short (API format) | `krea2_turbo_fp8_scaled.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `qwen_image_vae.safetensors` | Core only |
| [golden-hour-1-storyboard-krea-2-fix](09-Movie/Short-Film-Projects/golden-hour-1-storyboard-krea-2-fix.json) | Storyboard stills for the "Golden Hour" short: Krea 2 identity edit + multi-shot scene board (fix) | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2_identity_edit_v1_2.safetensors` +1 more | ComfyUI-MultiShot-Plan, comfyui-krea2edit |
| [golden-hour-1-storyboard-krea-2-v3](09-Movie/Short-Film-Projects/golden-hour-1-storyboard-krea-2-v3.json) | Storyboard stills for the "Golden Hour" short: Krea 2 identity edit + multi-shot scene board (v3) | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2_identity_edit_v1_2.safetensors` +1 more | ComfyUI-MultiShot-Plan, comfyui-krea2edit |
| [golden-hour-1-storyboard-krea-2](09-Movie/Short-Film-Projects/golden-hour-1-storyboard-krea-2.json) | Storyboard stills for the "Golden Hour" short: Krea 2 identity edit + multi-shot scene board | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2_identity_edit_v1_2.safetensors` +1 more | ComfyUI-MultiShot-Plan, comfyui-krea2edit |
| [golden-hour-2-film-minimax-h3-final](09-Movie/Short-Film-Projects/golden-hour-2-film-minimax-h3-final.json) | Scene-by-scene film render for the "Golden Hour" short with the MiniMax H3 reference-to-video chain (final) | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +3 more | ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, ComfyUI-Spectrum-MiniMax-H3 |
| [golden-hour-2-film-minimax-h3-v3](09-Movie/Short-Film-Projects/golden-hour-2-film-minimax-h3-v3.json) | Scene-by-scene film render for the "Golden Hour" short with the MiniMax H3 reference-to-video chain (v3) | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +3 more | ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, ComfyUI-Spectrum-MiniMax-H3 |
| [golden-hour-2-film-minimax-h3-v4](09-Movie/Short-Film-Projects/golden-hour-2-film-minimax-h3-v4.json) | Scene-by-scene film render for the "Golden Hour" short with the MiniMax H3 reference-to-video chain (v4) | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +3 more | ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, ComfyUI-Spectrum-MiniMax-H3 |
| [golden-hour-2-film-minimax-h3](09-Movie/Short-Film-Projects/golden-hour-2-film-minimax-h3.json) | Scene-by-scene film render for the "Golden Hour" short with the MiniMax H3 reference-to-video chain | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +3 more | ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, ComfyUI-Spectrum-MiniMax-H3 |
| [heroine-short-film-krea-minimax-h3-1280](09-Movie/Short-Film-Projects/heroine-short-film-krea-minimax-h3-1280.json) | Full 16-scene "Morning Departure – Heroine" short film at 1280 px: Krea 2 storyboard + MiniMax H3 video | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +7 more | ComfyUI-MultiShot-Plan, ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, comfyui-krea2edit, ComfyUI-Spectrum-MiniMax-H3 |
| [heroine-storyboard-krea-2-api](09-Movie/Short-Film-Projects/heroine-storyboard-krea-2-api.json) | Krea 2 multi-shot storyboard run for the Heroine short (API format) | `krea2_turbo_fp8_scaled.safetensors`, `krea2_identity_edit_v1_2.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors` +1 more | ComfyUI-MultiShot-Plan, comfyui-krea2edit |
| [heroine-storyboard-krea-2-fix-b1-api](09-Movie/Short-Film-Projects/heroine-storyboard-krea-2-fix-b1-api.json) | Krea 2 multi-shot storyboard run for the Heroine short — fix b1 (API format) | `krea2_turbo_fp8_scaled.safetensors`, `krea2_identity_edit_v1_2.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors` +1 more | ComfyUI-MultiShot-Plan, comfyui-krea2edit |
| [heroine-storyboard-krea-2-fix-b1-v2-api](09-Movie/Short-Film-Projects/heroine-storyboard-krea-2-fix-b1-v2-api.json) | Krea 2 multi-shot storyboard run for the Heroine short — fix b1 v2 (API format) | `krea2_turbo_fp8_scaled.safetensors`, `krea2_identity_edit_v1_2.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors` +1 more | ComfyUI-MultiShot-Plan, comfyui-krea2edit |
| [heroine-storyboard-krea-2-fix-b3-v2-api](09-Movie/Short-Film-Projects/heroine-storyboard-krea-2-fix-b3-v2-api.json) | Krea 2 multi-shot storyboard run for the Heroine short — fix b3 v2 (API format) | `krea2_turbo_fp8_scaled.safetensors`, `krea2_identity_edit_v1_2.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors` +1 more | ComfyUI-MultiShot-Plan, comfyui-krea2edit |
| [heroine-storyboard-krea-2-fix-c1-api](09-Movie/Short-Film-Projects/heroine-storyboard-krea-2-fix-c1-api.json) | Krea 2 multi-shot storyboard run for the Heroine short — fix c1 (API format) | `krea2_turbo_fp8_scaled.safetensors`, `krea2_identity_edit_v1_2.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors` +1 more | ComfyUI-MultiShot-Plan, comfyui-krea2edit |
| [minimax-h3-chain-plan-test-api](09-Movie/Short-Film-Projects/minimax-h3-chain-plan-test-api.json) | Preview a MiniMax H3 chain scene plan without rendering (API format) | — | ComfyUI-MiniMaxH3-Context-Loop |
| [morning-departure-storyboard-krea-2-api](09-Movie/Short-Film-Projects/morning-departure-storyboard-krea-2-api.json) | Krea 2 multi-shot storyboard run for the Morning Departure short (API format) | `krea2_turbo_fp8_scaled.safetensors`, `krea2_identity_edit_v1_2.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors` +1 more | ComfyUI-MultiShot-Plan, comfyui-krea2edit |
| [naisha-rain-1-storyboard-krea-2](09-Movie/Short-Film-Projects/naisha-rain-1-storyboard-krea-2.json) | Storyboard stills for the "Naisha Rain" short: Krea 2 identity edit + multi-shot scene board | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2_identity_edit_v1_2.safetensors` +1 more | ComfyUI-MultiShot-Plan, comfyui-krea2edit |
| [naisha-rain-2-film-minimax-h3-fix-s15](09-Movie/Short-Film-Projects/naisha-rain-2-film-minimax-h3-fix-s15.json) | Scene-by-scene film render for the "Naisha Rain" short with the MiniMax H3 reference-to-video chain (fix s15) | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +3 more | ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, ComfyUI-Spectrum-MiniMax-H3 |
| [naisha-rain-2-film-minimax-h3-fix-s15b](09-Movie/Short-Film-Projects/naisha-rain-2-film-minimax-h3-fix-s15b.json) | Scene-by-scene film render for the "Naisha Rain" short with the MiniMax H3 reference-to-video chain (fix s15b) | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +3 more | ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, ComfyUI-Spectrum-MiniMax-H3 |
| [naisha-rain-2-film-minimax-h3-fix-s15c](09-Movie/Short-Film-Projects/naisha-rain-2-film-minimax-h3-fix-s15c.json) | Scene-by-scene film render for the "Naisha Rain" short with the MiniMax H3 reference-to-video chain (fix s15c) | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +3 more | ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, ComfyUI-Spectrum-MiniMax-H3 |
| [naisha-rain-2-film-minimax-h3-fix-s9](09-Movie/Short-Film-Projects/naisha-rain-2-film-minimax-h3-fix-s9.json) | Scene-by-scene film render for the "Naisha Rain" short with the MiniMax H3 reference-to-video chain (fix s9) | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +3 more | ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, ComfyUI-Spectrum-MiniMax-H3 |
| [naisha-rain-2-film-minimax-h3](09-Movie/Short-Film-Projects/naisha-rain-2-film-minimax-h3.json) | Scene-by-scene film render for the "Naisha Rain" short with the MiniMax H3 reference-to-video chain | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +3 more | ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, ComfyUI-Spectrum-MiniMax-H3 |
| [toonboy-1-storyboard-krea-2](09-Movie/Short-Film-Projects/toonboy-1-storyboard-krea-2.json) | Storyboard stills for the "Toon Boy" short: Krea 2 identity edit + multi-shot scene board | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2_identity_edit_v1_2.safetensors` +1 more | ComfyUI-MultiShot-Plan, comfyui-krea2edit |
| [toonboy-2-film-minimax-h3-v1-backup](09-Movie/Short-Film-Projects/toonboy-2-film-minimax-h3-v1-backup.json) | Scene-by-scene film render for the "Toon Boy" short with the MiniMax H3 reference-to-video chain (v1 backup) | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +3 more | ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, ComfyUI-Spectrum-MiniMax-H3 |
| [toonboy-2-film-minimax-h3-v2-backup](09-Movie/Short-Film-Projects/toonboy-2-film-minimax-h3-v2-backup.json) | Scene-by-scene film render for the "Toon Boy" short with the MiniMax H3 reference-to-video chain (v2 backup) | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +3 more | ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, ComfyUI-Spectrum-MiniMax-H3 |
| [toonboy-2-film-minimax-h3](09-Movie/Short-Film-Projects/toonboy-2-film-minimax-h3.json) | Scene-by-scene film render for the "Toon Boy" short with the MiniMax H3 reference-to-video chain | `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` +3 more | ComfyUI-MiniMaxH3-Context-Loop, ComfyUI-KJNodes, ComfyUI-Spectrum-MiniMax-H3 |

### 10 · LLM and Prompt Tools

Local LLM / VLM workflows that output text: prompt enhancers, image-to-prompt, video-to-prompt and audio-to-text with Gemma 4, Qwen 3.5, Qwen3-VL and MiniMax H3 prompt generators. Folder: [`10-LLM-and-Prompt-Tools/`](10-LLM-and-Prompt-Tools) — 15 workflows.

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [gemma-4-anima-prompt-enhancer](10-LLM-and-Prompt-Tools/gemma-4-anima-prompt-enhancer.json) | Anima Prompt Enhancer | `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma |
| [gemma-4-audio-to-text](10-LLM-and-Prompt-Tools/gemma-4-audio-to-text.json) | Audio to Text | `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma |
| [gemma-4-image-to-prompt](10-LLM-and-Prompt-Tools/gemma-4-image-to-prompt.json) | Image to Prompt | `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma |
| [gemma-4-prompt-enhancer](10-LLM-and-Prompt-Tools/gemma-4-prompt-enhancer.json) | Prompt Enhancer | `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma |
| [gemma-4-video-to-description](10-LLM-and-Prompt-Tools/gemma-4-video-to-description.json) | Video to Description | `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma |
| [gemma-4-video-to-prompt](10-LLM-and-Prompt-Tools/gemma-4-video-to-prompt.json) | Video to Prompt | `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma |
| [minimax-h3-first-frame-to-video-prompt-generator](10-LLM-and-Prompt-Tools/minimax-h3-first-frame-to-video-prompt-generator.json) | First Frame to Video Prompt Generator | — | ComfyUI-Pixaroma |
| [minimax-h3-txt2video-prompt-generator](10-LLM-and-Prompt-Tools/minimax-h3-txt2video-prompt-generator.json) | Text to Video Prompt Generator | — | ComfyUI-Pixaroma |
| [minimax-music-3-caption-and-lyrics-generator](10-LLM-and-Prompt-Tools/minimax-music-3-caption-and-lyrics-generator.json) | Caption and Lyrics Generator | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-read-prompt-from-image-metadata](10-LLM-and-Prompt-Tools/pixaroma-nodes-read-prompt-from-image-metadata.json) | Read Prompt From Image Metadata | — | ComfyUI-Pixaroma |
| [qwen-3.5-image-to-prompt](10-LLM-and-Prompt-Tools/qwen-3.5-image-to-prompt.json) | Image to Prompt | `qwen3.5_4b_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-3.5-text-to-prompt](10-LLM-and-Prompt-Tools/qwen-3.5-text-to-prompt.json) | Text to Prompt | `qwen3.5_4b_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-image-to-prompt-qwen3-vl-8b](10-LLM-and-Prompt-Tools/qwen-image-2.1-image-to-prompt-qwen3-vl-8b.json) | Image to Prompt (Qwen3-VL 8B) | `qwen3vl_8b_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [qwen3-vl-prompt-from-image](10-LLM-and-Prompt-Tools/qwen3-vl-prompt-from-image.json) | Prompt from Image | `qwen3-vl-4b-heretic_int8.safetensors` | ComfyUI-Pixaroma |
| [qwenvl-3-image-and-text-to-prompt-gguf](10-LLM-and-Prompt-Tools/qwenvl-3-image-and-text-to-prompt-gguf.json) | Image and Text to Prompt (GGUF) | `Qwen3VL-8B-Instruct-Q8_0.gguf` | ComfyUI-QwenVL |

### 90 · Docs and Resources

Learning workflows and node demos, LoRA training notes, LLM prompt-assistant instructions and sample input media. Folder: [`90-Docs-and-Resources/`](90-Docs-and-Resources) — 9 workflows.

#### Learning workflows and node demos (8)

Folder: [`90-Docs-and-Resources/Learning-and-Node-Demos/`](90-Docs-and-Resources/Learning-and-Node-Demos)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [flux-2-klein-9b-fp8-multi-step-workflow-example](90-Docs-and-Resources/Learning-and-Node-Demos/flux-2-klein-9b-fp8-multi-step-workflow-example.json) | Multi-Step Workflow Example | `flux-2-klein-9b-fp8mixed.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-RMBG, ComfyUI_LayerStyle, rgthree-comfy |
| [nodes-explained-01-models-explained-finished-z-image-turbo](90-Docs-and-Resources/Learning-and-Node-Demos/nodes-explained-01-models-explained-finished-z-image-turbo.json) | Models Explained — Finished (Z-Image Turbo) | `z_image_turbo_int8_convrot.safetensors`, `qwen_3_4b_fp8_mixed.safetensors`, `ae.safetensors` | Core only |
| [nodes-explained-01-models-explained-practice-z-image-turbo](90-Docs-and-Resources/Learning-and-Node-Demos/nodes-explained-01-models-explained-practice-z-image-turbo.json) | Models Explained — Practice (Z-Image Turbo) | `qwen_3_4b_fp8_mixed.safetensors`, `ae.safetensors` | Core only |
| [pixaroma-help-and-resources](90-Docs-and-Resources/Learning-and-Node-Demos/pixaroma-help-and-resources.json) | Help and Resources | — | Core only |
| [pixaroma-nodes-change-node-color](90-Docs-and-Resources/Learning-and-Node-Demos/pixaroma-nodes-change-node-color.json) | Change Node Color | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-labels-ep11](90-Docs-and-Resources/Learning-and-Node-Demos/pixaroma-nodes-labels-ep11.json) | Labels (Ep11) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-labels-ep13](90-Docs-and-Resources/Learning-and-Node-Demos/pixaroma-nodes-labels-ep13.json) | Labels (Ep13) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-note](90-Docs-and-Resources/Learning-and-Node-Demos/pixaroma-nodes-note.json) | Note | — | ComfyUI-Pixaroma |

#### LoRA conversion and training (1)

Folder: [`90-Docs-and-Resources/LoRA-Training/`](90-Docs-and-Resources/LoRA-Training)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [krea-2-lora-converter](90-Docs-and-Resources/LoRA-Training/krea-2-lora-converter.json) | LoRA Converter | `krea2-questpaint26.safetensors`, `krea2-questpaint26_comfyui.safetensors` | ComfyUI-Pixaroma |

### 91 · Version Conflicts

Original versions of workflows whose library copy has different settings, kept for comparison. Folder: [`91-Review-Version-Conflicts/`](91-Review-Version-Conflicts) — 5 workflows.

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [ep11-flux-2-klein-9b-fp8-distilled-one-image-edit-with-paint-pixaroma-node-pixaroma-original](91-Review-Version-Conflicts/ep11-flux-2-klein-9b-fp8-distilled-one-image-edit-with-paint-pixaroma-node-pixaroma-original.json) | Flux 2 Klein 9B FP8 (Distilled) — One Image Edit with Paint Pixaroma Node (Pixaroma original) | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [ep15-ace-step-v1.5-xl-turbo-text-to-music-pixaroma-original](91-Review-Version-Conflicts/ep15-ace-step-v1.5-xl-turbo-text-to-music-pixaroma-original.json) | ACE-Step v1.5 XL Turbo — Text to Music (Pixaroma original) | `qwen_0.6b_ace15.safetensors`, `qwen_4b_ace15.safetensors`, `acestep_v1.5_xl_turbo_bf16.safetensors` +1 more | ComfyUI-Pixaroma |
| [ep16-flux-2-klein-9b-image-to-prompt-to-image-qwen-3.5-pixaroma-original](91-Review-Version-Conflicts/ep16-flux-2-klein-9b-image-to-prompt-to-image-qwen-3.5-pixaroma-original.json) | Flux 2 Klein 9B — Image to Prompt to Image (Qwen 3.5) (Pixaroma original) | `flux-2-klein-9b-fp8mixed.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma |
| [ep16-flux-2-klein-9b-txt2img-qwen-3.5-prompt-enhancer-pixaroma-original](91-Review-Version-Conflicts/ep16-flux-2-klein-9b-txt2img-qwen-3.5-prompt-enhancer-pixaroma-original.json) | Flux 2 Klein 9B — Text to Image + Qwen 3.5 Prompt Enhancer (Pixaroma original) | `flux-2-klein-9b-fp8mixed.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma |
| [ep20-anima-base-v1.0-anime-txt2img-gemma-4-prompt-enhancer-pixaroma-original](91-Review-Version-Conflicts/ep20-anima-base-v1.0-anime-txt2img-gemma-4-prompt-enhancer-pixaroma-original.json) | Anima Base v1.0 — Anime Text to Image + Gemma 4 Prompt Enhancer (Pixaroma original) | `anima-base-v1.0.safetensors`, `qwen_image_vae.safetensors`, `qwen_3_06b_base.safetensors` +1 more | ComfyUI-Pixaroma |

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

The **Models used** column shows the exact filenames each workflow loads. Most workflows include download links in a note on the canvas, and ComfyUI offers to download embedded model links when it detects missing models.

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
| ComfyUI-Pixaroma | 269 workflows | [github.com/pixaroma/ComfyUI-Pixaroma](https://github.com/pixaroma/ComfyUI-Pixaroma) |
| ComfyUI-VideoHelperSuite | 53 workflows | [github.com/Kosinkadink/ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite) |
| rgthree-comfy | 52 workflows | [github.com/rgthree/rgthree-comfy](https://github.com/rgthree/rgthree-comfy) |
| ComfyUI-KJNodes | 50 workflows | [github.com/kijai/ComfyUI-KJNodes](https://github.com/kijai/ComfyUI-KJNodes) |
| comfyui-krea2edit | 33 workflows | [github.com/lbouaraba/comfyui-krea2edit](https://github.com/lbouaraba/comfyui-krea2edit) |
| ComfyUI-MiniMaxH3-Context-Loop | 31 workflows | [github.com/ethanfel/ComfyUI-MiniMaxH3-Context-Loop](https://github.com/ethanfel/ComfyUI-MiniMaxH3-Context-Loop) |
| ComfyUI-Krea2T-Enhancer | 30 workflows | [github.com/capitan01R/ComfyUI-Krea2T-Enhancer](https://github.com/capitan01R/ComfyUI-Krea2T-Enhancer) |
| ComfyUI-Spectrum-MiniMax-H3 | 30 workflows | [github.com/xmarre/ComfyUI-Spectrum-MiniMax-H3](https://github.com/xmarre/ComfyUI-Spectrum-MiniMax-H3) |
| ComfyUI-MultiShot-Plan | 28 workflows | [github.com/CodingWithShahzaib/ComfyUI-MultiShot-Plan](https://github.com/CodingWithShahzaib/ComfyUI-MultiShot-Plan) |
| ComfyUI_LayerStyle | 23 workflows | [github.com/chflame163/ComfyUI_LayerStyle](https://github.com/chflame163/ComfyUI_LayerStyle) |
| ComfyUI-Easy-Use | 22 workflows | [github.com/yolain/ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) |
| ComfyUI-WanVideoWrapper | 14 workflows | [github.com/kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper) |
| ComfyUI-RMBG | 12 workflows | [github.com/1038lab/ComfyUI-RMBG](https://github.com/1038lab/ComfyUI-RMBG) |
| ComfyUI-SeedVR2_VideoUpscaler | 11 workflows | [github.com/numz/ComfyUI-SeedVR2_VideoUpscaler](https://github.com/numz/ComfyUI-SeedVR2_VideoUpscaler) |
| ComfyUI-GGUF | 10 workflows | [github.com/city96/ComfyUI-GGUF](https://github.com/city96/ComfyUI-GGUF) |
| ComfyUI-Qwen-TTS | 8 workflows | [github.com/flybirdxx/ComfyUI-Qwen-TTS](https://github.com/flybirdxx/ComfyUI-Qwen-TTS) |
| ComfyUI-DubSync (local) | 7 workflows | Local pack, not published |
| ComfyUI-WanAnimatePreprocess | 7 workflows | [github.com/kijai/ComfyUI-WanAnimatePreprocess](https://github.com/kijai/ComfyUI-WanAnimatePreprocess) |
| wan-scail2-gap | 7 workflows | [github.com/GeekatplayStudio/wan-scail2-gap](https://github.com/GeekatplayStudio/wan-scail2-gap) |
| ComfyUI-Easy-Sam3 | 5 workflows | [github.com/yolain/ComfyUI-Easy-Sam3](https://github.com/yolain/ComfyUI-Easy-Sam3) |
| ComfyUI-MelBandRoFormer | 5 workflows | [github.com/kijai/ComfyUI-MelBandRoFormer](https://github.com/kijai/ComfyUI-MelBandRoFormer) |
| ComfyUI-nunchaku | 5 workflows | [github.com/nunchaku-ai/ComfyUI-nunchaku](https://github.com/nunchaku-ai/ComfyUI-nunchaku) |
| ComfyUI-ChatterboxTTS | 4 workflows | [github.com/Yuan-ManX/ComfyUI-ChatterboxTTS](https://github.com/Yuan-ManX/ComfyUI-ChatterboxTTS) |
| comfy_mtb | 3 workflows | [github.com/melMass/comfy_mtb](https://github.com/melMass/comfy_mtb) |
| ComfyUI-Custom-Scripts | 3 workflows | [github.com/pythongosssss/ComfyUI-Custom-Scripts](https://github.com/pythongosssss/ComfyUI-Custom-Scripts) |
| comfyui-fish-audio-s2 | 3 workflows | [registry.comfy.org/nodes/comfyui-fish-audio-s2](https://registry.comfy.org/nodes/comfyui-fish-audio-s2) |
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

Each category folder has its own `README.md` with a short overview.

## Contributing

Contributions are welcome: new workflows, fixes, better descriptions and model links.

1. Fork the repo and create a branch.
2. Put the workflow in the folder that matches its main job, and name it `model-task-variant.json` in kebab-case.
3. Before committing, open the JSON and remove anything private: API keys or tokens in node inputs, and personal file paths (for example `C:\Users\<you>\…`).
4. Add a note inside the workflow with model download links, and add a row to the catalog table in this README.
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
