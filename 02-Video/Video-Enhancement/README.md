# Video Upscaling and Enhancement — ComfyUI workflows

Video super-resolution and refinement (SeedVR2, FlashVSR, RelayVSR, Wan 2.2 refine, MiniMax H3 sharpen / regenerate, NVIDIA RTX Video) and frame interpolation (FILM, GIMM-VFI).

[← 02-Video overview](../README.md) · [Atlas coverage tracker](../COVERAGE.md)

| Subfolder | What is inside | Workflows |
|---|---|---|
| [`Video-Upscaling/`](Video-Upscaling) | Video upscaling, super-resolution and refinement | 18 |
| [`Frame-Interpolation/`](Frame-Interpolation) | Frame interpolation (higher frame rate, slow motion) | 3 |

## Workflows (21)

The workflow JSONs added from the Open-Source Video Model Atlas (Nov 2026) are unmodified copies of published workflows. Each was checked only to be valid JSON, a genuine ComfyUI graph, and right for its model and task; **none has been runtime-tested in this library.** No model weights are included. The **model-weight licence is separate from the workflow (code) licence**; several weights are **non-commercial or carry custom terms** (marked below), so read the model card before commercial use. Workflows without a source row are original library workflows (Pixaroma tutorial episodes, Benji's AI Playground, or the library author's own MiniMax H3 / SeedVR2 runs); see the [root README credits](../../README.md#credits).

### Video Upscaling (18)

Video upscaling, super-resolution and refinement.

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [flashvsr-wan-1.3b-video-upscale](Video-Upscaling/flashvsr-wan-1.3b-video-upscale.json) | FlashVSR one-step streaming video super-resolution on Wan 2.1 1.3B | `Wan2_1-T2V-1_3B_FlashVSR_fp32.safetensors`, `Wan2_1_FlashVSR_LQ_proj_model_bf16.safetensors`, `Wan2_1_FlashVSR_TCDecoder_fp32.safetensors`, `umt5-xxl-enc-bf16.safetensors` | ComfyUI-WanVideoWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite |
| [minimax-h3-regenerate-lora-remake-video-2k](Video-Upscaling/minimax-h3-regenerate-lora-remake-video-2k.json) | MiniMax H3 regenerate LoRA, remake a video at 2K (original) | MiniMax H3 ref2va int8, `minimax_h3_latent_upscaler_3d_conv_v1_fp16.safetensors` | ComfyUI-Pixaroma |
| [minimax-h3-sharpen-lora-full-hd](Video-Upscaling/minimax-h3-sharpen-lora-full-hd.json) | Minimax H3 - Sharpen LoRA + Upscale to Full HD (Ep41) | MiniMax H3 ref2va int8, `RealESRGAN_x2.pth` | ComfyUI-Pixaroma |
| [minimax-h3-video-sharpener-refiner-upscale-from-video](Video-Upscaling/minimax-h3-video-sharpener-refiner-upscale-from-video.json) | Video Upscale / Sharpen — load any video, re-render it through the H3 2K refiner LoRA (Pika pass-2 only) | `minimax_h3_fl2va_pruned_w6a8.safetensors`, `minimax_h3_open_regenerate_2k_refiner_rank_384_bf16.safetensors` | — (core ComfyUI) |
| [nvidia-rtx-video-super-resolution-frame-gen-hdr](Video-Upscaling/nvidia-rtx-video-super-resolution-frame-gen-hdr.json) | NVIDIA RTX Video: super-resolution, frame generation (2× fps) and TrueHDR in one local pass (RTX GPU required) | — (NVIDIA driver / SDK) | Nvidia_RTX_Nodes_ComfyUI |
| [relayvsr-video-4x-upscale](Video-Upscaling/relayvsr-video-4x-upscale.json) | RelayVSR 4× video super-resolution with built-in nodes (an x2 checkpoint also exists) | `relayvsr_x4_int8_convrot.safetensors`, `relayvsr_flash_vae_x4_fp32.safetensors` | — (core ComfyUI) |
| [seedvr2-hd-video-upscale](Video-Upscaling/seedvr2-hd-video-upscale.json) | SeedVR2 HD video upscale with torch compile and alpha (original) | `seedvr2_ema_3b_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-native-core-nodes-temporal-chunk-video-upscale](Video-Upscaling/seedvr2-native-core-nodes-temporal-chunk-video-upscale.json) | SeedVR2 3B with **built-in** ComfyUI SeedVR2 nodes, temporal chunking and merge for long clips, tiled VAE | `seedvr2_3b_int8_convrot.safetensors`, `seedvr2_ema_vae_fp16.safetensors` | — (core ComfyUI) |
| [seedvr2-video-upscale](Video-Upscaling/seedvr2-video-upscale.json) | SeedVR2 video upscale (original) | `seedvr2_ema_3b_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler, ComfyUI-VideoHelperSuite |
| [seedvr2-video-upscale-1080p-api](Video-Upscaling/seedvr2-video-upscale-1080p-api.json) | SeedVR2 7B video upscale of one clip to 1080p (API format) | `seedvr2_ema_7b_fp8_e4m3fn_mixed_block35_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-api-run](Video-Upscaling/seedvr2-video-upscale-api-run.json) | SeedVR2 7B video upscale (original) | `seedvr2_ema_7b_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-cartoon-dance-api](Video-Upscaling/seedvr2-video-upscale-cartoon-dance-api.json) | SeedVR2 7B video upscale run (cartoon dance clip) (API format) | `seedvr2_ema_7b_fp8_e4m3fn_mixed_block35_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler, ComfyUI-VideoHelperSuite |
| [seedvr2-video-upscale-cartoon-talk-api](Video-Upscaling/seedvr2-video-upscale-cartoon-talk-api.json) | SeedVR2 7B video upscale run (cartoon talk clip) (API format) | same | same |
| [seedvr2-video-upscale-curly-dance-api](Video-Upscaling/seedvr2-video-upscale-curly-dance-api.json) | SeedVR2 7B video upscale run (curly dance clip) (API format) | same | same |
| [seedvr2-video-upscale-curly-talk-api](Video-Upscaling/seedvr2-video-upscale-curly-talk-api.json) | SeedVR2 7B video upscale run (curly talk clip) (API format) | same | same |
| [seedvr2-video-upscale-duo-api](Video-Upscaling/seedvr2-video-upscale-duo-api.json) | SeedVR2 7B video upscale run (duo clip) (API format) | same | same |
| [seedvr2-video-upscale-toons-api](Video-Upscaling/seedvr2-video-upscale-toons-api.json) | SeedVR2 7B video upscale run (toons clip) (API format) | same | same |
| [wan-2.2-video-upscale-refine](Video-Upscaling/wan-2.2-video-upscale-refine.json) | Wan 2.2 A14B low-noise video-to-video refine at a higher resolution (up to ~121 frames) | `Wan2_2-T2V-A14B-LOW_fp8_e4m3fn_scaled_KJ.safetensors`, lightx2v T2V LoRA, `wan_2.1_vae.safetensors`, `umt5_xxl_fp16.safetensors` | ComfyUI-WanVideoWrapper, ComfyUI_essentials |

### Frame Interpolation (3)

Frame interpolation (higher frame rate, slow motion).

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [film-frame-interpolation-core-nodes](Frame-Interpolation/film-frame-interpolation-core-nodes.json) | FILM interpolation with built-in ComfyUI nodes (Frame Interpolation Model Loader → Frame Interpolate), keeps audio | `film_net_fp16.safetensors` | — (core ComfyUI) |
| [film-frame-interpolation-vfi-node-pack](Frame-Interpolation/film-frame-interpolation-vfi-node-pack.json) | FILM interpolation with the ComfyUI-Frame-Interpolation pack; the same pack has drop-in RIFE, IFRNet, AMT, GMFSS Fortuna, CAIN and other VFI nodes | `film_net_fp32.pt` (auto-downloaded by the node) | ComfyUI-Frame-Interpolation, ComfyUI-VideoHelperSuite |
| [gimm-vfi-frame-interpolation](Frame-Interpolation/gimm-vfi-frame-interpolation.json) | GIMM-VFI arbitrary-timestep interpolation (implicit motion modelling), output fps = input fps × factor | `gimmvfi_r_arb_lpips_fp32.safetensors` | ComfyUI-GIMM-VFI, ComfyUI-VideoHelperSuite |

## Sources, model weights and licences

8 of these workflows were added from the atlas. Code licence = licence of the repository the JSON was copied from; weight licence = licence of the model the workflow loads.

| Workflow | Source | Code licence | Model weights | Weight licence | Status |
|---|---|---|---|---|---|
| [film-frame-interpolation-core-nodes](Frame-Interpolation/film-frame-interpolation-core-nodes.json) | [Comfy-Org/workflow_templates `utility_video_frame_interpolation`](https://github.com/Comfy-Org/workflow_templates) | MIT | [Comfy-Org/frame_interpolation](https://huggingface.co/Comfy-Org/frame_interpolation) | FILM: Apache-2.0 ([google-research/frame-interpolation](https://github.com/google-research/frame-interpolation)) | not runtime-tested |
| [film-frame-interpolation-vfi-node-pack](Frame-Interpolation/film-frame-interpolation-vfi-node-pack.json) | [Comfy-Org/workflow_templates `utility-frame_interpolation-film`](https://github.com/Comfy-Org/workflow_templates) | MIT | [Fannovel16/ComfyUI-Frame-Interpolation](https://github.com/Fannovel16/ComfyUI-Frame-Interpolation) (node pack MIT, downloads weights) | FILM: Apache-2.0 | not runtime-tested |
| [gimm-vfi-frame-interpolation](Frame-Interpolation/gimm-vfi-frame-interpolation.json) | [Comfy-Org/workflow_templates `utility_gimm_frame_interpolation`](https://github.com/Comfy-Org/workflow_templates) | MIT | [Kijai/GIMM-VFI_safetensors](https://huggingface.co/Kijai/GIMM-VFI_safetensors) via [kijai/ComfyUI-GIMM-VFI](https://github.com/kijai/ComfyUI-GIMM-VFI) | **Not stated on the model page — unverified**; check [GSean/GIMM-VFI](https://github.com/GSean/GIMM-VFI) before commercial use | not runtime-tested |
| [flashvsr-wan-1.3b-video-upscale](Video-Upscaling/flashvsr-wan-1.3b-video-upscale.json) | [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/tree/main/example_workflows) | Apache-2.0 | [Kijai/WanVideo_comfy `FlashVSR`](https://huggingface.co/Kijai/WanVideo_comfy), [JunhaoZhuang/FlashVSR](https://huggingface.co/JunhaoZhuang/FlashVSR) | Apache-2.0 | not runtime-tested |
| [nvidia-rtx-video-super-resolution-frame-gen-hdr](Video-Upscaling/nvidia-rtx-video-super-resolution-frame-gen-hdr.json) | [Comfy-Org/workflow_templates `utility_nvidia_rtx_video_enhance`](https://github.com/Comfy-Org/workflow_templates) | MIT | [Comfy-Org/Nvidia_RTX_Nodes_ComfyUI](https://github.com/Comfy-Org/Nvidia_RTX_Nodes_ComfyUI) (node pack Apache-2.0) | **NVIDIA RTX Video SDK terms (proprietary)** | not runtime-tested |
| [relayvsr-video-4x-upscale](Video-Upscaling/relayvsr-video-4x-upscale.json) | [Comfy-Org/workflow_templates `utility_relayvsr_video_x4_upscale`](https://github.com/Comfy-Org/workflow_templates) | MIT | [Comfy-Org/RelayVSR](https://huggingface.co/Comfy-Org/RelayVSR) | Apache-2.0 | not runtime-tested |
| [seedvr2-native-core-nodes-temporal-chunk-video-upscale](Video-Upscaling/seedvr2-native-core-nodes-temporal-chunk-video-upscale.json) | [Comfy-Org/workflow_templates `utility_seedvr2_3b_int8_upscale_video`](https://github.com/Comfy-Org/workflow_templates) | MIT | [Comfy-Org/SeedVR2](https://huggingface.co/Comfy-Org/SeedVR2) | Apache-2.0 ([ByteDance-Seed/SeedVR2-3B](https://huggingface.co/ByteDance-Seed/SeedVR2-3B)) | not runtime-tested |
| [wan-2.2-video-upscale-refine](Video-Upscaling/wan-2.2-video-upscale-refine.json) | [Comfy-Org/workflow_templates `utility_video_upscale`](https://github.com/Comfy-Org/workflow_templates) | MIT | [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy), [Wan-AI/Wan2.2-T2V-A14B](https://huggingface.co/Wan-AI/Wan2.2-T2V-A14B) | Apache-2.0 | not runtime-tested |

## Atlas entries with no separate workflow here

Entries of the Open-Source Video Model Atlas for this category that did not get their own workflow. "Equivalent already exists" means an existing workflow already covers the model and task (usually a checkpoint, size or quantisation swap); nothing was fabricated for the others. Full per-entry status: [COVERAGE.md](../COVERAGE.md).

| Family | Entry | Status | Notes |
|---|---|---|---|
| RIFE | RIFE 4.22 lite | availability or redistribution unconfirmed | node RIFE VFI in Fannovel16/ComfyUI-Frame-Interpolation; only third-party JSON (OpenShot template wrapper, unclear licence) found; use [`film-frame-interpolation-vfi-node-pack`](Frame-Interpolation/film-frame-interpolation-vfi-node-pack.json) and swap node |
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
