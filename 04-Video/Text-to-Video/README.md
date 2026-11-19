# Text to Video — ComfyUI workflows

Text-to-video (txt2video) workflows: MiniMax H3 / FastH3 / Pika-H3-Flex, Wan 2.1 / 2.2, HunyuanVideo and 1.5, LTX-Video and LTX-2.5, Kandinsky 5 / 6, CogVideoX, Pyramid Flow, Cosmos, Mochi and SDXL + SVD.

## Workflows (23)

The first table lists the 10 workflows already in the library; the 13 workflows added from the *Open-Source Video Model Atlas* (Nov 2026) follow in their own table.

### Existing workflows

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [minimax-fasth3-txt2video-8-step](minimax-fasth3-txt2video-8-step.json) | Text to Video (8-Step) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `fastvideo_fasth3_8step_v2_pruned_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-pika-flex-txt2video-2-stage-2k](minimax-h3-pika-flex-txt2video-2-stage-2k.json) | Text to Video — Pika-H3-Flex 6-Step + 2K Latent Upscale (2-Stage) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `pika_h3_flex_fl2va_v1_avg_rank_56_bf16.safetensors` +4 more | ComfyUI-KJNodes |
| [minimax-h3-pika-flex-txt2video-720p-to-1080p](minimax-h3-pika-flex-txt2video-720p-to-1080p.json) | Text to Video — Pika-H3-Flex, 720p → 1080p, 5 s (tuned for 16 GB VRAM / 30 GB RAM) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_fl2va_pruned_w6a8.safetensors`, `pika_h3_flex_fl2va_v1_avg_rank_56_bf16.safetensors` +4 more | ComfyUI-KJNodes |
| [minimax-h3-txt2video-2k-ep41](minimax-h3-txt2video-2k-ep41.json) | Bonus - Minimax H3 - Text to Video in 2K (Ep41) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_DMAD_4step_full_lora_avg_rank_39_bf16.safetensors`, `open_h3_regenerate_2k_comfy_swiglu_fixed.safetensors`, `minimax_h3_latent_upscaler_3d_conv_v1_fp16.safetensors` | ComfyUI-Pixaroma |
| [minimax-h3-txt2video-8-step-lora](minimax-h3-txt2video-8-step-lora.json) | Text to Video + 8-step speed LoRA (W6A8 model, int8 video VAE) (from captain's local ComfyUI, not re-tested) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_fl2va_pruned_w6a8.safetensors`, `minimax_h3_fl2v_turbo_8step_v1.0_comfyui_bf16.safetensors` +2 more | ComfyUI-Pixaroma |
| [minimax-h3-txt2video-low-vram-8gb](minimax-h3-txt2video-low-vram-8gb.json) | Text to Video — Low VRAM 8GB | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_fl2va_pruned_int8_convrot.safetensors` +1 more | ComfyUI_LayerStyle, ComfyUI-Pixaroma |
| [minimax-h3-txt2video-secret-sauce-4k-direct-output](minimax-h3-txt2video-secret-sauce-4k-direct-output.json) | Text to Video — Secret Sauce 4K Direct Output | `qwen3vl_32b_minimax_h3_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `taeh3.safetensors` +9 more | ComfyUI-MemoryCleaner, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, rgthree-comfy, ComfyUI-MiniMaxH3-TimelineDirector, ComfyUI_Comfyroll_CustomNodes, ComfyUI-MiniMaxH3-Unified, H3SigmaRefiner (unknown source), RH_DLSS5Enhance (unknown source) |
| [minimax-h3-txt2video-speed-lora](minimax-h3-txt2video-speed-lora.json) | Text to Video + Speed LoRA | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +2 more | ComfyUI-Pixaroma |
| [minimax-h3-txt2video](minimax-h3-txt2video.json) | Text to Video | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_fl2va_pruned_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [mochi-1-txt2video](mochi-1-txt2video.json) | Text to Video — Genmo Mochi 1 | `dit.safetensors`, `t5xxl_fp16.safetensors`, `decoder.safetensors` | — |

### Open-Source Video Model Atlas additions (13)

Every file is an unmodified copy of an existing workflow from the official [Comfy-Org workflow templates](https://github.com/Comfy-Org/workflow_templates) (MIT), the official [ComfyUI examples](https://github.com/comfyanonymous/ComfyUI_examples) (permissive workflow licence), the model authors' own repo, or the custom-node repo that implements the model. Files were checked to be valid ComfyUI workflow JSON for the named model and task; **none was run — not runtime-tested.** No model weights are included; download them from the links (several workflows also list them in a note inside the graph). "-" in custom nodes means core ComfyUI only (a recent ComfyUI build is needed for newer models). The licence column is the **model weight** licence summary — read the model card before commercial use; workflow-file licences are given under *Sources and licences*.

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence | Tested |
|---|---|---|---|---|---|---|---|
| [cogvideox-5b-txt2video](cogvideox-5b-txt2video.json) | CogVideoX 5B T2V | CogVideoX 1.0 5B text to video (6 s, 720x480); weights auto-download | [source](https://github.com/kijai/ComfyUI-CogVideoXWrapper/blob/main/example_workflows/cogvideox_1_0_5b_T2V_02.json) | [link](https://huggingface.co/THUDM/CogVideoX-5b) | ComfyUI-CogVideoXWrapper, ComfyUI-VideoHelperSuite | CogVideoX License (5B; registration for commercial use) | not runtime-tested |
| [cosmos-1-7b-text2world-txt2video](cosmos-1-7b-text2world-txt2video.json) | Cosmos-1.0 Diffusion 7B Text2World | NVIDIA Cosmos 1 world-model text to video | [source](https://github.com/comfyanonymous/ComfyUI_examples/tree/master/cosmos) | [link](https://huggingface.co/comfyanonymous/cosmos_1.0_text_encoder_and_VAE_ComfyUI) | - | NVIDIA Open Model License | not runtime-tested |
| [hunyuanvideo-1.5-720p-txt2video-1080p-sr](hunyuanvideo-1.5-720p-txt2video-1080p-sr.json) | HunyuanVideo 1.5 T2V 8.3B | 720p text to video with optional 1080p super-resolution pass and EasyCache | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_hunyuan_video_1.5_720p_t2v.json) | [link](https://huggingface.co/Comfy-Org/HunyuanVideo_1.5_repackaged) | - | Tencent Hunyuan Community License (excludes EU/UK/South Korea) | not runtime-tested |
| [hunyuanvideo-13b-txt2video](hunyuanvideo-13b-txt2video.json) | HunyuanVideo 13B T2V | Original HunyuanVideo 720p text to video | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/hunyuan_video_text_to_video.json) | [link](https://huggingface.co/Comfy-Org/HunyuanVideo_repackaged) | - | Tencent Hunyuan Community License (excludes EU/UK/South Korea) | not runtime-tested |
| [kandinsky-5-lite-txt2video](kandinsky-5-lite-txt2video.json) | Kandinsky 5 Lite T2V 2B (SFT 5s) | 5-second text to video with the 2B Lite model | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_kandinsky5_t2v.json) | [link](https://huggingface.co/kandinskylab) | - | MIT (check model card) | not runtime-tested |
| [kandinsky-6-pro-distill-txt2video-with-audio](kandinsky-6-pro-distill-txt2video-with-audio.json) | Kandinsky 6 Pro Distilled 29B + Video SR | Text to video with generated audio, prompt beautifier, MagCache and Kandinsky 6 video super-resolution | [source](https://github.com/kandinskylab/kandinsky-6/tree/main/comfyui/example_workflows) | [link](https://huggingface.co/kandinskylab) | kandinsky6, kandinsky6-sr | MIT code; check weight cards | not runtime-tested |
| [ltx-2.5-txt2video-with-audio](ltx-2.5-txt2video-with-audio.json) | LTX-2.5 22B distilled | Text to video with synchronised audio, Gemma 4 prompt enhancer, x2 latent upscale (INT8) | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_ltx2_5_t2v.json) | [link](https://huggingface.co/Lightricks/LTX-2.5) | - | LTX-2 Community License (revenue limit) | not runtime-tested |
| [ltx-video-0.9-txt2video](ltx-video-0.9-txt2video.json) | LTX-Video 0.9.x (2B) | Legacy LTX-Video text to video; works with any 0.9.x 2B checkpoint | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/ltxv_text_to_video.json) | [link](https://huggingface.co/Lightricks/LTX-Video) | - | LTX-Video licence per version (0.9.5+: OpenRAIL-M) | not runtime-tested |
| [pyramid-flow-miniflux-txt2video](pyramid-flow-miniflux-txt2video.json) | Pyramid Flow miniFLUX 384p | Autoregressive pyramidal-flow text to video | [source](https://github.com/kijai/ComfyUI-PyramidFlowWrapper/blob/main/examples/pyramid_flow_miniflux_text2vid_example_01.json) | [link](https://huggingface.co/rain1011/pyramid-flow-miniflux) | ComfyUI-PyramidFlowWrapper, ComfyUI-VideoHelperSuite | MIT (check model card) | not runtime-tested |
| [svd-xt-sdxl-txt2img2video](svd-xt-sdxl-txt2img2video.json) | SDXL + Stable Video Diffusion XT | Text to image with SDXL, then animate it with SVD-XT | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/txt_to_image_to_video.json) | [link](https://huggingface.co/stabilityai/stable-video-diffusion-img2vid-xt) | - | Stability AI Community License (SVD) | not runtime-tested |
| [wan-2.1-1.3b-txt2video-low-vram](wan-2.1-1.3b-txt2video-low-vram.json) | Wan 2.1 T2V 1.3B | Small 1.3B text to video (about 8 GB VRAM) | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/text_to_video_wan.json) | [link](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged) | - | Apache-2.0 | not runtime-tested |
| [wan-2.1-alpha-14b-txt2video-transparent-rgba](wan-2.1-alpha-14b-txt2video-transparent-rgba.json) | Wan 2.1 T2V 14B + Wan-Alpha | Text to video with a transparent background (RGBA), saved as animated WebP; Lightx2v 4-step LoRA | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan2.1_alpha_t2v_14B.json) | [link](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged) | - | Apache-2.0 (check Wan-Alpha LoRA card) | not runtime-tested |
| [wan-2.2-14b-txt2video](wan-2.2-14b-txt2video.json) | Wan 2.2 T2V A14B | Two-expert (high/low noise) 14B text to video, FP8, optional Lightx2v 4-step LoRAs | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan2_2_14B_t2v.json) | [link](https://huggingface.co/Comfy-Org/Wan_2.2_ComfyUI_Repackaged) | - | Apache-2.0 | not runtime-tested |

### Duplicates skipped

Official templates for a model + task the library already covers were not added: MiniMax H3 t2v and FastH3 t2v templates, Pika-H3-Flex t2v, LTX-2 t2v (dev and distilled) and LTX-2.3 t2v (same task as the LTX-2.5 t2v added here; checkpoint-only difference), ComfyUI_examples Wan 2.2 t2v (14B/5B, identical to the templates), Mochi (already present), LTXV 0.9.5 t2v example (same graph as `ltx-video-0.9-txt2video`), Kandinsky 5 repo ComfyUI T2V (same task as the template), ComfyUI-LTXVideo 2.5 T2V/I2V two-stage (same as templates).

### No ComfyUI workflow found (this slice)

No authentic ComfyUI workflow was found, so nothing was fabricated:

- **Open-Sora 1.0 / 1.1 / 1.2 / 2.0** — only a stale community port; no maintained ComfyUI workflow.
- **Open-Sora Plan v1.0–v1.5** — no ComfyUI workflow (official scripts only; v1.5 targets Ascend NPU).
- **Step-Video T2V / T2V Turbo / TI2V** — no maintained ComfyUI workflow found.
- **Allegro T2V / TI2V** — Diffusers only; no ComfyUI workflow found.
- **VideoCrafter1 / VideoCrafter2** — only old unmaintained community nodes, no published workflow; research/non-commercial weights.
- **Latte / Latte-1** — Diffusers only; no ComfyUI workflow.
- **Cosmos3 Edge / Nano / Super** — no ComfyUI template.
- **Cosmos-Predict2.5 (2B/14B, multiview, robot action)** — official CLI/Diffusers only; the Cosmos-Predict2 (2.0) workflow in Image-to-Video is the nearest ComfyUI path.
- **Pyramid Flow SD3 384p** — superseded; only miniFLUX workflows are published.
- **AnimateDiff SDXL beta / plain SD 1.5 text-to-video** — AnimateDiff-Evolved publishes no workflow JSON files; the AnimateLCM template in Image-to-Video is the official graph.
- **Kandinsky 5 Pro 19B / Lite Flash / Camera-Control LoRA** — no separate workflow; the Lite graphs load Pro/Flash checkpoints.
- **Wan 2.1 T2V 14B** — no separate plain graph; the 1.3B and Wan-Alpha graphs load the 14B checkpoint.

## Sources and licences

- Comfy-Org workflow templates: MIT — <https://github.com/Comfy-Org/workflow_templates>
- ComfyUI examples: "Permission to use, copy, modify, and/or distribute these workflows for any purpose" — <https://github.com/comfyanonymous/ComfyUI_examples>
- kijai/ComfyUI-CogVideoXWrapper: Apache-2.0; kijai/ComfyUI-PyramidFlowWrapper: MIT; kijai/ComfyUI-DynamiCrafterWrapper: Apache-2.0 (Tencent DynamiCrafter licence)
- kandinskylab/kandinsky-6 ComfyUI example workflows: MIT

