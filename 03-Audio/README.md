# Audio — ComfyUI workflows

229 ComfyUI workflows for music and speech: song and instrumental generation, covers and editing, sound effects, singing voices, music analysis and transcription, stem separation, text-to-speech and voice cloning, voice conversion, speech clean-up, speech-to-text and subtitles, speech translation and forced alignment.

Workflows are grouped into two categories, **Music** and **Speech**, and inside each category into one folder per model (Speech mixes TTS, voice-conversion and speech-to-text models, one folder each). Each file name starts with the task (`tts-`, `voice-clone-`, `stt-`, `txt2music-`, `stem-split-` ...). Every category README has one table per model folder with the workflow link, what it does, the models and custom nodes it needs, and the licence, VRAM and test notes that were recorded for it.

## Folders

| Category | What is inside | Model folders | Workflows |
|---|---|---|---|
| **[Music](Music/README.md)** | Songs, instrumentals and general audio from text, lyrics or images; covers, remixing and section edits; music LoRAs; sound effects; singing voice; music captioning and transcription to MIDI / ABC / lyrics; stem separation. | [ACE-Step-1](Music/ACE-Step-1), [ACE-Step-1.5](Music/ACE-Step-1.5), [AudioLDM2](Music/AudioLDM2), [AudioX](Music/AudioX), [Basic-Pitch](Music/Basic-Pitch), [Demucs](Music/Demucs), [DiffRhythm](Music/DiffRhythm), [Foundation-1](Music/Foundation-1), [HeartMuLa](Music/HeartMuLa), [MiniMax-Music](Music/MiniMax-Music), [MulaCover](Music/MulaCover), [MuScriptor](Music/MuScriptor), [Music-Flamingo](Music/Music-Flamingo), [MusicGen](Music/MusicGen), [Pika](Music/Pika), [RoFormer](Music/RoFormer), [SheetSage](Music/SheetSage), [SongBloom](Music/SongBloom), [SongGeneration](Music/SongGeneration), [Sonilo](Music/Sonilo), [SoulX-Singer](Music/SoulX-Singer), [Stable-Audio](Music/Stable-Audio), [Woosh](Music/Woosh), [YuE](Music/YuE), [Other](Music/Other) | 80 |
| **[Speech](Speech/README.md)** | Text-to-speech, voice cloning, voice design and dialogue; voice conversion; speech enhancement and voice isolation; speech-to-text, subtitles and diarisation; speech translation; forced alignment. | [Bark](Speech/Bark), [Chatterbox](Speech/Chatterbox), [ChatTTS](Speech/ChatTTS), [ClearVoice](Speech/ClearVoice), [CosyVoice](Speech/CosyVoice), [Dia](Speech/Dia), [DramaBox](Speech/DramaBox), [ElevenLabs](Speech/ElevenLabs), [F5-TTS](Speech/F5-TTS), [FireRedTTS](Speech/FireRedTTS), [Fish-Speech](Speech/Fish-Speech), [FunASR](Speech/FunASR), [GPT-SoVITS](Speech/GPT-SoVITS), [Hibiki](Speech/Hibiki), [Higgs-Audio](Speech/Higgs-Audio), [IndexTTS](Speech/IndexTTS), [Kani-TTS](Speech/Kani-TTS), [Kitten-TTS](Speech/Kitten-TTS), [Kokoro](Speech/Kokoro), [Kyutai](Speech/Kyutai), [MARS5](Speech/MARS5), [MaskGCT](Speech/MaskGCT), [Maya](Speech/Maya), [Mega-ASR](Speech/Mega-ASR), [MeloTTS](Speech/MeloTTS), [MisoTTS](Speech/MisoTTS), [MOSS](Speech/MOSS), [Nemotron](Speech/Nemotron), [NeuTTS](Speech/NeuTTS), [OmniVoice](Speech/OmniVoice), [OpenVoice](Speech/OpenVoice), [Orpheus](Speech/Orpheus), [Parakeet](Speech/Parakeet), [Parler-TTS](Speech/Parler-TTS), [Qwen3-ASR](Speech/Qwen3-ASR), [Qwen3-TTS](Speech/Qwen3-TTS), [RVC](Speech/RVC), [Seed-VC](Speech/Seed-VC), [SenseVoice](Speech/SenseVoice), [Sesame-CSM](Speech/Sesame-CSM), [Spark-TTS](Speech/Spark-TTS), [Step-Audio](Speech/Step-Audio), [Supertonic](Speech/Supertonic), [VibeVoice](Speech/VibeVoice), [VoiceBridge](Speech/VoiceBridge), [VoxCPM](Speech/VoxCPM), [VoxLock](Speech/VoxLock), [Whisper](Speech/Whisper), [ZipVoice](Speech/ZipVoice), [Zonos](Speech/Zonos), [Other](Speech/Other) | 149 |
| **Total** | | | **229** |

### Finding a task

| Task (file name prefix) | Where | Model folders |
|---|---|---|
| `add-tracks` | [Music](Music/README.md) | [ACE-Step-1.5](Music/README.md#ace-step-15) |
| `audio2abc` | [Music](Music/README.md) | [SheetSage](Music/README.md#sheetsage) |
| `audio2audio` | [Music](Music/README.md) | [ACE-Step-1](Music/README.md#ace-step-1), [ACE-Step-1.5](Music/README.md#ace-step-15) |
| `audio2midi` | [Music](Music/README.md) | [Basic-Pitch](Music/README.md#basic-pitch), [MuScriptor](Music/README.md#muscriptor) |
| `caption` | [Music](Music/README.md) | [ACE-Step-1.5](Music/README.md#ace-step-15) |
| `caption-song-analysis` | [Music](Music/README.md) | [Music-Flamingo](Music/README.md#music-flamingo) |
| `caption-understand-audio` | [Music](Music/README.md) | [ACE-Step-1.5](Music/README.md#ace-step-15) |
| `cover` | [Music](Music/README.md) | [ACE-Step-1.5](Music/README.md#ace-step-15), [DiffRhythm](Music/README.md#diffrhythm), [MulaCover](Music/README.md#mulacover), [YuE](Music/README.md#yue) |
| `extend-complete` | [Music](Music/README.md) | [ACE-Step-1.5](Music/README.md#ace-step-15) |
| `forced-alignment` | [Speech](Speech/README.md) | [Qwen3-ASR](Speech/README.md#qwen3-asr), [Other](Speech/README.md#other) |
| `img2music` | [Music](Music/README.md) | [AudioLDM2](Music/README.md#audioldm2), [Stable-Audio](Music/README.md#stable-audio) |
| `lora-training` | [Music](Music/README.md) | [ACE-Step-1.5](Music/README.md#ace-step-15) |
| `lyrics-transcribe` | [Music](Music/README.md) | [ACE-Step-1.5](Music/README.md#ace-step-15), [HeartMuLa](Music/README.md#heartmula) |
| `lyrics2song` | [Music](Music/README.md) | [ACE-Step-1.5](Music/README.md#ace-step-15), [DiffRhythm](Music/README.md#diffrhythm), [HeartMuLa](Music/README.md#heartmula), [SongBloom](Music/README.md#songbloom), [SongGeneration](Music/README.md#songgeneration), [YuE](Music/README.md#yue) |
| `remix` | [Music](Music/README.md) | [Demucs](Music/README.md#demucs), [MulaCover](Music/README.md#mulacover) |
| `repaint-section` | [Music](Music/README.md) | [ACE-Step-1.5](Music/README.md#ace-step-15), [DiffRhythm](Music/README.md#diffrhythm) |
| `singing-voice` | [Music](Music/README.md) | [SoulX-Singer](Music/README.md#soulx-singer) |
| `sound-effects` | [Music](Music/README.md) | [AudioX](Music/README.md#audiox), [Stable-Audio](Music/README.md#stable-audio), [Woosh](Music/README.md#woosh) |
| `speech-edit` | [Speech](Speech/README.md) | [F5-TTS](Speech/README.md#f5-tts), [Step-Audio](Speech/README.md#step-audio) |
| `speech-enhance` | [Speech](Speech/README.md) | [ClearVoice](Speech/README.md#clearvoice), [Other](Speech/README.md#other) |
| `speech-translation` | [Speech](Speech/README.md) | [Hibiki](Speech/README.md#hibiki), [VoiceBridge](Speech/README.md#voicebridge) |
| `stem-split` | [Music](Music/README.md) | [ACE-Step-1.5](Music/README.md#ace-step-15), [Demucs](Music/README.md#demucs), [RoFormer](Music/README.md#roformer), [Other](Music/README.md#other) |
| `stt` | [Speech](Speech/README.md) | [ElevenLabs](Speech/README.md#elevenlabs), [Fish-Speech](Speech/README.md#fish-speech), [Mega-ASR](Speech/README.md#mega-asr), [MOSS](Speech/README.md#moss), [Nemotron](Speech/README.md#nemotron), [Qwen3-ASR](Speech/README.md#qwen3-asr), [SenseVoice](Speech/README.md#sensevoice), [Whisper](Speech/README.md#whisper) |
| `style-transfer` | [Music](Music/README.md) | [HeartMuLa](Music/README.md#heartmula), [SongGeneration](Music/README.md#songgeneration) |
| `subtitles` | [Speech](Speech/README.md) | [FunASR](Speech/README.md#funasr), [Parakeet](Speech/README.md#parakeet), [Qwen3-ASR](Speech/README.md#qwen3-asr), [Whisper](Speech/README.md#whisper), [Other](Speech/README.md#other) |
| `tts` | [Speech](Speech/README.md) | [Bark](Speech/README.md#bark), [Chatterbox](Speech/README.md#chatterbox), [ChatTTS](Speech/README.md#chattts), [CosyVoice](Speech/README.md#cosyvoice), [Dia](Speech/README.md#dia), [DramaBox](Speech/README.md#dramabox), [ElevenLabs](Speech/README.md#elevenlabs), [F5-TTS](Speech/README.md#f5-tts), [FireRedTTS](Speech/README.md#fireredtts), [Fish-Speech](Speech/README.md#fish-speech), [GPT-SoVITS](Speech/README.md#gpt-sovits), [Higgs-Audio](Speech/README.md#higgs-audio), [IndexTTS](Speech/README.md#indextts), [Kani-TTS](Speech/README.md#kani-tts), [Kitten-TTS](Speech/README.md#kitten-tts), [Kokoro](Speech/README.md#kokoro), [Kyutai](Speech/README.md#kyutai), [MaskGCT](Speech/README.md#maskgct), [Maya](Speech/README.md#maya), [MeloTTS](Speech/README.md#melotts), [MisoTTS](Speech/README.md#misotts), [OmniVoice](Speech/README.md#omnivoice), [Orpheus](Speech/README.md#orpheus), [Parler-TTS](Speech/README.md#parler-tts), [Qwen3-TTS](Speech/README.md#qwen3-tts), [Sesame-CSM](Speech/README.md#sesame-csm), [Supertonic](Speech/README.md#supertonic), [VibeVoice](Speech/README.md#vibevoice), [ZipVoice](Speech/README.md#zipvoice), [Zonos](Speech/README.md#zonos) |
| `tts-and-voice-clone` | [Speech](Speech/README.md) | [VoxCPM](Speech/README.md#voxcpm) |
| `tts-and-voice-conversion` | [Speech](Speech/README.md) | [OpenVoice](Speech/README.md#openvoice) |
| `tts-dialogue` | [Speech](Speech/README.md) | [Chatterbox](Speech/README.md#chatterbox), [ElevenLabs](Speech/README.md#elevenlabs), [Fish-Speech](Speech/README.md#fish-speech), [IndexTTS](Speech/README.md#indextts), [MOSS](Speech/README.md#moss), [Sesame-CSM](Speech/README.md#sesame-csm), [VibeVoice](Speech/README.md#vibevoice) |
| `txt2audio` | [Music](Music/README.md) | [Stable-Audio](Music/README.md#stable-audio) |
| `txt2music` | [Music](Music/README.md) | [ACE-Step-1](Music/README.md#ace-step-1), [ACE-Step-1.5](Music/README.md#ace-step-15), [AudioX](Music/README.md#audiox), [Foundation-1](Music/README.md#foundation-1), [MiniMax-Music](Music/README.md#minimax-music), [MusicGen](Music/README.md#musicgen), [Pika](Music/README.md#pika), [Sonilo](Music/README.md#sonilo), [Stable-Audio](Music/README.md#stable-audio) |
| `voice-clone` | [Speech](Speech/README.md) | [CosyVoice](Speech/README.md#cosyvoice), [Dia](Speech/README.md#dia), [F5-TTS](Speech/README.md#f5-tts), [Fish-Speech](Speech/README.md#fish-speech), [Higgs-Audio](Speech/README.md#higgs-audio), [IndexTTS](Speech/README.md#indextts), [MARS5](Speech/README.md#mars5), [Maya](Speech/README.md#maya), [MOSS](Speech/README.md#moss), [NeuTTS](Speech/README.md#neutts), [Orpheus](Speech/README.md#orpheus), [Qwen3-TTS](Speech/README.md#qwen3-tts), [Sesame-CSM](Speech/README.md#sesame-csm), [Spark-TTS](Speech/README.md#spark-tts), [Step-Audio](Speech/README.md#step-audio), [VoxCPM](Speech/README.md#voxcpm), [Zonos](Speech/README.md#zonos) |
| `voice-conversion` | [Speech](Speech/README.md) | [Chatterbox](Speech/README.md#chatterbox), [ElevenLabs](Speech/README.md#elevenlabs), [RVC](Speech/README.md#rvc), [Seed-VC](Speech/README.md#seed-vc) |
| `voice-design` | [Speech](Speech/README.md) | [MOSS](Speech/README.md#moss), [Qwen3-TTS](Speech/README.md#qwen3-tts), [Zonos](Speech/README.md#zonos), [Other](Speech/README.md#other) |
| `voice-isolation` | [Speech](Speech/README.md) | [ElevenLabs](Speech/README.md#elevenlabs), [VoxLock](Speech/README.md#voxlock) |
| `voice-training` | [Speech](Speech/README.md) | [GPT-SoVITS](Speech/README.md#gpt-sovits), [RVC](Speech/README.md#rvc), [VoxCPM](Speech/README.md#voxcpm) |

## Naming and folder convention

- **Folders:** exactly three levels, `<section>/<Category>/<Model>/<file>.json`. Image and Video use the categories `Generation` (creates a new image or video), `Editing` (changes or analyses an existing one) and `Enhancement` (Image: upscaling only; Video: upscaling and frame interpolation). Audio uses `Music` and `Speech`. A model folder holds only workflow files, however many there are; there are no task subfolders.
- **Model folders** are TitleCase with hyphens and use one spelling across all sections (`Krea-2`, `FLUX-2`, `Qwen-Image`, `Wan-2.2`, `LTX-2`, `MiniMax-H3`, `ACE-Step-1.5`, `Qwen3-TTS`, `Whisper` ...). Generic, utility and multi-model workflows go in `Other/`.
- **File names** carry the task, because there is no task folder: `<task>[-<variant>][-<size>][-<precision>][-<feature>].json`, for example `Generation/Krea-2/txt2img-simple-int8-lora.json`, `Editing/Krea-2/outfit-transfer-v2.json`, `Enhancement/SeedVR2/upscale-7b-int8-native.json`. The model name is not repeated in the file name. Names are lowercase kebab-case and unique inside their folder; `-api` marks API-format graphs and `epNN` the tutorial episode a variant came from.
- **Common task prefixes:** `txt2img`, `img2img`, `img2prompt2img`, `controlnet`, `edit`, `multi-edit`, `inpaint`, `outpaint`, `object-removal`, `remove-background`, `outfit-change`, `relight`, `identity`, `reference`, `try-on`, `segment`, `depth-map`, `upscale`; `txt2video`, `img2video`, `ref2video`, `long-video`, `talking-avatar`, `lip-sync`, `character-swap`, `motion-transfer`, `frame-interpolation`; `txt2music`, `lyrics2song`, `cover`, `stem-split`, `tts`, `voice-clone`, `voice-design`, `voice-conversion`, `stt`, `subtitles`.

## Model coverage

Built from the category READMEs and the workflow files. "Covered" means at least one workflow in `03-Audio` loads the model; the number in brackets is how many workflows use that family as their main model. Families with several workflows usually cover several variants or modes (listed in the category README).

### Covered

- **Music generation and editing:** ACE-Step 1.5 turbo / SFT / base and 1.5 XL base / SFT / turbo, ACE-Step v1 3.5B (29 in total, incl. LoRA, cover, audio-to-audio, repaint, extend, stems, analysis and transcription), Stable Audio 3 Medium / Medium base (5), Stable Audio Open 1.0, YuE 2 (4) and YuE v1, HeartMuLa (4), MuLaCover (2), Tencent SongGeneration / LeVo / LeVo 2 (3), DiffRhythm (3) and DiffRhythm 2, SongBloom (2), AudioX (2), MusicGen, AudioLDM 2, MiniMax Music 3, Foundation-1, Pika (API), Sonilo Music 1.5 (API).
- **Sound effects:** Sony Woosh, Stable Audio 3, AudioX.
- **Singing voice:** SoulX-Singer (3).
- **Music analysis and transcription:** ACE-Step captioner / understand / transcriber, Music Flamingo, MuScriptor, SheetSage2, Spotify Basic Pitch, HeartMuLa lyrics transcriber.
- **Stem separation:** Demucs v4 (HT Demucs 4- and 6-stem, Hybrid Demucs), Mel-Band RoFormer, BS-RoFormer, MDX / UVR models through audio-separator, ensembles, SAM-Audio, ACE-Step extract.
- **Speech synthesis and voice cloning:** Qwen3-TTS (11 + voice designer), CosyVoice 300M / 2 / 3 (10), Fish Speech S2 / S2-Pro and Fish Audio API (8), IndexTTS 1.5 / 2 / 2.5 (7), Chatterbox / Multilingual / Turbo (6 + voice conversion), Dia 1.6B and Dia2 (5), F5-TTS (5), VibeVoice (5), Zonos v0.1 / ZONOS2 / ZONOS3 (5), MOSS-TTS / TTSD / VoiceGenerator (4), Sesame CSM-1B (4), Maya1 and Maya3 Indic (4), ElevenLabs API (4 + conversion, isolation, STT), VoxCPM / VoxCPM2 (3), OmniVoice (2), Higgs Audio v3 (2), Orpheus (2), GPT-SoVITS v2 (2), Step-Audio-EditX (2), and one workflow each for Bark, ChatTTS, DramaBox, FireRedTTS3, Kani-TTS, KittenTTS, Kokoro, Kyutai TTS, MARS5, MaskGCT, MeloTTS, MisoTTS, NeuTTS Air, OpenVoice, Parler-TTS, Spark-TTS, Supertonic 3, ZipVoice.
- **Voice conversion and clean-up:** RVC (3), Seed-VC (2), Chatterbox VC, ElevenLabs speech-to-speech; ClearerVoice / Resemble-Enhance / VoiceFixer, VoxLock, ElevenLabs voice isolation.
- **Speech recognition, subtitles and alignment:** Whisper large-v3 / turbo and smaller sizes, faster-whisper, Belle-whisper-large-v3-zh (6), Qwen3-ASR 0.6B / 1.7B and Qwen3-ForcedAligner (5), MOSS-Transcribe-Diarize (2), FunASR Paraformer (2), Nemotron ASR (2), Parakeet-TDT 0.6B v2, SenseVoiceSmall, Mega-ASR, IBM Granite Speech 4.0, VibeVoice-ASR, ElevenLabs Scribe and Fish Audio STT (API), torchaudio MMS aligner.
- **Speech translation:** Hibiki 2B, VoiceBridge (Qwen3-ASR + LLM + Qwen3-TTS).

### Mentioned in the docs but without a workflow

These are listed with the reason and an official link in the category READMEs ([music](Music/README.md#music-models-not-yet-available-in-comfyui), [speech](Speech/README.md#speech-models-not-yet-available-in-comfyui)). Some are only partly missing: a sibling version is covered above.

- **Music:** SongGen, MusicGen melody / continuation / style, MAGNeT, JASCO, Stable Audio 3 editing / inpainting / LoRA modes and SA3 Large, Stable Audio Open Small, AudioLDM2-Music, MusicLDM, Mustango, Riffusion, Microsoft Muzic models, MERT, MuQ / MuQ-MuLan standalone, HeartMuLa 7B, SongGeneration v2-medium / fast, InspireMusic, Magenta RealTime, DiffSinger and other SVS models, NotaGen and other symbolic models, MT3 and other transcription models, SCNet / Spleeter / Open-Unmix.
- **Speech:** XTTS-v2, StyleTTS2, Tortoise, Piper, VITS / Bert-VITS2, Matcha-TTS, GLM-TTS, Higgs Audio v2, OuteTTS, LLaSA, FireRedTTS 1 / 2, GPT-SoVITS v4 / v5, Kyutai Pocket TTS, Supertonic 2, MOSS-TTS Nano, Indic Parler-TTS, IndicF5, MagpieTTS, Distil-Whisper, whisper.cpp, WhisperX, Canary, Fun-ASR-Nano, Moonshine, Parakeet-TDT v3, MMS, SeamlessM4T, Omnilingual ASR, pyannote and other diarisation / VAD tools, and commercial speech APIs other than ElevenLabs and Fish Audio.

### Status unknown

Licence, VRAM or test status is "—" / "not recorded" for some rows that came from older tables (for example the Fish S2 and Qwen3-TTS node-pack examples). Treat those as untested and check the model card before use.

## How to use

1. Open the category README, pick a workflow and read its row: custom nodes, model files and folders, VRAM and licence.
2. Install the custom node packs (ComfyUI Manager can install missing nodes after you load the workflow) and download the model files into the folders shown.
3. Drag the `.json` file into ComfyUI. Replace sample audio, video or file paths in Load nodes with your own files; several workflows still hold the author's demo file names or local paths.
4. Check the licence before releasing anything, and get consent before cloning or converting a real person's voice.

Test notes: the Music README records which workflows were run on a test PC in November 2026 (Passed / Fixed / not working) and the node-pack fixes needed for transformers 5. Most speech workflows are marked **not yet tested**: they were only checked as loadable ComfyUI JSON.

See the [main README](../README.md) for setup steps, requirements and the other categories, or [`00-LIBRARY-INDEX.md`](../00-LIBRARY-INDEX.md) for the full list of workflows.
