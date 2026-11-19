# Reference and Audio Sync — ComfyUI video workflows

Talking avatars, lip-sync, dubbing and audio-driven video: a picture or a video plus a voice or song track becomes a talking, singing or dubbed clip. Also reference-to-video (pictures as subjects) and portrait animation from a driving video.

> **Not runtime-tested.** Every JSON here was checked only for valid JSON, a genuine ComfyUI graph, model/task fit and duplicates. None was run in this library. Use rights-cleared portraits and consented voices.

| Section | Workflows |
|---|---|
| [Talking avatars from a picture and an audio track](#talking-avatars-from-a-picture-and-an-audio-track) | 19 |
| [MiniMax H3 audio sync, typed speech and timelines](#minimax-h3-audio-sync-typed-speech-and-timelines) | 15 |
| [Reference-to-video (pictures as subjects)](#reference-to-video-pictures-as-subjects) | 6 |
| [Lip-sync and dubbing of existing video](#lip-sync-and-dubbing-of-existing-video) | 16 |
| [Portrait animation from a driving video (no audio)](#portrait-animation-from-a-driving-video-no-audio) | 3 |

## Workflows (59)

### Talking avatars from a picture and an audio track

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [wan-2.2-s2v-sound-to-video-talking-avatar](wan-2.2-s2v-sound-to-video-talking-avatar.json) | **New.** Wan 2.2 S2V: one picture + speech/song audio → talking or singing video, chunked for longer clips (official ComfyUI template) | `umt5_xxl_fp8_e4m3fn_scaled.safetensors`, `wan_2.1_vae.safetensors`, `wav2vec2_large_english_fp16.safetensors` +2 more | core only |
| [wan-2.1-humo-image-audio-reference-to-video](wan-2.1-humo-image-audio-reference-to-video.json) | **New.** HuMo: reference picture + audio + prompt → human video with lip-sync and subject identity (official ComfyUI template) | `umt5_xxl_fp8_e4m3fn_scaled.safetensors`, `wan_2.1_vae.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors` +2 more | core only |
| [wan-2.1-infinitetalk-two-speaker-conversation](wan-2.1-infinitetalk-two-speaker-conversation.json) | **New.** InfiniteTalk *multi* model: two speakers, two audio tracks, painted masks for who speaks → conversation video (official ComfyUI template) | `Wan2_1-I2V-14B-480p_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_infiniteTalk_multi_fp16.safetensors` +3 more | core only |
| [wan-2.1-infinitetalk-talking-video-from-audio-4-6-seconds](wan-2.1-infinitetalk-talking-video-from-audio-4-6-seconds.json) | InfiniteTalk single speaker, picture + audio → 4–6 s talking video | `Wan2_1-I2V-14B-480p_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_infiniteTalk_single_fp16.safetensors` +3 more | ComfyUI-VideoHelperSuite |
| [wan-2.1-infinitetalk-talking-video-from-audio-7-9-seconds](wan-2.1-infinitetalk-talking-video-from-audio-7-9-seconds.json) | InfiniteTalk single speaker, 7–9 s | `Wan2_1-I2V-14B-480p_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_infiniteTalk_single_fp16.safetensors` +3 more | ComfyUI-VideoHelperSuite |
| [wan-2.1-infinitetalk-talking-video-from-audio-10-11-seconds](wan-2.1-infinitetalk-talking-video-from-audio-10-11-seconds.json) | InfiniteTalk single speaker, 10–11 s | `Wan2_1-I2V-14B-480p_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_infiniteTalk_single_fp16.safetensors` +3 more | ComfyUI-VideoHelperSuite |
| [wan-2.1-infinitetalk-talking-video-easy-extend-3-to-34-seconds](wan-2.1-infinitetalk-talking-video-easy-extend-3-to-34-seconds.json) | InfiniteTalk with switchable extension groups, 3–34 s | `Wan2_1-I2V-14B-480p_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_infiniteTalk_single_fp16.safetensors` +3 more | ComfyUI-VideoHelperSuite, rgthree-comfy |
| [wan-2.1-infinitetalk-talking-video-manual-extend-3-to-34-seconds](wan-2.1-infinitetalk-talking-video-manual-extend-3-to-34-seconds.json) | InfiniteTalk with manually chained extension segments, 3–34 s | `Wan2_1-I2V-14B-480p_fp8_e4m3fn_scaled_KJ.safetensors`, `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors`, `wan2.1_infiniteTalk_single_fp16.safetensors` +3 more | ComfyUI-VideoHelperSuite, rgthree-comfy |
| [wan-2.1-fantasytalking-audio-driven-portrait](wan-2.1-fantasytalking-audio-driven-portrait.json) | **New.** FantasyTalking: portrait + speech → talking video on Wan 2.1 I2V (WanVideoWrapper example) | `umt5_xxl_fp16.safetensors`, `clip_vision_h.safetensors`, `Wan2_1-I2V-14B-720P_fp8_e4m3fn.safetensors` +3 more | ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper |
| [skyreels-v3-talking-avatar-audio-to-video](skyreels-v3-talking-avatar-audio-to-video.json) | **New.** SkyReels V3 Talking Avatar (A2V): portrait + audio, vocals separated with MelBandRoFormer (WanVideoWrapper example) | `Wan2_1_VAE_bf16.safetensors`, `wav2vec2-chinese-base_fp16.safetensors`, `MelBandRoformer_fp16.safetensors` +3 more | ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper |
| [longcat-avatar-audio-image-to-video](longcat-avatar-audio-image-to-video.json) | **New.** LongCat-Video Avatar: picture + audio → long talking video with overlapping windows and distill LoRA (WanVideoWrapper example) | `Wan2_1_VAE_bf16.safetensors`, `umt5-xxl-enc-bf16.safetensors`, `wav2vec2-chinese-base_fp16.safetensors` +3 more | ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper |
| [kandinsky-s2v-lite-distilled-speech-to-video](kandinsky-s2v-lite-distilled-speech-to-video.json) | **New.** Kandinsky S2V Lite distilled: reference picture + speech → talking video, trimmed to the audio length (official Kandinsky example) | `kandinsky_s2v_lite_distill.safetensors`, `hunyuan_video_vae_bf16.safetensors`, `clip_l.safetensors` | kandinsky-s2v (ComfyUI nodes) |
| [echomimic-v1-audio-driven-portrait](echomimic-v1-audio-driven-portrait.json) | **New.** EchoMimic V1: portrait + audio → talking head | `sd-vae-ft-mse.safetensors`, `umt5_xxl_fp8_e4m3fn_scaled.safetensors`, `clip_vision_h_wan.safetensors` | ComfyUI-VideoHelperSuite, ComfyUI_EchoMimic |
| [echomimic-v2-half-body-audio-and-pose](echomimic-v2-half-body-audio-and-pose.json) | **New.** EchoMimic V2: half-body picture + audio + pose sequence → talking half-body video with gestures | `umt5_xxl_fp8_e4m3fn_scaled.safetensors`, `clip_vision_h_wan.safetensors`, `sd-vae-ft-mse.safetensors` | ComfyUI-VideoHelperSuite, ComfyUI_EchoMimic |
| [echomimic-v3-audio-driven-avatar](echomimic-v3-audio-driven-avatar.json) | **New.** EchoMimic V3 (Wan 1.3B based): picture + audio → talking avatar | `umt5_xxl_fp8_e4m3fn_scaled.safetensors`, `clip_vision_h_wan.safetensors`, `Wan2.1_VAE.pth` +1 more | ComfyUI-VideoHelperSuite, ComfyUI_EchoMimic |
| [hallo-audio-driven-portrait](hallo-audio-driven-portrait.json) | **New.** Hallo: portrait + audio → expressive talking head (SD1.5-based) | — | ComfyUI-Hallo (AIFSH) |
| [hallo2-long-portrait-animation-with-upscale](hallo2-long-portrait-animation-with-upscale.json) | **New.** Hallo2: long-duration portrait animation with a built-in video super-resolution pass | `RealESRGAN_x2plus.pth`, `detection_Resnet50_Final.pth`, `v1-5-pruned-emaonly.safetensors` +2 more | ComfyUI-VideoHelperSuite, ComfyUI_Hallo2 |
| [sonic-audio-driven-portrait](sonic-audio-driven-portrait.json) | **New.** Sonic: portrait + audio → talking head on SVD, with RIFE frame interpolation | `svd_xt_1_1.safetensors`, `unet.pth` | ComfyUI_Sonic |
| [ltx-2.3-id-lora-talking-video-with-reference-voice](ltx-2.3-id-lora-talking-video-with-reference-voice.json) | **New.** LTX-2.3 ID-LoRA: picture + a short reference voice clip + `[VISUAL]/[SPEECH]/[SOUNDS]` prompt → video whose generated speech keeps that voice (official ComfyUI template) | `ltx-2.3-22b-dev-fp8.safetensors`, `ltx_2.3_22b_distilled_1.1_lora_dynamic_fro09_avg_rank_111_bf16.safetensors`, `gemma_3_12B_it_fp4_mixed.safetensors` +2 more | core only |

### MiniMax H3 audio sync, typed speech and timelines

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [minimax-h3-audio-sync-picture-talk-ep41](minimax-h3-audio-sync-picture-talk-ep41.json) | H3 picture + speech audio → talking video (Ep41) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-audio-sync-picture-sing-ep41](minimax-h3-audio-sync-picture-sing-ep41.json) | H3 picture + song → singing video (Ep41) | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-picture-talk-from-typed-words](minimax-h3-picture-talk-from-typed-words.json) | H3 picture + typed words → talking video with generated speech | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-reference-image-audio-sync-speak](minimax-h3-reference-image-audio-sync-speak.json) | H3 reference picture + speech audio | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-reference-image-audio-sync-speak-speed-lora](minimax-h3-reference-image-audio-sync-speak-speed-lora.json) | Same as above with the speed LoRA | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-reference-image-audio-sync-sing](minimax-h3-reference-image-audio-sync-sing.json) | H3 reference picture + song | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-reference-image-audio-sync-sing-speed-lora](minimax-h3-reference-image-audio-sync-sing-speed-lora.json) | Same as above with the speed LoRA | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-timeline-sing-scenes](minimax-h3-timeline-sing-scenes.json) | H3 timeline: song split into scenes | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-timeline-sing-clean-cuts](minimax-h3-timeline-sing-clean-cuts.json) | H3 timeline: song with clean cuts between scenes | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-timeline-sing-bigger-size](minimax-h3-timeline-sing-bigger-size.json) | H3 timeline: song at larger output size | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-timeline-sing-character-walks-in](minimax-h3-timeline-sing-character-walks-in.json) | H3 timeline: song, character walks into frame | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-timeline-four-singers](minimax-h3-timeline-four-singers.json) | H3 timeline: four singers | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-timeline-act-story-scenes](minimax-h3-timeline-act-story-scenes.json) | H3 timeline: acted story scenes | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-timeline-act-walk-new-place](minimax-h3-timeline-act-walk-new-place.json) | H3 timeline: character walks to a new place | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-timeline-redo-one-scene-keep](minimax-h3-timeline-redo-one-scene-keep.json) | H3 timeline: regenerate one scene, keep the others | `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |

### Reference-to-video (pictures as subjects)

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [minimax-h3-reference-to-video-2-images](minimax-h3-reference-to-video-2-images.json) | H3 reference-to-video from two pictures, native audio | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_fp16.safetensors`, `minimax_h3_audio_vae_fp32.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-reference-to-video-3-images](minimax-h3-reference-to-video-3-images.json) | H3 reference-to-video from three pictures, native audio | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors`, `minimax_h3_video_vae_fp16.safetensors` +1 more | ComfyUI-Pixaroma |
| [minimax-h3-pika-flex-reference-to-video-3-images-2-stage-1088](minimax-h3-pika-flex-reference-to-video-3-images-2-stage-1088.json) | Pika H3 Flex reference-to-video, three pictures, two-stage to 1088p | `minimax_h3_ref2va_pruned_w6a8.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `pika_h3_flex_ref2va_v1_avg_rank_55_bf16.safetensors` +4 more | ComfyUI-KJNodes |
| [minimax-h3-reference-to-video-audio-character-swap](minimax-h3-reference-to-video-audio-character-swap.json) | H3 reference-to-video character swap that keeps the source video audio | `minimax_h3_audio_vae_fp32.safetensors`, `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_video_vae_int8_convrot.safetensors` +4 more | core only |
| [minimax-h3-multiframe-reference-keyframe-guides](minimax-h3-multiframe-reference-keyframe-guides.json) | **New.** H3 reference + keyframe guides (`MiniMaxH3AddGuide`): several pictures pinned to frames of one shot (official ComfyUI template) | `minimax_h3_video_vae_int8_convrot.safetensors`, `minimax_h3_audio_vae_fp32.safetensors`, `minimax_h3_ref2va_pruned_int8_convrot.safetensors` +2 more | core only |
| [skyreels-a2-element-assembly-reference-to-video](skyreels-a2-element-assembly-reference-to-video.json) | **New.** SkyReels-A2: assemble several element pictures (people, objects, background) into one video (WanVideoWrapper example) | `umt5_xxl_fp16.safetensors`, `clip_vision_h.safetensors`, `umt5-xxl-enc-bf16.safetensors` +2 more | ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, ComfyUI_essentials |

### Lip-sync and dubbing of existing video

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [dubsync-latentsync-lip-sync-single-shot](dubsync-latentsync-lip-sync-single-shot.json) | DubSync LatentSync lip-sync of one shot | — | DubSync nodes |
| [dubsync-latentsync-lip-sync-api](dubsync-latentsync-lip-sync-api.json) | Same, API format | — | DubSync nodes |
| [dubsync-hindi-lip-sync-simple](dubsync-hindi-lip-sync-simple.json) | DubSync simple Hindi lip-sync | — | DubSync nodes |
| [dubsync-hindi-lip-sync-simple-api](dubsync-hindi-lip-sync-simple-api.json) | Same, API format | — | DubSync nodes |
| [dubsync-tbdub-teacher-lip-sync-single-shot](dubsync-tbdub-teacher-lip-sync-single-shot.json) | DubSync TBDub teacher model lip-sync of one shot | — | DubSync nodes |
| [dubsync-tbdub-teacher-lip-sync-api](dubsync-tbdub-teacher-lip-sync-api.json) | Same, API format | — | DubSync nodes |
| [latentsync-hindi-lip-sync-dubbing](latentsync-hindi-lip-sync-dubbing.json) | LatentSync Hindi dubbing | — | DubSync nodes |
| [musetalk-lip-sync-video](musetalk-lip-sync-video.json) | **New.** MuseTalk: re-sync mouth of an existing video to new audio (paths in the graph are the author's; point them at your files) | — | ComfyUI-MuseTalk, ComfyUI-VideoHelperSuite |
| [wav2lip-lip-sync-video-with-face-restore](wav2lip-lip-sync-video-with-face-restore.json) | **New.** Wav2Lip lip-sync with GFPGAN face restore. Pretrained Wav2Lip weights are **non-commercial research only** | `GFPGANv1.4.pth` | ComfyUI-VideoHelperSuite, ComfyUI-wav2lip (boxzoo), comfyui-reactor |
| [wan-2.1-infinitetalk-video-dubbing-video2video](wan-2.1-infinitetalk-video-dubbing-video2video.json) | InfiniteTalk video-to-video dubbing | `clip_vision_h.safetensors`, `Wan2_1-I2V-14B-720P_fp8_e4m3fn.safetensors`, `Wan21_I2V_14B_lightx2v_cfg_step_distill_lora_rank64.safetensors` +3 more | ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, comfy-mtb, comfyui-custom-scripts, comfyui_layerstyle, rgthree-comfy |
| [wan-2.1-infinitetalk-video-dubbing-video2video-flat](wan-2.1-infinitetalk-video-dubbing-video2video-flat.json) | Same, without groups/subgraphs | `clip_vision_h.safetensors`, `Wan2_1-I2V-14B-720P_fp8_e4m3fn.safetensors`, `Wan21_I2V_14B_lightx2v_cfg_step_distill_lora_rank64.safetensors` +3 more | ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, comfy-mtb, comfyui-custom-scripts, comfyui_layerstyle |
| [wan-2.1-infinitetalk-avatar-generator-video2video-basic-single](wan-2.1-infinitetalk-avatar-generator-video2video-basic-single.json) | InfiniteTalk V2V avatar with optional TTS | `clip_vision_h.safetensors`, `Wan2_1-I2V-14B-720P_fp8_e4m3fn.safetensors`, `Wan21_I2V_14B_lightx2v_cfg_step_distill_lora_rank64.safetensors` +3 more | ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, audio-separation-nodes-comfyui, chatterbox_srt_voice, comfy-mtb, comfyui-custom-scripts, comfyui_layerstyle, rgthree-comfy |
| [ltx-2-lip-sync-to-your-audio-r01-sc007-0037](ltx-2-lip-sync-to-your-audio-r01-sc007-0037.json) | LTX-2 lip-sync a shot to your audio (with voice conversion) | `LTX2_video_vae_bf16_KJ.safetensors`, `LTX2_audio_vae_bf16_KJ.safetensors`, `ltx-2-spatial-upscaler-x2-1.0.safetensors` +7 more | ComfyUI-ChatterboxTTS, ComfyUI-GGUF, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, rgthree-comfy |
| [ltx-2-video2video-voice-dubbing](ltx-2-video2video-voice-dubbing.json) | LTX-2 video-to-video voice dubbing | `LTX2_video_vae_bf16_KJ.safetensors`, `LTX2_audio_vae_bf16_KJ.safetensors`, `ltx-2-spatial-upscaler-x2-1.0.safetensors` +10 more | ComfyUI-ChatterboxTTS, ComfyUI-GGUF, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, rgthree-comfy |
| [ltx-2-video2video-voice-dubbing-compact](ltx-2-video2video-voice-dubbing-compact.json) | Same, compact layout | `LTX2_video_vae_bf16_KJ.safetensors`, `LTX2_audio_vae_bf16_KJ.safetensors`, `ltx-2-spatial-upscaler-x2-1.0.safetensors` +10 more | ComfyUI-ChatterboxTTS, ComfyUI-GGUF, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, rgthree-comfy |
| [ltx-2-video2video-voice-dubbing-runpod-1080p](ltx-2-video2video-voice-dubbing-runpod-1080p.json) | Same, 1080p RunPod settings | `LTX2_video_vae_bf16_KJ.safetensors`, `LTX2_audio_vae_bf16_KJ.safetensors`, `ltx-2-spatial-upscaler-x2-1.0.safetensors` +10 more | ComfyUI-ChatterboxTTS, ComfyUI-GGUF, ComfyUI-KJNodes, ComfyUI-MelBandRoFormer, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper, rgthree-comfy |

### Portrait animation from a driving video (no audio)

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [liveportrait-animate-image-from-driving-video](liveportrait-animate-image-from-driving-video.json) | **New.** LivePortrait: a still portrait copies the head motion and expressions of a driving video | — | ComfyUI-KJNodes, ComfyUI-LivePortraitKJ, ComfyUI-VideoHelperSuite, ComfyUI_essentials |
| [liveportrait-video-to-video-expression-retarget](liveportrait-video-to-video-expression-retarget.json) | **New.** LivePortrait video-to-video: retarget expressions from a driving video onto a source video | — | ComfyUI-KJNodes, ComfyUI-LivePortraitKJ, ComfyUI-VideoHelperSuite, ComfyUI_essentials |
| [wan-2.1-fantasyportrait-expression-transfer-from-video](wan-2.1-fantasyportrait-expression-transfer-from-video.json) | **New.** FantasyPortrait: facial expression transfer from a driving video on Wan 2.1 I2V (WanVideoWrapper example) | `Wan2_1_VAE_bf16.safetensors`, `clip_vision_h.safetensors`, `Wan2_1_FantasyPortrait_fp16.safetensors` +3 more | ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-WanVideoWrapper |

## Sources and licences of the new workflows

The workflow JSON licence (the repo it came from) is separate from the **model weight licence**. Weight licences below are from the model cards at collection time — recheck before commercial use.

| Workflow | Source | JSON licence | Model weights (download) | Weight licence |
|---|---|---|---|---|
| wan-2.2-s2v-sound-to-video-talking-avatar | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan2_2_14B_s2v.json) | MIT | [Comfy-Org/Wan_2.2_ComfyUI_Repackaged](https://huggingface.co/Comfy-Org/Wan_2.2_ComfyUI_Repackaged) | Apache-2.0 |
| wan-2.1-humo-image-audio-reference-to-video | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_humo.json) | MIT | [Comfy-Org/HuMo_ComfyUI](https://huggingface.co/Comfy-Org/HuMo_ComfyUI) | Apache-2.0 |
| wan-2.1-infinitetalk-two-speaker-conversation | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan2_1_infinitetalk.json) | MIT | [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy), [MeiGen-AI/InfiniteTalk](https://huggingface.co/MeiGen-AI/InfiniteTalk) | Apache-2.0 (verify model card) |
| ltx-2.3-id-lora-talking-video-with-reference-voice | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_ltx2_3_id_lora.json) | MIT | [Lightricks/LTX-2.3](https://huggingface.co/Lightricks/LTX-2.3), [ID-LoRA](https://github.com/ID-LoRA/ID-LoRA) | **LTX-2 Community License** (custom, revenue conditions) |
| minimax-h3-multiframe-reference-keyframe-guides | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_minimax_h3_multiframe_reference.json) | MIT | [Comfy-Org/MiniMax-H3](https://huggingface.co/Comfy-Org/MiniMax-H3) | **MiniMax custom licence** |
| longcat-avatar-audio-image-to-video | [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/LongCatAvatar_audio_image_to_video_example_01.json) | Apache-2.0 | [Kijai/LongCat-Video_comfy](https://huggingface.co/Kijai/LongCat-Video_comfy), [meituan-longcat](https://huggingface.co/meituan-longcat) | MIT |
| wan-2.1-fantasytalking-audio-driven-portrait | [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/wanvideo_2_1_14B_I2V_FantasyTalking_example_01.json) | Apache-2.0 | [acvlab/FantasyTalking](https://huggingface.co/acvlab/FantasyTalking), [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy) | Apache-2.0 (verify model card) |
| wan-2.1-fantasyportrait-expression-transfer-from-video | [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/wanvideo_2_1_14B_I2V_FantasyPortrait_example_01.json) | Apache-2.0 | [acvlab/FantasyPortrait](https://huggingface.co/acvlab/FantasyPortrait), [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy) | Apache-2.0 (verify model card) |
| skyreels-v3-talking-avatar-audio-to-video | [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/wanvideo_2_1_14B_I2V_SkyReelsV3_TalkingAvatar_example_01.json) | Apache-2.0 | [Skywork/SkyReels-V3](https://github.com/SkyworkAI/SkyReels-V3), [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy) | See SkyReels V3 model card |
| skyreels-a2-element-assembly-reference-to-video | [kijai/ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/wanvideo_2_1_14B_skyreels_a2_example_01.json) | Apache-2.0 | [Skywork/SkyReels-A2](https://huggingface.co/Skywork/SkyReels-A2), [Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy) | See SkyReels-A2 model card |
| kandinsky-s2v-lite-distilled-speech-to-video | [kandinskylab/kandinsky-s2v](https://github.com/kandinskylab/kandinsky-s2v/tree/main/dev/comfyui/example_workflows) | MIT | [kandinskylab/kandinsky-s2v](https://github.com/kandinskylab/kandinsky-s2v) (model links in README) | MIT per repo (verify model card) |
| echomimic-v1 / v2 / v3 | [smthemex/ComfyUI_EchoMimic](https://github.com/smthemex/ComfyUI_EchoMimic/tree/main/example_workflows) | Apache-2.0 | [BadToBest/EchoMimic](https://huggingface.co/BadToBest/EchoMimic), [EchoMimicV2](https://huggingface.co/BadToBest/EchoMimicV2), [EchoMimicV3](https://huggingface.co/BadToBest/EchoMimicV3) | Apache-2.0 (verify model card) |
| hallo-audio-driven-portrait | [AIFSH/ComfyUI-Hallo](https://github.com/AIFSH/ComfyUI-Hallo/blob/main/hallo_base_workflow.json) | MIT | [fudan-generative-ai/hallo](https://huggingface.co/fudan-generative-ai/hallo) | MIT (third-party sub-models have own terms) |
| hallo2-long-portrait-animation-with-upscale | [smthemex/ComfyUI_Hallo2](https://github.com/smthemex/ComfyUI_Hallo2/blob/main/workflow.json) | MIT | [fudan-generative-ai/hallo2](https://huggingface.co/fudan-generative-ai/hallo2) | MIT (third-party sub-models have own terms) |
| sonic-audio-driven-portrait | [smthemex/ComfyUI_Sonic](https://github.com/smthemex/ComfyUI_Sonic/blob/main/example_workflows/sonic.json) | MIT | [LeonJoe13/Sonic](https://huggingface.co/LeonJoe13/Sonic), SVD-XT 1.1 | **Non-commercial** (Sonic CC BY-NC-SA; SVD under Stability licence) — verify |
| musetalk-lip-sync-video | [chaojie/ComfyUI-MuseTalk](https://github.com/chaojie/ComfyUI-MuseTalk/blob/main/wf.json) | MIT | [TMElyralab/MuseTalk](https://huggingface.co/TMElyralab/MuseTalk) | MIT (whisper, sd-vae, dwpose have own terms) |
| wav2lip-lip-sync-video-with-face-restore | [boxzoo/ComfyUI-wav2lip](https://github.com/boxzoo/ComfyUI-wav2lip/tree/main/example) | GPL-3.0 | [Rudrabha/Wav2Lip](https://github.com/Rudrabha/Wav2Lip) | **Non-commercial research only** (LRS2) |
| liveportrait-animate-image / video-to-video | [kijai/ComfyUI-LivePortraitKJ](https://github.com/kijai/ComfyUI-LivePortraitKJ/tree/main/examples) | MIT | [Kijai/LivePortrait_safetensors](https://huggingface.co/Kijai/LivePortrait_safetensors) (auto-download) | MIT; the InsightFace cropper is **non-commercial** — use the MediaPipe cropper for commercial work |

## Equivalent already present (not added)

- LTX-2 / LTX-2.3 / LTX-2.5 image+audio-to-video ([template](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_ltx_2_audio_to_video.json), [2.3 IA2V](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_ltx2_3_ia2v.json), [2.5 A2V](https://github.com/Lightricks/ComfyUI-LTXVideo/blob/master/example_workflows/2.5/LTX-2.5_A2V_Two_Stage_Distilled.json)) — same task as `ltx-2-lip-sync-to-your-audio-*` here and `Image-to-Video/ltx-2-img2video-with-custom-audio`. Lightricks' own JSONs are under the LTX-2 Community License, which requires shipping the full licence text, so they are linked, not copied.
- LTX-2.3 DubIt IC-LoRA dubbing ([link](https://github.com/Lightricks/ComfyUI-LTXVideo/blob/master/example_workflows/2.3/LTX-2.3_ICLoRA_DubIt_Two_Stage_Distilled.json)) — same task as the `ltx-2-video2video-voice-dubbing*` files.
- InfiniteTalk I2V and V2V WanVideoWrapper examples — same tasks as the InfiniteTalk files here.
- HuMo WanVideoWrapper example — same task as the native HuMo template above.
- MiniMax H3 / Pika H3 Flex reference-to-video templates, FastH3 OmniRef 8-step reference — same task as the H3 reference files here (a faster checkpoint alone is not a new capability).
- Kandinsky S2V **Pro** distilled — same graph as Lite with a bigger checkpoint.
- EchoMimic V2 video-driven pose and V3 Flash — checkpoint/driver variants of the EchoMimic files above.

## No ComfyUI workflow found (talking avatar / lip-sync / audio-video slice)

| Model | Why not here |
|---|---|
| MultiTalk (MeiGen) | Folded into InfiniteTalk multi in maintained nodes; no current standalone MultiTalk JSON (see `wan-2.1-infinitetalk-two-speaker-conversation`) |
| SadTalker 256 / 512 | Only unlicensed community node repos with no example JSON |
| VideoReTalking | No ComfyUI node or workflow found |
| OmniAvatar | Single small community repo, no licence, no example JSON |
| HunyuanPortrait | Community nodes have no example JSON |
| HunyuanVideo-Avatar (single / dual) | Example JSONs exist in [smthemex/ComfyUI_HunyuanAvatar_Sm](https://github.com/smthemex/ComfyUI_HunyuanAvatar_Sm/tree/main/example_workflows) but the repo is under the Tencent Hunyuan Community License (territory-limited); linked, not copied |
| HunyuanVideo-Foley | Node packs found ([if-ai](https://github.com/if-ai/ComfyUI_HunyuanVideoFoley), [aistudynow](https://github.com/aistudynow/Comfyui-HunyuanFoley)) but no example workflow JSON |
| SkyReels-A1 portrait animation | No maintained ComfyUI workflow found |
| LatentSync 1.0 / 1.5 standalone | Covered by the DubSync LatentSync files; [ComfyUI-LatentSyncWrapper](https://github.com/ShmuelRonen/ComfyUI-LatentSyncWrapper) has no licence |
| LivePortrait animals branch | No separate ComfyUI workflow |
| AdvancedLivePortrait expression editing | [PowerHouseMan/ComfyUI-AdvancedLivePortrait](https://github.com/PowerHouseMan/ComfyUI-AdvancedLivePortrait/tree/main/sample/workflows) has samples but no licence; linked only |

## Belongs in other 04-Video folders (left for the integration pass)

Native audio+video generation that is plain text- or image-to-video: Kandinsky 6 T2V+Audio / I2V+Audio ([official JSONs, MIT](https://github.com/kandinskylab/kandinsky-6/tree/main/comfyui/example_workflows)), Ovi Wan 2.2 5B image-to-video+audio ([WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper/tree/main/example_workflows)), LTX-2.5 T2V/I2V with audio, MiniMax H3 / FastH3 T2V and I2V.
