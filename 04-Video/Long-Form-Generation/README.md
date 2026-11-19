# Long-Form Generation — ComfyUI workflows

Long videos built in chunks: autoregressive / streaming generators (MAGI-1), next-frame-section packing (FramePack), diffusion-forcing extension (SkyReels V2), and continuation of an existing clip (LongCat-Video, Wan 2.2 + Pusa).

[← Back to 04-Video](../README.md)

## Workflows (7)

None of these workflows has been runtime-tested: each was only checked to be valid JSON, a real ComfyUI graph, and right for its model and task. Each JSON is copied unchanged from the source linked below. Licences are as published upstream; the code licence (of the workflow / node pack) and the model-weight licence are listed separately — check the model card before commercial use.

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [magi-1-text-to-video](magi-1-text-to-video.json) | MAGI-1 text-to-video, autoregressive chunk-by-chunk generation | MAGI-1 (4.5B / 24B, set in the node config) | MAGI-1 `comfyui/` nodes |
| [magi-1-image-to-video](magi-1-image-to-video.json) | MAGI-1 image-to-video from a start image | MAGI-1 | MAGI-1 `comfyui/` nodes |
| [magi-1-video-continuation](magi-1-video-continuation.json) | MAGI-1 continues an input video with new chunks (video-to-video extension) | MAGI-1 | MAGI-1 `comfyui/` nodes |
| [framepack-hunyuan-image-to-video](framepack-hunyuan-image-to-video.json) | FramePack image-to-video: next-frame-section prediction for long clips on low VRAM | `FramePackI2V_HY_fp8_e4m3fn.safetensors`, `hunyuan_video_vae_bf16_repack.safetensors`, `llava_llama3_fp16.safetensors`, `clip_l.safetensors`, `sigclip_vision_patch14_384.safetensors` | ComfyUI-FramePackWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI_essentials |
| [skyreels-v2-diffusion-forcing-video-extension](skyreels-v2-diffusion-forcing-video-extension.json) | SkyReels V2 diffusion forcing: extends a loaded video window by window | `Wan2_1-SkyReels-V2-DF-1_3B-540P_fp32.safetensors`, `Wan2_1_VAE_bf16.safetensors`, `umt5-xxl-enc-bf16.safetensors` | ComfyUI-WanVideoWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI_essentials |
| [longcat-video-image-to-video-with-extension](longcat-video-image-to-video-with-extension.json) | LongCat-Video text/image-to-video, then extends the clip with overlapping continuation passes | `LongCat_TI2V_comfy_fp8_e4m3fn_scaled_KJ.safetensors`, `LongCat_distill_lora_rank128_bf16.safetensors`, `Wan2_1_VAE_bf16.safetensors`, `umt5-xxl-enc-bf16.safetensors` | ComfyUI-WanVideoWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite |
| [wan-2.2-pusa-video-extension](wan-2.2-pusa-video-extension.json) | Wan 2.2 A14B with Pusa LoRAs: extends an input video from its last frames | `Wan2_2-T2V-A14B-HIGH/LOW_fp8_e4m3fn_scaled_KJ.safetensors`, `Wan22_PusaV1_lora_HIGH/LOW_…bf16.safetensors`, lightx2v T2V LoRA, `taew2_1.safetensors` | ComfyUI-WanVideoWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI_essentials |

## Sources, downloads and licences

| Workflow | Workflow source (code licence) | Model download | Model-weight licence |
|---|---|---|---|
| magi-1-* (3) | [SandAI-org/MAGI-1 `comfyui/workflow`](https://github.com/SandAI-org/MAGI-1/tree/main/comfyui) (Apache-2.0) | [sand-ai/MAGI-1](https://huggingface.co/sand-ai/MAGI-1) | Apache-2.0 |
| framepack-hunyuan-image-to-video | [kijai/ComfyUI-FramePackWrapper](https://github.com/kijai/ComfyUI-FramePackWrapper/tree/main/example_workflows) (Apache-2.0) | [lllyasviel/FramePackI2V_HY](https://huggingface.co/lllyasviel/FramePackI2V_HY), [Kijai/HunyuanVideo_comfy](https://huggingface.co/Kijai/HunyuanVideo_comfy) | HunyuanVideo-based — **Tencent Hunyuan Community License** (custom; territory and user-count limits) |
| skyreels-v2-diffusion-forcing-video-extension | [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/tree/main/example_workflows) (Apache-2.0) | [Skywork/SkyReels-V2-DF-1.3B-540P](https://huggingface.co/Skywork/SkyReels-V2-DF-1.3B-540P), [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy) | **Skywork community licence (custom, "other")** — check before commercial use |
| longcat-video-image-to-video-with-extension | [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/tree/main/example_workflows) (Apache-2.0) | [meituan-longcat/LongCat-Video](https://huggingface.co/meituan-longcat/LongCat-Video), [Kijai/LongCat-Video_comfy](https://huggingface.co/Kijai/LongCat-Video_comfy) | MIT |
| wan-2.2-pusa-video-extension | [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/tree/main/example_workflows) (Apache-2.0) | [Wan-AI/Wan2.2-T2V-A14B](https://huggingface.co/Wan-AI/Wan2.2-T2V-A14B), [RaphaelLiu/Pusa-Wan2.2-V1](https://huggingface.co/RaphaelLiu/Pusa-Wan2.2-V1), [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy) | Apache-2.0 |

## No ComfyUI workflow found

| Model (Open Video Model Atlas) | Why there is no workflow here |
|---|---|
| Helios (Base / Mid / Distilled 14B) | Upstream ships Diffusers / SGLang / vLLM-Omni inference only; no ComfyUI node or workflow published |
| SEINE / LaVie | No maintained ComfyUI integration; research code only |
| SkyReels V1 human-centric, SkyReels V2 I2V 720p | Base generators, not long-form extension — left for the Image-to-Video / Text-to-Video collection |
| FramePack F1 / P1 | F1 loads in the same FramePackWrapper graph (swap the checkpoint); P1 has no released weights or workflow |
| LongCat interactive video | No ComfyUI workflow published (official scripts only) |
| LongCat Avatar multi-audio | Avatar workflow exists (WanVideoWrapper `LongCatAvatar_…`) — belongs to the talking-avatar collection, not this folder |
| MAGI-1 4.5B / 24B / distilled / FP8 / MAGI-1.1 | Checkpoint and quantisation variants of the same three graphs above; no separate workflow |
