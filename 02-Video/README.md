# AI Video — ComfyUI workflows

All video workflows in the library: **239 workflows** in three categories — text-to-video, image-to-video, reference-to-video, long-form generation and world models; video editing, control and character animation; talking avatars, lip-sync and audio-reactive video; video upscaling and frame interpolation; and supporting vision (depth, pose, segmentation). Each category README lists every workflow with what it does, the models it loads and the custom nodes it needs, and — for the Open-Source Video Model Atlas additions (Nov 2026) — the source, model download, code licence and weight licence. The atlas additions were checked to be valid ComfyUI workflow JSON for their model and task; they have **not** been runtime-tested.

## Folders

| Category | What is inside | Model folders | Workflows |
|---|---|---|---|
| **[Generation](Generation/README.md)** | Workflows that create a new video: text-to-video, image-to-video, first / last frame, reference-to-video, long-form generation, world models, talking avatars from a picture and audio, and audio-reactive visuals. | [AnimateDiff](Generation/AnimateDiff), [Capybara](Generation/Capybara), [CogVideoX](Generation/CogVideoX), [Cosmos](Generation/Cosmos), [DynamiCrafter](Generation/DynamiCrafter), [EchoMimic](Generation/EchoMimic), [FramePack](Generation/FramePack), [Hallo](Generation/Hallo), [HunyuanVideo](Generation/HunyuanVideo), [HY-Nomas](Generation/HY-Nomas), [Kandinsky](Generation/Kandinsky), [LivePortrait](Generation/LivePortrait), [LongCat-Video](Generation/LongCat-Video), [LTX-2](Generation/LTX-2), [LTX-Video](Generation/LTX-Video), [MAGI-1](Generation/MAGI-1), [MiniMax-H3](Generation/MiniMax-H3), [Mochi-1](Generation/Mochi-1), [Pyramid-Flow](Generation/Pyramid-Flow), [SkyReels](Generation/SkyReels), [Sonic](Generation/Sonic), [SVD](Generation/SVD), [ToonCrafter](Generation/ToonCrafter), [Wan-2.1](Generation/Wan-2.1), [Wan-2.2](Generation/Wan-2.2), [Other](Generation/Other) | 127 |
| **[Editing](Editing/README.md)** | Workflows that change or analyse an existing video: VACE and instruction edits, inpaint / outpaint, object and subtitle removal, relighting, camera and motion control, character / head / face swap, motion transfer, lip-sync and dubbing, and supporting vision (depth, normals, pose, line art, segmentation). | [Animate-Anyone](Editing/Animate-Anyone), [AnimateDiff](Editing/AnimateDiff), [Capybara](Editing/Capybara), [Champ](Editing/Champ), [Depth-Anything](Editing/Depth-Anything), [DubSync](Editing/DubSync), [DWPose](Editing/DWPose), [LatentSync](Editing/LatentSync), [LivePortrait](Editing/LivePortrait), [LTX-2](Editing/LTX-2), [MimicMotion](Editing/MimicMotion), [MiniMax-H3](Editing/MiniMax-H3), [MusePose](Editing/MusePose), [MuseTalk](Editing/MuseTalk), [NormalCrafter](Editing/NormalCrafter), [ProPainter](Editing/ProPainter), [ReActor](Editing/ReActor), [SAM-2](Editing/SAM-2), [SAM-3](Editing/SAM-3), [SDPose](Editing/SDPose), [Video-Depth-Anything](Editing/Video-Depth-Anything), [VOID](Editing/VOID), [Wan-2.1](Editing/Wan-2.1), [Wan-2.2](Editing/Wan-2.2), [Wan-Animate-2](Editing/Wan-Animate-2), [Wan-Move](Editing/Wan-Move), [Wav2Lip](Editing/Wav2Lip), [Other](Editing/Other) | 91 |
| **[Enhancement](Enhancement/README.md)** | Video upscaling, super-resolution and refinement, and frame interpolation. | [FILM](Enhancement/FILM), [FlashVSR](Enhancement/FlashVSR), [GIMM-VFI](Enhancement/GIMM-VFI), [MiniMax-H3](Enhancement/MiniMax-H3), [NVIDIA-RTX-VSR](Enhancement/NVIDIA-RTX-VSR), [RelayVSR](Enhancement/RelayVSR), [SeedVR2](Enhancement/SeedVR2), [Wan-2.2](Enhancement/Wan-2.2) | 21 |
| **Total** | | | **239** |

### Finding a task

| Task (file name prefix) | Where | Model folders |
|---|---|---|
| `audio-reactive` | [Generation](Generation/README.md) | [AnimateDiff](Generation/README.md#animatediff), [LivePortrait](Generation/README.md#liveportrait), [Wan-2.1](Generation/README.md#wan-21), [Other](Generation/README.md#other) |
| `audio-reactive` | [Editing](Editing/README.md) | [AnimateDiff](Editing/README.md#animatediff) |
| `camera-control` | [Editing](Editing/README.md) | [Wan-2.2](Editing/README.md#wan-22) |
| `camera-rerender` | [Editing](Editing/README.md) | [Wan-2.1](Editing/README.md#wan-21) |
| `character-swap` | [Editing](Editing/README.md) | [MiniMax-H3](Editing/README.md#minimax-h3), [Wan-2.1](Editing/README.md#wan-21), [Wan-2.2](Editing/README.md#wan-22) |
| `depth-map` | [Editing](Editing/README.md) | [Depth-Anything](Editing/README.md#depth-anything), [Video-Depth-Anything](Editing/README.md#video-depth-anything) |
| `edit` | [Editing](Editing/README.md) | [Capybara](Editing/README.md#capybara) |
| `expression-retarget` | [Editing](Editing/README.md) | [LivePortrait](Editing/README.md#liveportrait) |
| `expression-transfer` | [Editing](Editing/README.md) | [Wan-2.1](Editing/README.md#wan-21) |
| `face-swap` | [Editing](Editing/README.md) | [ReActor](Editing/README.md#reactor) |
| `frame-interpolation` | [Enhancement](Enhancement/README.md) | [FILM](Enhancement/README.md#film), [GIMM-VFI](Enhancement/README.md#gimm-vfi) |
| `head-swap` | [Editing](Editing/README.md) | [MiniMax-H3](Editing/README.md#minimax-h3) |
| `img2video` | [Generation](Generation/README.md) | [AnimateDiff](Generation/README.md#animatediff), [Capybara](Generation/README.md#capybara), [CogVideoX](Generation/README.md#cogvideox), [DynamiCrafter](Generation/README.md#dynamicrafter), [HunyuanVideo](Generation/README.md#hunyuanvideo), [Kandinsky](Generation/README.md#kandinsky), [LTX-2](Generation/README.md#ltx-2), [LTX-Video](Generation/README.md#ltx-video), [MiniMax-H3](Generation/README.md#minimax-h3), [Pyramid-Flow](Generation/README.md#pyramid-flow), [SVD](Generation/README.md#svd), [ToonCrafter](Generation/README.md#tooncrafter), [Wan-2.1](Generation/README.md#wan-21), [Wan-2.2](Generation/README.md#wan-22) |
| `inpaint` | [Editing](Editing/README.md) | [Wan-2.1](Editing/README.md#wan-21) |
| `lineart-extraction` | [Editing](Editing/README.md) | [Other](Editing/README.md#other) |
| `lip-sync` | [Editing](Editing/README.md) | [DubSync](Editing/README.md#dubsync), [LatentSync](Editing/README.md#latentsync), [LTX-2](Editing/README.md#ltx-2), [MuseTalk](Editing/README.md#musetalk), [Wan-2.1](Editing/README.md#wan-21), [Wav2Lip](Editing/README.md#wav2lip) |
| `long-video` | [Generation](Generation/README.md) | [FramePack](Generation/README.md#framepack), [LongCat-Video](Generation/README.md#longcat-video), [MAGI-1](Generation/README.md#magi-1), [SkyReels](Generation/README.md#skyreels), [Wan-2.2](Generation/README.md#wan-22) |
| `motion-control` | [Editing](Editing/README.md) | [Wan-Move](Editing/README.md#wan-move) |
| `motion-transfer` | [Editing](Editing/README.md) | [Animate-Anyone](Editing/README.md#animate-anyone), [Champ](Editing/README.md#champ), [MimicMotion](Editing/README.md#mimicmotion), [MiniMax-H3](Editing/README.md#minimax-h3), [MusePose](Editing/README.md#musepose), [Wan-2.1](Editing/README.md#wan-21), [Wan-Animate-2](Editing/README.md#wan-animate-2) |
| `normal-map` | [Editing](Editing/README.md) | [NormalCrafter](Editing/README.md#normalcrafter) |
| `object-and-interaction-removal` | [Editing](Editing/README.md) | [VOID](Editing/README.md#void) |
| `object-removal` | [Editing](Editing/README.md) | [LTX-2](Editing/README.md#ltx-2), [ProPainter](Editing/README.md#propainter) |
| `outpaint` | [Editing](Editing/README.md) | [Wan-2.1](Editing/README.md#wan-21) |
| `pixaroma` | [Editing](Editing/README.md) | [Other](Editing/README.md#other) |
| `portrait-animation` | [Generation](Generation/README.md) | [LivePortrait](Generation/README.md#liveportrait) |
| `pose-keypoints` | [Editing](Editing/README.md) | [DWPose](Editing/README.md#dwpose), [SDPose](Editing/README.md#sdpose) |
| `ref2video` | [Generation](Generation/README.md) | [MiniMax-H3](Generation/README.md#minimax-h3), [SkyReels](Generation/README.md#skyreels), [Wan-2.1](Generation/README.md#wan-21) |
| `relight` | [Editing](Editing/README.md) | [Wan-2.2](Editing/README.md#wan-22) |
| `segment` | [Editing](Editing/README.md) | [SAM-2](Editing/README.md#sam-2), [SAM-3](Editing/README.md#sam-3) |
| `style-transfer` | [Editing](Editing/README.md) | [MiniMax-H3](Editing/README.md#minimax-h3) |
| `talking-avatar` | [Generation](Generation/README.md) | [EchoMimic](Generation/README.md#echomimic), [Hallo](Generation/README.md#hallo), [Kandinsky](Generation/README.md#kandinsky), [LongCat-Video](Generation/README.md#longcat-video), [LTX-2](Generation/README.md#ltx-2), [MiniMax-H3](Generation/README.md#minimax-h3), [SkyReels](Generation/README.md#skyreels), [Sonic](Generation/README.md#sonic), [Wan-2.1](Generation/README.md#wan-21), [Wan-2.2](Generation/README.md#wan-22) |
| `txt2img2video` | [Generation](Generation/README.md) | [SVD](Generation/README.md#svd) |
| `txt2video` | [Generation](Generation/README.md) | [CogVideoX](Generation/README.md#cogvideox), [Cosmos](Generation/README.md#cosmos), [HunyuanVideo](Generation/README.md#hunyuanvideo), [Kandinsky](Generation/README.md#kandinsky), [LTX-2](Generation/README.md#ltx-2), [LTX-Video](Generation/README.md#ltx-video), [MiniMax-H3](Generation/README.md#minimax-h3), [Mochi-1](Generation/README.md#mochi-1), [Pyramid-Flow](Generation/README.md#pyramid-flow), [Wan-2.1](Generation/README.md#wan-21), [Wan-2.2](Generation/README.md#wan-22) |
| `upscale` | [Enhancement](Enhancement/README.md) | [FlashVSR](Enhancement/README.md#flashvsr), [MiniMax-H3](Enhancement/README.md#minimax-h3), [NVIDIA-RTX-VSR](Enhancement/README.md#nvidia-rtx-vsr), [RelayVSR](Enhancement/README.md#relayvsr), [SeedVR2](Enhancement/README.md#seedvr2), [Wan-2.2](Enhancement/README.md#wan-22) |
| `v2v` | [Editing](Editing/README.md) | [Wan-2.1](Editing/README.md#wan-21), [Wan-2.2](Editing/README.md#wan-22) |
| `vfx-edit` | [Editing](Editing/README.md) | [MiniMax-H3](Editing/README.md#minimax-h3) |
| `video2world` | [Generation](Generation/README.md) | [Cosmos](Generation/README.md#cosmos) |
| `voice-dubbing` | [Editing](Editing/README.md) | [LTX-2](Editing/README.md#ltx-2) |
| `world-model` | [Generation](Generation/README.md) | [HY-Nomas](Generation/README.md#hy-nomas) |

Atlas coverage, entry by entry: [COVERAGE.md](COVERAGE.md).

## Naming and folder convention

- **Folders:** exactly three levels, `<section>/<Category>/<Model>/<file>.json`. Image and Video use the categories `Generation` (creates a new image or video), `Editing` (changes or analyses an existing one) and `Enhancement` (Image: upscaling only; Video: upscaling and frame interpolation). Audio uses `Music` and `Speech`. A model folder holds only workflow files, however many there are; there are no task subfolders.
- **Model folders** are TitleCase with hyphens and use one spelling across all sections (`Krea-2`, `FLUX-2`, `Qwen-Image`, `Wan-2.2`, `LTX-2`, `MiniMax-H3`, `ACE-Step-1.5`, `Qwen3-TTS`, `Whisper` ...). Generic, utility and multi-model workflows go in `Other/`.
- **File names** carry the task, because there is no task folder: `<task>[-<variant>][-<size>][-<precision>][-<feature>].json`, for example `Generation/Krea-2/txt2img-simple-int8-lora.json`, `Editing/Krea-2/outfit-transfer-v2.json`, `Enhancement/SeedVR2/upscale-7b-int8-native.json`. The model name is not repeated in the file name. Names are lowercase kebab-case and unique inside their folder; `-api` marks API-format graphs and `epNN` the tutorial episode a variant came from.
- **Common task prefixes:** `txt2img`, `img2img`, `img2prompt2img`, `controlnet`, `edit`, `multi-edit`, `inpaint`, `outpaint`, `object-removal`, `remove-background`, `outfit-change`, `relight`, `identity`, `reference`, `try-on`, `segment`, `depth-map`, `upscale`; `txt2video`, `img2video`, `ref2video`, `long-video`, `talking-avatar`, `lip-sync`, `character-swap`, `motion-transfer`, `frame-interpolation`; `txt2music`, `lyrics2song`, `cover`, `stem-split`, `tts`, `voice-clone`, `voice-design`, `voice-conversion`, `stt`, `subtitles`.

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
