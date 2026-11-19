# Video Generation — ComfyUI workflows

Workflows that create a new video: text-to-video, image-to-video, first / last frame, reference-to-video, long-form generation, world models, talking avatars from a picture and audio, and audio-reactive visuals.

[← 02-Video overview](../README.md) · [Library index](../../00-LIBRARY-INDEX.md)

**127 workflows** in **26 model folders**. Each model folder holds only workflow files; the file name says the task first, then the variant: `<task>[-<variant>][-<size>][-<precision>][-<feature>].json`. `Other/` holds generic or multi-model workflows.

## Model folders

| Model | Workflows | Tasks |
|---|---|---|
| [AnimateDiff](#animatediff) | 3 | `audio-reactive`, `img2video` |
| [Capybara](#capybara) | 1 | `img2video` |
| [CogVideoX](#cogvideox) | 3 | `img2video`, `txt2video` |
| [Cosmos](#cosmos) | 3 | `txt2video`, `video2world` |
| [DynamiCrafter](#dynamicrafter) | 1 | `img2video` |
| [EchoMimic](#echomimic) | 3 | `talking-avatar` |
| [FramePack](#framepack) | 1 | `long-video` |
| [Hallo](#hallo) | 2 | `talking-avatar` |
| [HunyuanVideo](#hunyuanvideo) | 4 | `img2video`, `txt2video` |
| [HY-Nomas](#hy-nomas) | 5 | `world-model` |
| [Kandinsky](#kandinsky) | 5 | `img2video`, `talking-avatar`, `txt2video` |
| [LivePortrait](#liveportrait) | 2 | `audio-reactive`, `portrait-animation` |
| [LongCat-Video](#longcat-video) | 2 | `long-video`, `talking-avatar` |
| [LTX-2](#ltx-2) | 7 | `img2video`, `talking-avatar`, `txt2video` |
| [LTX-Video](#ltx-video) | 3 | `img2video`, `txt2video` |
| [MAGI-1](#magi-1) | 3 | `long-video` |
| [MiniMax-H3](#minimax-h3) | 42 | `img2video`, `ref2video`, `talking-avatar`, `txt2video` |
| [Mochi-1](#mochi-1) | 1 | `txt2video` |
| [Pyramid-Flow](#pyramid-flow) | 2 | `img2video`, `txt2video` |
| [SkyReels](#skyreels) | 3 | `long-video`, `ref2video`, `talking-avatar` |
| [Sonic](#sonic) | 1 | `talking-avatar` |
| [SVD](#svd) | 2 | `img2video`, `txt2img2video` |
| [ToonCrafter](#tooncrafter) | 1 | `img2video` |
| [Wan-2.1](#wan-21) | 19 | `audio-reactive`, `img2video`, `ref2video`, `talking-avatar`, `txt2video` |
| [Wan-2.2](#wan-22) | 7 | `img2video`, `long-video`, `talking-avatar`, `txt2video` |
| [Other](#other) | 1 | `audio-reactive` |

## AnimateDiff

Folder: [`AnimateDiff/`](AnimateDiff) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [audio-reactive-images-to-video](AnimateDiff/audio-reactive-images-to-video.json) | AnimateDiff + IPAdapter: a set of pictures morphs on the beat, with QR-monster ControlNet and SparseCtrl (Yvann-Nodes example) | [AnimateLCM](https://huggingface.co/wangfuyun/AnimateLCM), [AnimateDiff v3](https://huggingface.co/guoyww/animatediff), SD1.5 checkpoints (DreamShaper 8), [QR Code Monster](https://huggingface.co/monster-labs/control_v1p_sd15_qrcode_monster) | ComfyUI-Advanced-ControlNet, ComfyUI-AnimateDiff-Evolved, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI_IPAdapter_plus, ComfyUI_Yvann-Nodes | Model: `control_v1p_sd15_qrcode_monster_v2.safetensors`, `dreamshaper_8.safetensors`, `vae-ft-mse-840000-ema-pruned.safetensors` +6 more; Source: [yvann-ba/ComfyUI_Yvann-Nodes](https://github.com/yvann-ba/ComfyUI_Yvann-Nodes/tree/main/example_workflows); Code licence: GPL-3.0; Weight licence: Apache-2.0 (AnimateDiff/AnimateLCM); SD1.5 checkpoints CreativeML OpenRAIL-M; Status: not runtime-tested |
| [audio-reactive-txt2video](AnimateDiff/audio-reactive-txt2video.json) | AnimateDiff (AnimateLCM) text-to-video where prompts switch on detected audio peaks and motion follows audio strength (Yvann-Nodes example) | [AnimateLCM](https://huggingface.co/wangfuyun/AnimateLCM), [AnimateDiff v3](https://huggingface.co/guoyww/animatediff), SD1.5 checkpoints (DreamShaper 8), [QR Code Monster](https://huggingface.co/monster-labs/control_v1p_sd15_qrcode_monster) | ComfyUI-AnimateDiff-Evolved, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI_FizzNodes, ComfyUI_Yvann-Nodes | Model: `2x-sudo-UltraCompact.pth`, `dreamshaper_8.safetensors`, `Hyper-SD15-12steps-CFG-lora.safetensors` +3 more; Source: [yvann-ba/ComfyUI_Yvann-Nodes](https://github.com/yvann-ba/ComfyUI_Yvann-Nodes/tree/main/example_workflows); Code licence: GPL-3.0; Weight licence: Apache-2.0 (AnimateDiff/AnimateLCM); SD1.5 checkpoints CreativeML OpenRAIL-M; Status: not runtime-tested |
| [img2video-animatelcm-ipadapter-loop](AnimateDiff/img2video-animatelcm-ipadapter-loop.json) | Weighted IP-Adapter images to a looping AnimateDiff animation | [link](https://huggingface.co/wangfuyun/AnimateLCM) | ComfyUI-AnimateDiff-Evolved, ComfyUI_IPAdapter_plus, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite | Model: AnimateDiff AnimateLCM (SD 1.5); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/templates_purz_animatediff_simple_weighted_ipadapters_looping_animation.json); Code licence: MIT; Weight licence: Apache-2.0 motion module; base checkpoint licence applies; Status: not runtime-tested |

## Capybara

Folder: [`Capybara/`](Capybara) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2video-v01](Capybara/img2video-v01.json) | Image to video with Capybara, a HunyuanVideo 1.5 fine-tune | [link](https://huggingface.co/xgen-universe/Capybara) | Core only | Model: Capybara v0.1 (HunyuanVideo 1.5 based); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_capybara_v0_1_image_to_video.json); Code licence: MIT; Weight licence: Check Capybara model card (Tencent Hunyuan Community License base); Status: not runtime-tested |

## CogVideoX

Folder: [`CogVideoX/`](CogVideoX) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2video-5b-first-last-frame](CogVideoX/img2video-5b-first-last-frame.json) | First + last frame interpolation with the CogVideoX 5B interpolation model | [link](https://huggingface.co/feizhengcong/CogvideoX-Interpolation) | ComfyUI-CogVideoXWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite | Model: CogVideoX 5B I2V (interpolation); Source: [source](https://github.com/kijai/ComfyUI-CogVideoXWrapper/blob/main/example_workflows/cogvideox_1_0_5b_interpolation_02.json); Code licence: Apache-2.0; Weight licence: CogVideoX License; Status: not runtime-tested |
| [img2video-v15-5b](CogVideoX/img2video-v15-5b.json) | CogVideoX 1.5 image to video; weights auto-download | [link](https://huggingface.co/THUDM/CogVideoX1.5-5B-I2V) | ComfyUI-CogVideoXWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite | Model: CogVideoX 1.5 5B I2V; Source: [source](https://github.com/kijai/ComfyUI-CogVideoXWrapper/blob/main/example_workflows/cogvideox_1_5_5b_I2V_01.json); Code licence: Apache-2.0; Weight licence: CogVideoX License; Status: not runtime-tested |
| [txt2video-5b](CogVideoX/txt2video-5b.json) | CogVideoX 1.0 5B text to video (6 s, 720x480); weights auto-download | [link](https://huggingface.co/THUDM/CogVideoX-5b) | ComfyUI-CogVideoXWrapper, ComfyUI-VideoHelperSuite | Model: CogVideoX 5B T2V; Source: [source](https://github.com/kijai/ComfyUI-CogVideoXWrapper/blob/main/example_workflows/cogvideox_1_0_5b_T2V_02.json); Code licence: Apache-2.0; Weight licence: CogVideoX License (5B; registration for commercial use); Status: not runtime-tested |

## Cosmos

Folder: [`Cosmos/`](Cosmos) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2video-v1-7b-text2world](Cosmos/txt2video-v1-7b-text2world.json) | NVIDIA Cosmos 1 world-model text to video | [link](https://huggingface.co/comfyanonymous/cosmos_1.0_text_encoder_and_VAE_ComfyUI) | Core only | Model: Cosmos-1.0 Diffusion 7B Text2World; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/tree/master/cosmos); Code licence: ComfyUI_examples terms (free use and redistribution); Weight licence: NVIDIA Open Model License; Status: not runtime-tested |
| [video2world-predict2-2b](Cosmos/video2world-predict2-2b.json) | NVIDIA Cosmos-Predict2 480p 16 fps image to video | [link](https://huggingface.co/Comfy-Org/Cosmos_Predict2_repackaged) | Core only | Model: Cosmos-Predict2 2B Video2World; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/tree/master/cosmos_predict2); Code licence: ComfyUI_examples terms (free use and redistribution); Weight licence: NVIDIA Open Model License; Status: not runtime-tested |
| [video2world-v1-7b](Cosmos/video2world-v1-7b.json) | NVIDIA Cosmos 1 world-model image to video | [link](https://huggingface.co/comfyanonymous/cosmos_1.0_text_encoder_and_VAE_ComfyUI) | Core only | Model: Cosmos-1.0 Diffusion 7B Video2World; Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/tree/master/cosmos); Code licence: ComfyUI_examples terms (free use and redistribution); Weight licence: NVIDIA Open Model License; Status: not runtime-tested |

## DynamiCrafter

Folder: [`DynamiCrafter/`](DynamiCrafter) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2video-1024](DynamiCrafter/img2video-1024.json) | Open-domain image animation with DynamiCrafter; weights auto-download | [link](https://huggingface.co/Doubiiu/DynamiCrafter_1024) | ComfyUI-DynamiCrafterWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite | Model: DynamiCrafter 1024; Source: [source](https://github.com/kijai/ComfyUI-DynamiCrafterWrapper/blob/main/examples/dynamicrafter_i2v_example_01.json); Code licence: Apache-2.0; Weight licence: Apache-2.0 code; weights research/non-commercial; Status: not runtime-tested |

## EchoMimic

Folder: [`EchoMimic/`](EchoMimic) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [talking-avatar-v1-portrait](EchoMimic/talking-avatar-v1-portrait.json) | EchoMimic V1: portrait + audio → talking head | [BadToBest/EchoMimic](https://huggingface.co/BadToBest/EchoMimic), [EchoMimicV2](https://huggingface.co/BadToBest/EchoMimicV2), [EchoMimicV3](https://huggingface.co/BadToBest/EchoMimicV3) | ComfyUI-VideoHelperSuite, ComfyUI_EchoMimic | Model: `sd-vae-ft-mse.safetensors`, `umt5_xxl_fp8_e4m3fn_scaled.safetensors`, `clip_vision_h_wan.safetensors`; Source: [smthemex/ComfyUI_EchoMimic](https://github.com/smthemex/ComfyUI_EchoMimic/tree/main/example_workflows); Code licence: Apache-2.0; Weight licence: Apache-2.0 (verify model card); Status: not runtime-tested |
| [talking-avatar-v2-half-body-pose](EchoMimic/talking-avatar-v2-half-body-pose.json) | EchoMimic V2: half-body picture + audio + pose sequence → talking half-body video with gestures | [BadToBest/EchoMimic](https://huggingface.co/BadToBest/EchoMimic), [EchoMimicV2](https://huggingface.co/BadToBest/EchoMimicV2), [EchoMimicV3](https://huggingface.co/BadToBest/EchoMimicV3) | ComfyUI-VideoHelperSuite, ComfyUI_EchoMimic | Model: `umt5_xxl_fp8_e4m3fn_scaled.safetensors`, `clip_vision_h_wan.safetensors`, `sd-vae-ft-mse.safetensors`; Source: [smthemex/ComfyUI_EchoMimic](https://github.com/smthemex/ComfyUI_EchoMimic/tree/main/example_workflows); Code licence: Apache-2.0; Weight licence: Apache-2.0 (verify model card); Status: not runtime-tested |
| [talking-avatar-v3](EchoMimic/talking-avatar-v3.json) | EchoMimic V3 (Wan 1.3B based): picture + audio → talking avatar | [BadToBest/EchoMimic](https://huggingface.co/BadToBest/EchoMimic), [EchoMimicV2](https://huggingface.co/BadToBest/EchoMimicV2), [EchoMimicV3](https://huggingface.co/BadToBest/EchoMimicV3) | ComfyUI-VideoHelperSuite, ComfyUI_EchoMimic | Model: `umt5_xxl_fp8_e4m3fn_scaled.safetensors`, `clip_vision_h_wan.safetensors`, `Wan2.1_VAE.pth` +1 more; Source: [smthemex/ComfyUI_EchoMimic](https://github.com/smthemex/ComfyUI_EchoMimic/tree/main/example_workflows); Code licence: Apache-2.0; Weight licence: Apache-2.0 (verify model card); Status: not runtime-tested |

## FramePack

Folder: [`FramePack/`](FramePack) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [long-video-hunyuan-img2video](FramePack/long-video-hunyuan-img2video.json) | FramePack image-to-video: next-frame-section prediction for long clips on low VRAM | [lllyasviel/FramePackI2V_HY](https://huggingface.co/lllyasviel/FramePackI2V_HY), [Kijai/HunyuanVideo_comfy](https://huggingface.co/Kijai/HunyuanVideo_comfy) | ComfyUI-FramePackWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI_essentials | Model: `FramePackI2V_HY_fp8_e4m3fn.safetensors`, `hunyuan_video_vae_bf16_repack.safetensors`, `llava_llama3_fp16.safetensors`, `clip_l.safetensors`, `sigclip_vision_patch14_384.safetensors`; Source: [kijai/ComfyUI-FramePackWrapper](https://github.com/kijai/ComfyUI-FramePackWrapper/tree/main/example_workflows); Code licence: Apache-2.0; Weight licence: HunyuanVideo-based — **Tencent Hunyuan Community License** (custom; territory and user-count limits); Status: not runtime-tested |

## Hallo

Folder: [`Hallo/`](Hallo) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [talking-avatar-v1-portrait](Hallo/talking-avatar-v1-portrait.json) | Hallo: portrait + audio → expressive talking head (SD1.5-based) | [fudan-generative-ai/hallo](https://huggingface.co/fudan-generative-ai/hallo) | ComfyUI-Hallo (AIFSH) | Source: [AIFSH/ComfyUI-Hallo](https://github.com/AIFSH/ComfyUI-Hallo/blob/main/hallo_base_workflow.json); Code licence: MIT; Weight licence: MIT (third-party sub-models have own terms); Status: not runtime-tested |
| [talking-avatar-v2-long-portrait-upscale](Hallo/talking-avatar-v2-long-portrait-upscale.json) | Hallo2: long-duration portrait animation with a built-in video super-resolution pass | [fudan-generative-ai/hallo2](https://huggingface.co/fudan-generative-ai/hallo2) | ComfyUI-VideoHelperSuite, ComfyUI_Hallo2 | Model: `RealESRGAN_x2plus.pth`, `detection_Resnet50_Final.pth`, `v1-5-pruned-emaonly.safetensors` +2 more; Source: [smthemex/ComfyUI_Hallo2](https://github.com/smthemex/ComfyUI_Hallo2/blob/main/workflow.json); Code licence: MIT; Weight licence: MIT (third-party sub-models have own terms); Status: not runtime-tested |

## HunyuanVideo

Folder: [`HunyuanVideo/`](HunyuanVideo) — 4 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2video-base-v2](HunyuanVideo/img2video-base-v2.json) | HunyuanVideo image to video; v2 keeps the first frame closer to the input | [link](https://huggingface.co/Comfy-Org/HunyuanVideo_repackaged) | Core only | Model: HunyuanVideo I2V (v2 "replace"); Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/tree/master/hunyuan_video); Code licence: ComfyUI_examples terms (free use and redistribution); Weight licence: Tencent Hunyuan Community License (excludes EU/UK/South Korea); Status: not runtime-tested |
| [img2video-v15-720p-1080p-sr](HunyuanVideo/img2video-v15-720p-1080p-sr.json) | 720p image to video with optional 1080p super-resolution pass | [link](https://huggingface.co/Comfy-Org/HunyuanVideo_1.5_repackaged) | Core only | Model: HunyuanVideo 1.5 I2V 8.3B; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_hunyuan_video_1.5_720p_i2v.json); Code licence: MIT; Weight licence: Tencent Hunyuan Community License (excludes EU/UK/South Korea); Status: not runtime-tested |
| [txt2video-13b](HunyuanVideo/txt2video-13b.json) | Original HunyuanVideo 720p text to video | [link](https://huggingface.co/Comfy-Org/HunyuanVideo_repackaged) | Core only | Model: HunyuanVideo 13B T2V; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/hunyuan_video_text_to_video.json); Code licence: MIT; Weight licence: Tencent Hunyuan Community License (excludes EU/UK/South Korea); Status: not runtime-tested |
| [txt2video-v15-720p-1080p-sr](HunyuanVideo/txt2video-v15-720p-1080p-sr.json) | 720p text to video with optional 1080p super-resolution pass and EasyCache | [link](https://huggingface.co/Comfy-Org/HunyuanVideo_1.5_repackaged) | Core only | Model: HunyuanVideo 1.5 T2V 8.3B; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_hunyuan_video_1.5_720p_t2v.json); Code licence: MIT; Weight licence: Tencent Hunyuan Community License (excludes EU/UK/South Korea); Status: not runtime-tested |

## HY-Nomas

Folder: [`HY-Nomas/`](HY-Nomas) — 5 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [world-model-camera-control](HY-Nomas/world-model-camera-control.json) | Generates the world segment by segment with camera keys and camera recording to steer the camera | `hy_nomas_distil_int8.safetensors`, `hy_nomas_pixelumm_fp8.safetensors`, `qwen_2.5_vl_7b_fp8_scaled.safetensors` | ComfyUI-Hy-Nomas | — |
| [world-model-drive-interactive](HY-Nomas/world-model-drive-interactive.json) | Interactive drive: steer the world live from one node | `hy_nomas_distil_int8.safetensors`, `hy_nomas_pixelumm_fp8.safetensors`, `qwen_2.5_vl_7b_fp8_scaled.safetensors` | ComfyUI-Hy-Nomas | — |
| [world-model-one-node](HY-Nomas/world-model-one-node.json) | Generates a whole world from a text prompt with a single node | `hy_nomas_distil_int8.safetensors`, `hy_nomas_pixelumm_fp8.safetensors`, `qwen_2.5_vl_7b_fp8_scaled.safetensors` | ComfyUI-Hy-Nomas | — |
| [world-model-per-segment](HY-Nomas/world-model-per-segment.json) | Generates the world one segment at a time, so each segment can be sampled and extended separately | `hy_nomas_distil_int8.safetensors`, `hy_nomas_pixelumm_fp8.safetensors`, `qwen_2.5_vl_7b_fp8_scaled.safetensors` | ComfyUI-Hy-Nomas | — |
| [world-model-start-from-image](HY-Nomas/world-model-start-from-image.json) | Starts the world from a loaded image and generates the video from it | `hy_nomas_distil_int8.safetensors`, `hy_nomas_pixelumm_fp8.safetensors`, `qwen_2.5_vl_7b_fp8_scaled.safetensors` | ComfyUI-Hy-Nomas | — |

## Kandinsky

Folder: [`Kandinsky/`](Kandinsky) — 5 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2video-v5-lite](Kandinsky/img2video-v5-lite.json) | 5-second image to video with the Lite model | [link](https://huggingface.co/kandinskylab) | Core only | Model: Kandinsky 5 Lite I2V; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_kandinsky5_i2v.json); Code licence: MIT; Weight licence: MIT (check model card); Status: not runtime-tested |
| [img2video-v6-pro-distill-audio](Kandinsky/img2video-v6-pro-distill-audio.json) | Image to video with generated audio and Kandinsky 6 video super-resolution | [link](https://huggingface.co/kandinskylab) | kandinsky6, kandinsky6-sr | Model: Kandinsky 6 Pro Distilled 29B + Video SR; Source: [source](https://github.com/kandinskylab/kandinsky-6/tree/main/comfyui/example_workflows); Code licence: MIT; Weight licence: MIT code; check weight cards; Status: not runtime-tested |
| [talking-avatar-s2v-lite-distilled](Kandinsky/talking-avatar-s2v-lite-distilled.json) | Kandinsky S2V Lite distilled: reference picture + speech → talking video, trimmed to the audio length (official Kandinsky example) | [kandinskylab/kandinsky-s2v](https://github.com/kandinskylab/kandinsky-s2v) (model links in README) | kandinsky-s2v (ComfyUI nodes) | Model: `kandinsky_s2v_lite_distill.safetensors`, `hunyuan_video_vae_bf16.safetensors`, `clip_l.safetensors`; Source: [kandinskylab/kandinsky-s2v](https://github.com/kandinskylab/kandinsky-s2v/tree/main/dev/comfyui/example_workflows); Code licence: MIT; Weight licence: MIT per repo (verify model card); Status: not runtime-tested |
| [txt2video-v5-lite](Kandinsky/txt2video-v5-lite.json) | 5-second text to video with the 2B Lite model | [link](https://huggingface.co/kandinskylab) | Core only | Model: Kandinsky 5 Lite T2V 2B (SFT 5s); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_kandinsky5_t2v.json); Code licence: MIT; Weight licence: MIT (check model card); Status: not runtime-tested |
| [txt2video-v6-pro-distill-audio](Kandinsky/txt2video-v6-pro-distill-audio.json) | Text to video with generated audio, prompt beautifier, MagCache and Kandinsky 6 video super-resolution | [link](https://huggingface.co/kandinskylab) | kandinsky6, kandinsky6-sr | Model: Kandinsky 6 Pro Distilled 29B + Video SR; Source: [source](https://github.com/kandinskylab/kandinsky-6/tree/main/comfyui/example_workflows); Code licence: MIT; Weight licence: MIT code; check weight cards; Status: not runtime-tested |

## LivePortrait

Folder: [`LivePortrait/`](LivePortrait) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [audio-reactive-expressions](LivePortrait/audio-reactive-expressions.json) | Facial expressions of a still portrait (LivePortrait) driven by audio, MIDI and other features (RyanOnTheInside example) | LivePortrait (auto-download by ComfyUI-AdvancedLivePortrait) | ComfyUI-AdvancedLivePortrait, ComfyUI-VideoHelperSuite, ComfyUI_RyanOnTheInside | Source: [ryanontheinside/ComfyUI_RyanOnTheInside](https://github.com/ryanontheinside/ComfyUI_RyanOnTheInside/blob/main/examples/FLEX_Advanced_Audio_Reactive_expressionVERSION2.json); Code licence: MIT; Weight licence: MIT code; InsightFace parts non-commercial; Status: not runtime-tested |
| [portrait-animation-from-driving-video](LivePortrait/portrait-animation-from-driving-video.json) | LivePortrait: a still portrait copies the head motion and expressions of a driving video | [Kijai/LivePortrait_safetensors](https://huggingface.co/Kijai/LivePortrait_safetensors) (auto-download) | ComfyUI-KJNodes, ComfyUI-LivePortraitKJ, ComfyUI-VideoHelperSuite, ComfyUI_essentials | Source: [kijai/ComfyUI-LivePortraitKJ](https://github.com/kijai/ComfyUI-LivePortraitKJ/tree/main/examples); Code licence: MIT; Weight licence: MIT; the InsightFace cropper is **non-commercial** — use the MediaPipe cropper for commercial work; Status: not runtime-tested |

## LongCat-Video

Folder: [`LongCat-Video/`](LongCat-Video) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [long-video-img2video-with-extension](LongCat-Video/long-video-img2video-with-extension.json) | LongCat-Video text/image-to-video, then extends the clip with overlapping continuation passes | [meituan-longcat/LongCat-Video](https://huggingface.co/meituan-longcat/LongCat-Video), [Kijai/LongCat-Video_comfy](https://huggingface.co/Kijai/LongCat-Video_comfy) | ComfyUI-WanVideoWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite | Model: `LongCat_TI2V_comfy_fp8_e4m3fn_scaled_KJ.safetensors`, `LongCat_distill_lora_rank128_bf16.safetensors`, `Wan2_1_VAE_bf16.safetensors`, `umt5-xxl-enc-bf16.safetensors`; Source: [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/tree/main/example_workflows); Code licence: Apache-2.0; Weight licence: MIT; Status: not runtime-tested |
| [talking-avatar-audio-image-to-video](LongCat-Video/talking-avatar-audio-image-to-video.json) | LongCat-Video Avatar: picture + audio → long talking video with overlapping windows and distill LoRA (WanVideoWrapper example) | [Kijai/LongCat-Video_comfy](https://huggingface.co/Kijai/LongCat-Video_comfy), [meituan-longcat](https://huggingface.co/meituan-longcat) | ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper | Model: `Wan2_1_VAE_bf16.safetensors`, `umt5-xxl-enc-bf16.safetensors`, `wav2vec2-chinese-base_fp16.safetensors` +3 more; Source: [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/LongCatAvatar_audio_image_to_video_example_01.json); Code licence: Apache-2.0; Weight licence: MIT; Status: not runtime-tested |

## LTX-2

Folder: [`LTX-2/`](LTX-2) — 7 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2video-audio](LTX-2/img2video-audio.json) | Image to Video with Audio | `ltx-2-19b-distilled-fp8.safetensors`, `ltx-2-19b-distilled.safetensors`, `ltx-2-spatial-upscaler-x2-1.0.safetensors` +1 more | ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use | — |
| [img2video-custom-audio](LTX-2/img2video-custom-audio.json) | Image to Video with Custom Audio | `ltx-2-19b-dev-fp8.safetensors`, `gemma_3_12B_it_fp8_e4m3fn.safetensors`, `gemma_3_12B_it.safetensors` +6 more | ComfyUI_LayerStyle, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use | — |
| [img2video-v25-dfr-detailing-keyframes-temporal-x2](LTX-2/img2video-v25-dfr-detailing-keyframes-temporal-x2.json) | DFR path: image (or text) to video with audio, generated detailing keyframes, spatial x2 IC-LoRA detailing and temporal x2 (48 fps) | [link](https://huggingface.co/Lightricks/LTX-2.5) | ComfyUI-LTXVideo | Model: LTX-2.5 22B distilled + IC-LoRA pixel upscaler; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_ltx2_5_dfr_i2v.json); Code licence: MIT; Weight licence: LTX-2 Community License (revenue limit); Status: not runtime-tested |
| [img2video-v25-distilled-audio-2x-upscale](LTX-2/img2video-v25-distilled-audio-2x-upscale.json) | Image to Video with Audio — LTX-2.5 22B distilled + 2x latent upscaler | `ltx-2.5-22b-distilled-transformer-bf16.safetensors`, `gemma4-12b-with-proj-ltx-2.5-bf16.safetensors`, `ltx-2.5-latent-spatial-upscaler-x2-bf16-1.0.safetensors` +2 more | Core only | — |
| [img2video-v25-first-last-frame-audio](LTX-2/img2video-v25-first-last-frame-audio.json) | First + last frame to video with audio (INT8, Gemma 4 prompt enhancer) | [link](https://huggingface.co/Lightricks/LTX-2.5) | Core only | Model: LTX-2.5 22B distilled; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_ltx2_5_flf2v.json); Code licence: MIT; Weight licence: LTX-2 Community License (revenue limit); Status: not runtime-tested |
| [talking-avatar-v23-id-lora-reference-voice](LTX-2/talking-avatar-v23-id-lora-reference-voice.json) | LTX-2.3 ID-LoRA: picture + a short reference voice clip + `[VISUAL]/[SPEECH]/[SOUNDS]` prompt → video whose generated speech keeps that voice (official ComfyUI template) | [Lightricks/LTX-2.3](https://huggingface.co/Lightricks/LTX-2.3), [ID-LoRA](https://github.com/ID-LoRA/ID-LoRA) | Core only | Model: `ltx-2.3-22b-dev-fp8.safetensors`, `ltx_2.3_22b_distilled_1.1_lora_dynamic_fro09_avg_rank_111_bf16.safetensors`, `gemma_3_12B_it_fp4_mixed.safetensors` +2 more; Source: [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_ltx2_3_id_lora.json); Code licence: MIT; Weight licence: **LTX-2 Community License** (custom, revenue conditions); Status: not runtime-tested |
| [txt2video-v25-audio](LTX-2/txt2video-v25-audio.json) | Text to video with synchronised audio, Gemma 4 prompt enhancer, x2 latent upscale (INT8) | [link](https://huggingface.co/Lightricks/LTX-2.5) | Core only | Model: LTX-2.5 22B distilled; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_ltx2_5_t2v.json); Code licence: MIT; Weight licence: LTX-2 Community License (revenue limit); Status: not runtime-tested |

## LTX-Video

Folder: [`LTX-Video/`](LTX-Video) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2video-v095-keyframe-guides-first-last](LTX-Video/img2video-v095-keyframe-guides-first-last.json) | Keyframe guides: first frame, last frame or several chained guide images | [link](https://huggingface.co/Lightricks/LTX-Video) | Core only | Model: LTX-Video 0.9.5 (2B); Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/tree/master/ltxv); Code licence: ComfyUI_examples terms (free use and redistribution); Weight licence: OpenRAIL-M (0.9.5); Status: not runtime-tested |
| [img2video-v095](LTX-Video/img2video-v095.json) | Legacy LTX-Video image to video | [link](https://huggingface.co/Lightricks/LTX-Video) | Core only | Model: LTX-Video 0.9.5 (2B); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/ltxv_image_to_video.json); Code licence: MIT; Weight licence: OpenRAIL-M (0.9.5); Status: not runtime-tested |
| [txt2video-v09](LTX-Video/txt2video-v09.json) | Legacy LTX-Video text to video; works with any 0.9.x 2B checkpoint | [link](https://huggingface.co/Lightricks/LTX-Video) | Core only | Model: LTX-Video 0.9.x (2B); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/ltxv_text_to_video.json); Code licence: MIT; Weight licence: LTX-Video licence per version (0.9.5+: OpenRAIL-M); Status: not runtime-tested |

## MAGI-1

Folder: [`MAGI-1/`](MAGI-1) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [long-video-continuation](MAGI-1/long-video-continuation.json) | MAGI-1 continues an input video with new chunks (video-to-video extension) | [sand-ai/MAGI-1](https://huggingface.co/sand-ai/MAGI-1) | MAGI-1 `comfyui/` nodes | Model: MAGI-1; Source: [SandAI-org/MAGI-1 `comfyui/workflow`](https://github.com/SandAI-org/MAGI-1/tree/main/comfyui); Code licence: Apache-2.0; Weight licence: Apache-2.0; Status: not runtime-tested |
| [long-video-img2video](MAGI-1/long-video-img2video.json) | MAGI-1 image-to-video from a start image | [sand-ai/MAGI-1](https://huggingface.co/sand-ai/MAGI-1) | MAGI-1 `comfyui/` nodes | Model: MAGI-1; Source: [SandAI-org/MAGI-1 `comfyui/workflow`](https://github.com/SandAI-org/MAGI-1/tree/main/comfyui); Code licence: Apache-2.0; Weight licence: Apache-2.0; Status: not runtime-tested |
| [long-video-txt2video](MAGI-1/long-video-txt2video.json) | MAGI-1 text-to-video, autoregressive chunk-by-chunk generation | [sand-ai/MAGI-1](https://huggingface.co/sand-ai/MAGI-1) | MAGI-1 `comfyui/` nodes | Model: MAGI-1 (4.5B / 24B, set in the node config); Source: [SandAI-org/MAGI-1 `comfyui/workflow`](https://github.com/SandAI-org/MAGI-1/tree/main/comfyui); Code licence: Apache-2.0; Weight licence: Apache-2.0; Status: not runtime-tested |

## MiniMax-H3

Folder: [`MiniMax-H3/`](MiniMax-H3) — 42 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2video-fasth3-first-frame-8-step](MiniMax-H3/img2video-fasth3-first-frame-8-step.json) | Image to Video — First Frame (8-Step) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [img2video-fasth3-first-last-frame-8-step](MiniMax-H3/img2video-fasth3-first-last-frame-8-step.json) | Image to Video — First + Last Frame (8-Step) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [img2video-first-frame-speed-lora](MiniMax-H3/img2video-first-frame-speed-lora.json) | Image to Video — First Frame + Speed LoRA | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +2 more | ComfyUI-Pixaroma | — |
| [img2video-first-frame](MiniMax-H3/img2video-first-frame.json) | Image to Video — First Frame | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [img2video-first-last-frame-20-step-2-stage-1088](MiniMax-H3/img2video-first-last-frame-20-step-2-stage-1088.json) | Image to Video — First + Last Frame, full H3 20-step + Pika refiner upscale to 1920x1088, low-VRAM attention (Ulluman S01 Draft 2) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_fl2va_pruned_w6a8.safetensors`, `minimax_h3_open_regenerate_2k_refiner_rank_16_bf16.safetensors` +3 more | ComfyUI-KJNodes | — |
| [img2video-first-last-frame-ep41](MiniMax-H3/img2video-first-last-frame-ep41.json) | Bonus - Minimax H3 - First and Last Frame to Video (Ep41) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_DMAD_4step_full_lora_avg_rank_39_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [img2video-first-last-frame-speed-lora](MiniMax-H3/img2video-first-last-frame-speed-lora.json) | Image to Video — First + Last Frame + Speed LoRA | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +2 more | ComfyUI-Pixaroma | — |
| [img2video-first-last-frame](MiniMax-H3/img2video-first-last-frame.json) | Image to Video — First + Last Frame | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [img2video-flux-2-klein-outfit-change-spin](MiniMax-H3/img2video-flux-2-klein-outfit-change-spin.json) | Flux Klein + Minimax H3 - Outfit Change Spin (Ep41) | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_DMAD_4step_full_lora_avg_rank_39_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [img2video-last-frame](MiniMax-H3/img2video-last-frame.json) | Image to Video — Last Frame | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [img2video-pika-flex-first-last-frame-2-stage](MiniMax-H3/img2video-pika-flex-first-last-frame-2-stage.json) | Image to Video — First + Last Frame, Pika-H3-Flex 6-Step + Latent Upscale (2-Stage) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `pika_h3_flex_fl2va_v1_avg_rank_56_bf16.safetensors` +4 more | ComfyUI-KJNodes | — |
| [img2video-prompt-control](MiniMax-H3/img2video-prompt-control.json) | Minimax H3 - Picture to Video - Tell It What to Do (Ep41) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_DMAD_4step_full_lora_avg_rank_39_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [img2video](MiniMax-H3/img2video.json) | Bonus - Minimax H3 - Picture to Video (Ep42) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_DMAD_4step_full_lora_avg_rank_39_bf16.safetensors` | ComfyUI-Pixaroma | — |
| [ref2video-2-images](MiniMax-H3/ref2video-2-images.json) | H3 reference-to-video from two pictures, native audio | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [ref2video-3-images](MiniMax-H3/ref2video-3-images.json) | H3 reference-to-video from three pictures, native audio | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [ref2video-multiframe-keyframe-guides](MiniMax-H3/ref2video-multiframe-keyframe-guides.json) | H3 reference + keyframe guides (`MiniMaxH3AddGuide`): several pictures pinned to frames of one shot (official ComfyUI template) | [Comfy-Org/MiniMax-H3](https://huggingface.co/Comfy-Org/MiniMax-H3) | Core only | Model: `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors` +2 more; Source: [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_minimax_h3_multiframe_reference.json); Code licence: MIT; Weight licence: **MiniMax custom licence**; Status: not runtime-tested |
| [ref2video-pika-flex-3-images-2-stage-1088](MiniMax-H3/ref2video-pika-flex-3-images-2-stage-1088.json) | Reference to Video (3 images) — Pika-H3-Flex ref2va 6-Step + Refiner Upscale 1280x736 → 1920x1088, low-VRAM attention (Naisha SC01) | `minimax_h3_ref2va_pruned_w6a8.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `pika_h3_flex_ref2va_v1_avg_rank_55_bf16.safetensors` +4 more | ComfyUI-KJNodes | — |
| [talking-avatar-picture-sing](MiniMax-H3/talking-avatar-picture-sing.json) | Minimax H3 - Audio Sync - Make a Picture Sing (Ep41) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [talking-avatar-picture-talk-from-text](MiniMax-H3/talking-avatar-picture-talk-from-text.json) | H3 picture + typed words → talking video with generated speech | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [talking-avatar-picture-talk](MiniMax-H3/talking-avatar-picture-talk.json) | Minimax H3 - Audio Sync - Make a Picture Talk (Ep41) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [talking-avatar-reference-character-swap](MiniMax-H3/talking-avatar-reference-character-swap.json) | H3 reference-to-video character swap that keeps the source video audio | `minimax_h3_audio_vae_fp32.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +4 more | Core only | — |
| [talking-avatar-reference-sing-speed-lora](MiniMax-H3/talking-avatar-reference-sing-speed-lora.json) | Reference Image + Audio Sync — Sing + Speed LoRA | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [talking-avatar-reference-sing](MiniMax-H3/talking-avatar-reference-sing.json) | Reference Image + Audio Sync — Sing | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [talking-avatar-reference-speak-speed-lora](MiniMax-H3/talking-avatar-reference-speak-speed-lora.json) | Reference Image + Audio Sync — Speak + Speed LoRA | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [talking-avatar-reference-speak](MiniMax-H3/talking-avatar-reference-speak.json) | Reference Image + Audio Sync — Speak | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [talking-avatar-timeline-act-story-scenes](MiniMax-H3/talking-avatar-timeline-act-story-scenes.json) | Minimax H3 - Timeline - Act a Story in Scenes (Ep41) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [talking-avatar-timeline-act-walk-new-place](MiniMax-H3/talking-avatar-timeline-act-walk-new-place.json) | Minimax H3 - Timeline - Act - Walk Into a New Place (Ep41) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [talking-avatar-timeline-four-singers](MiniMax-H3/talking-avatar-timeline-four-singers.json) | Minimax H3 - Timeline - Four Singers in One Song (Ep41) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [talking-avatar-timeline-redo-one-scene](MiniMax-H3/talking-avatar-timeline-redo-one-scene.json) | Minimax H3 - Timeline - Redo One Scene (Keep) (Ep41) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [talking-avatar-timeline-sing-bigger-size](MiniMax-H3/talking-avatar-timeline-sing-bigger-size.json) | Minimax H3 - Timeline - Sing at a Bigger Size (Ep41) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [talking-avatar-timeline-sing-character-walks-in](MiniMax-H3/talking-avatar-timeline-sing-character-walks-in.json) | Minimax H3 - Timeline - Sing + a Character Walks In (Ep41) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [talking-avatar-timeline-sing-clean-cuts](MiniMax-H3/talking-avatar-timeline-sing-clean-cuts.json) | Minimax H3 - Timeline - Sing with Clean Cuts (Ep41) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [talking-avatar-timeline-sing-scenes](MiniMax-H3/talking-avatar-timeline-sing-scenes.json) | Minimax H3 - Timeline - Sing a Song in Scenes (Ep41) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [txt2video-2k](MiniMax-H3/txt2video-2k.json) | Bonus - Minimax H3 - Text to Video in 2K (Ep41) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_DMAD_4step_full_lora_avg_rank_39_bf16.safetensors`, `open_h3_regenerate_2k_comfy_swiglu_fixed.safetensors`, `minimax_h3_latent_upscaler_3d_conv_v1_fp16.safetensors` | ComfyUI-Pixaroma | — |
| [txt2video-8-step-lora](MiniMax-H3/txt2video-8-step-lora.json) | Text to Video + 8-step speed LoRA (W6A8 model, int8 video VAE) (from captain's local ComfyUI, not re-tested) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_fl2va_pruned_w6a8.safetensors`, `minimax_h3_fl2v_turbo_8step_v1.0_comfyui_bf16.safetensors` +2 more | ComfyUI-Pixaroma | — |
| [txt2video-fasth3-8-step](MiniMax-H3/txt2video-fasth3-8-step.json) | Text to Video (8-Step) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `fastvideo_fasth3_8step_v2_pruned_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma | — |
| [txt2video-low-vram-8gb](MiniMax-H3/txt2video-low-vram-8gb.json) | Text to Video — Low VRAM 8GB | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_fl2va_pruned_int8_convrot.safetensors` +1 more | ComfyUI_LayerStyle, ComfyUI-Pixaroma | — |
| [txt2video-pika-flex-2-stage-2k](MiniMax-H3/txt2video-pika-flex-2-stage-2k.json) | Text to Video — Pika-H3-Flex 6-Step + 2K Latent Upscale (2-Stage) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `pika_h3_flex_fl2va_v1_avg_rank_56_bf16.safetensors` +4 more | ComfyUI-KJNodes | — |
| [txt2video-pika-flex-720p-to-1080p](MiniMax-H3/txt2video-pika-flex-720p-to-1080p.json) | Text to Video — Pika-H3-Flex, 720p → 1080p, 5 s (tuned for 16 GB VRAM / 30 GB RAM) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_fl2va_pruned_w6a8.safetensors`, `pika_h3_flex_fl2va_v1_avg_rank_56_bf16.safetensors` +4 more | ComfyUI-KJNodes | — |
| [txt2video-secret-sauce-4k](MiniMax-H3/txt2video-secret-sauce-4k.json) | Text to Video — Secret Sauce 4K Direct Output | `qwen3vl_32b_minimax_h3_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `taeh3.safetensors` +9 more | ComfyUI-MemoryCleaner, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, rgthree-comfy, ComfyUI-MiniMaxH3-TimelineDirector, ComfyUI_Comfyroll_CustomNodes, ComfyUI-MiniMaxH3-Unified, H3SigmaRefiner (unknown source), RH_DLSS5Enhance (unknown source) | — |
| [txt2video-speed-lora](MiniMax-H3/txt2video-speed-lora.json) | Text to Video + Speed LoRA | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +2 more | ComfyUI-Pixaroma | — |
| [txt2video](MiniMax-H3/txt2video.json) | Text to Video | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_fl2va_pruned_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma | — |

## Mochi-1

Folder: [`Mochi-1/`](Mochi-1) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2video](Mochi-1/txt2video.json) | Text to Video — Genmo Mochi 1 | `dit.safetensors`, `t5xxl_fp16.safetensors`, `decoder.safetensors` | Core only | — |

## Pyramid-Flow

Folder: [`Pyramid-Flow/`](Pyramid-Flow) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2video-miniflux](Pyramid-Flow/img2video-miniflux.json) | Pyramidal-flow image to video | [link](https://huggingface.co/rain1011/pyramid-flow-miniflux) | ComfyUI-PyramidFlowWrapper, ComfyUI-VideoHelperSuite | Model: Pyramid Flow miniFLUX 384p; Source: [source](https://github.com/kijai/ComfyUI-PyramidFlowWrapper/blob/main/examples/pyramid_flow_miniflux_img2vid_example_01.json); Code licence: MIT; Weight licence: MIT (check model card); Status: not runtime-tested |
| [txt2video-miniflux](Pyramid-Flow/txt2video-miniflux.json) | Autoregressive pyramidal-flow text to video | [link](https://huggingface.co/rain1011/pyramid-flow-miniflux) | ComfyUI-PyramidFlowWrapper, ComfyUI-VideoHelperSuite | Model: Pyramid Flow miniFLUX 384p; Source: [source](https://github.com/kijai/ComfyUI-PyramidFlowWrapper/blob/main/examples/pyramid_flow_miniflux_text2vid_example_01.json); Code licence: MIT; Weight licence: MIT (check model card); Status: not runtime-tested |

## SkyReels

Folder: [`SkyReels/`](SkyReels) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [long-video-v2-diffusion-forcing-extension](SkyReels/long-video-v2-diffusion-forcing-extension.json) | SkyReels V2 diffusion forcing: extends a loaded video window by window | [Skywork/SkyReels-V2-DF-1.3B-540P](https://huggingface.co/Skywork/SkyReels-V2-DF-1.3B-540P), [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy) | ComfyUI-WanVideoWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI_essentials | Model: `Wan2_1-SkyReels-V2-DF-1_3B-540P_fp32.safetensors`, `Wan2_1_VAE_bf16.safetensors`, `umt5-xxl-enc-bf16.safetensors`; Source: [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/tree/main/example_workflows); Code licence: Apache-2.0; Weight licence: **Skywork community licence (custom, "other")** — check before commercial use; Status: not runtime-tested |
| [ref2video-a2-element-assembly](SkyReels/ref2video-a2-element-assembly.json) | SkyReels-A2: assemble several element pictures (people, objects, background) into one video (WanVideoWrapper example) | [Skywork/SkyReels-A2](https://huggingface.co/Skywork/SkyReels-A2), [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy) | ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, ComfyUI_essentials | Model: `umt5_xxl_fp16.safetensors`, `clip_vision_h.safetensors`, `umt5-xxl-enc-bf16.safetensors` +2 more; Source: [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/wanvideo_2_1_14B_skyreels_a2_example_01.json); Code licence: Apache-2.0; Weight licence: See SkyReels-A2 model card; Status: not runtime-tested |
| [talking-avatar-v3](SkyReels/talking-avatar-v3.json) | SkyReels V3 Talking Avatar (A2V): portrait + audio, vocals separated with MelBandRoFormer (WanVideoWrapper example) | [Skywork/SkyReels-V3](https://github.com/SkyworkAI/SkyReels-V3), [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy) | ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper | Model: `Wan2_1_VAE_bf16.safetensors`, `wav2vec2-chinese-base_fp16.safetensors`, `MelBandRoformer_fp16.safetensors` +3 more; Source: [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/wanvideo_2_1_14B_I2V_SkyReelsV3_TalkingAvatar_example_01.json); Code licence: Apache-2.0; Weight licence: See SkyReels V3 model card; Status: not runtime-tested |

## Sonic

Folder: [`Sonic/`](Sonic) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [talking-avatar-audio-driven-portrait](Sonic/talking-avatar-audio-driven-portrait.json) | Sonic: portrait + audio → talking head on SVD, with RIFE frame interpolation | [LeonJoe13/Sonic](https://huggingface.co/LeonJoe13/Sonic), SVD-XT 1.1 | ComfyUI_Sonic | Model: `svd_xt_1_1.safetensors`, `unet.pth`; Source: [smthemex/ComfyUI_Sonic](https://github.com/smthemex/ComfyUI_Sonic/blob/main/example_workflows/sonic.json); Code licence: MIT; Weight licence: **Non-commercial** (Sonic CC BY-NC-SA; SVD under Stability licence) — verify; Status: not runtime-tested |

## SVD

Folder: [`SVD/`](SVD) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2video](SVD/img2video.json) | Classic SVD image to video (14 frames; SVD-XT for 25) | [link](https://huggingface.co/stabilityai/stable-video-diffusion-img2vid) | Core only | Model: Stable Video Diffusion (SVD); Source: [source](https://github.com/comfyanonymous/ComfyUI_examples/tree/master/video); Code licence: ComfyUI_examples terms (free use and redistribution); Weight licence: Stability AI Community License; Status: not runtime-tested |
| [txt2img2video-xt-sdxl](SVD/txt2img2video-xt-sdxl.json) | Text to image with SDXL, then animate it with SVD-XT | [link](https://huggingface.co/stabilityai/stable-video-diffusion-img2vid-xt) | Core only | Model: SDXL + Stable Video Diffusion XT; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/txt_to_image_to_video.json); Code licence: MIT; Weight licence: Stability AI Community License (SVD); Status: not runtime-tested |

## ToonCrafter

Folder: [`ToonCrafter/`](ToonCrafter) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2video-cartoon-keyframe-interpolation](ToonCrafter/img2video-cartoon-keyframe-interpolation.json) | Cartoon first + last keyframe interpolation | [link](https://huggingface.co/Doubiiu/ToonCrafter) | ComfyUI-DynamiCrafterWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite | Model: ToonCrafter 512 (DynamiCrafter-based); Source: [source](https://github.com/kijai/ComfyUI-DynamiCrafterWrapper/blob/main/examples/tooncrafter_example_01.json); Code licence: Apache-2.0; Weight licence: Apache-2.0 code; weights research/non-commercial; Status: not runtime-tested |

## Wan-2.1

Folder: [`Wan-2.1/`](Wan-2.1) — 19 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [audio-reactive-vace-pose-animation](Wan-2.1/audio-reactive-vace-pose-animation.json) | Wan 2.1 VACE 1.3B: OpenPose skeletons driven by audio features (stems separated with Open-Unmix) → dancing character video (RyanOnTheInside example) | [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy) (Wan 2.1 T2V 1.3B + VACE), SDXL OpenPose ControlNet | ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, ComfyUI-ultimate-openpose-editor, ComfyUI_NNLatentUpscale, ComfyUI_RyanOnTheInside, comfyui_controlnet_aux, rgthree-comfy | Model: `umt5-xxl-enc-bf16.safetensors`, `wan2.1_t2v_1.3B_bf16.safetensors`, `Wan2_1_VAE_bf16.safetensors` +3 more; Source: [ryanontheinside/ComfyUI_RyanOnTheInside](https://github.com/ryanontheinside/ComfyUI_RyanOnTheInside/blob/main/examples/audio_pose_wan_vace.json); Code licence: MIT; Weight licence: Apache-2.0 (Wan); SDXL checkpoint per its card; Status: not runtime-tested |
| [img2video-14b-480p](Wan-2.1/img2video-14b-480p.json) | Wan 2.1 image to video with CLIP-Vision conditioning (720p model also works) | [link](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged) | Core only | Model: Wan 2.1 I2V 14B 480p; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_to_video_wan.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |
| [img2video-14b-720p-first-last-frame](Wan-2.1/img2video-14b-720p-first-last-frame.json) | Dedicated Wan 2.1 first + last frame model | [link](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged) | Core only | Model: Wan 2.1 FLF2V 14B 720p; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/wan2.1_flf2v_720_f16.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |
| [img2video-causal-forcing-realtime-4-step](Wan-2.1/img2video-causal-forcing-realtime-4-step.json) | Autoregressive few-step (4-step) image to video for near real-time generation, about 5 s | [link](https://huggingface.co/TalmajM/causal_forcing_framewise_ComfyUI_repackaged) | Core only | Model: Causal Forcing framewise (Wan 2.1 1.3B); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_causal_forcing_i2v.json); Code licence: MIT; Weight licence: Check model card (Wan 2.1 base Apache-2.0); Status: not runtime-tested |
| [img2video-scail-multi-character-9x16](Wan-2.1/img2video-scail-multi-character-9x16.json) | Image to Video — Multi Character (9-16 Ratio Only) | SCAIL (Wan 2.1 14B) (`wan_2.1_vae.safetensors`, `clip_vision_h.safetensors`, `Wan21_Uni3C_controlnet_fp16.safetensors` +5 more) | ComfyUI-SCAIL-Pose, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, comfyui-easy-use, comfyui-kjnodes, comfyui-videohelpersuite, comfyui_controlnet_aux | — |
| [img2video-scail-single-character](Wan-2.1/img2video-scail-single-character.json) | Image to Video — Single Character | SCAIL (Wan 2.1 14B) (`wan_2.1_vae.safetensors`, `clip_vision_h.safetensors`, `vitpose_h_wholebody_model.onnx` +3 more) | ComfyUI-SCAIL-Pose, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, comfyui-easy-use, comfyui-kjnodes, comfyui-videohelpersuite | — |
| [ref2video-phantom-14b-multi-subject](Wan-2.1/ref2video-phantom-14b-multi-subject.json) | Subject-consistent video from up to four subject reference images | [weights](https://huggingface.co/bytedance-research/Phantom) | ComfyUI-WanVideoWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite | Model: Phantom-Wan 14B (1.3B optional); Source: [source](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/wanvideo_2_1_14B_phantom_subject2vid_example_02.json); Code licence: Apache-2.0; Weight licence: Apache-2.0; Status: not runtime-tested |
| [ref2video-stand-in-identity](Wan-2.1/ref2video-stand-in-identity.json) | Identity-preserving text-to-video from a single face photo | [weights](https://huggingface.co/BowenXue/Stand-In) | ComfyUI-WanVideoWrapper, ComfyUI-KJNodes, ComfyUI_essentials, comfyui_controlnet_aux, ComfyUI-VideoHelperSuite | Model: Stand-In LoRA (Wan 2.1 14B T2V); Source: [source](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/wanvideo_2_1_14B_Stand-In_reference_example_01.json); Code licence: Apache-2.0; Weight licence: Apache-2.0; use consented faces; Status: not runtime-tested |
| [ref2video-vace-14b](Wan-2.1/ref2video-vace-14b.json) | Reference-anything video: one or more reference images (subject, style) steer a new clip | [weights](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged) | Core only | Model: Wan2.1 VACE 14B (1.3B optional); Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan_vace_14B_ref2v.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |
| [talking-avatar-fantasytalking-portrait](Wan-2.1/talking-avatar-fantasytalking-portrait.json) | FantasyTalking: portrait + speech → talking video on Wan 2.1 I2V (WanVideoWrapper example) | [acvlab/FantasyTalking](https://huggingface.co/acvlab/FantasyTalking), [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy) | ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper | Model: `umt5_xxl_fp16.safetensors`, `clip_vision_h.safetensors`, `Wan2_1-I2V-14B-720P_fp8_e4m3fn.safetensors` +3 more; Source: [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/wanvideo_2_1_14B_I2V_FantasyTalking_example_01.json); Code licence: Apache-2.0; Weight licence: Apache-2.0 (verify model card); Status: not runtime-tested |
| [talking-avatar-humo-image-audio-reference](Wan-2.1/talking-avatar-humo-image-audio-reference.json) | HuMo: reference picture + audio + prompt → human video with lip-sync and subject identity (official ComfyUI template) | [Comfy-Org/HuMo_ComfyUI](https://huggingface.co/Comfy-Org/HuMo_ComfyUI) | Core only | Model: `umt5_xxl_fp8_e4m3fn_scaled.safetensors`, `wan_2.1_vae.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors` +2 more; Source: [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_humo.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |
| [talking-avatar-infinitetalk-10-11s](Wan-2.1/talking-avatar-infinitetalk-10-11s.json) | Talking Video from Audio — 10-11 Seconds | `Wan2_1-I2V-14B-480p_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_infiniteTalk_single_fp16.safetensors` +3 more | ComfyUI-VideoHelperSuite | — |
| [talking-avatar-infinitetalk-4-6s](Wan-2.1/talking-avatar-infinitetalk-4-6s.json) | InfiniteTalk single speaker, picture + audio → 4–6 s talking video | `Wan2_1-I2V-14B-480p_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_infiniteTalk_single_fp16.safetensors` +3 more | ComfyUI-VideoHelperSuite | — |
| [talking-avatar-infinitetalk-7-9s](Wan-2.1/talking-avatar-infinitetalk-7-9s.json) | Talking Video from Audio — 7-9 Seconds | `Wan2_1-I2V-14B-480p_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_infiniteTalk_single_fp16.safetensors` +3 more | ComfyUI-VideoHelperSuite | — |
| [talking-avatar-infinitetalk-extend-3-34s-easy](Wan-2.1/talking-avatar-infinitetalk-extend-3-34s-easy.json) | InfiniteTalk with switchable extension groups, 3–34 s | `Wan2_1-I2V-14B-480p_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_infiniteTalk_single_fp16.safetensors` +3 more | ComfyUI-VideoHelperSuite, rgthree-comfy | — |
| [talking-avatar-infinitetalk-extend-3-34s-manual](Wan-2.1/talking-avatar-infinitetalk-extend-3-34s-manual.json) | InfiniteTalk with manually chained extension segments, 3–34 s | `Wan2_1-I2V-14B-480p_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_infiniteTalk_single_fp16.safetensors` +3 more | ComfyUI-VideoHelperSuite, rgthree-comfy | — |
| [talking-avatar-infinitetalk-two-speaker](Wan-2.1/talking-avatar-infinitetalk-two-speaker.json) | InfiniteTalk *multi* model: two speakers, two audio tracks, painted masks for who speaks → conversation video (official ComfyUI template) | [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy), [MeiGen-AI/InfiniteTalk](https://huggingface.co/MeiGen-AI/InfiniteTalk) | Core only | Model: `Wan2_1-I2V-14B-480p_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_infiniteTalk_multi_fp16.safetensors` +3 more; Source: [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan2_1_infinitetalk.json); Code licence: MIT; Weight licence: Apache-2.0 (verify model card); Status: not runtime-tested |
| [txt2video-13b-low-vram](Wan-2.1/txt2video-13b-low-vram.json) | Small 1.3B text to video (about 8 GB VRAM) | [link](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged) | Core only | Model: Wan 2.1 T2V 1.3B; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/text_to_video_wan.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |
| [txt2video-alpha-14b-rgba](Wan-2.1/txt2video-alpha-14b-rgba.json) | Text to video with a transparent background (RGBA), saved as animated WebP; Lightx2v 4-step LoRA | [link](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged) | Core only | Model: Wan 2.1 T2V 14B + Wan-Alpha; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan2.1_alpha_t2v_14B.json); Code licence: MIT; Weight licence: Apache-2.0 (check Wan-Alpha LoRA card); Status: not runtime-tested |

## Wan-2.2

Folder: [`Wan-2.2/`](Wan-2.2) — 7 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2video-14b-first-last-frame](Wan-2.2/img2video-14b-first-last-frame.json) | First + last frame to video, FP8, optional Lightx2v 4-step LoRAs | [link](https://huggingface.co/Comfy-Org/Wan_2.2_ComfyUI_Repackaged) | Core only | Model: Wan 2.2 I2V A14B; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan2_2_14B_flf2v.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |
| [img2video-5b-ti2v-low-vram](Wan-2.2/img2video-5b-ti2v-low-vram.json) | Text or image to 720p video with the 5B hybrid model (about 8 GB VRAM with offload) | [link](https://huggingface.co/Comfy-Org/Wan_2.2_ComfyUI_Repackaged) | Core only | Model: Wan 2.2 TI2V 5B; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan2_2_5B_ti2v.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |
| [img2video-gguf-lightx2v-4-step-lora](Wan-2.2/img2video-gguf-lightx2v-4-step-lora.json) | Image to Video — GGUF Lightx2v 4-Step + LoRA | `umt5_xxl_fp8_e4m3fn_scaled.safetensors`, `wan_2.1_vae.safetensors`, `wan2.2_i2v_A14b_high_noise_lightx2v_4step-Q6_K.gguf` +2 more | ComfyUI-GGUF, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use | — |
| [img2video-gguf-lightx2v-4-step](Wan-2.2/img2video-gguf-lightx2v-4-step.json) | Image to Video — GGUF Lightx2v 4-Step | `umt5_xxl_fp8_e4m3fn_scaled.safetensors`, `wan_2.1_vae.safetensors`, `wan2.2_i2v_A14b_high_noise_lightx2v_4step-Q6_K.gguf` +1 more | ComfyUI-GGUF, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use | — |
| [long-video-pusa-extension](Wan-2.2/long-video-pusa-extension.json) | Wan 2.2 A14B with Pusa LoRAs: extends an input video from its last frames | [Wan-AI/Wan2.2-T2V-A14B](https://huggingface.co/Wan-AI/Wan2.2-T2V-A14B), [RaphaelLiu/Pusa-Wan2.2-V1](https://huggingface.co/RaphaelLiu/Pusa-Wan2.2-V1), [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy) | ComfyUI-WanVideoWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI_essentials | Model: `Wan2_2-T2V-A14B-HIGH/LOW_fp8_e4m3fn_scaled_KJ.safetensors`, `Wan22_PusaV1_lora_HIGH/LOW_…bf16.safetensors`, lightx2v T2V LoRA, `taew2_1.safetensors`; Source: [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/tree/main/example_workflows); Code licence: Apache-2.0; Weight licence: Apache-2.0; Status: not runtime-tested |
| [talking-avatar-s2v](Wan-2.2/talking-avatar-s2v.json) | Wan 2.2 S2V: one picture + speech/song audio → talking or singing video, chunked for longer clips (official ComfyUI template) | [Comfy-Org/Wan_2.2_ComfyUI_Repackaged](https://huggingface.co/Comfy-Org/Wan_2.2_ComfyUI_Repackaged) | Core only | Model: `umt5_xxl_fp8_e4m3fn_scaled.safetensors`, `wan_2.1_vae.safetensors`, `wav2vec2_large_english_fp16.safetensors` +2 more; Source: [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan2_2_14B_s2v.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |
| [txt2video-14b](Wan-2.2/txt2video-14b.json) | Two-expert (high/low noise) 14B text to video, FP8, optional Lightx2v 4-step LoRAs | [link](https://huggingface.co/Comfy-Org/Wan_2.2_ComfyUI_Repackaged) | Core only | Model: Wan 2.2 T2V A14B; Source: [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan2_2_14B_t2v.json); Code licence: MIT; Weight licence: Apache-2.0; Status: not runtime-tested |

## Other

Folder: [`Other/`](Other) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [audio-reactive-images-react-to-music](Other/audio-reactive-images-react-to-music.json) | Pictures cut and pulse to the beat of a music track, saved as MP4 | — | ComfyUI-Pixaroma | — |

## Notes carried over from the previous folder layout

Setup notes, licences, test results and "not available in ComfyUI" lists from the former task-folder READMEs. Links point to the new locations.

### From the former "Talking Avatars, Lip-Sync and Audio-Driven Video" README

Talking avatars from a picture and an audio track, lip-sync and dubbing of existing video, portrait animation from a driving video, MiniMax H3 audio sync and timelines, and audio-reactive visuals.

The workflow JSONs added from the Open-Source Video Model Atlas (Nov 2026) are unmodified copies of published workflows. Each was checked only to be valid JSON, a genuine ComfyUI graph, and right for its model and task; **none has been runtime-tested in this library.** No model weights are included. The **model-weight licence is separate from the workflow (code) licence**; several weights are **non-commercial or carry custom terms** (marked below), so read the model card before commercial use. Workflows without a source row are original library workflows (Pixaroma tutorial episodes, Benji's AI Playground, or the library author's own MiniMax H3 / SeedVR2 runs); see the [root README credits](../../README.md#credits).

#### Sources, model weights and licences

Source link, code licence, weight licence and model download for each atlas workflow are in the Notes column of its model table above.

#### Atlas entries with no separate workflow here

Entries of the Open-Source Video Model Atlas for this category that did not get their own workflow. "Equivalent already exists" means an existing workflow already covers the model and task (usually a checkpoint, size or quantisation swap); nothing was fabricated for the others. Full per-entry status: [COVERAGE.md](../COVERAGE.md).

| Family | Entry | Status | Notes |
|---|---|---|---|
| LTX 2.x | LTX-2.3 Distilled | equivalent already exists | as LTX-2.3 Dev / IA2V template and DubIt IC-LoRA (Lightricks) duplicate existing LTX-2 A2V/dubbing files; Lightricks JSONs need full LTX licence copy -> linked in README |
| Kandinsky Video 6 | Kandinsky 6 Lite 3B | equivalent already exists | Lite loads in the Kandinsky 6 example graphs (model selector) |
| Kandinsky Video 6 | Kandinsky 6 Lite Distilled 3B | equivalent already exists | Lite Distilled loads in the Kandinsky 6 example graphs |
| Kandinsky Video 6 | Kandinsky 6 Pro 29B | equivalent already exists | Pro (non-distilled) loads in the Kandinsky 6 example graphs |
| MultiTalk | MultiTalk multi-person dialogue | equivalent already exists | [`wan-2.1-infinitetalk-two-speaker-conversation`](Wan-2.1/talking-avatar-infinitetalk-two-speaker.json) (InfiniteTalk multi supersedes MultiTalk in maintained nodes) |
| MultiTalk | MultiTalk single speaker singing | equivalent already exists | InfiniteTalk/H3 singing files in 02-Video/Reference-and-Audio-Sync |
| Wav2Lip | Wav2Lip GAN | equivalent already exists | checkpoint choice inside the same Wav2Lip workflow |
| MuseTalk | MuseTalk 1.5 | equivalent already exists | same node/graph as MuseTalk 1.0 file; checkpoint swap only |
| EchoMimic | EchoMimic V2 Accelerated | equivalent already exists | accelerated checkpoint of V2 / V3 flash variants; not a new capability |
| Kandinsky S2V | Kandinsky S2V Pro Distill | equivalent already exists | same graph as Lite with larger checkpoint (official Pro JSON linked) |
| SkyReels V3 | SkyReels V3 Reference-to-Video 14B | no suitable ComfyUI workflow | no first-party/maintained JSON found for the R2V checkpoint (left for other slices to recheck) |
| SkyReels V3 | SkyReels V3 Video Extension 14B | no suitable ComfyUI workflow | No dedicated ComfyUI video-extension workflow was collected by any slice; the closest library path is the SkyReels V2 diffusion-forcing extension [`long-video-v2-diffusion-forcing-extension`](SkyReels/long-video-v2-diffusion-forcing-extension.json). Remaining gap: not separately searched at integration |
| LivePortrait | LivePortrait animals / community branch | no suitable ComfyUI workflow | no separate ComfyUI workflow |
| SadTalker | SadTalker 256 | no suitable ComfyUI workflow | only unlicensed community node repos, no example JSON |
| SadTalker | SadTalker 512 beta | no suitable ComfyUI workflow | same as SadTalker 256 |
| Hunyuan Portrait | HunyuanPortrait image-audio animation | no suitable ComfyUI workflow | community nodes have no example JSON |
| OmniAvatar | OmniAvatar audio to full-body video | no suitable ComfyUI workflow | one small unlicensed repo, no example JSON |
| VideoReTalking | VideoReTalking lip-sync repair | no suitable ComfyUI workflow | no ComfyUI node or workflow found |

### From the former "Video Generation" README

Text-to-video, image-to-video, first/last frame, reference-to-video, long-form generation and world models, including models that generate audio with the video (LTX-2.x, Kandinsky 6, MiniMax H3).

The workflow JSONs added from the Open-Source Video Model Atlas (Nov 2026) are unmodified copies of published workflows. Each was checked only to be valid JSON, a genuine ComfyUI graph, and right for its model and task; **none has been runtime-tested in this library.** No model weights are included. The **model-weight licence is separate from the workflow (code) licence**; several weights are **non-commercial or carry custom terms** (marked below), so read the model card before commercial use. Workflows without a source row are original library workflows (Pixaroma tutorial episodes, Benji's AI Playground, or the library author's own MiniMax H3 / SeedVR2 runs); see the [root README credits](../../README.md#credits).

#### Sources, model weights and licences

Source link, code licence, weight licence and model download for each atlas workflow are in the Notes column of its model table above.

#### Atlas entries with no separate workflow here

Entries of the Open-Source Video Model Atlas for this category that did not get their own workflow. "Equivalent already exists" means an existing workflow already covers the model and task (usually a checkpoint, size or quantisation swap); nothing was fabricated for the others. Full per-entry status: [COVERAGE.md](../COVERAGE.md).

| Family | Entry | Status | Notes |
|---|---|---|---|
| Wan 2.1 | Wan2.1 I2V 14B 720p | equivalent already exists | [`wan-2.1-14b-img2video-480p`](Wan-2.1/img2video-14b-480p.json) (swap to 720p checkpoint) |
| LTX-Video legacy | LTX-Video 0.9.7 | equivalent already exists | loads in the LTX-Video 0.9.x graphs; dedicated 0.9.7 workflows were removed upstream (ComfyUI-LTXVideo now ships 2.x only) |
| LTX-Video legacy | LTX-Video 0.9.8 | equivalent already exists | loads in the LTX-Video 0.9.x graphs; no maintained 0.9.8 workflow upstream |
| HunyuanVideo 1.5 | HunyuanVideo 1.5 I2V Step-Distilled | equivalent already exists | step-distilled checkpoint loads in [`hunyuanvideo-1.5-720p-img2video-1080p-sr`](HunyuanVideo/img2video-v15-720p-1080p-sr.json) |
| Kandinsky Video 5 | Kandinsky 5 Lite 16-step Flash | equivalent already exists | Flash checkpoint loads in the Lite T2V graph |
| Kandinsky Video 5 | Kandinsky 5 Pro 19B T2V | equivalent already exists | Pro checkpoint loads in the Lite T2V graph; no separate published workflow |
| Kandinsky Video 5 | Kandinsky 5 Pro I2V | equivalent already exists | Pro I2V loads in the Lite I2V graph |
| CogVideoX | CogVideoX 2B T2V | equivalent already exists | 2B uses the 5B T2V wrapper graph (model selector) |
| CogVideoX | CogVideoX 5B I2V | equivalent already exists | CogVideoX 1.0 5B I2V skipped; 1.5 I2V kept |
| CogVideoX | CogVideoX 1.5 5B T2V | equivalent already exists | 1.5 T2V selectable in the CogVideoX wrapper T2V graph |
| Mochi | Mochi 1 LoRA-enabled | equivalent already exists | LoRA adds a LoraLoader to [`txt2video`](Mochi-1/txt2video.json); no separate official workflow |
| SkyReels V1-V2 | SkyReels V1 human-centric | equivalent already exists | HunyuanVideo fine-tune; no dedicated ComfyUI workflow collected by any slice. The checkpoint loads in the HunyuanVideo T2V/I2V graphs: [`hunyuanvideo-13b-txt2video`](HunyuanVideo/txt2video-13b.json), [`hunyuanvideo-img2video-v2`](HunyuanVideo/img2video-base-v2.json) |
| SkyReels V1-V2 | SkyReels V2 I2V 14B 720p | equivalent already exists | Wan 2.1 I2V-architecture checkpoint; loads in [`wan-2.1-14b-img2video-480p`](Wan-2.1/img2video-14b-480p.json) (checkpoint swap). Not separately collected |
| MAGI-1 | MAGI-1 4.5B distilled | equivalent already exists | checkpoint variant of the MAGI-1 graphs |
| MAGI-1 | MAGI-1 4.5B FP8 | equivalent already exists | quantisation variant of the MAGI-1 graphs |
| MAGI-1 | MAGI-1 24B | equivalent already exists | checkpoint variant of the MAGI-1 graphs |
| MAGI-1 | MAGI-1 24B distilled | equivalent already exists | checkpoint variant of the MAGI-1 graphs |
| MAGI-1 | MAGI-1.1 24B distilled | equivalent already exists | checkpoint variant of the MAGI-1 graphs |
| Pyramid Flow | Pyramid Flow miniFLUX 768p | equivalent already exists | 768p example differs only by resolution/checkpoint |
| DynamiCrafter | DynamiCrafter 256 | equivalent already exists | smaller checkpoint for [`img2video-1024`](DynamiCrafter/img2video-1024.json) |
| DynamiCrafter | DynamiCrafter 512 | equivalent already exists | smaller checkpoint for [`img2video-1024`](DynamiCrafter/img2video-1024.json) |
| FramePack | FramePack F1 | equivalent already exists | checkpoint swap in same FramePackWrapper graph |
| Stable Video Diffusion | Stable Video Diffusion XT 1.1 | equivalent already exists | XT 1.1 checkpoint loads in the SVD graphs |
| HunyuanVideo | HunyuanVideo Avatar | availability or redistribution unconfirmed | smthemex/ComfyUI_HunyuanAvatar_Sm JSONs under Tencent Hunyuan Community License (territory-limited); linked in README |
| FramePack | FramePack P1 research update | availability or redistribution unconfirmed | no released weights/workflow found |
| HunyuanVideo | HunyuanVideo Foley (support extension) | no suitable ComfyUI workflow | node packs exist (if-ai, aistudynow) but no example workflow JSON |
| LongCat-Video | LongCat interactive video | no suitable ComfyUI workflow | official scripts only |
| Kandinsky Video 5 | Kandinsky 5 Camera-Control LoRA | no suitable ComfyUI workflow | no published camera-control LoRA workflow |
| Open-Sora | Open-Sora 1.0 | no suitable ComfyUI workflow | no maintained ComfyUI workflow |
| Open-Sora | Open-Sora 1.1 | no suitable ComfyUI workflow | no maintained ComfyUI workflow |
| Open-Sora | Open-Sora 1.2 | no suitable ComfyUI workflow | only stale community port |
| Open-Sora | Open-Sora 2.0 11B | no suitable ComfyUI workflow | no maintained ComfyUI workflow |
| Open-Sora Plan | Open-Sora Plan v1.0 | no suitable ComfyUI workflow | official scripts only |
| Open-Sora Plan | Open-Sora Plan v1.1 | no suitable ComfyUI workflow | official scripts only |
| Open-Sora Plan | Open-Sora Plan v1.2 I2V | no suitable ComfyUI workflow | official scripts only |
| Open-Sora Plan | Open-Sora Plan v1.3 | no suitable ComfyUI workflow | official scripts only |
| Open-Sora Plan | Open-Sora Plan v1.5 (Ascend NPU) | no suitable ComfyUI workflow | Ascend NPU only |
| Step Video | Step-Video T2V | no suitable ComfyUI workflow | no maintained ComfyUI workflow found |
| Step Video | Step-Video T2V Turbo | no suitable ComfyUI workflow | no maintained ComfyUI workflow found |
| Step Video | Step-Video TI2V | no suitable ComfyUI workflow | no maintained ComfyUI workflow found |
| Pyramid Flow | Pyramid Flow SD3 384p | no suitable ComfyUI workflow | SD3 variant superseded; wrapper only publishes miniFLUX examples |
| Allegro | Allegro T2V | no suitable ComfyUI workflow | Diffusers only |
| Allegro | Allegro TI2V | no suitable ComfyUI workflow | Diffusers only |
| VideoCrafter | VideoCrafter1 T2V 1024 | no suitable ComfyUI workflow | old unmaintained community nodes, no published workflow; non-commercial weights |
| VideoCrafter | VideoCrafter1 T2V 512 | no suitable ComfyUI workflow | as above |
| VideoCrafter | VideoCrafter1 I2V 1024 | no suitable ComfyUI workflow | as above |
| VideoCrafter | VideoCrafter1 I2V 512 | no suitable ComfyUI workflow | as above |
| VideoCrafter | VideoCrafter2 T2V 512 | no suitable ComfyUI workflow | as above |
| AnimateDiff | AnimateDiff SDXL beta | no suitable ComfyUI workflow | AnimateDiff-Evolved publishes no workflow JSONs |
| AnimateDiff | AnimateDiff SparseCtrl | no suitable ComfyUI workflow | no official SparseCtrl workflow JSON published |
| VGen / I2VGen-XL | I2VGen-XL | no suitable ComfyUI workflow | no maintained ComfyUI graph |
| VGen / I2VGen-XL | VGen VideoComposer | no suitable ComfyUI workflow | no maintained ComfyUI graph |
| SEINE / LaVie | SEINE generative transitions | no suitable ComfyUI workflow | no maintained node |
| SEINE / LaVie | LaVie text to video | no suitable ComfyUI workflow | no maintained node |
| Latte | Latte T2V | no suitable ComfyUI workflow | Diffusers only |
| Latte | Latte-1 T2V | no suitable ComfyUI workflow | Diffusers only |
| Latte | Latte I2I training baseline | no suitable ComfyUI workflow | training baseline, not a generation workflow |
| Helios | Helios Base 14B | no suitable ComfyUI workflow | Diffusers/SGLang/vLLM-Omni only |
| Helios | Helios Mid 14B | no suitable ComfyUI workflow | Diffusers/SGLang/vLLM-Omni only |
| Helios | Helios Distilled 14B | no suitable ComfyUI workflow | Diffusers/SGLang/vLLM-Omni only |
| Cosmos 3 | Cosmos3 Edge 4B | no suitable ComfyUI workflow | no ComfyUI template |
| Cosmos 3 | Cosmos3 Nano 16B | no suitable ComfyUI workflow | no ComfyUI template |
| Cosmos 3 | Cosmos3 Super 64B | no suitable ComfyUI workflow | no ComfyUI template |
| Cosmos Predict2.5 | Cosmos Predict2.5 2B pre-trained | no suitable ComfyUI workflow | Predict2.5 has no ComfyUI integration; nearest: [`cosmos-predict2-2b-video2world-img2video`](Cosmos/video2world-predict2-2b.json) (Predict2) |
| Cosmos Predict2.5 | Cosmos Predict2.5 2B post-trained | no suitable ComfyUI workflow | Predict2.5 has no ComfyUI integration; nearest: [`cosmos-predict2-2b-video2world-img2video`](Cosmos/video2world-predict2-2b.json) (Predict2) |
| Cosmos Predict2.5 | Cosmos Predict2.5 2B distilled | no suitable ComfyUI workflow | Predict2.5 has no ComfyUI integration; nearest: [`cosmos-predict2-2b-video2world-img2video`](Cosmos/video2world-predict2-2b.json) (Predict2) |
| Cosmos Predict2.5 | Cosmos Predict2.5 14B pre-trained | no suitable ComfyUI workflow | Predict2.5 has no ComfyUI integration; nearest: [`cosmos-predict2-2b-video2world-img2video`](Cosmos/video2world-predict2-2b.json) (Predict2) |
| Cosmos Predict2.5 | Cosmos Predict2.5 14B post-trained | no suitable ComfyUI workflow | Predict2.5 has no ComfyUI integration; nearest: [`cosmos-predict2-2b-video2world-img2video`](Cosmos/video2world-predict2-2b.json) (Predict2) |
| Cosmos Predict2.5 | Cosmos Predict2.5 auto multi-view | no suitable ComfyUI workflow | Predict2.5 has no ComfyUI integration; nearest: [`cosmos-predict2-2b-video2world-img2video`](Cosmos/video2world-predict2-2b.json) (Predict2) |
| Cosmos Predict2.5 | Cosmos Predict2.5 robot action-conditioned | no suitable ComfyUI workflow | Predict2.5 has no ComfyUI integration; nearest: [`cosmos-predict2-2b-video2world-img2video`](Cosmos/video2world-predict2-2b.json) (Predict2) |

See the [02-Video overview](../README.md) for the other categories, the [main README](../../README.md) for setup, or [`00-LIBRARY-INDEX.md`](../../00-LIBRARY-INDEX.md) for the full list.
