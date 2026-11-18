# Audio — ComfyUI workflows

Text-to-speech, voice cloning and voice design (Qwen3-TTS, Fish S2, ChatterBox) and music generation (Stable Audio 3, ACE-Step, MiniMax Music 3, YuE 2, Foundation-1) sound effects (Sony Woosh) and music transcription to MIDI (MuScriptor).

| Subfolder | What is inside | Workflows |
|---|---|---|
| [`Music-Generation/`](Music-Generation) | Music generation | 9 |
| [`Music-Transcription/`](Music-Transcription) | Audio to MIDI music transcription | 1 |
| [`Speech-and-Voice-Cloning/`](Speech-and-Voice-Cloning) | Text-to-speech and voice cloning | 11 |
| [`Stem-Separation/`](Stem-Separation) | Vocal, instrument and drum stem extraction | 1 |

## Workflows (22)

### Music generation

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [ace-step-v1.5-lora-training](Music-Generation/ace-step-v1.5-lora-training.json) | LoRA Training (by ZETALVX) | `ace_step_1.5_turbo_aio.safetensors` | fl-acestep-training |
| [ace-step-v1.5-xl-turbo-text-to-music](Music-Generation/ace-step-v1.5-xl-turbo-text-to-music.json) | Text to Music | `qwen_0.6b_ace15.safetensors`, `qwen_4b_ace15.safetensors`, `ace_1.5_vae.safetensors` +1 more | ComfyUI-Pixaroma |
| [foundation-1-text-to-music-loops](Music-Generation/foundation-1-text-to-music-loops.json) | Text to Music Loops and Samples (Foundation-1) that follow key, bar count and BPM (node pack by Saganaki22) | `Foundation_1.safetensors` (auto-downloaded by the node pack) | ComfyUI-Foundation-1 |
| [minimax-music-3-text-to-music](Music-Generation/minimax-music-3-text-to-music.json) | Text to Music | `minimax_music3_dit_int8_convrot.safetensors`, `minimax_music3_text_encoder_pruned_int8_convrot.safetensors`, `minimax_music3_dav.safetensors` | ComfyUI-Pixaroma |
| [stable-audio-3-image-to-music-gemma-4](Music-Generation/stable-audio-3-image-to-music-gemma-4.json) | Image to Music + Gemma 4 | `stable_audio_3_medium.safetensors`, `t5gemma_b_b_ul2.safetensors`, `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma |
| [stable-audio-3-text-to-music-gemma-4-prompt-enhancer](Music-Generation/stable-audio-3-text-to-music-gemma-4-prompt-enhancer.json) | Text to Music + Gemma 4 Prompt Enhancer | `stable_audio_3_medium.safetensors`, `t5gemma_b_b_ul2.safetensors`, `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma |
| [stable-audio-3-text-to-music](Music-Generation/stable-audio-3-text-to-music.json) | Text to Music | `t5gemma_b_b_ul2.safetensors`, `stable_audio_3_medium.safetensors` | ComfyUI-Pixaroma |
| [stable-audio-3-text-to-sound-effects-gemma-4](Music-Generation/stable-audio-3-text-to-sound-effects-gemma-4.json) | Text to Sound Effects + Gemma 4 | `stable_audio_3_medium.safetensors`, `t5gemma_b_b_ul2.safetensors`, `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma |
| [woosh-text-and-video-to-sound-effects](Music-Generation/woosh-text-and-video-to-sound-effects.json) | Text to Sound Effects and Video to Sound Effects (Sony Woosh) | `Woosh-Flow`, `Woosh-VFlow-8s` | ComfyUI-Woosh, ComfyUI-VideoHelperSuite |
| [yue2-lyrics-to-song](Music-Generation/yue2-lyrics-to-song.json) | Lyrics to Song (YuE 2) with SheetSage melody-to-ABC | `yue2_3b_bf16.safetensors`, `sheetsage2_bf16.safetensors` | — |

### Music transcription

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [muscriptor-audio-to-midi-transcription](Music-Transcription/muscriptor-audio-to-midi-transcription.json) | Audio to MIDI multi-instrument transcription (MuScriptor by Kyutai and Mirelo; example workflow by martyyz-ai). The MuScriptor weights are gated on HuggingFace: accept the CC BY-NC 4.0 licence and log in to HuggingFace; they auto-download on first use | MuScriptor `large` (auto-downloaded by the node pack) | [ComfyUI-MuScriptor](https://github.com/martyyz-ai/ComfyUI-MuScriptor), ComfyUI-Custom-Scripts |

### Text-to-speech and voice cloning

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [fish-s2-multi-speaker-dialogue-tts](Speech-and-Voice-Cloning/fish-s2-multi-speaker-dialogue-tts.json) | Multi-Speaker Dialogue TTS | — | ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use, comfyui-fish-audio-s2 |
| [fish-s2-text-to-speech](Speech-and-Voice-Cloning/fish-s2-text-to-speech.json) | Text to Speech | — | ComfyUI-Easy-Use, comfyui-fish-audio-s2 |
| [fish-s2-voice-clone-tts](Speech-and-Voice-Cloning/fish-s2-voice-clone-tts.json) | Voice Clone TTS | — | ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use, comfyui-fish-audio-s2 |
| [qwen3-tts-custom-voice](Speech-and-Voice-Cloning/qwen3-tts-custom-voice.json) | Custom Voice | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-clone-load-saved-voice](Speech-and-Voice-Cloning/qwen3-tts-voice-clone-load-saved-voice.json) | Voice Clone + Load Saved Voice | — | ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-clone-save-voice](Speech-and-Voice-Cloning/qwen3-tts-voice-clone-save-voice.json) | Voice Clone + Save Voice | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-clone-saved-multi-voice-dialogue](Speech-and-Voice-Cloning/qwen3-tts-voice-clone-saved-multi-voice-dialogue.json) | Voice Clone + Saved Multi Voice + Dialogue | — | ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-clone](Speech-and-Voice-Cloning/qwen3-tts-voice-clone.json) | Voice Clone | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-design-dialogue](Speech-and-Voice-Cloning/qwen3-tts-voice-design-dialogue.json) | Voice Design + Dialogue | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-design-save-voice](Speech-and-Voice-Cloning/qwen3-tts-voice-design-save-voice.json) | Voice Design + Save Voice | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-design](Speech-and-Voice-Cloning/qwen3-tts-voice-design.json) | Voice Design | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |

### Stem separation

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [demucs-mdx-audio-separator-stem-separation](Stem-Separation/demucs-mdx-audio-separator-stem-separation.json) | Demucs + MDX + Audio Separator stem extraction: vocals, instruments and percussion from any track (by ZETALVX) | — | audio-separation, audio-separation-nodes-comfyui |

See the [main README](../README.md) for setup steps, requirements and the other categories, or [`00-LIBRARY-INDEX.md`](../00-LIBRARY-INDEX.md) for the full list of workflows.
