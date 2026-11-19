# Video Upscaling and Enhancement — ComfyUI workflows

Video super-resolution and restoration: SeedVR2 (custom node and core-node versions), FlashVSR, RelayVSR, Wan 2.2 generative refine-upscale, MiniMax H3 sharpen / regenerate refiners, and NVIDIA RTX Video super-resolution.

[← Back to 04-Video](../README.md)

## Workflows (18)

The 13 workflows marked "original" were already in this library. The 5 others were added from the Open Video Model Atlas review and have **not been runtime-tested**: each was only checked to be valid JSON, a real ComfyUI graph, and right for its model and task, and is copied unchanged from the source linked below. Licences are as published upstream; check the model card before commercial use.

### SeedVR2

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [seedvr2-video-upscale](seedvr2-video-upscale.json) | SeedVR2 video upscale (original) | `seedvr2_ema_3b_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler, ComfyUI-VideoHelperSuite |
| [seedvr2-hd-video-upscale](seedvr2-hd-video-upscale.json) | SeedVR2 HD video upscale with torch compile and alpha (original) | `seedvr2_ema_3b_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-1080p-api](seedvr2-video-upscale-1080p-api.json) | SeedVR2 7B fp8 upscale to 1080p (original) | `seedvr2_ema_7b_fp8_e4m3fn_mixed_block35_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-api-run](seedvr2-video-upscale-api-run.json) | SeedVR2 7B video upscale (original) | `seedvr2_ema_7b_fp16.safetensors`, `ema_vae_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-cartoon-dance-api](seedvr2-video-upscale-cartoon-dance-api.json) | SeedVR2 7B fp8 production run (original) | `seedvr2_ema_7b_fp8_e4m3fn_mixed_block35_fp16.safetensors` | ComfyUI-SeedVR2_VideoUpscaler, ComfyUI-VideoHelperSuite |
| [seedvr2-video-upscale-cartoon-talk-api](seedvr2-video-upscale-cartoon-talk-api.json) | SeedVR2 7B fp8 production run (original) | same | same |
| [seedvr2-video-upscale-curly-dance-api](seedvr2-video-upscale-curly-dance-api.json) | SeedVR2 7B fp8 production run (original) | same | same |
| [seedvr2-video-upscale-curly-talk-api](seedvr2-video-upscale-curly-talk-api.json) | SeedVR2 7B fp8 production run (original) | same | same |
| [seedvr2-video-upscale-duo-api](seedvr2-video-upscale-duo-api.json) | SeedVR2 7B fp8 production run (original) | same | same |
| [seedvr2-video-upscale-toons-api](seedvr2-video-upscale-toons-api.json) | SeedVR2 7B fp8 production run (original) | same | same |
| [seedvr2-native-core-nodes-temporal-chunk-video-upscale](seedvr2-native-core-nodes-temporal-chunk-video-upscale.json) | SeedVR2 3B with **built-in** ComfyUI SeedVR2 nodes, temporal chunking and merge for long clips, tiled VAE | `seedvr2_3b_int8_convrot.safetensors`, `seedvr2_ema_vae_fp16.safetensors` | — (core ComfyUI) |

### Diffusion video super-resolution

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [flashvsr-wan-1.3b-video-upscale](flashvsr-wan-1.3b-video-upscale.json) | FlashVSR one-step streaming video super-resolution on Wan 2.1 1.3B | `Wan2_1-T2V-1_3B_FlashVSR_fp32.safetensors`, `Wan2_1_FlashVSR_LQ_proj_model_bf16.safetensors`, `Wan2_1_FlashVSR_TCDecoder_fp32.safetensors`, `umt5-xxl-enc-bf16.safetensors` | ComfyUI-WanVideoWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite |
| [relayvsr-video-4x-upscale](relayvsr-video-4x-upscale.json) | RelayVSR 4× video super-resolution with built-in nodes (an x2 checkpoint also exists) | `relayvsr_x4_int8_convrot.safetensors`, `relayvsr_flash_vae_x4_fp32.safetensors` | — (core ComfyUI) |
| [wan-2.2-video-upscale-refine](wan-2.2-video-upscale-refine.json) | Wan 2.2 A14B low-noise video-to-video refine at a higher resolution (up to ~121 frames) | `Wan2_2-T2V-A14B-LOW_fp8_e4m3fn_scaled_KJ.safetensors`, lightx2v T2V LoRA, `wan_2.1_vae.safetensors`, `umt5_xxl_fp16.safetensors` | ComfyUI-WanVideoWrapper, ComfyUI_essentials |

### MiniMax H3 refiners

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [minimax-h3-sharpen-lora-full-hd](minimax-h3-sharpen-lora-full-hd.json) | MiniMax H3 sharpen LoRA pass to Full HD (original) | MiniMax H3 ref2va int8, `RealESRGAN_x2.pth` | ComfyUI-Pixaroma |
| [minimax-h3-regenerate-lora-remake-video-2k](minimax-h3-regenerate-lora-remake-video-2k.json) | MiniMax H3 regenerate LoRA, remake a video at 2K (original) | MiniMax H3 ref2va int8, `minimax_h3_latent_upscaler_3d_conv_v1_fp16.safetensors` | ComfyUI-Pixaroma |
| [minimax-h3-video-sharpener-refiner-upscale-from-video](minimax-h3-video-sharpener-refiner-upscale-from-video.json) | MiniMax H3 2K refiner LoRA, upscale from a video (original) | `minimax_h3_fl2va_pruned_w6a8.safetensors`, `minimax_h3_open_regenerate_2k_refiner_rank_384_bf16.safetensors` | — (core ComfyUI) |

### GPU video enhancement

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [nvidia-rtx-video-super-resolution-frame-gen-hdr](nvidia-rtx-video-super-resolution-frame-gen-hdr.json) | NVIDIA RTX Video: super-resolution, frame generation (2× fps) and TrueHDR in one local pass (RTX GPU required) | — (NVIDIA driver / SDK) | Nvidia_RTX_Nodes_ComfyUI |

## Sources, downloads and licences (added workflows)

| Workflow | Workflow source (code licence) | Model download | Model-weight licence |
|---|---|---|---|
| seedvr2-native-core-nodes-temporal-chunk-video-upscale | [Comfy-Org/workflow_templates `utility_seedvr2_3b_int8_upscale_video`](https://github.com/Comfy-Org/workflow_templates) (MIT) | [Comfy-Org/SeedVR2](https://huggingface.co/Comfy-Org/SeedVR2) | Apache-2.0 ([ByteDance-Seed/SeedVR2-3B](https://huggingface.co/ByteDance-Seed/SeedVR2-3B)) |
| flashvsr-wan-1.3b-video-upscale | [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/tree/main/example_workflows) (Apache-2.0) | [Kijai/WanVideo_comfy `FlashVSR`](https://huggingface.co/Kijai/WanVideo_comfy), [JunhaoZhuang/FlashVSR](https://huggingface.co/JunhaoZhuang/FlashVSR) | Apache-2.0 |
| relayvsr-video-4x-upscale | [Comfy-Org/workflow_templates `utility_relayvsr_video_x4_upscale`](https://github.com/Comfy-Org/workflow_templates) (MIT) | [Comfy-Org/RelayVSR](https://huggingface.co/Comfy-Org/RelayVSR) | Apache-2.0 |
| wan-2.2-video-upscale-refine | [Comfy-Org/workflow_templates `utility_video_upscale`](https://github.com/Comfy-Org/workflow_templates) (MIT) | [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy), [Wan-AI/Wan2.2-T2V-A14B](https://huggingface.co/Wan-AI/Wan2.2-T2V-A14B) | Apache-2.0 |
| nvidia-rtx-video-super-resolution-frame-gen-hdr | [Comfy-Org/workflow_templates `utility_nvidia_rtx_video_enhance`](https://github.com/Comfy-Org/workflow_templates) (MIT) | [Comfy-Org/Nvidia_RTX_Nodes_ComfyUI](https://github.com/Comfy-Org/Nvidia_RTX_Nodes_ComfyUI) (node pack Apache-2.0) | **NVIDIA RTX Video SDK terms (proprietary)** |

The SeedVR2 custom-node workflows use [numz/ComfyUI-SeedVR2_VideoUpscaler](https://github.com/numz/ComfyUI-SeedVR2_VideoUpscaler) (Apache-2.0) with weights from [numz/SeedVR2_comfyUI](https://huggingface.co/numz/SeedVR2_comfyUI) (Apache-2.0).

## No ComfyUI workflow found

| Model (Open Video Model Atlas) | Why there is no workflow here |
|---|---|
| SeedVR (v1) 3B / 7B | Superseded by SeedVR2 in ComfyUI; no v1 workflow published |
| Kandinsky 6 Video Super-Resolution | Part of the Kandinsky 6 pipeline; no stand-alone ComfyUI upscale workflow found |
| VRT (SR, deblur, denoise), RVRT (SR, deblur, denoise) | No maintained ComfyUI node |
| BasicVSR, IconVSR, BasicVSR++, RealBasicVSR | No maintained ComfyUI node (MMCV-based) |
| EDVR (SR, deblur) | No maintained ComfyUI node or workflow |
| TecoGAN | No ComfyUI node |
| VEnhancer (spatial upscale, temporal refine) | No maintained ComfyUI node or workflow |
| Upscale-A-Video | No maintained ComfyUI node or workflow |
