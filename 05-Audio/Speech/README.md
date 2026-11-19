# Speech — ComfyUI workflows

Text-to-speech, voice cloning, voice design and voice conversion (Qwen3-TTS, OmniVoice, MOSS-TTS, Higgs Audio v3, FireRedTTS3, IndexTTS 1.5 / 2 / 2.5, CosyVoice 1 / 2 / 3, Orpheus, Zonos, Maya1 / Maya3 Indic, Spark-TTS, RVC, Seed-VC, Fish S2, Chatterbox, Kokoro, Parler-TTS, OpenVoice, F5-TTS, Bark, ChatTTS, Dia, Sesame CSM, VibeVoice, VoxCPM, ElevenLabs and Fish Audio API, and more); speech clean-up; speech-to-text, subtitles, diarisation, speech translation and forced alignment (MOSS-Transcribe-Diarize, FunASR, Hibiki, Whisper, faster-whisper, Qwen3-ASR, Parakeet, Nemotron, SenseVoice, Granite Speech).

| Subfolder | What is inside | Workflows | Details |
|---|---|---|---|
| [`Text-to-Speech-and-Voice-Cloning/`](Text-to-Speech-and-Voice-Cloning) | Text-to-speech, voice cloning, voice design and custom voices, multi-speaker dialogue and speech editing. One subfolder per model family | 110 | [README](Text-to-Speech-and-Voice-Cloning/README.md) |
| [`Voice-Conversion/`](Voice-Conversion) | Speech-to-speech voice conversion and voice changers (RVC, Seed-VC, Chatterbox VC, ElevenLabs) | 7 | [below](#voice-conversion) |
| [`Speech-Enhancement-and-Cleanup/`](Speech-Enhancement-and-Cleanup) | Denoise, enhance, isolate a speaker, remove music and noise from speech | 5 | [below](#speech-enhancement-and-clean-up) |
| [`Speech-to-Text-and-Subtitles/`](Speech-to-Text-and-Subtitles) | Speech recognition, subtitles (SRT / VTT, burned-in), speaker diarisation. One subfolder per model family | 22 | [README](Speech-to-Text-and-Subtitles/README.md) |
| [`Speech-Translation/`](Speech-Translation) | Speech-to-speech and transcribe-translate-revoice pipelines | 2 | [below](#speech-translation) |
| [`Forced-Alignment/`](Forced-Alignment) | Align a known script, SRT or lyric file to audio with word timestamps | 3 | [below](#forced-alignment) |

## Workflows (149)

The two large subfolders have their own READMEs with one table per model family. The smaller functional folders are listed here. Status notes are carried over unchanged from the earlier library README; none of the Atlas additions has been run. Voice cloning and voice conversion need the consent of the person whose voice you use.

## Voice conversion

Folder [`Voice-Conversion/`](Voice-Conversion) — Speech-to-speech voice conversion and voice changers (RVC, Seed-VC, Chatterbox VC, ElevenLabs). 7 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [chatterbox-voice-conversion](Voice-Conversion/chatterbox-voice-conversion.json) | Chatterbox VC | Speech-to-speech voice conversion (official Comfy template) | [ComfyUI_Fill-ChatterBox](https://github.com/filliptm/ComfyUI_Fill-ChatterBox) | As above | 8 GB+ | Model MIT (commercial OK) | not yet tested |
| [elevenlabs-api-speech-to-speech](Voice-Conversion/elevenlabs-api-speech-to-speech.json) | ElevenLabs (API) | Speech-to-speech voice changer | none (ComfyUI core API nodes) | None (cloud) | None | paid Comfy API credits; output under provider terms | not yet tested |
| [rvc-native](Voice-Conversion/rvc-native.json) | RVC (Retrieval-based Voice Conversion) | Speech-to-speech voice conversion with your own RVC voice model and index | [ComfyUI-RVC (Aero-Ex)](https://github.com/Aero-Ex/ComfyUI-RVC) | [Aero-Ex/ComfyUI-RVC](https://huggingface.co/Aero-Ex/ComfyUI-RVC) (hubert, rmvpe) plus a voice `.pth` of your own | low | Voice models carry their own licence; **pack has no licence file** | not yet tested |
| [seedvc-billwuhao](Voice-Conversion/seedvc-billwuhao.json) | Seed-VC | Zero-shot voice conversion for speech or singing | [ComfyUI_Seed-VC](https://github.com/billwuhao/ComfyUI_Seed-VC) | [Plachta/Seed-VC](https://huggingface.co/Plachta/Seed-VC), campplus, rmvpe, bigvgan_v2 | ~4-8 GB (estimate) | Pack Apache-2.0; **Seed-VC weights GPL-3.0** | not yet tested |
| [seedvc-voice-swap-1](Voice-Conversion/seedvc-voice-swap-1.json) | Seed-VC | One-voice swap of an input recording | [comfyui-seedvc-voice-swap](https://github.com/rasmont/comfyui-seedvc-voice-swap) | Seed-VC (auto-download) | about 1.5 GB peak (pack README) | **GPL-3.0** | not yet tested |
| [rvc-chatterbox-tts-audio-suite-voice-changer](Voice-Conversion/rvc-chatterbox-tts-audio-suite-voice-changer.json) | RVC + Chatterbox VC | Unified voice changer: RVC or Chatterbox conversion with character voices | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Auto-download to `models/TTS/`; RVC voice models of your own | ~6-8 GB | Pack MIT; check each voice model | not yet tested |
| [rvc-model-training-tts-audio-suite](Voice-Conversion/rvc-model-training-tts-audio-suite.json) | RVC | Prepare a dataset, train an RVC voice model and test the conversion | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Auto-download to `models/TTS/` | ~8 GB+ | Pack MIT | not yet tested |

## Speech enhancement and clean-up

Folder [`Speech-Enhancement-and-Cleanup/`](Speech-Enhancement-and-Cleanup) — Denoise, enhance, isolate a speaker, remove music and noise from speech. 5 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [elevenlabs-api-voice-isolation](Speech-Enhancement-and-Cleanup/elevenlabs-api-voice-isolation.json) | ElevenLabs (API) | Isolate voice from background noise and music | none (ComfyUI core API nodes) | None (cloud) | None | paid Comfy API credits; output under provider terms | not yet tested |
| [voice-cleaning-tts-audio-suite](Speech-Enhancement-and-Cleanup/voice-cleaning-tts-audio-suite.json) | Voice Fixer and vocal removal | Remove background music and noise from speech | [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | Auto-download to `models/TTS/` | ~2-4 GB | Pack MIT | not yet tested |
| [fl-clearvoice-enhance](Speech-Enhancement-and-Cleanup/fl-clearvoice-enhance.json) | ClearerVoice, Resemble-Enhance, VoiceFixer | Denoise, enhance and super-resolve speech (the `FL_Audio_Crop` node was not found in the pack mappings) | [ComfyUI_FL-ClearVoice](https://github.com/filliptm/ComfyUI_FL-ClearVoice) | Auto-download to `models/clear_voice/` | ~2-4 GB | Models Apache-2.0 / MIT; pack MIT per pyproject, no LICENSE file | not yet tested |
| [voxlock-isolate-voice](Speech-Enhancement-and-Cleanup/voxlock-isolate-voice.json) | VoxLock (target-speaker isolation) | Keep one speaker and remove the others (CPU ONNX) | [ComfyUI-VoxLock](https://github.com/hiroki-abe-58/ComfyUI-VoxLock) | [arbazsiddiqui/voxlock](https://huggingface.co/arbazsiddiqui/voxlock) ONNX (~275 MB) to `models/voxlock/onnx`; `pip install voxlock==1.1.1` | CPU | Pack MIT; check the model licence | not yet tested |
| [voxlock-isolate-with-sample](Speech-Enhancement-and-Cleanup/voxlock-isolate-with-sample.json) | VoxLock | Same, enrolled from a sample of the wanted speaker | [ComfyUI-VoxLock](https://github.com/hiroki-abe-58/ComfyUI-VoxLock) | As above | CPU | Pack MIT; check the model licence | not yet tested |

## Speech translation

Folder [`Speech-Translation/`](Speech-Translation) — Speech-to-speech and transcribe-translate-revoice pipelines. 2 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [voicebridge-speech-translation](Speech-Translation/voicebridge-speech-translation.json) | Qwen3-ASR + LLM translation + Qwen3-TTS | Speech translation pipeline: transcribe, translate (OpenAI-compatible API, your own key), re-voice with a cloned voice and rebuild the audio from SRT times. Contains an author `E:\` path | [comfyui_voicebridge](https://github.com/YanTianlong-01/comfyui_voicebridge), [ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) | Qwen3-ASR 1.7B / 0.6B + Qwen3-ForcedAligner-0.6B to `models/qwen-asr/`; Qwen3-TTS-12Hz-1.7B-Base to `models/qwen-tts/` | ~8-12 GB | Models Apache-2.0; pack MIT; the translation API is a paid third-party service | not yet tested |
| [hibiki-speech2speech-translation](Speech-Translation/hibiki-speech2speech-translation.json) | Hibiki 2B (Kyutai) | Simultaneous French-to-English speech-to-speech translation | [ComfyUI-hibiki](https://github.com/jhj0517/ComfyUI-hibiki) | [kyutai/hibiki-2b-pytorch-bf16](https://huggingface.co/kyutai/hibiki-2b-pytorch-bf16) (auto-download to the Hugging Face cache); `pip install` the pack requirements (moshi) | ~8 GB (estimate) | Weights CC-BY-4.0 per Kyutai; **pack has no licence file** | not yet tested |

## Forced alignment

Folder [`Forced-Alignment/`](Forced-Alignment) — Align a known script, SRT or lyric file to audio with word timestamps. 3 workflows.

| Workflow | Model | What it does | Custom nodes needed | Model weights and folder | VRAM (approx.) | Licence | Status |
|---|---|---|---|---|---|---|---|
| [qwen3-forced-aligner-word-timestamps](Forced-Alignment/qwen3-forced-aligner-word-timestamps.json) | Qwen3-ASR + Qwen3-ForcedAligner 0.6B | Forced alignment: word-level timestamps for a transcript | [ComfyUI-Qwen3ASR](https://github.com/Aero-Ex/ComfyUI-Qwen3ASR) | `qwen3-asr-1.7B.safetensors` / `-0.6B` and `qwen3-forcedaligner-0.6B.safetensors` to `models/qwen3asr/` | ~3-6 GB | Model Apache-2.0 (commercial OK); pack MIT. Do not install together with DarioFT/ComfyUI-Qwen3-ASR | not yet tested |
| [audio-srt-aligner-overlay](Forced-Alignment/audio-srt-aligner-overlay.json) | Whisper + UVR vocal separation | Force-align a known script or SRT to audio and burn subtitles into a video. Contains an author `/home/jovyan/...` path; several helper packs are named in the graph | [ComfyUI-Audio-Srt-Aligner](https://github.com/ahkimkoo/ComfyUI-Audio-Srt-Aligner), [audio-separation-nodes-comfyui](https://github.com/christian-byrne/audio-separation-nodes-comfyui), [ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite), [rgthree-comfy](https://github.com/rgthree/rgthree-comfy) | Whisper to `models/stt/whisper`; UVR / Roformer vocal model (1.8 GB) to `models/uvr5/`; a font in `models/fonts` | ~2-6 GB | Pack MIT; check each model | not yet tested |
| [lyric-align-showcase](Forced-Alignment/lyric-align-showcase.json) | torchaudio MMS forced aligner (wav2vec2 CTC) | Align a lyric or script file to audio with word times and slice by time; usable for speech | [comfyui_lyric_align](https://github.com/bmad4ever/comfyui_lyric_align), [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | torchaudio MMS_FA bundle (1.2 GB, downloaded on first align) | ~2 GB | **MMS alignment weights are CC-BY-NC-4.0 (non-commercial)**; pack MIT; some helper nodes are unverified | not yet tested |

## Speech models not yet available in ComfyUI

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

See the [Audio overview](../README.md) for the full category map and model coverage, the [main README](../../README.md) for setup steps, or [`00-LIBRARY-INDEX.md`](../../00-LIBRARY-INDEX.md) for the full list of workflows.
