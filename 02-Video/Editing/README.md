# Video Editing — ComfyUI workflows

Workflows that change or analyse an existing video: VACE and instruction edits, inpaint / outpaint, object and subtitle removal, relighting, camera and motion control, character / head / face swap, motion transfer, lip-sync and dubbing, and supporting vision (depth, normals, pose, line art, segmentation).

[← 02-Video overview](../README.md) · [Library index](../../00-LIBRARY-INDEX.md)

**91 workflows** in **28 model folders**. Each model folder holds only workflow files; the file name says the task first, then the variant: `<task>[-<variant>][-<size>][-<precision>][-<feature>].json`. `Other/` holds generic or multi-model workflows.

## Model folders

| Model | Workflows | Tasks |
|---|---|---|
| [Animate-Anyone](#animate-anyone) | 1 | `motion-transfer` |
| [AnimateDiff](#animatediff) | 1 | `audio-reactive` |
| [Capybara](#capybara) | 1 | `edit` |
| [Champ](#champ) | 1 | `motion-transfer` |
| [Depth-Anything](#depth-anything) | 2 | `depth-map` |
| [DubSync](#dubsync) | 6 | `lip-sync` |
| [DWPose](#dwpose) | 1 | `pose-keypoints` |
| [LatentSync](#latentsync) | 1 | `lip-sync` |
| [LivePortrait](#liveportrait) | 1 | `expression-retarget` |
| [LTX-2](#ltx-2) | 6 | `lip-sync`, `object-removal`, `voice-dubbing` |
| [MimicMotion](#mimicmotion) | 1 | `motion-transfer` |
| [MiniMax-H3](#minimax-h3) | 27 | `character-swap`, `head-swap`, `motion-transfer`, `style-transfer`, `vfx-edit` |
| [MusePose](#musepose) | 1 | `motion-transfer` |
| [MuseTalk](#musetalk) | 1 | `lip-sync` |
| [NormalCrafter](#normalcrafter) | 1 | `normal-map` |
| [ProPainter](#propainter) | 1 | `object-removal` |
| [ReActor](#reactor) | 1 | `face-swap` |
| [SAM-2](#sam-2) | 1 | `segment` |
| [SAM-3](#sam-3) | 1 | `segment` |
| [SDPose](#sdpose) | 1 | `pose-keypoints` |
| [Video-Depth-Anything](#video-depth-anything) | 1 | `depth-map` |
| [VOID](#void) | 1 | `object-and-interaction-removal` |
| [Wan-2.1](#wan-21) | 19 | `camera-rerender`, `character-swap`, `expression-transfer`, `inpaint`, `lip-sync`, `motion-transfer`, `outpaint`, `v2v` |
| [Wan-2.2](#wan-22) | 8 | `camera-control`, `character-swap`, `relight`, `v2v` |
| [Wan-Animate-2](#wan-animate-2) | 1 | `motion-transfer` |
| [Wan-Move](#wan-move) | 1 | `motion-control` |
| [Wav2Lip](#wav2lip) | 1 | `lip-sync` |
| [Other](#other) | 2 | `lineart-extraction`, `pixaroma` |

## Animate-Anyone

Folder: [`Animate-Anyone/`](Animate-Anyone) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [motion-transfer-evolved-pose-to-video](Animate-Anyone/motion-transfer-evolved-pose-to-video.json) | ReferenceNet + pose guider character animation (Moore-AnimateAnyone reproduction) | [weights](https://huggingface.co/patrolli/AnimateAnyone) | ComfyUI-AnimateAnyone-Evolved, ComfyUI-VideoHelperSuite | Model: Moore-AnimateAnyone (SD 1.5 based); Source: [source](https://github.com/MrForExample/ComfyUI-AnimateAnyone-Evolved/blob/main/_Example_Workflow/MooreAnimateAnyone_DDIM.json); Code licence: MIT; Weight licence: Apache-2.0 (community reproduction, not the official Animate Anyone weights); Status: not runtime-tested |

## AnimateDiff

Folder: [`AnimateDiff/`](AnimateDiff) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [audio-reactive-v2v](AnimateDiff/audio-reactive-v2v.json) | AnimateDiff video-to-video restyle where the strength and the IPAdapter pictures follow the audio (Yvann-Nodes example) | [AnimateLCM](https://huggingface.co/wangfuyun/AnimateLCM), [AnimateDiff v3](https://huggingface.co/guoyww/animatediff), SD1.5 checkpoints (DreamShaper 8), [QR Code Monster](https://huggingface.co/monster-labs/control_v1p_sd15_qrcode_monster) | ComfyUI-Advanced-ControlNet, ComfyUI-AnimateDiff-Evolved, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI_IPAdapter_plus, ComfyUI_Yvann-Nodes, comfyui_controlnet_aux | Model: `AnimateLCM_sd15_t2v.ckpt`, `LiquidAF-0-1.safetensors`, `2x-sudo-UltraCompact.pth` +7 more; Source: [yvann-ba/ComfyUI_Yvann-Nodes](https://github.com/yvann-ba/ComfyUI_Yvann-Nodes/tree/main/example_workflows); Code licence: GPL-3.0; Weight licence: Apache-2.0 (AnimateDiff/AnimateLCM); SD1.5 checkpoints CreativeML OpenRAIL-M; Status: not runtime-tested |

## Capybara

Folder: [`Capybara/`](Capybara) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [edit-v01-instruction](Capybara/edit-v01-instruction.json) | Edit a video with a plain-language instruction | [weights](https://huggingface.co/Comfy-Org/HunyuanVideo_1.5_repackaged) | Core only | Model: Capybara v0.1 (HunyuanVideo 1.5 based); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_capybara_v0_1_video_edit.json); Code licence: MIT; Weight licence: Weights: check Capybara model card (not confirmed); Status: not runtime-tested |

## Champ

Folder: [`Champ/`](Champ) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [motion-transfer-3d-pose-guided](Champ/motion-transfer-3d-pose-guided.json) | Human animation guided by SMPL depth, normal, DensePose and skeleton maps | [weights](https://huggingface.co/fudan-generative-ai/champ) | ComfyUI-champWrapper, ComfyUI-KJNodes, comfyui_controlnet_aux, ComfyUI_essentials, rgthree-comfy, ComfyUI-VideoHelperSuite (+ SMPL/4D-Humans nodes) | Model: Champ (SD 1.5 based); Source: [source](https://github.com/kijai/ComfyUI-champWrapper/blob/main/examples/motion_diff_champ_example_01.json); Code licence: Apache-2.0; Weight licence: Apache-2.0 (+ SD 1.5 CreativeML OpenRAIL-M); Status: not runtime-tested |

## Depth-Anything

Folder: [`Depth-Anything/`](Depth-Anything) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [depth-map-v2-video](Depth-Anything/depth-map-v2-video.json) | Depth Anything V2 relative depth, frame by frame | [Kijai/DepthAnythingV2-safetensors](https://huggingface.co/Kijai/DepthAnythingV2-safetensors) | ComfyUI-DepthAnythingV2, ComfyUI-VideoHelperSuite | Model: `depth_anything_v2_vitl_fp32.safetensors`; Source: [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates); Code licence: MIT; Weight licence: ViT-L: **CC-BY-NC-4.0 (non-commercial)**; ViT-S: Apache-2.0; Status: not runtime-tested |
| [depth-map-v3-video](Depth-Anything/depth-map-v3-video.json) | Depth Anything 3 (mono large) depth on video frames with built-in DA3 nodes | [Comfy-Org/Depth-Anything-3](https://huggingface.co/Comfy-Org/Depth-Anything-3) | — (core ComfyUI) | Model: `depth_anything_3_mono_large.safetensors`; Source: [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates); Code licence: MIT; Weight licence: Apache-2.0 (mono large); Status: not runtime-tested |

## DubSync

Folder: [`DubSync/`](DubSync) — 6 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [lip-sync-hindi-simple-api](DubSync/lip-sync-hindi-simple-api.json) | One-node DubSync lip-sync (API format) | — | DubSync nodes | — |
| [lip-sync-hindi-simple](DubSync/lip-sync-hindi-simple.json) | One-node DubSync lip-sync: video + dubbed audio in, lip-synced video out | — | DubSync nodes | — |
| [lip-sync-latentsync-api](DubSync/lip-sync-latentsync-api.json) | DubSync + LatentSync lip-sync (API format) | — | DubSync nodes | — |
| [lip-sync-latentsync-single-shot](DubSync/lip-sync-latentsync-single-shot.json) | DubSync + LatentSync lip-sync for a single shot (load video and audio, sync, save) | — | DubSync nodes | — |
| [lip-sync-tbdub-teacher-api](DubSync/lip-sync-tbdub-teacher-api.json) | TBDub Teacher lip-sync (API format) | — | DubSync nodes | — |
| [lip-sync-tbdub-teacher-single-shot](DubSync/lip-sync-tbdub-teacher-single-shot.json) | Best-quality 30-step TBDub Teacher lip-sync for one shot with one visible speaker | — | DubSync nodes | — |

## DWPose

Folder: [`DWPose/`](DWPose) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [pose-keypoints-video](DWPose/pose-keypoints-video.json) | DWPose (OpenPose-style) skeletons for every frame | [yzd-v/DWPose](https://huggingface.co/yzd-v/DWPose) | comfyui_controlnet_aux, ComfyUI-VideoHelperSuite | Model: `dw-ll_ucoco_384_bs5.torchscript.pt`, `yolox_l.onnx`; Source: [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |

## LatentSync

Folder: [`LatentSync/`](LatentSync) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [lip-sync-hindi-dubbing](LatentSync/lip-sync-hindi-dubbing.json) | Lip-sync an existing video to a new dubbed voice track (e.g. Hindi) with LatentSync | — | DubSync nodes | — |

## LivePortrait

Folder: [`LivePortrait/`](LivePortrait) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [expression-retarget-video](LivePortrait/expression-retarget-video.json) | LivePortrait video-to-video: retarget expressions from a driving video onto a source video | [Kijai/LivePortrait_safetensors](https://huggingface.co/Kijai/LivePortrait_safetensors) (auto-download) | ComfyUI-KJNodes, ComfyUI-LivePortraitKJ, ComfyUI-VideoHelperSuite, ComfyUI_essentials | Source: [kijai/ComfyUI-LivePortraitKJ](https://github.com/kijai/ComfyUI-LivePortraitKJ/tree/main/examples); Code licence: MIT; Weight licence: MIT; the InsightFace cropper is **non-commercial** — use the MediaPipe cropper for commercial work; Status: not runtime-tested |

## LTX-2

Folder: [`LTX-2/`](LTX-2) — 6 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [lip-sync-own-audio](LTX-2/lip-sync-own-audio.json) | LTX-2 lip-sync a shot to your audio (with voice conversion) | `LTX2_video_vae_bf16_KJ.safetensors`, `LTX2_audio_vae_bf16_KJ.safetensors`, `ltx-2-spatial-upscaler-x2-1.0.safetensors` +7 more | ComfyUI-ChatterboxTTS, ComfyUI-GGUF, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, rgthree-comfy | — |
| [object-removal-v23-lora-subtitles](LTX-2/object-removal-v23-lora-subtitles.json) | Remove burned-in subtitles and text overlays from your own footage | [weights](https://huggingface.co/Lightricks/LTX-2.3) | ComfyUI-LTXVideo, ComfyUI-KJNodes | Model: LTX-2.3 22B + subtitle-removal IC-LoRA; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/template_ltx2_3_lora_remove_subtitles_from_video.json); Code licence: MIT; Weight licence: **LTX-2 Community License** (custom; commercial limits); Status: not runtime-tested |
| [object-removal-v23-obscura-lora](LTX-2/object-removal-v23-obscura-lora.json) | Text-prompted object removal without drawing a mask | [weights](https://huggingface.co/Lightricks/LTX-2.3) | ComfyUI-LTXVideo, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite | Model: LTX-2.3 22B + Obscura Remova IC-LoRA; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/template_ltx2_3_obscura_remova_lora_remove_object_from_video.json); Code licence: MIT; Weight licence: **LTX-2 Community License** (custom; commercial limits); Status: not runtime-tested |
| [voice-dubbing-1080p-runpod](LTX-2/voice-dubbing-1080p-runpod.json) | Video to Video — Voice Dubbing — RunPod 1080p | `LTX2_video_vae_bf16_KJ.safetensors`, `LTX2_audio_vae_bf16_KJ.safetensors`, `ltx-2-spatial-upscaler-x2-1.0.safetensors` +10 more | ComfyUI-ChatterboxTTS, ComfyUI-GGUF, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, rgthree-comfy | — |
| [voice-dubbing-compact](LTX-2/voice-dubbing-compact.json) | Video to Video — Voice Dubbing — Compact | `LTX2_video_vae_bf16_KJ.safetensors`, `LTX2_audio_vae_bf16_KJ.safetensors`, `ltx-2-spatial-upscaler-x2-1.0.safetensors` +10 more | ComfyUI-ChatterboxTTS, ComfyUI-GGUF, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, rgthree-comfy | — |
| [voice-dubbing](LTX-2/voice-dubbing.json) | LTX-2 video-to-video voice dubbing | `LTX2_video_vae_bf16_KJ.safetensors`, `LTX2_audio_vae_bf16_KJ.safetensors`, `ltx-2-spatial-upscaler-x2-1.0.safetensors` +10 more | ComfyUI-ChatterboxTTS, ComfyUI-GGUF, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, rgthree-comfy | — |

## MimicMotion

Folder: [`MimicMotion/`](MimicMotion) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [motion-transfer-pose-guided](MimicMotion/motion-transfer-pose-guided.json) | Reference image + pose sequence from a video to a human video | [weights](https://huggingface.co/tencent/MimicMotion) | ComfyUI-MimicMotionWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite | Model: MimicMotion 1.0 (SVD based); Source: [source](https://github.com/kijai/ComfyUI-MimicMotionWrapper/blob/main/examples/mimic_motion_example_02.json); Code licence: Apache-2.0; Weight licence: **Custom Tencent licence** (restrictions; read model card); Status: not runtime-tested |

## MiniMax-H3

Folder: [`MiniMax-H3/`](MiniMax-H3) — 27 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [character-swap-cartoon-mascot](MiniMax-H3/character-swap-cartoon-mascot.json) | Minimax H3 - Cartoon and Mascot Swap with Reference Video (Ep41) | MiniMax H3 (`qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`) | ComfyUI-Pixaroma | — |
| [character-swap-lora-1080p](MiniMax-H3/character-swap-lora-1080p.json) | Minimax H3 - Character Swap LoRA + Upscale to Full HD (Ep41) | MiniMax H3 (`qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more) | ComfyUI-Pixaroma | — |
| [character-swap-lora](MiniMax-H3/character-swap-lora.json) | Minimax H3 - Character Swap LoRA (Ep41) | MiniMax H3 (`qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`) | ComfyUI-Pixaroma | — |
| [character-swap-motion-guide-api](MiniMax-H3/character-swap-motion-guide-api.json) | SAM3 motion-guide preview for the H3 character swap (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`) | Core only (API-format graph) | — |
| [character-swap-motion-guide-v2-api](MiniMax-H3/character-swap-motion-guide-v2-api.json) | SAM3 motion-guide preview for the H3 character swap (v2) (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`) | Core only (API-format graph) | — |
| [character-swap-sam3-mdmz](MiniMax-H3/character-swap-sam3-mdmz.json) | Character swap / motion transfer: SAM3 masks the person, MiniMax H3 regenerates the shot with your character (Gemini prompt helper) | MiniMax H3 (`minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +3 more) | comfyui-unload-model, comfyui-videohelpersuite | — |
| [character-swap-sam3-run01-480p-api](MiniMax-H3/character-swap-sam3-run01-480p-api.json) | MiniMax H3 character swap run 01 (480p): SAM3 mask + reference-to-video (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | Core only (API-format graph) | — |
| [character-swap-sam3-run02-480p-api](MiniMax-H3/character-swap-sam3-run02-480p-api.json) | MiniMax H3 character swap run 02 (480p): SAM3 mask + reference-to-video (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | Core only (API-format graph) | — |
| [character-swap-sam3-run03-480p-api](MiniMax-H3/character-swap-sam3-run03-480p-api.json) | MiniMax H3 character swap run 03 (480p): SAM3 mask + reference-to-video (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | Core only (API-format graph) | — |
| [character-swap-sam3-run04-480p-api](MiniMax-H3/character-swap-sam3-run04-480p-api.json) | MiniMax H3 character swap run 04 (480p): SAM3 mask + reference-to-video (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | Core only (API-format graph) | — |
| [character-swap-sam3-run05-480p-api](MiniMax-H3/character-swap-sam3-run05-480p-api.json) | MiniMax H3 character swap run 05 (480p): SAM3 mask + reference-to-video (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | Core only (API-format graph) | — |
| [character-swap-sam3-run05-720p-api](MiniMax-H3/character-swap-sam3-run05-720p-api.json) | MiniMax H3 character swap run 05 (720p): SAM3 mask + reference-to-video (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | Core only (API-format graph) | — |
| [character-swap-sam3-run06-720p-api](MiniMax-H3/character-swap-sam3-run06-720p-api.json) | MiniMax H3 character swap run 06 (720p): SAM3 mask + reference-to-video (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | Core only (API-format graph) | — |
| [character-swap-sam3-run07a-720p-dance-api](MiniMax-H3/character-swap-sam3-run07a-720p-dance-api.json) | MiniMax H3 character swap run 07A (dance 720p): SAM3 mask + reference-to-video (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | Core only (API-format graph) | — |
| [character-swap-sam3-run07b-720p-talk-api](MiniMax-H3/character-swap-sam3-run07b-720p-talk-api.json) | MiniMax H3 character swap run 07B (talk 720p): SAM3 mask + reference-to-video (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | Core only (API-format graph) | — |
| [character-swap-sam3-run08-720p-duo-api](MiniMax-H3/character-swap-sam3-run08-720p-duo-api.json) | MiniMax H3 character swap run 08 (duo 720p): SAM3 mask + reference-to-video (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | Core only (API-format graph) | — |
| [character-swap-sam3-run09-720p-toons-api](MiniMax-H3/character-swap-sam3-run09-720p-toons-api.json) | MiniMax H3 character swap run 09 (toons 720p): SAM3 mask + reference-to-video (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | Core only (API-format graph) | — |
| [character-swap-sam3-run10-faceswap-api](MiniMax-H3/character-swap-sam3-run10-faceswap-api.json) | MiniMax H3 character swap run 10 (faceswap): SAM3 mask + reference-to-video (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | Core only (API-format graph) | — |
| [character-swap-sam3-run11a-480p-api](MiniMax-H3/character-swap-sam3-run11a-480p-api.json) | MiniMax H3 character swap run 11A (480p): SAM3 mask + reference-to-video (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | Core only (API-format graph) | — |
| [character-swap-sam3-run11b-480p-api](MiniMax-H3/character-swap-sam3-run11b-480p-api.json) | MiniMax H3 character swap run 11B (480p): SAM3 mask + reference-to-video (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | Core only (API-format graph) | — |
| [character-swap-sam3-run11c-480p-api](MiniMax-H3/character-swap-sam3-run11c-480p-api.json) | MiniMax H3 character swap run 11C (480p): SAM3 mask + reference-to-video (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | Core only (API-format graph) | — |
| [character-swap-sam3-run11c-720p-api](MiniMax-H3/character-swap-sam3-run11c-720p-api.json) | MiniMax H3 character swap run 11C (720p): SAM3 mask + reference-to-video (API format) | MiniMax H3 (`sam3.1_multiplex_fp16.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more) | Core only (API-format graph) | — |
| [head-swap-lora](MiniMax-H3/head-swap-lora.json) | Minimax H3 - Head Swap LoRA (Ep41) | MiniMax H3 (`qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`) | ComfyUI-Pixaroma | — |
| [motion-transfer-pose-controlnet](MiniMax-H3/motion-transfer-pose-controlnet.json) | Minimax H3 - Pose ControlNet - Motion Transfer (Ep41) | MiniMax H3 (`qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +3 more) | ComfyUI-Pixaroma | — |
| [style-transfer-lora](MiniMax-H3/style-transfer-lora.json) | Minimax H3 - Style Transfer LoRA - Restyle a Video (Ep41) | MiniMax H3 (`qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`) | ComfyUI-Pixaroma | — |
| [vfx-edit-lora-by-text](MiniMax-H3/vfx-edit-lora-by-text.json) | Minimax H3 - VFX Edit LoRA - Edit a Video by Text (Ep41) | MiniMax H3 (`qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`) | ComfyUI-Pixaroma | — |
| [vfx-edit-lora-outfit-from-pictures](MiniMax-H3/vfx-edit-lora-outfit-from-pictures.json) | Minimax H3 - VFX Edit LoRA - Change the Outfit from Pictures (Ep41) | MiniMax H3 (`qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`) | ComfyUI-Pixaroma | — |

## MusePose

Folder: [`MusePose/`](MusePose) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [motion-transfer-pose-driven-dance](MusePose/motion-transfer-pose-driven-dance.json) | Align a dance pose video to a reference image and render the dance | [weights](https://huggingface.co/TMElyralab/MusePose) | Comfyui-MusePose, ComfyUI-VideoHelperSuite | Model: MusePose (SD image-variations based); Source: [source](https://github.com/TMElyralab/Comfyui-MusePose/blob/main/musepose-workflow-demo.json); Code licence: MIT; Weight licence: CreativeML OpenRAIL-M; Status: not runtime-tested |

## MuseTalk

Folder: [`MuseTalk/`](MuseTalk) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [lip-sync](MuseTalk/lip-sync.json) | MuseTalk: re-sync mouth of an existing video to new audio (paths in the graph are the author's; point them at your files) | [TMElyralab/MuseTalk](https://huggingface.co/TMElyralab/MuseTalk) | ComfyUI-MuseTalk, ComfyUI-VideoHelperSuite | Source: [chaojie/ComfyUI-MuseTalk](https://github.com/chaojie/ComfyUI-MuseTalk/blob/main/wf.json); Code licence: MIT; Weight licence: MIT (whisper, sd-vae, dwpose have own terms); Status: not runtime-tested |

## NormalCrafter

Folder: [`NormalCrafter/`](NormalCrafter) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [normal-map-video](NormalCrafter/normal-map-video.json) | NormalCrafter temporally consistent surface-normal video | [Yanrui95/NormalCrafter](https://huggingface.co/Yanrui95/NormalCrafter) | ComfyUI-NormalCrafterWrapper, ComfyUI-VideoHelperSuite | Model: NormalCrafter (auto-downloaded); Source: [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |

## ProPainter

Folder: [`ProPainter/`](ProPainter) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [object-removal](ProPainter/object-removal.json) | Flow-guided video inpainting: remove a masked object or complete missing regions | [ProPainter](https://github.com/sczhou/ProPainter) (weights download on first run) | ComfyUI_ProPainter_Nodes, ComfyUI-VideoHelperSuite, ComfyUI_essentials | Model: ProPainter; Source: [source](https://github.com/daniabib/ComfyUI_ProPainter_Nodes/blob/main/examples/propainter-inpainting-workflow.json); Code licence: GPL-3.0; Weight licence: **Non-commercial** (NTU S-Lab License 1.0); node pack GPL-3.0; Status: not runtime-tested |

## ReActor

Folder: [`ReActor/`](ReActor) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [face-swap-api](ReActor/face-swap-api.json) | Face swap on every frame of a video with ReActor + CodeFormer restore (API format) | ReActor (inswapper_128) (`inswapper_128.onnx`, `codeformer-v0.1.0.pth`) | comfyui-reactor, comfyui-videohelpersuite | — |

## SAM-2

Folder: [`SAM-2/`](SAM-2) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [segment-points-video](SAM-2/segment-points-video.json) | SAM 2 click-point segmentation propagated through a video | [Kijai/sam2-safetensors](https://huggingface.co/Kijai/sam2-safetensors) | ComfyUI-segment-anything-2, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-Custom-Scripts | Model: `sam2_hiera_base_plus.safetensors`; Source: [kijai/ComfyUI-segment-anything-2](https://github.com/kijai/ComfyUI-segment-anything-2); Code licence: Apache-2.0; Weight licence: Apache-2.0; Status: not runtime-tested |

## SAM-3

Folder: [`SAM-3/`](SAM-3) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [segment-text-prompt-video](SAM-3/segment-text-prompt-video.json) | SAM 3.1 video masks from a text prompt (e.g. `person:2`) with built-in nodes | [Comfy-Org/sam3.1](https://huggingface.co/Comfy-Org/sam3.1) | — (core ComfyUI) | Model: `sam3.1_multiplex_fp16.safetensors`; Source: [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates); Code licence: MIT; Weight licence: **SAM License (custom Meta licence)**; Status: not runtime-tested |

## SDPose

Folder: [`SDPose/`](SDPose) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [pose-keypoints-multi-person-video](SDPose/pose-keypoints-multi-person-video.json) | SDPose whole-body keypoints for several people (RT-DETR person detection) | [Comfy-Org/SDPose](https://huggingface.co/Comfy-Org/SDPose) | — (core ComfyUI) | Model: `sdpose_wholebody_fp16.safetensors`, `rt_detr_v4-x-hgnet_fp16.safetensors`; Source: [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates); Code licence: MIT; Weight licence: SDPose: MIT; RT-DETR: check upstream; Status: not runtime-tested |

## Video-Depth-Anything

Folder: [`Video-Depth-Anything/`](Video-Depth-Anything) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [depth-map-video](Video-Depth-Anything/depth-map-video.json) | Video Depth Anything: temporally consistent depth for long videos, saves video and EXR | [depth-anything/Video-Depth-Anything-Large](https://huggingface.co/depth-anything/Video-Depth-Anything-Large) / [-Small](https://huggingface.co/depth-anything/Video-Depth-Anything-Small) | ComfyUI-Video-Depth-Anything, ComfyUI-VideoHelperSuite | Model: `video_depth_anything_vitl.pth`; Source: [yuvraj108c/ComfyUI-Video-Depth-Anything](https://github.com/yuvraj108c/ComfyUI-Video-Depth-Anything); Code licence: Apache-2.0; Weight licence: Large: **CC-BY-NC-4.0 (non-commercial)**; Small: Apache-2.0; Status: not runtime-tested |

## VOID

Folder: [`VOID/`](VOID) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [object-and-interaction-removal](VOID/object-and-interaction-removal.json) | Remove an object and its physical effects (shadows, reflections, interactions) from a video | [weights](https://huggingface.co/Comfy-Org/void-model) | Core only | Model: VOID (CogVideoX-based) + SAM 3.1 + RAFT; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/utility_void_video_inpainting.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |

## Wan-2.1

Folder: [`Wan-2.1/`](Wan-2.1) — 19 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [camera-rerender-recammaster-13b](Wan-2.1/camera-rerender-recammaster-13b.json) | Re-shoot an existing video along a new camera trajectory | [weights](https://huggingface.co/Kijai/WanVideo_comfy) | ComfyUI-WanVideoWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-Florence2, ComfyUI-Custom-Scripts | Model: ReCamMaster (Wan 2.1 1.3B); Source: [source](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/wanvideo_1_3B_ReCamMaster_example_01.json); Code licence: Apache-2.0; Weight licence: Weights: check KwaiVGI ReCamMaster model card (not confirmed); Status: not runtime-tested |
| [character-swap-scail-2](Wan-2.1/character-swap-scail-2.json) | Scail 2 character replacement | SCAIL-2 (Wan 2.1 14B) (`wan2.1_14B_SCAIL_2_fp16.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more) | Core only | — |
| [expression-transfer-fantasyportrait](Wan-2.1/expression-transfer-fantasyportrait.json) | FantasyPortrait: facial expression transfer from a driving video on Wan 2.1 I2V (WanVideoWrapper example) | [acvlab/FantasyPortrait](https://huggingface.co/acvlab/FantasyPortrait), [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy) | ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper | Model: `Wan2_1_VAE_bf16.safetensors`, `clip_vision_h.safetensors`, `Wan2_1_FantasyPortrait_fp16.safetensors` +3 more; Source: [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/wanvideo_2_1_14B_I2V_FantasyPortrait_example_01.json); Code licence: Apache-2.0; Weight licence: Apache-2.0 (verify model card); Status: not runtime-tested |
| [inpaint-vace-14b](Wan-2.1/inpaint-vace-14b.json) | Masked video-to-video: replace or remove an object inside a SAM 3.1 mask | [weights](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged) | Core only | Model: Wan2.1 VACE 14B + SAM 3.1; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan_vace_inpainting.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |
| [lip-sync-infinitetalk-dubbing-v2v-flat](Wan-2.1/lip-sync-infinitetalk-dubbing-v2v-flat.json) | Flattened single-path version of the InfiniteTalk video dubbing workflow | `clip_vision_h.safetensors`, `Wan2_1-I2V-14B-720P_fp8_e4m3fn.safetensors`, `Wan21_I2V_14B_lightx2v_cfg_step_distill_lora_rank64.safetensors` +3 more | ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, comfy-mtb, comfyui-custom-scripts, comfyui_layerstyle | — |
| [lip-sync-infinitetalk-dubbing-v2v](Wan-2.1/lip-sync-infinitetalk-dubbing-v2v.json) | Video dubbing (video2video): Wan 2.1 InfiniteTalk re-animates the speaker to a new audio track, TTS or text | `clip_vision_h.safetensors`, `Wan2_1-I2V-14B-720P_fp8_e4m3fn.safetensors`, `Wan21_I2V_14B_lightx2v_cfg_step_distill_lora_rank64.safetensors` +3 more | ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, comfy-mtb, comfyui-custom-scripts, comfyui_layerstyle, rgthree-comfy | — |
| [lip-sync-infinitetalk-v2v-basic-single](Wan-2.1/lip-sync-infinitetalk-v2v-basic-single.json) | Talking avatar generator: drive a video with an audio file, TTS or typed text using Wan 2.1 InfiniteTalk | `clip_vision_h.safetensors`, `Wan2_1-I2V-14B-720P_fp8_e4m3fn.safetensors`, `Wan21_I2V_14B_lightx2v_cfg_step_distill_lora_rank64.safetensors` +3 more | ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, audio-separation-nodes-comfyui, chatterbox_srt_voice, comfy-mtb, comfyui-custom-scripts, comfyui_layerstyle, rgthree-comfy | — |
| [motion-transfer-scail-2-driving-video-compact](Wan-2.1/motion-transfer-scail-2-driving-video-compact.json) | Scail 2 character animation from driving video compact | SCAIL-2 (Wan 2.1 14B) (`clip_vision_h.safetensors`, `umt5_xxl_fp8_e4m3fn_scaled.safetensors`, `Wan2_1_VAE_bf16.safetensors`) | ComfyUI-Pixaroma, comfyui-kjnodes | — |
| [motion-transfer-scail-2-driving-video-long](Wan-2.1/motion-transfer-scail-2-driving-video-long.json) | Scail 2 character animation from driving video long | SCAIL-2 (Wan 2.1 14B) (`clip_vision_h.safetensors`, `Wan2_1_VAE_bf16.safetensors`, `umt5_xxl_fp8_e4m3fn_scaled.safetensors`) | ComfyUI-Pixaroma, comfyui-kjnodes | — |
| [motion-transfer-scail-2-gap-hi-woman](Wan-2.1/motion-transfer-scail-2-gap-hi-woman.json) | Scail 2 gap hi woman | SCAIL-2 (Wan 2.1 14B) (`sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more) | wan-scail2-gap | — |
| [motion-transfer-scail-2-gap-multi-character-long](Wan-2.1/motion-transfer-scail-2-gap-multi-character-long.json) | Scail 2 gap multi character long | SCAIL-2 (Wan 2.1 14B) (`sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more) | Core only | — |
| [motion-transfer-scail-2-gap-video-2](Wan-2.1/motion-transfer-scail-2-gap-video-2.json) | Scail 2 gap video 2 | SCAIL-2 (Wan 2.1 14B) (`sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more) | wan-scail2-gap | — |
| [motion-transfer-scail-2-gap-video-3-man](Wan-2.1/motion-transfer-scail-2-gap-video-3-man.json) | Scail 2 gap video 3 man | SCAIL-2 (Wan 2.1 14B) (`sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more) | wan-scail2-gap | — |
| [motion-transfer-scail-2-gap-video-4-man-closeup](Wan-2.1/motion-transfer-scail-2-gap-video-4-man-closeup.json) | Scail 2 gap video 4 man closeup | SCAIL-2 (Wan 2.1 14B) (`sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more) | wan-scail2-gap | — |
| [motion-transfer-scail-2-gap-video-5-man-head](Wan-2.1/motion-transfer-scail-2-gap-video-5-man-head.json) | Scail 2 gap video 5 man head | SCAIL-2 (Wan 2.1 14B) (`sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more) | wan-scail2-gap | — |
| [motion-transfer-scail-2-gap-video-6-man-head-fix](Wan-2.1/motion-transfer-scail-2-gap-video-6-man-head-fix.json) | Scail 2 gap video 6 man head fix | SCAIL-2 (Wan 2.1 14B) (`sam3.1_multiplex_fp16.safetensors`, `wan2.1_14B_SCAIL_2_fp8_scaled.safetensors`, `wan2.1_SCAIL_2_DPO_lora_bf16.safetensors` +4 more) | wan-scail2-gap | — |
| [motion-transfer-steadydancer-first-frame-dance](Wan-2.1/motion-transfer-steadydancer-first-frame-dance.json) | Pose-driven dance animation that keeps the reference image as the first frame | [weights](https://huggingface.co/MCG-NJU/SteadyDancer-14B) | ComfyUI-WanVideoWrapper, ComfyUI-WanAnimatePreprocess, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite | Model: SteadyDancer 14B (Wan 2.1); Source: [source](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/wanvideo_2_1_14B_SteadyDancer_pose_control_example_01.json); Code licence: Apache-2.0; Weight licence: Apache-2.0; Status: not runtime-tested |
| [outpaint-vace-14b](Wan-2.1/outpaint-vace-14b.json) | Extend the frame of an existing video (pad and fill new borders) | [weights](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged) | Core only | Model: Wan2.1 VACE 14B; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan_vace_outpainting.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |
| [v2v-vace-14b-control](Wan-2.1/v2v-vace-14b-control.json) | Video-to-video driven by a control video (Canny/depth/pose) plus a reference image | [weights](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged) | Core only | Model: Wan2.1 VACE 14B; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan_vace_14B_v2v.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |

## Wan-2.2

Folder: [`Wan-2.2/`](Wan-2.2) — 8 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [camera-control-fun-14b](Wan-2.2/camera-control-fun-14b.json) | Image-to-video with preset camera moves (pan, zoom, orbit) | [weights](https://huggingface.co/alibaba-pai/Wan2.2-Fun-A14B-Control-Camera) | Core only | Model: Wan2.2 Fun Control-Camera A14B; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan2_2_14B_fun_camera.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |
| [character-swap-animate-character-and-background-16fps](Wan-2.2/character-swap-animate-character-and-background-16fps.json) | Animate replace character and background 16fps | Wan 2.2 Animate 14B (`sam3.pt`, `vitpose_h_wholebody_model.onnx`, `yolov10m.onnx` +3 more) | ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, comfyui-easy-sam3, comfyui-easy-use, comfyui-kjnodes, comfyui-videohelpersuite, comfyui_layerstyle | — |
| [character-swap-animate-character-and-background-24fps-hd](Wan-2.2/character-swap-animate-character-and-background-24fps-hd.json) | Animate replace character and background 24fps hd | Wan 2.2 Animate 14B (`sam3.pt`, `vitpose_h_wholebody_model.onnx`, `yolov10m.onnx` +3 more) | ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, comfyui-easy-sam3, comfyui-easy-use, comfyui-kjnodes, comfyui-videohelpersuite, comfyui_layerstyle | — |
| [character-swap-animate-character-and-background-24fps](Wan-2.2/character-swap-animate-character-and-background-24fps.json) | Animate replace character and background 24fps | Wan 2.2 Animate 14B (`sam3.pt`, `vitpose_h_wholebody_model.onnx`, `yolov10m.onnx` +3 more) | ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, comfyui-easy-sam3, comfyui-easy-use, comfyui-kjnodes, comfyui-videohelpersuite, comfyui_layerstyle | — |
| [character-swap-animate-only-character-16fps](Wan-2.2/character-swap-animate-only-character-16fps.json) | Animate replace only character 16fps | Wan 2.2 Animate 14B (`sam3.pt`, `vitpose_h_wholebody_model.onnx`, `yolov10m.onnx` +3 more) | ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, comfyui-easy-sam3, comfyui-easy-use, comfyui-kjnodes, comfyui-videohelpersuite, comfyui_layerstyle | — |
| [character-swap-animate-only-character-24fps](Wan-2.2/character-swap-animate-only-character-24fps.json) | Animate replace only character 24fps | Wan 2.2 Animate 14B (`sam3.pt`, `vitpose_h_wholebody_model.onnx`, `yolov10m.onnx` +3 more) | ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, comfyui-easy-sam3, comfyui-easy-use, comfyui-kjnodes, comfyui-videohelpersuite, comfyui_layerstyle | — |
| [relight-bernini-r](Wan-2.2/relight-bernini-r.json) | Relight an existing video from a lighting reference or prompt | [weights](https://huggingface.co/Comfy-Org/Bernini-R) | Core only | Model: Bernini-R (Wan 2.2 A14B); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_bernini_r_video_editing.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |
| [v2v-fun-control-14b-pose-depth-canny](Wan-2.2/v2v-fun-control-14b-pose-depth-canny.json) | Start image + control video (pose, depth or Canny) to a new video | [weights](https://huggingface.co/alibaba-pai/Wan2.2-Fun-A14B-Control) | Core only | Model: Wan2.2 Fun Control A14B; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan2_2_14B_fun_control.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |

## Wan-Animate-2

Folder: [`Wan-Animate-2/`](Wan-Animate-2) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [motion-transfer](Wan-Animate-2/motion-transfer.json) | Animate a still character directly from a driving video (no skeleton preprocessing) | [weights](https://huggingface.co/Comfy-Org/Wan-Animate-2) | Core only | Model: Wan Animate 2 14B; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan_animate2.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |

## Wan-Move

Folder: [`Wan-Move/`](Wan-Move) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [motion-control-trajectory-480p](Wan-Move/motion-control-trajectory-480p.json) | Image-to-video with point-level motion trajectories drawn in the graph | [weights](https://huggingface.co/Ruihang/Wan-Move-14B-480P) | Core only | Model: Wan-Move 14B 480p; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wanmove_480p.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |

## Wav2Lip

Folder: [`Wav2Lip/`](Wav2Lip) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [lip-sync-face-restore](Wav2Lip/lip-sync-face-restore.json) | Wav2Lip lip-sync with GFPGAN face restore. Pretrained Wav2Lip weights are **non-commercial research only** | [Rudrabha/Wav2Lip](https://github.com/Rudrabha/Wav2Lip) | ComfyUI-VideoHelperSuite, ComfyUI-wav2lip (boxzoo), comfyui-reactor | Model: `GFPGANv1.4.pth`; Source: [boxzoo/ComfyUI-wav2lip](https://github.com/boxzoo/ComfyUI-wav2lip/tree/main/example); Code licence: GPL-3.0; Weight licence: **Non-commercial research only** (LRS2); Status: not runtime-tested |

## Other

Folder: [`Other/`](Other) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [lineart-extraction-video](Other/lineart-extraction-video.json) | Line-art control maps for every frame | [lllyasviel/Annotators](https://huggingface.co/lllyasviel/Annotators) | comfyui_controlnet_aux, ComfyUI-VideoHelperSuite | Model: Annotators `sk_model.pth` (auto-downloaded); Source: [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates); Code licence: MIT; Weight licence: Custom ("other") — check model card; Status: not runtime-tested |
| [pixaroma-join-clips](Other/pixaroma-join-clips.json) | Video Tools - Join Your Clips into One Video (Ep41) | — | ComfyUI-Pixaroma | — |

## Notes carried over from the previous folder layout

Setup notes, licences, test results and "not available in ComfyUI" lists from the former task-folder READMEs. Links point to the new locations.

### From the former "Supporting Vision for Video" README

Per-frame analysis that feeds the control and editing workflows: video depth and normals, pose and line-art extraction, and video segmentation. These are not generation models.

The workflow JSONs added from the Open-Source Video Model Atlas (Nov 2026) are unmodified copies of published workflows. Each was checked only to be valid JSON, a genuine ComfyUI graph, and right for its model and task; **none has been runtime-tested in this library.** No model weights are included. The **model-weight licence is separate from the workflow (code) licence**; several weights are **non-commercial or carry custom terms** (marked below), so read the model card before commercial use. Workflows without a source row are original library workflows (Pixaroma tutorial episodes, Benji's AI Playground, or the library author's own MiniMax H3 / SeedVR2 runs); see the [root README credits](../../README.md#credits).

#### Sources, model weights and licences

Source link, code licence, weight licence and model download for each atlas workflow are in the Notes column of its model table above.

#### Atlas entries with no separate workflow here

Entries of the Open-Source Video Model Atlas for this category that did not get their own workflow. "Equivalent already exists" means an existing workflow already covers the model and task (usually a checkpoint, size or quantisation swap); nothing was fabricated for the others. Full per-entry status: [COVERAGE.md](../COVERAGE.md).

| Family | Entry | Status | Notes |
|---|---|---|---|
| Video Depth Anything | Video Depth Anything Base | equivalent already exists | checkpoint swap in same graph |
| Video Depth Anything | Video Depth Anything Metric Small | equivalent already exists | checkpoint swap in same graph |
| Video Depth Anything | Video Depth Anything Metric Large | equivalent already exists | checkpoint swap in same graph |
| CoTracker | CoTracker2 | availability or redistribution unconfirmed | s9roll7/comfyui_cotracker_node has no licence; only personal-project JSON (CreativeInquiry/ComfyCV) found |
| CoTracker | CoTracker3 | availability or redistribution unconfirmed | same as above |
| XMem / DeAOT | XMem long-term video masks | no suitable ComfyUI workflow | no maintained node |
| XMem / DeAOT | DeAOT object tracking masks | no suitable ComfyUI workflow | no maintained node |
| RAFT / GMFlow | RAFT optical flow | no suitable ComfyUI workflow | internal to other packs only |
| RAFT / GMFlow | GMFlow optical flow | no suitable ComfyUI workflow | no node |

### From the former "Video Editing and Control" README

Editing existing video (VACE, inpainting, outpainting, object and subtitle removal, relighting, instruction edits, clip tools), structure / camera / trajectory control, and character animation: pose and motion transfer, character replacement and swap, face swap, restyle.

The workflow JSONs added from the Open-Source Video Model Atlas (Nov 2026) are unmodified copies of published workflows. Each was checked only to be valid JSON, a genuine ComfyUI graph, and right for its model and task; **none has been runtime-tested in this library.** No model weights are included. The **model-weight licence is separate from the workflow (code) licence**; several weights are **non-commercial or carry custom terms** (marked below), so read the model card before commercial use. Workflows without a source row are original library workflows (Pixaroma tutorial episodes, Benji's AI Playground, or the library author's own MiniMax H3 / SeedVR2 runs); see the [root README credits](../../README.md#credits).

#### Sources, model weights and licences

Source link, code licence, weight licence and model download for each atlas workflow are in the Notes column of its model table above.

#### Atlas entries with no separate workflow here

Entries of the Open-Source Video Model Atlas for this category that did not get their own workflow. "Equivalent already exists" means an existing workflow already covers the model and task (usually a checkpoint, size or quantisation swap); nothing was fabricated for the others. Full per-entry status: [COVERAGE.md](../COVERAGE.md).

| Family | Entry | Status | Notes |
|---|---|---|---|
| Wan Animate 2 | Wan-Animate-2 Distilled 14B | equivalent already exists | distilled checkpoint of the Base workflow (template video_wan_animate2_distilled linked in README) |
| VACE | VACE Wan2.1 1.3B Preview | equivalent already exists | same tasks as VACE 14B workflows (1.3B selectable in loaders) |
| ProPainter | ProPainter video completion | equivalent already exists | same ProPainterInpaint graph as object removal workflow |
| Phantom-Wan | Phantom-Wan-1.3B | equivalent already exists | selectable in the Phantom 14B workflow loader |
| Phantom-Wan | Phantom-Wan-14B Pro | equivalent already exists | checkpoint swap in the same Phantom graph |
| UniAnimate | UniAnimate pose animation | availability or redistribution unconfirmed | Isi-dev/ComfyUI-UniAnimate-W workflows exist but repo has no licence; linked only |
| Wan Animate 2 | Wan-Animate-2 Lite research variant | no suitable ComfyUI workflow | no released weights or graph |
| Wan Dancer | Wan-Dancer 14B | no suitable ComfyUI workflow | official repo has no ComfyUI integration; SteadyDancer added as dance alternative |
| VACE | VACE LTX 0.9 | no suitable ComfyUI workflow | no VACE LTX release/graph found |
| SkyReels A-series | SkyReels-A1 portrait animation | no suitable ComfyUI workflow | ComfyUI is TODO in official repo / no maintained ComfyUI workflow found |
| MagicAnimate | MagicAnimate pose-driven character | no suitable ComfyUI workflow | node pack exists but publishes no workflow JSON |
| Rerender A Video | Rerender A Video keyframe edit | no suitable ComfyUI workflow | research code only |
| Rerender A Video | Rerender A Video LoRA+ControlNet | no suitable ComfyUI workflow | research code only |
| TokenFlow | TokenFlow zero-shot V2V | no suitable ComfyUI workflow | research code only |
| FateZero | FateZero cross-attention edit | no suitable ComfyUI workflow | research code only |
| Tune-A-Video | Tune-A-Video one-shot tuning | no suitable ComfyUI workflow | research code only |
| Vid2Vid-Zero | Vid2Vid-Zero video editing | no suitable ComfyUI workflow | research code only |
| AnyV2V | AnyV2V video editing | no suitable ComfyUI workflow | research code only |
| PnP Video | PnP Video (discovery lead) | no suitable ComfyUI workflow | discovery lead; no ComfyUI node/graph |
| Video-P2P | Video-P2P prompt editing | no suitable ComfyUI workflow | research code only |
| LOVECon | LOVECon stylization | no suitable ComfyUI workflow | research code only |
| VideoSwap | VideoSwap semantic swap | no suitable ComfyUI workflow | research code only |
| ControlVideo | ControlVideo spatial control | no suitable ComfyUI workflow | research code only |
| FRESCO | FRESCO feature correspondence | no suitable ComfyUI workflow | research code only |
| VideoPainter | VideoPainter video inpainting | no suitable ComfyUI workflow | official repo has no ComfyUI integration |
| E2FGVI | E2FGVI 432x240 | no suitable ComfyUI workflow | no maintained ComfyUI graph |
| E2FGVI | E2FGVI-HQ arbitrary resolution | no suitable ComfyUI workflow | no maintained ComfyUI graph |
| STTN / FuseFormer | STTN video inpainting | no suitable ComfyUI workflow | no ComfyUI support found |
| STTN / FuseFormer | FuseFormer video inpainting | no suitable ComfyUI workflow | no ComfyUI support found |

See the [02-Video overview](../README.md) for the other categories, the [main README](../../README.md) for setup, or [`00-LIBRARY-INDEX.md`](../../00-LIBRARY-INDEX.md) for the full list.
