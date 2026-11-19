# Audio Speech — ComfyUI workflows

Text-to-speech, voice cloning, voice design and dialogue; voice conversion; speech enhancement and voice isolation; speech-to-text, subtitles and diarisation; speech translation; forced alignment.

[← 03-Audio overview](../README.md) · [Library index](../../00-LIBRARY-INDEX.md)

**149 workflows** in **51 model folders**. Each model folder holds only workflow files; the file name says the task first, then the variant: `<task>[-<variant>][-<size>][-<precision>][-<feature>].json`. `Other/` holds generic or multi-model workflows.

## Model folders

| Model | Workflows | Tasks |
|---|---|---|
| [Bark](#bark) | 1 | `tts` |
| [Chatterbox](#chatterbox) | 7 | `tts`, `tts-dialogue`, `voice-conversion` |
| [ChatTTS](#chattts) | 1 | `tts` |
| [ClearVoice](#clearvoice) | 1 | `speech-enhance` |
| [CosyVoice](#cosyvoice) | 10 | `tts`, `voice-clone` |
| [Dia](#dia) | 5 | `tts`, `voice-clone` |
| [DramaBox](#dramabox) | 1 | `tts` |
| [ElevenLabs](#elevenlabs) | 7 | `stt`, `tts`, `tts-dialogue`, `voice-conversion`, `voice-isolation` |
| [F5-TTS](#f5-tts) | 5 | `speech-edit`, `tts`, `voice-clone` |
| [FireRedTTS](#fireredtts) | 1 | `tts` |
| [Fish-Speech](#fish-speech) | 9 | `stt`, `tts`, `tts-dialogue`, `voice-clone` |
| [FunASR](#funasr) | 2 | `subtitles` |
| [GPT-SoVITS](#gpt-sovits) | 2 | `tts`, `voice-training` |
| [Hibiki](#hibiki) | 1 | `speech-translation` |
| [Higgs-Audio](#higgs-audio) | 2 | `tts`, `voice-clone` |
| [IndexTTS](#indextts) | 7 | `tts`, `tts-dialogue`, `voice-clone` |
| [Kani-TTS](#kani-tts) | 1 | `tts` |
| [Kitten-TTS](#kitten-tts) | 1 | `tts` |
| [Kokoro](#kokoro) | 1 | `tts` |
| [Kyutai](#kyutai) | 1 | `tts` |
| [MARS5](#mars5) | 1 | `voice-clone` |
| [MaskGCT](#maskgct) | 1 | `tts` |
| [Maya](#maya) | 4 | `tts`, `voice-clone` |
| [Mega-ASR](#mega-asr) | 1 | `stt` |
| [MeloTTS](#melotts) | 1 | `tts` |
| [MisoTTS](#misotts) | 1 | `tts` |
| [MOSS](#moss) | 6 | `stt`, `tts-dialogue`, `voice-clone`, `voice-design` |
| [Nemotron](#nemotron) | 2 | `stt` |
| [NeuTTS](#neutts) | 1 | `voice-clone` |
| [OmniVoice](#omnivoice) | 2 | `tts` |
| [OpenVoice](#openvoice) | 1 | `tts-and-voice-conversion` |
| [Orpheus](#orpheus) | 2 | `tts`, `voice-clone` |
| [Parakeet](#parakeet) | 1 | `subtitles` |
| [Parler-TTS](#parler-tts) | 1 | `tts` |
| [Qwen3-ASR](#qwen3-asr) | 5 | `forced-alignment`, `stt`, `subtitles` |
| [Qwen3-TTS](#qwen3-tts) | 11 | `tts`, `voice-clone`, `voice-design` |
| [RVC](#rvc) | 3 | `voice-conversion`, `voice-training` |
| [Seed-VC](#seed-vc) | 2 | `voice-conversion` |
| [SenseVoice](#sensevoice) | 1 | `stt` |
| [Sesame-CSM](#sesame-csm) | 4 | `tts`, `tts-dialogue`, `voice-clone` |
| [Spark-TTS](#spark-tts) | 1 | `voice-clone` |
| [Step-Audio](#step-audio) | 2 | `speech-edit`, `voice-clone` |
| [Supertonic](#supertonic) | 1 | `tts` |
| [VibeVoice](#vibevoice) | 5 | `tts`, `tts-dialogue` |
| [VoiceBridge](#voicebridge) | 1 | `speech-translation` |
| [VoxCPM](#voxcpm) | 3 | `tts-and-voice-clone`, `voice-clone`, `voice-training` |
| [VoxLock](#voxlock) | 2 | `voice-isolation` |
| [Whisper](#whisper) | 6 | `stt`, `subtitles` |
| [ZipVoice](#zipvoice) | 1 | `tts` |
| [Zonos](#zonos) | 5 | `tts`, `voice-clone`, `voice-design` |
| [Other](#other) | 5 | `forced-alignment`, `speech-enhance`, `subtitles`, `voice-design` |

## Bark

Folder: [`Bark/`](Bark) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts](Bark/tts.json) | Text to speech with laughs, music and non-speech sounds | Auto-download [GitMylo/bark-safetensors](https://huggingface.co/GitMylo/bark-safetensors) | [ComfyUI-audio-nodes](https://github.com/gitmylo/ComfyUI-audio-nodes) | Model: Bark (Suno); VRAM (approx.): ~6-12 GB; Licence: Model MIT (commercial OK); pack has no licence file; Status: not yet tested |

## Chatterbox

Folder: [`Chatterbox/`](Chatterbox) — 7 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-dialogue](Chatterbox/tts-dialogue.json) | Two-speaker dialogue (official Comfy template) | As above | [ComfyUI_Fill-ChatterBox](https://github.com/filliptm/ComfyUI_Fill-ChatterBox) | Model: Chatterbox; VRAM (approx.): 8 GB+; Licence: Model MIT (commercial OK); Status: not yet tested |
| [tts-fill-all-modes-incl-turbo](Chatterbox/tts-fill-all-modes-incl-turbo.json) | All Fill-ChatterBox nodes in one graph, including Turbo | As above | [ComfyUI_Fill-ChatterBox](https://github.com/filliptm/ComfyUI_Fill-ChatterBox) | Model: Chatterbox, Turbo, Multilingual, VC; VRAM (approx.): 8 GB+; Licence: Model MIT (commercial OK); Status: not yet tested |
| [tts-multilingual](Chatterbox/tts-multilingual.json) | Multilingual TTS with voice clone (official Comfy template) | As above | [ComfyUI_Fill-ChatterBox](https://github.com/filliptm/ComfyUI_Fill-ChatterBox) | Model: Chatterbox Multilingual (23 languages incl. Hindi); VRAM (approx.): 8 GB+; Licence: Model MIT (commercial OK); Status: not yet tested |
| [tts-wildminder-dialogue-srt-vc](Chatterbox/tts-wildminder-dialogue-srt-vc.json) | TTS, multilingual, dialogue, SRT timing and voice conversion | Auto-download [ResembleAI/chatterbox](https://huggingface.co/ResembleAI/chatterbox) to `models/tts/chatterbox/` (~2.5 GB each) | [ComfyUI-Chatterbox](https://github.com/wildminder/ComfyUI-Chatterbox) | Model: Chatterbox, Multilingual, Turbo; VRAM (approx.): ~6-8 GB; Licence: Model MIT (commercial OK); pack Apache-2.0; Status: not yet tested |
| [tts](Chatterbox/tts.json) | Text to speech with optional voice clone (official Comfy template) | Auto-download to `models/chatterbox/` | [ComfyUI_Fill-ChatterBox](https://github.com/filliptm/ComfyUI_Fill-ChatterBox) | Model: Chatterbox (Resemble AI); VRAM (approx.): 8 GB+ recommended; Licence: Model MIT (commercial OK); outputs watermarked; upstream retired Aug 2026; Status: not yet tested |
| [voice-conversion-tts-audio-suite](Chatterbox/voice-conversion-tts-audio-suite.json) | Character voices TTS and voice changer | Auto-download to `models/TTS/` | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Model: Chatterbox; VRAM (approx.): ~6-8 GB; Licence: Model MIT (commercial OK); Status: not yet tested |
| [voice-conversion](Chatterbox/voice-conversion.json) | Speech-to-speech voice conversion (official Comfy template) | As above | [ComfyUI_Fill-ChatterBox](https://github.com/filliptm/ComfyUI_Fill-ChatterBox) | Model: Chatterbox VC; VRAM (approx.): 8 GB+; Licence: Model MIT (commercial OK); Status: not yet tested |

## ChatTTS

Folder: [`ChatTTS/`](ChatTTS) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts](ChatTTS/tts.json) | Conversational text to speech with sampled speakers | ChatTTS weights to `models/chattts/` | [ComfyUI-ChatTTS](https://github.com/neverbiasu/ComfyUI-ChatTTS) | Model: ChatTTS; VRAM (approx.): ~4 GB; Licence: **Weights CC-BY-NC-4.0 (non-commercial)**; pack MIT; Status: not yet tested |

## ClearVoice

Folder: [`ClearVoice/`](ClearVoice) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [speech-enhance-fl](ClearVoice/speech-enhance-fl.json) | Denoise, enhance and super-resolve speech (the `FL_Audio_Crop` node was not found in the pack mappings) | Auto-download to `models/clear_voice/` | [ComfyUI_FL-ClearVoice](https://github.com/filliptm/ComfyUI_FL-ClearVoice) | Model: ClearerVoice, Resemble-Enhance, VoiceFixer; VRAM (approx.): ~2-4 GB; Licence: Models Apache-2.0 / MIT; pack MIT per pyproject, no LICENSE file; Status: not yet tested |

## CosyVoice

Folder: [`CosyVoice/`](CosyVoice) — 10 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-300m-instruct](CosyVoice/tts-300m-instruct.json) | Instruct TTS: speaker, emotion and style from a text instruction | Auto-download `iic/CosyVoice-300M-Instruct` | [CosyVoice-ComfyUI](https://github.com/AIFSH/CosyVoice-ComfyUI) | Model: CosyVoice 300M-Instruct (v1); VRAM (approx.): ~4-8 GB; Licence: Model Apache-2.0 (commercial OK); Status: not yet tested |
| [tts-300m-sft-preset-speakers](CosyVoice/tts-300m-sft-preset-speakers.json) | TTS with built-in preset speakers | Auto-download `iic/CosyVoice-300M-SFT` | [CosyVoice-ComfyUI](https://github.com/AIFSH/CosyVoice-ComfyUI) | Model: CosyVoice 300M-SFT (v1); VRAM (approx.): ~4-8 GB; Licence: Model Apache-2.0 (commercial OK); Status: not yet tested |
| [tts-v2-basic](CosyVoice/tts-v2-basic.json) | Basic CosyVoice2 text to speech with a reference voice | [FunAudioLLM/CosyVoice2-0.5B](https://huggingface.co/FunAudioLLM/CosyVoice2-0.5B) | [ComfyUI_CosyVoice2](https://github.com/HJH-AILab/ComfyUI_CosyVoice2) | Model: CosyVoice2 0.5B; VRAM (approx.): ~4-6 GB; Licence: Weights Apache-2.0; pack Apache-2.0; Status: not yet tested |
| [tts-v2-instruct](CosyVoice/tts-v2-instruct.json) | Instruct2: control style and dialect with a text instruction | As above | [ComfyUI_NTCosyVoice](https://github.com/muxueChen/ComfyUI_NTCosyVoice) | Model: CosyVoice2 0.5B; VRAM (approx.): ~4-6 GB; Licence: Weights Apache-2.0; pack licence not declared; Status: not yet tested |
| [tts-v3-all-modes](CosyVoice/tts-v3-all-modes.json) | Zero-shot, cross-lingual, dialogue and voice conversion | [FunAudioLLM/Fun-CosyVoice3-0.5B-2512](https://huggingface.co/FunAudioLLM/Fun-CosyVoice3-0.5B-2512) to `models/cosyvoice/`; Python 3.10; the sample is a video file in a Load Audio node | [ComfyUI_FL-CosyVoice3](https://github.com/filliptm/ComfyUI_FL-CosyVoice3) | Model: CosyVoice3 0.5B; VRAM (approx.): ~8-16 GB; Licence: Weights Apache-2.0; pack licence not declared on GitHub; Status: not yet tested |
| [tts-v3-ts-examples](CosyVoice/tts-v3-ts-examples.json) | Instruct, voice conversion, cross-lingual, dialogue and saved speakers | As above, plus `speaker/` and `whisper/` subfolders; needs ffmpeg | [comfyui-ts-cosyvoice](https://github.com/AlexYez/comfyui-ts-cosyvoice) | Model: CosyVoice3 0.5B; VRAM (approx.): ~5 GB; Licence: Weights Apache-2.0; pack MIT; sample in Russian; Status: not yet tested |
| [voice-clone-300m-cross-lingual](CosyVoice/voice-clone-300m-cross-lingual.json) | Cross-lingual voice clone (speak another language in the reference voice) | Auto-download `iic/CosyVoice-300M` | [CosyVoice-ComfyUI](https://github.com/AIFSH/CosyVoice-ComfyUI) | Model: CosyVoice 300M (v1); VRAM (approx.): ~4-8 GB; Licence: Model Apache-2.0 (commercial OK); Status: not yet tested |
| [voice-clone-300m-zero-shot](CosyVoice/voice-clone-300m-zero-shot.json) | Zero-shot voice clone from a 3 s reference | Auto-download from ModelScope `iic/CosyVoice-300M` into the pack's `pretrained_models/` | [CosyVoice-ComfyUI](https://github.com/AIFSH/CosyVoice-ComfyUI) | Model: CosyVoice 300M (v1); VRAM (approx.): ~4-8 GB (tested on 11 GB); Licence: Model Apache-2.0 (commercial OK); pack Apache-2.0; pack last updated 2024-09; Status: not yet tested |
| [voice-clone-v2-crosslingual](CosyVoice/voice-clone-v2-crosslingual.json) | Cross-lingual clone (speak another language in the reference voice) | As above | [ComfyUI_NTCosyVoice](https://github.com/muxueChen/ComfyUI_NTCosyVoice) | Model: CosyVoice2 0.5B; VRAM (approx.): ~4-6 GB; Licence: Weights Apache-2.0; pack licence not declared; Status: not yet tested |
| [voice-clone-v2-zero-shot](CosyVoice/voice-clone-v2-zero-shot.json) | Zero-shot voice clone (3-node graph) | CosyVoice2-0.5B; model folder per pack README | [ComfyUI_NTCosyVoice](https://github.com/muxueChen/ComfyUI_NTCosyVoice) | Model: CosyVoice2 0.5B; VRAM (approx.): ~4-6 GB; Licence: Weights Apache-2.0; pack licence not declared; Status: not yet tested |

## Dia

Folder: [`Dia/`](Dia) — 5 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-1.6b-audio-retimer](Dia/tts-1.6b-audio-retimer.json) | Dialogue TTS, then stretch the result to a target length | As above | [comfyUI-customDia](https://github.com/nobrainX2/comfyUI-customDia) | Model: Dia 1.6B; VRAM (approx.): ~10 GB; Licence: Model Apache-2.0 (commercial OK); Status: not yet tested |
| [tts-1.6b-dialogue](Dia/tts-1.6b-dialogue.json) | Two-speaker dialogue TTS with [S1]/[S2] tags and non-verbal sounds | [nari-labs/Dia-1.6B](https://huggingface.co/nari-labs/Dia-1.6B) `.pth` + `.json` to `models/Dia/` | [comfyUI-customDia](https://github.com/nobrainX2/comfyUI-customDia) | Model: Dia 1.6B (Nari Labs); VRAM (approx.): ~10 GB; Licence: Model Apache-2.0 (commercial OK); pack Apache-2.0; Status: not yet tested |
| [tts-1.6b-safetensors-loader](Dia/tts-1.6b-safetensors-loader.json) | Dialogue TTS with a separate model loader (safetensors) | [nari-labs/Dia-1.6B](https://huggingface.co/nari-labs/Dia-1.6B) `model.safetensors` to `models/diffusion_models/` | [ComfyUI-DiaTTS](https://github.com/BobRandomNumber/ComfyUI-DiaTTS) | Model: Dia 1.6B; VRAM (approx.): ~10 GB; Licence: Model Apache-2.0 (commercial OK); pack experimental; Status: not yet tested |
| [tts-v2-and-captions](Dia/tts-v2-and-captions.json) | Dialogue TTS plus caption generation from audio | [nari-labs/Dia2-2B](https://huggingface.co/nari-labs/Dia2-2B) `model.safetensors` + `tokenizer.json` to `models/Dia2/` | [ComfyUI-lethris-dia2](https://github.com/lord-lethris/ComfyUI-lethris-dia2), [rgthree-comfy](https://github.com/rgthree/rgthree-comfy), [ComfyUI-Custom-Scripts](https://github.com/pythongosssss/ComfyUI-Custom-Scripts) | Model: Dia2 2B; VRAM (approx.): ~10-12 GB; needs CUDA 12.8+; Licence: Model Apache-2.0 (commercial OK); pack MIT; Status: not yet tested |
| [voice-clone-1.6b](Dia/voice-clone-1.6b.json) | Dialogue TTS that clones the voices of a reference clip | As above | [comfyUI-customDia](https://github.com/nobrainX2/comfyUI-customDia) | Model: Dia 1.6B; VRAM (approx.): ~10 GB; Licence: Model Apache-2.0 (commercial OK); Status: not yet tested |

## DramaBox

Folder: [`DramaBox/`](DramaBox) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-audio-suite](DramaBox/tts-audio-suite.json) | Expressive acted TTS through the unified engine | Auto-download to `models/TTS/` | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Model: DramaBox (Resemble AI); VRAM (approx.): not stated; Licence: Pack MIT; check the DramaBox licence; Status: not yet tested |

## ElevenLabs

Folder: [`ElevenLabs/`](ElevenLabs) — 7 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [stt-api](ElevenLabs/stt-api.json) | Speech to text | None (cloud) | none (ComfyUI core API nodes) | Model: ElevenLabs Scribe (API); VRAM (approx.): None; Licence: paid Comfy API credits; output under provider terms; Status: not yet tested |
| [tts-api](ElevenLabs/tts-api.json) | Text to speech with voice selector or instant voice clone | None (cloud) | none (ComfyUI core API nodes) | Model: ElevenLabs (API); VRAM (approx.): None; Licence: paid Comfy API credits; output under provider terms; Status: not yet tested |
| [tts-dialogue-api](ElevenLabs/tts-dialogue-api.json) | Multi-voice dialogue | None (cloud) | none (ComfyUI core API nodes) | Model: ElevenLabs (API); VRAM (approx.): None; Licence: paid Comfy API credits; output under provider terms; Status: not yet tested |
| [tts-dialogue-v4-api](ElevenLabs/tts-dialogue-v4-api.json) | Multi-voice dialogue, v4 model | None (cloud) | none (ComfyUI core API nodes) | Model: ElevenLabs v4 (API); VRAM (approx.): None; Licence: paid Comfy API credits; output under provider terms; Status: not yet tested |
| [tts-v4-api](ElevenLabs/tts-v4-api.json) | Text to speech, v4 model | None (cloud) | none (ComfyUI core API nodes) | Model: ElevenLabs v4 (API); VRAM (approx.): None; Licence: paid Comfy API credits; output under provider terms; Status: not yet tested |
| [voice-conversion-api](ElevenLabs/voice-conversion-api.json) | Speech-to-speech voice changer | None (cloud) | none (ComfyUI core API nodes) | Model: ElevenLabs (API); VRAM (approx.): None; Licence: paid Comfy API credits; output under provider terms; Status: not yet tested |
| [voice-isolation-api](ElevenLabs/voice-isolation-api.json) | Isolate voice from background noise and music | None (cloud) | none (ComfyUI core API nodes) | Model: ElevenLabs (API); VRAM (approx.): None; Licence: paid Comfy API credits; output under provider terms; Status: not yet tested |

## F5-TTS

Folder: [`F5-TTS/`](F5-TTS) — 5 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [speech-edit-tts-audio-suite](F5-TTS/speech-edit-tts-audio-suite.json) | Speech editor: replace words inside an existing recording | Auto-download to `models/TTS/` | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Model: F5-TTS; VRAM (approx.): ~4-6 GB; Licence: **F5 weights CC-BY-NC-4.0 (non-commercial)**; Status: not yet tested |
| [tts-audio-suite-srt-phoneme-normalizer](F5-TTS/tts-audio-suite-srt-phoneme-normalizer.json) | Character voices, SRT-timed speech and phoneme text normalizer | Auto-download (~1.2 GB per model) to `models/TTS/` | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Model: F5-TTS; VRAM (approx.): ~4-6 GB; Licence: **F5 weights CC-BY-NC-4.0 (non-commercial)**; Status: not yet tested |
| [tts-speak-like-a-local-translate](F5-TTS/tts-speak-like-a-local-translate.json) | Translate text, then speak it with a native-language F5 checkpoint | Language `.pt` + vocab to `models/checkpoints/F5-TTS/` (e.g. Hindi [SPRINGLab/F5-Hindi-24KHz](https://huggingface.co/SPRINGLab/F5-Hindi-24KHz)) | [ComfyUI-F5-TTS](https://github.com/niknah/ComfyUI-F5-TTS), [GF_translate](https://github.com/gorillaframeai/GF_translate), [rgthree-comfy](https://github.com/rgthree/rgthree-comfy) | Model: F5-TTS (language checkpoints); VRAM (approx.): ~3-6 GB; Licence: **Check each checkpoint; official F5 weights CC-BY-NC-4.0**; Status: not yet tested |
| [voice-clone-whisper-auto-transcript](F5-TTS/voice-clone-whisper-auto-transcript.json) | Voice clone; Whisper writes the reference transcript | As above, plus Whisper auto-download to `models/stt/whisper` | [ComfyUI-F5-TTS](https://github.com/niknah/ComfyUI-F5-TTS), [ComfyUI-Whisper](https://github.com/yuvraj108c/ComfyUI-Whisper) | Model: F5-TTS + Whisper; VRAM (approx.): ~6-10 GB; Licence: **F5 weights CC-BY-NC-4.0 (non-commercial)**; Status: not yet tested |
| [voice-clone](F5-TTS/voice-clone.json) | Voice clone from a reference clip and its transcript | Base F5/E2 auto-download ([SWivid/F5-TTS](https://huggingface.co/SWivid/F5-TTS)); extra `.pt` + vocab `.txt` to `models/checkpoints/F5-TTS/` | [ComfyUI-F5-TTS](https://github.com/niknah/ComfyUI-F5-TTS) | Model: F5-TTS / E2-TTS; VRAM (approx.): ~3-6 GB; Licence: **Weights CC-BY-NC-4.0 (non-commercial)**; pack MIT; Status: not yet tested |

## FireRedTTS

Folder: [`FireRedTTS/`](FireRedTTS) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-v3-all-in-one](FireRedTTS/tts-v3-all-in-one.json) | Voice clone, voice design, acoustic edit and semantic (word) edit of speech | [FireRedTeam/FireRedTTS3](https://huggingface.co/FireRedTeam/FireRedTTS3) (or bf16 / int8 repacks) to `models/fireredtts3/` | [FireRedTTS3-ComfyUI](https://github.com/Saganaki22/FireRedTTS3-ComfyUI) | Model: FireRedTTS3; VRAM (approx.): ~14 GB; Licence: Weights Apache-2.0; pack MIT; Status: not yet tested |

## Fish-Speech

Folder: [`Fish-Speech/`](Fish-Speech) — 9 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [stt-fish-audio-api](Fish-Speech/stt-fish-audio-api.json) | Speech to text | None (cloud) | none (ComfyUI core API nodes) | Model: Fish Audio (API); VRAM (approx.): None; Licence: paid Comfy API credits; output under provider terms; Status: not yet tested |
| [tts-dialogue-fish-audio-api-drama-3](Fish-Speech/tts-dialogue-fish-audio-api-drama-3.json) | Multi-character drama dialogue | None (cloud) | none (ComfyUI core API nodes) | Model: Fish Audio Drama 3 (API); VRAM (approx.): None; Licence: paid Comfy API credits; output under provider terms; Status: not yet tested |
| [tts-dialogue-s2-multi-speaker](Fish-Speech/tts-dialogue-s2-multi-speaker.json) | Multi-Speaker Dialogue TTS | — | ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use, comfyui-fish-audio-s2 | Status: not recorded |
| [tts-fish-audio-api-drama-3-directed](Fish-Speech/tts-fish-audio-api-drama-3-directed.json) | Directed performance with acting instructions | None (cloud) | none (ComfyUI core API nodes) | Model: Fish Audio Drama 3 (API); VRAM (approx.): None; Licence: paid Comfy API credits; output under provider terms; Status: not yet tested |
| [tts-fish-audio-api-s2](Fish-Speech/tts-fish-audio-api-s2.json) | Text to speech with voice selector | None (cloud) | none (ComfyUI core API nodes) | Model: Fish Audio S2 (API); VRAM (approx.): None; Licence: paid Comfy API credits; output under provider terms; Status: not yet tested |
| [tts-s2-pro-tts-audio-suite-srt-characters](Fish-Speech/tts-s2-pro-tts-audio-suite-srt-characters.json) | Multi-character voices and SRT-timed speech through the unified engine | S2-Pro to `models/TTS/fish_audio_s2_pro/` (BF16, FP8 or INT8/NF4 at load) | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Model: Fish Audio S2-Pro; VRAM (approx.): ~12-24 GB (less quantised); Licence: **Fish Audio Research License (non-commercial without a licence)**; Status: not yet tested |
| [tts-s2](Fish-Speech/tts-s2.json) | Text to Speech | — | ComfyUI-Easy-Use, comfyui-fish-audio-s2 | Status: not recorded |
| [voice-clone-fish-audio-api](Fish-Speech/voice-clone-fish-audio-api.json) | Instant voice clone, then speak | None (cloud) | none (ComfyUI core API nodes) | Model: Fish Audio (API); VRAM (approx.): None; Licence: paid Comfy API credits; output under provider terms; Status: not yet tested |
| [voice-clone-s2](Fish-Speech/voice-clone-s2.json) | Voice Clone TTS | — | ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use, comfyui-fish-audio-s2 | Status: not recorded |

## FunASR

Folder: [`FunASR/`](FunASR) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [subtitles-av-audio2subtitle-prompt-1](FunASR/subtitles-av-audio2subtitle-prompt-1.json) | Chinese audio to timestamped SRT with optional hot-word prompt | ModelScope `iic/speech_seaco_paraformer_large_asr_nat-zh-cn-16k-common-vocab8404-pytorch` and `iic/speech_fsmn_vad_zh-cn-16k-common-pytorch` to `models/ASR/FunASR/iic/`; `pip install funasr` | [ComfyUI-AV-FunASR](https://github.com/avenstack/ComfyUI-AV-FunASR), [ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) | Model: FunASR Paraformer-seaco + FSMN-VAD; VRAM (approx.): ~2-4 GB; Licence: FunASR model licence (attribution); **pack has no licence file**; Status: not yet tested |
| [subtitles-av-audio2subtitle-prompt-2](FunASR/subtitles-av-audio2subtitle-prompt-2.json) | Align a supplied Chinese text to the audio for subtitles | As above plus `iic/speech_timestamp_prediction-v1-16k-offline` | [ComfyUI-AV-FunASR](https://github.com/avenstack/ComfyUI-AV-FunASR), [ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) | Model: FunASR + speech-timestamp prediction; VRAM (approx.): ~2-4 GB; Licence: As above; Status: not yet tested |

## GPT-SoVITS

Folder: [`GPT-SoVITS/`](GPT-SoVITS) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-v2](GPT-SoVITS/tts-v2.json) | Few-shot TTS from a reference clip and its text | [lj1995/GPT-SoVITS](https://huggingface.co/lj1995/GPT-SoVITS) into the pack's model folder; needs ffmpeg; pack from 2024, v2 only | [GSTTS-ComfyUI](https://github.com/AIFSH/GSTTS-ComfyUI) | Model: GPT-SoVITS v2; VRAM (approx.): ~4 GB; Licence: Weights MIT; pack MIT; Status: not yet tested |
| [voice-training-v2-finetune](GPT-SoVITS/voice-training-v2-finetune.json) | Dataset chain (ASR, slicing, labelling) and fine-tuning of your own voice model | As above | [GSTTS-ComfyUI](https://github.com/AIFSH/GSTTS-ComfyUI) | Model: GPT-SoVITS v2; VRAM (approx.): ~8 GB+; Licence: Weights MIT; pack MIT; Status: not yet tested |

## Hibiki

Folder: [`Hibiki/`](Hibiki) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [speech-translation-speech2speech](Hibiki/speech-translation-speech2speech.json) | Simultaneous French-to-English speech-to-speech translation | [kyutai/hibiki-2b-pytorch-bf16](https://huggingface.co/kyutai/hibiki-2b-pytorch-bf16) (auto-download to the Hugging Face cache); `pip install` the pack requirements (moshi) | [ComfyUI-hibiki](https://github.com/jhj0517/ComfyUI-hibiki) | Model: Hibiki 2B (Kyutai); VRAM (approx.): ~8 GB (estimate); Licence: Weights CC-BY-4.0 per Kyutai; **pack has no licence file**; Status: not yet tested |

## Higgs-Audio

Folder: [`Higgs-Audio/`](Higgs-Audio) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-v3-audio-suite](Higgs-Audio/tts-v3-audio-suite.json) | Inline emotion, style, prosody and sound-effect tags plus SRT timing | Auto-download to `models/TTS/` (~8 GB) | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Model: Higgs Audio v3; VRAM (approx.): ~8 GB; Licence: **Weights non-commercial**; pack MIT; Status: not yet tested |
| [voice-clone-v3-multispeaker](Higgs-Audio/voice-clone-v3-multispeaker.json) | Generation, voice clone and multi-speaker speech; Whisper transcribes the reference | [bosonai/higgs-audio-v3-tts-4b](https://huggingface.co/bosonai/higgs-audio-v3-tts-4b) to `models/higgsv3tts/higgs-audio-v3-tts-4b/` | [Higgs_v3-TTS-ComfyUI](https://github.com/Saganaki22/Higgs_v3-TTS-ComfyUI) | Model: Higgs Audio v3 (4B, Boson AI); VRAM (approx.): ~11 GB; Licence: **Weights: Boson research / non-commercial licence**; pack MIT; Status: not yet tested |

## IndexTTS

Folder: [`IndexTTS/`](IndexTTS) — 7 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-2-audio-suite-emotion-srt](IndexTTS/tts-2-audio-suite-emotion-srt.json) | Emotion-controlled character voices and SRT timing (maintained pack) | Auto-download to `models/TTS/` | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Model: IndexTTS-2; VRAM (approx.): ~8-12 GB; Licence: **bilibili IndexTTS licence (check commercial terms)**; Status: not yet tested |
| [tts-2-emotion-control](IndexTTS/tts-2-emotion-control.json) | Voice clone with emotion from audio, text or an emotion vector | [IndexTeam/IndexTTS-2](https://huggingface.co/IndexTeam/IndexTTS-2) into the pack's `checkpoints/` | [ComfyUI-IndexTTS2](https://github.com/snicolast/ComfyUI-IndexTTS2) (archived) | Model: IndexTTS-2 (bilibili); VRAM (approx.): ~8-12 GB; Licence: **bilibili IndexTTS licence (check commercial terms)**; Status: not yet tested |
| [tts-2.5-multilingual](IndexTTS/tts-2.5-multilingual.json) | Multilingual voice clone with emotion, speed and pronunciation control | [IndexTeam/IndexTTS-2.5](https://huggingface.co/IndexTeam/IndexTTS-2.5) to `models/TTS/IndexTTS-2.5/`; the loader field holds a placeholder, pick the folder | [Comfyui-indextts25-xzg](https://github.com/xiaozhuguang/Comfyui-indextts25-xzg) | Model: IndexTTS 2.5 (zh, en, ja, es, ar); VRAM (approx.): ~8 GB+; Licence: **Bilibili IndexTTS licence (check commercial terms)**; Status: not yet tested |
| [tts-dialogue-1.5](IndexTTS/tts-dialogue-1.5.json) | Two-person dialogue with cloned voices | As above | [ComfyUI_IndexTTS](https://github.com/billwuhao/ComfyUI_IndexTTS) | Model: IndexTTS 1.5; VRAM (approx.): ~6-8 GB; Licence: Weights Apache-2.0; pack Apache-2.0; Status: not yet tested |
| [tts-dialogue-2.5](IndexTTS/tts-dialogue-2.5.json) | Multi-speaker dialogue with saved speaker packs | IndexTTS-2.5 to `models/TTS/IndexTTS-2.5/` | [ComfyUI-IndexTTS-2.5](https://github.com/mailzwj/ComfyUI-IndexTTS-2.5), [ComfyUI-Custom-Scripts](https://github.com/pythongosssss/ComfyUI-Custom-Scripts) | Model: IndexTTS 2.5; VRAM (approx.): ~8 GB+; Licence: **Bilibili IndexTTS licence**; pack Apache-2.0; Status: not yet tested |
| [voice-clone-1.5](IndexTTS/voice-clone-1.5.json) | Voice clone from a reference clip | [IndexTeam/IndexTTS-1.5](https://huggingface.co/IndexTeam/IndexTTS-1.5) (`gpt.pth`, `bigvgan_generator.pth`, `bpe.model`); folder per pack README; text normalisation needs `pynini` | [ComfyUI_IndexTTS](https://github.com/billwuhao/ComfyUI_IndexTTS) | Model: IndexTTS 1.5; VRAM (approx.): ~6-8 GB; Licence: Weights Apache-2.0 (1.0 / 1.5); pack Apache-2.0; sample names Chinese; Status: not yet tested |
| [voice-clone-2.5-basic](IndexTTS/voice-clone-2.5-basic.json) | Basic voice cloning | IndexTTS-2.5 to `models/IndexTTS2.5/` | [BSAI_ComfyUI_IndexTTS-2.5](https://github.com/xm6018924/BSAI_ComfyUI_IndexTTS-2.5) | Model: IndexTTS 2.5; VRAM (approx.): ~4-10 GB; Licence: **Bilibili IndexTTS licence**; pack licence not declared; Status: not yet tested |

## Kani-TTS

Folder: [`Kani-TTS/`](Kani-TTS) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts](Kani-TTS/tts.json) | Compact LM-based TTS (Kani-TTS-2 is not confirmed as selectable) | [nineninesix](https://huggingface.co/nineninesix) kani-tts-370m / 450m (auto-download) | [ComfyUI-KaniTTS](https://github.com/wildminder/ComfyUI-KaniTTS) | Model: Kani-TTS (370M / 450M); VRAM (approx.): small, not stated; Licence: Weights: Hugging Face tag "other", check the card; pack Apache-2.0; Status: not yet tested |

## Kitten-TTS

Folder: [`Kitten-TTS/`](Kitten-TTS) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-saganaki](Kitten-TTS/tts-saganaki.json) | Tiny CPU-friendly ONNX TTS | [KittenML/kitten-tts](https://huggingface.co/KittenML) nano / micro / mini 0.8 (auto-download) | [ComfyUI-KittenTTS](https://github.com/Saganaki22/ComfyUI-KittenTTS) | Model: KittenTTS (15-80M); VRAM (approx.): CPU, under 1 GB; Licence: Weights Apache-2.0; pack Apache-2.0; Status: not yet tested |

## Kokoro

Folder: [`Kokoro/`](Kokoro) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-82m](Kokoro/tts-82m.json) | Text to speech with preset voices and voice blending | [hexgrad/Kokoro-82M](https://huggingface.co/hexgrad/Kokoro-82M) ONNX, handled by the pack | [comfyui-kokoro](https://github.com/stavsap/comfyui-kokoro) | Model: Kokoro 82M (ONNX); VRAM (approx.): Under 1 GB; runs on CPU; Licence: Model Apache-2.0 (commercial OK); pack Apache-2.0; Status: not yet tested |

## Kyutai

Folder: [`Kyutai/`](Kyutai) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts](Kyutai/tts.json) | Streaming-style TTS with Kyutai voices. Edit the author's `C:\` model folder widget to `models/checkpoints/KyutaiTTS` | [kyutai/tts-1.6b-en_fr](https://huggingface.co/kyutai/tts-1.6b-en_fr) + [kyutai/tts-voices](https://huggingface.co/kyutai/tts-voices) to `models/checkpoints/KyutaiTTS/` | [ComfyUI-KyutaiTTS](https://github.com/BobRandomNumber/ComfyUI-KyutaiTTS) | Model: Kyutai TTS 1.6B (en, fr); VRAM (approx.): ~6-8 GB (estimate); Licence: Weights CC-BY-4.0; pack MIT; pack last updated 2025-07; Status: not yet tested |

## MARS5

Folder: [`MARS5/`](MARS5) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [voice-clone-uvr5](MARS5/voice-clone-uvr5.json) | Voice clone with prosody conditioning; the `UVR5_Node` comes from a separate AIFSH pack (old, 2024) | [Camb-ai/MARS5-TTS](https://huggingface.co/CAMB-AI/MARS5-TTS) | [ComfyUI-MARS5-TTS](https://github.com/AIFSH/ComfyUI-MARS5-TTS) | Model: MARS5 (CAMB.AI); VRAM (approx.): large (about 20 GB claimed upstream); Licence: **Weights and pack AGPL-3.0**; Status: not yet tested |

## MaskGCT

Folder: [`MaskGCT/`](MaskGCT) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts](MaskGCT/tts.json) | Zero-shot clone with masked codec generation; edit the author's `D:\` sample folder in the Load Audio Path node | [amphion/MaskGCT](https://huggingface.co/amphion/MaskGCT), w2v-bert-2.0, Whisper large-v3; the pack's own `models/`; also needs Crystools and a pack providing `string-to-array` | [ComfyUI_MaskGCT](https://github.com/807502278/ComfyUI_MaskGCT) | Model: MaskGCT (Amphion); VRAM (approx.): ~10 GB+ (estimate); Licence: **Weights CC-BY-NC-4.0 (non-commercial)**; pack licence not declared; Status: not yet tested |

## Maya

Folder: [`Maya/`](Maya) — 4 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-v1](Maya/tts-v1.json) | Expressive TTS with emotion tags and a natural-language voice description | [maya-research/maya1](https://huggingface.co/maya-research/maya1) + SNAC codec to `models/maya1-TTS/`; 4/8-bit needs bitsandbytes | [ComfyUI-Maya1_TTS](https://github.com/Saganaki22/ComfyUI-Maya1_TTS) | Model: Maya1 (Maya Research); VRAM (approx.): ~6 GB (4-bit) to ~16 GB (bf16); Licence: Weights Apache-2.0; pack Apache-2.0; Status: not yet tested |
| [tts-v3-indic-builtin-voice](Maya/tts-v3-indic-builtin-voice.json) | Streaming Indic TTS with 20 built-in voices | [maya-research/maya2-native](https://huggingface.co/maya-research/maya2-native) (auto-download, ~5.6 GB) to `models/maya3/hf`; needs Linux, NVIDIA, CUDA 12.8 driver; installs an isolated transformers 5 runtime on first use | [ComfyUI-maya2-native](https://github.com/Praveenhalder/ComfyUI-maya2-native) | Model: Maya3 (maya2-native), 11 Indian languages + English; VRAM (approx.): ~8 GB; Licence: Weights Apache-2.0; pack Apache-2.0; Status: not yet tested |
| [voice-clone-v3-indic-auto-transcribe](Maya/voice-clone-v3-indic-auto-transcribe.json) | Whisper transcribes the reference clip, then Maya3 clones the voice | As above | [ComfyUI-maya2-native](https://github.com/Praveenhalder/ComfyUI-maya2-native) | Model: Maya3 + Whisper; VRAM (approx.): ~8 GB; Licence: Weights Apache-2.0; pack Apache-2.0; Status: not yet tested |
| [voice-clone-v3-indic](Maya/voice-clone-v3-indic.json) | Zero-shot voice clone in Hindi and other Indian languages | As above | [ComfyUI-maya2-native](https://github.com/Praveenhalder/ComfyUI-maya2-native) | Model: Maya3 (maya2-native); VRAM (approx.): ~8 GB; Licence: Weights Apache-2.0; pack Apache-2.0; Status: not yet tested |

## Mega-ASR

Folder: [`Mega-ASR/`](Mega-ASR) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [stt](Mega-ASR/stt.json) | Transcribe audio | [zhifeixie/Mega-ASR](https://huggingface.co/zhifeixie/Mega-ASR) to `models/Mega-ASR` | [ComfyUI-Mega-ASR](https://github.com/starsFriday/ComfyUI-Mega-ASR), [ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) | Model: Mega-ASR (Qwen3-ASR derivative); VRAM (approx.): ~4-6 GB; Licence: Check model card; pack Apache-2.0; Status: not yet tested |

## MeloTTS

Folder: [`MeloTTS/`](MeloTTS) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-zetalvx](MeloTTS/tts-zetalvx.json) | Fast multi-accent TTS; the graph's `ZetalvxIntToString` node was not found in the pack source and may show red | [myshell-ai/MeloTTS](https://huggingface.co/myshell-ai) models (auto-download) | [Zetalvx-ComfyUI-MeloTTS](https://github.com/ZETALVX/Zetalvx-ComfyUI-MeloTTS) | Model: MeloTTS (MyShell); VRAM (approx.): CPU capable; Licence: Weights MIT; **pack has no licence file**; Status: not yet tested |

## MisoTTS

Folder: [`MisoTTS/`](MisoTTS) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts](MisoTTS/tts.json) | Conversational TTS with voice clone; Whisper transcribes the reference | [MisoLabs/MisoTTS](https://huggingface.co/MisoLabs/MisoTTS) (or drbaph BF16) to `models/misotts/`; kyutai/mimi codec | [MisoTTS-ComfyUI](https://github.com/Saganaki22/MisoTTS-ComfyUI) | Model: MisoTTS 8B (Sesame-style CSM); VRAM (approx.): high (8B), not stated; Licence: Weights: Hugging Face tag "other", check the card; pack MIT; Status: not yet tested |

## MOSS

Folder: [`MOSS/`](MOSS) — 6 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [stt-diarize-basic](MOSS/stt-diarize-basic.json) | Multi-speaker transcription with speaker labels, hotwords and SRT export | Download script in the pack to `models/moss_transcribe_diarize` | [comfyui-MOSS-Transcribe-Diarize-T8](https://github.com/T8mars/comfyui-MOSS-Transcribe-Diarize-T8) | Model: MOSS-Transcribe-Diarize (0.9B class); VRAM (approx.): ~4 GB short clips, 12 GB+ recommended; Licence: Model licence not confirmed; pack Apache-2.0; Status: not yet tested |
| [stt-diarize-long-audio](MOSS/stt-diarize-long-audio.json) | Chunked long-audio run with a quality gate and diagnostics | As above | [comfyui-MOSS-Transcribe-Diarize-T8](https://github.com/T8mars/comfyui-MOSS-Transcribe-Diarize-T8) | Model: MOSS-Transcribe-Diarize; VRAM (approx.): ~5-12 GB (5-10 min clips); Licence: Model licence not confirmed; pack Apache-2.0; Status: not yet tested |
| [tts-dialogue-ttsd](MOSS/tts-dialogue-ttsd.json) | Multi-speaker dialogue synthesis with a split codec loader | MOSS-TTSD-v1.0 + MOSS-Audio-Tokenizer from [OpenMOSS-Team](https://huggingface.co/OpenMOSS-Team) to `models/moss_ttsd/`; Python 3.12 and flash-attn per its README | [ComfyUI-kaola-moss-tts](https://github.com/kana112233/ComfyUI-kaola-moss-tts) | Model: MOSS-TTSD v1.0; VRAM (approx.): ~16-18 GB; Licence: Weights Apache-2.0; pack Apache-2.0; Status: not yet tested |
| [tts-dialogue-v15](MOSS/tts-dialogue-v15.json) | Single-voice speech and multi-speaker dialogue | [OpenMOSS-Team/MOSS-TTS](https://huggingface.co/OpenMOSS-Team/MOSS-TTS) to `models/moss_tts/` | [comfyui-moss-tts](https://github.com/wonderingearth/comfyui-moss-tts) | Model: MOSS-TTS v1.5 (8B); VRAM (approx.): 16 GB+; Licence: Weights Apache-2.0; pack licence not declared; sample file names are Chinese; Status: not yet tested |
| [voice-clone-v15-continue](MOSS/voice-clone-v15-continue.json) | Speech generation, zero-shot clone and speech continuation; Whisper transcribes the reference | Auto-download to `models/mosstts/` (includes MOSS-Audio-Tokenizer-v2) | [Moss_TTS-ComfyUI](https://github.com/Saganaki22/Moss_TTS-ComfyUI) | Model: MOSS-TTS Local Transformer v1.5; VRAM (approx.): ~6 GB; Licence: Weights Apache-2.0; pack licence not declared; Status: not yet tested |
| [voice-design-voicegenerator](MOSS/voice-design-voicegenerator.json) | Design a voice from a text description, then speak dialogue with it | MOSS-VoiceGenerator to `models/moss_ttsd/MOSS-VoiceGenerator`, plus the TTSD files above | [ComfyUI-kaola-moss-tts](https://github.com/kana112233/ComfyUI-kaola-moss-tts) | Model: MOSS-VoiceGenerator 1.7B + MOSS-TTSD; VRAM (approx.): ~6-18 GB; Licence: Weights Apache-2.0; pack Apache-2.0; Status: not yet tested |

## Nemotron

Folder: [`Nemotron/`](Nemotron) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [stt-live-microphone](Nemotron/stt-live-microphone.json) | Live microphone transcription through the server | As above | [comfyui_nemotron_asr](https://github.com/Rakeshcool/comfyui_nemotron_asr) | Model: Nemotron ASR streaming; VRAM (approx.): On the server; Licence: NVIDIA Open Model License (check card); Status: not yet tested |
| [stt-server](Nemotron/stt-server.json) | Send audio to a local NeMo-Speech.cpp server and get text | None in ComfyUI: run a NeMo-Speech.cpp server at `http://127.0.0.1:8080` | [comfyui_nemotron_asr](https://github.com/Rakeshcool/comfyui_nemotron_asr) | Model: Nemotron ASR streaming; VRAM (approx.): On the server; Licence: NVIDIA Open Model License (check card); pack MIT; Status: not yet tested |

## NeuTTS

Folder: [`NeuTTS/`](NeuTTS) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [voice-clone](NeuTTS/voice-clone.json) | Instant voice clone from a reference clip and transcript | [neuphonic/neutts-air](https://huggingface.co/neuphonic/neutts-air) (GGUF or torch) + NeuCodec; needs `espeak` | [ComfyUI-Neutts](https://github.com/AsifOnWeb3/ComfyUI-Neutts) | Model: NeuTTS Air (Neuphonic); VRAM (approx.): CPU / low; Licence: Weights Apache-2.0; **pack has no licence file**; Status: not yet tested |

## OmniVoice

Folder: [`OmniVoice/`](OmniVoice) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-all-modes](OmniVoice/tts-all-modes.json) | Zero-shot clone, voice design, multi-speaker and long-form TTS; optional Whisper transcript of the reference | [k2-fsa/OmniVoice](https://huggingface.co/k2-fsa/OmniVoice) (auto-download); Whisper large-v3-turbo auto-download | [ComfyUI-OmniVoice-TTS](https://github.com/Saganaki22/ComfyUI-OmniVoice-TTS) | Model: OmniVoice (k2-fsa, 600+ languages); VRAM (approx.): ~4-12 GB by mode; Licence: Pack Apache-2.0; weights licence not confirmed; Status: not yet tested |
| [tts-audio-suite](OmniVoice/tts-audio-suite.json) | OmniVoice through the unified nodes: SRT-timed speech, voice-design instruction builder, non-verbal tags | Auto-download to `models/TTS/` (~3.7 GB) | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Model: OmniVoice; VRAM (approx.): ~4 GB; Licence: Pack MIT; weights licence not confirmed; Status: not yet tested |

## OpenVoice

Folder: [`OpenVoice/`](OpenVoice) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-and-voice-conversion](OpenVoice/tts-and-voice-conversion.json) | Text to speech in a reference voice, and speech-to-speech voice conversion | Auto-download. V2 needs `pip install git+https://github.com/myshell-ai/MeloTTS.git` and `python -m unidic download` | [ComfyUI_OpenVoice](https://github.com/hay86/ComfyUI_OpenVoice), [ComfyUI_AceNodes](https://github.com/hay86/ComfyUI_AceNodes) | Model: OpenVoice (V1, V2 with MeloTTS); VRAM (approx.): ~2-4 GB; Licence: Model MIT (commercial OK); pack MIT; pack last updated 2024-07; Status: not yet tested |

## Orpheus

Folder: [`Orpheus/`](Orpheus) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts](Orpheus/tts.json) | Expressive TTS with emotion tags | [orpheus-3b-f16-safetensors](https://huggingface.co/AustinMroz/orpheus-3b-f16-safetensors) + [snac-24khz-ST](https://huggingface.co/Annuvin/snac-24khz-ST); folders per pack README | [ComfyUI-Orpheus (AustinMroz)](https://github.com/AustinMroz/ComfyUI-Orpheus) | Model: Orpheus 3B (Canopy Labs); VRAM (approx.): ~8 GB; Licence: Orpheus Apache-2.0; pack GPL-3.0; Status: not yet tested |
| [voice-clone](Orpheus/voice-clone.json) | Voice clone from a single reference segment | As above | [ComfyUI-Orpheus (AustinMroz)](https://github.com/AustinMroz/ComfyUI-Orpheus), [ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite) | Model: Orpheus 3B; VRAM (approx.): ~8 GB; Licence: Orpheus Apache-2.0; pack GPL-3.0; Status: not yet tested |

## Parakeet

Folder: [`Parakeet/`](Parakeet) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [subtitles-tdt-0.6b-v2-with-kokoro](Parakeet/subtitles-tdt-0.6b-v2-with-kokoro.json) | Kokoro speaks text, Parakeet transcribes it with word timestamps and subtitles a video | [parakeet-tdt-0.6b-v2.nemo](https://huggingface.co/nvidia/parakeet-tdt-0.6b-v2) to `models/TTS`. v3 is not supported | [ComfyUI_parakeet-tdt](https://github.com/billwuhao/ComfyUI_parakeet-tdt), [ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite), [ComfyUI_KokoroTTS_MW](https://github.com/billwuhao/ComfyUI_KokoroTTS_MW), [ComfyUI_AudioTools](https://github.com/billwuhao/ComfyUI_AudioTools) | Model: Parakeet-TDT 0.6B v2 (English) + Kokoro; VRAM (approx.): ~2-4 GB; Licence: Model CC-BY-4.0 (commercial OK with attribution); pack Apache-2.0; Status: not yet tested |

## Parler-TTS

Folder: [`Parler-TTS/`](Parler-TTS) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-described-voice](Parler-TTS/tts-described-voice.json) | Text to speech with the voice described in words (gender, pitch, pace, room) | [parler-tts/parler-tts-mini-v1](https://huggingface.co/parler-tts/parler-tts-mini-v1) `model.safetensors` renamed to `parler-tts-mini-v1.safetensors` in `models/clip/` | [ComfyUI_ParlerTTS](https://github.com/smthemex/ComfyUI_ParlerTTS) | Model: Parler-TTS mini v1 / large v1; VRAM (approx.): ~2-4 GB (mini); Licence: Model Apache-2.0 (commercial OK); pack Apache-2.0; Status: not yet tested |

## Qwen3-ASR

Folder: [`Qwen3-ASR/`](Qwen3-ASR) — 5 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [forced-alignment-word-timestamps](Qwen3-ASR/forced-alignment-word-timestamps.json) | Forced alignment: word-level timestamps for a transcript | `qwen3-asr-1.7B.safetensors` / `-0.6B` and `qwen3-forcedaligner-0.6B.safetensors` to `models/qwen3asr/` | [ComfyUI-Qwen3ASR](https://github.com/Aero-Ex/ComfyUI-Qwen3ASR) | Model: Qwen3-ASR + Qwen3-ForcedAligner 0.6B; VRAM (approx.): ~3-6 GB; Licence: Model Apache-2.0 (commercial OK); pack MIT. Do not install together with DarioFT/ComfyUI-Qwen3-ASR; Status: not yet tested |
| [stt-0.6b](Qwen3-ASR/stt-0.6b.json) | Transcribe audio (52 languages incl. Hindi) with optional timestamps | Auto-download `Qwen/Qwen3-ASR-0.6B-hf` + `Qwen/Qwen3-ForcedAligner-0.6B-hf` to `models/Qwen3-ASR/` | [ComfyUI-QwenASR](https://github.com/1038lab/ComfyUI-QwenASR) | Model: Qwen3-ASR 0.6B + Forced Aligner; VRAM (approx.): ~2-4 GB; Licence: Model Apache-2.0 (commercial OK); pack GPL-3.0; Status: not yet tested |
| [stt-1.7b](Qwen3-ASR/stt-1.7b.json) | Transcribe audio with the larger model | [Qwen/Qwen3-ASR-1.7B](https://huggingface.co/Qwen/Qwen3-ASR-1.7B) to `models/Qwen3-ASR/` | [ComfyUI-Qwen3-ASR](https://github.com/DarioFT/ComfyUI-Qwen3-ASR) | Model: Qwen3-ASR 1.7B; VRAM (approx.): ~4-6 GB; Licence: Model Apache-2.0 (commercial OK); pack Apache-2.0. Do not install together with Aero-Ex/ComfyUI-Qwen3ASR (same node names); Status: not yet tested |
| [stt-with-forced-aligner-config](Qwen3-ASR/stt-with-forced-aligner-config.json) | Transcribe with word timestamps (bf16/fp16, FlashAttention2) | Manual download to `models/diffusion_models/Qwen3-ASR/<name>/` | [ComfyUI-Qwen3-ASR](https://github.com/kaushiknishchay/ComfyUI-Qwen3-ASR) | Model: Qwen3-ASR 0.6B / 1.7B + Forced Aligner; VRAM (approx.): ~2-6 GB; Licence: Model Apache-2.0 (commercial OK); pack MIT; Status: not yet tested |
| [subtitles-0.6b](Qwen3-ASR/subtitles-0.6b.json) | Transcribe to timestamped subtitles | As above | [ComfyUI-QwenASR](https://github.com/1038lab/ComfyUI-QwenASR) | Model: Qwen3-ASR 0.6B + Forced Aligner; VRAM (approx.): ~2-4 GB; Licence: Model Apache-2.0 (commercial OK); pack GPL-3.0; Status: not yet tested |

## Qwen3-TTS

Folder: [`Qwen3-TTS/`](Qwen3-TTS) — 11 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-custom-voice](Qwen3-TTS/tts-custom-voice.json) | Custom Voice | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use | Status: not recorded |
| [voice-clone-1038lab-with-asr](Qwen3-TTS/voice-clone-1038lab-with-asr.json) | Voice clone; reference transcript filled by Qwen3-ASR | [Qwen/Qwen3-TTS-12Hz-1.7B-Base](https://huggingface.co/Qwen/Qwen3-TTS-12Hz-1.7B-Base) or 0.6B-Base + Tokenizer-12Hz to `models/TTS/Qwen3-TTS/<name>/` | [ComfyUI-QwenTTS](https://github.com/1038lab/ComfyUI-QwenTTS) | Model: Qwen3-TTS 0.6B / 1.7B Base + Qwen3-ASR; VRAM (approx.): ~4-8 GB (1.7B), less for 0.6B; Licence: Model Apache-2.0 (commercial OK); pack GPL-3.0; Status: not yet tested |
| [voice-clone-load-saved-voice](Qwen3-TTS/voice-clone-load-saved-voice.json) | Voice Clone + Load Saved Voice | — | ComfyUI-Qwen-TTS, ComfyUI-Easy-Use | Status: not recorded |
| [voice-clone-save-voice](Qwen3-TTS/voice-clone-save-voice.json) | Voice Clone + Save Voice | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use | Status: not recorded |
| [voice-clone-saved-multi-voice-dialogue](Qwen3-TTS/voice-clone-saved-multi-voice-dialogue.json) | Voice Clone + Saved Multi Voice + Dialogue | — | ComfyUI-Qwen-TTS, ComfyUI-Easy-Use | Status: not recorded |
| [voice-clone](Qwen3-TTS/voice-clone.json) | Voice Clone | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use | Status: not recorded |
| [voice-design-1038lab-create-your-voice](Qwen3-TTS/voice-design-1038lab-create-your-voice.json) | Record your voice, transcribe it and save it to a voices library | Qwen3-TTS weights to `models/TTS/Qwen3-TTS/<name>/` | [ComfyUI-QwenTTS](https://github.com/1038lab/ComfyUI-QwenTTS) | Model: Qwen3-TTS + Whisper STT; VRAM (approx.): ~4-8 GB; Licence: Model Apache-2.0 (commercial OK); pack GPL-3.0; Status: not yet tested |
| [voice-design-dialogue](Qwen3-TTS/voice-design-dialogue.json) | Voice Design + Dialogue | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use | Status: not recorded |
| [voice-design-save-voice](Qwen3-TTS/voice-design-save-voice.json) | Voice Design + Save Voice | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use | Status: not recorded |
| [voice-design-tts-audio-suite-asr-srt](Qwen3-TTS/voice-design-tts-audio-suite-asr-srt.json) | Voice design, character voices, ASR transcription and SRT-timed speech | Auto-download to `models/TTS/` (3-6 GB) | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Model: Qwen3-TTS + Qwen3-ASR; VRAM (approx.): ~6-10 GB; Licence: Model Apache-2.0 (commercial OK); pack licence unclear, check repo; Status: not yet tested |
| [voice-design](Qwen3-TTS/voice-design.json) | Voice Design | — | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use | Status: not recorded |

## RVC

Folder: [`RVC/`](RVC) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [voice-conversion-chatterbox-tts-audio-suite](RVC/voice-conversion-chatterbox-tts-audio-suite.json) | Unified voice changer: RVC or Chatterbox conversion with character voices | Auto-download to `models/TTS/`; RVC voice models of your own | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Model: RVC + Chatterbox VC; VRAM (approx.): ~6-8 GB; Licence: Pack MIT; check each voice model; Status: not yet tested |
| [voice-conversion-native](RVC/voice-conversion-native.json) | Speech-to-speech voice conversion with your own RVC voice model and index | [Aero-Ex/ComfyUI-RVC](https://huggingface.co/Aero-Ex/ComfyUI-RVC) (hubert, rmvpe) plus a voice `.pth` of your own | [ComfyUI-RVC (Aero-Ex)](https://github.com/Aero-Ex/ComfyUI-RVC) | Model: RVC (Retrieval-based Voice Conversion); VRAM (approx.): low; Licence: Voice models carry their own licence; **pack has no licence file**; Status: not yet tested |
| [voice-training-tts-audio-suite](RVC/voice-training-tts-audio-suite.json) | Prepare a dataset, train an RVC voice model and test the conversion | Auto-download to `models/TTS/` | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Model: RVC; VRAM (approx.): ~8 GB+; Licence: Pack MIT; Status: not yet tested |

## Seed-VC

Folder: [`Seed-VC/`](Seed-VC) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [voice-conversion-billwuhao](Seed-VC/voice-conversion-billwuhao.json) | Zero-shot voice conversion for speech or singing | [Plachta/Seed-VC](https://huggingface.co/Plachta/Seed-VC), campplus, rmvpe, bigvgan_v2 | [ComfyUI_Seed-VC](https://github.com/billwuhao/ComfyUI_Seed-VC) | Model: Seed-VC; VRAM (approx.): ~4-8 GB (estimate); Licence: Pack Apache-2.0; **Seed-VC weights GPL-3.0**; Status: not yet tested |
| [voice-conversion-swap-1](Seed-VC/voice-conversion-swap-1.json) | One-voice swap of an input recording | Seed-VC (auto-download) | [comfyui-seedvc-voice-swap](https://github.com/rasmont/comfyui-seedvc-voice-swap) | Model: Seed-VC; VRAM (approx.): about 1.5 GB peak (pack README); Licence: **GPL-3.0**; Status: not yet tested |

## SenseVoice

Folder: [`SenseVoice/`](SenseVoice) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [stt-small-and-cosyvoice](SenseVoice/stt-small-and-cosyvoice.json) | Speech recognition with language, emotion and event tags, plus CosyVoice TTS | Auto-download | [ComfyUI-FunAudioLLM](https://github.com/SpenserCai/ComfyUI-FunAudioLLM), [ComfyUI-Custom-Scripts](https://github.com/pythongosssss/ComfyUI-Custom-Scripts), [was-node-suite-comfyui](https://github.com/WASasquatch/was-node-suite-comfyui) | Model: SenseVoiceSmall + CosyVoice 300M; VRAM (approx.): ~4-8 GB; Licence: **FunASR model licence (custom; check commercial terms)**; pack has no licence file, last updated 2024-11; Status: not yet tested |

## Sesame-CSM

Folder: [`Sesame-CSM/`](Sesame-CSM) — 4 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-1b](Sesame-CSM/tts-1b.json) | Conversational text to speech | [sesame/csm-1b](https://huggingface.co/sesame/csm-1b) `ckpt.pt` to `models/sesame/`; Llama-3.2-1B tokenizer to `models/sesame_tokenizer/` | [ComfyUI-CSM-Nodes](https://github.com/thezveroboy/ComfyUI-CSM-Nodes), [QualityOfLifeSuit_Omar92](https://github.com/omar92/ComfyUI-QualityOfLifeSuit_Omar92) | Model: Sesame CSM-1B; VRAM (approx.): ~5-8 GB; Licence: Model Apache-2.0 (commercial OK) + Llama 3.2 licence for the tokenizer; pack Apache-2.0; Status: not yet tested |
| [tts-dialogue-1b-saved-speakers](Sesame-CSM/tts-dialogue-1b-saved-speakers.json) | Dialogue with saved speakers | As above | [ComfyUI_CSM](https://github.com/billwuhao/ComfyUI_CSM) | Model: Sesame CSM-1B; VRAM (approx.): ~5-8 GB; Licence: Model Apache-2.0 + Llama 3.2 licence; Status: not yet tested |
| [voice-clone-1b-context](Sesame-CSM/voice-clone-1b-context.json) | Voice clone from context clips with transcripts | As above | [ComfyUI-CSM-Nodes](https://github.com/thezveroboy/ComfyUI-CSM-Nodes), [QualityOfLifeSuit_Omar92](https://github.com/omar92/ComfyUI-QualityOfLifeSuit_Omar92) | Model: Sesame CSM-1B; VRAM (approx.): ~5-8 GB; Licence: Model Apache-2.0 + Llama 3.2 licence; Status: not yet tested |
| [voice-clone-1b-dialogue](Sesame-CSM/voice-clone-1b-dialogue.json) | Two-speaker dialogue cloned from reference clips | csm-1b to `models/TTS/csm-1b`; Mimi tokenizer ([kyutai/moshiko-pytorch-bf16](https://huggingface.co/kyutai/moshiko-pytorch-bf16)) to `models/TTS/moshiko-pytorch-bf16`; Llama-3.2-1B to `models/LLM/Llama-3.2-1B` | [ComfyUI_CSM](https://github.com/billwuhao/ComfyUI_CSM) | Model: Sesame CSM-1B; VRAM (approx.): ~5-8 GB; Licence: Model Apache-2.0 + Llama 3.2 licence; pack Apache-2.0; Status: not yet tested |

## Spark-TTS

Folder: [`Spark-TTS/`](Spark-TTS) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [voice-clone-create](Spark-TTS/voice-clone-create.json) | Voice creator (gender, pitch, speed), voice clone and advanced clone | [SparkAudio/Spark-TTS-0.5B](https://huggingface.co/SparkAudio/Spark-TTS-0.5B) to `models/TTS/SparkTTS/` | [ComfyUI-SparkTTS](https://github.com/1038lab/ComfyUI-SparkTTS) | Model: Spark-TTS 0.5B; VRAM (approx.): ~4 GB; Licence: **Weights CC-BY-NC-SA-4.0 (non-commercial)**; pack GPL-3.0; Status: not yet tested |

## Step-Audio

Folder: [`Step-Audio/`](Step-Audio) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [speech-edit-editx](Step-Audio/speech-edit-editx.json) | Edit existing speech: emotion, style, speed and paralinguistic sounds | As above | [ComfyUI-Step_Audio_EditX_TTS](https://github.com/Saganaki22/ComfyUI-Step_Audio_EditX_TTS) | Model: Step-Audio-EditX; VRAM (approx.): ~16 GB (estimate); Licence: Weights licence not confirmed; pack Apache-2.0; Status: not yet tested |
| [voice-clone-editx](Step-Audio/voice-clone-editx.json) | Zero-shot voice clone | [stepfun-ai/Step-Audio-EditX](https://huggingface.co/stepfun-ai/Step-Audio-EditX) + Step-Audio-Tokenizer; the graph also uses comfy_mtb, ComfyUI-Custom-Scripts and ComfyUI-Easy-Use | [ComfyUI-Step_Audio_EditX_TTS](https://github.com/Saganaki22/ComfyUI-Step_Audio_EditX_TTS) | Model: Step-Audio-EditX; VRAM (approx.): ~16 GB (estimate); Licence: Weights licence not confirmed; pack Apache-2.0; Status: not yet tested |

## Supertonic

Folder: [`Supertonic/`](Supertonic) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-v3](Supertonic/tts-v3.json) | Fast on-device multilingual TTS with effects | [Supertone/supertonic-3](https://huggingface.co/Supertone/supertonic-3) ONNX | [ComfyUI-Supertonic3TTS](https://github.com/Anonymzx/ComfyUI-Supertonic3TTS) | Model: Supertonic 3 (99M); VRAM (approx.): CPU capable; Licence: Weights OpenRAIL (use conditions apply); pack MIT; Status: not yet tested |

## VibeVoice

Folder: [`VibeVoice/`](VibeVoice) — 5 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-audio-suite-srt-characters](VibeVoice/tts-audio-suite-srt-characters.json) | Character voices and SRT-timed speech | Auto-download to `models/TTS/` | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Model: VibeVoice; VRAM (approx.): ~6-20 GB; Licence: Model MIT; Status: not yet tested |
| [tts-dialogue-multi-speaker-podcast](VibeVoice/tts-dialogue-multi-speaker-podcast.json) | Up to 4-speaker podcast-style dialogue | As above | [VibeVoice-ComfyUI](https://github.com/Enemyx-net/VibeVoice-ComfyUI) | Model: VibeVoice; VRAM (approx.): As above; Licence: Model MIT; Status: not yet tested |
| [tts-pause-tags](VibeVoice/tts-pause-tags.json) | Single speaker with explicit [pause] timing tags | As above | [VibeVoice-ComfyUI](https://github.com/Enemyx-net/VibeVoice-ComfyUI) | Model: VibeVoice; VRAM (approx.): As above; Licence: Model MIT; Status: not yet tested |
| [tts-single-speaker](VibeVoice/tts-single-speaker.json) | Long-form single-speaker TTS with voice clone | `models/vibevoice/`: [microsoft/VibeVoice-1.5B](https://huggingface.co/microsoft/VibeVoice-1.5B), [aoi-ot/VibeVoice-Large](https://huggingface.co/aoi-ot/VibeVoice-Large), Q8/Q4 community quantisations | [VibeVoice-ComfyUI](https://github.com/Enemyx-net/VibeVoice-ComfyUI) | Model: VibeVoice 1.5B / 7B (Microsoft); VRAM (approx.): ~6 GB (1.5B), ~20 GB (Large), 8-12 GB quantised; Licence: Model MIT; official 7B withdrawn, Large weights are community re-uploads; pack MIT; Status: not yet tested |
| [tts-wildminder-and-asr](VibeVoice/tts-wildminder-and-asr.json) | TTS plus VibeVoice speech recognition | `models/tts/VibeVoice/`: VibeVoice-1.5B (3 GB), 7B (17.4 GB), [microsoft/VibeVoice-ASR-HF](https://huggingface.co/microsoft/VibeVoice-ASR-HF) | [ComfyUI-VibeVoice](https://github.com/wildminder/ComfyUI-VibeVoice), [ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) | Model: VibeVoice TTS + VibeVoice-ASR; VRAM (approx.): ~6-20 GB; Licence: Model MIT; pack MIT; Status: not yet tested |

## VoiceBridge

Folder: [`VoiceBridge/`](VoiceBridge) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [speech-translation](VoiceBridge/speech-translation.json) | Speech translation pipeline: transcribe, translate (OpenAI-compatible API, your own key), re-voice with a cloned voice and rebuild the audio from SRT times. Contains an author `E:\` path | Qwen3-ASR 1.7B / 0.6B + Qwen3-ForcedAligner-0.6B to `models/qwen-asr/`; Qwen3-TTS-12Hz-1.7B-Base to `models/qwen-tts/` | [comfyui_voicebridge](https://github.com/YanTianlong-01/comfyui_voicebridge), [ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) | Model: Qwen3-ASR + LLM translation + Qwen3-TTS; VRAM (approx.): ~8-12 GB; Licence: Models Apache-2.0; pack MIT; the translation API is a paid third-party service; Status: not yet tested |

## VoxCPM

Folder: [`VoxCPM/`](VoxCPM) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-and-voice-clone](VoxCPM/tts-and-voice-clone.json) | Tokenizer-free TTS and voice clone | Auto-download to `models/tts/VoxCPM/` ([openbmb/VoxCPM1.5](https://huggingface.co/openbmb/VoxCPM1.5)) | [ComfyUI-VoxCPM](https://github.com/wildminder/ComfyUI-VoxCPM) | Model: VoxCPM 0.5B / 1.5; VRAM (approx.): ~4-6 GB; Licence: Model Apache-2.0 (commercial OK); pack Apache-2.0; Status: not yet tested |
| [voice-clone-v2-and-lora](VoxCPM/voice-clone-v2-and-lora.json) | TTS, voice clone and LoRA training | [openbmb/VoxCPM2](https://huggingface.co/openbmb/VoxCPM2) to `models/tts/VoxCPM/` | [ComfyUI-VoxCPM2](https://github.com/Saganaki22/ComfyUI-VoxCPM2) | Model: VoxCPM2 2B; VRAM (approx.): ~8 GB; Licence: Model Apache-2.0 (commercial OK); pack Apache-2.0; Status: not yet tested |
| [voice-training-lora](VoxCPM/voice-training-lora.json) | Make a dataset and train a voice LoRA | As above; LoRAs to `models/loras/` | [ComfyUI-VoxCPM](https://github.com/wildminder/ComfyUI-VoxCPM), [ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) | Model: VoxCPM; VRAM (approx.): ~8+ GB; Licence: Model Apache-2.0 (commercial OK); Status: not yet tested |

## VoxLock

Folder: [`VoxLock/`](VoxLock) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [voice-isolation-with-sample](VoxLock/voice-isolation-with-sample.json) | Same, enrolled from a sample of the wanted speaker | As above | [ComfyUI-VoxLock](https://github.com/hiroki-abe-58/ComfyUI-VoxLock) | Model: VoxLock; VRAM (approx.): CPU; Licence: Pack MIT; check the model licence; Status: not yet tested |
| [voice-isolation](VoxLock/voice-isolation.json) | Keep one speaker and remove the others (CPU ONNX) | [arbazsiddiqui/voxlock](https://huggingface.co/arbazsiddiqui/voxlock) ONNX (~275 MB) to `models/voxlock/onnx`; `pip install voxlock==1.1.1` | [ComfyUI-VoxLock](https://github.com/hiroki-abe-58/ComfyUI-VoxLock) | Model: VoxLock (target-speaker isolation); VRAM (approx.): CPU; Licence: Pack MIT; check the model licence; Status: not yet tested |

## Whisper

Folder: [`Whisper/`](Whisper) — 6 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [stt-large-v3-audio-or-video](Whisper/stt-large-v3-audio-or-video.json) | Transcribe one audio or video file | Auto-download [openai/whisper-large-v3](https://huggingface.co/openai/whisper-large-v3) to the HF cache | [ComfyUI-TranscriptionTools](https://github.com/royceschultz/ComfyUI-TranscriptionTools) | Model: Whisper large-v3 (transformers); VRAM (approx.): ~5-10 GB; Licence: Model MIT (commercial OK); pack has no licence file; Status: not yet tested |
| [stt-large-v3-batch](Whisper/stt-large-v3-batch.json) | Batch-transcribe a folder of files | As above | [ComfyUI-TranscriptionTools](https://github.com/royceschultz/ComfyUI-TranscriptionTools) | Model: Whisper large-v3 (transformers); VRAM (approx.): ~5-10 GB; Licence: Model MIT (commercial OK); Status: not yet tested |
| [subtitles-faster-whisper](Whisper/subtitles-faster-whisper.json) | Fast transcription to a subtitle file | Auto-download | [ComfyUI-faster-whisper](https://github.com/ai-joe-git/ComfyUI-faster-whisper) | Model: faster-whisper (large-v2, CTranslate2); VRAM (approx.): ~3-5 GB; Licence: Model MIT (commercial OK); pack MIT; Status: not yet tested |
| [subtitles-large-v3-chinese-to-video](Whisper/subtitles-large-v3-chinese-to-video.json) | Chinese ASR with static or karaoke-style subtitles burned into video | See pack README | [ComfyUI_ASR-zh](https://github.com/billwuhao/ComfyUI_ASR-zh), [ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite), [ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) | Model: Belle-whisper-large-v3-zh (CTranslate2); VRAM (approx.): ~5 GB; Licence: Model per its card; pack Apache-2.0; Status: not yet tested |
| [subtitles-srt-vtt](Whisper/subtitles-srt-vtt.json) | Transcribe audio to text, SRT and VTT (set the output paths; the example holds the author's Windows paths) | Auto-download | [ComfyUI-whisper](https://github.com/woqiyoni/ComfyUI-whisper), [ComfyUI-Custom-Scripts](https://github.com/pythongosssss/ComfyUI-Custom-Scripts) | Model: Whisper large; VRAM (approx.): ~10 GB; Licence: Model MIT; pack has no licence file; Status: not yet tested |
| [subtitles-video-to-srt](Whisper/subtitles-video-to-srt.json) | Transcribe a video, save an SRT and burn subtitles into frames (model size is a widget choice) | Auto-download to `models/stt/whisper` | [ComfyUI-Whisper](https://github.com/yuvraj108c/ComfyUI-Whisper), [ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite) | Model: Whisper large-v3 / turbo / medium / small / base / tiny; VRAM (approx.): ~10 GB large-v3, ~6 GB turbo, ~2 GB small; Licence: Model MIT (commercial OK); pack has no licence file; Status: not yet tested |

## ZipVoice

Folder: [`ZipVoice/`](ZipVoice) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-en](ZipVoice/tts-en.json) | Zero-shot voice clone from a reference clip and transcript (base model only) | [k2-fsa/ZipVoice](https://huggingface.co/k2-fsa/ZipVoice) to `models/zipvoice/<name>` | [ComfyUI-ZipVoice](https://github.com/Burgstall-labs/ComfyUI-ZipVoice) | Model: ZipVoice (k2-fsa, 123M); VRAM (approx.): low, not stated; Licence: Weights Apache-2.0 upstream; **pack has no licence file**; Status: not yet tested |

## Zonos

Folder: [`Zonos/`](Zonos) — 5 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [tts-v2-emotion](Zonos/tts-v2-emotion.json) | As above with emotion-direction steering | As above | [zonos2-tts-comfyui-emotion](https://github.com/shiwano/zonos2-tts-comfyui-emotion) | Model: ZONOS2; VRAM (approx.): ~13-17 GB; Licence: Weights Apache-2.0; pack MIT; Status: not yet tested |
| [tts-v2](Zonos/tts-v2.json) | Multilingual voice-clone TTS | [Zyphra/ZONOS2](https://huggingface.co/Zyphra/ZONOS2) (BF16 / FP8 repacks by drbaph) + `descript/dac_44khz` codec | [Zonos2_TTS-ComfyUI](https://github.com/Saganaki22/Zonos2_TTS-ComfyUI) | Model: ZONOS2 (Zyphra); VRAM (approx.): ~13-17 GB; Licence: Weights Apache-2.0; pack MIT; Status: not yet tested |
| [voice-clone-v0.1-emotion](Zonos/voice-clone-v0.1-emotion.json) | TTS with an emotion vector and optional reference-voice clone | [Zyphra/Zonos-v0.1-transformer](https://huggingface.co/Zyphra/Zonos-v0.1-transformer) (auto-download); needs system package `espeak-ng` | [ComfyUI-Zonos](https://github.com/BuffMcBigHuge/ComfyUI-Zonos) | Model: Zonos v0.1 (Zyphra); VRAM (approx.): ~6 GB+; Licence: Weights Apache-2.0; pack MIT; Status: not yet tested |
| [voice-clone-v3](Zonos/voice-clone-v3.json) | Clone a voice from a reference (runs Zyphra's local server in a separate process) | [Zyphra/ZONOS3-Mini](https://huggingface.co/Zyphra/ZONOS3-Mini) | [ComfyUI-ZONOS3](https://github.com/claudianeodev/ComfyUI-ZONOS3) | Model: ZONOS3-Mini (Zyphra, 43 languages); VRAM (approx.): not stated; Licence: Weights Apache-2.0; pack MIT (very new pack); Status: not yet tested |
| [voice-design-v3](Zonos/voice-design-v3.json) | Design a voice from a text description | As above | [ComfyUI-ZONOS3](https://github.com/claudianeodev/ComfyUI-ZONOS3) | Model: ZONOS3-Mini; VRAM (approx.): not stated; Licence: Weights Apache-2.0; pack MIT; Status: not yet tested |

## Other

Folder: [`Other/`](Other) — 5 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [forced-alignment-lyrics-showcase](Other/forced-alignment-lyrics-showcase.json) | Align a lyric or script file to audio with word times and slice by time; usable for speech | torchaudio MMS_FA bundle (1.2 GB, downloaded on first align) | [comfyui_lyric_align](https://github.com/bmad4ever/comfyui_lyric_align), [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Model: torchaudio MMS forced aligner (wav2vec2 CTC); VRAM (approx.): ~2 GB; Licence: **MMS alignment weights are CC-BY-NC-4.0 (non-commercial)**; pack MIT; some helper nodes are unverified; Status: not yet tested |
| [forced-alignment-srt-overlay](Other/forced-alignment-srt-overlay.json) | Force-align a known script or SRT to audio and burn subtitles into a video. Contains an author `/home/jovyan/...` path; several helper packs are named in the graph | Whisper to `models/stt/whisper`; UVR / Roformer vocal model (1.8 GB) to `models/uvr5/`; a font in `models/fonts` | [ComfyUI-Audio-Srt-Aligner](https://github.com/ahkimkoo/ComfyUI-Audio-Srt-Aligner), [audio-separation-nodes-comfyui](https://github.com/christian-byrne/audio-separation-nodes-comfyui), [ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite), [rgthree-comfy](https://github.com/rgthree/rgthree-comfy) | Model: Whisper + UVR vocal separation; VRAM (approx.): ~2-6 GB; Licence: Pack MIT; check each model; Status: not yet tested |
| [speech-enhance-tts-audio-suite](Other/speech-enhance-tts-audio-suite.json) | Remove background music and noise from speech | Auto-download to `models/TTS/` | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Model: Voice Fixer and vocal removal; VRAM (approx.): ~2-4 GB; Licence: Pack MIT; Status: not yet tested |
| [subtitles-tts-audio-suite-asr-granite-qwen3](Other/subtitles-tts-audio-suite-asr-granite-qwen3.json) | ASR, punctuation/truecase and SRT builder; Granite can also translate speech | Auto-download to `models/TTS/` | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Model: Qwen3-ASR or IBM Granite Speech 4.0 1B; VRAM (approx.): ~4-6 GB; Licence: Qwen3-ASR Apache-2.0; Granite Apache-2.0 (commercial OK); Status: not yet tested |
| [voice-design-moss-omnivoice-qwen](Other/voice-design-moss-omnivoice-qwen.json) | Unified Voice Designer: create a voice from a text description with any of three engines and save it as a character voice | Auto-download to `models/TTS/` (MOSS VoiceGenerator 1.7B + audio tokenizer ~8.5 GB) | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Model: MOSS-VoiceGenerator, OmniVoice, Qwen3-TTS; VRAM (approx.): ~6-18 GB by engine; Licence: MOSS and Qwen3 Apache-2.0; pack MIT; Status: not yet tested |

## Notes carried over from the previous folder layout

Setup notes, licences, test results and "not available in ComfyUI" lists from the former task-folder READMEs. Links point to the new locations.

### From the former "Speech" README

Text-to-speech, voice cloning, voice design and voice conversion (Qwen3-TTS, OmniVoice, MOSS-TTS, Higgs Audio v3, FireRedTTS3, IndexTTS 1.5 / 2 / 2.5, CosyVoice 1 / 2 / 3, Orpheus, Zonos, Maya1 / Maya3 Indic, Spark-TTS, RVC, Seed-VC, Fish S2, Chatterbox, Kokoro, Parler-TTS, OpenVoice, F5-TTS, Bark, ChatTTS, Dia, Sesame CSM, VibeVoice, VoxCPM, ElevenLabs and Fish Audio API, and more); speech clean-up; speech-to-text, subtitles, diarisation, speech translation and forced alignment (MOSS-Transcribe-Diarize, FunASR, Hibiki, Whisper, faster-whisper, Qwen3-ASR, Parakeet, Nemotron, SenseVoice, Granite Speech).

Status notes are carried over unchanged from the earlier library README; none of the Atlas additions has been run. Voice cloning and voice conversion need the consent of the person whose voice you use.

#### Speech models not yet available in ComfyUI

No published ComfyUI workflow exists for these models, so the library has no workflow for them. The Open Speech Model Atlas additions (November 2026) are included below the older rows. Where a node pack exists, it is named so a workflow can be built and tested later.

| Model | Why there is no workflow | Official link |
|---|---|---|
| AI4Bharat Indic-TTS | No pack | [AI4Bharat/Indic-TTS](https://github.com/AI4Bharat/Indic-TTS) |
| XTTS-v2 | Pack [AIFSH/ComfyUI-XTTS](https://github.com/AIFSH/ComfyUI-XTTS) exists (last updated 2024-06) but ships no workflow. Weights are CPML (non-commercial) | [coqui/XTTS-v2](https://huggingface.co/coqui/XTTS-v2) |
| YourTTS | No pack; only inside the coqui TTS library | [coqui-ai/TTS](https://github.com/coqui-ai/TTS) |
| VITS | No pack | [jaywalnut310/vits](https://github.com/jaywalnut310/vits) |
| StyleTTS2 | Only a client node that calls a separate TTS WebUI server ([rsxdalv/ComfyUI-TTS-Webui](https://github.com/rsxdalv/ComfyUI-TTS-Webui)); no workflow | [yl4579/StyleTTS2](https://github.com/yl4579/StyleTTS2) |
| Tortoise | Pack [eigenpunk/ComfyUI-audio](https://github.com/eigenpunk/ComfyUI-audio) has Tortoise nodes but no workflow | [neonbjb/tortoise-tts](https://github.com/neonbjb/tortoise-tts) |
| Matcha-TTS | No pack | [shivammehta25/Matcha-TTS](https://github.com/shivammehta25/Matcha-TTS) |
| Piper | Pack [yuvraj108c/ComfyUI-PiperTTS](https://github.com/yuvraj108c/ComfyUI-PiperTTS) (one `PiperTTS` node) ships no workflow; original Piper repo archived | [rhasspy/piper](https://github.com/rhasspy/piper) |
| MagpieTTS (Hindi) | No pack; runs through NVIDIA NeMo, NIM or Riva | [NVIDIA/NeMo](https://github.com/NVIDIA/NeMo) |
| Distil-Whisper | No pack | [distil-whisper](https://huggingface.co/distil-whisper) |
| whisper.cpp | No pack | [ggml-org/whisper.cpp](https://github.com/ggml-org/whisper.cpp) |
| WhisperX | Packs [AIFSH/ComfyUI-WhisperX](https://github.com/AIFSH/ComfyUI-WhisperX) and loockluo/comfyui-whisperx-pro ship no loadable workflow | [m-bain/whisperX](https://github.com/m-bain/whisperX) |
| Whisper translate-to-English | No published workflow uses Whisper's translate task | [openai/whisper](https://github.com/openai/whisper) |
| Whisper on Apple Silicon (MLX) | Pack [feishengfei/comfyui_whisper_mlx](https://github.com/feishengfei/comfyui_whisper_mlx) has a workflow, but it runs only on macOS, so it is not included | [ml-explore/mlx-examples](https://github.com/ml-explore/mlx-examples) |
| Parakeet-TDT-0.6B-v3 | Only v2 (English) is supported (see `parakeet-tdt-0.6b-v2-subtitles-with-kokoro`) | [nvidia/parakeet-tdt-0.6b-v3](https://huggingface.co/nvidia/parakeet-tdt-0.6b-v3) |
| Nemotron 3.5 Transcribe | No pack; Nemotron streaming works only through a separate server | [NVIDIA NeMo](https://github.com/NVIDIA/NeMo) |
| Canary-1B-v2 / Canary Flash | Pack [Juste-Leo2/Canary-ComfyUI](https://github.com/Juste-Leo2/Canary-ComfyUI) (ASR and speech translation) ships no workflow | [nvidia/canary-1b-v2](https://huggingface.co/nvidia/canary-1b-v2) |
| Canary-Qwen 2.5B | No published workflow found | [nvidia/canary-qwen-2.5b](https://huggingface.co/nvidia/canary-qwen-2.5b) |
| Fun-ASR-Nano | No pack; [ahkimkoo/ComfyUI-FunASR](https://github.com/ahkimkoo/ComfyUI-FunASR) covers only Paraformer and ships no workflow | [FunAudioLLM/Fun-ASR-Nano-2512](https://huggingface.co/FunAudioLLM/Fun-ASR-Nano-2512) |
| Moonshine | No pack | [usefulsensors/moonshine](https://github.com/usefulsensors/moonshine) |
| IndicConformer / IndicWhisper | No pack | [AI4Bharat](https://github.com/AI4Bharat) |
| wav2vec2 / XLSR / HuBERT / WavLM | No speech-to-text pack; used only as feature extractors inside other packs | [facebook/wav2vec2-base-960h](https://huggingface.co/facebook/wav2vec2-base-960h) |
| MMS | No pack; weights CC-BY-NC-4.0 | [facebook/mms-1b-all](https://huggingface.co/facebook/mms-1b-all) |
| SeamlessM4T | No pack; weights CC-BY-NC-4.0 | [facebookresearch/seamless_communication](https://github.com/facebookresearch/seamless_communication) |
| OWSM / ESPnet | No pack | [espnet/espnet](https://github.com/espnet/espnet) |
| sherpa-onnx | No pack | [k2-fsa/sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx) |
| Vosk | No pack | [alphacep/vosk-api](https://github.com/alphacep/vosk-api) |
| Google, OpenAI, Deepgram, Cartesia, PlayHT, Sarvam, Amazon Polly, Azure, AssemblyAI, Speechmatics speech APIs | ComfyUI core has no speech API nodes and Comfy publishes no templates for them (only ElevenLabs and Fish Audio, above) | — |
| Omnilingual ASR (CTC and LLM, 300M-7B, 1600+ languages) | Only HTTP-server wrappers exist (for example [ARahim3/omniASR-server](https://github.com/ARahim3/omniASR-server)); no ComfyUI node pack | [facebookresearch/omnilingual-asr](https://github.com/facebookresearch/omnilingual-asr) |
| MOSS-TTS Nano and MOSS-TTS Realtime | No ComfyUI pack found (the full MOSS-TTS models are covered above) | [OpenMOSS-Team/MOSS-TTS-Nano-100M](https://huggingface.co/OpenMOSS-Team/MOSS-TTS-Nano-100M) |
| GLM-TTS / GLM-TTS-RL | Pack [karas17/comfyui_GLM_TTS](https://github.com/karas17/comfyui_GLM_TTS) (Apache-2.0) ships no workflow | [zai-org/GLM-TTS](https://huggingface.co/zai-org/GLM-TTS) |
| Higgs Audio v2 | Pack [Yuan-ManX/ComfyUI-HiggsAudio](https://github.com/Yuan-ManX/ComfyUI-HiggsAudio) ships no workflow; the engine appears only inside multi-engine TTS-Audio-Suite graphs. Higgs v3 is covered above | [bosonai/higgs-audio-v2-generation-3B-base](https://huggingface.co/bosonai/higgs-audio-v2-generation-3B-base) |
| OuteTTS | Pack [billwuhao/ComfyUI_OuteTTS](https://github.com/billwuhao/ComfyUI_OuteTTS) has README screenshots only; weights CC-BY-NC-SA-4.0 | [OuteAI/Llama-OuteTTS-1.0-1B](https://huggingface.co/OuteAI/Llama-OuteTTS-1.0-1B) |
| LLaSA | No ComfyUI pack found; weights CC-BY-NC-4.0 | [HKUSTAudio/Llasa-3B](https://huggingface.co/HKUSTAudio/Llasa-3B) |
| FireRedTTS / FireRedTTS2 (v1 and v2) | FireRedTTS3 is covered above. [1038lab/ComfyUI-FireRedTTS](https://github.com/1038lab/ComfyUI-FireRedTTS) (GPL-3.0) ships no workflow; no FireRedTTS2 pack in the registry | [FireRedTeam/FireRedTTS2](https://huggingface.co/FireRedTeam/FireRedTTS2) |
| GPT-SoVITS v4 / v5 Turbo | Only the 2024 v2 pack is covered above; the v4 repo is empty and [bozoyan/ComfyUI_GPT_SoVITS_Lite](https://github.com/bozoyan/ComfyUI_GPT_SoVITS_Lite) ships no workflow | [RVC-Boss/GPT-SoVITS](https://github.com/RVC-Boss/GPT-SoVITS) |
| Veena (Hindi-English) | No ComfyUI pack found | [maya-research](https://huggingface.co/maya-research) |
| ZipVoice-Distill, ZipVoice-Dialog, ZipVoice-Dialog-Stereo | The only pack ([Burgstall-labs/ComfyUI-ZipVoice](https://github.com/Burgstall-labs/ComfyUI-ZipVoice)) covers the base model | [k2-fsa/ZipVoice](https://github.com/k2-fsa/ZipVoice) |
| Kyutai Pocket TTS | Packs [ai-joe-git/ComfyUI-Pocket-TTS](https://github.com/ai-joe-git/ComfyUI-Pocket-TTS) and [scofano/ComfyUI-Pocket-TTS-V2](https://github.com/scofano/ComfyUI-Pocket-TTS-V2) ship only a `.yml` file, no loadable JSON | [kyutai-labs/pocket-tts](https://github.com/kyutai-labs/pocket-tts) |
| Supertonic 2 | No pack found (Supertonic 3 is covered above) | [Supertone](https://huggingface.co/Supertone) |
| WhisperSpeech, MetaVoice, VoiceCraft, EmotiVoice, Bert-VITS2 / Style-Bert-VITS2 / VITS2, VALL-E X, Moshi | No ComfyUI pack found. [eigenpunk/ComfyUI-audio](https://github.com/eigenpunk/ComfyUI-audio) (GPL-3.0) wraps some older models without a workflow | [WhisperSpeech](https://github.com/WhisperSpeech/WhisperSpeech), [metavoice-src](https://github.com/metavoiceio/metavoice-src), [VoiceCraft](https://github.com/jasonppy/VoiceCraft), [EmotiVoice](https://github.com/netease-youdao/EmotiVoice), [Moshi](https://github.com/kyutai-labs/moshi) |
| NVIDIA MagpieTTS, FastPitch, NeMo TTS zoo | No pack; the only Magpie pack found (BlueMagpie-TTS) is a different, Taiwanese model with API-format JSON only | [nvidia/magpie_tts_multilingual_357m](https://huggingface.co/nvidia/magpie_tts_multilingual_357m) |
| AI4Bharat IndicF5 | No ComfyUI loader. [niknah/ComfyUI-F5-TTS](https://github.com/niknah/ComfyUI-F5-TTS) lists community Indic F5 checkpoints (`ShriAishu/hindiSpeech`, `SPRINGLab/F5-Hindi-24KHz`) but its example workflows have no Indic selection. Use Maya3 above for Indic TTS | [ai4bharat/IndicF5](https://huggingface.co/ai4bharat/IndicF5) |
| Indic Parler-TTS | [smthemex/ComfyUI_ParlerTTS](https://github.com/smthemex/ComfyUI_ParlerTTS) targets the English Parler models; Indic support is unconfirmed | [ai4bharat/indic-parler-tts](https://huggingface.co/ai4bharat/indic-parler-tts) |
| Vakyansh TTS and ASR, Project Vaani (DhVaani, SraVaani, Vaani Whisper and FastConformer), IndicWav2Vec, KhayaAI DONDO, Dolphin ASR | No ComfyUI pack found | [Open-Speech-EkStep](https://github.com/Open-Speech-EkStep), [Project Vaani](https://huggingface.co/ARTPARK-IISc), [KhayaAI](https://huggingface.co/KhayaAI) |
| Meta MMS-TTS and MMS-LID (MMS ASR is listed above) | No ComfyUI pack; weights CC-BY-NC-4.0 | [facebook/mms-tts](https://huggingface.co/facebook/mms-tts) |
| Canary-Qwen, Fun-ASR-Nano, Moonshine, Voxtral STT, Kyutai STT, GLM-ASR, Cohere Transcribe, OWSM, wav2vec2 family (see rows above) | Searched again in November 2026: still no pack with a loadable workflow. FireRedASR / FireRedASR2S exist only as API-format examples in [T8mars/comfyui-fireredaudio-T8](https://github.com/T8mars/comfyui-fireredaudio-T8); Voxtral packs are TTS only | [moonshine-ai/moonshine](https://github.com/moonshine-ai/moonshine), [mistralai/Voxtral-Mini-3B-2507](https://huggingface.co/mistralai/Voxtral-Mini-3B-2507), [kyutai/stt-2.6b-en](https://huggingface.co/kyutai/stt-2.6b-en), [FireRedTeam](https://huggingface.co/FireRedTeam) |
| SeamlessM4T / SeamlessStreaming (speech translation) | No pack; weights CC-BY-NC-4.0 (existing row covers the repo) | [facebook/seamless-m4t-v2-large](https://huggingface.co/facebook/seamless-m4t-v2-large) |
| WhisperX (alignment and diarisation), pyannote.audio, Montreal Forced Aligner, Silero VAD, WebRTC VAD, MarbleNet, MSDD | Packs exist ([AIFSH/ComfyUI-WhisperX](https://github.com/AIFSH/ComfyUI-WhisperX), [ComfyUI_pyannote](https://github.com/ramesh-x90/ComfyUI_pyannote), [ComfyUI-MontrealForcedAligner](https://github.com/teddy1565/ComfyUI-MontrealForcedAligner)) but none ships a loadable workflow; pyannote weights are gated on Hugging Face | [pyannote/pyannote-audio](https://github.com/pyannote/pyannote-audio), [snakers4/silero-vad](https://github.com/snakers4/silero-vad) |
| ReazonSpeech, kotoba-whisper (Japanese) | [kale4eat/ComfyUI-speech-dataset-toolkit](https://github.com/kale4eat/ComfyUI-speech-dataset-toolkit) (GPL-3.0) lists them but ships no workflow | [reazon-research/reazonspeech-nemo-v2](https://huggingface.co/reazon-research/reazonspeech-nemo-v2) |
| CrisperWhisper, DeepFilterNet, sherpa-onnx Paraformer, whisper.cpp node | CrisperWhisper has only a CLI port; [obvirm/ComfyUI-WhisperCPP](https://github.com/obvirm/ComfyUI-WhisperCPP) and [comfyui-dm-paraformer-asr](https://github.com/dxyliwei520/comfyui-dm-paraformer-asr) ship API-format JSON only; no DeepFilterNet pack | [nyrahealth/CrisperWhisper](https://github.com/nyrahealth/CrisperWhisper), [Rikorose/DeepFilterNet](https://github.com/Rikorose/DeepFilterNet) |
| Classic and research models without a ComfyUI path: Tacotron / Tacotron2, FastSpeech / FastSpeech2, Glow-TTS, JETS, Grad-TTS, FastDiff, DiffSpeech, Mimic, Flite, Festival, MaryTTS, RHVoice, eSpeak NG, PaddleSpeech, TensorFlowTTS, DeepSpeech, Coqui STT, wav2letter, Kaldi, WeNet, SpeechBrain, Icefall, Conformer / Zipformer recipes, QuartzNet, Citrinet, Jasper, KoSpeech, MedASR, Silero STT, the Whisper Hindi / Urdu / Japanese community fine-tunes | Training recipes, toolkits or archived projects; no ComfyUI node pack found for any of them | [espnet/espnet](https://github.com/espnet/espnet), [k2-fsa/icefall](https://github.com/k2-fsa/icefall) |

### From the former "Speech-to-Text and Subtitles" README

Speech recognition, subtitle creation and speaker diarisation: 22 workflows in 11 model-family folders. Speech translation and forced alignment are in [`../Speech-Translation/`](.) and [`../Forced-Alignment/`](.).

#### Notes

- Status notes are carried over unchanged from the earlier library README; none of these workflows has a recorded test run unless its Status cell says so.
- API workflows (ElevenLabs, Fish Audio) need a Comfy.org account and paid API credits.

#### Find by task

Each workflow lives in one model-family folder; this index lists the same files by what they do (a workflow can appear under more than one task; the main tables below are authoritative).

- **Subtitles (SRT / VTT, burned into video)** (9): [subtitles-video-to-srt](Whisper/subtitles-video-to-srt.json), [subtitles-srt-vtt](Whisper/subtitles-srt-vtt.json), [subtitles-large-v3-chinese-to-video](Whisper/subtitles-large-v3-chinese-to-video.json), [subtitles-faster-whisper](Whisper/subtitles-faster-whisper.json), [subtitles-0.6b](Qwen3-ASR/subtitles-0.6b.json), [subtitles-tts-audio-suite-asr-granite-qwen3](Other/subtitles-tts-audio-suite-asr-granite-qwen3.json), [subtitles-tdt-0.6b-v2-with-kokoro](Parakeet/subtitles-tdt-0.6b-v2-with-kokoro.json), [subtitles-av-audio2subtitle-prompt-1](FunASR/subtitles-av-audio2subtitle-prompt-1.json), [subtitles-av-audio2subtitle-prompt-2](FunASR/subtitles-av-audio2subtitle-prompt-2.json)
- **Speaker diarisation** (2): [stt-diarize-basic](MOSS/stt-diarize-basic.json), [stt-diarize-long-audio](MOSS/stt-diarize-long-audio.json)
- **Live / streaming transcription** (2): [stt-server](Nemotron/stt-server.json), [stt-live-microphone](Nemotron/stt-live-microphone.json)
- **Batch / long audio** (2): [stt-large-v3-batch](Whisper/stt-large-v3-batch.json), [stt-diarize-long-audio](MOSS/stt-diarize-long-audio.json)

### From the former "Text-to-Speech and Voice Cloning" README

Text-to-speech, voice cloning, voice design and custom voices, multi-speaker dialogue, expressive / emotion control, speech editing and voice-model training: 110 workflows in 38 model-family folders. Voice conversion, speech clean-up, speech-to-text, translation and alignment are in the sibling folders listed in the [Speech README](README.md).

#### Notes

- Status / test notes are carried over unchanged from the earlier library README. Rows whose VRAM, licence or status read "—" / "not recorded" had no such data recorded (they came from an earlier four-column table).
- The speech workflows below were collected from their node packs' official example workflows and Comfy-Org templates. They are checked only as loadable ComfyUI workflow files: none has been run yet, so each is marked **not yet tested**. VRAM figures are rough estimates. API workflows (ElevenLabs, Fish Audio) need a Comfy.org account and paid API credits.
- Added after reading the 19 November 2026 *Open Speech Model Atlas* (122 TTS entries, 145 STT / ASR entries, 42 supporting tools) and comparing it with the library: 57 text-to-speech, voice-design, voice-conversion and speech clean-up workflows and 8 speech-to-text, diarisation, speech-translation and alignment workflows. Every file is a published example workflow from its node pack, saved unmodified. They were only checked as loadable ComfyUI JSON (valid UI format, every link resolves, every custom node type found in the named pack's source unless noted) and nothing was run, so all are marked **not yet tested**. No weights were downloaded: the weight links and folders come from each pack's README and may change. VRAM figures are the pack authors' numbers or rough estimates.
Things to know before running them:
  - Every Load Audio node holds the author's sample file name: pick your own reference clip.
  - Four files contain author-local paths (`kyutai-tts`, `maskgct-tts`, `audio-srt-aligner-overlay`, `voicebridge-speech-translation`); the table row says which widget to change.
  - Many of these packs are new, small or have no licence file. **Non-commercial or restricted weights** are in bold in the Licence column. Voice cloning needs the consent of the person whose voice you clone.
  - TTS-Audio-Suite and several single-model packs install their own dependencies (some need Transformers 5 or an isolated runtime); install one pack at a time and read its README.

#### Find by task

Each workflow lives in one model-family folder; this index lists the same files by what they do (a workflow can appear under more than one task; the main tables below are authoritative).

- **Voice design and custom voices** (12): [tts-custom-voice](Qwen3-TTS/tts-custom-voice.json), [voice-design-dialogue](Qwen3-TTS/voice-design-dialogue.json), [voice-design-save-voice](Qwen3-TTS/voice-design-save-voice.json), [voice-design](Qwen3-TTS/voice-design.json), [voice-design-1038lab-create-your-voice](Qwen3-TTS/voice-design-1038lab-create-your-voice.json), [voice-design-tts-audio-suite-asr-srt](Qwen3-TTS/voice-design-tts-audio-suite-asr-srt.json), [tts-described-voice](Parler-TTS/tts-described-voice.json), [voice-design-moss-omnivoice-qwen](Other/voice-design-moss-omnivoice-qwen.json), [voice-design-voicegenerator](MOSS/voice-design-voicegenerator.json), [voice-clone-create](Spark-TTS/voice-clone-create.json), [voice-design-v3](Zonos/voice-design-v3.json), [tts-v1](Maya/tts-v1.json)
- **Multi-speaker dialogue** (25): [tts-dialogue-s2-multi-speaker](Fish-Speech/tts-dialogue-s2-multi-speaker.json), [voice-clone-saved-multi-voice-dialogue](Qwen3-TTS/voice-clone-saved-multi-voice-dialogue.json), [voice-design-dialogue](Qwen3-TTS/voice-design-dialogue.json), [tts-s2-pro-tts-audio-suite-srt-characters](Fish-Speech/tts-s2-pro-tts-audio-suite-srt-characters.json), [tts-1.6b-dialogue](Dia/tts-1.6b-dialogue.json), [voice-clone-1.6b](Dia/voice-clone-1.6b.json), [tts-1.6b-audio-retimer](Dia/tts-1.6b-audio-retimer.json), [tts-1.6b-safetensors-loader](Dia/tts-1.6b-safetensors-loader.json), [tts-v2-and-captions](Dia/tts-v2-and-captions.json), [voice-clone-1b-dialogue](Sesame-CSM/voice-clone-1b-dialogue.json), [tts-dialogue-1b-saved-speakers](Sesame-CSM/tts-dialogue-1b-saved-speakers.json), [tts-dialogue](Chatterbox/tts-dialogue.json), [tts-wildminder-dialogue-srt-vc](Chatterbox/tts-wildminder-dialogue-srt-vc.json), [tts-dialogue-multi-speaker-podcast](VibeVoice/tts-dialogue-multi-speaker-podcast.json), [tts-audio-suite-srt-characters](VibeVoice/tts-audio-suite-srt-characters.json), [tts-dialogue-api](ElevenLabs/tts-dialogue-api.json), [tts-dialogue-v4-api](ElevenLabs/tts-dialogue-v4-api.json), [tts-dialogue-fish-audio-api-drama-3](Fish-Speech/tts-dialogue-fish-audio-api-drama-3.json), [tts-fish-audio-api-drama-3-directed](Fish-Speech/tts-fish-audio-api-drama-3-directed.json), [tts-dialogue-v15](MOSS/tts-dialogue-v15.json), [tts-dialogue-ttsd](MOSS/tts-dialogue-ttsd.json), [voice-clone-v3-multispeaker](Higgs-Audio/voice-clone-v3-multispeaker.json), [tts-dialogue-1.5](IndexTTS/tts-dialogue-1.5.json), [tts-dialogue-2.5](IndexTTS/tts-dialogue-2.5.json), [tts-audio-suite](DramaBox/tts-audio-suite.json)
- **Voice cloning** (36): [voice-clone-s2](Fish-Speech/voice-clone-s2.json), [voice-clone-load-saved-voice](Qwen3-TTS/voice-clone-load-saved-voice.json), [voice-clone-save-voice](Qwen3-TTS/voice-clone-save-voice.json), [voice-clone-saved-multi-voice-dialogue](Qwen3-TTS/voice-clone-saved-multi-voice-dialogue.json), [voice-clone](Qwen3-TTS/voice-clone.json), [voice-clone-1038lab-with-asr](Qwen3-TTS/voice-clone-1038lab-with-asr.json), [voice-clone-300m-zero-shot](CosyVoice/voice-clone-300m-zero-shot.json), [voice-clone-300m-cross-lingual](CosyVoice/voice-clone-300m-cross-lingual.json), [voice-clone](F5-TTS/voice-clone.json), [voice-clone-whisper-auto-transcript](F5-TTS/voice-clone-whisper-auto-transcript.json), [voice-clone-1.6b](Dia/voice-clone-1.6b.json), [voice-clone-1b-context](Sesame-CSM/voice-clone-1b-context.json), [voice-clone-1b-dialogue](Sesame-CSM/voice-clone-1b-dialogue.json), [tts-and-voice-clone](VoxCPM/tts-and-voice-clone.json), [voice-clone-v2-and-lora](VoxCPM/voice-clone-v2-and-lora.json), [voice-clone-fish-audio-api](Fish-Speech/voice-clone-fish-audio-api.json), [voice-clone-v15-continue](MOSS/voice-clone-v15-continue.json), [voice-clone-v3-multispeaker](Higgs-Audio/voice-clone-v3-multispeaker.json), [voice-clone-1.5](IndexTTS/voice-clone-1.5.json), [voice-clone-2.5-basic](IndexTTS/voice-clone-2.5-basic.json), [voice-clone-create](Spark-TTS/voice-clone-create.json), [voice-clone](Orpheus/voice-clone.json), [voice-clone-v2-zero-shot](CosyVoice/voice-clone-v2-zero-shot.json), [voice-clone-v2-crosslingual](CosyVoice/voice-clone-v2-crosslingual.json), [tts-v2](GPT-SoVITS/tts-v2.json), [voice-training-v2-finetune](GPT-SoVITS/voice-training-v2-finetune.json), [voice-clone-v0.1-emotion](Zonos/voice-clone-v0.1-emotion.json), [voice-clone-v3](Zonos/voice-clone-v3.json), [voice-clone-v3-indic](Maya/voice-clone-v3-indic.json), [voice-clone-v3-indic-auto-transcribe](Maya/voice-clone-v3-indic-auto-transcribe.json), [tts-en](ZipVoice/tts-en.json), [tts](MaskGCT/tts.json), [voice-clone](NeuTTS/voice-clone.json), [voice-clone-uvr5](MARS5/voice-clone-uvr5.json), [tts](MisoTTS/tts.json), [voice-clone-editx](Step-Audio/voice-clone-editx.json)
- **Speech editing, emotion and expressive control** (14): [tts-300m-instruct](CosyVoice/tts-300m-instruct.json), [speech-edit-tts-audio-suite](F5-TTS/speech-edit-tts-audio-suite.json), [tts](Bark/tts.json), [tts-pause-tags](VibeVoice/tts-pause-tags.json), [tts-2-emotion-control](IndexTTS/tts-2-emotion-control.json), [tts-2-audio-suite-emotion-srt](IndexTTS/tts-2-audio-suite-emotion-srt.json), [voice-clone-v3-multispeaker](Higgs-Audio/voice-clone-v3-multispeaker.json), [tts-v3-audio-suite](Higgs-Audio/tts-v3-audio-suite.json), [tts-v2-instruct](CosyVoice/tts-v2-instruct.json), [voice-clone-v0.1-emotion](Zonos/voice-clone-v0.1-emotion.json), [tts-v2-emotion](Zonos/tts-v2-emotion.json), [voice-clone-editx](Step-Audio/voice-clone-editx.json), [speech-edit-editx](Step-Audio/speech-edit-editx.json), [tts-audio-suite](DramaBox/tts-audio-suite.json)
- **Voice model training (LoRA / fine-tune)** (3): [voice-training-lora](VoxCPM/voice-training-lora.json), [voice-clone-v2-and-lora](VoxCPM/voice-clone-v2-and-lora.json), [voice-training-v2-finetune](GPT-SoVITS/voice-training-v2-finetune.json)

See the [03-Audio overview](../README.md) for the other categories, the [main README](../../README.md) for setup, or [`00-LIBRARY-INDEX.md`](../../00-LIBRARY-INDEX.md) for the full list.
