# Image Generation — ComfyUI workflows

Workflows that create a new image: text-to-image, ControlNet- and layout-guided generation, LLM prompt enhancers and image-to-prompt-to-image, prompt batches, character sheets, design (logos, posters, text in images) and transparent PNGs.

[← 01-Image overview](../README.md) · [Library index](../../00-LIBRARY-INDEX.md)

**178 workflows** in **32 model folders**. Each model folder holds only workflow files; the file name says the task first, then the variant: `<task>[-<variant>][-<size>][-<precision>][-<feature>].json`. `Other/` holds generic or multi-model workflows.

## Model folders

| Model | Workflows | Tasks |
|---|---|---|
| [Anima](#anima) | 5 | `controlnet`, `txt2img` |
| [AuraFlow](#auraflow) | 1 | `txt2img` |
| [Boogu](#boogu) | 2 | `txt2img` |
| [Chroma](#chroma) | 2 | `txt2img` |
| [ERNIE-Image](#ernie-image) | 2 | `txt2img` |
| [FLUX-1](#flux-1) | 6 | `controlnet`, `txt2img` |
| [FLUX-2](#flux-2) | 17 | `img2prompt2img`, `prompt-batch`, `txt2img` |
| [FLUX-3](#flux-3) | 7 | `img2prompt2img`, `txt2img` |
| [GLIGEN](#gligen) | 2 | `layout` |
| [HiDream](#hidream) | 3 | `txt2img` |
| [HunyuanImage](#hunyuanimage) | 1 | `txt2img` |
| [Janus-Pro](#janus-pro) | 1 | `txt2img` |
| [Kandinsky](#kandinsky) | 1 | `txt2img` |
| [Kolors](#kolors) | 1 | `txt2img` |
| [Krea-2](#krea-2) | 24 | `img2prompt2img`, `txt2img` |
| [LayerDiffusion](#layerdiffusion) | 2 | `txt2img` |
| [Lens](#lens) | 1 | `txt2img` |
| [LongCat-Image](#longcat-image) | 1 | `txt2img` |
| [Lumina-Image-2](#lumina-image-2) | 1 | `txt2img` |
| [Ming-Image](#ming-image) | 12 | `design`, `txt2img` |
| [MiniMax-H3](#minimax-h3) | 2 | `txt2img` |
| [MOSS-Image](#moss-image) | 9 | `controlnet`, `img2prompt2img`, `txt2img` |
| [P-H3](#p-h3) | 3 | `txt2img` |
| [PixArt-Alpha](#pixart-alpha) | 1 | `txt2img` |
| [Qwen-Image](#qwen-image) | 14 | `controlnet`, `img2prompt2img`, `txt2img` |
| [Sana](#sana) | 3 | `txt2img` |
| [SD15](#sd15) | 10 | `controlnet`, `t2i-adapter`, `txt2img` |
| [SD3](#sd3) | 5 | `controlnet`, `txt2img` |
| [SDXL](#sdxl) | 8 | `controlnet`, `txt2img` |
| [Stable-Cascade](#stable-cascade) | 2 | `controlnet`, `txt2img` |
| [Z-Image](#z-image) | 24 | `character-sheet`, `controlnet`, `img2prompt2img`, `prompt-batch`, `txt2img` |
| [Other](#other) | 5 | `prompt-batch` |

## Anima

Folder: [`Anima/`](Anima) — 5 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [controlnet-lllite-any-control](Anima/controlnet-lllite-any-control.json) | ControlNet-LLLite "any" control to image (anime) | [link](https://huggingface.co/circlestone-labs/Anima) | — | Model: Anima; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_anima_lllite_any_control_to_image.json); Licence: Check Anima model card (non-commercial terms); Tested: not runtime-tested |
| [controlnet-lllite-depth](Anima/controlnet-lllite-depth.json) | Depth (Depth Anything 3) LLLite control to image | [link](https://huggingface.co/circlestone-labs/Anima) | — | Model: Anima; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_anima_lllite_depth_control_to_image.json); Licence: Check Anima model card (non-commercial terms); Tested: not runtime-tested |
| [txt2img-base-anime-gemma4-prompt-enhancer](Anima/txt2img-base-anime-gemma4-prompt-enhancer.json) | Anime Text to Image + Gemma 4 Prompt Enhancer | `qwen_image_vae.safetensors`, `qwen_3_06b_base.safetensors`, `gemma4_e4b_it_fp8_scaled.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [txt2img-base-anime-seedvr2-upscale](Anima/txt2img-base-anime-seedvr2-upscale.json) | Anime Text to Image + SeedVR2 Upscale | `anima-base-v1.0.safetensors`, `qwen_3_06b_base.safetensors`, `qwen_image_vae.safetensors` +2 more | ComfyUI-SeedVR2_VideoUpscaler, ComfyUI-Pixaroma | — |
| [txt2img-base-anime](Anima/txt2img-base-anime.json) | Anime Text to Image | `anima-base-v1.0.safetensors`, `qwen_3_06b_base.safetensors`, `qwen_image_vae.safetensors` | ComfyUI-Pixaroma | — |

## AuraFlow

Folder: [`AuraFlow/`](AuraFlow) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2img-v03](AuraFlow/txt2img-v03.json) | Text to image with AuraFlow (checkpoint name set to v0.3) | [link](https://huggingface.co/fal/AuraFlow-v0.3) | — | Model: AuraFlow v0.3; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/tree/master/aura_flow); Licence: Apache-2.0; Tested: not runtime-tested |

## Boogu

Folder: [`Boogu/`](Boogu) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2img-prompt-enhancer](Boogu/txt2img-prompt-enhancer.json) | Text to Image + Prompt Enhancer | `ae.safetensors`, `boogu_image_turbo_hotfix_int8_convrot.safetensors`, `qwen3vl_8b_fp8_scaled.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img](Boogu/txt2img.json) | Text to Image | `ae.safetensors`, `qwen3vl_8b_fp8_scaled.safetensors`, `boogu_image_turbo_hotfix_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |

## Chroma

Folder: [`Chroma/`](Chroma) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2img-hd](Chroma/txt2img-hd.json) | Text to image with Chroma1-HD (FP8-mixed) | [link](https://huggingface.co/lodestones/Chroma1-HD) | — | Model: Chroma 1 (HD); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_chroma_text_to_image.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [txt2img-radiance](Chroma/txt2img-radiance.json) | Pixel-space (no VAE) text to image with Chroma1-Radiance | [link](https://huggingface.co/lodestones/Chroma1-Radiance) | — | Model: Chroma 1 (Radiance); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_chroma1_radiance_text_to_image.json); Licence: Apache-2.0; Tested: not runtime-tested |

## ERNIE-Image

Folder: [`ERNIE-Image/`](ERNIE-Image) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2img-prompt-enhancer](ERNIE-Image/txt2img-prompt-enhancer.json) | Full ERNIE Image text to image with built-in prompt enhancer | [link](https://huggingface.co/Comfy-Org/ERNIE-Image/resolve/main/diffusion_models/ernie-image.safetensors) | — | Model: ERNIE Image; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_ernie_image.json); Licence: Check ERNIE Image model card; Tested: not runtime-tested |
| [txt2img-turbo-gguf](ERNIE-Image/txt2img-turbo-gguf.json) | Text to Image — GGUF | `ministral-3-3b.safetensors`, `flux2-vae.safetensors`, `ernie-image-turbo-Q8_0.gguf` | ComfyUI-GGUF, ComfyUI-Pixaroma | — |

## FLUX-1

Folder: [`FLUX-1/`](FLUX-1) — 6 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [controlnet-canny-dev](FLUX-1/controlnet-canny-dev.json) | Canny-edge controlled generation with FLUX.1 Canny dev | [link](https://huggingface.co/black-forest-labs/FLUX.1-Canny-dev) | — | Model: FLUX.1 [dev] (Canny); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/flux_canny_model_example.json); Licence: FLUX.1 [dev] Non-Commercial; Tested: not runtime-tested |
| [controlnet-depth-dev-lora](FLUX-1/controlnet-depth-dev-lora.json) | Depth-controlled generation with FLUX.1 Depth LoRA | [link](https://huggingface.co/black-forest-labs/FLUX.1-Depth-dev-lora) | — | Model: FLUX.1 [dev] (Depth LoRA); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/flux_depth_lora_example.json); Licence: FLUX.1 [dev] Non-Commercial; Tested: not runtime-tested |
| [txt2img-dev-nunchaku](FLUX-1/txt2img-dev-nunchaku.json) | Flux.1 Dev — Text to Image | `t5-v1_1-xxl-encoder-Q8_0.gguf`, `clip_l.safetensors`, `ae.safetensors` +1 more | ComfyUI-GGUF, ComfyUI-nunchaku | — |
| [txt2img-dev](FLUX-1/txt2img-dev.json) | Official full-precision text to image (separate UNet, CLIP-L, T5, VAE) | [link](https://huggingface.co/Comfy-Org/flux1-dev) | — | Model: FLUX.1 [dev]; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/flux_dev_checkpoint_example.json); Licence: FLUX.1 [dev] Non-Commercial; Tested: not runtime-tested |
| [txt2img-schnell-fp8](FLUX-1/txt2img-schnell-fp8.json) | Fast 4-step text to image, single FP8 checkpoint (low VRAM) | [link](https://huggingface.co/Comfy-Org/flux1-schnell) | — | Model: FLUX.1 [schnell]; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/flux_schnell.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [txt2img-schnell-full](FLUX-1/txt2img-schnell-full.json) | Text to image with separate full-precision UNet, CLIP-L/T5 and VAE | [link](https://huggingface.co/Comfy-Org/flux1-schnell) | — | Model: FLUX.1 [schnell]; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/flux_schnell_full_text_to_image.json); Licence: Apache-2.0; Tested: not runtime-tested |

## FLUX-2

Folder: [`FLUX-2/`](FLUX-2) — 17 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2prompt2img-klein-9b-qwen35](FLUX-2/img2prompt2img-klein-9b-qwen35.json) | Image to Prompt to Image (Qwen 3.5) | `flux-2-klein-9b-fp8mixed.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [prompt-batch-klein-9b-build-a-prompt-from-switches](FLUX-2/prompt-batch-klein-9b-build-a-prompt-from-switches.json) | Build a Prompt from Switches | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [prompt-batch-klein-9b-one-image-per-prompt](FLUX-2/prompt-batch-klein-9b-one-image-per-prompt.json) | One Image per Prompt | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [prompt-batch-klein-9b-one-subject-in-many-styles](FLUX-2/prompt-batch-klein-9b-one-subject-in-many-styles.json) | One Subject in Many Styles | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [prompt-batch-klein-9b-prompt-combinations-brackets](FLUX-2/prompt-batch-klein-9b-prompt-combinations-brackets.json) | Every Prompt Combination with Brackets | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [prompt-batch-klein-9b-queue-a-list-of-prompts](FLUX-2/prompt-batch-klein-9b-queue-a-list-of-prompts.json) | Queue a List of Prompts | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [prompt-batch-klein-9b-random-prompts-every-run](FLUX-2/prompt-batch-klein-9b-random-prompts-every-run.json) | Random Prompts Every Run | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [prompt-batch-klein-9b-short-ideas-to-images-qwen35](FLUX-2/prompt-batch-klein-9b-short-ideas-to-images-qwen35.json) | Short Ideas into Finished Images (Qwen 3.5 AI Prompt) | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [prompt-batch-klein-9b-story-to-storyboard-qwen35](FLUX-2/prompt-batch-klein-9b-story-to-storyboard-qwen35.json) | Short Story to Storyboard (Qwen 3.5 AI Prompt) | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [txt2img-dev-turbo-lora](FLUX-2/txt2img-dev-turbo-lora.json) | Text to image, FP8-mixed 32B model with Turbo LoRA and small decoder | [link](https://huggingface.co/Comfy-Org/flux2-dev) | — | Model: FLUX.2 [dev]; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_flux2_text_to_image.json); Licence: FLUX.2 [dev] Non-Commercial; Tested: not runtime-tested |
| [txt2img-klein-4b-and-4b-base](FLUX-2/txt2img-klein-4b-and-4b-base.json) | Text to image comparing distilled 4B and tunable 4B Base side by side | [link](https://huggingface.co/Comfy-Org/flux2-klein) | — | Model: FLUX.2 [klein] 4B / 4B Base; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_flux2_klein_text_to_image.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [txt2img-klein-4b-fp8-distill-basic](FLUX-2/txt2img-klein-4b-fp8-distill-basic.json) | Text to Image — Basic | `flux-2-klein-4b-fp8.safetensors`, `qwen_3_4b.safetensors`, `flux2-vae.safetensors` | Core only | — |
| [txt2img-klein-9b-base-fp8](FLUX-2/txt2img-klein-9b-base-fp8.json) | Text to image with the tunable 9B Base (FP8) | [link](https://huggingface.co/black-forest-labs/FLUX.2-klein-base-9b-fp8) | — | Model: FLUX.2 [klein] 9B Base; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_flux2_text_to_image_9b.json); Licence: FLUX Non-Commercial (9B); Tested: not runtime-tested |
| [txt2img-klein-9b-fp8-distill-basic](FLUX-2/txt2img-klein-9b-fp8-distill-basic.json) | Text to Image — Basic | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | Core only | — |
| [txt2img-klein-9b-fp8](FLUX-2/txt2img-klein-9b-fp8.json) | Text to Image (Ep16) | `flux-2-klein-9b-fp8mixed.safetensors`, `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img-klein-9b-qwen35-prompt-enhancer](FLUX-2/txt2img-klein-9b-qwen35-prompt-enhancer.json) | Text to Image + Qwen 3.5 Prompt Enhancer | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `qwen3.5_4b_bf16.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [txt2img-klein-9b](FLUX-2/txt2img-klein-9b.json) | Text to Image | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma | — |

## FLUX-3

Folder: [`FLUX-3/`](FLUX-3) — 7 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2prompt2img-klein](FLUX-3/img2prompt2img-klein.json) | Image to Prompt to Image | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [txt2img-klein-base](FLUX-3/txt2img-klein-base.json) | Text to image with the tunable Base checkpoint (INT8) + prompt upsampler | [link](https://huggingface.co/black-forest-labs/flux-3-image-klein-comfy) | — | Model: FLUX.3 Image Klein Base; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_flux3_klein_t2i.json); Licence: Check FLUX.3 Klein licence on model card; Tested: not runtime-tested |
| [txt2img-klein-layout-with-boxes](FLUX-3/txt2img-klein-layout-with-boxes.json) | Layout with Boxes | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img-klein-prompt-upsampler](FLUX-3/txt2img-klein-prompt-upsampler.json) | Text to Image + Prompt Upsampler | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [txt2img-klein-text-in-images](FLUX-3/txt2img-klein-text-in-images.json) | Text in Images | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img-klein-z-image-realism-pass](FLUX-3/txt2img-klein-z-image-realism-pass.json) | Text to Image + Z-Image Realism Pass | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` +4 more | ComfyUI-Pixaroma | — |
| [txt2img-klein](FLUX-3/txt2img-klein.json) | Text to Image | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |

## GLIGEN

Folder: [`GLIGEN/`](GLIGEN) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [layout-gui-draw-boxes](GLIGEN/layout-gui-draw-boxes.json) | Draw the GLIGEN boxes in a GUI node instead of typing coordinates | [weights](https://huggingface.co/comfyanonymous/GLIGEN_pruned_safetensors) | comfyui-gligengui-node | Model: GLIGEN; Source: [source](https://github.com/mut-ex/comfyui-gligengui-node/blob/main/gligen_gui_workflow.png); Licence: Review GLIGEN weight terms; Tested: not runtime-tested |
| [layout-textbox](GLIGEN/layout-textbox.json) | Place prompted objects inside boxes (box coordinates typed in) | [weights](https://huggingface.co/comfyanonymous/GLIGEN_pruned_safetensors) | — (core) | Model: GLIGEN; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/gligen/gligen_textbox_example.png); Licence: Review GLIGEN weight terms; Tested: not runtime-tested |

## HiDream

Folder: [`HiDream/`](HiDream) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2img-i1-dev](HiDream/txt2img-i1-dev.json) | Distilled HiDream-I1 text to image (~28 steps) | [link](https://huggingface.co/Comfy-Org/HiDream-I1_ComfyUI) | — | Model: HiDream-I1 Dev; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/hidream_i1_dev.json); Licence: MIT (Llama 3.1 encoder: Llama licence); Tested: not runtime-tested |
| [txt2img-i1-fast](HiDream/txt2img-i1-fast.json) | Fast HiDream-I1 text to image (~16 steps) | [link](https://huggingface.co/Comfy-Org/HiDream-I1_ComfyUI) | — | Model: HiDream-I1 Fast; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/hidream_i1_fast.json); Licence: MIT (Llama 3.1 encoder: Llama licence); Tested: not runtime-tested |
| [txt2img-i1-full](HiDream/txt2img-i1-full.json) | Highest-quality HiDream-I1 text to image (FP8, 50 steps) | [link](https://huggingface.co/Comfy-Org/HiDream-I1_ComfyUI) | — | Model: HiDream-I1 Full; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/hidream_i1_full.json); Licence: MIT (Llama 3.1 encoder: Llama licence); Tested: not runtime-tested |

## HunyuanImage

Folder: [`HunyuanImage/`](HunyuanImage) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2img-v21-refiner](HunyuanImage/txt2img-v21-refiner.json) | 2K text to image with base + refiner pass and glyph text encoder | [link](https://huggingface.co/Comfy-Org/HunyuanImage_2.1_ComfyUI) | — | Model: HunyuanImage 2.1; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/tree/master/hunyuan_image); Licence: Tencent Hunyuan Community (territory limits); Tested: not runtime-tested |

## Janus-Pro

Folder: [`Janus-Pro/`](Janus-Pro) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2img-and-understanding](Janus-Pro/txt2img-and-understanding.json) | Autoregressive text to image plus image understanding (select 1B or 7B) | [link](https://huggingface.co/deepseek-ai/Janus-Pro-7B) | ComfyUI-Janus-Pro, ComfyUI-Custom-Scripts | Model: Janus-Pro-7B; Source: [source](https://github.com/CY-CHENYUE/ComfyUI-Janus-Pro); Licence: MIT code + DeepSeek Model Licence; Tested: not runtime-tested |

## Kandinsky

Folder: [`Kandinsky/`](Kandinsky) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2img-v5-lite](Kandinsky/txt2img-v5-lite.json) | Text to image with Kandinsky 5.0 Image Lite | [link](https://huggingface.co/kandinskylab/Kandinsky-5.0-T2I-Lite) | — | Model: Kandinsky 5 Image (Lite); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_kandinsky5_t2i.json); Licence: Check Kandinsky 5 model card; Tested: not runtime-tested |

## Kolors

Folder: [`Kolors/`](Kolors) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2img](Kolors/txt2img.json) | Bilingual text to image with ChatGLM3 encoder | [link](https://huggingface.co/Kwai-Kolors/Kolors) | ComfyUI-KwaiKolorsWrapper | Model: Kolors; Source: [source](https://github.com/kijai/ComfyUI-KwaiKolorsWrapper/tree/main/examples); Licence: Kolors licence (commercial use needs registration); Tested: not runtime-tested |

## Krea-2

Folder: [`Krea-2/`](Krea-2) — 24 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2prompt2img-ep31](Krea-2/img2prompt2img-ep31.json) | Image to Prompt to Image (Ep31 AI Prompt Node) | `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [img2prompt2img-extra-pass-int8](Krea-2/img2prompt2img-extra-pass-int8.json) | Text to Image + Extra Pass + Image to Prompt | `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors`, `Huihui-Qwen3-VL-4B-Instruct-abliterated-fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [img2prompt2img-int8](Krea-2/img2prompt2img-int8.json) | Image to Prompt to Image | `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors`, `Huihui-Qwen3-VL-4B-Instruct-abliterated-fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [img2prompt2img](Krea-2/img2prompt2img.json) | Image to Prompt to Image | `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [txt2img-2k-prompt-enhancer-uncensored](Krea-2/txt2img-2k-prompt-enhancer-uncensored.json) | Text to Image — 2K Hi-Res + Prompt Enhancer (Uncensored) | `krea2_turbo_fp8_scaled.safetensors`, `Huihui-Qwen3-VL-4B-Instruct-abliterated-fp8_scaled.safetensors`, `qwen_image_vae.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [txt2img-2k-prompt-enhancer](Krea-2/txt2img-2k-prompt-enhancer.json) | Text to Image — 2K Hi-Res + Prompt Enhancer | `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [txt2img-base](Krea-2/txt2img-base.json) | Text to Image (Ep28) | `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [txt2img-extra-pass-int8-lora](Krea-2/txt2img-extra-pass-int8-lora.json) | Text to Image + Extra Pass + LoRA | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2-questpaint26_comfyui.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma, rgthree-comfy | — |
| [txt2img-extra-pass-int8-prompt-enhancer](Krea-2/txt2img-extra-pass-int8-prompt-enhancer.json) | Text to Image + Extra Pass + Prompt Enhancer | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2_turbo_int8_convrot.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [txt2img-extra-pass-int8](Krea-2/txt2img-extra-pass-int8.json) | Text to Image + Extra Pass | `qwen3vl_4b_fp8_scaled.safetensors`, `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [txt2img-extra-pass-lora](Krea-2/txt2img-extra-pass-lora.json) | Text to Image + Extra Pass + LoRA | `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma, rgthree-comfy | — |
| [txt2img-extra-pass-prompt-enhancer-uncensored](Krea-2/txt2img-extra-pass-prompt-enhancer-uncensored.json) | Text to Image + Extra Pass + Prompt Enhancer (Uncensored) | `krea2_turbo_fp8_scaled.safetensors`, `Huihui-Qwen3-VL-4B-Instruct-abliterated-fp8_scaled.safetensors`, `qwen_image_vae.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [txt2img-extra-pass-prompt-enhancer](Krea-2/txt2img-extra-pass-prompt-enhancer.json) | Text to Image + Extra Pass + Prompt Enhancer | `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [txt2img-extra-pass](Krea-2/txt2img-extra-pass.json) | Text to Image + Extra Pass | `qwen3vl_4b_fp8_scaled.safetensors`, `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [txt2img-int8-prompt-enhancer](Krea-2/txt2img-int8-prompt-enhancer.json) | Text to Image + Prompt Enhancer | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2_turbo_int8_convrot.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [txt2img-prompt-enhancer-ep28](Krea-2/txt2img-prompt-enhancer-ep28.json) | Text to Image + Prompt Enhancer (Ep28) | `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [txt2img-prompt-enhancer-ep31](Krea-2/txt2img-prompt-enhancer-ep31.json) | Text to Image + AI Prompt Enhancer (Ep31) | `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [txt2img-prompt-enhancer-uncensored](Krea-2/txt2img-prompt-enhancer-uncensored.json) | Text to Image + Prompt Enhancer (Uncensored) | `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors`, `Huihui-Qwen3-VL-4B-Instruct-abliterated-fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [txt2img-prompt-enhancer](Krea-2/txt2img-prompt-enhancer.json) | Text to Image + Prompt Enhancer | `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [txt2img-simple-int8-lora](Krea-2/txt2img-simple-int8-lora.json) | Text to Image — Simple + LoRA | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2_turbo_int8_convrot.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma, rgthree-comfy | — |
| [txt2img-simple-int8](Krea-2/txt2img-simple-int8.json) | Text to Image — Simple | `qwen3vl_4b_fp8_scaled.safetensors`, `qwen_image_vae.safetensors`, `krea2_turbo_int8_convrot.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [txt2img-simple-lora](Krea-2/txt2img-simple-lora.json) | Text to Image — Simple + LoRA | `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma, rgthree-comfy | — |
| [txt2img-simple-low-vram](Krea-2/txt2img-simple-low-vram.json) | Text to Image — Simple — Low VRAM | `qwen3vl_4b_fp8_scaled.safetensors`, `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |
| [txt2img-simple](Krea-2/txt2img-simple.json) | Text to Image — Simple | `qwen3vl_4b_fp8_scaled.safetensors`, `qwen_image_vae.safetensors`, `krea2_turbo_fp8_scaled.safetensors` | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma | — |

## LayerDiffusion

Folder: [`LayerDiffusion/`](LayerDiffusion) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2img-joint-fg-bg-blend](LayerDiffusion/txt2img-joint-fg-bg-blend.json) | Generate foreground, background and blended image together | same + any SD 1.5 checkpoint | ComfyUI-layerdiffuse | Model: LayerDiffusion (SD 1.5); Source: same; Licence: Check model card |
| [txt2img-transparent-fg](LayerDiffusion/txt2img-transparent-fg.json) | Text-to-image with a transparent RGBA foreground | [LayerDiffusion/layerdiffusion-v1](https://huggingface.co/LayerDiffusion/layerdiffusion-v1) (auto-download) + any SDXL checkpoint | ComfyUI-layerdiffuse | Model: LayerDiffusion (SDXL); Source: [huchenlei/ComfyUI-layerdiffuse](https://github.com/huchenlei/ComfyUI-layerdiffuse/tree/main/example_workflows); Licence: Check model card; base checkpoint licence applies |

## Lens

Folder: [`Lens/`](Lens) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2img](Lens/txt2img.json) | Text to Image | `lens_bf16.safetensors`, `gpt_oss_20b_nvfp4.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma | — |

## LongCat-Image

Folder: [`LongCat-Image/`](LongCat-Image) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2img](LongCat-Image/txt2img.json) | Bilingual (EN/ZH) text to image with strong text rendering | [link](https://huggingface.co/Comfy-Org/LongCat-Image/resolve/main/split_files/diffusion_models/longcat_image_bf16.safetensors) | — | Model: LongCat Image; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_longcat_text_to_image.json); Licence: Check LongCat-Image model card; Tested: not runtime-tested |

## Lumina-Image-2

Folder: [`Lumina-Image-2/`](Lumina-Image-2) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2img](Lumina-Image-2/txt2img.json) | Text to image with the all-in-one Lumina 2 checkpoint | [link](https://huggingface.co/Comfy-Org/Lumina_Image_2.0_Repackaged) | — | Model: Lumina Image 2.0; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/tree/master/lumina2); Licence: Apache-2.0; Tested: not runtime-tested |

## Ming-Image

Folder: [`Ming-Image/`](Ming-Image) — 12 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [design-3d-lettering](Ming-Image/design-3d-lettering.json) | 3D Lettering | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [design-app-and-website-screens](Ming-Image/design-app-and-website-screens.json) | App and Website Screens | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [design-event-poster](Ming-Image/design-event-poster.json) | Event Poster | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [design-game-screens-and-icons](Ming-Image/design-game-screens-and-icons.json) | Game Screens and Icons | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [design-infographic](Ming-Image/design-infographic.json) | Infographic | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [design-logo-variations](Ming-Image/design-logo-variations.json) | Logo Variations | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [design-logo](Ming-Image/design-logo.json) | Logo Design | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [design-social-media-post](Ming-Image/design-social-media-post.json) | Social Media Post | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [design-youtube-thumbnail](Ming-Image/design-youtube-thumbnail.json) | YouTube Thumbnail | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img-prompt-enhancer](Ming-Image/txt2img-prompt-enhancer.json) | Text to Image + Prompt Enhancer | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [txt2img-transparent-png](Ming-Image/txt2img-transparent-png.json) | Transparent PNG | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img](Ming-Image/txt2img.json) | Text to Image | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |

## MiniMax-H3

Folder: [`MiniMax-H3/`](MiniMax-H3) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2img-single-frame](MiniMax-H3/txt2img-single-frame.json) | Text to Image (Single Frame) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `minimax_h3_video_vae_fp16.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img](MiniMax-H3/txt2img.json) | MiniMax H3 Image — Text to Image (official ComfyUI template) | `minimax_h3_image_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_int8_convrot.safetensors`, `minimax_h3_image_vae_fp16.safetensors` +1 more | Core only | — |

## MOSS-Image

Folder: [`MOSS-Image/`](MOSS-Image) — 9 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [controlnet-color-depth](MOSS-Image/controlnet-color-depth.json) | Colour + depth (MoGe-3) controlled generation | [link](https://huggingface.co/Comfy-Org/MOSS-Image/resolve/main/diffusion_models/moss_image_sft_int8_convrot.safetensors) | — | Model: MOSS-Image SFT; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_moss_image_color_depth_control.json); Licence: Check MOSS-Image model card; Tested: not runtime-tested |
| [img2prompt2img](MOSS-Image/img2prompt2img.json) | MOSS Image - Image to Prompt to Image (Ep40) | `moss_image_sft_int8_convrot.safetensors`, `qwen3.5_9b_w4a8_gptq.safetensors`, `flux2-vae_small.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img-4-step-speed-lora](MOSS-Image/txt2img-4-step-speed-lora.json) | MOSS Image - Fast 4 Steps with a Speed LoRA (Ep40) | `moss_image_sft_int8_convrot.safetensors`, `qwen3.5_9b_w4a8_gptq.safetensors`, `flux2-vae_small.safetensors`, `moss_image_sft_4step_v2.0.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img-base-layout-with-boxes](MOSS-Image/txt2img-base-layout-with-boxes.json) | Layout control with bounding boxes on the Base checkpoint | [link](https://huggingface.co/Comfy-Org/MOSS-Image/resolve/main/diffusion_models/moss_image_base_int8_convrot.safetensors) | — | Model: MOSS-Image Base; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_moss_image_base_t2i_bboxes.json); Licence: Check MOSS-Image model card; Tested: not runtime-tested |
| [txt2img-base](MOSS-Image/txt2img-base.json) | Text to image with the Base (pre-SFT) checkpoint | [link](https://huggingface.co/Comfy-Org/MOSS-Image/resolve/main/diffusion_models/moss_image_base_int8_convrot.safetensors) | — | Model: MOSS-Image Base; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_moss_image_base_t2i.json); Licence: Check MOSS-Image model card; Tested: not runtime-tested |
| [txt2img-layout-with-boxes](MOSS-Image/txt2img-layout-with-boxes.json) | MOSS Image - Layout with Boxes (Ep40) | `moss_image_sft_int8_convrot.safetensors`, `qwen3.5_9b_w4a8_gptq.safetensors`, `flux2-vae_small.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img-prompt-helper](MOSS-Image/txt2img-prompt-helper.json) | MOSS Image - Text to Image + Prompt Helper (Ep40) | `moss_image_sft_int8_convrot.safetensors`, `qwen3.5_9b_w4a8_gptq.safetensors`, `flux2-vae_small.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img-text-in-images](MOSS-Image/txt2img-text-in-images.json) | MOSS Image - Words in Pictures (Ep40) | `moss_image_sft_int8_convrot.safetensors`, `qwen3.5_9b_w4a8_gptq.safetensors`, `flux2-vae_small.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img](MOSS-Image/txt2img.json) | MOSS Image - Text to Image (Ep40) | `moss_image_sft_int8_convrot.safetensors`, `qwen3.5_9b_w4a8_gptq.safetensors`, `flux2-vae_small.safetensors` | ComfyUI-Pixaroma | — |

## P-H3

Folder: [`P-H3/`](P-H3) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2img-short-idea-prompt-upsampler](P-H3/txt2img-short-idea-prompt-upsampler.json) | P-H3 Image - Short Idea with Prompt Upsampler (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors`, `p-h3-image_prompt_upsampler_w4a8.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img-text-in-images](P-H3/txt2img-text-in-images.json) | P-H3 Image - Words in Pictures (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img](P-H3/txt2img.json) | P-H3 Image - Text to Image (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |

## PixArt-Alpha

Folder: [`PixArt-Alpha/`](PixArt-Alpha) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2img](PixArt-Alpha/txt2img.json) | PixArt-XL-2 1024px text to image with T5 encoder | [link](https://huggingface.co/PixArt-alpha/PixArt-XL-2-1024-MS) | ComfyUI_ExtraModels | Model: PixArt-alpha; Source: [source](https://github.com/city96/ComfyUI_ExtraModels); Licence: OpenRAIL++; Tested: not runtime-tested |

## Qwen-Image

Folder: [`Qwen-Image/`](Qwen-Image) — 14 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [controlnet-canny-diffsynth-patch](Qwen-Image/controlnet-canny-diffsynth-patch.json) | Canny control via DiffSynth model patch | [link](https://huggingface.co/Comfy-Org/Qwen-Image-DiffSynth-ControlNets) | — | Model: Qwen-Image; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_qwen_image_controlnet_patch.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [controlnet-union-2512-fun](Qwen-Image/controlnet-union-2512-fun.json) | Fun ControlNet Union on Qwen-Image-2512 | [link](https://huggingface.co/Comfy-Org/Qwen-Image_ComfyUI/resolve/main/split_files/diffusion_models/qwen_image_2512_fp8_e4m3fn.safetensors) | — | Model: Qwen-Image-2512; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_qwen_Image_2512_controlnet.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [controlnet-union-control-lora](Qwen-Image/controlnet-union-control-lora.json) | DiffSynth Union control LoRA | [link](https://huggingface.co/Comfy-Org/Qwen-Image-DiffSynth-ControlNets) | — | Model: Qwen-Image; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_qwen_image_union_control_lora.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [controlnet-union-instantx](Qwen-Image/controlnet-union-instantx.json) | InstantX ControlNet Union (canny/depth/pose) with Lotus depth | [link](https://huggingface.co/InstantX/Qwen-Image-ControlNet-Union) | — | Model: Qwen-Image; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_qwen_image_instantx_controlnet.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [img2prompt2img-v21](Qwen-Image/img2prompt2img-v21.json) | Image to Prompt to Image | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img-2512-2-step-turbo-lora](Qwen-Image/txt2img-2512-2-step-turbo-lora.json) | 2-step text to image with the Wuli Turbo LoRA | [link](https://huggingface.co/Comfy-Org/Qwen-Image_ComfyUI) | — | Model: Qwen-Image-2512; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_qwen_image_2512_with_2steps_lora.json); Licence: Apache-2.0 (check LoRA card); Tested: not runtime-tested |
| [txt2img-2512](Qwen-Image/txt2img-2512.json) | Text to image with Qwen-Image-2512 (FP8) and Lightning 4-step LoRA | [link](https://huggingface.co/Comfy-Org/Qwen-Image_ComfyUI) | — | Model: Qwen-Image-2512; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_qwen_Image_2512.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [txt2img-base](Qwen-Image/txt2img-base.json) | Original Qwen-Image text to image (FP8) with optional Lightning 8-step LoRA | [link](https://huggingface.co/Comfy-Org/Qwen-Image_ComfyUI) | — | Model: Qwen-Image (20B); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_qwen_image.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [txt2img-lightning-nunchaku](Qwen-Image/txt2img-lightning-nunchaku.json) | Qwen Image Lightning — Text to Image | `svdq-int4_r128-qwen-image-lightningv1.1-8steps.safetensors`, `qwen_2.5_vl_7b_fp8_scaled.safetensors`, `qwen_image_vae.safetensors` | ComfyUI-nunchaku | — |
| [txt2img-v21-low-vram](Qwen-Image/txt2img-v21-low-vram.json) | Text to Image — Low VRAM | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img-v21-prompt-enhancer](Qwen-Image/txt2img-v21-prompt-enhancer.json) | Text to Image + Prompt Enhancer | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img-v21-transparent-png](Qwen-Image/txt2img-v21-transparent-png.json) | Transparent PNG | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img-v21-turbo](Qwen-Image/txt2img-v21-turbo.json) | Text to Image — Turbo | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [txt2img-v21](Qwen-Image/txt2img-v21.json) | Text to Image | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma | — |

## Sana

Folder: [`Sana/`](Sana) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2img-1b6-4k](Sana/txt2img-1b6-4k.json) | Native 4K text to image with Sana 1600M 4K | [link](https://huggingface.co/Efficient-Large-Model/Sana_1600M_4Kpx_BF16) | ComfyUI_ExtraModels (Efficient-Large-Model fork) | Model: Sana 1.6B (4K); Source: [source](https://github.com/NVlabs/Sana/tree/main/asset/docs/ComfyUI); Licence: NVIDIA Sana licence (non-commercial); Tested: not runtime-tested |
| [txt2img-1b6](Sana/txt2img-1b6.json) | Text to image with Sana 1600M 1024px | [link](https://huggingface.co/Efficient-Large-Model/Sana_1600M_1024px_BF16) | ComfyUI_ExtraModels (Efficient-Large-Model fork) | Model: Sana 1.6B; Source: [source](https://github.com/NVlabs/Sana/tree/main/asset/docs/ComfyUI); Licence: NVIDIA Sana licence (non-commercial); Tested: not runtime-tested |
| [txt2img-v15-4b8](Sana/txt2img-v15-4b8.json) | Text to image with SANA 1.5 4.8B | [link](https://huggingface.co/Efficient-Large-Model/SANA1.5_4.8B_1024px) | ComfyUI_ExtraModels (Efficient-Large-Model fork) | Model: Sana 1.5; Source: [source](https://github.com/NVlabs/Sana/tree/main/asset/docs/ComfyUI); Licence: NVIDIA Sana licence (non-commercial); Tested: not runtime-tested |

## SD15

Folder: [`SD15/`](SD15) — 10 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [controlnet-canny-juggernaut](SD15/controlnet-canny-juggernaut.json) | Text to Image + ControlNet Canny | `juggernaut_reborn.safetensors`, `control_v11p_sd15_canny_fp16.safetensors` | comfyui_controlnet_aux | — |
| [controlnet-depth](SD15/controlnet-depth.json) | Depth-map guided SD 1.5 generation (official example, ControlNet file switched to v1.1) | [weights](https://huggingface.co/lllyasviel/ControlNet-v1-1) | — (core) | Model: ControlNet v1.1 Depth; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/controlnet/depth_controlnet.png); Licence: OpenRAIL; review checkpoint; Tested: not runtime-tested |
| [controlnet-lineart](SD15/controlnet-lineart.json) | Clean line art to image (official ControlNet example graph with the LineArt model; feed white-on-black line art) | [weights](https://huggingface.co/lllyasviel/ControlNet-v1-1) | — (core) | Model: ControlNet v1.1 LineArt; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/controlnet/controlnet_example.png); Licence: OpenRAIL; review checkpoint; Tested: not runtime-tested |
| [controlnet-openpose-2-pass](SD15/controlnet-openpose-2-pass.json) | Pose-skeleton guided generation with a 2-pass hires fix (ControlNet file switched to v1.1) | [weights](https://huggingface.co/lllyasviel/ControlNet-v1-1) | — (core) | Model: ControlNet v1.1 OpenPose; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/controlnet/2_pass_pose_worship.png); Licence: OpenRAIL; review checkpoint; Tested: not runtime-tested |
| [controlnet-openpose-plus-scribble](SD15/controlnet-openpose-plus-scribble.json) | Chain two ControlNets (pose + scribble) in one generation | [weights](https://huggingface.co/lllyasviel/ControlNet-v1-1) | — (core) | Model: ControlNet v1.1 OpenPose + Scribble; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/controlnet/mixing_controlnets.png); Licence: OpenRAIL; review checkpoint; Tested: not runtime-tested |
| [controlnet-scribble](SD15/controlnet-scribble.json) | Loose sketch to image (ControlNet file switched to v1.1) | [weights](https://huggingface.co/lllyasviel/ControlNet-v1-1) | — (core) | Model: ControlNet v1.1 Scribble; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/controlnet/controlnet_example.png); Licence: OpenRAIL; review checkpoint; Tested: not runtime-tested |
| [t2i-adapter-depth](SD15/t2i-adapter-depth.json) | Lightweight depth control with a T2I-Adapter | [weights](https://huggingface.co/TencentARC/T2I-Adapter) | — (core) | Model: T2I-Adapter (depth); Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/controlnet/depth_t2i_adapter.png); Licence: Apache-2.0; Tested: not runtime-tested |
| [txt2img-juggernaut-lora-starter](SD15/txt2img-juggernaut-lora-starter.json) | SD 1.5 text-to-image with Juggernaut Reborn plus a style LoRA (ComfyUI-Easy-Install starter version) | `juggernaut_reborn.safetensors`, `CakeStyle.safetensors` | Core only | — |
| [txt2img-juggernaut-lora](SD15/txt2img-juggernaut-lora.json) | Text to Image + LoRA | `juggernaut_reborn.safetensors`, `CakeStyle.safetensors` | Core only | — |
| [txt2img-juggernaut](SD15/txt2img-juggernaut.json) | Text to Image | `juggernaut_reborn.safetensors` | Core only | — |

## SD3

Folder: [`SD3/`](SD3) — 5 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [controlnet-blur-large](SD3/controlnet-blur-large.json) | Blur ControlNet (tile-like re-detailing) on SD3.5 Large | [link](https://huggingface.co/stabilityai/stable-diffusion-3.5-controlnets) | — | Model: Stable Diffusion 3.5 Large; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/sd3.5_large_blur.json); Licence: Stability AI Community; Tested: not runtime-tested |
| [controlnet-canny-large](SD3/controlnet-canny-large.json) | Canny ControlNet on SD3.5 Large | [link](https://huggingface.co/stabilityai/stable-diffusion-3.5-controlnets) | — | Model: Stable Diffusion 3.5 Large; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/sd3.5_large_canny_controlnet_example.json); Licence: Stability AI Community; Tested: not runtime-tested |
| [controlnet-depth-large](SD3/controlnet-depth-large.json) | Depth ControlNet on SD3.5 Large (Lotus depth) | [link](https://huggingface.co/stabilityai/stable-diffusion-3.5-controlnets) | — | Model: Stable Diffusion 3.5 Large; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/sd3.5_large_depth.json); Licence: Stability AI Community; Tested: not runtime-tested |
| [txt2img-large-fp8](SD3/txt2img-large-fp8.json) | Text to image with SD3.5 Large FP8 all-in-one checkpoint | [link](https://huggingface.co/Comfy-Org/stable-diffusion-3.5-fp8) | — | Model: Stable Diffusion 3.5 Large; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/sd3.5_simple_example.json); Licence: Stability AI Community; Tested: not runtime-tested |
| [txt2img-medium](SD3/txt2img-medium.json) | Text to image, all-in-one SD3 Medium checkpoint with T5 FP8 | [link](https://huggingface.co/stabilityai/stable-diffusion-3-medium) | — | Model: Stable Diffusion 3 Medium; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/tree/master/sd3); Licence: Stability AI Community; Tested: not runtime-tested |

## SDXL

Folder: [`SDXL/`](SDXL) — 8 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [controlnet-canny](SDXL/controlnet-canny.json) | SDXL generation following Canny edges of an input picture | [weights](https://huggingface.co/lllyasviel/sd_control_collection) | — (core) | Model: ControlNet XL (Canny); Source: [source](https://github.com/CerebriumAI/examples/blob/master/7-image-and-video/1-comfyui/workflow.json); Licence: Review checkpoint (diffusers SDXL ControlNet); Tested: not runtime-tested |
| [txt2img-base-plus-refiner](SDXL/txt2img-base-plus-refiner.json) | Base then refiner two-stage SDXL text to image | [link](https://huggingface.co/stabilityai/stable-diffusion-xl-refiner-1.0) | — | Model: SDXL Base 1.0 + Refiner 1.0; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/sdxl_simple_example.json); Licence: CreativeML OpenRAIL++-M; Tested: not runtime-tested |
| [txt2img-base](SDXL/txt2img-base.json) | Basic SDXL base text to image | [link](https://huggingface.co/stabilityai/stable-diffusion-xl-base-1.0) | — | Model: SDXL Base 1.0; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_sdxl_simple.json); Licence: CreativeML OpenRAIL++-M; Tested: not runtime-tested |
| [txt2img-hyper-1-step-unet](SDXL/txt2img-hyper-1-step-unet.json) | 1-step text to image with Hyper-SDXL UNet and TCD-style scheduler | [link](https://huggingface.co/ByteDance/Hyper-SD) | ComfyUI-HyperSDXL1StepUnetScheduler (see Hyper-SD repo) | Model: SDXL Hyper (Hyper-SD); Source: [source](https://huggingface.co/ByteDance/Hyper-SD/tree/main/comfyui); Licence: Check Hyper-SD model card; Tested: not runtime-tested |
| [txt2img-hyper-2-step-lora](SDXL/txt2img-hyper-2-step-lora.json) | Few-step Hyper-SDXL LoRA on SDXL base | [link](https://huggingface.co/ByteDance/Hyper-SD) | — | Model: SDXL Hyper (Hyper-SD); Source: [source](https://huggingface.co/ByteDance/Hyper-SD/tree/main/comfyui); Licence: Check Hyper-SD model card; Tested: not runtime-tested |
| [txt2img-lightning-4-step-lora](SDXL/txt2img-lightning-4-step-lora.json) | 4-step Lightning LoRA on SDXL base (works with SDXL fine-tunes) | [link](https://huggingface.co/ByteDance/SDXL-Lightning) | — | Model: SDXL-Lightning; Source: [source](https://huggingface.co/ByteDance/SDXL-Lightning/tree/main/comfyui); Licence: OpenRAIL++; Tested: not runtime-tested |
| [txt2img-lightning-4-step-unet](SDXL/txt2img-lightning-4-step-unet.json) | 4-step text to image with the full Lightning checkpoint | [link](https://huggingface.co/ByteDance/SDXL-Lightning) | — | Model: SDXL-Lightning; Source: [source](https://huggingface.co/ByteDance/SDXL-Lightning/tree/main/comfyui); Licence: OpenRAIL++; Tested: not runtime-tested |
| [txt2img-turbo](SDXL/txt2img-turbo.json) | 1-step text to image with SDXL Turbo | [link](https://huggingface.co/stabilityai/sdxl-turbo) | — | Model: SDXL Turbo; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/sdxlturbo_example.json); Licence: Stability AI Community / research; Tested: not runtime-tested |

## Stable-Cascade

Folder: [`Stable-Cascade/`](Stable-Cascade) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [controlnet-canny](Stable-Cascade/controlnet-canny.json) | Canny ControlNet for Stable Cascade | [link](https://huggingface.co/stabilityai/stable-cascade) | — | Model: Stable Cascade; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/tree/master/stable_cascade); Licence: Stability non-commercial research; Tested: not runtime-tested |
| [txt2img](Stable-Cascade/txt2img.json) | Stage C + Stage B text to image | [link](https://huggingface.co/stabilityai/stable-cascade) | — | Model: Stable Cascade; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/tree/master/stable_cascade); Licence: Stability non-commercial research; Tested: not runtime-tested |

## Z-Image

Folder: [`Z-Image/`](Z-Image) — 24 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [character-sheet-turbo-alt-1](Z-Image/character-sheet-turbo-alt-1.json) | Z-Image Turbo character sheet, alternate prompt/settings | `z_image_turbo_bf16.safetensors`, `qwen_3_4b.safetensors`, `ae.safetensors` | Core only | — |
| [character-sheet-turbo-alt-2](Z-Image/character-sheet-turbo-alt-2.json) | Z-Image Turbo character sheet, alternate prompt/settings | `z_image_turbo_bf16.safetensors`, `qwen_3_4b.safetensors`, `ae.safetensors` | Core only | — |
| [character-sheet-turbo](Z-Image/character-sheet-turbo.json) | Z-Image Turbo character sheet (based on the official ComfyUI Z-Image template) | `qwen_3_4b.safetensors`, `ae.safetensors`, `z_image_turbo_bf16.safetensors` | Core only | — |
| [controlnet-union-turbo-fp8-aio](Z-Image/controlnet-union-turbo-fp8-aio.json) | Text to Image — FP8 AIO + ControlNet Union | `Z-Image-Turbo-Fun-Controlnet-Union.safetensors`, `z-image-turbo-fp8-aio.safetensors` | comfyui_controlnet_aux, rgthree-comfy | — |
| [img2prompt2img-turbo-gemma4](Z-Image/img2prompt2img-turbo-gemma4.json) | Image to Prompt to Image (Gemma 4) | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [prompt-batch-turbo-multi-queue-text](Z-Image/prompt-batch-turbo-multi-queue-text.json) | Prompt Multi — Queue Text | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | ComfyUI-Pixaroma | — |
| [prompt-batch-turbo-pack-line](Z-Image/prompt-batch-turbo-pack-line.json) | Prompt Pack — Line | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | ComfyUI-Pixaroma | — |
| [prompt-batch-turbo-pack-paragraph](Z-Image/prompt-batch-turbo-pack-paragraph.json) | Prompt Pack — Paragraph | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | ComfyUI-Pixaroma | — |
| [prompt-batch-turbo-stack](Z-Image/prompt-batch-turbo-stack.json) | Prompt Stack | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img-base-int8](Z-Image/txt2img-base-int8.json) | Low-VRAM INT8 text to image with Z-Image base | [link](https://huggingface.co/Comfy-Org/z_image) | — | Model: Z-Image (Base); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_z_image_int8.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [txt2img-base](Z-Image/txt2img-base.json) | Text to image with the non-distilled Z-Image base (BF16) | [link](https://huggingface.co/Comfy-Org/z_image) | — | Model: Z-Image (Base); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_z_image.json); Licence: Apache-2.0; Tested: not runtime-tested |
| [txt2img-turbo-fp8-aio-checkpoint](Z-Image/txt2img-turbo-fp8-aio-checkpoint.json) | Text to Image — FP8 AIO Checkpoint | `z-image-turbo-fp8-aio.safetensors` | Core only | — |
| [txt2img-turbo-fp8-aio-lora](Z-Image/txt2img-turbo-fp8-aio-lora.json) | Text to Image — FP8 AIO + LoRA | `pixag1rlwh1t3.safetensors`, `z-image-turbo-fp8-aio.safetensors` | Core only | — |
| [txt2img-turbo-fp8-aio-starter](Z-Image/txt2img-turbo-fp8-aio-starter.json) | Z-Image Turbo text-to-image from one FP8 all-in-one checkpoint (ComfyUI-Easy-Install starter version) | `z-image-turbo-fp8-aio.safetensors` | Core only | — |
| [txt2img-turbo-fp8-ep18](Z-Image/txt2img-turbo-fp8-ep18.json) | Text to Image — FP8 (Ep18) | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img-turbo-fp8](Z-Image/txt2img-turbo-fp8.json) | Text to Image — FP8 | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | Core only | — |
| [txt2img-turbo-gemma4-prompt-enhancer-replace](Z-Image/txt2img-turbo-gemma4-prompt-enhancer-replace.json) | Text to Image + Gemma 4 Prompt Enhancer + Find and Replace | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [txt2img-turbo-gemma4-prompt-enhancer](Z-Image/txt2img-turbo-gemma4-prompt-enhancer.json) | Text to Image + Gemma 4 Prompt Enhancer | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [txt2img-turbo-gguf](Z-Image/txt2img-turbo-gguf.json) | Text to Image — GGUF | `z-image-turbo-q4_k_s.gguf`, `qwen-4b-zimage-heretic-q8.gguf`, `ae.safetensors` | ComfyUI-GGUF | — |
| [txt2img-turbo-int8-prompt-enhancer](Z-Image/txt2img-turbo-int8-prompt-enhancer.json) | Text to Image + AI Prompt Enhancer | `ae.safetensors`, `z_image_turbo_int8_convrot.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img-turbo-int8](Z-Image/txt2img-turbo-int8.json) | Text to Image | `qwen_3_4b_fp8_mixed.safetensors`, `z_image_turbo_int8_convrot.safetensors`, `ae.safetensors` | ComfyUI-Pixaroma | — |
| [txt2img-turbo-nunchaku-qwenvl-prompt-enhancer](Z-Image/txt2img-turbo-nunchaku-qwenvl-prompt-enhancer.json) | Z-Image Turbo — Text to Image + QwenVL GGUF Prompt Enhancer | `Qwen3VL-8B-Instruct-Q8_0.gguf`, `svdq-int4_r256-z-image-turbo.safetensors`, `Huihui-Qwen3-4B-abliterated-v2_fp8mixed.safetensors` +1 more | ComfyUI-QwenVL, ComfyUI-nunchaku | — |
| [txt2img-turbo-nunchaku](Z-Image/txt2img-turbo-nunchaku.json) | Z-Image Turbo — Text to Image | `ae.safetensors`, `svdq-int4_r256-z-image-turbo.safetensors`, `Huihui-Qwen3-4B-abliterated-v2_fp8mixed.safetensors` | ComfyUI-nunchaku | — |
| [txt2img-turbo-text-overlay](Z-Image/txt2img-turbo-text-overlay.json) | Text to Image + Text Overlay | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | ComfyUI-Pixaroma | — |

## Other

Folder: [`Other/`](Other) — 5 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [prompt-batch-pixaroma-multi-from-list](Other/prompt-batch-pixaroma-multi-from-list.json) | Prompt Multi — From List | — | ComfyUI-Pixaroma | — |
| [prompt-batch-pixaroma-multi-queue-text](Other/prompt-batch-pixaroma-multi-queue-text.json) | Prompt Multi — Queue Text | — | ComfyUI-Pixaroma | — |
| [prompt-batch-pixaroma-pack-line](Other/prompt-batch-pixaroma-pack-line.json) | Prompt Pack — Line | — | ComfyUI-Pixaroma | — |
| [prompt-batch-pixaroma-pack-paragraph](Other/prompt-batch-pixaroma-pack-paragraph.json) | Prompt Pack — Paragraph | — | ComfyUI-Pixaroma | — |
| [prompt-batch-pixaroma-stack](Other/prompt-batch-pixaroma-stack.json) | Prompt Stack | — | ComfyUI-Pixaroma | — |

## Notes carried over from the previous folder layout

Setup notes, licences, test results and "not available in ComfyUI" lists from the former task-folder READMEs. Links point to the new locations.

### From the former "Image Generation" README

Text-to-image (txt2img) workflows for FLUX.2 / FLUX.3 Klein, Qwen-Image 2.1, Krea 2, Z-Image Turbo, Ming Image, SD 1.5 and more — plus ControlNet, LLM prompt enhancers, typography / logo / transparent PNG design and prompt batching.

#### Open-Source Image Model Atlas additions (Nov 2026, 88 workflows)

Collected for the "Image Generation" entries (IMG-001 to IMG-085) of the *Open-Source Image Model Atlas* research document. Every file is an existing workflow from the official [Comfy-Org workflow templates](https://github.com/Comfy-Org/workflow_templates), the official [ComfyUI examples](https://github.com/comfyanonymous/ComfyUI_examples) (graph extracted from the example PNG), the model authors' own repos, or the custom-node repo that implements the model. Only change made: the AuraFlow example checkpoint name was set to v0.3. Files were checked to be valid ComfyUI workflow JSON for the named model and task; **none was run — not runtime-tested.** No model weights are included; download them from the links. "-" in custom nodes means core ComfyUI only (a recent ComfyUI build is needed for newer models). Licences are summaries: read the model card before commercial use.

##### Duplicates skipped (30)

Official templates for a model + task the library already covers (anywhere in `01-Image`) were not added: Z-Image Turbo t2i, Z-Image Turbo INT8, Z-Image Turbo Fun ControlNet Union; Krea 2 Turbo t2i and INT8; MOSS-Image t2i and bbox layout; Ming Image 0.1 t2i and edit; MiniMax H3 Image t2i (2 templates) and edit; P-H3 Image t2i and edit; Boogu 0.1 Turbo t2i; Anima base v1 t2i; Qwen-Image 2.1 t2i, Turbo t2i, edit, Turbo edit and background removal; FLUX.2 Klein 4B distilled edit, 9B distilled edit and 9B KV edit; FLUX.3 Klein distilled t2i and edit; ERNIE Image Turbo; plus three identical-graph templates (FLUX.1 dev "full", FLUX.1 schnell checkpoint example, SDXL refiner-prompt example).

##### Not available in ComfyUI (this slice)

No authentic ComfyUI workflow was found, so nothing was fabricated:

- **GLM-Image** (IMG-029) — no ComfyUI integration found.
- **HunyuanImage 3.0 / 3.0 Instruct / 3.0 Instruct Distil** (IMG-037–039) — 80B MoE autoregressive; no native or maintained ComfyUI workflow.
- **Boogu Image 0.1 Base** (IMG-042) — only Turbo and Edit have ComfyUI templates.
- **Kandinsky 3** (IMG-048), **Wuerstchen v2** (IMG-072), **DeepFloyd IF Stage I XL** (IMG-073) — no maintained ComfyUI workflow.
- **Show-o2** (IMG-083), **BAGEL** (IMG-084), **Emu3** (IMG-085) — no verified ComfyUI workflow.
- **PixArt-Sigma** (IMG-053) and **Sana 0.6B** (IMG-054) — supported by ComfyUI_ExtraModels but no published sample workflow; use the PixArt / Sana graphs above with the other checkpoint.
- **Stable Diffusion 2.1** (IMG-061), **SD 3.5 Medium** (IMG-068), **SD 3.5 Large Turbo** (IMG-070) — no dedicated official workflow; they load in the SDXL/SD3.5 graphs above by swapping the checkpoint.
- **Playground v2.5, OpenJourney v4, DreamShaper XL, RealVisXL, Animagine XL 3.1, Illustrious XL, Pony Diffusion XL** (IMG-074, 075, 077–081) — checkpoint fine-tunes with no workflow of their own; load them in `sdxl-base-txt2img` (or the SD 1.5 workflows). No copies were added just to rename a checkpoint.

Already covered by existing library workflows: Qwen-Image 2.1, Z-Image Turbo, Krea 2 Raw/Turbo, MOSS-Image SFT, Ming Image 0.1, MiniMax-H3-Image, P-H3-Image, Boogu Turbo / Edit Turbo, Anima, ERNIE Image Turbo, FLUX.2 Klein 4B/9B, FLUX.3 Klein, Juggernaut Reborn, Stable Diffusion 1.5.

See the [01-Image overview](../README.md) for the other categories, the [main README](../../README.md) for setup, or [`00-LIBRARY-INDEX.md`](../../00-LIBRARY-INDEX.md) for the full list.
