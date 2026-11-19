# AI Video — ComfyUI workflows

All video workflows in the library: **239 workflows** in five categories — text-to-video, image-to-video, reference-to-video, long-form generation and world models; video editing, control and character animation; talking avatars, lip-sync and audio-reactive video; video upscaling and frame interpolation; and supporting vision (depth, pose, segmentation). Each category README lists every workflow with what it does, the models it loads and the custom nodes it needs, and — for the Open-Source Video Model Atlas additions (Nov 2026) — the source, model download, code licence and weight licence. The atlas additions were checked to be valid ComfyUI workflow JSON for their model and task; they have **not** been runtime-tested.

## Folders

| Category | Subfolder | Workflows |
|---|---|---|
| [Video-Generation](Video-Generation/README.md) | | 84 |
| | [Text-to-Video](Video-Generation/Text-to-Video) | 23 |
| | [Image-to-Video](Video-Generation/Image-to-Video) | 41 |
| | [Reference-to-Video](Video-Generation/Reference-to-Video) | 8 |
| | [Long-Form-Generation](Video-Generation/Long-Form-Generation) | 7 |
| | [World-Models](Video-Generation/World-Models) | 5 |
| [Video-Editing-and-Control](Video-Editing-and-Control/README.md) | | 65 |
| | [Video-Editing-and-Tools](Video-Editing-and-Control/Video-Editing-and-Tools) | 14 |
| | [Character-Animation-Video-to-Video](Video-Editing-and-Control/Character-Animation-Video-to-Video) | 51 |
| [Talking-Avatar-and-Audio](Talking-Avatar-and-Audio/README.md) | | 60 |
| | [Talking-Avatar-and-Lip-Sync](Talking-Avatar-and-Audio/Talking-Avatar-and-Lip-Sync) | 54 |
| | [Audio-Reactive](Talking-Avatar-and-Audio/Audio-Reactive) | 6 |
| [Video-Enhancement](Video-Enhancement/README.md) | | 21 |
| | [Video-Upscaling](Video-Enhancement/Video-Upscaling) | 18 |
| | [Frame-Interpolation](Video-Enhancement/Frame-Interpolation) | 3 |
| [Supporting-Vision](Supporting-Vision/README.md) | | 9 |
| | [Depth-and-Normals](Supporting-Vision/Depth-and-Normals) | 4 |
| | [Pose-and-Line-Art](Supporting-Vision/Pose-and-Line-Art) | 3 |
| | [Segmentation](Supporting-Vision/Segmentation) | 2 |
| **Total** | | **239** |

Atlas coverage, entry by entry: [COVERAGE.md](COVERAGE.md).

## Model families

- **Foundation and image-to-video:** Wan 2.1 / 2.2 (T2V, I2V, FLF2V, TI2V 5B, Wan-Alpha, GGUF + Lightx2v), LTX-Video 0.9.x, LTX-2 / 2.3 / 2.5 (with audio), MiniMax H3 / FastH3 / Pika-H3-Flex, HunyuanVideo and HunyuanVideo 1.5, Kandinsky 5 Lite and Kandinsky 6, CogVideoX, Mochi 1, Cosmos 1 and Cosmos-Predict2, Pyramid Flow, Stable Video Diffusion, DynamiCrafter, ToonCrafter, AnimateDiff / AnimateLCM, Capybara, Causal Forcing.
- **Reference-to-video, long-form and world models:** MiniMax H3 reference-to-video and multi-frame reference, Phantom, Stand-In, VACE reference, SkyReels-A2; MAGI-1, FramePack, SkyReels V2 diffusion forcing, LongCat-Video, Wan 2.2 + Pusa; Hy-Nomas world model.
- **Editing and control:** Wan 2.1 VACE (control, reference, inpaint, outpaint), Wan 2.2 Fun Control and Fun Camera, Wan-Move, ReCamMaster, ProPainter, VOID, LTX-2.3 Obscura and subtitle-removal LoRAs, Bernini-R relighting, Capybara instruction edit.
- **Character animation:** Wan 2.2 Animate, Wan Animate 2, SCAIL / SCAIL-2, SteadyDancer, MimicMotion, Champ, MusePose, Animate Anyone (community), MiniMax H3 character / head swap, pose ControlNet, VFX and style LoRAs, ReActor face swap.
- **Talking avatars and lip-sync:** InfiniteTalk, Wan 2.2 S2V, HuMo, FantasyTalking, FantasyPortrait, EchoMimic V1–V3, Hallo / Hallo2, Sonic, LongCat-Avatar, SkyReels V3 talking avatar, Kandinsky S2V, LTX-2 / 2.3 dubbing and ID-LoRA, MiniMax H3 audio sync and timelines, LatentSync / DubSync / TBDub, MuseTalk, Wav2Lip, LivePortrait.
- **Enhancement:** SeedVR2 (3B / 7B, wrapper and core nodes), FlashVSR, RelayVSR, Wan 2.2 refine, MiniMax H3 sharpen / regenerate LoRAs, NVIDIA RTX Video; FILM and GIMM-VFI frame interpolation.
- **Supporting vision:** Depth Anything V2 / 3, Video Depth Anything, NormalCrafter, DWPose, SDPose, line art, SAM 2, SAM 3.

## Model coverage summary

Against the 237 entries of the Open-Source Video Model Atlas (92 families):

| Disposition | Entries |
|---|---|
| new workflow collected | 60 |
| useful variation added | 5 |
| already present | 18 |
| equivalent already exists | 41 |
| availability or redistribution unconfirmed | 9 |
| no suitable ComfyUI workflow | 104 |

83 entries are covered by a workflow (already present, new or a useful variation); 41 more load in an existing workflow; 104 have no suitable ComfyUI workflow; 9 are unconfirmed for weights or redistribution.

### Not available in ComfyUI

No authentic, redistributable ComfyUI workflow was found for these atlas entries, so none was added (reasons in [COVERAGE.md](COVERAGE.md) and each category README):

- **Video Generation:** HunyuanVideo Avatar (unconfirmed), HunyuanVideo Foley (support extension), LongCat interactive video, Kandinsky 5 Camera-Control LoRA, Open-Sora 1.0, Open-Sora 1.1, Open-Sora 1.2, Open-Sora 2.0 11B, Open-Sora Plan v1.0, Open-Sora Plan v1.1, Open-Sora Plan v1.2 I2V, Open-Sora Plan v1.3, Open-Sora Plan v1.5 (Ascend NPU), Step-Video T2V, Step-Video T2V Turbo, Step-Video TI2V, Pyramid Flow SD3 384p, Allegro T2V, Allegro TI2V, VideoCrafter1 T2V 1024, VideoCrafter1 T2V 512, VideoCrafter1 I2V 1024, VideoCrafter1 I2V 512, VideoCrafter2 T2V 512, FramePack P1 research update (unconfirmed), AnimateDiff SDXL beta, AnimateDiff SparseCtrl, I2VGen-XL, VGen VideoComposer, SEINE generative transitions, LaVie text to video, Latte T2V, Latte-1 T2V, Latte I2I training baseline, Helios Base 14B, Helios Mid 14B, Helios Distilled 14B, Cosmos3 Edge 4B, Cosmos3 Nano 16B, Cosmos3 Super 64B, Cosmos Predict2.5 2B pre-trained, Cosmos Predict2.5 2B post-trained, Cosmos Predict2.5 2B distilled, Cosmos Predict2.5 14B pre-trained, Cosmos Predict2.5 14B post-trained, Cosmos Predict2.5 auto multi-view, Cosmos Predict2.5 robot action-conditioned.
- **Video Editing and Control:** Wan-Animate-2 Lite research variant, Wan-Dancer 14B, VACE LTX 0.9, SkyReels-A1 portrait animation, MagicAnimate pose-driven character, UniAnimate pose animation (unconfirmed), Rerender A Video keyframe edit, Rerender A Video LoRA+ControlNet, TokenFlow zero-shot V2V, FateZero cross-attention edit, Tune-A-Video one-shot tuning, Vid2Vid-Zero video editing, AnyV2V video editing, PnP Video (discovery lead), Video-P2P prompt editing, LOVECon stylization, VideoSwap semantic swap, ControlVideo spatial control, FRESCO feature correspondence, VideoPainter video inpainting, E2FGVI 432x240, E2FGVI-HQ arbitrary resolution, STTN video inpainting, FuseFormer video inpainting.
- **Talking Avatars, Lip-Sync and Audio-Driven Video:** SkyReels V3 Reference-to-Video 14B, SkyReels V3 Video Extension 14B, LivePortrait animals / community branch, SadTalker 256, SadTalker 512 beta, HunyuanPortrait image-audio animation, OmniAvatar audio to full-body video, VideoReTalking lip-sync repair.
- **Video Upscaling and Enhancement:** SeedVR 3B, SeedVR 7B, VRT video super-resolution, VRT video deblurring, VRT video denoising, VRT video interpolation, RVRT recurrent restoration, BasicVSR video super-resolution, IconVSR, BasicVSR++, RealBasicVSR, RIFE 4.22 lite (unconfirmed), RIFE 4.7 (unconfirmed), RIFE 4.10 (unconfirmed), RIFE arbitrary timestep (unconfirmed), DAIN depth-aware interpolation, EDVR video SR, EDVR deblurring, TecoGAN video upscaling, RVRT super-resolution, RVRT deblur, RVRT denoise, VEnhancer spatial upscale, VEnhancer temporal refine, Upscale-A-Video 4x, IFRNet interpolation, AMT intermediate frame generation, GMFSS Fortuna interpolation.
- **Supporting Vision for Video:** CoTracker2 (unconfirmed), CoTracker3 (unconfirmed), XMem long-term video masks, DeAOT object tracking masks, RAFT optical flow, GMFlow optical flow.

## How to use

1. Drag a `.json` file onto the ComfyUI canvas (files ending in `-api` are API-format graphs for the ComfyUI HTTP API; load them with *Workflow → Open*).
2. Install missing custom nodes with ComfyUI-Manager (*Install Missing Custom Nodes*). "Core only" means a recent ComfyUI build is enough — newer models (LTX-2.5, MiniMax H3, Kandinsky 6, Wan Animate 2) need an up-to-date ComfyUI.
3. Download the models listed in the category README (or in the note inside the graph) into the usual `ComfyUI/models/` subfolders (`diffusion_models`, `text_encoders`, `vae`, `clip_vision`, `loras`, `upscale_models`). Several wrapper nodes download weights automatically on first run.
4. Set the inputs (prompt, start / end image, reference images, driving video, audio) and press **Run**.

Video models are heavy: most need 16–24 GB+ VRAM; *Low VRAM*, *FP8*, *INT8*, *GGUF*, *4-step* / *8-step* and *distilled* variants trade quality for memory and speed. Use only people, faces and voices you have consent to use.

### Most-used custom nodes

| Custom node pack | Workflows |
|---|---|
| comfyui-videohelpersuite | 77 |
| comfyui-kjnodes | 53 |
| comfyui-pixaroma | 48 |
| comfyui-wanvideowrapper | 29 |
| rgthree-comfy | 11 |
| comfyui-easy-use | 11 |
| comfyui_layerstyle | 10 |
| comfyui_essentials | 10 |
| comfyui-wananimatepreprocess | 8 |
| dubsync nodes | 7 |
| comfyui-melbandroformer | 7 |
| comfyui_controlnet_aux | 7 |
| comfyui-gguf | 6 |
| wan-scail2-gap | 6 |
| comfyui-custom-scripts | 5 |

See the [root README](../README.md) for setup and the other sections, or [`00-LIBRARY-INDEX.md`](../00-LIBRARY-INDEX.md) for a flat list of every workflow.
