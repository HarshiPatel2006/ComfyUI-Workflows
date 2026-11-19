# Speech-to-Text and Subtitles — ComfyUI workflows

Speech recognition, subtitle creation and speaker diarisation: 22 workflows in 11 model-family folders. Speech translation and forced alignment are in [`../Speech-Translation/`](../Speech-Translation) and [`../Forced-Alignment/`](../Forced-Alignment).

| Model family folder | Workflows |
|---|---|
| [`ElevenLabs/`](#elevenlabs) | 1 |
| [`Fish-Speech/`](#fish-speech) | 1 |
| [`FunASR/`](#funasr) | 2 |
| [`Mega-ASR/`](#mega-asr) | 1 |
| [`MOSS/`](#moss) | 2 |
| [`Multi-Model/`](#multi-model) | 1 |
| [`Nemotron/`](#nemotron) | 2 |
| [`Parakeet/`](#parakeet) | 1 |
| [`Qwen3-ASR/`](#qwen3-asr) | 4 |
| [`SenseVoice/`](#sensevoice) | 1 |
| [`Whisper/`](#whisper) | 6 |

## Notes

- Status notes are carried over unchanged from the earlier library README; none of these workflows has a recorded test run unless its Status cell says so.
- API workflows (ElevenLabs, Fish Audio) need a Comfy.org account and paid API credits.

## Find by task

Each workflow lives in one model-family folder; this index lists the same files by what they do (a workflow can appear under more than one task; the main tables below are authoritative).

- **Subtitles (SRT / VTT, burned into video)** (9): [whisper-video-to-subtitles-srt](Whisper/whisper-video-to-subtitles-srt.json), [whisper-transcribe-to-srt-vtt](Whisper/whisper-transcribe-to-srt-vtt.json), [whisper-large-v3-chinese-subtitles-to-video](Whisper/whisper-large-v3-chinese-subtitles-to-video.json), [faster-whisper-transcribe-to-subtitles](Whisper/faster-whisper-transcribe-to-subtitles.json), [qwen3-asr-0.6b-subtitles](Qwen3-ASR/qwen3-asr-0.6b-subtitles.json), [tts-audio-suite-asr-to-srt-granite-qwen3](Multi-Model/tts-audio-suite-asr-to-srt-granite-qwen3.json), [parakeet-tdt-0.6b-v2-subtitles-with-kokoro](Parakeet/parakeet-tdt-0.6b-v2-subtitles-with-kokoro.json), [funasr-av-audio2subtitle-prompt-1](FunASR/funasr-av-audio2subtitle-prompt-1.json), [funasr-av-audio2subtitle-prompt-2](FunASR/funasr-av-audio2subtitle-prompt-2.json)
- **Speaker diarisation** (2): [moss-transcribe-diarize-basic](MOSS/moss-transcribe-diarize-basic.json), [moss-transcribe-diarize-long-audio](MOSS/moss-transcribe-diarize-long-audio.json)
- **Live / streaming transcription** (2): [nemotron-asr-transcribe-server](Nemotron/nemotron-asr-transcribe-server.json), [nemotron-asr-live-microphone](Nemotron/nemotron-asr-live-microphone.json)
- **Batch / long audio** (2): [whisper-large-v3-batch-transcribe](Whisper/whisper-large-v3-batch-transcribe.json), [moss-transcribe-diarize-long-audio](MOSS/moss-transcribe-diarize-long-audio.json)

## Workflows by model family

### ElevenLabs

Folder [`ElevenLabs/`](ElevenLabs) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [elevenlabs-api-speech-to-text](ElevenLabs/elevenlabs-api-speech-to-text.json) | ElevenLabs Scribe (API) | Speech to text | none (ComfyUI core API nodes) | None (cloud) | None | paid Comfy API credits; output under provider terms | not yet tested |

### Fish-Speech

Folder [`Fish-Speech/`](Fish-Speech) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [fish-audio-api-speech-to-text](Fish-Speech/fish-audio-api-speech-to-text.json) | Fish Audio (API) | Speech to text | none (ComfyUI core API nodes) | None (cloud) | None | paid Comfy API credits; output under provider terms | not yet tested |

### FunASR

Folder [`FunASR/`](FunASR) — 2 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [funasr-av-audio2subtitle-prompt-1](FunASR/funasr-av-audio2subtitle-prompt-1.json) | FunASR Paraformer-seaco + FSMN-VAD | Chinese audio to timestamped SRT with optional hot-word prompt | [ComfyUI-AV-FunASR](https://github.com/avenstack/ComfyUI-AV-FunASR), [ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) | ModelScope `iic/speech_seaco_paraformer_large_asr_nat-zh-cn-16k-common-vocab8404-pytorch` and `iic/speech_fsmn_vad_zh-cn-16k-common-pytorch` to `models/ASR/FunASR/iic/`; `pip install funasr` | ~2-4 GB | FunASR model licence (attribution); **pack has no licence file** | not yet tested |
| [funasr-av-audio2subtitle-prompt-2](FunASR/funasr-av-audio2subtitle-prompt-2.json) | FunASR + speech-timestamp prediction | Align a supplied Chinese text to the audio for subtitles | [ComfyUI-AV-FunASR](https://github.com/avenstack/ComfyUI-AV-FunASR), [ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) | As above plus `iic/speech_timestamp_prediction-v1-16k-offline` | ~2-4 GB | As above | not yet tested |

### Mega-ASR

Folder [`Mega-ASR/`](Mega-ASR) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [mega-asr-transcribe](Mega-ASR/mega-asr-transcribe.json) | Mega-ASR (Qwen3-ASR derivative) | Transcribe audio | [ComfyUI-Mega-ASR](https://github.com/starsFriday/ComfyUI-Mega-ASR), [ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) | [zhifeixie/Mega-ASR](https://huggingface.co/zhifeixie/Mega-ASR) to `models/Mega-ASR` | ~4-6 GB | Check model card; pack Apache-2.0 | not yet tested |

### MOSS

Folder [`MOSS/`](MOSS) — 2 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [moss-transcribe-diarize-basic](MOSS/moss-transcribe-diarize-basic.json) | MOSS-Transcribe-Diarize (0.9B class) | Multi-speaker transcription with speaker labels, hotwords and SRT export | [comfyui-MOSS-Transcribe-Diarize-T8](https://github.com/T8mars/comfyui-MOSS-Transcribe-Diarize-T8) | Download script in the pack to `models/moss_transcribe_diarize` | ~4 GB short clips, 12 GB+ recommended | Model licence not confirmed; pack Apache-2.0 | not yet tested |
| [moss-transcribe-diarize-long-audio](MOSS/moss-transcribe-diarize-long-audio.json) | MOSS-Transcribe-Diarize | Chunked long-audio run with a quality gate and diagnostics | [comfyui-MOSS-Transcribe-Diarize-T8](https://github.com/T8mars/comfyui-MOSS-Transcribe-Diarize-T8) | As above | ~5-12 GB (5-10 min clips) | Model licence not confirmed; pack Apache-2.0 | not yet tested |

### Multi-Model

Folder [`Multi-Model/`](Multi-Model) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [tts-audio-suite-asr-to-srt-granite-qwen3](Multi-Model/tts-audio-suite-asr-to-srt-granite-qwen3.json) | Qwen3-ASR or IBM Granite Speech 4.0 1B | ASR, punctuation/truecase and SRT builder; Granite can also translate speech | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Auto-download to `models/TTS/` | ~4-6 GB | Qwen3-ASR Apache-2.0; Granite Apache-2.0 (commercial OK) | not yet tested |

### Nemotron

Folder [`Nemotron/`](Nemotron) — 2 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [nemotron-asr-transcribe-server](Nemotron/nemotron-asr-transcribe-server.json) | Nemotron ASR streaming | Send audio to a local NeMo-Speech.cpp server and get text | [comfyui_nemotron_asr](https://github.com/Rakeshcool/comfyui_nemotron_asr) | None in ComfyUI: run a NeMo-Speech.cpp server at `http://127.0.0.1:8080` | On the server | NVIDIA Open Model License (check card); pack MIT | not yet tested |
| [nemotron-asr-live-microphone](Nemotron/nemotron-asr-live-microphone.json) | Nemotron ASR streaming | Live microphone transcription through the server | [comfyui_nemotron_asr](https://github.com/Rakeshcool/comfyui_nemotron_asr) | As above | On the server | NVIDIA Open Model License (check card) | not yet tested |

### Parakeet

Folder [`Parakeet/`](Parakeet) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [parakeet-tdt-0.6b-v2-subtitles-with-kokoro](Parakeet/parakeet-tdt-0.6b-v2-subtitles-with-kokoro.json) | Parakeet-TDT 0.6B v2 (English) + Kokoro | Kokoro speaks text, Parakeet transcribes it with word timestamps and subtitles a video | [ComfyUI_parakeet-tdt](https://github.com/billwuhao/ComfyUI_parakeet-tdt), [ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite), [ComfyUI_KokoroTTS_MW](https://github.com/billwuhao/ComfyUI_KokoroTTS_MW), [ComfyUI_AudioTools](https://github.com/billwuhao/ComfyUI_AudioTools) | [parakeet-tdt-0.6b-v2.nemo](https://huggingface.co/nvidia/parakeet-tdt-0.6b-v2) to `models/TTS`. v3 is not supported | ~2-4 GB | Model CC-BY-4.0 (commercial OK with attribution); pack Apache-2.0 | not yet tested |

### Qwen3-ASR

Folder [`Qwen3-ASR/`](Qwen3-ASR) — 4 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [qwen3-asr-0.6b-transcribe](Qwen3-ASR/qwen3-asr-0.6b-transcribe.json) | Qwen3-ASR 0.6B + Forced Aligner | Transcribe audio (52 languages incl. Hindi) with optional timestamps | [ComfyUI-QwenASR](https://github.com/1038lab/ComfyUI-QwenASR) | Auto-download `Qwen/Qwen3-ASR-0.6B-hf` + `Qwen/Qwen3-ForcedAligner-0.6B-hf` to `models/Qwen3-ASR/` | ~2-4 GB | Model Apache-2.0 (commercial OK); pack GPL-3.0 | not yet tested |
| [qwen3-asr-0.6b-subtitles](Qwen3-ASR/qwen3-asr-0.6b-subtitles.json) | Qwen3-ASR 0.6B + Forced Aligner | Transcribe to timestamped subtitles | [ComfyUI-QwenASR](https://github.com/1038lab/ComfyUI-QwenASR) | As above | ~2-4 GB | Model Apache-2.0 (commercial OK); pack GPL-3.0 | not yet tested |
| [qwen3-asr-1.7b-transcribe](Qwen3-ASR/qwen3-asr-1.7b-transcribe.json) | Qwen3-ASR 1.7B | Transcribe audio with the larger model | [ComfyUI-Qwen3-ASR](https://github.com/DarioFT/ComfyUI-Qwen3-ASR) | [Qwen/Qwen3-ASR-1.7B](https://huggingface.co/Qwen/Qwen3-ASR-1.7B) to `models/Qwen3-ASR/` | ~4-6 GB | Model Apache-2.0 (commercial OK); pack Apache-2.0. Do not install together with Aero-Ex/ComfyUI-Qwen3ASR (same node names) | not yet tested |
| [qwen3-asr-transcribe-with-forced-aligner-config](Qwen3-ASR/qwen3-asr-transcribe-with-forced-aligner-config.json) | Qwen3-ASR 0.6B / 1.7B + Forced Aligner | Transcribe with word timestamps (bf16/fp16, FlashAttention2) | [ComfyUI-Qwen3-ASR](https://github.com/kaushiknishchay/ComfyUI-Qwen3-ASR) | Manual download to `models/diffusion_models/Qwen3-ASR/<name>/` | ~2-6 GB | Model Apache-2.0 (commercial OK); pack MIT | not yet tested |

### SenseVoice

Folder [`SenseVoice/`](SenseVoice) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [sensevoice-small-asr-and-cosyvoice](SenseVoice/sensevoice-small-asr-and-cosyvoice.json) | SenseVoiceSmall + CosyVoice 300M | Speech recognition with language, emotion and event tags, plus CosyVoice TTS | [ComfyUI-FunAudioLLM](https://github.com/SpenserCai/ComfyUI-FunAudioLLM), [ComfyUI-Custom-Scripts](https://github.com/pythongosssss/ComfyUI-Custom-Scripts), [was-node-suite-comfyui](https://github.com/WASasquatch/was-node-suite-comfyui) | Auto-download | ~4-8 GB | **FunASR model licence (custom; check commercial terms)**; pack has no licence file, last updated 2024-11 | not yet tested |

### Whisper

Folder [`Whisper/`](Whisper) — 6 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [whisper-video-to-subtitles-srt](Whisper/whisper-video-to-subtitles-srt.json) | Whisper large-v3 / turbo / medium / small / base / tiny | Transcribe a video, save an SRT and burn subtitles into frames (model size is a widget choice) | [ComfyUI-Whisper](https://github.com/yuvraj108c/ComfyUI-Whisper), [ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite) | Auto-download to `models/stt/whisper` | ~10 GB large-v3, ~6 GB turbo, ~2 GB small | Model MIT (commercial OK); pack has no licence file | not yet tested |
| [whisper-large-v3-transcribe-audio-or-video](Whisper/whisper-large-v3-transcribe-audio-or-video.json) | Whisper large-v3 (transformers) | Transcribe one audio or video file | [ComfyUI-TranscriptionTools](https://github.com/royceschultz/ComfyUI-TranscriptionTools) | Auto-download [openai/whisper-large-v3](https://huggingface.co/openai/whisper-large-v3) to the HF cache | ~5-10 GB | Model MIT (commercial OK); pack has no licence file | not yet tested |
| [whisper-large-v3-batch-transcribe](Whisper/whisper-large-v3-batch-transcribe.json) | Whisper large-v3 (transformers) | Batch-transcribe a folder of files | [ComfyUI-TranscriptionTools](https://github.com/royceschultz/ComfyUI-TranscriptionTools) | As above | ~5-10 GB | Model MIT (commercial OK) | not yet tested |
| [whisper-transcribe-to-srt-vtt](Whisper/whisper-transcribe-to-srt-vtt.json) | Whisper large | Transcribe audio to text, SRT and VTT (set the output paths; the example holds the author's Windows paths) | [ComfyUI-whisper](https://github.com/woqiyoni/ComfyUI-whisper), [ComfyUI-Custom-Scripts](https://github.com/pythongosssss/ComfyUI-Custom-Scripts) | Auto-download | ~10 GB | Model MIT; pack has no licence file | not yet tested |
| [whisper-large-v3-chinese-subtitles-to-video](Whisper/whisper-large-v3-chinese-subtitles-to-video.json) | Belle-whisper-large-v3-zh (CTranslate2) | Chinese ASR with static or karaoke-style subtitles burned into video | [ComfyUI_ASR-zh](https://github.com/billwuhao/ComfyUI_ASR-zh), [ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite), [ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) | See pack README | ~5 GB | Model per its card; pack Apache-2.0 | not yet tested |
| [faster-whisper-transcribe-to-subtitles](Whisper/faster-whisper-transcribe-to-subtitles.json) | faster-whisper (large-v2, CTranslate2) | Fast transcription to a subtitle file | [ComfyUI-faster-whisper](https://github.com/ai-joe-git/ComfyUI-faster-whisper) | Auto-download | ~3-5 GB | Model MIT (commercial OK); pack MIT | not yet tested |

See the [Audio overview](../../README.md) for the full category map and model coverage, the [main README](../../../README.md) for setup steps, or [`00-LIBRARY-INDEX.md`](../../../00-LIBRARY-INDEX.md) for the full list of workflows.
