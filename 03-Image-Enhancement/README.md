# Image Upscaling and Enhancement — ComfyUI workflows

Image upscaling (SeedVR2, tiled diffusion, 4x ESRGAN-style models, paid API upscalers) and filters / color grading.

| Subfolder | What is inside | Workflows |
|---|---|---|
| [`Filters-and-Color-Grading/`](Filters-and-Color-Grading) | Filters and color grading | 2 |
| [`Upscaling/`](Upscaling) | Image upscaling | 11 |

## Workflows (13)

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

See the [main README](../README.md) for setup steps, requirements and the other categories, or [`00-LIBRARY-INDEX.md`](../00-LIBRARY-INDEX.md) for the full list of workflows.
