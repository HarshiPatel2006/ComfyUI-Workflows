# Image Enhancement — ComfyUI workflows

Image upscaling only: GAN / transformer upscale models, SeedVR2, tiled-diffusion and creative upscalers, diffusion super-resolution (SUPIR, CCSR, StableSR, DiffBIR) and paid API upscalers.

[← 01-Image overview](../README.md) · [Library index](../../00-LIBRARY-INDEX.md)

**32 workflows** in **12 model folders**. Each model folder holds only workflow files; the file name says the task first, then the variant: `<task>[-<variant>][-<size>][-<precision>][-<feature>].json`. `Other/` holds generic or multi-model workflows.

## Model folders

| Model | Workflows | Tasks |
|---|---|---|
| [CCSR](#ccsr) | 1 | `upscale` |
| [DiffBIR](#diffbir) | 1 | `upscale` |
| [FLUX-1](#flux-1) | 1 | `upscale` |
| [MOSS-Image](#moss-image) | 2 | `upscale` |
| [P-H3](#p-h3) | 1 | `upscale` |
| [Paid-API](#paid-api) | 3 | `upscale` |
| [Real-ESRGAN](#real-esrgan) | 4 | `upscale` |
| [SeedVR2](#seedvr2) | 4 | `upscale` |
| [StableSR](#stablesr) | 3 | `upscale` |
| [SUPIR](#supir) | 2 | `upscale` |
| [Z-Image](#z-image) | 1 | `upscale` |
| [Other](#other) | 9 | `upscale` |

## CCSR

Folder: [`CCSR/`](CCSR) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-tiled](CCSR/upscale-tiled.json) | Consistent tiled SR, optional SDXL refine | [real-world_ccsr.ckpt](https://huggingface.co/camenduru/CCSR) | ComfyUI-CCSR, KJNodes, ComfyUI-Advanced-ControlNet, ComfyUI-TiledDiffusion, ComfyUI_essentials, rgthree-comfy | Model: CCSR real-world; Source: [kijai example](https://github.com/kijai/ComfyUI-CCSR/tree/main/examples); Licence: Apache-2.0 code; SD terms |

## DiffBIR

Folder: [`DiffBIR/`](DiffBIR) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-blind-super-resolution](DiffBIR/upscale-blind-super-resolution.json) | Blind SR | [lxq007/DiffBIR-v2](https://huggingface.co/lxq007/DiffBIR-v2) + table in node README | ComfyUI-DiffBIR | Model: DiffBIR v2; Source: [jtscmw01 example](https://github.com/jtscmw01/ComfyUI-DiffBIR/tree/main/example_workflows); Licence: Apache-2.0 |

## FLUX-1

Folder: [`FLUX-1/`](FLUX-1) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-nunchaku-fluxmania-tiled-diffusion](FLUX-1/upscale-nunchaku-fluxmania-tiled-diffusion.json) | Fluxmania — Tiled Diffusion Upscaler | `t5-v1_1-xxl-encoder-Q8_0.gguf`, `clip_l.safetensors`, `ae.safetensors` +2 more | ComfyUI-GGUF, ComfyUI-nunchaku, rgthree-comfy, comfyui-yaser-nodes | — |

## MOSS-Image

Folder: [`MOSS-Image/`](MOSS-Image) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-2x-keep-picture](MOSS-Image/upscale-2x-keep-picture.json) | MOSS Image - Upscale 2x, Keep the Picture (Ep40) | `moss_image_sft_int8_convrot.safetensors`, `qwen3.5_9b_w4a8_gptq.safetensors`, `flux2-vae_small.safetensors` | ComfyUI-Pixaroma | — |
| [upscale-picture](MOSS-Image/upscale-picture.json) | MOSS Image - Upscale a Picture (Ep40) | `moss_image_sft_int8_convrot.safetensors`, `qwen3.5_9b_w4a8_gptq.safetensors`, `flux2-vae_small.safetensors`, `4x_NMKD-Siax_200k.pth` | ComfyUI-Pixaroma | — |

## P-H3

Folder: [`P-H3/`](P-H3) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-creative](P-H3/upscale-creative.json) | P-H3 Image - Creative Upscale (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma | — |

## Paid-API

Folder: [`Paid-API/`](Paid-API) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-nano-banana-pro](Paid-API/upscale-nano-banana-pro.json) | Nano Banana Pro — Upscale | — | rgthree-comfy | — |
| [upscale-recraft-creative](Paid-API/upscale-recraft-creative.json) | Recraft — Creative Upscale | — | rgthree-comfy | — |
| [upscale-seedream-45](Paid-API/upscale-seedream-45.json) | SeeDream 4.5 — Upscale | — | rgthree-comfy | — |

## Real-ESRGAN

Folder: [`Real-ESRGAN/`](Real-ESRGAN) — 4 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-animevideo-v3-frame](Real-ESRGAN/upscale-animevideo-v3-frame.json) | Fast compact 4x for anime frames | [realesr-animevideov3.pth](https://github.com/xinntao/Real-ESRGAN/releases/download/v0.2.5.0/realesr-animevideov3.pth) | none | Model: Real-ESRGAN AnimeVideo-v3; Source: ComfyUI example (adapted); Licence: BSD-3-Clause |
| [upscale-x2-after-sd15-txt2img](Real-ESRGAN/upscale-x2-after-sd15-txt2img.json) | Generate, then 2x upscale (official example, unchanged) | [RealESRGAN_x2plus.pth](https://github.com/xinntao/Real-ESRGAN/releases/download/v0.2.1/RealESRGAN_x2plus.pth) (rename to `RealESRGAN_x2.pth` or reselect) | none | Model: SD 1.5 + Real-ESRGAN x2; Source: [ComfyUI example](https://comfyanonymous.github.io/ComfyUI_examples/upscale_models/); Licence: BSD-3-Clause; SD 1.5 CreativeML OpenRAIL-M |
| [upscale-x4plus-anime-6b](Real-ESRGAN/upscale-x4plus-anime-6b.json) | 4x anime / line art | [RealESRGAN_x4plus_anime_6B.pth](https://github.com/xinntao/Real-ESRGAN/releases/download/v0.2.2.4/RealESRGAN_x4plus_anime_6B.pth) | none | Model: Real-ESRGAN x4plus-anime-6B; Source: ComfyUI example (adapted); Licence: BSD-3-Clause |
| [upscale-x4plus](Real-ESRGAN/upscale-x4plus.json) | Faithful 4x photo upscale | [RealESRGAN_x4plus.pth](https://github.com/xinntao/Real-ESRGAN/releases/download/v0.1.0/RealESRGAN_x4plus.pth) | none | Model: Real-ESRGAN x4plus; Source: [ComfyUI example](https://comfyanonymous.github.io/ComfyUI_examples/upscale_models/) (adapted); Licence: BSD-3-Clause |

## SeedVR2

Folder: [`SeedVR2/`](SeedVR2) — 4 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-3b-fp8-simple-low-vram](SeedVR2/upscale-3b-fp8-simple-low-vram.json) | Low-VRAM upscale with the community node | [numz/SeedVR2_comfyUI](https://huggingface.co/numz/SeedVR2_comfyUI) | ComfyUI-SeedVR2_VideoUpscaler | Model: SeedVR2 3B fp8; Source: [numz example](https://github.com/numz/ComfyUI-SeedVR2_VideoUpscaler/tree/main/example_workflows); Licence: Apache-2.0 |
| [upscale-3b-int8-native-low-vram](SeedVR2/upscale-3b-int8-native-low-vram.json) | Low-VRAM one-step restore/upscale | [Comfy-Org/SeedVR2](https://huggingface.co/Comfy-Org/SeedVR2) | none (recent ComfyUI) | Model: SeedVR2 3B int8 (native nodes); Source: [Comfy-Org template](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/utility_seedvr2_3b_int8_upscale_image.json); Licence: Apache-2.0 |
| [upscale-7b-int8-native](SeedVR2/upscale-7b-int8-native.json) | Higher-quality restore/upscale | [Comfy-Org/SeedVR2](https://huggingface.co/Comfy-Org/SeedVR2) | none (recent ComfyUI) | Model: SeedVR2 7B int8 (native nodes); Source: [Comfy-Org template](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/utility_seedvr2_7b_int8_upscale_image.json); Licence: Apache-2.0 |
| [upscale](SeedVR2/upscale.json) | Upscale | `ema_vae_fp16.safetensors`, `seedvr2_ema_7b_fp8_e4m3fn_mixed_block35_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler, rgthree-comfy | — |

## StableSR

Folder: [`StableSR/`](StableSR) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-color-fix](StableSR/upscale-color-fix.json) | SD 2.1 SR with colour fix | [Iceclear/StableSR](https://huggingface.co/Iceclear/StableSR) | Comfyui-StableSR | Model: StableSR 768v; Source: [gameltb example](https://github.com/gameltb/Comfyui-StableSR/tree/main/examples); Licence: S-Lab licence (non-commercial) |
| [upscale-sd-turbo-fast](StableSR/upscale-sd-turbo-fast.json) | Fast few-step SR with ToDo | Iceclear/StableSR, [sd-turbo](https://huggingface.co/stabilityai/sd-turbo) | Comfyui-StableSR, [comfy-todo](https://github.com/ethansmith2000/comfy-todo) | Model: StableSR + SD-Turbo; Source: gameltb example; Licence: S-Lab; SD-Turbo non-commercial |
| [upscale-ultimate-sd-tiled](StableSR/upscale-ultimate-sd-tiled.json) | Tiled large-image SR | Iceclear/StableSR | Comfyui-StableSR, ComfyUI_UltimateSDUpscale | Model: StableSR 768v; Source: gameltb example; Licence: S-Lab licence (non-commercial) |

## SUPIR

Folder: [`SUPIR/`](SUPIR) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-lightning-sdxl-restore](SUPIR/upscale-lightning-sdxl-restore.json) | Restore/upscale (kijai nodes) | [Kijai/SUPIR_pruned](https://huggingface.co/Kijai/SUPIR_pruned) | ComfyUI-SUPIR, KJNodes, ComfyUI_essentials, rgthree-comfy | Model: SUPIR v0F + Juggernaut XL Lightning; Source: [kijai example](https://github.com/kijai/ComfyUI-SUPIR/tree/main/example_workflows); Licence: SUPIR non-commercial terms |
| [upscale-native-auto-caption](SUPIR/upscale-native-auto-caption.json) | Photoreal restore/upscale, Qwen3.5 auto-caption | SUPIR-v0Q_fp16 and links in the workflow note | none (recent ComfyUI) | Model: SUPIR v0Q + SDXL Lightning; Source: [Comfy-Org template](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/utility_image_upscale_supir.json); Licence: SUPIR non-commercial terms |

## Z-Image

Folder: [`Z-Image/`](Z-Image) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-turbo-tiled-diffusion](Z-Image/upscale-turbo-tiled-diffusion.json) | Tiled Diffusion Upscaler | `4x_NMKD-Siax_200k.pth`, `ae.safetensors`, `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors` +1 more | rgthree-comfy, comfyui-yaser-nodes | — |

## Other

Folder: [`Other/`](Other) — 9 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-4x-ultrasharp](Other/upscale-4x-ultrasharp.json) | Sharp community 4x | [4x-UltraSharp.pth](https://huggingface.co/lokCX/4x-Ultrasharp/resolve/main/4x-UltraSharp.pth) | none | Model: 4x-UltraSharp (ESRGAN fine-tune); Source: ComfyUI example (adapted); Licence: Community; verify author terms |
| [upscale-bsrgan-x4-blind](Other/upscale-bsrgan-x4-blind.json) | Blind 4x for real degraded photos | [BSRGAN.pth](https://github.com/cszn/KAIR/releases/download/v1.0/BSRGAN.pth) | none | Model: BSRGAN; Source: ComfyUI example (adapted); Licence: Apache-2.0 |
| [upscale-dat-x4](Other/upscale-dat-x4.json) | Transformer 4x | [DAT weights](https://github.com/zhengchen1999/DAT#testing) | none | Model: DAT x4; Source: ComfyUI example (adapted); Licence: Apache-2.0 |
| [upscale-esrgan-rrdb-x4-legacy](Other/upscale-esrgan-rrdb-x4-legacy.json) | Legacy 4x baseline | [RRDB_ESRGAN_x4.pth](https://github.com/xinntao/ESRGAN#test-models) | none | Model: ESRGAN (RRDB); Source: ComfyUI example (adapted); Licence: Apache-2.0 |
| [upscale-hat-real-gan-x4](Other/upscale-hat-real-gan-x4.json) | Transformer 4x, fine detail | [HAT weights](https://github.com/XPixelGroup/HAT#how-to-test) | none | Model: HAT (Real_HAT_GAN_SRx4); Source: ComfyUI example (adapted); Licence: Apache-2.0 |
| [upscale-srformer-x4](Other/upscale-srformer-x4.json) | Transformer 4x | [SRFormer weights](https://github.com/HVision-NKU/SRFormer#pretrain-models) | spandrel_extra_arches (pip) | Model: SRFormer x4 ⁺; Source: ComfyUI example (adapted); Licence: Check repo; non-commercial arch |
| [upscale-swinir-l-realsr-x4-gan](Other/upscale-swinir-l-realsr-x4-gan.json) | Transformer 4x for real photos | [SwinIR v0.0 release](https://github.com/JingyunLiang/SwinIR/releases/tag/v0.0) | none | Model: SwinIR-L real-world x4; Source: ComfyUI example (adapted); Licence: Apache-2.0 |
| [upscale-universal-4x-nmkd-siax](Other/upscale-universal-4x-nmkd-siax.json) | Upscale with 4x Model (NMKD-Siax) | `4x_NMKD-Siax_200k.pth` | rgthree-comfy | — |
| [upscale-universal-no-model](Other/upscale-universal-no-model.json) | Upscale Simple (No Model) | — | rgthree-comfy | — |

## Notes carried over from the previous folder layout

Setup notes, licences, test results and "not available in ComfyUI" lists from the former task-folder READMEs. Links point to the new locations.

### From the former "Image Upscaling and Enhancement" README

Image upscaling (SeedVR2, tiled diffusion, GAN and transformer upscale models, paid API upscalers), diffusion restoration (SUPIR, CCSR, StableSR, DiffBIR), face restoration, denoise / deblur / low-light, colorization, and filters / color grading.

None of the workflows added from the Open-Source Image Model Atlas (everything below except the original 13) has been runtime-tested: each was only checked to be valid JSON, a real ComfyUI graph, and right for its model and task. Licences are as published upstream; check the model card before commercial use. Model files go in the usual ComfyUI `models/` subfolder (`upscale_models` for the 1x/2x/4x restoration models).

The "Upscale model" workflows use the upscale branch of the official ComfyUI [upscale_models example](https://comfyanonymous.github.io/ComfyUI_examples/upscale_models/) (Load Upscale Model → Upscale Image (using Model)) fed by Load Image, with the checkpoint set for that model. Core ComfyUI loads these through [spandrel](https://github.com/chaiNNer-org/spandrel); architectures marked ⁺ also need `pip install spandrel_extra_arches`, which covers non-commercial architectures.

##### Atlas entries with no workflow added

Duplicates skipped: SeedVR2 7B through the numz node already exists as `5-seedvr2-upscale`, so the Comfy-Org `utility_seedvr2_image_upscale` template and numz `SeedVR2_4K_image_upscale` were not added.

Not available in ComfyUI (no authentic, maintained ComfyUI workflow found; not fabricated):

- **ResShift**: only unmaintained node packs without example workflows.
- **SeeSR**, **PASD**, **SinSR**: no ComfyUI node or workflow found.
- **RestoreFormer / RestoreFormer++**: ReActor loads `RestoreFormer_PP.onnx` as a face-restore option, but no standalone published workflow was found.
- **DeOldify**: no maintained ComfyUI node or workflow found.
- **Zero-DCE**: no ComfyUI node or workflow found.

See the [01-Image overview](../README.md) for the other categories, the [main README](../../README.md) for setup, or [`00-LIBRARY-INDEX.md`](../../00-LIBRARY-INDEX.md) for the full list.
