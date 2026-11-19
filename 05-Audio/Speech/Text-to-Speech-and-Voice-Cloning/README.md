# Text-to-Speech and Voice Cloning — ComfyUI workflows

Text-to-speech, voice cloning, voice design and custom voices, multi-speaker dialogue, expressive / emotion control, speech editing and voice-model training: 110 workflows in 38 model-family folders. Voice conversion, speech clean-up, speech-to-text, translation and alignment are in the sibling folders listed in the [Speech README](../README.md).

| Model family folder | Workflows |
|---|---|
| [`Bark/`](#bark) | 1 |
| [`Chatterbox/`](#chatterbox) | 6 |
| [`ChatTTS/`](#chattts) | 1 |
| [`CosyVoice/`](#cosyvoice) | 10 |
| [`Dia/`](#dia) | 5 |
| [`DramaBox/`](#dramabox) | 1 |
| [`ElevenLabs/`](#elevenlabs) | 4 |
| [`F5-TTS/`](#f5-tts) | 5 |
| [`FireRedTTS/`](#fireredtts) | 1 |
| [`Fish-Speech/`](#fish-speech) | 8 |
| [`GPT-SoVITS/`](#gpt-sovits) | 2 |
| [`Higgs-Audio/`](#higgs-audio) | 2 |
| [`IndexTTS/`](#indextts) | 7 |
| [`Kani-TTS/`](#kani-tts) | 1 |
| [`Kitten-TTS/`](#kitten-tts) | 1 |
| [`Kokoro/`](#kokoro) | 1 |
| [`Kyutai/`](#kyutai) | 1 |
| [`MARS5/`](#mars5) | 1 |
| [`MaskGCT/`](#maskgct) | 1 |
| [`Maya/`](#maya) | 4 |
| [`MeloTTS/`](#melotts) | 1 |
| [`MisoTTS/`](#misotts) | 1 |
| [`MOSS/`](#moss) | 4 |
| [`Multi-Model/`](#multi-model) | 1 |
| [`NeuTTS/`](#neutts) | 1 |
| [`OmniVoice/`](#omnivoice) | 2 |
| [`OpenVoice/`](#openvoice) | 1 |
| [`Orpheus/`](#orpheus) | 2 |
| [`Parler-TTS/`](#parler-tts) | 1 |
| [`Qwen3-TTS/`](#qwen3-tts) | 11 |
| [`Sesame-CSM/`](#sesame-csm) | 4 |
| [`Spark-TTS/`](#spark-tts) | 1 |
| [`Step-Audio/`](#step-audio) | 2 |
| [`Supertonic/`](#supertonic) | 1 |
| [`VibeVoice/`](#vibevoice) | 5 |
| [`VoxCPM/`](#voxcpm) | 3 |
| [`ZipVoice/`](#zipvoice) | 1 |
| [`Zonos/`](#zonos) | 5 |

## Notes

- Status / test notes are carried over unchanged from the earlier library README. Rows whose VRAM, licence or status read "—" / "not recorded" had no such data recorded (they came from an earlier four-column table).
- The speech workflows below were collected from their node packs' official example workflows and Comfy-Org templates. They are checked only as loadable ComfyUI workflow files: none has been run yet, so each is marked **not yet tested**. VRAM figures are rough estimates. API workflows (ElevenLabs, Fish Audio) need a Comfy.org account and paid API credits.
- Added after reading the 19 November 2026 *Open Speech Model Atlas* (122 TTS entries, 145 STT / ASR entries, 42 supporting tools) and comparing it with the library: 57 text-to-speech, voice-design, voice-conversion and speech clean-up workflows and 8 speech-to-text, diarisation, speech-translation and alignment workflows. Every file is a published example workflow from its node pack, saved unmodified. They were only checked as loadable ComfyUI JSON (valid UI format, every link resolves, every custom node type found in the named pack's source unless noted) and nothing was run, so all are marked **not yet tested**. No weights were downloaded: the weight links and folders come from each pack's README and may change. VRAM figures are the pack authors' numbers or rough estimates.
Things to know before running them:
  - Every Load Audio node holds the author's sample file name: pick your own reference clip.
  - Four files contain author-local paths (`kyutai-tts`, `maskgct-tts`, `audio-srt-aligner-overlay`, `voicebridge-speech-translation`); the table row says which widget to change.
  - Many of these packs are new, small or have no licence file. **Non-commercial or restricted weights** are in bold in the Licence column. Voice cloning needs the consent of the person whose voice you clone.
  - TTS-Audio-Suite and several single-model packs install their own dependencies (some need Transformers 5 or an isolated runtime); install one pack at a time and read its README.

## Find by task

Each workflow lives in one model-family folder; this index lists the same files by what they do (a workflow can appear under more than one task; the main tables below are authoritative).

- **Voice design and custom voices** (12): [qwen3-tts-custom-voice](Qwen3-TTS/qwen3-tts-custom-voice.json), [qwen3-tts-voice-design-dialogue](Qwen3-TTS/qwen3-tts-voice-design-dialogue.json), [qwen3-tts-voice-design-save-voice](Qwen3-TTS/qwen3-tts-voice-design-save-voice.json), [qwen3-tts-voice-design](Qwen3-TTS/qwen3-tts-voice-design.json), [qwen3-tts-1038lab-create-your-voice](Qwen3-TTS/qwen3-tts-1038lab-create-your-voice.json), [qwen3-tts-tts-audio-suite-voice-design-asr-srt](Qwen3-TTS/qwen3-tts-tts-audio-suite-voice-design-asr-srt.json), [parler-tts-described-voice](Parler-TTS/parler-tts-described-voice.json), [voice-designer-moss-omnivoice-qwen](Multi-Model/voice-designer-moss-omnivoice-qwen.json), [moss-voicegenerator-voice-design](MOSS/moss-voicegenerator-voice-design.json), [spark-tts-create-clone](Spark-TTS/spark-tts-create-clone.json), [zonos3-design-voice](Zonos/zonos3-design-voice.json), [maya1-tts](Maya/maya1-tts.json)
- **Multi-speaker dialogue** (25): [fish-s2-multi-speaker-dialogue-tts](Fish-Speech/fish-s2-multi-speaker-dialogue-tts.json), [qwen3-tts-voice-clone-saved-multi-voice-dialogue](Qwen3-TTS/qwen3-tts-voice-clone-saved-multi-voice-dialogue.json), [qwen3-tts-voice-design-dialogue](Qwen3-TTS/qwen3-tts-voice-design-dialogue.json), [fish-s2-pro-tts-audio-suite-srt-characters](Fish-Speech/fish-s2-pro-tts-audio-suite-srt-characters.json), [dia-1.6b-dialogue-tts](Dia/dia-1.6b-dialogue-tts.json), [dia-1.6b-voice-clone](Dia/dia-1.6b-voice-clone.json), [dia-1.6b-tts-with-audio-retimer](Dia/dia-1.6b-tts-with-audio-retimer.json), [dia-1.6b-safetensors-loader](Dia/dia-1.6b-safetensors-loader.json), [dia2-tts-and-captions](Dia/dia2-tts-and-captions.json), [sesame-csm-1b-dialogue-clone](Sesame-CSM/sesame-csm-1b-dialogue-clone.json), [sesame-csm-1b-saved-speakers-dialogue](Sesame-CSM/sesame-csm-1b-saved-speakers-dialogue.json), [chatterbox-dialogue-tts](Chatterbox/chatterbox-dialogue-tts.json), [chatterbox-wildminder-tts-dialogue-srt-vc](Chatterbox/chatterbox-wildminder-tts-dialogue-srt-vc.json), [vibevoice-multi-speaker-podcast](VibeVoice/vibevoice-multi-speaker-podcast.json), [vibevoice-tts-audio-suite-srt-characters](VibeVoice/vibevoice-tts-audio-suite-srt-characters.json), [elevenlabs-api-text-to-dialogue](ElevenLabs/elevenlabs-api-text-to-dialogue.json), [elevenlabs-api-v4-text-to-dialogue](ElevenLabs/elevenlabs-api-v4-text-to-dialogue.json), [fish-audio-api-drama-3-dialogue](Fish-Speech/fish-audio-api-drama-3-dialogue.json), [fish-audio-api-drama-3-directed](Fish-Speech/fish-audio-api-drama-3-directed.json), [moss-tts-v15-dialogue](MOSS/moss-tts-v15-dialogue.json), [moss-ttsd-dialogue](MOSS/moss-ttsd-dialogue.json), [higgs-audio-v3-clone-multispeaker](Higgs-Audio/higgs-audio-v3-clone-multispeaker.json), [indextts-1.5-dialogue](IndexTTS/indextts-1.5-dialogue.json), [indextts-2.5-dialogue](IndexTTS/indextts-2.5-dialogue.json), [dramabox-tts-audio-suite](DramaBox/dramabox-tts-audio-suite.json)
- **Voice cloning** (36): [fish-s2-voice-clone-tts](Fish-Speech/fish-s2-voice-clone-tts.json), [qwen3-tts-voice-clone-load-saved-voice](Qwen3-TTS/qwen3-tts-voice-clone-load-saved-voice.json), [qwen3-tts-voice-clone-save-voice](Qwen3-TTS/qwen3-tts-voice-clone-save-voice.json), [qwen3-tts-voice-clone-saved-multi-voice-dialogue](Qwen3-TTS/qwen3-tts-voice-clone-saved-multi-voice-dialogue.json), [qwen3-tts-voice-clone](Qwen3-TTS/qwen3-tts-voice-clone.json), [qwen3-tts-1038lab-voice-clone-with-asr](Qwen3-TTS/qwen3-tts-1038lab-voice-clone-with-asr.json), [cosyvoice-300m-zero-shot-voice-clone](CosyVoice/cosyvoice-300m-zero-shot-voice-clone.json), [cosyvoice-300m-cross-lingual-clone](CosyVoice/cosyvoice-300m-cross-lingual-clone.json), [f5-tts-voice-clone](F5-TTS/f5-tts-voice-clone.json), [f5-tts-voice-clone-whisper-auto-transcript](F5-TTS/f5-tts-voice-clone-whisper-auto-transcript.json), [dia-1.6b-voice-clone](Dia/dia-1.6b-voice-clone.json), [sesame-csm-1b-context-voice-clone](Sesame-CSM/sesame-csm-1b-context-voice-clone.json), [sesame-csm-1b-dialogue-clone](Sesame-CSM/sesame-csm-1b-dialogue-clone.json), [voxcpm-tts-and-voice-clone](VoxCPM/voxcpm-tts-and-voice-clone.json), [voxcpm2-tts-clone-and-lora](VoxCPM/voxcpm2-tts-clone-and-lora.json), [fish-audio-api-voice-clone-tts](Fish-Speech/fish-audio-api-voice-clone-tts.json), [moss-tts-v15-clone-continue](MOSS/moss-tts-v15-clone-continue.json), [higgs-audio-v3-clone-multispeaker](Higgs-Audio/higgs-audio-v3-clone-multispeaker.json), [indextts-1.5-voice-clone](IndexTTS/indextts-1.5-voice-clone.json), [indextts-2.5-basic-clone](IndexTTS/indextts-2.5-basic-clone.json), [spark-tts-create-clone](Spark-TTS/spark-tts-create-clone.json), [orpheus-voice-clone](Orpheus/orpheus-voice-clone.json), [cosyvoice2-zeroshot](CosyVoice/cosyvoice2-zeroshot.json), [cosyvoice2-crosslingual](CosyVoice/cosyvoice2-crosslingual.json), [gpt-sovits-v2-tts](GPT-SoVITS/gpt-sovits-v2-tts.json), [gpt-sovits-v2-finetune](GPT-SoVITS/gpt-sovits-v2-finetune.json), [zonos-v0.1-emotion-voice-clone](Zonos/zonos-v0.1-emotion-voice-clone.json), [zonos3-clone-voice](Zonos/zonos3-clone-voice.json), [maya3-indic-tts-voice-clone](Maya/maya3-indic-tts-voice-clone.json), [maya3-indic-voice-clone-auto-transcribe](Maya/maya3-indic-voice-clone-auto-transcribe.json), [zipvoice-en](ZipVoice/zipvoice-en.json), [maskgct-tts](MaskGCT/maskgct-tts.json), [neutts-clone](NeuTTS/neutts-clone.json), [mars5-uvr5](MARS5/mars5-uvr5.json), [misotts](MisoTTS/misotts.json), [step-audio-editx-clone](Step-Audio/step-audio-editx-clone.json)
- **Speech editing, emotion and expressive control** (14): [cosyvoice-300m-instruct](CosyVoice/cosyvoice-300m-instruct.json), [f5-tts-tts-audio-suite-speech-editor](F5-TTS/f5-tts-tts-audio-suite-speech-editor.json), [bark-text-to-speech](Bark/bark-text-to-speech.json), [vibevoice-pause-tags](VibeVoice/vibevoice-pause-tags.json), [index-tts2-emotion-control](IndexTTS/index-tts2-emotion-control.json), [index-tts2-tts-audio-suite-emotion-srt](IndexTTS/index-tts2-tts-audio-suite-emotion-srt.json), [higgs-audio-v3-clone-multispeaker](Higgs-Audio/higgs-audio-v3-clone-multispeaker.json), [higgs-audio-v3-tts-audio-suite](Higgs-Audio/higgs-audio-v3-tts-audio-suite.json), [cosyvoice2-instruct](CosyVoice/cosyvoice2-instruct.json), [zonos-v0.1-emotion-voice-clone](Zonos/zonos-v0.1-emotion-voice-clone.json), [zonos2-tts-emotion](Zonos/zonos2-tts-emotion.json), [step-audio-editx-clone](Step-Audio/step-audio-editx-clone.json), [step-audio-editx-edit](Step-Audio/step-audio-editx-edit.json), [dramabox-tts-audio-suite](DramaBox/dramabox-tts-audio-suite.json)
- **Voice model training (LoRA / fine-tune)** (3): [voxcpm-lora-training](VoxCPM/voxcpm-lora-training.json), [voxcpm2-tts-clone-and-lora](VoxCPM/voxcpm2-tts-clone-and-lora.json), [gpt-sovits-v2-finetune](GPT-SoVITS/gpt-sovits-v2-finetune.json)

## Workflows by model family

### Bark

Folder [`Bark/`](Bark) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [bark-text-to-speech](Bark/bark-text-to-speech.json) | Bark (Suno) | Text to speech with laughs, music and non-speech sounds | [ComfyUI-audio-nodes](https://github.com/gitmylo/ComfyUI-audio-nodes) | Auto-download [GitMylo/bark-safetensors](https://huggingface.co/GitMylo/bark-safetensors) | ~6-12 GB | Model MIT (commercial OK); pack has no licence file | not yet tested |

### Chatterbox

Folder [`Chatterbox/`](Chatterbox) — 6 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [chatterbox-text-to-speech](Chatterbox/chatterbox-text-to-speech.json) | Chatterbox (Resemble AI) | Text to speech with optional voice clone (official Comfy template) | [ComfyUI_Fill-ChatterBox](https://github.com/filliptm/ComfyUI_Fill-ChatterBox) | Auto-download to `models/chatterbox/` | 8 GB+ recommended | Model MIT (commercial OK); outputs watermarked; upstream retired Aug 2026 | not yet tested |
| [chatterbox-dialogue-tts](Chatterbox/chatterbox-dialogue-tts.json) | Chatterbox | Two-speaker dialogue (official Comfy template) | [ComfyUI_Fill-ChatterBox](https://github.com/filliptm/ComfyUI_Fill-ChatterBox) | As above | 8 GB+ | Model MIT (commercial OK) | not yet tested |
| [chatterbox-multilingual-tts](Chatterbox/chatterbox-multilingual-tts.json) | Chatterbox Multilingual (23 languages incl. Hindi) | Multilingual TTS with voice clone (official Comfy template) | [ComfyUI_Fill-ChatterBox](https://github.com/filliptm/ComfyUI_Fill-ChatterBox) | As above | 8 GB+ | Model MIT (commercial OK) | not yet tested |
| [chatterbox-fill-all-modes-incl-turbo](Chatterbox/chatterbox-fill-all-modes-incl-turbo.json) | Chatterbox, Turbo, Multilingual, VC | All Fill-ChatterBox nodes in one graph, including Turbo | [ComfyUI_Fill-ChatterBox](https://github.com/filliptm/ComfyUI_Fill-ChatterBox) | As above | 8 GB+ | Model MIT (commercial OK) | not yet tested |
| [chatterbox-wildminder-tts-dialogue-srt-vc](Chatterbox/chatterbox-wildminder-tts-dialogue-srt-vc.json) | Chatterbox, Multilingual, Turbo | TTS, multilingual, dialogue, SRT timing and voice conversion | [ComfyUI-Chatterbox](https://github.com/wildminder/ComfyUI-Chatterbox) | Auto-download [ResembleAI/chatterbox](https://huggingface.co/ResembleAI/chatterbox) to `models/tts/chatterbox/` (~2.5 GB each) | ~6-8 GB | Model MIT (commercial OK); pack Apache-2.0 | not yet tested |
| [chatterbox-tts-audio-suite-voice-changer](Chatterbox/chatterbox-tts-audio-suite-voice-changer.json) | Chatterbox | Character voices TTS and voice changer | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Auto-download to `models/TTS/` | ~6-8 GB | Model MIT (commercial OK) | not yet tested |

### ChatTTS

Folder [`ChatTTS/`](ChatTTS) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [chattts-text-to-speech](ChatTTS/chattts-text-to-speech.json) | ChatTTS | Conversational text to speech with sampled speakers | [ComfyUI-ChatTTS](https://github.com/neverbiasu/ComfyUI-ChatTTS) | ChatTTS weights to `models/chattts/` | ~4 GB | **Weights CC-BY-NC-4.0 (non-commercial)**; pack MIT | not yet tested |

### CosyVoice

Folder [`CosyVoice/`](CosyVoice) — 10 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [cosyvoice-300m-zero-shot-voice-clone](CosyVoice/cosyvoice-300m-zero-shot-voice-clone.json) | CosyVoice 300M (v1) | Zero-shot voice clone from a 3 s reference | [CosyVoice-ComfyUI](https://github.com/AIFSH/CosyVoice-ComfyUI) | Auto-download from ModelScope `iic/CosyVoice-300M` into the pack's `pretrained_models/` | ~4-8 GB (tested on 11 GB) | Model Apache-2.0 (commercial OK); pack Apache-2.0; pack last updated 2024-09 | not yet tested |
| [cosyvoice-300m-cross-lingual-clone](CosyVoice/cosyvoice-300m-cross-lingual-clone.json) | CosyVoice 300M (v1) | Cross-lingual voice clone (speak another language in the reference voice) | [CosyVoice-ComfyUI](https://github.com/AIFSH/CosyVoice-ComfyUI) | Auto-download `iic/CosyVoice-300M` | ~4-8 GB | Model Apache-2.0 (commercial OK) | not yet tested |
| [cosyvoice-300m-instruct](CosyVoice/cosyvoice-300m-instruct.json) | CosyVoice 300M-Instruct (v1) | Instruct TTS: speaker, emotion and style from a text instruction | [CosyVoice-ComfyUI](https://github.com/AIFSH/CosyVoice-ComfyUI) | Auto-download `iic/CosyVoice-300M-Instruct` | ~4-8 GB | Model Apache-2.0 (commercial OK) | not yet tested |
| [cosyvoice-300m-sft-preset-speakers](CosyVoice/cosyvoice-300m-sft-preset-speakers.json) | CosyVoice 300M-SFT (v1) | TTS with built-in preset speakers | [CosyVoice-ComfyUI](https://github.com/AIFSH/CosyVoice-ComfyUI) | Auto-download `iic/CosyVoice-300M-SFT` | ~4-8 GB | Model Apache-2.0 (commercial OK) | not yet tested |
| [cosyvoice3-all-modes](CosyVoice/cosyvoice3-all-modes.json) | CosyVoice3 0.5B | Zero-shot, cross-lingual, dialogue and voice conversion | [ComfyUI_FL-CosyVoice3](https://github.com/filliptm/ComfyUI_FL-CosyVoice3) | [FunAudioLLM/Fun-CosyVoice3-0.5B-2512](https://huggingface.co/FunAudioLLM/Fun-CosyVoice3-0.5B-2512) to `models/cosyvoice/`; Python 3.10; the sample is a video file in a Load Audio node | ~8-16 GB | Weights Apache-2.0; pack licence not declared on GitHub | not yet tested |
| [cosyvoice3-ts-examples](CosyVoice/cosyvoice3-ts-examples.json) | CosyVoice3 0.5B | Instruct, voice conversion, cross-lingual, dialogue and saved speakers | [comfyui-ts-cosyvoice](https://github.com/AlexYez/comfyui-ts-cosyvoice) | As above, plus `speaker/` and `whisper/` subfolders; needs ffmpeg | ~5 GB | Weights Apache-2.0; pack MIT; sample in Russian | not yet tested |
| [cosyvoice2-basic](CosyVoice/cosyvoice2-basic.json) | CosyVoice2 0.5B | Basic CosyVoice2 text to speech with a reference voice | [ComfyUI_CosyVoice2](https://github.com/HJH-AILab/ComfyUI_CosyVoice2) | [FunAudioLLM/CosyVoice2-0.5B](https://huggingface.co/FunAudioLLM/CosyVoice2-0.5B) | ~4-6 GB | Weights Apache-2.0; pack Apache-2.0 | not yet tested |
| [cosyvoice2-zeroshot](CosyVoice/cosyvoice2-zeroshot.json) | CosyVoice2 0.5B | Zero-shot voice clone (3-node graph) | [ComfyUI_NTCosyVoice](https://github.com/muxueChen/ComfyUI_NTCosyVoice) | CosyVoice2-0.5B; model folder per pack README | ~4-6 GB | Weights Apache-2.0; pack licence not declared | not yet tested |
| [cosyvoice2-instruct](CosyVoice/cosyvoice2-instruct.json) | CosyVoice2 0.5B | Instruct2: control style and dialect with a text instruction | [ComfyUI_NTCosyVoice](https://github.com/muxueChen/ComfyUI_NTCosyVoice) | As above | ~4-6 GB | Weights Apache-2.0; pack licence not declared | not yet tested |
| [cosyvoice2-crosslingual](CosyVoice/cosyvoice2-crosslingual.json) | CosyVoice2 0.5B | Cross-lingual clone (speak another language in the reference voice) | [ComfyUI_NTCosyVoice](https://github.com/muxueChen/ComfyUI_NTCosyVoice) | As above | ~4-6 GB | Weights Apache-2.0; pack licence not declared | not yet tested |

### Dia

Folder [`Dia/`](Dia) — 5 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [dia-1.6b-dialogue-tts](Dia/dia-1.6b-dialogue-tts.json) | Dia 1.6B (Nari Labs) | Two-speaker dialogue TTS with [S1]/[S2] tags and non-verbal sounds | [comfyUI-customDia](https://github.com/nobrainX2/comfyUI-customDia) | [nari-labs/Dia-1.6B](https://huggingface.co/nari-labs/Dia-1.6B) `.pth` + `.json` to `models/Dia/` | ~10 GB | Model Apache-2.0 (commercial OK); pack Apache-2.0 | not yet tested |
| [dia-1.6b-voice-clone](Dia/dia-1.6b-voice-clone.json) | Dia 1.6B | Dialogue TTS that clones the voices of a reference clip | [comfyUI-customDia](https://github.com/nobrainX2/comfyUI-customDia) | As above | ~10 GB | Model Apache-2.0 (commercial OK) | not yet tested |
| [dia-1.6b-tts-with-audio-retimer](Dia/dia-1.6b-tts-with-audio-retimer.json) | Dia 1.6B | Dialogue TTS, then stretch the result to a target length | [comfyUI-customDia](https://github.com/nobrainX2/comfyUI-customDia) | As above | ~10 GB | Model Apache-2.0 (commercial OK) | not yet tested |
| [dia-1.6b-safetensors-loader](Dia/dia-1.6b-safetensors-loader.json) | Dia 1.6B | Dialogue TTS with a separate model loader (safetensors) | [ComfyUI-DiaTTS](https://github.com/BobRandomNumber/ComfyUI-DiaTTS) | [nari-labs/Dia-1.6B](https://huggingface.co/nari-labs/Dia-1.6B) `model.safetensors` to `models/diffusion_models/` | ~10 GB | Model Apache-2.0 (commercial OK); pack experimental | not yet tested |
| [dia2-tts-and-captions](Dia/dia2-tts-and-captions.json) | Dia2 2B | Dialogue TTS plus caption generation from audio | [ComfyUI-lethris-dia2](https://github.com/lord-lethris/ComfyUI-lethris-dia2), [rgthree-comfy](https://github.com/rgthree/rgthree-comfy), [ComfyUI-Custom-Scripts](https://github.com/pythongosssss/ComfyUI-Custom-Scripts) | [nari-labs/Dia2-2B](https://huggingface.co/nari-labs/Dia2-2B) `model.safetensors` + `tokenizer.json` to `models/Dia2/` | ~10-12 GB; needs CUDA 12.8+ | Model Apache-2.0 (commercial OK); pack MIT | not yet tested |

### DramaBox

Folder [`DramaBox/`](DramaBox) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [dramabox-tts-audio-suite](DramaBox/dramabox-tts-audio-suite.json) | DramaBox (Resemble AI) | Expressive acted TTS through the unified engine | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Auto-download to `models/TTS/` | not stated | Pack MIT; check the DramaBox licence | not yet tested |

### ElevenLabs

Folder [`ElevenLabs/`](ElevenLabs) — 4 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [elevenlabs-api-text-to-speech](ElevenLabs/elevenlabs-api-text-to-speech.json) | ElevenLabs (API) | Text to speech with voice selector or instant voice clone | none (ComfyUI core API nodes) | None (cloud) | None | paid Comfy API credits; output under provider terms | not yet tested |
| [elevenlabs-api-v4-text-to-speech](ElevenLabs/elevenlabs-api-v4-text-to-speech.json) | ElevenLabs v4 (API) | Text to speech, v4 model | none (ComfyUI core API nodes) | None (cloud) | None | paid Comfy API credits; output under provider terms | not yet tested |
| [elevenlabs-api-text-to-dialogue](ElevenLabs/elevenlabs-api-text-to-dialogue.json) | ElevenLabs (API) | Multi-voice dialogue | none (ComfyUI core API nodes) | None (cloud) | None | paid Comfy API credits; output under provider terms | not yet tested |
| [elevenlabs-api-v4-text-to-dialogue](ElevenLabs/elevenlabs-api-v4-text-to-dialogue.json) | ElevenLabs v4 (API) | Multi-voice dialogue, v4 model | none (ComfyUI core API nodes) | None (cloud) | None | paid Comfy API credits; output under provider terms | not yet tested |

### F5-TTS

Folder [`F5-TTS/`](F5-TTS) — 5 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [f5-tts-voice-clone](F5-TTS/f5-tts-voice-clone.json) | F5-TTS / E2-TTS | Voice clone from a reference clip and its transcript | [ComfyUI-F5-TTS](https://github.com/niknah/ComfyUI-F5-TTS) | Base F5/E2 auto-download ([SWivid/F5-TTS](https://huggingface.co/SWivid/F5-TTS)); extra `.pt` + vocab `.txt` to `models/checkpoints/F5-TTS/` | ~3-6 GB | **Weights CC-BY-NC-4.0 (non-commercial)**; pack MIT | not yet tested |
| [f5-tts-voice-clone-whisper-auto-transcript](F5-TTS/f5-tts-voice-clone-whisper-auto-transcript.json) | F5-TTS + Whisper | Voice clone; Whisper writes the reference transcript | [ComfyUI-F5-TTS](https://github.com/niknah/ComfyUI-F5-TTS), [ComfyUI-Whisper](https://github.com/yuvraj108c/ComfyUI-Whisper) | As above, plus Whisper auto-download to `models/stt/whisper` | ~6-10 GB | **F5 weights CC-BY-NC-4.0 (non-commercial)** | not yet tested |
| [f5-tts-speak-like-a-local-translate](F5-TTS/f5-tts-speak-like-a-local-translate.json) | F5-TTS (language checkpoints) | Translate text, then speak it with a native-language F5 checkpoint | [ComfyUI-F5-TTS](https://github.com/niknah/ComfyUI-F5-TTS), [GF_translate](https://github.com/gorillaframeai/GF_translate), [rgthree-comfy](https://github.com/rgthree/rgthree-comfy) | Language `.pt` + vocab to `models/checkpoints/F5-TTS/` (e.g. Hindi [SPRINGLab/F5-Hindi-24KHz](https://huggingface.co/SPRINGLab/F5-Hindi-24KHz)) | ~3-6 GB | **Check each checkpoint; official F5 weights CC-BY-NC-4.0** | not yet tested |
| [f5-tts-tts-audio-suite-srt-phoneme-normalizer](F5-TTS/f5-tts-tts-audio-suite-srt-phoneme-normalizer.json) | F5-TTS | Character voices, SRT-timed speech and phoneme text normalizer | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Auto-download (~1.2 GB per model) to `models/TTS/` | ~4-6 GB | **F5 weights CC-BY-NC-4.0 (non-commercial)** | not yet tested |
| [f5-tts-tts-audio-suite-speech-editor](F5-TTS/f5-tts-tts-audio-suite-speech-editor.json) | F5-TTS | Speech editor: replace words inside an existing recording | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Auto-download to `models/TTS/` | ~4-6 GB | **F5 weights CC-BY-NC-4.0 (non-commercial)** | not yet tested |

### FireRedTTS

Folder [`FireRedTTS/`](FireRedTTS) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [fireredtts3-all-in-one](FireRedTTS/fireredtts3-all-in-one.json) | FireRedTTS3 | Voice clone, voice design, acoustic edit and semantic (word) edit of speech | [FireRedTTS3-ComfyUI](https://github.com/Saganaki22/FireRedTTS3-ComfyUI) | [FireRedTeam/FireRedTTS3](https://huggingface.co/FireRedTeam/FireRedTTS3) (or bf16 / int8 repacks) to `models/fireredtts3/` | ~14 GB | Weights Apache-2.0; pack MIT | not yet tested |

### Fish-Speech

Folder [`Fish-Speech/`](Fish-Speech) — 8 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [fish-s2-multi-speaker-dialogue-tts](Fish-Speech/fish-s2-multi-speaker-dialogue-tts.json) | — | Multi-Speaker Dialogue TTS | ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use, comfyui-fish-audio-s2 | — | — | — | not recorded |
| [fish-s2-text-to-speech](Fish-Speech/fish-s2-text-to-speech.json) | — | Text to Speech | ComfyUI-Easy-Use, comfyui-fish-audio-s2 | — | — | — | not recorded |
| [fish-s2-voice-clone-tts](Fish-Speech/fish-s2-voice-clone-tts.json) | — | Voice Clone TTS | ComfyUI-VideoHelperSuite, ComfyUI-Easy-Use, comfyui-fish-audio-s2 | — | — | — | not recorded |
| [fish-s2-pro-tts-audio-suite-srt-characters](Fish-Speech/fish-s2-pro-tts-audio-suite-srt-characters.json) | Fish Audio S2-Pro | Multi-character voices and SRT-timed speech through the unified engine | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | S2-Pro to `models/TTS/fish_audio_s2_pro/` (BF16, FP8 or INT8/NF4 at load) | ~12-24 GB (less quantised) | **Fish Audio Research License (non-commercial without a licence)** | not yet tested |
| [fish-audio-api-s2-text-to-speech](Fish-Speech/fish-audio-api-s2-text-to-speech.json) | Fish Audio S2 (API) | Text to speech with voice selector | none (ComfyUI core API nodes) | None (cloud) | None | paid Comfy API credits; output under provider terms | not yet tested |
| [fish-audio-api-voice-clone-tts](Fish-Speech/fish-audio-api-voice-clone-tts.json) | Fish Audio (API) | Instant voice clone, then speak | none (ComfyUI core API nodes) | None (cloud) | None | paid Comfy API credits; output under provider terms | not yet tested |
| [fish-audio-api-drama-3-dialogue](Fish-Speech/fish-audio-api-drama-3-dialogue.json) | Fish Audio Drama 3 (API) | Multi-character drama dialogue | none (ComfyUI core API nodes) | None (cloud) | None | paid Comfy API credits; output under provider terms | not yet tested |
| [fish-audio-api-drama-3-directed](Fish-Speech/fish-audio-api-drama-3-directed.json) | Fish Audio Drama 3 (API) | Directed performance with acting instructions | none (ComfyUI core API nodes) | None (cloud) | None | paid Comfy API credits; output under provider terms | not yet tested |

### GPT-SoVITS

Folder [`GPT-SoVITS/`](GPT-SoVITS) — 2 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [gpt-sovits-v2-tts](GPT-SoVITS/gpt-sovits-v2-tts.json) | GPT-SoVITS v2 | Few-shot TTS from a reference clip and its text | [GSTTS-ComfyUI](https://github.com/AIFSH/GSTTS-ComfyUI) | [lj1995/GPT-SoVITS](https://huggingface.co/lj1995/GPT-SoVITS) into the pack's model folder; needs ffmpeg; pack from 2024, v2 only | ~4 GB | Weights MIT; pack MIT | not yet tested |
| [gpt-sovits-v2-finetune](GPT-SoVITS/gpt-sovits-v2-finetune.json) | GPT-SoVITS v2 | Dataset chain (ASR, slicing, labelling) and fine-tuning of your own voice model | [GSTTS-ComfyUI](https://github.com/AIFSH/GSTTS-ComfyUI) | As above | ~8 GB+ | Weights MIT; pack MIT | not yet tested |

### Higgs-Audio

Folder [`Higgs-Audio/`](Higgs-Audio) — 2 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [higgs-audio-v3-clone-multispeaker](Higgs-Audio/higgs-audio-v3-clone-multispeaker.json) | Higgs Audio v3 (4B, Boson AI) | Generation, voice clone and multi-speaker speech; Whisper transcribes the reference | [Higgs_v3-TTS-ComfyUI](https://github.com/Saganaki22/Higgs_v3-TTS-ComfyUI) | [bosonai/higgs-audio-v3-tts-4b](https://huggingface.co/bosonai/higgs-audio-v3-tts-4b) to `models/higgsv3tts/higgs-audio-v3-tts-4b/` | ~11 GB | **Weights: Boson research / non-commercial licence**; pack MIT | not yet tested |
| [higgs-audio-v3-tts-audio-suite](Higgs-Audio/higgs-audio-v3-tts-audio-suite.json) | Higgs Audio v3 | Inline emotion, style, prosody and sound-effect tags plus SRT timing | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Auto-download to `models/TTS/` (~8 GB) | ~8 GB | **Weights non-commercial**; pack MIT | not yet tested |

### IndexTTS

Folder [`IndexTTS/`](IndexTTS) — 7 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [index-tts2-emotion-control](IndexTTS/index-tts2-emotion-control.json) | IndexTTS-2 (bilibili) | Voice clone with emotion from audio, text or an emotion vector | [ComfyUI-IndexTTS2](https://github.com/snicolast/ComfyUI-IndexTTS2) (archived) | [IndexTeam/IndexTTS-2](https://huggingface.co/IndexTeam/IndexTTS-2) into the pack's `checkpoints/` | ~8-12 GB | **bilibili IndexTTS licence (check commercial terms)** | not yet tested |
| [index-tts2-tts-audio-suite-emotion-srt](IndexTTS/index-tts2-tts-audio-suite-emotion-srt.json) | IndexTTS-2 | Emotion-controlled character voices and SRT timing (maintained pack) | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Auto-download to `models/TTS/` | ~8-12 GB | **bilibili IndexTTS licence (check commercial terms)** | not yet tested |
| [indextts-1.5-voice-clone](IndexTTS/indextts-1.5-voice-clone.json) | IndexTTS 1.5 | Voice clone from a reference clip | [ComfyUI_IndexTTS](https://github.com/billwuhao/ComfyUI_IndexTTS) | [IndexTeam/IndexTTS-1.5](https://huggingface.co/IndexTeam/IndexTTS-1.5) (`gpt.pth`, `bigvgan_generator.pth`, `bpe.model`); folder per pack README; text normalisation needs `pynini` | ~6-8 GB | Weights Apache-2.0 (1.0 / 1.5); pack Apache-2.0; sample names Chinese | not yet tested |
| [indextts-1.5-dialogue](IndexTTS/indextts-1.5-dialogue.json) | IndexTTS 1.5 | Two-person dialogue with cloned voices | [ComfyUI_IndexTTS](https://github.com/billwuhao/ComfyUI_IndexTTS) | As above | ~6-8 GB | Weights Apache-2.0; pack Apache-2.0 | not yet tested |
| [indextts-2.5-multilingual](IndexTTS/indextts-2.5-multilingual.json) | IndexTTS 2.5 (zh, en, ja, es, ar) | Multilingual voice clone with emotion, speed and pronunciation control | [Comfyui-indextts25-xzg](https://github.com/xiaozhuguang/Comfyui-indextts25-xzg) | [IndexTeam/IndexTTS-2.5](https://huggingface.co/IndexTeam/IndexTTS-2.5) to `models/TTS/IndexTTS-2.5/`; the loader field holds a placeholder, pick the folder | ~8 GB+ | **Bilibili IndexTTS licence (check commercial terms)** | not yet tested |
| [indextts-2.5-basic-clone](IndexTTS/indextts-2.5-basic-clone.json) | IndexTTS 2.5 | Basic voice cloning | [BSAI_ComfyUI_IndexTTS-2.5](https://github.com/xm6018924/BSAI_ComfyUI_IndexTTS-2.5) | IndexTTS-2.5 to `models/IndexTTS2.5/` | ~4-10 GB | **Bilibili IndexTTS licence**; pack licence not declared | not yet tested |
| [indextts-2.5-dialogue](IndexTTS/indextts-2.5-dialogue.json) | IndexTTS 2.5 | Multi-speaker dialogue with saved speaker packs | [ComfyUI-IndexTTS-2.5](https://github.com/mailzwj/ComfyUI-IndexTTS-2.5), [ComfyUI-Custom-Scripts](https://github.com/pythongosssss/ComfyUI-Custom-Scripts) | IndexTTS-2.5 to `models/TTS/IndexTTS-2.5/` | ~8 GB+ | **Bilibili IndexTTS licence**; pack Apache-2.0 | not yet tested |

### Kani-TTS

Folder [`Kani-TTS/`](Kani-TTS) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [kani-tts](Kani-TTS/kani-tts.json) | Kani-TTS (370M / 450M) | Compact LM-based TTS (Kani-TTS-2 is not confirmed as selectable) | [ComfyUI-KaniTTS](https://github.com/wildminder/ComfyUI-KaniTTS) | [nineninesix](https://huggingface.co/nineninesix) kani-tts-370m / 450m (auto-download) | small, not stated | Weights: Hugging Face tag "other", check the card; pack Apache-2.0 | not yet tested |

### Kitten-TTS

Folder [`Kitten-TTS/`](Kitten-TTS) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [kitten-tts-saganaki](Kitten-TTS/kitten-tts-saganaki.json) | KittenTTS (15-80M) | Tiny CPU-friendly ONNX TTS | [ComfyUI-KittenTTS](https://github.com/Saganaki22/ComfyUI-KittenTTS) | [KittenML/kitten-tts](https://huggingface.co/KittenML) nano / micro / mini 0.8 (auto-download) | CPU, under 1 GB | Weights Apache-2.0; pack Apache-2.0 | not yet tested |

### Kokoro

Folder [`Kokoro/`](Kokoro) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [kokoro-82m-text-to-speech](Kokoro/kokoro-82m-text-to-speech.json) | Kokoro 82M (ONNX) | Text to speech with preset voices and voice blending | [comfyui-kokoro](https://github.com/stavsap/comfyui-kokoro) | [hexgrad/Kokoro-82M](https://huggingface.co/hexgrad/Kokoro-82M) ONNX, handled by the pack | Under 1 GB; runs on CPU | Model Apache-2.0 (commercial OK); pack Apache-2.0 | not yet tested |

### Kyutai

Folder [`Kyutai/`](Kyutai) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [kyutai-tts](Kyutai/kyutai-tts.json) | Kyutai TTS 1.6B (en, fr) | Streaming-style TTS with Kyutai voices. Edit the author's `C:\` model folder widget to `models/checkpoints/KyutaiTTS` | [ComfyUI-KyutaiTTS](https://github.com/BobRandomNumber/ComfyUI-KyutaiTTS) | [kyutai/tts-1.6b-en_fr](https://huggingface.co/kyutai/tts-1.6b-en_fr) + [kyutai/tts-voices](https://huggingface.co/kyutai/tts-voices) to `models/checkpoints/KyutaiTTS/` | ~6-8 GB (estimate) | Weights CC-BY-4.0; pack MIT; pack last updated 2025-07 | not yet tested |

### MARS5

Folder [`MARS5/`](MARS5) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [mars5-uvr5](MARS5/mars5-uvr5.json) | MARS5 (CAMB.AI) | Voice clone with prosody conditioning; the `UVR5_Node` comes from a separate AIFSH pack (old, 2024) | [ComfyUI-MARS5-TTS](https://github.com/AIFSH/ComfyUI-MARS5-TTS) | [Camb-ai/MARS5-TTS](https://huggingface.co/CAMB-AI/MARS5-TTS) | large (about 20 GB claimed upstream) | **Weights and pack AGPL-3.0** | not yet tested |

### MaskGCT

Folder [`MaskGCT/`](MaskGCT) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [maskgct-tts](MaskGCT/maskgct-tts.json) | MaskGCT (Amphion) | Zero-shot clone with masked codec generation; edit the author's `D:\` sample folder in the Load Audio Path node | [ComfyUI_MaskGCT](https://github.com/807502278/ComfyUI_MaskGCT) | [amphion/MaskGCT](https://huggingface.co/amphion/MaskGCT), w2v-bert-2.0, Whisper large-v3; the pack's own `models/`; also needs Crystools and a pack providing `string-to-array` | ~10 GB+ (estimate) | **Weights CC-BY-NC-4.0 (non-commercial)**; pack licence not declared | not yet tested |

### Maya

Folder [`Maya/`](Maya) — 4 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [maya1-tts](Maya/maya1-tts.json) | Maya1 (Maya Research) | Expressive TTS with emotion tags and a natural-language voice description | [ComfyUI-Maya1_TTS](https://github.com/Saganaki22/ComfyUI-Maya1_TTS) | [maya-research/maya1](https://huggingface.co/maya-research/maya1) + SNAC codec to `models/maya1-TTS/`; 4/8-bit needs bitsandbytes | ~6 GB (4-bit) to ~16 GB (bf16) | Weights Apache-2.0; pack Apache-2.0 | not yet tested |
| [maya3-indic-tts-builtin-voice](Maya/maya3-indic-tts-builtin-voice.json) | Maya3 (maya2-native), 11 Indian languages + English | Streaming Indic TTS with 20 built-in voices | [ComfyUI-maya2-native](https://github.com/Praveenhalder/ComfyUI-maya2-native) | [maya-research/maya2-native](https://huggingface.co/maya-research/maya2-native) (auto-download, ~5.6 GB) to `models/maya3/hf`; needs Linux, NVIDIA, CUDA 12.8 driver; installs an isolated transformers 5 runtime on first use | ~8 GB | Weights Apache-2.0; pack Apache-2.0 | not yet tested |
| [maya3-indic-tts-voice-clone](Maya/maya3-indic-tts-voice-clone.json) | Maya3 (maya2-native) | Zero-shot voice clone in Hindi and other Indian languages | [ComfyUI-maya2-native](https://github.com/Praveenhalder/ComfyUI-maya2-native) | As above | ~8 GB | Weights Apache-2.0; pack Apache-2.0 | not yet tested |
| [maya3-indic-voice-clone-auto-transcribe](Maya/maya3-indic-voice-clone-auto-transcribe.json) | Maya3 + Whisper | Whisper transcribes the reference clip, then Maya3 clones the voice | [ComfyUI-maya2-native](https://github.com/Praveenhalder/ComfyUI-maya2-native) | As above | ~8 GB | Weights Apache-2.0; pack Apache-2.0 | not yet tested |

### MeloTTS

Folder [`MeloTTS/`](MeloTTS) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [melotts-zetalvx](MeloTTS/melotts-zetalvx.json) | MeloTTS (MyShell) | Fast multi-accent TTS; the graph's `ZetalvxIntToString` node was not found in the pack source and may show red | [Zetalvx-ComfyUI-MeloTTS](https://github.com/ZETALVX/Zetalvx-ComfyUI-MeloTTS) | [myshell-ai/MeloTTS](https://huggingface.co/myshell-ai) models (auto-download) | CPU capable | Weights MIT; **pack has no licence file** | not yet tested |

### MisoTTS

Folder [`MisoTTS/`](MisoTTS) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [misotts](MisoTTS/misotts.json) | MisoTTS 8B (Sesame-style CSM) | Conversational TTS with voice clone; Whisper transcribes the reference | [MisoTTS-ComfyUI](https://github.com/Saganaki22/MisoTTS-ComfyUI) | [MisoLabs/MisoTTS](https://huggingface.co/MisoLabs/MisoTTS) (or drbaph BF16) to `models/misotts/`; kyutai/mimi codec | high (8B), not stated | Weights: Hugging Face tag "other", check the card; pack MIT | not yet tested |

### MOSS

Folder [`MOSS/`](MOSS) — 4 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [moss-tts-v15-clone-continue](MOSS/moss-tts-v15-clone-continue.json) | MOSS-TTS Local Transformer v1.5 | Speech generation, zero-shot clone and speech continuation; Whisper transcribes the reference | [Moss_TTS-ComfyUI](https://github.com/Saganaki22/Moss_TTS-ComfyUI) | Auto-download to `models/mosstts/` (includes MOSS-Audio-Tokenizer-v2) | ~6 GB | Weights Apache-2.0; pack licence not declared | not yet tested |
| [moss-tts-v15-dialogue](MOSS/moss-tts-v15-dialogue.json) | MOSS-TTS v1.5 (8B) | Single-voice speech and multi-speaker dialogue | [comfyui-moss-tts](https://github.com/wonderingearth/comfyui-moss-tts) | [OpenMOSS-Team/MOSS-TTS](https://huggingface.co/OpenMOSS-Team/MOSS-TTS) to `models/moss_tts/` | 16 GB+ | Weights Apache-2.0; pack licence not declared; sample file names are Chinese | not yet tested |
| [moss-ttsd-dialogue](MOSS/moss-ttsd-dialogue.json) | MOSS-TTSD v1.0 | Multi-speaker dialogue synthesis with a split codec loader | [ComfyUI-kaola-moss-tts](https://github.com/kana112233/ComfyUI-kaola-moss-tts) | MOSS-TTSD-v1.0 + MOSS-Audio-Tokenizer from [OpenMOSS-Team](https://huggingface.co/OpenMOSS-Team) to `models/moss_ttsd/`; Python 3.12 and flash-attn per its README | ~16-18 GB | Weights Apache-2.0; pack Apache-2.0 | not yet tested |
| [moss-voicegenerator-voice-design](MOSS/moss-voicegenerator-voice-design.json) | MOSS-VoiceGenerator 1.7B + MOSS-TTSD | Design a voice from a text description, then speak dialogue with it | [ComfyUI-kaola-moss-tts](https://github.com/kana112233/ComfyUI-kaola-moss-tts) | MOSS-VoiceGenerator to `models/moss_ttsd/MOSS-VoiceGenerator`, plus the TTSD files above | ~6-18 GB | Weights Apache-2.0; pack Apache-2.0 | not yet tested |

### Multi-Model

Folder [`Multi-Model/`](Multi-Model) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [voice-designer-moss-omnivoice-qwen](Multi-Model/voice-designer-moss-omnivoice-qwen.json) | MOSS-VoiceGenerator, OmniVoice, Qwen3-TTS | Unified Voice Designer: create a voice from a text description with any of three engines and save it as a character voice | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Auto-download to `models/TTS/` (MOSS VoiceGenerator 1.7B + audio tokenizer ~8.5 GB) | ~6-18 GB by engine | MOSS and Qwen3 Apache-2.0; pack MIT | not yet tested |

### NeuTTS

Folder [`NeuTTS/`](NeuTTS) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [neutts-clone](NeuTTS/neutts-clone.json) | NeuTTS Air (Neuphonic) | Instant voice clone from a reference clip and transcript | [ComfyUI-Neutts](https://github.com/AsifOnWeb3/ComfyUI-Neutts) | [neuphonic/neutts-air](https://huggingface.co/neuphonic/neutts-air) (GGUF or torch) + NeuCodec; needs `espeak` | CPU / low | Weights Apache-2.0; **pack has no licence file** | not yet tested |

### OmniVoice

Folder [`OmniVoice/`](OmniVoice) — 2 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [omnivoice-all-modes](OmniVoice/omnivoice-all-modes.json) | OmniVoice (k2-fsa, 600+ languages) | Zero-shot clone, voice design, multi-speaker and long-form TTS; optional Whisper transcript of the reference | [ComfyUI-OmniVoice-TTS](https://github.com/Saganaki22/ComfyUI-OmniVoice-TTS) | [k2-fsa/OmniVoice](https://huggingface.co/k2-fsa/OmniVoice) (auto-download); Whisper large-v3-turbo auto-download | ~4-12 GB by mode | Pack Apache-2.0; weights licence not confirmed | not yet tested |
| [omnivoice-tts-audio-suite](OmniVoice/omnivoice-tts-audio-suite.json) | OmniVoice | OmniVoice through the unified nodes: SRT-timed speech, voice-design instruction builder, non-verbal tags | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Auto-download to `models/TTS/` (~3.7 GB) | ~4 GB | Pack MIT; weights licence not confirmed | not yet tested |

### OpenVoice

Folder [`OpenVoice/`](OpenVoice) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [openvoice-tts-and-voice-conversion](OpenVoice/openvoice-tts-and-voice-conversion.json) | OpenVoice (V1, V2 with MeloTTS) | Text to speech in a reference voice, and speech-to-speech voice conversion | [ComfyUI_OpenVoice](https://github.com/hay86/ComfyUI_OpenVoice), [ComfyUI_AceNodes](https://github.com/hay86/ComfyUI_AceNodes) | Auto-download. V2 needs `pip install git+https://github.com/myshell-ai/MeloTTS.git` and `python -m unidic download` | ~2-4 GB | Model MIT (commercial OK); pack MIT; pack last updated 2024-07 | not yet tested |

### Orpheus

Folder [`Orpheus/`](Orpheus) — 2 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [orpheus-tts](Orpheus/orpheus-tts.json) | Orpheus 3B (Canopy Labs) | Expressive TTS with emotion tags | [ComfyUI-Orpheus (AustinMroz)](https://github.com/AustinMroz/ComfyUI-Orpheus) | [orpheus-3b-f16-safetensors](https://huggingface.co/AustinMroz/orpheus-3b-f16-safetensors) + [snac-24khz-ST](https://huggingface.co/Annuvin/snac-24khz-ST); folders per pack README | ~8 GB | Orpheus Apache-2.0; pack GPL-3.0 | not yet tested |
| [orpheus-voice-clone](Orpheus/orpheus-voice-clone.json) | Orpheus 3B | Voice clone from a single reference segment | [ComfyUI-Orpheus (AustinMroz)](https://github.com/AustinMroz/ComfyUI-Orpheus), [ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite) | As above | ~8 GB | Orpheus Apache-2.0; pack GPL-3.0 | not yet tested |

### Parler-TTS

Folder [`Parler-TTS/`](Parler-TTS) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [parler-tts-described-voice](Parler-TTS/parler-tts-described-voice.json) | Parler-TTS mini v1 / large v1 | Text to speech with the voice described in words (gender, pitch, pace, room) | [ComfyUI_ParlerTTS](https://github.com/smthemex/ComfyUI_ParlerTTS) | [parler-tts/parler-tts-mini-v1](https://huggingface.co/parler-tts/parler-tts-mini-v1) `model.safetensors` renamed to `parler-tts-mini-v1.safetensors` in `models/clip/` | ~2-4 GB (mini) | Model Apache-2.0 (commercial OK); pack Apache-2.0 | not yet tested |

### Qwen3-TTS

Folder [`Qwen3-TTS/`](Qwen3-TTS) — 11 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [qwen3-tts-custom-voice](Qwen3-TTS/qwen3-tts-custom-voice.json) | — | Custom Voice | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use | — | — | — | not recorded |
| [qwen3-tts-voice-clone-load-saved-voice](Qwen3-TTS/qwen3-tts-voice-clone-load-saved-voice.json) | — | Voice Clone + Load Saved Voice | ComfyUI-Qwen-TTS, ComfyUI-Easy-Use | — | — | — | not recorded |
| [qwen3-tts-voice-clone-save-voice](Qwen3-TTS/qwen3-tts-voice-clone-save-voice.json) | — | Voice Clone + Save Voice | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use | — | — | — | not recorded |
| [qwen3-tts-voice-clone-saved-multi-voice-dialogue](Qwen3-TTS/qwen3-tts-voice-clone-saved-multi-voice-dialogue.json) | — | Voice Clone + Saved Multi Voice + Dialogue | ComfyUI-Qwen-TTS, ComfyUI-Easy-Use | — | — | — | not recorded |
| [qwen3-tts-voice-clone](Qwen3-TTS/qwen3-tts-voice-clone.json) | — | Voice Clone | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use | — | — | — | not recorded |
| [qwen3-tts-voice-design-dialogue](Qwen3-TTS/qwen3-tts-voice-design-dialogue.json) | — | Voice Design + Dialogue | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use | — | — | — | not recorded |
| [qwen3-tts-voice-design-save-voice](Qwen3-TTS/qwen3-tts-voice-design-save-voice.json) | — | Voice Design + Save Voice | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use | — | — | — | not recorded |
| [qwen3-tts-voice-design](Qwen3-TTS/qwen3-tts-voice-design.json) | — | Voice Design | ComfyUI_LayerStyle, ComfyUI-Qwen-TTS, ComfyUI-Easy-Use | — | — | — | not recorded |
| [qwen3-tts-1038lab-voice-clone-with-asr](Qwen3-TTS/qwen3-tts-1038lab-voice-clone-with-asr.json) | Qwen3-TTS 0.6B / 1.7B Base + Qwen3-ASR | Voice clone; reference transcript filled by Qwen3-ASR | [ComfyUI-QwenTTS](https://github.com/1038lab/ComfyUI-QwenTTS) | [Qwen/Qwen3-TTS-12Hz-1.7B-Base](https://huggingface.co/Qwen/Qwen3-TTS-12Hz-1.7B-Base) or 0.6B-Base + Tokenizer-12Hz to `models/TTS/Qwen3-TTS/<name>/` | ~4-8 GB (1.7B), less for 0.6B | Model Apache-2.0 (commercial OK); pack GPL-3.0 | not yet tested |
| [qwen3-tts-1038lab-create-your-voice](Qwen3-TTS/qwen3-tts-1038lab-create-your-voice.json) | Qwen3-TTS + Whisper STT | Record your voice, transcribe it and save it to a voices library | [ComfyUI-QwenTTS](https://github.com/1038lab/ComfyUI-QwenTTS) | Qwen3-TTS weights to `models/TTS/Qwen3-TTS/<name>/` | ~4-8 GB | Model Apache-2.0 (commercial OK); pack GPL-3.0 | not yet tested |
| [qwen3-tts-tts-audio-suite-voice-design-asr-srt](Qwen3-TTS/qwen3-tts-tts-audio-suite-voice-design-asr-srt.json) | Qwen3-TTS + Qwen3-ASR | Voice design, character voices, ASR transcription and SRT-timed speech | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Auto-download to `models/TTS/` (3-6 GB) | ~6-10 GB | Model Apache-2.0 (commercial OK); pack licence unclear, check repo | not yet tested |

### Sesame-CSM

Folder [`Sesame-CSM/`](Sesame-CSM) — 4 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [sesame-csm-1b-text-to-speech](Sesame-CSM/sesame-csm-1b-text-to-speech.json) | Sesame CSM-1B | Conversational text to speech | [ComfyUI-CSM-Nodes](https://github.com/thezveroboy/ComfyUI-CSM-Nodes), [QualityOfLifeSuit_Omar92](https://github.com/omar92/ComfyUI-QualityOfLifeSuit_Omar92) | [sesame/csm-1b](https://huggingface.co/sesame/csm-1b) `ckpt.pt` to `models/sesame/`; Llama-3.2-1B tokenizer to `models/sesame_tokenizer/` | ~5-8 GB | Model Apache-2.0 (commercial OK) + Llama 3.2 licence for the tokenizer; pack Apache-2.0 | not yet tested |
| [sesame-csm-1b-context-voice-clone](Sesame-CSM/sesame-csm-1b-context-voice-clone.json) | Sesame CSM-1B | Voice clone from context clips with transcripts | [ComfyUI-CSM-Nodes](https://github.com/thezveroboy/ComfyUI-CSM-Nodes), [QualityOfLifeSuit_Omar92](https://github.com/omar92/ComfyUI-QualityOfLifeSuit_Omar92) | As above | ~5-8 GB | Model Apache-2.0 + Llama 3.2 licence | not yet tested |
| [sesame-csm-1b-dialogue-clone](Sesame-CSM/sesame-csm-1b-dialogue-clone.json) | Sesame CSM-1B | Two-speaker dialogue cloned from reference clips | [ComfyUI_CSM](https://github.com/billwuhao/ComfyUI_CSM) | csm-1b to `models/TTS/csm-1b`; Mimi tokenizer ([kyutai/moshiko-pytorch-bf16](https://huggingface.co/kyutai/moshiko-pytorch-bf16)) to `models/TTS/moshiko-pytorch-bf16`; Llama-3.2-1B to `models/LLM/Llama-3.2-1B` | ~5-8 GB | Model Apache-2.0 + Llama 3.2 licence; pack Apache-2.0 | not yet tested |
| [sesame-csm-1b-saved-speakers-dialogue](Sesame-CSM/sesame-csm-1b-saved-speakers-dialogue.json) | Sesame CSM-1B | Dialogue with saved speakers | [ComfyUI_CSM](https://github.com/billwuhao/ComfyUI_CSM) | As above | ~5-8 GB | Model Apache-2.0 + Llama 3.2 licence | not yet tested |

### Spark-TTS

Folder [`Spark-TTS/`](Spark-TTS) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [spark-tts-create-clone](Spark-TTS/spark-tts-create-clone.json) | Spark-TTS 0.5B | Voice creator (gender, pitch, speed), voice clone and advanced clone | [ComfyUI-SparkTTS](https://github.com/1038lab/ComfyUI-SparkTTS) | [SparkAudio/Spark-TTS-0.5B](https://huggingface.co/SparkAudio/Spark-TTS-0.5B) to `models/TTS/SparkTTS/` | ~4 GB | **Weights CC-BY-NC-SA-4.0 (non-commercial)**; pack GPL-3.0 | not yet tested |

### Step-Audio

Folder [`Step-Audio/`](Step-Audio) — 2 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [step-audio-editx-clone](Step-Audio/step-audio-editx-clone.json) | Step-Audio-EditX | Zero-shot voice clone | [ComfyUI-Step_Audio_EditX_TTS](https://github.com/Saganaki22/ComfyUI-Step_Audio_EditX_TTS) | [stepfun-ai/Step-Audio-EditX](https://huggingface.co/stepfun-ai/Step-Audio-EditX) + Step-Audio-Tokenizer; the graph also uses comfy_mtb, ComfyUI-Custom-Scripts and ComfyUI-Easy-Use | ~16 GB (estimate) | Weights licence not confirmed; pack Apache-2.0 | not yet tested |
| [step-audio-editx-edit](Step-Audio/step-audio-editx-edit.json) | Step-Audio-EditX | Edit existing speech: emotion, style, speed and paralinguistic sounds | [ComfyUI-Step_Audio_EditX_TTS](https://github.com/Saganaki22/ComfyUI-Step_Audio_EditX_TTS) | As above | ~16 GB (estimate) | Weights licence not confirmed; pack Apache-2.0 | not yet tested |

### Supertonic

Folder [`Supertonic/`](Supertonic) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [supertonic3-tts](Supertonic/supertonic3-tts.json) | Supertonic 3 (99M) | Fast on-device multilingual TTS with effects | [ComfyUI-Supertonic3TTS](https://github.com/Anonymzx/ComfyUI-Supertonic3TTS) | [Supertone/supertonic-3](https://huggingface.co/Supertone/supertonic-3) ONNX | CPU capable | Weights OpenRAIL (use conditions apply); pack MIT | not yet tested |

### VibeVoice

Folder [`VibeVoice/`](VibeVoice) — 5 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [vibevoice-single-speaker](VibeVoice/vibevoice-single-speaker.json) | VibeVoice 1.5B / 7B (Microsoft) | Long-form single-speaker TTS with voice clone | [VibeVoice-ComfyUI](https://github.com/Enemyx-net/VibeVoice-ComfyUI) | `models/vibevoice/`: [microsoft/VibeVoice-1.5B](https://huggingface.co/microsoft/VibeVoice-1.5B), [aoi-ot/VibeVoice-Large](https://huggingface.co/aoi-ot/VibeVoice-Large), Q8/Q4 community quantisations | ~6 GB (1.5B), ~20 GB (Large), 8-12 GB quantised | Model MIT; official 7B withdrawn, Large weights are community re-uploads; pack MIT | not yet tested |
| [vibevoice-multi-speaker-podcast](VibeVoice/vibevoice-multi-speaker-podcast.json) | VibeVoice | Up to 4-speaker podcast-style dialogue | [VibeVoice-ComfyUI](https://github.com/Enemyx-net/VibeVoice-ComfyUI) | As above | As above | Model MIT | not yet tested |
| [vibevoice-pause-tags](VibeVoice/vibevoice-pause-tags.json) | VibeVoice | Single speaker with explicit [pause] timing tags | [VibeVoice-ComfyUI](https://github.com/Enemyx-net/VibeVoice-ComfyUI) | As above | As above | Model MIT | not yet tested |
| [vibevoice-wildminder-tts-and-asr](VibeVoice/vibevoice-wildminder-tts-and-asr.json) | VibeVoice TTS + VibeVoice-ASR | TTS plus VibeVoice speech recognition | [ComfyUI-VibeVoice](https://github.com/wildminder/ComfyUI-VibeVoice), [ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) | `models/tts/VibeVoice/`: VibeVoice-1.5B (3 GB), 7B (17.4 GB), [microsoft/VibeVoice-ASR-HF](https://huggingface.co/microsoft/VibeVoice-ASR-HF) | ~6-20 GB | Model MIT; pack MIT | not yet tested |
| [vibevoice-tts-audio-suite-srt-characters](VibeVoice/vibevoice-tts-audio-suite-srt-characters.json) | VibeVoice | Character voices and SRT-timed speech | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Auto-download to `models/TTS/` | ~6-20 GB | Model MIT | not yet tested |

### VoxCPM

Folder [`VoxCPM/`](VoxCPM) — 3 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [voxcpm-tts-and-voice-clone](VoxCPM/voxcpm-tts-and-voice-clone.json) | VoxCPM 0.5B / 1.5 | Tokenizer-free TTS and voice clone | [ComfyUI-VoxCPM](https://github.com/wildminder/ComfyUI-VoxCPM) | Auto-download to `models/tts/VoxCPM/` ([openbmb/VoxCPM1.5](https://huggingface.co/openbmb/VoxCPM1.5)) | ~4-6 GB | Model Apache-2.0 (commercial OK); pack Apache-2.0 | not yet tested |
| [voxcpm-lora-training](VoxCPM/voxcpm-lora-training.json) | VoxCPM | Make a dataset and train a voice LoRA | [ComfyUI-VoxCPM](https://github.com/wildminder/ComfyUI-VoxCPM), [ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) | As above; LoRAs to `models/loras/` | ~8+ GB | Model Apache-2.0 (commercial OK) | not yet tested |
| [voxcpm2-tts-clone-and-lora](VoxCPM/voxcpm2-tts-clone-and-lora.json) | VoxCPM2 2B | TTS, voice clone and LoRA training | [ComfyUI-VoxCPM2](https://github.com/Saganaki22/ComfyUI-VoxCPM2) | [openbmb/VoxCPM2](https://huggingface.co/openbmb/VoxCPM2) to `models/tts/VoxCPM/` | ~8 GB | Model Apache-2.0 (commercial OK); pack Apache-2.0 | not yet tested |

### ZipVoice

Folder [`ZipVoice/`](ZipVoice) — 1 workflow.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [zipvoice-en](ZipVoice/zipvoice-en.json) | ZipVoice (k2-fsa, 123M) | Zero-shot voice clone from a reference clip and transcript (base model only) | [ComfyUI-ZipVoice](https://github.com/Burgstall-labs/ComfyUI-ZipVoice) | [k2-fsa/ZipVoice](https://huggingface.co/k2-fsa/ZipVoice) to `models/zipvoice/<name>` | low, not stated | Weights Apache-2.0 upstream; **pack has no licence file** | not yet tested |

### Zonos

Folder [`Zonos/`](Zonos) — 5 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [zonos-v0.1-emotion-voice-clone](Zonos/zonos-v0.1-emotion-voice-clone.json) | Zonos v0.1 (Zyphra) | TTS with an emotion vector and optional reference-voice clone | [ComfyUI-Zonos](https://github.com/BuffMcBigHuge/ComfyUI-Zonos) | [Zyphra/Zonos-v0.1-transformer](https://huggingface.co/Zyphra/Zonos-v0.1-transformer) (auto-download); needs system package `espeak-ng` | ~6 GB+ | Weights Apache-2.0; pack MIT | not yet tested |
| [zonos2-tts](Zonos/zonos2-tts.json) | ZONOS2 (Zyphra) | Multilingual voice-clone TTS | [Zonos2_TTS-ComfyUI](https://github.com/Saganaki22/Zonos2_TTS-ComfyUI) | [Zyphra/ZONOS2](https://huggingface.co/Zyphra/ZONOS2) (BF16 / FP8 repacks by drbaph) + `descript/dac_44khz` codec | ~13-17 GB | Weights Apache-2.0; pack MIT | not yet tested |
| [zonos2-tts-emotion](Zonos/zonos2-tts-emotion.json) | ZONOS2 | As above with emotion-direction steering | [zonos2-tts-comfyui-emotion](https://github.com/shiwano/zonos2-tts-comfyui-emotion) | As above | ~13-17 GB | Weights Apache-2.0; pack MIT | not yet tested |
| [zonos3-clone-voice](Zonos/zonos3-clone-voice.json) | ZONOS3-Mini (Zyphra, 43 languages) | Clone a voice from a reference (runs Zyphra's local server in a separate process) | [ComfyUI-ZONOS3](https://github.com/claudianeodev/ComfyUI-ZONOS3) | [Zyphra/ZONOS3-Mini](https://huggingface.co/Zyphra/ZONOS3-Mini) | not stated | Weights Apache-2.0; pack MIT (very new pack) | not yet tested |
| [zonos3-design-voice](Zonos/zonos3-design-voice.json) | ZONOS3-Mini | Design a voice from a text description | [ComfyUI-ZONOS3](https://github.com/claudianeodev/ComfyUI-ZONOS3) | As above | not stated | Weights Apache-2.0; pack MIT | not yet tested |

See the [Audio overview](../../README.md) for the full category map and model coverage, the [main README](../../../README.md) for setup steps, or [`00-LIBRARY-INDEX.md`](../../../00-LIBRARY-INDEX.md) for the full list of workflows.
