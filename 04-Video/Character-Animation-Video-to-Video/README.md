# Character Animation and Video-to-Video — ComfyUI workflows

Make a character move: pose and motion transfer from a driving video, character and face replacement in existing footage, and character-level restyling with MiniMax H3, SCAIL / SCAIL-2, Wan Animate and earlier pose-driven models.

## Workflows (51)

### Pose and motion transfer (6)

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [wan-animate-2-motion-transfer-from-driving-video](wan-animate-2-motion-transfer-from-driving-video.json) | Animate a still character directly from a driving video (no skeleton preprocessing) | Wan Animate 2 14B | core only |
| [wan-2.1-steadydancer-first-frame-dance-animation](wan-2.1-steadydancer-first-frame-dance-animation.json) | Pose-driven dance animation that keeps the reference image as the first frame | SteadyDancer 14B (Wan 2.1) | ComfyUI-WanVideoWrapper, ComfyUI-WanAnimatePreprocess, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite |
| [mimicmotion-pose-guided-human-animation](mimicmotion-pose-guided-human-animation.json) | Reference image + pose sequence from a video to a human video | MimicMotion 1.0 (SVD based) | ComfyUI-MimicMotionWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite |
| [champ-3d-pose-guided-human-animation](champ-3d-pose-guided-human-animation.json) | Human animation guided by SMPL depth, normal, DensePose and skeleton maps | Champ (SD 1.5 based) | ComfyUI-champWrapper, ComfyUI-KJNodes, comfyui_controlnet_aux, ComfyUI_essentials, rgthree-comfy, ComfyUI-VideoHelperSuite (+ SMPL/4D-Humans nodes) |
| [musepose-pose-driven-dance-video](musepose-pose-driven-dance-video.json) | Align a dance pose video to a reference image and render the dance | MusePose (SD image-variations based) | Comfyui-MusePose, ComfyUI-VideoHelperSuite |
| [animate-anyone-evolved-pose-to-video](animate-anyone-evolved-pose-to-video.json) | ReferenceNet + pose guider character animation (Moore-AnimateAnyone reproduction) | Moore-AnimateAnyone (SD 1.5 based) | ComfyUI-AnimateAnyone-Evolved, ComfyUI-VideoHelperSuite |

### Wan 2.2 Animate character replacement (5)

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [wan-2.2-animate-replace-character-and-background-16fps](wan-2.2-animate-replace-character-and-background-16fps.json) | Animate replace character and background 16fps | Wan 2.2 Animate 14B (`sam3.pt`, `vitpose_h_wholebody_model.onnx`, `yolov10m.onnx` +3 more) | ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, comfyui-easy-sam3, comfyui-easy-use, comfyui-kjnodes, comfyui-videohelpersuite, comfyui_layerstyle |
| [wan-2.2-animate-replace-character-and-background-24fps](wan-2.2-animate-replace-character-and-background-24fps.json) | Animate replace character and background 24fps | Wan 2.2 Animate 14B (`sam3.pt`, `vitpose_h_wholebody_model.onnx`, `yolov10m.onnx` +3 more) | ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, comfyui-easy-sam3, comfyui-easy-use, comfyui-kjnodes, comfyui-videohelpersuite, comfyui_layerstyle |
| [wan-2.2-animate-replace-character-and-background-24fps-hd](wan-2.2-animate-replace-character-and-background-24fps-hd.json) | Animate replace character and background 24fps hd | Wan 2.2 Animate 14B (`sam3.pt`, `vitpose_h_wholebody_model.onnx`, `yolov10m.onnx` +3 more) | ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, comfyui-easy-sam3, comfyui-easy-use, comfyui-kjnodes, comfyui-videohelpersuite, comfyui_layerstyle |
| [wan-2.2-animate-replace-only-character-16fps](wan-2.2-animate-replace-only-character-16fps.json) | Animate replace only character 16fps | Wan 2.2 Animate 14B (`sam3.pt`, `vitpose_h_wholebody_model.onnx`, `yolov10m.onnx` +3 more) | ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, comfyui-easy-sam3, comfyui-easy-use, comfyui-kjnodes, comfyui-videohelpersuite, comfyui_layerstyle |
| [wan-2.2-animate-replace-only-character-24fps](wan-2.2-animate-replace-only-character-24fps.json) | Animate replace only character 24fps | Wan 2.2 Animate 14B (`sam3.pt`, `vitpose_h_wholebody_model.onnx`, `yolov10m.onnx` +3 more) | ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, comfyui-easy-sam3, comfyui-easy-use, comfyui-kjnodes, comfyui-videohelpersuite, comfyui_layerstyle |

### SCAIL and SCAIL-2 character animation (12)

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [wan-2.1-scail-2-character-animation-from-driving-video-compact](wan-2.1-scail-2-character-animation-from-driving-video-compact.json) | Scail 2 character animation from driving video compact | SCAIL-2 (Wan 2.1 14B) (`clip_vision_h.safetensors`, `umt5_xxl_fp8_e4m3fn_scaled.safetensors`, `Wan2_1_VAE_bf16.safetensors`) | ComfyUI-Pixaroma, comfyui-kjnodes |
| [wan-2.1-scail-2-character-animation-from-driving-video-long](wan-2.1-scail-2-character-animation-from-driving-video-long.json) | Scail 2 character animation from driving video long | SCAIL-2 (Wan 2.1 14B) (`clip_vision_h.safetensors`, `Wan2_1_VAE_bf16.safetensors`, `umt5_xxl_fp8_e4m3fn_scaled.safetensors`) | ComfyUI-Pixaroma, comfyui-kjnodes |
| [wan-2.1-scail-2-character-replacement](wan-2.1-scail-2-character-replacement.json) | Scail 2 character replacement | SCAIL-2 (Wan 2.1 14B) (`wan2.1_14B_SCAIL_2_fp16.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more) | core only |
| [wan-2.1-scail-2-gap-hi-woman](wan-2.1-scail-2-gap-hi-woman.json) | Scail 2 gap hi woman | SCAIL-2 (Wan 2.1 14B) (`sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more) | wan-scail2-gap |
| [wan-2.1-scail-2-gap-multi-character-long](wan-2.1-scail-2-gap-multi-character-long.json) | Scail 2 gap multi character long | SCAIL-2 (Wan 2.1 14B) (`sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more) | core only |
| [wan-2.1-scail-2-gap-video-2](wan-2.1-scail-2-gap-video-2.json) | Scail 2 gap video 2 | SCAIL-2 (Wan 2.1 14B) (`sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more) | wan-scail2-gap |
| [wan-2.1-scail-2-gap-video-3-man](wan-2.1-scail-2-gap-video-3-man.json) | Scail 2 gap video 3 man | SCAIL-2 (Wan 2.1 14B) (`sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more) | wan-scail2-gap |
| [wan-2.1-scail-2-gap-video-4-man-closeup](wan-2.1-scail-2-gap-video-4-man-closeup.json) | Scail 2 gap video 4 man closeup | SCAIL-2 (Wan 2.1 14B) (`sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more) | wan-scail2-gap |
| [wan-2.1-scail-2-gap-video-5-man-head](wan-2.1-scail-2-gap-video-5-man-head.json) | Scail 2 gap video 5 man head | SCAIL-2 (Wan 2.1 14B) (`sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more) | wan-scail2-gap |
| [wan-2.1-scail-2-gap-video-6-man-head-fix](wan-2.1-scail-2-gap-video-6-man-head-fix.json) | Scail 2 gap video 6 man head fix | SCAIL-2 (Wan 2.1 14B) (`sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more) | wan-scail2-gap |
| [wan-2.1-scail-img2video-multi-character-9-16-ratio-only](wan-2.1-scail-img2video-multi-character-9-16-ratio-only.json) | Scail img2video multi character 9 16 ratio only | SCAIL (Wan 2.1 14B) (`wan_2.1_vae.safetensors`, `clip_vision_h.safetensors`, `Wan21_Uni3C_controlnet_fp16.safetensors` +5 more) | ComfyUI-SCAIL-Pose, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, comfyui-easy-use, comfyui-kjnodes, comfyui-videohelpersuite, comfyui_controlnet_aux |
| [wan-2.1-scail-img2video-single-character](wan-2.1-scail-img2video-single-character.json) | Scail img2video single character | SCAIL (Wan 2.1 14B) (`wan_2.1_vae.safetensors`, `clip_vision_h.safetensors`, `vitpose_h_wholebody_model.onnx` +3 more) | ComfyUI-SCAIL-Pose, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, comfyui-easy-use, comfyui-kjnodes, comfyui-videohelpersuite |

### MiniMax H3 character swap, head swap, restyle and face swap (28)

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [minimax-h3-cartoon-mascot-swap-reference-video](minimax-h3-cartoon-mascot-swap-reference-video.json) | Cartoon mascot swap reference video | MiniMax H3 (`qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`) | ComfyUI-Pixaroma |
| [minimax-h3-character-swap-lora](minimax-h3-character-swap-lora.json) | Character swap lora | MiniMax H3 (`qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`) | ComfyUI-Pixaroma |
| [minimax-h3-character-swap-lora-full-hd](minimax-h3-character-swap-lora-full-hd.json) | Character swap lora full hd | MiniMax H3 (`qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more) | ComfyUI-Pixaroma |
| [minimax-h3-character-swap-motion-guide-check-run08-api](minimax-h3-character-swap-motion-guide-check-run08-api.json) | Character swap motion guide check run08 | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`) | core only (API-format graph) |
| [minimax-h3-character-swap-motion-guide-check-run08-v2-api](minimax-h3-character-swap-motion-guide-check-run08-v2-api.json) | Character swap motion guide check run08 v2 | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`) | core only (API-format graph) |
| [minimax-h3-character-swap-sam3-mdmz-v1](minimax-h3-character-swap-sam3-mdmz-v1.json) | Character swap sam3 mdmz v1 | MiniMax H3 (`minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +3 more) | comfyui-unload-model, comfyui-videohelpersuite |
| [minimax-h3-character-swap-sam3-run01-480p-api](minimax-h3-character-swap-sam3-run01-480p-api.json) | Character swap sam3 run01 480p | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | core only (API-format graph) |
| [minimax-h3-character-swap-sam3-run02-480p-api](minimax-h3-character-swap-sam3-run02-480p-api.json) | Character swap sam3 run02 480p | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | core only (API-format graph) |
| [minimax-h3-character-swap-sam3-run03-480p-api](minimax-h3-character-swap-sam3-run03-480p-api.json) | Character swap sam3 run03 480p | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | core only (API-format graph) |
| [minimax-h3-character-swap-sam3-run04-480p-api](minimax-h3-character-swap-sam3-run04-480p-api.json) | Character swap sam3 run04 480p | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | core only (API-format graph) |
| [minimax-h3-character-swap-sam3-run05-480p-api](minimax-h3-character-swap-sam3-run05-480p-api.json) | Character swap sam3 run05 480p | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | core only (API-format graph) |
| [minimax-h3-character-swap-sam3-run05-720p-api](minimax-h3-character-swap-sam3-run05-720p-api.json) | Character swap sam3 run05 720p | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | core only (API-format graph) |
| [minimax-h3-character-swap-sam3-run06-720p-api](minimax-h3-character-swap-sam3-run06-720p-api.json) | Character swap sam3 run06 720p | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | core only (API-format graph) |
| [minimax-h3-character-swap-sam3-run07a-dance-720p-api](minimax-h3-character-swap-sam3-run07a-dance-720p-api.json) | Character swap sam3 run07a dance 720p | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | core only (API-format graph) |
| [minimax-h3-character-swap-sam3-run07b-talk-720p-api](minimax-h3-character-swap-sam3-run07b-talk-720p-api.json) | Character swap sam3 run07b talk 720p | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | core only (API-format graph) |
| [minimax-h3-character-swap-sam3-run08-duo-720p-api](minimax-h3-character-swap-sam3-run08-duo-720p-api.json) | Character swap sam3 run08 duo 720p | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | core only (API-format graph) |
| [minimax-h3-character-swap-sam3-run09-toons-720p-api](minimax-h3-character-swap-sam3-run09-toons-720p-api.json) | Character swap sam3 run09 toons 720p | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | core only (API-format graph) |
| [minimax-h3-character-swap-sam3-run10-faceswap-api](minimax-h3-character-swap-sam3-run10-faceswap-api.json) | Character swap sam3 run10 faceswap | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | core only (API-format graph) |
| [minimax-h3-character-swap-sam3-run11a-480p-api](minimax-h3-character-swap-sam3-run11a-480p-api.json) | Character swap sam3 run11a 480p | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | core only (API-format graph) |
| [minimax-h3-character-swap-sam3-run11b-480p-api](minimax-h3-character-swap-sam3-run11b-480p-api.json) | Character swap sam3 run11b 480p | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | core only (API-format graph) |
| [minimax-h3-character-swap-sam3-run11c-480p-api](minimax-h3-character-swap-sam3-run11c-480p-api.json) | Character swap sam3 run11c 480p | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | core only (API-format graph) |
| [minimax-h3-character-swap-sam3-run11c-720p-api](minimax-h3-character-swap-sam3-run11c-720p-api.json) | Character swap sam3 run11c 720p | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | core only (API-format graph) |
| [minimax-h3-head-swap-lora](minimax-h3-head-swap-lora.json) | Head swap lora | MiniMax H3 (`qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`) | ComfyUI-Pixaroma |
| [minimax-h3-pose-controlnet-motion-transfer](minimax-h3-pose-controlnet-motion-transfer.json) | Pose controlnet motion transfer | MiniMax H3 (`qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +3 more) | ComfyUI-Pixaroma |
| [minimax-h3-style-transfer-lora-restyle-video](minimax-h3-style-transfer-lora-restyle-video.json) | Style transfer lora restyle video | MiniMax H3 (`qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`) | ComfyUI-Pixaroma |
| [minimax-h3-vfx-edit-lora-outfit-from-pictures](minimax-h3-vfx-edit-lora-outfit-from-pictures.json) | Vfx edit lora outfit from pictures | MiniMax H3 (`qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`) | ComfyUI-Pixaroma |
| [minimax-h3-vfx-edit-lora-video-by-text](minimax-h3-vfx-edit-lora-video-by-text.json) | Vfx edit lora video by text | MiniMax H3 (`qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`) | ComfyUI-Pixaroma |
| [reactor-video-face-swap-api](reactor-video-face-swap-api.json) | Reactor video face swap | ReActor (inswapper_128) (`inswapper_128.onnx`, `codeformer-v0.1.0.pth`) | comfyui-reactor, comfyui-videohelpersuite |

## Sources, model downloads and licences (new workflows)

Workflow JSONs were copied unchanged from the sources below, whose code licences allow redistribution (Comfy-Org workflow_templates: MIT; kijai wrappers: Apache-2.0; Comfyui-MusePose and ComfyUI-AnimateAnyone-Evolved: MIT). The **weight licence is separate** from the workflow/code licence. None has been runtime-tested in this library. Use consented reference people and driving videos.

| Workflow | Source | Model download | Weight licence | Status |
|---|---|---|---|---|
| [wan-animate-2-motion-transfer-from-driving-video](wan-animate-2-motion-transfer-from-driving-video.json) | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan_animate2.json) | [weights](https://huggingface.co/Comfy-Org/Wan-Animate-2) | Apache-2.0 | not runtime-tested |
| [wan-2.1-steadydancer-first-frame-dance-animation](wan-2.1-steadydancer-first-frame-dance-animation.json) | [source](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/wanvideo_2_1_14B_SteadyDancer_pose_control_example_01.json) | [weights](https://huggingface.co/MCG-NJU/SteadyDancer-14B) | Apache-2.0 | not runtime-tested |
| [mimicmotion-pose-guided-human-animation](mimicmotion-pose-guided-human-animation.json) | [source](https://github.com/kijai/ComfyUI-MimicMotionWrapper/blob/main/examples/mimic_motion_example_02.json) | [weights](https://huggingface.co/tencent/MimicMotion) | **Custom Tencent licence** (restrictions; read model card) | not runtime-tested |
| [champ-3d-pose-guided-human-animation](champ-3d-pose-guided-human-animation.json) | [source](https://github.com/kijai/ComfyUI-champWrapper/blob/main/examples/motion_diff_champ_example_01.json) | [weights](https://huggingface.co/fudan-generative-ai/champ) | Apache-2.0 (+ SD 1.5 CreativeML OpenRAIL-M) | not runtime-tested |
| [musepose-pose-driven-dance-video](musepose-pose-driven-dance-video.json) | [source](https://github.com/TMElyralab/Comfyui-MusePose/blob/main/musepose-workflow-demo.json) | [weights](https://huggingface.co/TMElyralab/MusePose) | CreativeML OpenRAIL-M | not runtime-tested |
| [animate-anyone-evolved-pose-to-video](animate-anyone-evolved-pose-to-video.json) | [source](https://github.com/MrForExample/ComfyUI-AnimateAnyone-Evolved/blob/main/_Example_Workflow/MooreAnimateAnyone_DDIM.json) | [weights](https://huggingface.co/patrolli/AnimateAnyone) | Apache-2.0 (community reproduction, not the official Animate Anyone weights) | not runtime-tested |

## Open Video Model Atlas (Nov 2026) — character animation coverage

### Equivalent already exists (skipped as duplicates)

- SCAIL-2 character replacement template — identical graph to [`wan-2.1-scail-2-character-replacement`](wan-2.1-scail-2-character-replacement.json)
- SCAIL (v1) template and WanVideoWrapper SCAIL example — covered by `wan-2.1-scail-img2video-*`
- Wan 2.2 Animate native template, Purz auto character-replace template, WanAnimate wrapper example — same task as the `wan-2.2-animate-*` workflows
- Wan Animate 2 Distilled — distilled checkpoint of `wan-animate-2-motion-transfer-from-driving-video` (template: `video_wan_animate2_distilled`)
- One-to-All Animation, MTV-Crafter (WIP), MoCha subject replacement — same pose-transfer / replacement tasks as SCAIL-2, Wan Animate and SteadyDancer

### Not redistributed (link only)

- UniAnimate / Animate-X — community workflows exist at [Isi-dev/ComfyUI-UniAnimate-W](https://github.com/Isi-dev/ComfyUI-UniAnimate-W) but the repo has no licence file, so they are not copied here

### No ComfyUI workflow found

- Wan Dancer 14B — official repo has no ComfyUI integration yet
- Wan-Animate-2 Lite research variant — no released weights or graph
- MagicAnimate — ComfyUI node pack exists ([thecooltechguy/ComfyUI-MagicAnimate](https://github.com/thecooltechguy/ComfyUI-MagicAnimate)) but publishes no workflow JSON
- Animate Anyone (official HumanAIGC) — no official weights; the community reproduction above is the only ComfyUI route
- SkyReels-A1 portrait animation — ComfyUI listed as TODO in the official repo

See the [04-Video README](../README.md) for the other video categories.
