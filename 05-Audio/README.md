# Audio — ComfyUI workflows

Text-to-speech, voice cloning and voice design (Qwen3-TTS, Fish S2, ChatterBox) and music generation (Stable Audio 3, ACE-Step, MiniMax Music 3).

| Subfolder | What is inside | Workflows |
|---|---|---|
| [`Music-Generation/`](Music-Generation) | Music generation | 6 |
| [`Speech-and-Voice-Cloning/`](Speech-and-Voice-Cloning) | Text-to-speech and voice cloning | 11 |

## Workflows (17)

### Music generation

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [ace-step-v1.5-xl-turbo-text-to-music](Music-Generation/ace-step-v1.5-xl-turbo-text-to-music.json) | Text to Music | ComfyUI-Pixaroma |
| [minimax-music-3-text-to-music](Music-Generation/minimax-music-3-text-to-music.json) | Text to Music | ComfyUI-Pixaroma |
| [stable-audio-3-image-to-music-gemma-4](Music-Generation/stable-audio-3-image-to-music-gemma-4.json) | Image to Music + Gemma 4 | ComfyUI-Pixaroma |
| [stable-audio-3-text-to-music-gemma-4-prompt-enhancer](Music-Generation/stable-audio-3-text-to-music-gemma-4-prompt-enhancer.json) | Text to Music + Gemma 4 Prompt Enhancer | ComfyUI-Pixaroma |
| [stable-audio-3-text-to-music](Music-Generation/stable-audio-3-text-to-music.json) | Text to Music | ComfyUI-Pixaroma |
| [stable-audio-3-text-to-sound-effects-gemma-4](Music-Generation/stable-audio-3-text-to-sound-effects-gemma-4.json) | Text to Sound Effects + Gemma 4 | ComfyUI-Pixaroma |

### Text-to-speech and voice cloning

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [fish-s2-multi-speaker-dialogue-tts](Speech-and-Voice-Cloning/fish-s2-multi-speaker-dialogue-tts.json) | Multi-Speaker Dialogue TTS | ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use, comfyui-fish-audio-s2 |
| [fish-s2-text-to-speech](Speech-and-Voice-Cloning/fish-s2-text-to-speech.json) | Text to Speech | ComfyUI-Easy-Use, comfyui-fish-audio-s2 |
| [fish-s2-voice-clone-tts](Speech-and-Voice-Cloning/fish-s2-voice-clone-tts.json) | Voice Clone TTS | ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use, comfyui-fish-audio-s2 |
| [qwen3-tts-custom-voice](Speech-and-Voice-Cloning/qwen3-tts-custom-voice.json) | Custom Voice | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-clone-load-saved-voice](Speech-and-Voice-Cloning/qwen3-tts-voice-clone-load-saved-voice.json) | Voice Clone + Load Saved Voice | ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-clone-save-voice](Speech-and-Voice-Cloning/qwen3-tts-voice-clone-save-voice.json) | Voice Clone + Save Voice | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-clone-saved-multi-voice-dialogue](Speech-and-Voice-Cloning/qwen3-tts-voice-clone-saved-multi-voice-dialogue.json) | Voice Clone + Saved Multi Voice + Dialogue | ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-clone](Speech-and-Voice-Cloning/qwen3-tts-voice-clone.json) | Voice Clone | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-design-dialogue](Speech-and-Voice-Cloning/qwen3-tts-voice-design-dialogue.json) | Voice Design + Dialogue | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-design-save-voice](Speech-and-Voice-Cloning/qwen3-tts-voice-design-save-voice.json) | Voice Design + Save Voice | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |
| [qwen3-tts-voice-design](Speech-and-Voice-Cloning/qwen3-tts-voice-design.json) | Voice Design | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use |

See the [main README](../README.md) for models used, setup steps and the full catalog.
