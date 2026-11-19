# Audio — ComfyUI workflows

229 ComfyUI workflows for music and speech: song and instrumental generation, covers and editing, sound effects, singing voices, music analysis and transcription, stem separation, text-to-speech and voice cloning, voice conversion, speech clean-up, speech-to-text and subtitles, speech translation and forced alignment.

Workflows are grouped by **what they do**. Each workflow has one folder; the two large speech folders keep one subfolder per model family. Every category README has a table per subcategory with the workflow link, what it does, the models and custom nodes it needs, and the licence, VRAM and test notes that were recorded for it.

## Folders

| Category | Subfolder | What is inside | Workflows |
|---|---|---|---|
| **[Music](Music/README.md)** (80) | [`Text-to-Music-and-Songs/`](Music/Text-to-Music-and-Songs) | Text, lyrics, style or image to full songs, instrumentals, loops and general audio | 37 |
| | [`Covers-Remixing-and-Editing/`](Music/Covers-Remixing-and-Editing) | Covers, style transfer, repaint, extend, add tracks, edit sections | 15 |
| | [`Music-LoRA-and-Training/`](Music/Music-LoRA-and-Training) | Generate with a music LoRA, or train one | 4 |
| | [`Sound-Effects-and-Ambience/`](Music/Sound-Effects-and-Ambience) | Text- and video-to-sound effects and foley | 3 |
| | [`Singing-Voice-Synthesis/`](Music/Singing-Voice-Synthesis) | Melody / lyrics to a sung vocal, re-singing, lyric editing | 3 |
| | [`Music-Analysis-and-Captioning/`](Music/Music-Analysis-and-Captioning) | Describe and caption music (genre, BPM, key, tags) | 3 |
| | [`Music-Transcription-and-MIDI/`](Music/Music-Transcription-and-MIDI) | Audio to MIDI, ABC score and sung lyrics | 5 |
| | [`Stem-Separation/`](Music/Stem-Separation) | Vocal, instrument and drum stem extraction | 10 |
| **[Speech](Speech/README.md)** (149) | [`Text-to-Speech-and-Voice-Cloning/`](Speech/Text-to-Speech-and-Voice-Cloning/README.md) | Text-to-speech, voice cloning, voice design, multi-speaker dialogue, speech editing; one subfolder per model family | 110 |
| | [`Voice-Conversion/`](Speech/Voice-Conversion) | Speech-to-speech voice conversion and voice changers | 7 |
| | [`Speech-Enhancement-and-Cleanup/`](Speech/Speech-Enhancement-and-Cleanup) | Denoise, enhance, isolate a speaker | 5 |
| | [`Speech-to-Text-and-Subtitles/`](Speech/Speech-to-Text-and-Subtitles/README.md) | Speech recognition, subtitles, diarisation; one subfolder per model family | 22 |
| | [`Speech-Translation/`](Speech/Speech-Translation) | Speech-to-speech and transcribe-translate-revoice | 2 |
| | [`Forced-Alignment/`](Speech/Forced-Alignment) | Align a script, SRT or lyric file to audio with word timestamps | 3 |
| **Total** | | | **229** |

### Finding a task

| I want to… | Look in |
|---|---|
| Make a song or instrumental from text / lyrics | [Music → Text to music and full songs](Music/README.md#text-to-music-and-full-songs) |
| Cover, remix, extend or repaint a song | [Music → Covers, remixing and editing](Music/README.md#covers-remixing-and-editing) |
| Train or use a music LoRA | [Music → Music LoRA and fine-tuning](Music/README.md#music-lora-and-fine-tuning) |
| Make sound effects or foley | [Music → Sound effects and ambience](Music/README.md#sound-effects-and-ambience) |
| Synthesise or re-sing a vocal | [Music → Singing voice synthesis](Music/README.md#singing-voice-synthesis) |
| Caption or analyse a song, transcribe to MIDI / ABC / lyrics | [Music analysis](Music/README.md#music-analysis-and-captioning), [Music transcription](Music/README.md#music-transcription-lyrics-and-midi) |
| Split vocals and instruments | [Music → Stem separation](Music/README.md#stem-separation-and-vocal-extraction) |
| Text-to-speech, voice cloning, voice design, dialogue | [Text-to-Speech README](Speech/Text-to-Speech-and-Voice-Cloning/README.md) (with a find-by-task index) |
| Change one voice into another | [Speech → Voice conversion](Speech/README.md#voice-conversion) |
| Clean up or isolate speech | [Speech → Speech enhancement and clean-up](Speech/README.md#speech-enhancement-and-clean-up) |
| Transcribe, subtitle or diarise speech | [Speech-to-Text README](Speech/Speech-to-Text-and-Subtitles/README.md) |
| Translate speech | [Speech → Speech translation](Speech/README.md#speech-translation) |
| Get word timestamps for a known script | [Speech → Forced alignment](Speech/README.md#forced-alignment) |

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
