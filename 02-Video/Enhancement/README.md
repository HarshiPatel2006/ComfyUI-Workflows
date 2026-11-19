# Video Enhancement — ComfyUI workflows

Video upscaling, super-resolution and refinement, and frame interpolation.

[← 02-Video overview](../README.md) · [Library index](../../00-LIBRARY-INDEX.md)

**21 workflows** in **8 model folders**. Each model folder holds only workflow files; the file name says the task first, then the variant: `<task>[-<variant>][-<size>][-<precision>][-<feature>].json`. `Other/` holds generic or multi-model workflows.

## Model folders

| Model | Workflows | Tasks |
|---|---|---|
| [FILM](#film) | 2 | `frame-interpolation` |
| [FlashVSR](#flashvsr) | 1 | `upscale` |
| [GIMM-VFI](#gimm-vfi) | 1 | `frame-interpolation` |
| [MiniMax-H3](#minimax-h3) | 3 | `upscale` |
| [NVIDIA-RTX-VSR](#nvidia-rtx-vsr) | 1 | `upscale` |
| [RelayVSR](#relayvsr) | 1 | `upscale` |
| [SeedVR2](#seedvr2) | 11 | `upscale` |
| [Wan-2.2](#wan-22) | 1 | `upscale` |

## FILM

Folder: [`FILM/`](FILM) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [frame-interpolation-core-nodes](FILM/frame-interpolation-core-nodes.json) | FILM interpolation with built-in ComfyUI nodes (Frame Interpolation Model Loader → Frame Interpolate), keeps audio | [Comfy-Org/frame_interpolation](https://huggingface.co/Comfy-Org/frame_interpolation) | — (core ComfyUI) | Model: `film_net_fp16.safetensors`; Source: [Comfy-Org/workflow_templates `utility_video_frame_interpolation`](https://github.com/Comfy-Org/workflow_templates); Code licence: MIT; Weight licence: FILM: Apache-2.0 ([google-research/frame-interpolation](https://github.com/google-research/frame-interpolation)); Status: not runtime-tested |
| [frame-interpolation-vfi-node-pack](FILM/frame-interpolation-vfi-node-pack.json) | FILM interpolation with the ComfyUI-Frame-Interpolation pack; the same pack has drop-in RIFE, IFRNet, AMT, GMFSS Fortuna, CAIN and other VFI nodes | [Fannovel16/ComfyUI-Frame-Interpolation](https://github.com/Fannovel16/ComfyUI-Frame-Interpolation) (node pack MIT, downloads weights) | ComfyUI-Frame-Interpolation, ComfyUI-VideoHelperSuite | Model: `film_net_fp32.pt` (auto-downloaded by the node); Source: [Comfy-Org/workflow_templates `utility-frame_interpolation-film`](https://github.com/Comfy-Org/workflow_templates); Code licence: MIT; Weight licence: FILM: Apache-2.0; Status: not runtime-tested |

## FlashVSR

Folder: [`FlashVSR/`](FlashVSR) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-wan-13b](FlashVSR/upscale-wan-13b.json) | FlashVSR one-step streaming video super-resolution on Wan 2.1 1.3B | [Kijai/WanVideo_comfy `FlashVSR`](https://huggingface.co/Kijai/WanVideo_comfy), [JunhaoZhuang/FlashVSR](https://huggingface.co/JunhaoZhuang/FlashVSR) | ComfyUI-WanVideoWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite | Model: `Wan2_1-T2V-1_3B_FlashVSR_fp32.safetensors`, `Wan2_1_FlashVSR_LQ_proj_model_bf16.safetensors`, `Wan2_1_FlashVSR_TCDecoder_fp32.safetensors`, `umt5-xxl-enc-bf16.safetensors`; Source: [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/tree/main/example_workflows); Code licence: Apache-2.0; Weight licence: Apache-2.0; Status: not runtime-tested |

## GIMM-VFI

Folder: [`GIMM-VFI/`](GIMM-VFI) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [frame-interpolation](GIMM-VFI/frame-interpolation.json) | GIMM-VFI arbitrary-timestep interpolation (implicit motion modelling), output fps = input fps × factor | [Kijai/GIMM-VFI_safetensors](https://huggingface.co/Kijai/GIMM-VFI_safetensors) via [kijai/ComfyUI-GIMM-VFI](https://github.com/kijai/ComfyUI-GIMM-VFI) | ComfyUI-GIMM-VFI, ComfyUI-VideoHelperSuite | Model: `gimmvfi_r_arb_lpips_fp32.safetensors`; Source: [Comfy-Org/workflow_templates `utility_gimm_frame_interpolation`](https://github.com/Comfy-Org/workflow_templates); Code licence: MIT; Weight licence: **Not stated on the model page — unverified**; check [GSean/GIMM-VFI](https://github.com/GSean/GIMM-VFI) before commercial use; Status: not runtime-tested |

## MiniMax-H3

Folder: [`MiniMax-H3/`](MiniMax-H3) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-regenerate-lora-2k](MiniMax-H3/upscale-regenerate-lora-2k.json) | MiniMax H3 regenerate LoRA, remake a video at 2K (original) | MiniMax H3 ref2va int8, `minimax_h3_latent_upscaler_3d_conv_v1_fp16.safetensors` | ComfyUI-Pixaroma | — |
| [upscale-sharpen-lora-1080p](MiniMax-H3/upscale-sharpen-lora-1080p.json) | Minimax H3 - Sharpen LoRA + Upscale to Full HD (Ep41) | MiniMax H3 ref2va int8, `RealESRGAN_x2.pth` | ComfyUI-Pixaroma | — |
| [upscale-sharpener-refiner](MiniMax-H3/upscale-sharpener-refiner.json) | Video Upscale / Sharpen — load any video, re-render it through the H3 2K refiner LoRA (Pika pass-2 only) | `minimax_h3_fl2va_pruned_w6a8.safetensors`, `minimax_h3_open_regenerate_2k_refiner_rank_384_bf16.safetensors` | — (core ComfyUI) | — |

## NVIDIA-RTX-VSR

Folder: [`NVIDIA-RTX-VSR/`](NVIDIA-RTX-VSR) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-frame-gen-hdr](NVIDIA-RTX-VSR/upscale-frame-gen-hdr.json) | NVIDIA RTX Video: super-resolution, frame generation (2× fps) and TrueHDR in one local pass (RTX GPU required) | [Comfy-Org/Nvidia_RTX_Nodes_ComfyUI](https://github.com/Comfy-Org/Nvidia_RTX_Nodes_ComfyUI) (node pack Apache-2.0) | Nvidia_RTX_Nodes_ComfyUI | Model: — (NVIDIA driver / SDK); Source: [Comfy-Org/workflow_templates `utility_nvidia_rtx_video_enhance`](https://github.com/Comfy-Org/workflow_templates); Code licence: MIT; Weight licence: **NVIDIA RTX Video SDK terms (proprietary)**; Status: not runtime-tested |

## RelayVSR

Folder: [`RelayVSR/`](RelayVSR) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-4x](RelayVSR/upscale-4x.json) | RelayVSR 4× video super-resolution with built-in nodes (an x2 checkpoint also exists) | [Comfy-Org/RelayVSR](https://huggingface.co/Comfy-Org/RelayVSR) | — (core ComfyUI) | Model: `relayvsr_x4_int8_convrot.safetensors`, `relayvsr_flash_vae_x4_fp32.safetensors`; Source: [Comfy-Org/workflow_templates `utility_relayvsr_video_x4_upscale`](https://github.com/Comfy-Org/workflow_templates); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |

## SeedVR2

Folder: [`SeedVR2/`](SeedVR2) — 11 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-1080p-api](SeedVR2/upscale-1080p-api.json) | SeedVR2 7B video upscale of one clip to 1080p (API format) | `seedvr2_ema_7b_fp8_e4m3fn_mixed_block35_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler | — |
| [upscale-api](SeedVR2/upscale-api.json) | SeedVR2 7B video upscale (original) | `seedvr2_ema_7b_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler | — |
| [upscale-cartoon-dance-api](SeedVR2/upscale-cartoon-dance-api.json) | SeedVR2 7B video upscale run (cartoon dance clip) (API format) | `seedvr2_ema_7b_fp8_e4m3fn_mixed_block35_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler, ComfyUI-VideoHelperSuite | — |
| [upscale-cartoon-talk-api](SeedVR2/upscale-cartoon-talk-api.json) | SeedVR2 7B video upscale run (cartoon talk clip) (API format) | same | same | — |
| [upscale-curly-dance-api](SeedVR2/upscale-curly-dance-api.json) | SeedVR2 7B video upscale run (curly dance clip) (API format) | same | same | — |
| [upscale-curly-talk-api](SeedVR2/upscale-curly-talk-api.json) | SeedVR2 7B video upscale run (curly talk clip) (API format) | same | same | — |
| [upscale-duo-api](SeedVR2/upscale-duo-api.json) | SeedVR2 7B video upscale run (duo clip) (API format) | same | same | — |
| [upscale-hd](SeedVR2/upscale-hd.json) | SeedVR2 HD video upscale with torch compile and alpha (original) | `seedvr2_ema_3b_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler | — |
| [upscale-native-temporal-chunk](SeedVR2/upscale-native-temporal-chunk.json) | SeedVR2 3B with **built-in** ComfyUI SeedVR2 nodes, temporal chunking and merge for long clips, tiled VAE | [Comfy-Org/SeedVR2](https://huggingface.co/Comfy-Org/SeedVR2) | — (core ComfyUI) | Model: `seedvr2_3b_int8_convrot.safetensors`, `seedvr2_ema_vae_fp16.safetensors`; Source: [Comfy-Org/workflow_templates `utility_seedvr2_3b_int8_upscale_video`](https://github.com/Comfy-Org/workflow_templates); Code licence: MIT; Weight licence: Apache-2.0 ([ByteDance-Seed/SeedVR2-3B](https://huggingface.co/ByteDance-Seed/SeedVR2-3B)); Status: not runtime-tested |
| [upscale-toons-api](SeedVR2/upscale-toons-api.json) | SeedVR2 7B video upscale run (toons clip) (API format) | same | same | — |
| [upscale](SeedVR2/upscale.json) | SeedVR2 video upscale (original) | `seedvr2_ema_3b_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler, ComfyUI-VideoHelperSuite | — |

## Wan-2.2

Folder: [`Wan-2.2/`](Wan-2.2) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [upscale-refine](Wan-2.2/upscale-refine.json) | Wan 2.2 A14B low-noise video-to-video refine at a higher resolution (up to ~121 frames) | [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy), [Wan-AI/Wan2.2-T2V-A14B](https://huggingface.co/Wan-AI/Wan2.2-T2V-A14B) | ComfyUI-WanVideoWrapper, ComfyUI_essentials | Model: `Wan2_2-T2V-A14B-LOW_fp8_e4m3fn_scaled_KJ.safetensors`, lightx2v T2V LoRA, `wan_2.1_vae.safetensors`, `umt5_xxl_fp16.safetensors`; Source: [Comfy-Org/workflow_templates `utility_video_upscale`](https://github.com/Comfy-Org/workflow_templates); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |

## Notes carried over from the previous folder layout

Setup notes, licences, test results and "not available in ComfyUI" lists from the former task-folder READMEs. Links point to the new locations.

### From the former "Video Upscaling and Enhancement" README

Video super-resolution and refinement (SeedVR2, FlashVSR, RelayVSR, Wan 2.2 refine, MiniMax H3 sharpen / regenerate, NVIDIA RTX Video) and frame interpolation (FILM, GIMM-VFI).

The workflow JSONs added from the Open-Source Video Model Atlas (Nov 2026) are unmodified copies of published workflows. Each was checked only to be valid JSON, a genuine ComfyUI graph, and right for its model and task; **none has been runtime-tested in this library.** No model weights are included. The **model-weight licence is separate from the workflow (code) licence**; several weights are **non-commercial or carry custom terms** (marked below), so read the model card before commercial use. Workflows without a source row are original library workflows (Pixaroma tutorial episodes, Benji's AI Playground, or the library author's own MiniMax H3 / SeedVR2 runs); see the [root README credits](../../README.md#credits).

#### Sources, model weights and licences

Source link, code licence, weight licence and model download for each atlas workflow are in the Notes column of its model table above.

#### Atlas entries with no separate workflow here

Entries of the Open-Source Video Model Atlas for this category that did not get their own workflow. "Equivalent already exists" means an existing workflow already covers the model and task (usually a checkpoint, size or quantisation swap); nothing was fabricated for the others. Full per-entry status: [COVERAGE.md](../COVERAGE.md).

| Family | Entry | Status | Notes |
|---|---|---|---|
| RIFE | RIFE 4.22 lite | availability or redistribution unconfirmed | node RIFE VFI in Fannovel16/ComfyUI-Frame-Interpolation; only third-party JSON (OpenShot template wrapper, unclear licence) found; use [`frame-interpolation-vfi-node-pack`](FILM/frame-interpolation-vfi-node-pack.json) and swap node |
| RIFE | RIFE 4.7 | availability or redistribution unconfirmed | same as above |
| RIFE | RIFE 4.10 | availability or redistribution unconfirmed | same as above |
| RIFE | RIFE arbitrary timestep | availability or redistribution unconfirmed | same as above |
| SeedVR / SeedVR2 | SeedVR 3B | no suitable ComfyUI workflow | v1 superseded by SeedVR2 in ComfyUI |
| SeedVR / SeedVR2 | SeedVR 7B | no suitable ComfyUI workflow | v1 superseded by SeedVR2 in ComfyUI |
| VRT / RVRT | VRT video super-resolution | no suitable ComfyUI workflow | no maintained node |
| VRT / RVRT | VRT video deblurring | no suitable ComfyUI workflow | no maintained node |
| VRT / RVRT | VRT video denoising | no suitable ComfyUI workflow | no maintained node |
| VRT / RVRT | VRT video interpolation | no suitable ComfyUI workflow | no maintained node |
| VRT / RVRT | RVRT recurrent restoration | no suitable ComfyUI workflow | no maintained node |
| BasicVSR family | BasicVSR video super-resolution | no suitable ComfyUI workflow | MMCV-based, no maintained node |
| BasicVSR family | IconVSR | no suitable ComfyUI workflow | no maintained node |
| BasicVSR family | BasicVSR++ | no suitable ComfyUI workflow | no maintained node |
| BasicVSR family | RealBasicVSR | no suitable ComfyUI workflow | no maintained node |
| DAIN | DAIN depth-aware interpolation | no suitable ComfyUI workflow | legacy CUDA, no node |
| EDVR | EDVR video SR | no suitable ComfyUI workflow | no maintained node |
| EDVR | EDVR deblurring | no suitable ComfyUI workflow | no maintained node |
| TecoGAN | TecoGAN video upscaling | no suitable ComfyUI workflow | no node |
| RVRT | RVRT super-resolution | no suitable ComfyUI workflow | no maintained node |
| RVRT | RVRT deblur | no suitable ComfyUI workflow | no maintained node |
| RVRT | RVRT denoise | no suitable ComfyUI workflow | no maintained node |
| VEnhancer | VEnhancer spatial upscale | no suitable ComfyUI workflow | no maintained node |
| VEnhancer | VEnhancer temporal refine | no suitable ComfyUI workflow | no maintained node |
| Upscale-A-Video | Upscale-A-Video 4x | no suitable ComfyUI workflow | no maintained node |
| IFRNet | IFRNet interpolation | no suitable ComfyUI workflow | node exists in ComfyUI-Frame-Interpolation, no published workflow |
| AMT | AMT intermediate frame generation | no suitable ComfyUI workflow | node exists in ComfyUI-Frame-Interpolation, no published workflow |
| GMFSS | GMFSS Fortuna interpolation | no suitable ComfyUI workflow | node exists in ComfyUI-Frame-Interpolation, no published workflow |

See the [02-Video overview](../README.md) for the other categories, the [main README](../../README.md) for setup, or [`00-LIBRARY-INDEX.md`](../../00-LIBRARY-INDEX.md) for the full list.
