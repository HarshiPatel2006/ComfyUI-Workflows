# Audio-Reactive — ComfyUI video workflows

Video that moves with music: prompts, pictures, poses and facial expressions change with beats, loudness and separated stems.

> **Not runtime-tested.** Every JSON here was checked only for valid JSON, a genuine ComfyUI graph, model/task fit and duplicates. None was run in this library.

## Workflows (6)

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [utility-images-react-to-music-audio-reactive](utility-images-react-to-music-audio-reactive.json) | Pictures cut and pulse to the beat of a music track, saved as MP4 | — | ComfyUI-Pixaroma |
| [animatediff-audio-reactive-text-to-video](animatediff-audio-reactive-text-to-video.json) | **New.** AnimateDiff (AnimateLCM) text-to-video where prompts switch on detected audio peaks and motion follows audio strength (Yvann-Nodes example) | `2x-sudo-UltraCompact.pth`, `dreamshaper_8.safetensors`, `Hyper-SD15-12steps-CFG-lora.safetensors` +3 more | ComfyUI-AnimateDiff-Evolved, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI_FizzNodes, ComfyUI_Yvann-Nodes |
| [animatediff-audio-reactive-images-to-video](animatediff-audio-reactive-images-to-video.json) | **New.** AnimateDiff + IPAdapter: a set of pictures morphs on the beat, with QR-monster ControlNet and SparseCtrl (Yvann-Nodes example) | `control_v1p_sd15_qrcode_monster_v2.safetensors`, `dreamshaper_8.safetensors`, `vae-ft-mse-840000-ema-pruned.safetensors` +6 more | ComfyUI-Advanced-ControlNet, ComfyUI-AnimateDiff-Evolved, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI_IPAdapter_plus, ComfyUI_Yvann-Nodes |
| [animatediff-audio-reactive-video-to-video](animatediff-audio-reactive-video-to-video.json) | **New.** AnimateDiff video-to-video restyle where the strength and the IPAdapter pictures follow the audio (Yvann-Nodes example) | `AnimateLCM_sd15_t2v.ckpt`, `LiquidAF-0-1.safetensors`, `2x-sudo-UltraCompact.pth` +7 more | ComfyUI-Advanced-ControlNet, ComfyUI-AnimateDiff-Evolved, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI_IPAdapter_plus, ComfyUI_Yvann-Nodes, comfyui_controlnet_aux |
| [wan-2.1-vace-audio-reactive-pose-animation](wan-2.1-vace-audio-reactive-pose-animation.json) | **New.** Wan 2.1 VACE 1.3B: OpenPose skeletons driven by audio features (stems separated with Open-Unmix) → dancing character video (RyanOnTheInside example) | `umt5-xxl-enc-bf16.safetensors`, `wan2.1_t2v_1.3B_bf16.safetensors`, `Wan2_1_VAE_bf16.safetensors` +3 more | ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, ComfyUI-ultimate-openpose-editor, ComfyUI_NNLatentUpscale, ComfyUI_RyanOnTheInside, comfyui_controlnet_aux, rgthree-comfy |
| [liveportrait-audio-reactive-expressions](liveportrait-audio-reactive-expressions.json) | **New.** Facial expressions of a still portrait (LivePortrait) driven by audio, MIDI and other features (RyanOnTheInside example) | — | ComfyUI-AdvancedLivePortrait, ComfyUI-VideoHelperSuite, ComfyUI_RyanOnTheInside |

## Sources and licences of the new workflows

| Workflow | Source | JSON licence | Model weights | Weight licence |
|---|---|---|---|---|
| animatediff-audio-reactive-text-to-video / images-to-video / video-to-video | [yvann-ba/ComfyUI_Yvann-Nodes](https://github.com/yvann-ba/ComfyUI_Yvann-Nodes/tree/main/example_workflows) | GPL-3.0 | [AnimateLCM](https://huggingface.co/wangfuyun/AnimateLCM), [AnimateDiff v3](https://huggingface.co/guoyww/animatediff), SD1.5 checkpoints (DreamShaper 8), [QR Code Monster](https://huggingface.co/monster-labs/control_v1p_sd15_qrcode_monster) | Apache-2.0 (AnimateDiff/AnimateLCM); SD1.5 checkpoints CreativeML OpenRAIL-M |
| wan-2.1-vace-audio-reactive-pose-animation | [ryanontheinside/ComfyUI_RyanOnTheInside](https://github.com/ryanontheinside/ComfyUI_RyanOnTheInside/blob/main/examples/audio_pose_wan_vace.json) | MIT | [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy) (Wan 2.1 T2V 1.3B + VACE), SDXL OpenPose ControlNet | Apache-2.0 (Wan); SDXL checkpoint per its card |
| liveportrait-audio-reactive-expressions | [ryanontheinside/ComfyUI_RyanOnTheInside](https://github.com/ryanontheinside/ComfyUI_RyanOnTheInside/blob/main/examples/FLEX_Advanced_Audio_Reactive_expressionVERSION2.json) | MIT | LivePortrait (auto-download by ComfyUI-AdvancedLivePortrait) | MIT code; InsightFace parts non-commercial |

Talking avatars and lip-sync driven by speech are in [`../Reference-and-Audio-Sync`](../Reference-and-Audio-Sync).
