# Image Upscaling and Enhancement — ComfyUI workflows

Image upscaling (SeedVR2, tiled diffusion, 4x ESRGAN-style models, paid API upscalers) and filters / color grading.

| Subfolder | What is inside | Workflows |
|---|---|---|
| [`Filters-and-Color-Grading/`](Filters-and-Color-Grading) | Filters and color grading | 2 |
| [`Upscaling/`](Upscaling) | Image upscaling | 8 |

## Workflows (10)

### Filters and color grading

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [layerstyle-image-filters-and-color-adjustments](Filters-and-Color-Grading/layerstyle-image-filters-and-color-adjustments.json) | Image Filters and Color Adjustments | ComfyUI_LayerStyle, rgthree-comfy |
| [utility-image-filters-example](Filters-and-Color-Grading/utility-image-filters-example.json) | Image Filters Example | ComfyUI-RMBG, ComfyUI_LayerStyle, rgthree-comfy |

### Image upscaling

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [1-universal-upscale-simple-no-model](Upscaling/1-universal-upscale-simple-no-model.json) | Upscale Simple (No Model) | rgthree-comfy |
| [2-universal-upscale-with-4x-model-nmkd-siax](Upscaling/2-universal-upscale-with-4x-model-nmkd-siax.json) | Upscale with 4x Model (NMKD-Siax) | rgthree-comfy |
| [3-z-image-turbo-tiled-diffusion-upscaler](Upscaling/3-z-image-turbo-tiled-diffusion-upscaler.json) | Tiled Diffusion Upscaler | rgthree-comfy, comfyui-yaser-nodes |
| [4-nunchaku-fluxmania-tiled-diffusion-upscaler](Upscaling/4-nunchaku-fluxmania-tiled-diffusion-upscaler.json) | Fluxmania — Tiled Diffusion Upscaler | ComfyUI-GGUF, ComfyUI-nunchaku, rgthree-comfy, comfyui-yaser-nodes |
| [5-seedvr2-upscale](Upscaling/5-seedvr2-upscale.json) | Upscale | ComfyUI-SeedVR2_VideoUpscaler, rgthree-comfy |
| [6-paid-api-51-credits-nano-banana-pro-upscale](Upscaling/6-paid-api-51-credits-nano-banana-pro-upscale.json) | Nano Banana Pro — Upscale | rgthree-comfy |
| [7-paid-api-53-credits-recraft-creative-upscale](Upscaling/7-paid-api-53-credits-recraft-creative-upscale.json) | Recraft — Creative Upscale | rgthree-comfy |
| [8-paid-api-8.5-credits-seedream-4.5-upscale](Upscaling/8-paid-api-8.5-credits-seedream-4.5-upscale.json) | SeeDream 4.5 — Upscale | rgthree-comfy |

See the [main README](../README.md) for models used, setup steps and the full catalog.
