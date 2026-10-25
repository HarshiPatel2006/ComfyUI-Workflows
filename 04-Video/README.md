# AI Video — ComfyUI workflows

Text-to-video (txt2video), image-to-video (img2video), video-to-video, talking video and lip-sync, character animation and character swap, video upscaling and audio-reactive video — Wan 2.1 / 2.2, LTX-2, MiniMax H3, SeedVR2, InfiniteTalk, SCAIL.

| Subfolder | What is inside | Workflows |
|---|---|---|
| [`Audio-Reactive/`](Audio-Reactive) | Audio-reactive visuals | 1 |
| [`Character-Animation-Video-to-Video/`](Character-Animation-Video-to-Video) | Character animation, character replacement, character swap and face swap (video2video) | 37 |
| [`Image-to-Video/`](Image-to-Video) | Image-to-video (img2video), first/last frame | 11 |
| [`Reference-and-Audio-Sync/`](Reference-and-Audio-Sync) | Reference-to-video, talking video, lip-sync and video dubbing | 26 |
| [`Text-to-Video/`](Text-to-Video) | Text-to-video (txt2video) | 5 |
| [`Video-Upscaling/`](Video-Upscaling) | Video upscaling | 10 |

## Workflows (90)

### Audio-reactive visuals

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [utility-images-react-to-music-audio-reactive](Audio-Reactive/utility-images-react-to-music-audio-reactive.json) | Images React to Music (Audio Reactive) | ComfyUI-Pixaroma |

### Character animation, character replacement, character swap and face swap (video2video)

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [minimax-h3-character-swap-motion-guide-check-run08-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-motion-guide-check-run08-api.json) | SAM3 motion-guide preview for the H3 character swap (API format) | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-motion-guide-check-run08-v2-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-motion-guide-check-run08-v2-api.json) | SAM3 motion-guide preview for the H3 character swap (v2) (API format) | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-mdmz-v1](Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-mdmz-v1.json) | Character swap / motion transfer: SAM3 masks the person, MiniMax H3 regenerates the shot with your character (Gemini prompt helper) | ComfyUI-VideoHelperSuite, rgthree-comfy, ComfyUI-Unload-Model |
| [minimax-h3-character-swap-sam3-run01-480p-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run01-480p-api.json) | MiniMax H3 character swap run 01 (480p): SAM3 mask + reference-to-video (API format) | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run02-480p-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run02-480p-api.json) | MiniMax H3 character swap run 02 (480p): SAM3 mask + reference-to-video (API format) | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run03-480p-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run03-480p-api.json) | MiniMax H3 character swap run 03 (480p): SAM3 mask + reference-to-video (API format) | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run04-480p-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run04-480p-api.json) | MiniMax H3 character swap run 04 (480p): SAM3 mask + reference-to-video (API format) | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run05-480p-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run05-480p-api.json) | MiniMax H3 character swap run 05 (480p): SAM3 mask + reference-to-video (API format) | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run05-720p-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run05-720p-api.json) | MiniMax H3 character swap run 05 (720p): SAM3 mask + reference-to-video (API format) | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run06-720p-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run06-720p-api.json) | MiniMax H3 character swap run 06 (720p): SAM3 mask + reference-to-video (API format) | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run07a-dance-720p-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run07a-dance-720p-api.json) | MiniMax H3 character swap run 07A (dance 720p): SAM3 mask + reference-to-video (API format) | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run07b-talk-720p-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run07b-talk-720p-api.json) | MiniMax H3 character swap run 07B (talk 720p): SAM3 mask + reference-to-video (API format) | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run08-duo-720p-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run08-duo-720p-api.json) | MiniMax H3 character swap run 08 (duo 720p): SAM3 mask + reference-to-video (API format) | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run09-toons-720p-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run09-toons-720p-api.json) | MiniMax H3 character swap run 09 (toons 720p): SAM3 mask + reference-to-video (API format) | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run10-faceswap-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run10-faceswap-api.json) | MiniMax H3 character swap run 10 (faceswap): SAM3 mask + reference-to-video (API format) | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run11a-480p-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run11a-480p-api.json) | MiniMax H3 character swap run 11A (480p): SAM3 mask + reference-to-video (API format) | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run11b-480p-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run11b-480p-api.json) | MiniMax H3 character swap run 11B (480p): SAM3 mask + reference-to-video (API format) | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run11c-480p-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run11c-480p-api.json) | MiniMax H3 character swap run 11C (480p): SAM3 mask + reference-to-video (API format) | ComfyUI-VideoHelperSuite |
| [minimax-h3-character-swap-sam3-run11c-720p-api](Character-Animation-Video-to-Video/minimax-h3-character-swap-sam3-run11c-720p-api.json) | MiniMax H3 character swap run 11C (720p): SAM3 mask + reference-to-video (API format) | ComfyUI-VideoHelperSuite |
| [reactor-video-face-swap-api](Character-Animation-Video-to-Video/reactor-video-face-swap-api.json) | Face swap on every frame of a video with ReActor + CodeFormer restore (API format) | ComfyUI-ReActor, ComfyUI-VideoHelperSuite |
| [wan-2.1-scail-2-character-animation-from-driving-video-compact](Character-Animation-Video-to-Video/wan-2.1-scail-2-character-animation-from-driving-video-compact.json) | Character Animation from Driving Video — Compact | ComfyUI-KJNodes, ComfyUI-Pixaroma |
| [wan-2.1-scail-2-character-animation-from-driving-video-long](Character-Animation-Video-to-Video/wan-2.1-scail-2-character-animation-from-driving-video-long.json) | Character Animation from Driving Video — Long | ComfyUI-KJNodes, ComfyUI-Pixaroma |
| [wan-2.1-scail-2-character-replacement](Character-Animation-Video-to-Video/wan-2.1-scail-2-character-replacement.json) | Character Replacement | Core only |
| [wan-2.1-scail-2-gap-hi-woman](Character-Animation-Video-to-Video/wan-2.1-scail-2-gap-hi-woman.json) | GAP — Hi Woman | wan-scail2-gap |
| [wan-2.1-scail-2-gap-multi-character-long](Character-Animation-Video-to-Video/wan-2.1-scail-2-gap-multi-character-long.json) | GAP Multi Character — Long | wan-scail2-gap |
| [wan-2.1-scail-2-gap-video-2](Character-Animation-Video-to-Video/wan-2.1-scail-2-gap-video-2.json) | GAP — Video 2 | wan-scail2-gap |
| [wan-2.1-scail-2-gap-video-3-man](Character-Animation-Video-to-Video/wan-2.1-scail-2-gap-video-3-man.json) | GAP — Video 3 Man | wan-scail2-gap |
| [wan-2.1-scail-2-gap-video-4-man-closeup](Character-Animation-Video-to-Video/wan-2.1-scail-2-gap-video-4-man-closeup.json) | GAP — Video 4 Man Closeup | wan-scail2-gap |
| [wan-2.1-scail-2-gap-video-5-man-head](Character-Animation-Video-to-Video/wan-2.1-scail-2-gap-video-5-man-head.json) | GAP — Video 5 Man Head | wan-scail2-gap |
| [wan-2.1-scail-2-gap-video-6-man-head-fix](Character-Animation-Video-to-Video/wan-2.1-scail-2-gap-video-6-man-head-fix.json) | GAP — Video 6 Man Head Fix | wan-scail2-gap |
| [wan-2.1-scail-img2video-multi-character-9-16-ratio-only](Character-Animation-Video-to-Video/wan-2.1-scail-img2video-multi-character-9-16-ratio-only.json) | Image to Video — Multi Character (9-16 Ratio Only) | comfyui_controlnet_aux, ComfyUI-KJNodes, ComfyUI-SCAIL-Pose, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use |
| [wan-2.1-scail-img2video-single-character](Character-Animation-Video-to-Video/wan-2.1-scail-img2video-single-character.json) | Image to Video — Single Character | ComfyUI-KJNodes, ComfyUI-SCAIL-Pose, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use |
| [wan-2.2-animate-replace-character-and-background-16fps](Character-Animation-Video-to-Video/wan-2.2-animate-replace-character-and-background-16fps.json) | Replace Character and Background — 16FPS | ComfyUI_LayerStyle, ComfyUI-KJNodes, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Sam3, ComfyUI-Easy-Use |
| [wan-2.2-animate-replace-character-and-background-24fps-hd](Character-Animation-Video-to-Video/wan-2.2-animate-replace-character-and-background-24fps-hd.json) | Replace Character and Background — 24FPS HD | ComfyUI_LayerStyle, ComfyUI-KJNodes, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Sam3, ComfyUI-Easy-Use |
| [wan-2.2-animate-replace-character-and-background-24fps](Character-Animation-Video-to-Video/wan-2.2-animate-replace-character-and-background-24fps.json) | Replace Character and Background — 24FPS | ComfyUI_LayerStyle, ComfyUI-KJNodes, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Sam3, ComfyUI-Easy-Use |
| [wan-2.2-animate-replace-only-character-16fps](Character-Animation-Video-to-Video/wan-2.2-animate-replace-only-character-16fps.json) | Replace Only Character — 16FPS | ComfyUI_LayerStyle, ComfyUI-KJNodes, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Sam3, ComfyUI-Easy-Use |
| [wan-2.2-animate-replace-only-character-24fps](Character-Animation-Video-to-Video/wan-2.2-animate-replace-only-character-24fps.json) | Replace Only Character — 24FPS | ComfyUI_LayerStyle, ComfyUI-KJNodes, ComfyUI-WanAnimatePreprocess, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Sam3, ComfyUI-Easy-Use |

### Image-to-video (img2video), first/last frame

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [ltx-2-img2video-with-audio](Image-to-Video/ltx-2-img2video-with-audio.json) | Image to Video with Audio | ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use |
| [ltx-2-img2video-with-custom-audio](Image-to-Video/ltx-2-img2video-with-custom-audio.json) | Image to Video with Custom Audio | ComfyUI_LayerStyle, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use |
| [minimax-fasth3-img2video-first-frame-8-step](Image-to-Video/minimax-fasth3-img2video-first-frame-8-step.json) | Image to Video — First Frame (8-Step) | ComfyUI-Pixaroma |
| [minimax-fasth3-img2video-first-last-frame-8-step](Image-to-Video/minimax-fasth3-img2video-first-last-frame-8-step.json) | Image to Video — First + Last Frame (8-Step) | ComfyUI-Pixaroma |
| [minimax-h3-img2video-first-frame-speed-lora](Image-to-Video/minimax-h3-img2video-first-frame-speed-lora.json) | Image to Video — First Frame + Speed LoRA | ComfyUI-Pixaroma |
| [minimax-h3-img2video-first-frame](Image-to-Video/minimax-h3-img2video-first-frame.json) | Image to Video — First Frame | ComfyUI-Pixaroma |
| [minimax-h3-img2video-first-last-frame-speed-lora](Image-to-Video/minimax-h3-img2video-first-last-frame-speed-lora.json) | Image to Video — First + Last Frame + Speed LoRA | ComfyUI-Pixaroma |
| [minimax-h3-img2video-first-last-frame](Image-to-Video/minimax-h3-img2video-first-last-frame.json) | Image to Video — First + Last Frame | ComfyUI-Pixaroma |
| [minimax-h3-img2video-last-frame](Image-to-Video/minimax-h3-img2video-last-frame.json) | Image to Video — Last Frame | ComfyUI-Pixaroma |
| [wan-2.2-img2video-gguf-lightx2v-4-step-lora](Image-to-Video/wan-2.2-img2video-gguf-lightx2v-4-step-lora.json) | Image to Video — GGUF Lightx2v 4-Step + LoRA | ComfyUI-GGUF, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use |
| [wan-2.2-img2video-gguf-lightx2v-4-step](Image-to-Video/wan-2.2-img2video-gguf-lightx2v-4-step.json) | Image to Video — GGUF Lightx2v 4-Step | ComfyUI-GGUF, ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use |

### Reference-to-video, talking video, lip-sync and video dubbing

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [dubsync-hindi-lip-sync-simple-api](Reference-and-Audio-Sync/dubsync-hindi-lip-sync-simple-api.json) | One-node DubSync lip-sync (API format) | ComfyUI-DubSync (local) |
| [dubsync-hindi-lip-sync-simple](Reference-and-Audio-Sync/dubsync-hindi-lip-sync-simple.json) | One-node DubSync lip-sync: video + dubbed audio in, lip-synced video out | ComfyUI-DubSync (local) |
| [dubsync-latentsync-lip-sync-api](Reference-and-Audio-Sync/dubsync-latentsync-lip-sync-api.json) | DubSync + LatentSync lip-sync (API format) | ComfyUI-DubSync (local) |
| [dubsync-latentsync-lip-sync-single-shot](Reference-and-Audio-Sync/dubsync-latentsync-lip-sync-single-shot.json) | DubSync + LatentSync lip-sync for a single shot (load video and audio, sync, save) | ComfyUI-DubSync (local) |
| [dubsync-tbdub-teacher-lip-sync-api](Reference-and-Audio-Sync/dubsync-tbdub-teacher-lip-sync-api.json) | TBDub Teacher lip-sync (API format) | ComfyUI-DubSync (local) |
| [dubsync-tbdub-teacher-lip-sync-single-shot](Reference-and-Audio-Sync/dubsync-tbdub-teacher-lip-sync-single-shot.json) | Best-quality 30-step TBDub Teacher lip-sync for one shot with one visible speaker | ComfyUI-DubSync (local) |
| [latentsync-hindi-lip-sync-dubbing](Reference-and-Audio-Sync/latentsync-hindi-lip-sync-dubbing.json) | Lip-sync an existing video to a new dubbed voice track (e.g. Hindi) with LatentSync | ComfyUI-DubSync (local) |
| [ltx-2-lip-sync-to-your-audio-r01-sc007-0037](Reference-and-Audio-Sync/ltx-2-lip-sync-to-your-audio-r01-sc007-0037.json) | R01_SC007_0037 | ComfyUI-GGUF, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, rgthree-comfy, ComfyUI-ChatterboxTTS |
| [ltx-2-video2video-voice-dubbing-compact](Reference-and-Audio-Sync/ltx-2-video2video-voice-dubbing-compact.json) | Video to Video — Voice Dubbing — Compact | ComfyUI-GGUF, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, rgthree-comfy, ComfyUI-ChatterboxTTS |
| [ltx-2-video2video-voice-dubbing-runpod-1080p](Reference-and-Audio-Sync/ltx-2-video2video-voice-dubbing-runpod-1080p.json) | Video to Video — Voice Dubbing — RunPod 1080p | ComfyUI-GGUF, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, rgthree-comfy, ComfyUI-ChatterboxTTS |
| [ltx-2-video2video-voice-dubbing](Reference-and-Audio-Sync/ltx-2-video2video-voice-dubbing.json) | Video to Video — Voice Dubbing | ComfyUI-GGUF, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, rgthree-comfy, ComfyUI-ChatterboxTTS |
| [minimax-h3-reference-image-audio-sync-sing-speed-lora](Reference-and-Audio-Sync/minimax-h3-reference-image-audio-sync-sing-speed-lora.json) | Reference Image + Audio Sync — Sing + Speed LoRA | ComfyUI-Pixaroma |
| [minimax-h3-reference-image-audio-sync-sing](Reference-and-Audio-Sync/minimax-h3-reference-image-audio-sync-sing.json) | Reference Image + Audio Sync — Sing | ComfyUI-Pixaroma |
| [minimax-h3-reference-image-audio-sync-speak-speed-lora](Reference-and-Audio-Sync/minimax-h3-reference-image-audio-sync-speak-speed-lora.json) | Reference Image + Audio Sync — Speak + Speed LoRA | ComfyUI-Pixaroma |
| [minimax-h3-reference-image-audio-sync-speak](Reference-and-Audio-Sync/minimax-h3-reference-image-audio-sync-speak.json) | Reference Image + Audio Sync — Speak | ComfyUI-Pixaroma |
| [minimax-h3-reference-to-video-2-images](Reference-and-Audio-Sync/minimax-h3-reference-to-video-2-images.json) | Reference to Video — 2 Images | ComfyUI-Pixaroma |
| [minimax-h3-reference-to-video-3-images](Reference-and-Audio-Sync/minimax-h3-reference-to-video-3-images.json) | Reference to Video — 3 Images | ComfyUI-Pixaroma |
| [minimax-h3-reference-to-video-audio-character-swap](Reference-and-Audio-Sync/minimax-h3-reference-to-video-audio-character-swap.json) | Reference to Video + Audio — Character Swap | Core only |
| [wan-2.1-infinitetalk-avatar-generator-video2video-basic-single](Reference-and-Audio-Sync/wan-2.1-infinitetalk-avatar-generator-video2video-basic-single.json) | Talking avatar generator: drive a video with an audio file, TTS or typed text using Wan 2.1 InfiniteTalk | ComfyUI_LayerStyle, audio-separation-nodes-comfyui, ComfyUI_ChatterBox_SRT_Voice, ComfyUI-KJNodes, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, comfy_mtb, ComfyUI-Custom-Scripts, rgthree-comfy |
| [wan-2.1-infinitetalk-talking-video-easy-extend-3-to-34-seconds](Reference-and-Audio-Sync/wan-2.1-infinitetalk-talking-video-easy-extend-3-to-34-seconds.json) | Talking Video — Easy Extend 3 to 34 Seconds | ComfyUI-VideoHelperSuite, rgthree-comfy |
| [wan-2.1-infinitetalk-talking-video-from-audio-10-11-seconds](Reference-and-Audio-Sync/wan-2.1-infinitetalk-talking-video-from-audio-10-11-seconds.json) | Talking Video from Audio — 10-11 Seconds | ComfyUI-VideoHelperSuite |
| [wan-2.1-infinitetalk-talking-video-from-audio-4-6-seconds](Reference-and-Audio-Sync/wan-2.1-infinitetalk-talking-video-from-audio-4-6-seconds.json) | Talking Video from Audio — 4-6 Seconds | ComfyUI-VideoHelperSuite |
| [wan-2.1-infinitetalk-talking-video-from-audio-7-9-seconds](Reference-and-Audio-Sync/wan-2.1-infinitetalk-talking-video-from-audio-7-9-seconds.json) | Talking Video from Audio — 7-9 Seconds | ComfyUI-VideoHelperSuite |
| [wan-2.1-infinitetalk-talking-video-manual-extend-3-to-34-seconds](Reference-and-Audio-Sync/wan-2.1-infinitetalk-talking-video-manual-extend-3-to-34-seconds.json) | Talking Video — Manual Extend 3 to 34 Seconds | ComfyUI-VideoHelperSuite, rgthree-comfy |
| [wan-2.1-infinitetalk-video-dubbing-video2video-flat](Reference-and-Audio-Sync/wan-2.1-infinitetalk-video-dubbing-video2video-flat.json) | Flattened single-path version of the InfiniteTalk video dubbing workflow | ComfyUI_LayerStyle, ComfyUI-KJNodes, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, comfy_mtb, ComfyUI-Custom-Scripts |
| [wan-2.1-infinitetalk-video-dubbing-video2video](Reference-and-Audio-Sync/wan-2.1-infinitetalk-video-dubbing-video2video.json) | Video dubbing (video2video): Wan 2.1 InfiniteTalk re-animates the speaker to a new audio track, TTS or text | ComfyUI_LayerStyle, ComfyUI-KJNodes, ComfyUI-WanVideoWrapper, ComfyUI-VideoHelperSuite, comfy_mtb, ComfyUI-Custom-Scripts, rgthree-comfy |

### Text-to-video (txt2video)

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [minimax-fasth3-txt2video-8-step](Text-to-Video/minimax-fasth3-txt2video-8-step.json) | Text to Video (8-Step) | ComfyUI-Pixaroma |
| [minimax-h3-txt2video-low-vram-8gb](Text-to-Video/minimax-h3-txt2video-low-vram-8gb.json) | Text to Video — Low VRAM 8GB | ComfyUI_LayerStyle, ComfyUI-Pixaroma |
| [minimax-h3-txt2video-secret-sauce-4k-direct-output](Text-to-Video/minimax-h3-txt2video-secret-sauce-4k-direct-output.json) | Text to Video — Secret Sauce 4K Direct Output | ComfyUI-MemoryCleaner, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, rgthree-comfy, ComfyUI-MiniMaxH3-TimelineDirector, ComfyUI_Comfyroll_CustomNodes, ComfyUI-MiniMaxH3-Unified, H3SigmaRefiner (unknown source), RH_DLSS5Enhance (unknown source) |
| [minimax-h3-txt2video-speed-lora](Text-to-Video/minimax-h3-txt2video-speed-lora.json) | Text to Video + Speed LoRA | ComfyUI-Pixaroma |
| [minimax-h3-txt2video](Text-to-Video/minimax-h3-txt2video.json) | Text to Video | ComfyUI-Pixaroma |

### Video upscaling

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [seedvr2-hd-video-upscale](Video-Upscaling/seedvr2-hd-video-upscale.json) | HD Video Upscale | ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-1080p-api](Video-Upscaling/seedvr2-video-upscale-1080p-api.json) | SeedVR2 7B video upscale of one clip to 1080p (API format) | ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-api-run](Video-Upscaling/seedvr2-video-upscale-api-run.json) | Video Upscale — API Run | ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-cartoon-dance-api](Video-Upscaling/seedvr2-video-upscale-cartoon-dance-api.json) | SeedVR2 7B video upscale run (cartoon dance clip) (API format) | ComfyUI-VideoHelperSuite, ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-cartoon-talk-api](Video-Upscaling/seedvr2-video-upscale-cartoon-talk-api.json) | SeedVR2 7B video upscale run (cartoon talk clip) (API format) | ComfyUI-VideoHelperSuite, ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-curly-dance-api](Video-Upscaling/seedvr2-video-upscale-curly-dance-api.json) | SeedVR2 7B video upscale run (curly dance clip) (API format) | ComfyUI-VideoHelperSuite, ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-curly-talk-api](Video-Upscaling/seedvr2-video-upscale-curly-talk-api.json) | SeedVR2 7B video upscale run (curly talk clip) (API format) | ComfyUI-VideoHelperSuite, ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-duo-api](Video-Upscaling/seedvr2-video-upscale-duo-api.json) | SeedVR2 7B video upscale run (duo clip) (API format) | ComfyUI-VideoHelperSuite, ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale-toons-api](Video-Upscaling/seedvr2-video-upscale-toons-api.json) | SeedVR2 7B video upscale run (toons clip) (API format) | ComfyUI-VideoHelperSuite, ComfyUI-SeedVR2_VideoUpscaler |
| [seedvr2-video-upscale](Video-Upscaling/seedvr2-video-upscale.json) | Video Upscale | ComfyUI-VideoHelperSuite, ComfyUI-SeedVR2_VideoUpscaler |

See the [main README](../README.md) for models used, setup steps and the full catalog.
