# Open-Source Video Model Atlas — coverage tracker

[← 02-Video overview](README.md)

Final disposition of every entry in the *Open-Source Video Model Atlas* research document (117 pages, 92 model families, 237 named model / checkpoint / variant / supporting entries). Built from the four collection slices (PRs #25–#28) and resolved at integration: where slices disagreed, the strongest supported disposition wins (new workflow > useful variation > already present > equivalent exists > unconfirmed > none) and the other view is kept in [`coverage-final.tsv` notes](#how-conflicts-were-resolved). No workflow was runtime-tested.

| Disposition | Entries |
|---|---|
| new workflow collected | 60 |
| useful variation added | 5 |
| already present | 18 |
| equivalent already exists | 41 |
| availability or redistribution unconfirmed | 9 |
| no suitable ComfyUI workflow | 104 |
| **Total** | **237** |

"Already present" = the library had a workflow before the atlas work; "new workflow collected" = a workflow JSON was added for it; "useful variation added" = a distinct capability variant was added next to existing coverage; "equivalent already exists" = an existing workflow covers it (checkpoint, size or quantisation swap); "availability or redistribution unconfirmed" = weights or a redistributable workflow could not be confirmed, so the source is only linked; "no suitable ComfyUI workflow" = no authentic ComfyUI workflow was found, and none was invented.

## Foundation Generation (56)

| # | Family | Entry | Disposition | Workflow or reason |
|---|---|---|---|---|
| 1 | Wan 2.1 | Wan2.1 T2V 1.3B | new workflow collected | [`wan-2.1-1.3b-txt2video-low-vram`](Generation/Wan-2.1/txt2video-13b-low-vram.json) |
| 1 | Wan 2.1 | Wan2.1 T2V 14B | useful variation added | [`wan-2.1-alpha-14b-txt2video-transparent-rgba`](Generation/Wan-2.1/txt2video-alpha-14b-rgba.json) (14B T2V + Wan-Alpha RGBA); plain 14B loads in the 1.3B graph |
| 1 | Wan 2.1 | Wan2.1 I2V 14B 480p | new workflow collected | [`wan-2.1-14b-img2video-480p`](Generation/Wan-2.1/img2video-14b-480p.json) |
| 1 | Wan 2.1 | Wan2.1 I2V 14B 720p | equivalent already exists | [`wan-2.1-14b-img2video-480p`](Generation/Wan-2.1/img2video-14b-480p.json) (swap to 720p checkpoint) |
| 1 | Wan 2.1 | Wan2.1 FLF2V 14B | new workflow collected | [`wan-2.1-14b-flf2v-first-last-frame-720p`](Generation/Wan-2.1/img2video-14b-720p-first-last-frame.json) |
| 2 | Wan 2.2 | Wan2.2 T2V A14B | new workflow collected | [`wan-2.2-14b-txt2video`](Generation/Wan-2.2/txt2video-14b.json) |
| 2 | Wan 2.2 | Wan2.2 I2V A14B | useful variation added | existing `Generation/Wan-2.2/img2video-gguf-lightx2v-4-step*.json`; added [`wan-2.2-14b-img2video-first-last-frame`](Generation/Wan-2.2/img2video-14b-first-last-frame.json) |
| 2 | Wan 2.2 | Wan2.2 TI2V 5B | new workflow collected | [`wan-2.2-5b-ti2v-text-or-image-to-video-low-vram`](Generation/Wan-2.2/img2video-5b-ti2v-low-vram.json) |
| 2 | Wan 2.2 | Wan2.2 S2V 14B | new workflow collected | [`wan-2.2-s2v-sound-to-video-talking-avatar`](Generation/Wan-2.2/talking-avatar-s2v.json) |
| 2 | Wan 2.2 | Wan2.2 Animate 14B | already present | `Editing/Wan-2.2/character-swap-animate-*.json` (5 files, WanVideoWrapper); native template skipped as equivalent |
| 5 | LTX-Video legacy | LTX-Video 0.9.1 | new workflow collected | [`ltx-video-0.9-txt2video`](Generation/LTX-Video/txt2video-v09.json) |
| 5 | LTX-Video legacy | LTX-Video 0.9.5 | new workflow collected | [`ltx-video-0.9.5-img2video`](Generation/LTX-Video/img2video-v095.json); [`ltx-video-0.9.5-img2video-keyframe-guides-first-last`](Generation/LTX-Video/img2video-v095-keyframe-guides-first-last.json) |
| 5 | LTX-Video legacy | LTX-Video 0.9.7 | equivalent already exists | loads in the LTX-Video 0.9.x graphs; dedicated 0.9.7 workflows were removed upstream (ComfyUI-LTXVideo now ships 2.x only) |
| 5 | LTX-Video legacy | LTX-Video 0.9.8 | equivalent already exists | loads in the LTX-Video 0.9.x graphs; no maintained 0.9.8 workflow upstream |
| 8 | HunyuanVideo | HunyuanVideo 13B T2V | new workflow collected | [`hunyuanvideo-13b-txt2video`](Generation/HunyuanVideo/txt2video-13b.json) |
| 8 | HunyuanVideo | HunyuanVideo I2V | new workflow collected | [`hunyuanvideo-img2video-v2`](Generation/HunyuanVideo/img2video-base-v2.json) (v1 concat variant skipped) |
| 8 | HunyuanVideo | HunyuanVideo Avatar | availability or redistribution unconfirmed | smthemex/ComfyUI_HunyuanAvatar_Sm JSONs under Tencent Hunyuan Community License (territory-limited); linked in README |
| 8 | HunyuanVideo | HunyuanVideo Foley (support extension) | no suitable ComfyUI workflow | node packs exist (if-ai, aistudynow) but no example workflow JSON |
| 9 | HunyuanVideo 1.5 | HunyuanVideo 1.5 T2V 8.3B | new workflow collected | [`hunyuanvideo-1.5-720p-txt2video-1080p-sr`](Generation/HunyuanVideo/txt2video-v15-720p-1080p-sr.json) |
| 9 | HunyuanVideo 1.5 | HunyuanVideo 1.5 I2V 8.3B | new workflow collected | [`hunyuanvideo-1.5-720p-img2video-1080p-sr`](Generation/HunyuanVideo/img2video-v15-720p-1080p-sr.json) |
| 9 | HunyuanVideo 1.5 | HunyuanVideo 1.5 I2V Step-Distilled | equivalent already exists | step-distilled checkpoint loads in [`hunyuanvideo-1.5-720p-img2video-1080p-sr`](Generation/HunyuanVideo/img2video-v15-720p-1080p-sr.json) |
| 11 | Kandinsky Video 5 | Kandinsky 5 Lite T2V 2B SFT | new workflow collected | [`kandinsky-5-lite-txt2video`](Generation/Kandinsky/txt2video-v5-lite.json) |
| 11 | Kandinsky Video 5 | Kandinsky 5 Lite I2V | new workflow collected | [`kandinsky-5-lite-img2video`](Generation/Kandinsky/img2video-v5-lite.json) |
| 11 | Kandinsky Video 5 | Kandinsky 5 Lite 16-step Flash | equivalent already exists | Flash checkpoint loads in the Lite T2V graph |
| 11 | Kandinsky Video 5 | Kandinsky 5 Pro 19B T2V | equivalent already exists | Pro checkpoint loads in the Lite T2V graph; no separate published workflow |
| 11 | Kandinsky Video 5 | Kandinsky 5 Pro I2V | equivalent already exists | Pro I2V loads in the Lite I2V graph |
| 11 | Kandinsky Video 5 | Kandinsky 5 Camera-Control LoRA | no suitable ComfyUI workflow | no published camera-control LoRA workflow |
| 13 | CogVideoX | CogVideoX 2B T2V | equivalent already exists | 2B uses the 5B T2V wrapper graph (model selector) |
| 13 | CogVideoX | CogVideoX 5B T2V | new workflow collected | [`txt2video-5b`](Generation/CogVideoX/txt2video-5b.json); [`cogvideox-5b-first-last-frame-interpolation`](Generation/CogVideoX/img2video-5b-first-last-frame.json) |
| 13 | CogVideoX | CogVideoX 5B I2V | equivalent already exists | CogVideoX 1.0 5B I2V skipped; 1.5 I2V kept |
| 13 | CogVideoX | CogVideoX 1.5 5B T2V | equivalent already exists | 1.5 T2V selectable in the CogVideoX wrapper T2V graph |
| 13 | CogVideoX | CogVideoX 1.5 5B I2V | new workflow collected | [`cogvideox-1.5-5b-img2video`](Generation/CogVideoX/img2video-v15-5b.json) |
| 14 | Mochi | Mochi 1 Preview 10B | already present | [`txt2video`](Generation/Mochi-1/txt2video.json) |
| 14 | Mochi | Mochi 1 LoRA-enabled | equivalent already exists | LoRA adds a LoraLoader to [`txt2video`](Generation/Mochi-1/txt2video.json); no separate official workflow |
| 15 | Open-Sora | Open-Sora 1.0 | no suitable ComfyUI workflow | no maintained ComfyUI workflow |
| 15 | Open-Sora | Open-Sora 1.1 | no suitable ComfyUI workflow | no maintained ComfyUI workflow |
| 15 | Open-Sora | Open-Sora 1.2 | no suitable ComfyUI workflow | only stale community port |
| 15 | Open-Sora | Open-Sora 2.0 11B | no suitable ComfyUI workflow | no maintained ComfyUI workflow |
| 16 | Open-Sora Plan | Open-Sora Plan v1.0 | no suitable ComfyUI workflow | official scripts only |
| 16 | Open-Sora Plan | Open-Sora Plan v1.1 | no suitable ComfyUI workflow | official scripts only |
| 16 | Open-Sora Plan | Open-Sora Plan v1.2 I2V | no suitable ComfyUI workflow | official scripts only |
| 16 | Open-Sora Plan | Open-Sora Plan v1.3 | no suitable ComfyUI workflow | official scripts only |
| 16 | Open-Sora Plan | Open-Sora Plan v1.5 (Ascend NPU) | no suitable ComfyUI workflow | Ascend NPU only |
| 20 | Step Video | Step-Video T2V | no suitable ComfyUI workflow | no maintained ComfyUI workflow found |
| 20 | Step Video | Step-Video T2V Turbo | no suitable ComfyUI workflow | no maintained ComfyUI workflow found |
| 20 | Step Video | Step-Video TI2V | no suitable ComfyUI workflow | no maintained ComfyUI workflow found |
| 21 | Pyramid Flow | Pyramid Flow SD3 384p | no suitable ComfyUI workflow | SD3 variant superseded; wrapper only publishes miniFLUX examples |
| 21 | Pyramid Flow | Pyramid Flow miniFLUX 384p | new workflow collected | [`txt2video-miniflux`](Generation/Pyramid-Flow/txt2video-miniflux.json); [`img2video-miniflux`](Generation/Pyramid-Flow/img2video-miniflux.json) |
| 21 | Pyramid Flow | Pyramid Flow miniFLUX 768p | equivalent already exists | 768p example differs only by resolution/checkpoint |
| 22 | Allegro | Allegro T2V | no suitable ComfyUI workflow | Diffusers only |
| 22 | Allegro | Allegro TI2V | no suitable ComfyUI workflow | Diffusers only |
| 23 | VideoCrafter | VideoCrafter1 T2V 1024 | no suitable ComfyUI workflow | old unmaintained community nodes, no published workflow; non-commercial weights |
| 23 | VideoCrafter | VideoCrafter1 T2V 512 | no suitable ComfyUI workflow | as above |
| 23 | VideoCrafter | VideoCrafter1 I2V 1024 | no suitable ComfyUI workflow | as above |
| 23 | VideoCrafter | VideoCrafter1 I2V 512 | no suitable ComfyUI workflow | as above |
| 23 | VideoCrafter | VideoCrafter2 T2V 512 | no suitable ComfyUI workflow | as above |

## Image-To-Video Generation (9)

| # | Family | Entry | Disposition | Workflow or reason |
|---|---|---|---|---|
| 24 | DynamiCrafter | DynamiCrafter 256 | equivalent already exists | smaller checkpoint for [`img2video-1024`](Generation/DynamiCrafter/img2video-1024.json) |
| 24 | DynamiCrafter | DynamiCrafter 512 | equivalent already exists | smaller checkpoint for [`img2video-1024`](Generation/DynamiCrafter/img2video-1024.json) |
| 24 | DynamiCrafter | DynamiCrafter 1024 | new workflow collected | [`img2video-1024`](Generation/DynamiCrafter/img2video-1024.json) |
| 24 | DynamiCrafter | DynamiCrafter 512 interpolation | useful variation added | [`img2video-cartoon-keyframe-interpolation`](Generation/ToonCrafter/img2video-cartoon-keyframe-interpolation.json) (ToonCrafter, DynamiCrafter-based interpolation); also relevant to interpolation slice |
| 27 | Stable Video Diffusion | Stable Video Diffusion SVD | new workflow collected | [`img2video`](Generation/SVD/img2video.json) |
| 27 | Stable Video Diffusion | Stable Video Diffusion SVD-XT | new workflow collected | [`txt2img2video-xt-sdxl`](Generation/SVD/txt2img2video-xt-sdxl.json) |
| 27 | Stable Video Diffusion | Stable Video Diffusion XT 1.1 | equivalent already exists | XT 1.1 checkpoint loads in the SVD graphs |
| 28 | VGen / I2VGen-XL | I2VGen-XL | no suitable ComfyUI workflow | no maintained ComfyUI graph |
| 28 | VGen / I2VGen-XL | VGen VideoComposer | no suitable ComfyUI workflow | no maintained ComfyUI graph |

## Animation / Motion Module (3)

| # | Family | Entry | Disposition | Workflow or reason |
|---|---|---|---|---|
| 26 | AnimateDiff | AnimateDiff SD 1.5 motion module | new workflow collected | [`animatediff-animatelcm-ipadapter-looping-animation-from-images`](Generation/AnimateDiff/img2video-animatelcm-ipadapter-loop.json) (AnimateLCM SD1.5 motion module) |
| 26 | AnimateDiff | AnimateDiff SDXL beta | no suitable ComfyUI workflow | AnimateDiff-Evolved publishes no workflow JSONs |
| 26 | AnimateDiff | AnimateDiff SparseCtrl | no suitable ComfyUI workflow | no official SparseCtrl workflow JSON published |

## Long-Form Generation (23)

| # | Family | Entry | Disposition | Workflow or reason |
|---|---|---|---|---|
| 10 | LongCat-Video | LongCat-Video T2V | new workflow collected | [`long-video-img2video-with-extension`](Generation/LongCat-Video/long-video-img2video-with-extension.json) (TI2V graph covers T2V and I2V) |
| 10 | LongCat-Video | LongCat-Video I2V | new workflow collected | [`long-video-img2video-with-extension`](Generation/LongCat-Video/long-video-img2video-with-extension.json) |
| 10 | LongCat-Video | LongCat-Video continuation | new workflow collected | [`long-video-img2video-with-extension`](Generation/LongCat-Video/long-video-img2video-with-extension.json) (overlap extension passes) |
| 10 | LongCat-Video | LongCat interactive video | no suitable ComfyUI workflow | official scripts only |
| 10 | LongCat-Video | LongCat Avatar multi-audio | new workflow collected | [`talking-avatar-audio-image-to-video`](Generation/LongCat-Video/talking-avatar-audio-image-to-video.json) |
| 17 | SkyReels V1-V2 | SkyReels V1 human-centric | equivalent already exists | HunyuanVideo fine-tune; no dedicated ComfyUI workflow collected by any slice. The checkpoint loads in the HunyuanVideo T2V/I2V graphs: [`hunyuanvideo-13b-txt2video`](Generation/HunyuanVideo/txt2video-13b.json), [`hunyuanvideo-img2video-v2`](Generation/HunyuanVideo/img2video-base-v2.json) |
| 17 | SkyReels V1-V2 | SkyReels V2 I2V 14B 720p | equivalent already exists | Wan 2.1 I2V-architecture checkpoint; loads in [`wan-2.1-14b-img2video-480p`](Generation/Wan-2.1/img2video-14b-480p.json) (checkpoint swap). Not separately collected |
| 17 | SkyReels V1-V2 | SkyReels V2 Diffusion Forcing 14B | new workflow collected | [`long-video-v2-diffusion-forcing-extension`](Generation/SkyReels/long-video-v2-diffusion-forcing-extension.json) (example uses DF 1.3B; 14B is checkpoint swap) |
| 17 | SkyReels V1-V2 | SkyReels V2 Video Extension | new workflow collected | [`long-video-v2-diffusion-forcing-extension`](Generation/SkyReels/long-video-v2-diffusion-forcing-extension.json) |
| 19 | MAGI-1 | MAGI-1 4.5B | new workflow collected | [`long-video-txt2video`](Generation/MAGI-1/long-video-txt2video.json), magi-1-image-to-video.json, magi-1-video-continuation.json |
| 19 | MAGI-1 | MAGI-1 4.5B distilled | equivalent already exists | checkpoint variant of the MAGI-1 graphs |
| 19 | MAGI-1 | MAGI-1 4.5B FP8 | equivalent already exists | quantisation variant of the MAGI-1 graphs |
| 19 | MAGI-1 | MAGI-1 24B | equivalent already exists | checkpoint variant of the MAGI-1 graphs |
| 19 | MAGI-1 | MAGI-1 24B distilled | equivalent already exists | checkpoint variant of the MAGI-1 graphs |
| 19 | MAGI-1 | MAGI-1.1 24B distilled | equivalent already exists | checkpoint variant of the MAGI-1 graphs |
| 25 | FramePack | FramePack Base | new workflow collected | [`long-video-hunyuan-img2video`](Generation/FramePack/long-video-hunyuan-img2video.json) |
| 25 | FramePack | FramePack F1 | equivalent already exists | checkpoint swap in same FramePackWrapper graph |
| 25 | FramePack | FramePack P1 research update | availability or redistribution unconfirmed | no released weights/workflow found |
| 29 | SEINE / LaVie | SEINE generative transitions | no suitable ComfyUI workflow | no maintained node |
| 29 | SEINE / LaVie | LaVie text to video | no suitable ComfyUI workflow | no maintained node |
| 89 | Helios | Helios Base 14B | no suitable ComfyUI workflow | Diffusers/SGLang/vLLM-Omni only |
| 89 | Helios | Helios Mid 14B | no suitable ComfyUI workflow | Diffusers/SGLang/vLLM-Omni only |
| 89 | Helios | Helios Distilled 14B | no suitable ComfyUI workflow | Diffusers/SGLang/vLLM-Omni only |

## Audio-Video Generation (18)

| # | Family | Entry | Disposition | Workflow or reason |
|---|---|---|---|---|
| 6 | LTX 2.x | LTX-2.0 Dev | already present | [`ltx-2-img2video-with-audio`](Generation/LTX-2/img2video-audio.json) (+ custom-audio); T2V template skipped as same task as LTX-2.5 T2V / [`ltx-2-lip-sync-to-your-audio-r01-sc007-0037`](Editing/LTX-2/lip-sync-own-audio.json) (audio-driven); T2V/I2V with audio belongs to other slices |
| 6 | LTX 2.x | LTX-2.0 Distilled | already present | [`ltx-2-img2video-with-audio`](Generation/LTX-2/img2video-audio.json) (distilled fp8) / [`ltx-2-video2video-voice-dubbing`](Editing/LTX-2/voice-dubbing.json); Image-to-Video/ltx-2-img2video-with-custom-audio.json |
| 6 | LTX 2.x | LTX-2.3 Dev | new workflow collected | [`ltx-2.3-id-lora-talking-video-with-reference-voice`](Generation/LTX-2/talking-avatar-v23-id-lora-reference-voice.json) (ID-LoRA reference-voice talking video) |
| 6 | LTX 2.x | LTX-2.3 Distilled | equivalent already exists | as LTX-2.3 Dev / IA2V template and DubIt IC-LoRA (Lightricks) duplicate existing LTX-2 A2V/dubbing files; Lightricks JSONs need full LTX licence copy -> linked in README |
| 6 | LTX 2.x | LTX-2.5 Dev 22B | new workflow collected | [`ltx-2.5-txt2video-with-audio`](Generation/LTX-2/txt2video-v25-audio.json); [`ltx-2.5-img2video-first-last-frame-with-audio`](Generation/LTX-2/img2video-v25-first-last-frame-audio.json); [`ltx-2.5-dfr-img2video-detailing-keyframes-temporal-x2`](Generation/LTX-2/img2video-v25-dfr-detailing-keyframes-temporal-x2.json) |
| 6 | LTX 2.x | LTX-2.5 Distilled 22B | already present | [`ltx-2.5-img2video-with-audio-distilled-2x-upscale`](Generation/LTX-2/img2video-v25-distilled-audio-2x-upscale.json) / Image-to-Video/ltx-2.5-img2video-with-audio-distilled-2x-upscale.json (other slice) |
| 7 | MiniMax H3 | MiniMax H3 33B | already present | `Generation/MiniMax-H3/txt2video*.json`, `Generation/MiniMax-H3/img2video*.json`, `Generation/MiniMax-H3/talking-avatar-*.json` (audio sync, reference sing/speak and timelines) |
| 7 | MiniMax H3 | MiniMax FastH3 | already present | [`minimax-fasth3-txt2video-8-step`](Generation/MiniMax-H3/txt2video-fasth3-8-step.json), `Generation/MiniMax-H3/img2video-fasth3-first-*.json` |
| 7 | MiniMax H3 | MiniMax H3 reference conditioning | useful variation added | [`ref2video-multiframe-keyframe-guides`](Generation/MiniMax-H3/ref2video-multiframe-keyframe-guides.json) (existing: minimax-h3-reference-to-video-2/3-images) |
| 7 | MiniMax H3 | MiniMax H3 Turbo LoRA (community) | already present | [`minimax-h3-txt2video-8-step-lora`](Generation/MiniMax-H3/txt2video-8-step-lora.json), *-speed-lora.json / speed-lora variants in 02-Video/Reference-and-Audio-Sync and Character-Animation-Video-to-Video |
| 12 | Kandinsky Video 6 | Kandinsky 6 Lite 3B | equivalent already exists | Lite loads in the Kandinsky 6 example graphs (model selector) |
| 12 | Kandinsky Video 6 | Kandinsky 6 Lite Distilled 3B | equivalent already exists | Lite Distilled loads in the Kandinsky 6 example graphs |
| 12 | Kandinsky Video 6 | Kandinsky 6 Pro 29B | equivalent already exists | Pro (non-distilled) loads in the Kandinsky 6 example graphs |
| 12 | Kandinsky Video 6 | Kandinsky 6 Pro Distilled 29B | new workflow collected | [`kandinsky-6-pro-distill-txt2video-with-audio`](Generation/Kandinsky/txt2video-v6-pro-distill-audio.json); [`kandinsky-6-pro-distill-img2video-with-audio`](Generation/Kandinsky/img2video-v6-pro-distill-audio.json) |
| 12 | Kandinsky Video 6 | Kandinsky 6 Video Super-Resolution | new workflow collected | Video SR stage included in both Kandinsky 6 workflows (kandinsky6-sr nodes) |
| 18 | SkyReels V3 | SkyReels V3 Reference-to-Video 14B | no suitable ComfyUI workflow | no first-party/maintained JSON found for the R2V checkpoint (left for other slices to recheck) |
| 18 | SkyReels V3 | SkyReels V3 Video Extension 14B | no suitable ComfyUI workflow | No dedicated ComfyUI video-extension workflow was collected by any slice; the closest library path is the SkyReels V2 diffusion-forcing extension [`long-video-v2-diffusion-forcing-extension`](Generation/SkyReels/long-video-v2-diffusion-forcing-extension.json). Remaining gap: not separately searched at integration |
| 18 | SkyReels V3 | SkyReels V3 Talking Avatar 19B | new workflow collected | [`skyreels-v3-talking-avatar-audio-to-video`](Generation/SkyReels/talking-avatar-v3.json) |

## Talking Avatar / Lip-Sync (29)

| # | Family | Entry | Disposition | Workflow or reason |
|---|---|---|---|---|
| 33 | InfiniteTalk | InfiniteTalk I2V audio-driven | already present | `Generation/Wan-2.1/talking-avatar-infinitetalk-*.json`; added multi-speaker variant [`wan-2.1-infinitetalk-two-speaker-conversation`](Generation/Wan-2.1/talking-avatar-infinitetalk-two-speaker.json) |
| 33 | InfiniteTalk | InfiniteTalk V2V video dubbing | already present | `Editing/Wan-2.1/lip-sync-infinitetalk-dubbing-v2v*.json` |
| 33 | InfiniteTalk | InfiniteTalk unlimited-chunk extension | already present | `Generation/Wan-2.1/talking-avatar-infinitetalk-extend-3-34s-*.json` |
| 34 | MultiTalk | MultiTalk multi-person dialogue | equivalent already exists | [`wan-2.1-infinitetalk-two-speaker-conversation`](Generation/Wan-2.1/talking-avatar-infinitetalk-two-speaker.json) (InfiniteTalk multi supersedes MultiTalk in maintained nodes) |
| 34 | MultiTalk | MultiTalk single speaker singing | equivalent already exists | InfiniteTalk/H3 singing files in 02-Video/Reference-and-Audio-Sync |
| 35 | LivePortrait | LivePortrait portrait retargeting | new workflow collected | [`liveportrait-video-to-video-expression-retarget`](Editing/LivePortrait/expression-retarget-video.json) |
| 35 | LivePortrait | LivePortrait video-driven animation | new workflow collected | [`liveportrait-animate-image-from-driving-video`](Generation/LivePortrait/portrait-animation-from-driving-video.json) |
| 35 | LivePortrait | LivePortrait animals / community branch | no suitable ComfyUI workflow | no separate ComfyUI workflow |
| 36 | SadTalker | SadTalker 256 | no suitable ComfyUI workflow | only unlicensed community node repos, no example JSON |
| 36 | SadTalker | SadTalker 512 beta | no suitable ComfyUI workflow | same as SadTalker 256 |
| 37 | Wav2Lip | Wav2Lip original | new workflow collected | [`wav2lip-lip-sync-video-with-face-restore`](Editing/Wav2Lip/lip-sync-face-restore.json) (weights non-commercial) |
| 37 | Wav2Lip | Wav2Lip GAN | equivalent already exists | checkpoint choice inside the same Wav2Lip workflow |
| 38 | LatentSync | LatentSync 1.0 | already present | [`dubsync-latentsync-lip-sync-single-shot`](Editing/DubSync/lip-sync-latentsync-single-shot.json) |
| 38 | LatentSync | LatentSync 1.5 | already present | `Editing/DubSync/lip-sync-latentsync-*.json`, latentsync-hindi-dubbing.json |
| 38 | LatentSync | LatentSync video dubbing workflow | already present | `Editing/DubSync/lip-sync-*.json` (7 files) |
| 39 | MuseTalk | MuseTalk 1.0 | new workflow collected | [`musetalk-lip-sync-video`](Editing/MuseTalk/lip-sync.json) |
| 39 | MuseTalk | MuseTalk 1.5 | equivalent already exists | same node/graph as MuseTalk 1.0 file; checkpoint swap only |
| 40 | Hallo | Hallo 1 | new workflow collected | [`hallo-audio-driven-portrait`](Generation/Hallo/talking-avatar-v1-portrait.json) |
| 40 | Hallo | Hallo 2 | new workflow collected | [`hallo2-long-portrait-animation-with-upscale`](Generation/Hallo/talking-avatar-v2-long-portrait-upscale.json) |
| 41 | EchoMimic | EchoMimic V1 | new workflow collected | [`echomimic-v1-audio-driven-portrait`](Generation/EchoMimic/talking-avatar-v1-portrait.json) |
| 41 | EchoMimic | EchoMimic V2 | new workflow collected | [`echomimic-v2-half-body-audio-and-pose`](Generation/EchoMimic/talking-avatar-v2-half-body-pose.json) |
| 41 | EchoMimic | EchoMimic V2 Accelerated | equivalent already exists | accelerated checkpoint of V2 / V3 flash variants; not a new capability |
| 41 | EchoMimic | EchoMimic V3 1.3B | new workflow collected | [`echomimic-v3-audio-driven-avatar`](Generation/EchoMimic/talking-avatar-v3.json) |
| 42 | Hunyuan Portrait | HunyuanPortrait image-audio animation | no suitable ComfyUI workflow | community nodes have no example JSON |
| 49 | OmniAvatar | OmniAvatar audio to full-body video | no suitable ComfyUI workflow | one small unlicensed repo, no example JSON |
| 50 | Sonic | Sonic audio-driven portrait | new workflow collected | [`talking-avatar-audio-driven-portrait`](Generation/Sonic/talking-avatar-audio-driven-portrait.json) (weights non-commercial, verify) |
| 51 | VideoReTalking | VideoReTalking lip-sync repair | no suitable ComfyUI workflow | no ComfyUI node or workflow found |
| 92 | Kandinsky S2V | Kandinsky S2V Lite Distill | new workflow collected | [`kandinsky-s2v-lite-distilled-speech-to-video`](Generation/Kandinsky/talking-avatar-s2v-lite-distilled.json) |
| 92 | Kandinsky S2V | Kandinsky S2V Pro Distill | equivalent already exists | same graph as Lite with larger checkpoint (official Pro JSON linked) |

## Video Editing / Control (29)

| # | Family | Entry | Disposition | Workflow or reason |
|---|---|---|---|---|
| 31 | VACE | VACE Wan2.1 1.3B Preview | equivalent already exists | same tasks as VACE 14B workflows (1.3B selectable in loaders) |
| 31 | VACE | VACE Wan2.1 14B | new workflow collected | [`wan-2.1-vace-14b-reference-to-video`](Generation/Wan-2.1/ref2video-vace-14b.json); [`wan-2.1-vace-14b-control-video-to-video`](Editing/Wan-2.1/v2v-vace-14b-control.json); [`wan-2.1-vace-14b-video-outpainting`](Editing/Wan-2.1/outpaint-vace-14b.json) |
| 31 | VACE | VACE LTX 0.9 | no suitable ComfyUI workflow | no VACE LTX release/graph found |
| 31 | VACE | VACE masked video-to-video | new workflow collected | [`wan-2.1-vace-14b-video-inpainting`](Editing/Wan-2.1/inpaint-vace-14b.json) |
| 32 | SkyReels A-series | SkyReels-A1 portrait animation | no suitable ComfyUI workflow | ComfyUI is TODO in official repo / no maintained ComfyUI workflow found |
| 32 | SkyReels A-series | SkyReels-A2 element assembly | new workflow collected | [`ref2video-a2-element-assembly`](Generation/SkyReels/ref2video-a2-element-assembly.json) / [`ref2video-a2-element-assembly`](Generation/SkyReels/ref2video-a2-element-assembly.json) |
| 52 | Rerender A Video | Rerender A Video keyframe edit | no suitable ComfyUI workflow | research code only |
| 52 | Rerender A Video | Rerender A Video LoRA+ControlNet | no suitable ComfyUI workflow | research code only |
| 53 | TokenFlow | TokenFlow zero-shot V2V | no suitable ComfyUI workflow | research code only |
| 54 | FateZero | FateZero cross-attention edit | no suitable ComfyUI workflow | research code only |
| 55 | Tune-A-Video | Tune-A-Video one-shot tuning | no suitable ComfyUI workflow | research code only |
| 56 | Vid2Vid-Zero | Vid2Vid-Zero video editing | no suitable ComfyUI workflow | research code only |
| 57 | AnyV2V | AnyV2V video editing | no suitable ComfyUI workflow | research code only |
| 58 | PnP Video | PnP Video (discovery lead) | no suitable ComfyUI workflow | discovery lead; no ComfyUI node/graph |
| 59 | Video-P2P | Video-P2P prompt editing | no suitable ComfyUI workflow | research code only |
| 60 | LOVECon | LOVECon stylization | no suitable ComfyUI workflow | research code only |
| 61 | VideoSwap | VideoSwap semantic swap | no suitable ComfyUI workflow | research code only |
| 62 | ControlVideo | ControlVideo spatial control | no suitable ComfyUI workflow | research code only |
| 63 | FRESCO | FRESCO feature correspondence | no suitable ComfyUI workflow | research code only |
| 64 | VideoPainter | VideoPainter video inpainting | no suitable ComfyUI workflow | official repo has no ComfyUI integration |
| 65 | ProPainter | ProPainter video object removal | new workflow collected | [`object-removal`](Editing/ProPainter/object-removal.json) (NTU S-Lab non-commercial) |
| 65 | ProPainter | ProPainter video completion | equivalent already exists | same ProPainterInpaint graph as object removal workflow |
| 66 | E2FGVI | E2FGVI 432x240 | no suitable ComfyUI workflow | no maintained ComfyUI graph |
| 66 | E2FGVI | E2FGVI-HQ arbitrary resolution | no suitable ComfyUI workflow | no maintained ComfyUI graph |
| 67 | STTN / FuseFormer | STTN video inpainting | no suitable ComfyUI workflow | no ComfyUI support found |
| 67 | STTN / FuseFormer | FuseFormer video inpainting | no suitable ComfyUI workflow | no ComfyUI support found |
| 88 | Phantom-Wan | Phantom-Wan-1.3B | equivalent already exists | selectable in the Phantom 14B workflow loader |
| 88 | Phantom-Wan | Phantom-Wan-14B | new workflow collected | [`wan-2.1-phantom-14b-multi-subject-to-video`](Generation/Wan-2.1/ref2video-phantom-14b-multi-subject.json) |
| 88 | Phantom-Wan | Phantom-Wan-14B Pro | equivalent already exists | checkpoint swap in the same Phantom graph |

## Character Animation (13)

| # | Family | Entry | Disposition | Workflow or reason |
|---|---|---|---|---|
| 3 | Wan Animate 2 | Wan-Animate-2 Base 14B | new workflow collected | [`wan-animate-2-motion-transfer-from-driving-video`](Editing/Wan-Animate-2/motion-transfer.json) |
| 3 | Wan Animate 2 | Wan-Animate-2 Distilled 14B | equivalent already exists | distilled checkpoint of the Base workflow (template video_wan_animate2_distilled linked in README) |
| 3 | Wan Animate 2 | Wan-Animate-2 Lite research variant | no suitable ComfyUI workflow | no released weights or graph |
| 4 | Wan Dancer | Wan-Dancer 14B | no suitable ComfyUI workflow | official repo has no ComfyUI integration; SteadyDancer added as dance alternative |
| 43 | MagicAnimate | MagicAnimate pose-driven character | no suitable ComfyUI workflow | node pack exists but publishes no workflow JSON |
| 44 | MimicMotion | MimicMotion pose-driven | new workflow collected | [`mimicmotion-pose-guided-human-animation`](Editing/MimicMotion/motion-transfer-pose-guided.json) (custom Tencent weight licence) |
| 45 | UniAnimate | UniAnimate pose animation | availability or redistribution unconfirmed | Isi-dev/ComfyUI-UniAnimate-W workflows exist but repo has no licence; linked only |
| 46 | Champ | Champ 3D pose guided animation | new workflow collected | [`champ-3d-pose-guided-human-animation`](Editing/Champ/motion-transfer-3d-pose-guided.json) |
| 47 | MusePose | MusePose human pose driving | new workflow collected | [`musepose-pose-driven-dance-video`](Editing/MusePose/motion-transfer-pose-driven-dance.json) |
| 48 | Animate Anyone | Animate Anyone reference motion | new workflow collected | [`motion-transfer-evolved-pose-to-video`](Editing/Animate-Anyone/motion-transfer-evolved-pose-to-video.json) (Moore-AnimateAnyone community reproduction; official weights unavailable) |
| 87 | SCAIL-2 | SCAIL-2 base in-context animation | already present | `Editing/Wan-2.1/motion-transfer-scail-2-driving-video-*.json` |
| 87 | SCAIL-2 | SCAIL-2 multi-reference animation | already present | [`wan-2.1-scail-2-gap-multi-character-long`](Editing/Wan-2.1/motion-transfer-scail-2-gap-multi-character-long.json) and gap-* files |
| 87 | SCAIL-2 | SCAIL-2 replacement relighting LoRA | already present | [`wan-2.1-scail-2-character-replacement`](Editing/Wan-2.1/character-swap-scail-2.json) (identical to official template) |

## Video Enhancement (22)

| # | Family | Entry | Disposition | Workflow or reason |
|---|---|---|---|---|
| 68 | SeedVR / SeedVR2 | SeedVR 3B | no suitable ComfyUI workflow | v1 superseded by SeedVR2 in ComfyUI |
| 68 | SeedVR / SeedVR2 | SeedVR 7B | no suitable ComfyUI workflow | v1 superseded by SeedVR2 in ComfyUI |
| 68 | SeedVR / SeedVR2 | SeedVR2 video restore | already present | [`seedvr2-video-upscale`](Enhancement/SeedVR2/upscale.json) (+9 other SeedVR2 files); template utility_seedvr2_video_upscale skipped = duplicate of api.json |
| 68 | SeedVR / SeedVR2 | SeedVR2 fast / tiled workflow | useful variation added | [`seedvr2-native-core-nodes-temporal-chunk-video-upscale`](Enhancement/SeedVR2/upscale-native-temporal-chunk.json) (core nodes, temporal chunk, tiled VAE) |
| 69 | VRT / RVRT | VRT video super-resolution | no suitable ComfyUI workflow | no maintained node |
| 69 | VRT / RVRT | VRT video deblurring | no suitable ComfyUI workflow | no maintained node |
| 69 | VRT / RVRT | VRT video denoising | no suitable ComfyUI workflow | no maintained node |
| 69 | VRT / RVRT | VRT video interpolation | no suitable ComfyUI workflow | no maintained node |
| 69 | VRT / RVRT | RVRT recurrent restoration | no suitable ComfyUI workflow | no maintained node |
| 70 | BasicVSR family | BasicVSR video super-resolution | no suitable ComfyUI workflow | MMCV-based, no maintained node |
| 70 | BasicVSR family | IconVSR | no suitable ComfyUI workflow | no maintained node |
| 70 | BasicVSR family | BasicVSR++ | no suitable ComfyUI workflow | no maintained node |
| 70 | BasicVSR family | RealBasicVSR | no suitable ComfyUI workflow | no maintained node |
| 74 | EDVR | EDVR video SR | no suitable ComfyUI workflow | no maintained node |
| 74 | EDVR | EDVR deblurring | no suitable ComfyUI workflow | no maintained node |
| 75 | TecoGAN | TecoGAN video upscaling | no suitable ComfyUI workflow | no node |
| 76 | RVRT | RVRT super-resolution | no suitable ComfyUI workflow | no maintained node |
| 76 | RVRT | RVRT deblur | no suitable ComfyUI workflow | no maintained node |
| 76 | RVRT | RVRT denoise | no suitable ComfyUI workflow | no maintained node |
| 77 | VEnhancer | VEnhancer spatial upscale | no suitable ComfyUI workflow | no maintained node |
| 77 | VEnhancer | VEnhancer temporal refine | no suitable ComfyUI workflow | no maintained node |
| 78 | Upscale-A-Video | Upscale-A-Video 4x | no suitable ComfyUI workflow | no maintained node |

## Frame Interpolation (9)

| # | Family | Entry | Disposition | Workflow or reason |
|---|---|---|---|---|
| 71 | RIFE | RIFE 4.22 lite | availability or redistribution unconfirmed | node RIFE VFI in Fannovel16/ComfyUI-Frame-Interpolation; only third-party JSON (OpenShot template wrapper, unclear licence) found; use [`frame-interpolation-vfi-node-pack`](Enhancement/FILM/frame-interpolation-vfi-node-pack.json) and swap node |
| 71 | RIFE | RIFE 4.7 | availability or redistribution unconfirmed | same as above |
| 71 | RIFE | RIFE 4.10 | availability or redistribution unconfirmed | same as above |
| 71 | RIFE | RIFE arbitrary timestep | availability or redistribution unconfirmed | same as above |
| 72 | FILM | FILM frame interpolation | new workflow collected | [`frame-interpolation-core-nodes`](Enhancement/FILM/frame-interpolation-core-nodes.json); [`frame-interpolation-vfi-node-pack`](Enhancement/FILM/frame-interpolation-vfi-node-pack.json) |
| 73 | DAIN | DAIN depth-aware interpolation | no suitable ComfyUI workflow | legacy CUDA, no node |
| 79 | IFRNet | IFRNet interpolation | no suitable ComfyUI workflow | node exists in ComfyUI-Frame-Interpolation, no published workflow |
| 80 | AMT | AMT intermediate frame generation | no suitable ComfyUI workflow | node exists in ComfyUI-Frame-Interpolation, no published workflow |
| 81 | GMFSS | GMFSS Fortuna interpolation | no suitable ComfyUI workflow | node exists in ComfyUI-Frame-Interpolation, no published workflow |

## Supporting Vision (13)

| # | Family | Entry | Disposition | Workflow or reason |
|---|---|---|---|---|
| 82 | Video Depth Anything | Video Depth Anything Small | new workflow collected | [`depth-map-video`](Editing/Video-Depth-Anything/depth-map-video.json) (model selector) |
| 82 | Video Depth Anything | Video Depth Anything Base | equivalent already exists | checkpoint swap in same graph |
| 82 | Video Depth Anything | Video Depth Anything Large | new workflow collected | [`depth-map-video`](Editing/Video-Depth-Anything/depth-map-video.json) (default vitl; CC-BY-NC-4.0) |
| 82 | Video Depth Anything | Video Depth Anything Metric Small | equivalent already exists | checkpoint swap in same graph |
| 82 | Video Depth Anything | Video Depth Anything Metric Large | equivalent already exists | checkpoint swap in same graph |
| 83 | SAM 2 / SAM 3 | SAM2 video segmentation | new workflow collected | [`segment-points-video`](Editing/SAM-2/segment-points-video.json); SAM3 video: [`segment-text-prompt-video`](Editing/SAM-3/segment-text-prompt-video.json) |
| 83 | SAM 2 / SAM 3 | SAM2 memory tracking | new workflow collected | [`segment-points-video`](Editing/SAM-2/segment-points-video.json) (propagation across frames) |
| 84 | CoTracker | CoTracker2 | availability or redistribution unconfirmed | s9roll7/comfyui_cotracker_node has no licence; only personal-project JSON (CreativeInquiry/ComfyCV) found |
| 84 | CoTracker | CoTracker3 | availability or redistribution unconfirmed | same as above |
| 85 | XMem / DeAOT | XMem long-term video masks | no suitable ComfyUI workflow | no maintained node |
| 85 | XMem / DeAOT | DeAOT object tracking masks | no suitable ComfyUI workflow | no maintained node |
| 86 | RAFT / GMFlow | RAFT optical flow | no suitable ComfyUI workflow | internal to other packs only |
| 86 | RAFT / GMFlow | GMFlow optical flow | no suitable ComfyUI workflow | no node |

## Experimental Research (13)

| # | Family | Entry | Disposition | Workflow or reason |
|---|---|---|---|---|
| 30 | Latte | Latte T2V | no suitable ComfyUI workflow | Diffusers only |
| 30 | Latte | Latte-1 T2V | no suitable ComfyUI workflow | Diffusers only |
| 30 | Latte | Latte I2I training baseline | no suitable ComfyUI workflow | training baseline, not a generation workflow |
| 90 | Cosmos 3 | Cosmos3 Edge 4B | no suitable ComfyUI workflow | no ComfyUI template |
| 90 | Cosmos 3 | Cosmos3 Nano 16B | no suitable ComfyUI workflow | no ComfyUI template |
| 90 | Cosmos 3 | Cosmos3 Super 64B | no suitable ComfyUI workflow | no ComfyUI template |
| 91 | Cosmos Predict2.5 | Cosmos Predict2.5 2B pre-trained | no suitable ComfyUI workflow | Predict2.5 has no ComfyUI integration; nearest: [`cosmos-predict2-2b-video2world-img2video`](Generation/Cosmos/video2world-predict2-2b.json) (Predict2) |
| 91 | Cosmos Predict2.5 | Cosmos Predict2.5 2B post-trained | no suitable ComfyUI workflow | Predict2.5 has no ComfyUI integration; nearest: [`cosmos-predict2-2b-video2world-img2video`](Generation/Cosmos/video2world-predict2-2b.json) (Predict2) |
| 91 | Cosmos Predict2.5 | Cosmos Predict2.5 2B distilled | no suitable ComfyUI workflow | Predict2.5 has no ComfyUI integration; nearest: [`cosmos-predict2-2b-video2world-img2video`](Generation/Cosmos/video2world-predict2-2b.json) (Predict2) |
| 91 | Cosmos Predict2.5 | Cosmos Predict2.5 14B pre-trained | no suitable ComfyUI workflow | Predict2.5 has no ComfyUI integration; nearest: [`cosmos-predict2-2b-video2world-img2video`](Generation/Cosmos/video2world-predict2-2b.json) (Predict2) |
| 91 | Cosmos Predict2.5 | Cosmos Predict2.5 14B post-trained | no suitable ComfyUI workflow | Predict2.5 has no ComfyUI integration; nearest: [`cosmos-predict2-2b-video2world-img2video`](Generation/Cosmos/video2world-predict2-2b.json) (Predict2) |
| 91 | Cosmos Predict2.5 | Cosmos Predict2.5 auto multi-view | no suitable ComfyUI workflow | Predict2.5 has no ComfyUI integration; nearest: [`cosmos-predict2-2b-video2world-img2video`](Generation/Cosmos/video2world-predict2-2b.json) (Predict2) |
| 91 | Cosmos Predict2.5 | Cosmos Predict2.5 robot action-conditioned | no suitable ComfyUI workflow | Predict2.5 has no ComfyUI integration; nearest: [`cosmos-predict2-2b-video2world-img2video`](Generation/Cosmos/video2world-predict2-2b.json) (Predict2) |

## Additions outside the atlas entries

Workflows the slices added for models or tasks that are not a separate atlas entry (counted in the workflow total, not in the table above).

| Model / task | Disposition | Workflow |
|---|---|---|
| Audio-reactive AnimateDiff T2V | new workflow collected | [`audio-reactive-txt2video`](Generation/AnimateDiff/audio-reactive-txt2video.json) |
| Audio-reactive AnimateDiff V2V | new workflow collected | [`audio-reactive-v2v`](Editing/AnimateDiff/audio-reactive-v2v.json) |
| Audio-reactive AnimateDiff images-to-video | new workflow collected | [`audio-reactive-images-to-video`](Generation/AnimateDiff/audio-reactive-images-to-video.json) |
| Audio-reactive LivePortrait expressions | new workflow collected | [`audio-reactive-expressions`](Generation/LivePortrait/audio-reactive-expressions.json) |
| Audio-reactive Wan VACE pose | new workflow collected | [`wan-2.1-vace-audio-reactive-pose-animation`](Generation/Wan-2.1/audio-reactive-vace-pose-animation.json) |
| Bernini-R | useful variation added | [`wan-2.2-bernini-r-video-relighting`](Editing/Wan-2.2/relight-bernini-r.json) |
| Capybara v0.1 | useful variation added | [`capybara-v0.1-instruction-video-edit`](Editing/Capybara/edit-v01-instruction.json) |
| Capybara v0.1 (not a PDF entry; HunyuanVideo 1.5 base) | new workflow collected | [`capybara-v0.1-img2video`](Generation/Capybara/img2video-v01.json) |
| Causal Forcing (not a PDF entry; Wan 2.1 base) | new workflow collected | [`causal-forcing-wan-2.1-img2video-realtime-4-step`](Generation/Wan-2.1/img2video-causal-forcing-realtime-4-step.json) |
| Cosmos 1 (not a PDF entry) | new workflow collected | [`cosmos-1-7b-video2world-img2video`](Generation/Cosmos/video2world-v1-7b.json) |
| Cosmos 1 (not a PDF entry; Cosmos family) | new workflow collected | [`cosmos-1-7b-text2world-txt2video`](Generation/Cosmos/txt2video-v1-7b-text2world.json) |
| Cosmos-Predict2 (nearest to Predict2.5) | new workflow collected | [`cosmos-predict2-2b-video2world-img2video`](Generation/Cosmos/video2world-predict2-2b.json) |
| DWPose video | new workflow collected | [`pose-keypoints-video`](Editing/DWPose/pose-keypoints-video.json) |
| Depth Anything 3 video | new workflow collected | [`depth-map-v3-video`](Editing/Depth-Anything/depth-map-v3-video.json) |
| Depth Anything V2 video | new workflow collected | [`depth-map-v2-video`](Editing/Depth-Anything/depth-map-v2-video.json) |
| FantasyPortrait | new workflow collected | [`wan-2.1-fantasyportrait-expression-transfer-from-video`](Editing/Wan-2.1/expression-transfer-fantasyportrait.json) |
| FantasyTalking | new workflow collected | [`wan-2.1-fantasytalking-audio-driven-portrait`](Generation/Wan-2.1/talking-avatar-fantasytalking-portrait.json) |
| FlashVSR | new workflow collected | [`flashvsr-wan-1.3b-video-upscale`](Enhancement/FlashVSR/upscale-wan-13b.json) |
| GIMM-VFI | new workflow collected | [`frame-interpolation`](Enhancement/GIMM-VFI/frame-interpolation.json) |
| HuMo | new workflow collected | [`wan-2.1-humo-image-audio-reference-to-video`](Generation/Wan-2.1/talking-avatar-humo-image-audio-reference.json) |
| LTX-2.3 Obscura Remova LoRA | useful variation added | [`ltx-2.3-obscura-lora-prompt-object-removal`](Editing/LTX-2/object-removal-v23-obscura-lora.json) |
| LTX-2.3 subtitle removal LoRA | useful variation added | [`ltx-2.3-lora-remove-subtitles-from-video`](Editing/LTX-2/object-removal-v23-lora-subtitles.json) |
| Line art video | new workflow collected | [`lineart-extraction-video`](Editing/Other/lineart-extraction-video.json) |
| NVIDIA RTX Video SR / frame gen / HDR | new workflow collected | [`nvidia-rtx-video-super-resolution-frame-gen-hdr`](Enhancement/NVIDIA-RTX-VSR/upscale-frame-gen-hdr.json) |
| NormalCrafter video | new workflow collected | [`normal-map-video`](Editing/NormalCrafter/normal-map-video.json) |
| ReCamMaster | useful variation added | [`wan-2.1-recammaster-1.3b-camera-rerender-video`](Editing/Wan-2.1/camera-rerender-recammaster-13b.json) |
| RelayVSR | new workflow collected | [`upscale-4x`](Enhancement/RelayVSR/upscale-4x.json) (x2 template skipped: scale variant) |
| SDPose multi-person video | new workflow collected | [`pose-keypoints-multi-person-video`](Editing/SDPose/pose-keypoints-multi-person-video.json) (OOD single-pose template skipped as near-equivalent) |
| Stand-In | useful variation added | [`wan-2.1-stand-in-identity-reference-to-video`](Generation/Wan-2.1/ref2video-stand-in-identity.json) |
| SteadyDancer | useful variation added | [`wan-2.1-steadydancer-first-frame-dance-animation`](Editing/Wan-2.1/motion-transfer-steadydancer-first-frame-dance.json) |
| VOID | useful variation added | [`object-and-interaction-removal`](Editing/VOID/object-and-interaction-removal.json) |
| Wan 2.2 Pusa video extension | new workflow collected | [`wan-2.2-pusa-video-extension`](Generation/Wan-2.2/long-video-pusa-extension.json) |
| Wan 2.2 generative video upscale | new workflow collected | [`wan-2.2-video-upscale-refine`](Enhancement/Wan-2.2/upscale-refine.json) |
| Wan-Move 14B | useful variation added | [`motion-control-trajectory-480p`](Editing/Wan-Move/motion-control-trajectory-480p.json) |
| Wan2.2 Fun Control A14B | useful variation added | [`wan-2.2-fun-control-14b-pose-depth-canny`](Editing/Wan-2.2/v2v-fun-control-14b-pose-depth-canny.json) |
| Wan2.2 Fun Control-Camera A14B | useful variation added | [`wan-2.2-fun-camera-control-14b`](Editing/Wan-2.2/camera-control-fun-14b.json) |

## How conflicts were resolved

- **LTX-2.3 Dev** → new workflow collected. conflict resolved: vid-gen said "equivalent already exists" (LTX-2.3 t2v/i2v/flf2v templates = same tasks as LTX-2.5 workflows; checkpoint-only difference)
- **LTX-2.5 Dev 22B** → new workflow collected. conflict resolved: vid-avatar said "equivalent already exists" (LTX-2.5 A2V two-stage (Lightricks, LTX-2 Community License) = same task as existing LTX-2 A2V; linked only; T2V/I2V+audio -> other slices)
- **MiniMax FastH3** → already present. conflict resolved: vid-avatar said "equivalent already exists" (FastH3 OmniRef 8-step r2v template is a faster checkpoint of existing H3 reference-to-video; FastH3 T2V/I2V already in other folders)
- **Kandinsky 6 Video Super-Resolution** → new workflow collected. conflict resolved: vid-long said "no suitable ComfyUI workflow" (no stand-alone ComfyUI SR workflow found)
- **SkyReels V1 human-centric** → equivalent already exists. unassigned in all slices (vid-long deferred to T2V/I2V; vid-gen deferred to long-form); resolved at integration
- **SkyReels V2 I2V 14B 720p** → equivalent already exists. unassigned in all slices (vid-long deferred to I2V; vid-gen deferred to long-form); resolved at integration
- **SkyReels V3 Video Extension 14B** → no suitable ComfyUI workflow. unassigned in all slices (vid-gen deferred to audio-video/long-form workers); resolved at integration

## Duplicates removed at integration

- `Video-Editing-and-Tools/wan-2.1-skyreels-a2-element-assembly-to-video.json` (added in #28) was the same graph from the same source (kijai/ComfyUI-WanVideoWrapper `wanvideo_2_1_14B_skyreels_a2_example_01`) as [`ref2video-a2-element-assembly`](Generation/SkyReels/ref2video-a2-element-assembly.json) (added in #25); the #28 copy was removed. No pre-existing workflow was removed.
