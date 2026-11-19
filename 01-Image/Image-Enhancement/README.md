# Image Upscaling and Enhancement — ComfyUI workflows

Image upscaling (SeedVR2, tiled diffusion, GAN and transformer upscale models, paid API upscalers), diffusion restoration (SUPIR, CCSR, StableSR, DiffBIR), face restoration, denoise / deblur / low-light, colorization, and filters / color grading.

| Subfolder | What is inside | Workflows |
|---|---|---|
| [`Colorization/`](Colorization) | Black-and-white photo colorization | 1 |
| [`Denoise-Deblur-and-Low-Light/`](Denoise-Deblur-and-Low-Light) | 1x restoration models: denoise, deblur, low-light | 4 |
| [`Diffusion-Restoration/`](Diffusion-Restoration) | Diffusion-based restoration and super-resolution | 9 |
| [`Face-Restoration/`](Face-Restoration) | Face restoration | 3 |
| [`Filters-and-Color-Grading/`](Filters-and-Color-Grading) | Filters and color grading | 2 |
| [`Upscaling/`](Upscaling) | Image upscaling | 25 |

## Workflows (44)

None of the workflows added from the Open-Source Image Model Atlas (everything below except the original 13) has been runtime-tested: each was only checked to be valid JSON, a real ComfyUI graph, and right for its model and task. Licences are as published upstream; check the model card before commercial use. Model files go in the usual ComfyUI `models/` subfolder (`upscale_models` for the 1x/2x/4x restoration models).

The "Upscale model" workflows use the upscale branch of the official ComfyUI [upscale_models example](https://comfyanonymous.github.io/ComfyUI_examples/upscale_models/) (Load Upscale Model → Upscale Image (using Model)) fed by Load Image, with the checkpoint set for that model. Core ComfyUI loads these through [spandrel](https://github.com/chaiNNer-org/spandrel); architectures marked ⁺ also need `pip install spandrel_extra_arches`, which covers non-commercial architectures.

### Filters and color grading

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [layerstyle-image-filters-and-color-adjustments](Filters-and-Color-Grading/layerstyle-image-filters-and-color-adjustments.json) | Image Filters and Color Adjustments | — | ComfyUI_LayerStyle, rgthree-comfy |
| [utility-image-filters-example](Filters-and-Color-Grading/utility-image-filters-example.json) | Image Filters Example | — | ComfyUI-RMBG, ComfyUI_LayerStyle, rgthree-comfy |

### Image upscaling

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [1-universal-upscale-simple-no-model](Upscaling/1-universal-upscale-simple-no-model.json) | Upscale Simple (No Model) | — | rgthree-comfy |
| [2-universal-upscale-with-4x-model-nmkd-siax](Upscaling/2-universal-upscale-with-4x-model-nmkd-siax.json) | Upscale with 4x Model (NMKD-Siax) | `4x_NMKD-Siax_200k.pth` | rgthree-comfy |
| [3-z-image-turbo-tiled-diffusion-upscaler](Upscaling/3-z-image-turbo-tiled-diffusion-upscaler.json) | Tiled Diffusion Upscaler | `4x_NMKD-Siax_200k.pth`, `ae.safetensors`, `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors` +1 more | rgthree-comfy, comfyui-yaser-nodes |
| [4-nunchaku-fluxmania-tiled-diffusion-upscaler](Upscaling/4-nunchaku-fluxmania-tiled-diffusion-upscaler.json) | Fluxmania — Tiled Diffusion Upscaler | `t5-v1_1-xxl-encoder-Q8_0.gguf`, `clip_l.safetensors`, `ae.safetensors` +2 more | ComfyUI-GGUF, ComfyUI-nunchaku, rgthree-comfy, comfyui-yaser-nodes |
| [5-seedvr2-upscale](Upscaling/5-seedvr2-upscale.json) | Upscale | `ema_vae_fp16.safetensors`, `seedvr2_ema_7b_fp8_e4m3fn_mixed_block35_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler, rgthree-comfy |
| [6-paid-api-51-credits-nano-banana-pro-upscale](Upscaling/6-paid-api-51-credits-nano-banana-pro-upscale.json) | Nano Banana Pro — Upscale | — | rgthree-comfy |
| [7-paid-api-53-credits-recraft-creative-upscale](Upscaling/7-paid-api-53-credits-recraft-creative-upscale.json) | Recraft — Creative Upscale | — | rgthree-comfy |
| [8-paid-api-8.5-credits-seedream-4.5-upscale](Upscaling/8-paid-api-8.5-credits-seedream-4.5-upscale.json) | SeeDream 4.5 — Upscale | — | rgthree-comfy |
| [moss-image-upscale-2x-keep-picture](Upscaling/moss-image-upscale-2x-keep-picture.json) | MOSS Image - Upscale 2x, Keep the Picture (Ep40) | `moss_image_sft_int8_convrot.safetensors`, `qwen3.5_9b_w4a8_gptq.safetensors`, `flux2-vae_small.safetensors` | ComfyUI-Pixaroma |
| [moss-image-upscale-picture](Upscaling/moss-image-upscale-picture.json) | MOSS Image - Upscale a Picture (Ep40) | `moss_image_sft_int8_convrot.safetensors`, `qwen3.5_9b_w4a8_gptq.safetensors`, `flux2-vae_small.safetensors`, `4x_NMKD-Siax_200k.pth` | ComfyUI-Pixaroma |
| [p-h3-image-creative-upscale](Upscaling/p-h3-image-creative-upscale.json) | P-H3 Image - Creative Upscale (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |

### Added from the Open-Source Image Model Atlas (not runtime-tested)

#### Upscaling — upscale models and SeedVR2

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence |
|---|---|---|---|---|---|---|
| [real-esrgan-x4plus-image-upscale](Upscaling/real-esrgan-x4plus-image-upscale.json) | Real-ESRGAN x4plus | Faithful 4x photo upscale | [ComfyUI example](https://comfyanonymous.github.io/ComfyUI_examples/upscale_models/) (adapted) | [RealESRGAN_x4plus.pth](https://github.com/xinntao/Real-ESRGAN/releases/download/v0.1.0/RealESRGAN_x4plus.pth) | none | BSD-3-Clause |
| [real-esrgan-x4plus-anime-6b-image-upscale](Upscaling/real-esrgan-x4plus-anime-6b-image-upscale.json) | Real-ESRGAN x4plus-anime-6B | 4x anime / line art | ComfyUI example (adapted) | [RealESRGAN_x4plus_anime_6B.pth](https://github.com/xinntao/Real-ESRGAN/releases/download/v0.2.2.4/RealESRGAN_x4plus_anime_6B.pth) | none | BSD-3-Clause |
| [real-esrgan-animevideo-v3-frame-upscale](Upscaling/real-esrgan-animevideo-v3-frame-upscale.json) | Real-ESRGAN AnimeVideo-v3 | Fast compact 4x for anime frames | ComfyUI example (adapted) | [realesr-animevideov3.pth](https://github.com/xinntao/Real-ESRGAN/releases/download/v0.2.5.0/realesr-animevideov3.pth) | none | BSD-3-Clause |
| [esrgan-rrdb-x4-legacy-upscale](Upscaling/esrgan-rrdb-x4-legacy-upscale.json) | ESRGAN (RRDB) | Legacy 4x baseline | ComfyUI example (adapted) | [RRDB_ESRGAN_x4.pth](https://github.com/xinntao/ESRGAN#test-models) | none | Apache-2.0 |
| [swinir-l-realsr-x4-gan-upscale](Upscaling/swinir-l-realsr-x4-gan-upscale.json) | SwinIR-L real-world x4 | Transformer 4x for real photos | ComfyUI example (adapted) | [SwinIR v0.0 release](https://github.com/JingyunLiang/SwinIR/releases/tag/v0.0) | none | Apache-2.0 |
| [hat-real-gan-x4-upscale](Upscaling/hat-real-gan-x4-upscale.json) | HAT (Real_HAT_GAN_SRx4) | Transformer 4x, fine detail | ComfyUI example (adapted) | [HAT weights](https://github.com/XPixelGroup/HAT#how-to-test) | none | Apache-2.0 |
| [dat-x4-upscale](Upscaling/dat-x4-upscale.json) | DAT x4 | Transformer 4x | ComfyUI example (adapted) | [DAT weights](https://github.com/zhengchen1999/DAT#testing) | none | Apache-2.0 |
| [srformer-x4-upscale](Upscaling/srformer-x4-upscale.json) | SRFormer x4 ⁺ | Transformer 4x | ComfyUI example (adapted) | [SRFormer weights](https://github.com/HVision-NKU/SRFormer#pretrain-models) | spandrel_extra_arches (pip) | Check repo; non-commercial arch |
| [bsrgan-x4-blind-upscale](Upscaling/bsrgan-x4-blind-upscale.json) | BSRGAN | Blind 4x for real degraded photos | ComfyUI example (adapted) | [BSRGAN.pth](https://github.com/cszn/KAIR/releases/download/v1.0/BSRGAN.pth) | none | Apache-2.0 |
| [4x-ultrasharp-upscale](Upscaling/4x-ultrasharp-upscale.json) | 4x-UltraSharp (ESRGAN fine-tune) | Sharp community 4x | ComfyUI example (adapted) | [4x-UltraSharp.pth](https://huggingface.co/lokCX/4x-Ultrasharp/resolve/main/4x-UltraSharp.pth) | none | Community; verify author terms |
| [official-sd15-txt2img-then-real-esrgan-x2-upscale](Upscaling/official-sd15-txt2img-then-real-esrgan-x2-upscale.json) | SD 1.5 + Real-ESRGAN x2 | Generate, then 2x upscale (official example, unchanged) | [ComfyUI example](https://comfyanonymous.github.io/ComfyUI_examples/upscale_models/) | [RealESRGAN_x2plus.pth](https://github.com/xinntao/Real-ESRGAN/releases/download/v0.2.1/RealESRGAN_x2plus.pth) (rename to `RealESRGAN_x2.pth` or reselect) | none | BSD-3-Clause; SD 1.5 CreativeML OpenRAIL-M |
| [official-seedvr2-3b-int8-native-image-upscale-low-vram](Upscaling/official-seedvr2-3b-int8-native-image-upscale-low-vram.json) | SeedVR2 3B int8 (native nodes) | Low-VRAM one-step restore/upscale | [Comfy-Org template](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/utility_seedvr2_3b_int8_upscale_image.json) | [Comfy-Org/SeedVR2](https://huggingface.co/Comfy-Org/SeedVR2) | none (recent ComfyUI) | Apache-2.0 |
| [official-seedvr2-7b-int8-native-image-upscale](Upscaling/official-seedvr2-7b-int8-native-image-upscale.json) | SeedVR2 7B int8 (native nodes) | Higher-quality restore/upscale | [Comfy-Org template](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/utility_seedvr2_7b_int8_upscale_image.json) | [Comfy-Org/SeedVR2](https://huggingface.co/Comfy-Org/SeedVR2) | none (recent ComfyUI) | Apache-2.0 |
| [seedvr2-3b-fp8-simple-image-upscale-low-vram](Upscaling/seedvr2-3b-fp8-simple-image-upscale-low-vram.json) | SeedVR2 3B fp8 | Low-VRAM upscale with the community node | [numz example](https://github.com/numz/ComfyUI-SeedVR2_VideoUpscaler/tree/main/example_workflows) | [numz/SeedVR2_comfyUI](https://huggingface.co/numz/SeedVR2_comfyUI) | ComfyUI-SeedVR2_VideoUpscaler | Apache-2.0 |

#### Diffusion restoration

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence |
|---|---|---|---|---|---|---|
| [official-supir-native-image-upscale-auto-caption](Diffusion-Restoration/official-supir-native-image-upscale-auto-caption.json) | SUPIR v0Q + SDXL Lightning | Photoreal restore/upscale, Qwen3.5 auto-caption | [Comfy-Org template](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/utility_image_upscale_supir.json) | SUPIR-v0Q_fp16 and links in the workflow note | none (recent ComfyUI) | SUPIR non-commercial terms |
| [supir-lightning-sdxl-restore-upscale](Diffusion-Restoration/supir-lightning-sdxl-restore-upscale.json) | SUPIR v0F + Juggernaut XL Lightning | Restore/upscale (kijai nodes) | [kijai example](https://github.com/kijai/ComfyUI-SUPIR/tree/main/example_workflows) | [Kijai/SUPIR_pruned](https://huggingface.co/Kijai/SUPIR_pruned) | ComfyUI-SUPIR, KJNodes, ComfyUI_essentials, rgthree-comfy | SUPIR non-commercial terms |
| [ccsr-tiled-upscale](Diffusion-Restoration/ccsr-tiled-upscale.json) | CCSR real-world | Consistent tiled SR, optional SDXL refine | [kijai example](https://github.com/kijai/ComfyUI-CCSR/tree/main/examples) | [real-world_ccsr.ckpt](https://huggingface.co/camenduru/CCSR) | ComfyUI-CCSR, KJNodes, ComfyUI-Advanced-ControlNet, ComfyUI-TiledDiffusion, ComfyUI_essentials, rgthree-comfy | Apache-2.0 code; SD terms |
| [stablesr-upscale-color-fix](Diffusion-Restoration/stablesr-upscale-color-fix.json) | StableSR 768v | SD 2.1 SR with colour fix | [gameltb example](https://github.com/gameltb/Comfyui-StableSR/tree/main/examples) | [Iceclear/StableSR](https://huggingface.co/Iceclear/StableSR) | Comfyui-StableSR | S-Lab licence (non-commercial) |
| [stablesr-ultimate-sd-upscale-tiled](Diffusion-Restoration/stablesr-ultimate-sd-upscale-tiled.json) | StableSR 768v | Tiled large-image SR | gameltb example | Iceclear/StableSR | Comfyui-StableSR, ComfyUI_UltimateSDUpscale | S-Lab licence (non-commercial) |
| [stablesr-sd-turbo-fast-upscale](Diffusion-Restoration/stablesr-sd-turbo-fast-upscale.json) | StableSR + SD-Turbo | Fast few-step SR with ToDo | gameltb example | Iceclear/StableSR, [sd-turbo](https://huggingface.co/stabilityai/sd-turbo) | Comfyui-StableSR, [comfy-todo](https://github.com/ethansmith2000/comfy-todo) | S-Lab; SD-Turbo non-commercial |
| [diffbir-blind-super-resolution](Diffusion-Restoration/diffbir-blind-super-resolution.json) | DiffBIR v2 | Blind SR | [jtscmw01 example](https://github.com/jtscmw01/ComfyUI-DiffBIR/tree/main/example_workflows) | [lxq007/DiffBIR-v2](https://huggingface.co/lxq007/DiffBIR-v2) + table in node README | ComfyUI-DiffBIR | Apache-2.0 |
| [diffbir-blind-face-restoration](Diffusion-Restoration/diffbir-blind-face-restoration.json) | DiffBIR v2 | Blind face restoration | jtscmw01 example | DiffBIR-v2 + face_swinir_v1 | ComfyUI-DiffBIR | Apache-2.0 |
| [diffbir-blind-image-denoise](Diffusion-Restoration/diffbir-blind-image-denoise.json) | DiffBIR v2 | Blind denoise | jtscmw01 example | DiffBIR-v2 + scunet_color_real_psnr | ComfyUI-DiffBIR | Apache-2.0 |

#### Face restoration

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence |
|---|---|---|---|---|---|---|
| [codeformer-face-restore](Face-Restoration/codeformer-face-restore.json) | CodeFormer | Detect and restore faces, fidelity slider | [AI Horde hordelib pipeline](https://github.com/Haidra-Org/hordelib/blob/main/hordelib/pipeline_designs/pipeline_image_facefix.json) (model file renamed to `codeformer.pth`) | [codeformer.pth](https://github.com/sczhou/CodeFormer/releases/download/v0.1.0/codeformer.pth) | facerestore_cf | S-Lab licence (non-commercial) |
| [gfpgan-v1.4-face-restore](Face-Restoration/gfpgan-v1.4-face-restore.json) | GFPGAN v1.4 | Detect and restore faces | Same pipeline, model set to GFPGAN | [GFPGANv1.4.pth](https://github.com/TencentARC/GFPGAN/releases/download/v1.3.0/GFPGANv1.4.pth) | facerestore_cf | Apache-2.0 (see repo for bundled parts) |
| [gpen-bfr-512-face-swap-and-restore](Face-Restoration/gpen-bfr-512-face-swap-and-restore.json) | GPEN-BFR-512 | ReActor face swap, then GPEN restore | [GPENO example](https://github.com/SparknightLLC/ComfyUI-GPENO/tree/main/workflows) | [GPEN-BFR-512.onnx](https://huggingface.co/datasets/Gourieff/ReActor/resolve/main/models/facerestore_models/GPEN-BFR-512.onnx) | ComfyUI-GPENO, ComfyUI-ReActor | GPEN non-commercial; inswapper non-commercial |

#### Denoise, deblur and low-light

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence |
|---|---|---|---|---|---|---|
| [scunet-real-denoise-1x](Denoise-Deblur-and-Low-Light/scunet-real-denoise-1x.json) | SCUNet | Blind real-photo denoise | ComfyUI example (adapted) | [scunet_color_real_psnr.pth](https://github.com/cszn/KAIR/releases/download/v1.0/scunet_color_real_psnr.pth) | none | Apache-2.0 |
| [nafnet-sidd-denoise-1x](Denoise-Deblur-and-Low-Light/nafnet-sidd-denoise-1x.json) | NAFNet (SIDD; GoPro for deblur) | Denoise / deblur | ComfyUI example (adapted) | [NAFNet weights](https://github.com/megvii-research/NAFNet#results-and-pre-trained-models) | none | See repo |
| [restormer-real-denoise-1x](Denoise-Deblur-and-Low-Light/restormer-real-denoise-1x.json) | Restormer ⁺ | Denoise (deblur / derain checkpoints too) | ComfyUI example (adapted) | [Restormer v1.0 release](https://github.com/swz30/Restormer/releases/tag/v1.0) | spandrel_extra_arches (pip) | Code MIT; non-commercial arch in spandrel |
| [retinexformer-low-light-enhance-1x](Denoise-Deblur-and-Low-Light/retinexformer-low-light-enhance-1x.json) | Retinexformer (LOL-v2-real) | Low-light enhancement | ComfyUI example (adapted) | [CaiYuanhao/Retinexformer](https://huggingface.co/CaiYuanhao/Retinexformer) | none | MIT |

#### Colorization

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence |
|---|---|---|---|---|---|---|
| [ddcolor-colorize-black-and-white-photo](Colorization/ddcolor-colorize-black-and-white-photo.json) | DDColor (artistic; paper / modelscope / tiny selectable) | Colorize B&W photos (API-format graph) | [Intel AI Playground preset](https://github.com/intel/AI-Playground/blob/main/modes/base/presets/Colorize.json) | [piddnad/ddcolor_artistic](https://huggingface.co/piddnad/ddcolor_artistic) | ComfyUI-DDColor | Apache-2.0 |

### Atlas entries with no workflow added

Duplicates skipped: SeedVR2 7B through the numz node already exists as `5-seedvr2-upscale`, so the Comfy-Org `utility_seedvr2_image_upscale` template and numz `SeedVR2_4K_image_upscale` were not added.

Not available in ComfyUI (no authentic, maintained ComfyUI workflow found; not fabricated):

- **ResShift**: only unmaintained node packs without example workflows.
- **SeeSR**, **PASD**, **SinSR**: no ComfyUI node or workflow found.
- **RestoreFormer / RestoreFormer++**: ReActor loads `RestoreFormer_PP.onnx` as a face-restore option, but no standalone published workflow was found.
- **DeOldify**: no maintained ComfyUI node or workflow found.
- **Zero-DCE**: no ComfyUI node or workflow found.

See the [main README](../../README.md) for setup steps, requirements and the other categories, or [`00-LIBRARY-INDEX.md`](../../00-LIBRARY-INDEX.md) for the full list of workflows.
