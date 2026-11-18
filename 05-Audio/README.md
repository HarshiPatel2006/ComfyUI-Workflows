# Audio — ComfyUI workflows

Text-to-speech, voice cloning and voice design (Qwen3-TTS, Fish S2, ChatterBox); full-song and instrumental music generation (ACE-Step 1.5 / XL, YuE 2, YuE v1, HeartMuLa, MuLaCover, Tencent SongGeneration / LeVo 2, DiffRhythm, DiffRhythm 2, Stable Audio 3, Stable Audio Open, MusicGen, AudioLDM 2, MiniMax Music 3, Foundation-1); sound effects (Sony Woosh); music analysis, transcription to MIDI / ABC (MuScriptor, SheetSage2, ACE-Step) and stem separation (Demucs v4).

| Subfolder | What is inside | Workflows |
|---|---|---|
| [`Music-Generation/`](Music-Generation) | Music generation, covers, editing, LoRA, sound effects | 48 |
| [`Music-Analysis/`](Music-Analysis) | Describe and caption music (genre, BPM, key, tags) | 2 |
| [`Music-Transcription/`](Music-Transcription) | Audio to MIDI, ABC score and lyrics | 3 |
| [`Speech-and-Voice-Cloning/`](Speech-and-Voice-Cloning) | Text-to-speech and voice cloning | 11 |
| [`Stem-Separation/`](Stem-Separation) | Vocal, instrument and drum stem extraction | 4 |

## Workflows (68)

Licence column: **Commercial** = weights may be used commercially, **Non-commercial** = research / personal use only, **Community** = Stability AI Community License (free commercial use under USD 1M annual revenue, Enterprise licence above that). Always confirm on the model card before releasing music. VRAM figures are the node authors' numbers or rough estimates, not measurements.

### Custom node packs used in this folder

| Pack | Install |
|---|---|
| ComfyUI core (no install) | update ComfyUI to a 2026 build |
| ComfyUI-kaola-ace-step | [github.com/kana112233/ComfyUI-kaola-ace-step](https://github.com/kana112233/ComfyUI-kaola-ace-step) (also `pip install -e` the [ACE-Step-1.5](https://github.com/ace-step/ACE-Step-1.5) repo, see its README) |
| ACE-Step-ComfyUI (official, API client) | [github.com/ace-step/ACE-Step-ComfyUI](https://github.com/ace-step/ACE-Step-ComfyUI) |
| ComfyUI-AceStep_SFT | [github.com/jeankassio/ComfyUI-AceStep_SFT](https://github.com/jeankassio/ComfyUI-AceStep_SFT) |
| ComfyUI-FL-YuE2 | [github.com/filliptm/ComfyUI-FL-YuE2](https://github.com/filliptm/ComfyUI-FL-YuE2) |
| ComfyUI_YuE | [github.com/smthemex/ComfyUI_YuE](https://github.com/smthemex/ComfyUI_YuE) |
| Comfyui-Mulacover-T8 | [github.com/T8mars/Comfyui-Mulacover-T8](https://github.com/T8mars/Comfyui-Mulacover-T8) |
| comfyui_MuLaCover | [github.com/klossm/comfyui_MuLaCover](https://github.com/klossm/comfyui_MuLaCover) |
| ComfyUI_SongGeneration | [github.com/smthemex/ComfyUI_SongGeneration](https://github.com/smthemex/ComfyUI_SongGeneration) |
| ComfyUI_FL-SongGen | [github.com/filliptm/ComfyUI_FL-SongGen](https://github.com/filliptm/ComfyUI_FL-SongGen) |
| ComfyUI-Easy-SongGeneration | [github.com/eastmoe/ComfyUI-Easy-SongGeneration](https://github.com/eastmoe/ComfyUI-Easy-SongGeneration) |
| ComfyUI_DiffRhythm | [github.com/billwuhao/ComfyUI_DiffRhythm](https://github.com/billwuhao/ComfyUI_DiffRhythm) (needs system package `espeak-ng`) |
| ComfyUI_DiffRhythm2 | [github.com/billwuhao/ComfyUI_DiffRhythm2](https://github.com/billwuhao/ComfyUI_DiffRhythm2) (needs `espeak-ng`) |
| ComfyUI-MusicGen-HF | [github.com/ebrinz/ComfyUI-MusicGen-HF](https://github.com/ebrinz/ComfyUI-MusicGen-HF) |
| ComfyUI_VLM_nodes | [github.com/gokayfem/ComfyUI_VLM_nodes](https://github.com/gokayfem/ComfyUI_VLM_nodes) |
| ComfyUI_AudioTools | [github.com/lum3on/ComfyUI_AudioTools](https://github.com/lum3on/ComfyUI_AudioTools) |
| ComfyUI-Demucs-AudioSeparator | [github.com/Meisoftcoltd/ComfyUI-Demucs-AudioSeparator](https://github.com/Meisoftcoltd/ComfyUI-Demucs-AudioSeparator) |

### Music generation

#### ACE-Step 1.5 and 1.5 XL (weights MIT, commercial; 10–600 s, lyrics, instrumentals, BPM / key / time-signature metadata)

Core-node models from [Comfy-Org/ace_step_1.5_ComfyUI_files](https://huggingface.co/Comfy-Org/ace_step_1.5_ComfyUI_files): `acestep_v1.5_turbo.safetensors`, `acestep_v1.5_xl_base_bf16.safetensors`, `acestep_v1.5_xl_sft_bf16.safetensors` → `models/diffusion_models/`; `qwen_0.6b_ace15.safetensors` + one of `qwen_1.7b_ace15` / `qwen_4b_ace15` → `models/text_encoders/`; `ace_1.5_vae.safetensors` → `models/vae/`; all-in-one `ace_step_1.5_turbo_aio.safetensors` → `models/checkpoints/`. The kaola workflows use the original weights: `hf download ACE-Step/Ace-Step1.5 --local-dir ComfyUI/models/Ace-Step1.5`.

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence |
|---|---|---|---|---|---|
| [ace-step-v1.5-turbo-text-to-music-all-in-one](Music-Generation/ace-step-v1.5-turbo-text-to-music-all-in-one.json) | Text + lyrics to song, single all-in-one checkpoint (official Comfy-Org template) | `ace_step_1.5_turbo_aio.safetensors` | core | ~8 GB | Commercial |
| [ace-step-v1.5-turbo-text-to-music-1.7b-lm](Music-Generation/ace-step-v1.5-turbo-text-to-music-1.7b-lm.json) | Text + lyrics to song, split files with the 1.7B language model (official template) | `acestep_v1.5_turbo`, `qwen_0.6b_ace15`, `qwen_1.7b_ace15`, `ace_1.5_vae` | core | ~8 GB | Commercial |
| [ace-step-v1.5-turbo-text-to-music-4b-lm](Music-Generation/ace-step-v1.5-turbo-text-to-music-4b-lm.json) | Same with the larger 4B language model for better lyric and structure following (official template) | `acestep_v1.5_turbo`, `qwen_0.6b_ace15`, `qwen_4b_ace15`, `ace_1.5_vae` | core | ~12 GB | Commercial |
| [ace-step-v1.5-text-to-music-gemini-prompt-api](Music-Generation/ace-step-v1.5-text-to-music-gemini-prompt-api.json) | *PAID API* Gemini writes caption, lyrics and metadata, then ACE-Step generates locally (official template) | turbo split files | core (Gemini partner node, Comfy account credits) | ~8 GB | Commercial |
| [ace-step-v1.5-xl-base-text-to-music](Music-Generation/ace-step-v1.5-xl-base-text-to-music.json) | XL base model, highest quality, more steps (official template) | `acestep_v1.5_xl_base_bf16`, text encoders, VAE | core | ~20–24 GB | Commercial |
| [ace-step-v1.5-xl-sft-text-to-music](Music-Generation/ace-step-v1.5-xl-sft-text-to-music.json) | XL SFT model (official template) | `acestep_v1.5_xl_sft_bf16`, text encoders, VAE | core | ~20–24 GB | Commercial |
| [ace-step-v1.5-xl-turbo-text-to-music](Music-Generation/ace-step-v1.5-xl-turbo-text-to-music.json) | Text to Music | `qwen_0.6b_ace15.safetensors`, `qwen_4b_ace15.safetensors`, `ace_1.5_vae.safetensors` +1 more | ComfyUI-Pixaroma | ~20 GB | Commercial |
| [ace-step-v1.5-lyrics-to-song](Music-Generation/ace-step-v1.5-lyrics-to-song.json) | Caption + lyrics + BPM / key / time signature / duration to song | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial |
| [ace-step-v1.5-simple-mode](Music-Generation/ace-step-v1.5-simple-mode.json) | One-line description, the language model writes everything else | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial |
| [ace-step-v1.5-create-sample-to-music](Music-Generation/ace-step-v1.5-create-sample-to-music.json) | Language model creates caption, lyrics and metadata, then generates the song | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial |
| [ace-step-v1.5-repaint-section](Music-Generation/ace-step-v1.5-repaint-section.json) | Repaint: regenerate a time range of an existing song | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial |
| [ace-step-v1.5-complete-and-extend](Music-Generation/ace-step-v1.5-complete-and-extend.json) | Completion: continue / extend a partial song | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial |
| [ace-step-v1.5-cover](Music-Generation/ace-step-v1.5-cover.json) | Cover: re-perform a reference song in a new style, keeping its structure | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial |
| [ace-step-v1.5-lego-add-tracks](Music-Generation/ace-step-v1.5-lego-add-tracks.json) | Lego: add a new instrument / vocal layer on top of an existing track | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial |
| [ace-step-v1.5-lora-text-to-music](Music-Generation/ace-step-v1.5-lora-text-to-music.json) | Text to music with a trained ACE-Step LoRA | `Ace-Step1.5` + your LoRA | ComfyUI-kaola-ace-step | 6 GB+ | Commercial (check the LoRA) |
| [ace-step-v1.5-lora-cover](Music-Generation/ace-step-v1.5-lora-cover.json) | Cover with a LoRA style | `Ace-Step1.5` + your LoRA | ComfyUI-kaola-ace-step | 6 GB+ | Commercial (check the LoRA) |
| [ace-step-v1.5-lora-training](Music-Generation/ace-step-v1.5-lora-training.json) | LoRA Training (by ZETALVX) | `ace_step_1.5_turbo_aio.safetensors` | fl-acestep-training | 16 GB+ | Commercial |
| [ace-step-v1.5-sft-merge-lora-text-to-music](Music-Generation/ace-step-v1.5-sft-merge-lora-text-to-music.json) | High-quality text to music with SFT / merged models and LoRA stacking (by jeankassio) | ACE-Step 1.5 SFT or merged model (see pack README) | ComfyUI-AceStep_SFT | 12 GB+ | Commercial |
| [ace-step-v1.5-text-to-music-official-api-server](Music-Generation/ace-step-v1.5-text-to-music-official-api-server.json) | Official ACE-Step node: text2music, cover / remix, repaint and reference audio via a running ACE-Step 1.5 API server (local or remote) | served by the ACE-Step 1.5 server | ACE-Step-ComfyUI | on the server | Commercial |
| [ace-step-v1-audio-to-audio-editing](Music-Generation/ace-step-v1-audio-to-audio-editing.json) | Legacy ACE-Step v1 (3.5B): edit a song's style / lyrics audio-to-audio (official template) | [`ace_step_v1_3.5b.safetensors`](https://huggingface.co/Comfy-Org/ACE-Step_ComfyUI_repackaged/resolve/main/all_in_one/ace_step_v1_3.5b.safetensors) → `checkpoints` | core | ~10 GB | Commercial (Apache-2.0) |

#### YuE 2 and YuE v1 (lyrics + style to full song)

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence |
|---|---|---|---|---|---|
| [yue2-lyrics-to-song](Music-Generation/yue2-lyrics-to-song.json) | Lyrics to Song (YuE 2) with SheetSage melody-to-ABC | `yue2_3b_bf16.safetensors`, `sheetsage2_bf16.safetensors` | — | ~12 GB | Non-commercial (CC BY-NC 4.0) |
| [yue2-music-cover](Music-Generation/yue2-music-cover.json) | Cover: SheetSage2 transcribes a reference song to ABC, YuE 2 sings it in a new style (official template) | [`yue2_3b_int8_convrot.safetensors`](https://huggingface.co/Comfy-Org/YuE2/resolve/main/checkpoints/yue2_3b_int8_convrot.safetensors) → `checkpoints`, [`sheetsage2_bf16.safetensors`](https://huggingface.co/Comfy-Org/YuE2/resolve/main/audio_encoders/sheetsage2_bf16.safetensors) → `audio_encoders` | core | ~8 GB | Non-commercial |
| [yue2-score-editor-to-song](Music-Generation/yue2-score-editor-to-song.json) | Write / edit the melody and chords in a score (ABC / piano-roll) editor, then render the song (by filliptm) | YuE 2 weights (auto-download, see pack README) | ComfyUI-FL-YuE2 | ~12 GB | Non-commercial |
| [yue2-lyrics-to-song-and-cover-smthemex](Music-Generation/yue2-lyrics-to-song-and-cover-smthemex.json) | Lyrics to song with optional reference audio for cover mode (by smthemex) | `m-a-p/YuE2-3B` → `diffusion_models`, `m-a-p/YuE2-Vae` → `vae`, `m-a-p/SheetSage2` + `m-a-p/MERT-v2-FullSong` → `clip` | ComfyUI_YuE | ~12 GB | Non-commercial |
| [yue-v1-lyrics-to-song-legacy](Music-Generation/yue-v1-lyrics-to-song-legacy.json) | Legacy YuE v1 (7B stage 1 + 1B stage 2) lyrics to song. Install ComfyUI_YuE at commit `d560498`: current main only supports YuE 2 | `YuE-s1-7B-anneal-en-cot`, `YuE-s2-1B-general`, `xcodec_mini_infer`, `YuE-upsampler` → `models/yue/` | ComfyUI_YuE (pinned) | 24 GB fp16, 16 GB with int8 / offload | Commercial (Apache-2.0) |

#### HeartMuLa and MuLaCover

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence |
|---|---|---|---|---|---|
| [heartmula-fl-text-to-song](Music-Generation/heartmula-fl-text-to-song.json) | Text to Song with HeartMuLa, tags builder and lyrics (workflow by filliptm) | HeartMuLa model weights (several GB), downloaded separately | ComfyUI_FL-HeartMuLa | ~16 GB | Commercial (Apache-2.0) |
| [heartmula-lyrics-and-style-to-song](Music-Generation/heartmula-lyrics-and-style-to-song.json) | Lyrics and Style to full Song with HeartMuLa (workflow by benjiyaya) | HeartMuLa model weights (several GB), downloaded separately | HeartMuLa_ComfyUI | ~16 GB | Commercial (Apache-2.0) |
| [heartmula-lyrics-transcriber](Music-Generation/heartmula-lyrics-transcriber.json) | Lyrics Transcriber: extract lyrics from a song with HeartMuLa (workflow by benjiyaya) | HeartMuLa model weights (several GB), downloaded separately | HeartMuLa_ComfyUI, ComfyUI-VideoHelperSuite, ComfyUI-Custom-Scripts | — | Commercial (Apache-2.0) |
| [mulacover-audio-remix](Music-Generation/mulacover-audio-remix.json) | MuLaCover cover / remix of a reference song with a new style (by T8mars) | [HeartMuLa/MuLaCover](https://huggingface.co/HeartMuLa/MuLaCover) + HeartCodec-oss → `models/MuLaCover-T8/` | Comfyui-Mulacover-T8 | ~24 GB | Non-commercial (CC BY-NC 4.0) |
| [mulacover-cover-from-reference-or-midi](Music-Generation/mulacover-cover-from-reference-or-midi.json) | MuLaCover cover from reference audio or from a melody / chord MIDI file (by klossm) | MuLaCover, HeartCodec-oss, Qwen3-Embedding-0.6B, YourMT3 transcriber (~10 GB, reference-audio mode only) → `models/MuLaCover/` | comfyui_MuLaCover | ~12 GB | Non-commercial |

#### Tencent SongGeneration / LeVo / LeVo 2

The official repo is currently offline and the weight licence could not be verified; the report lists it as **non-commercial**. Treat it as non-commercial.

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence |
|---|---|---|---|---|---|
| [songgeneration-levo-2-lyrics-to-song](Music-Generation/songgeneration-levo-2-lyrics-to-song.json) | Lyrics + description (+ optional audio prompt) to full song up to 4m30s, LeVo 2 / v1 and GGUF (by smthemex) | `large_model_v2.pt` (from [lglg666/SongGeneration-v2-large](https://huggingface.co/lglg666/SongGeneration-v2-large)), `new_auto_prompt.pt`, `htdemucs.pth` → `models/SongGeneration/`; GGUF in `models/gguf/` | ComfyUI_SongGeneration | 12 GB+ | Non-commercial |
| [songgeneration-levo-style-transfer](Music-Generation/songgeneration-levo-style-transfer.json) | LeVo v1 lyrics to song with auto-style and style transfer from a reference clip (by filliptm) | auto-download → `models/songgen/` | ComfyUI_FL-SongGen | 10–28 GB by model size | Non-commercial |
| [songgeneration-levo-2-easy-fp4](Music-Generation/songgeneration-levo-2-easy-fp4.json) | LeVo 2 large with fp4 quantisation and a lyrics / style formatter (by eastmoe) | SongGeneration-v2-large (see pack README) | ComfyUI-Easy-SongGeneration | ~10 GB | Non-commercial |

#### DiffRhythm and DiffRhythm 2 (weights Apache-2.0, commercial)

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence |
|---|---|---|---|---|---|
| [diffrhythm-lyrics-and-style-to-song](Music-Generation/diffrhythm-lyrics-and-style-to-song.json) | Timed LRC lyrics + style prompt to song, 95 s (base / v1.2) or 285 s (full); leave lyrics empty for instrumental (by billwuhao) | `cfm_model_v1_2.pt`, `cfm_full_model.pt`, DiffRhythm-vae, MuQ-MuLan-large, MuQ-large-msd-iter, xlm-roberta-base (see pack README) | ComfyUI_DiffRhythm | ~8 GB | Commercial |
| [diffrhythm-reference-audio-style-to-song](Music-Generation/diffrhythm-reference-audio-style-to-song.json) | Song in the style of a reference audio clip | same | ComfyUI_DiffRhythm | ~8 GB | Commercial |
| [diffrhythm-edit-song-sections](Music-Generation/diffrhythm-edit-song-sections.json) | Edit / regenerate chosen sections of an existing song | same | ComfyUI_DiffRhythm | ~8 GB | Commercial |
| [diffrhythm-2-lyrics-and-style-to-song](Music-Generation/diffrhythm-2-lyrics-and-style-to-song.json) | DiffRhythm 2 block flow matching: section-tagged lyrics + style text (or a reference song) to song up to 3m30s. Built for this library from the pack's only node, which ships no example | [ASLP-lab/DiffRhythm2](https://huggingface.co/ASLP-lab/DiffRhythm2), MuQ-MuLan-large, xlm-roberta-base (auto-download → `models/TTS/DiffRhythm/`) | ComfyUI_DiffRhythm2 | ~10 GB | Commercial |

#### Stable Audio, MusicGen, AudioLDM 2 and others

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence |
|---|---|---|---|---|---|
| [stable-audio-3-text-to-music](Music-Generation/stable-audio-3-text-to-music.json) | Text to Music | `t5gemma_b_b_ul2.safetensors`, `stable_audio_3_medium.safetensors` | ComfyUI-Pixaroma | ~12 GB | Community |
| [stable-audio-3-medium-base-text-to-music](Music-Generation/stable-audio-3-medium-base-text-to-music.json) | Text to music / audio with the non-distilled SA3 Medium base model and a Qwen 3.5 prompt rewriter (official template). Swap the checkpoint to the Small-Music weights from the same repo for the small model | [`stable_audio_3_medium_base`](https://huggingface.co/Comfy-Org/stable-audio-3) → `checkpoints`, `t5gemma_b_b_ul2`, `qwen3.5_2b_bf16` → `text_encoders` | core | 12–16 GB | Community |
| [stable-audio-3-image-to-music-gemma-4](Music-Generation/stable-audio-3-image-to-music-gemma-4.json) | Image to Music + Gemma 4 | `stable_audio_3_medium.safetensors`, `t5gemma_b_b_ul2.safetensors`, `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma | ~16 GB | Community |
| [stable-audio-3-text-to-music-gemma-4-prompt-enhancer](Music-Generation/stable-audio-3-text-to-music-gemma-4-prompt-enhancer.json) | Text to Music + Gemma 4 Prompt Enhancer | `stable_audio_3_medium.safetensors`, `t5gemma_b_b_ul2.safetensors`, `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma | ~16 GB | Community |
| [stable-audio-3-text-to-sound-effects-gemma-4](Music-Generation/stable-audio-3-text-to-sound-effects-gemma-4.json) | Text to Sound Effects + Gemma 4 | `stable_audio_3_medium.safetensors`, `t5gemma_b_b_ul2.safetensors`, `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma | ~16 GB | Community |
| [stable-audio-open-1.0-text-to-audio](Music-Generation/stable-audio-open-1.0-text-to-audio.json) | Stable Audio Open 1.0 text to music / sound up to 47 s (official template) | [`stable-audio-open-1.0.safetensors`](https://huggingface.co/stabilityai/stable-audio-open-1.0) → `checkpoints`, `t5-base` → `text_encoders` | core | 6–8 GB | Community |
| [musicgen-text-to-music-bpm-loop](Music-Generation/musicgen-text-to-music-bpm-loop.json) | MusicGen text to music with BPM / bar-length duration and looping preview (by ebrinz) | `facebook/musicgen-*` (auto-download from HuggingFace) | ComfyUI-MusicGen-HF | 4 / 8 / 16 GB (small / medium / large) | Non-commercial (CC BY-NC 4.0) |
| [audioldm2-image-to-music-llava](Music-Generation/audioldm2-image-to-music-llava.json) | LLaVA describes an image, AudioLDM 2 turns the description into music (by gokayfem). Uses the general `cvssp/audioldm2` checkpoint, not `audioldm2-music` | `cvssp/audioldm2` (auto-download), LLaVA GGUF (see pack README) | ComfyUI_VLM_nodes | ~8 GB | Non-commercial (CC BY-NC-SA 4.0) |
| [minimax-music-3-text-to-music](Music-Generation/minimax-music-3-text-to-music.json) | Text to Music | `minimax_music3_dit_int8_convrot.safetensors`, `minimax_music3_text_encoder_pruned_int8_convrot.safetensors`, `minimax_music3_dav.safetensors` | ComfyUI-Pixaroma | — | see model card |
| [foundation-1-text-to-music-loops](Music-Generation/foundation-1-text-to-music-loops.json) | Text to Music Loops and Samples (Foundation-1) that follow key, bar count and BPM (node pack by Saganaki22) | `Foundation_1.safetensors` (auto-downloaded by the node pack) | ComfyUI-Foundation-1 | — | see model card |
| [woosh-text-and-video-to-sound-effects](Music-Generation/woosh-text-and-video-to-sound-effects.json) | Text to Sound Effects and Video to Sound Effects (Sony Woosh) | `Woosh-Flow`, `Woosh-VFlow-8s` | ComfyUI-Woosh, ComfyUI-VideoHelperSuite | — | see model card |

### Music analysis

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence |
|---|---|---|---|---|---|
| [ace-step-v1.5-understand-audio](Music-Analysis/ace-step-v1.5-understand-audio.json) | Understand a song: caption, lyrics, BPM, key, time signature, duration (reusable as a prompt) | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial |
| [ace-step-v1.5-audio-captioner](Music-Analysis/ace-step-v1.5-audio-captioner.json) | Detailed music caption with the ACE-Step captioner (Qwen2.5-Omni-7B based) | `acestep-captioner` → `models/Ace-Step1.5/` | ComfyUI-kaola-ace-step | ~16 GB | Commercial (check Qwen licence) |

### Music transcription

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence |
|---|---|---|---|---|---|
| [muscriptor-audio-to-midi-transcription](Music-Transcription/muscriptor-audio-to-midi-transcription.json) | Audio to MIDI multi-instrument transcription (MuScriptor by Kyutai and Mirelo; example workflow by martyyz-ai). The MuScriptor weights are gated on HuggingFace: accept the CC BY-NC 4.0 licence and log in to HuggingFace; they auto-download on first use | MuScriptor `large` (auto-downloaded by the node pack) | [ComfyUI-MuScriptor](https://github.com/martyyz-ai/ComfyUI-MuScriptor), ComfyUI-Custom-Scripts | — | Non-commercial |
| [sheetsage2-audio-to-abc-melody-and-chords](Music-Transcription/sheetsage2-audio-to-abc-melody-and-chords.json) | SheetSage2: transcribe a song's melody (and melody + chords) to an ABC score; open it in an ABC editor to export MIDI. Built for this library from core nodes | [`sheetsage2_bf16.safetensors`](https://huggingface.co/Comfy-Org/YuE2/resolve/main/audio_encoders/sheetsage2_bf16.safetensors) → `audio_encoders` | core | ~4 GB | Non-commercial (CC BY-NC 4.0) |
| [ace-step-v1.5-lyrics-transcriber](Music-Transcription/ace-step-v1.5-lyrics-transcriber.json) | Transcribe sung lyrics from a song with the ACE-Step transcriber | `acestep-transcriber` → `models/Ace-Step1.5/` | ComfyUI-kaola-ace-step | ~16 GB | Commercial (check model card) |

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

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence |
|---|---|---|---|---|---|
| [demucs-htdemucs-4-stem-separation](Stem-Separation/demucs-htdemucs-4-stem-separation.json) | Demucs v4 (HT Demucs) 4 stems: vocals, drums, bass, other (official Comfy-Org template) | `htdemucs` (auto-download to the torch hub cache) | ComfyUI_AudioTools | ~4 GB | Commercial (MIT) |
| [demucs-htdemucs-6s-six-stem-separation](Stem-Separation/demucs-htdemucs-6s-six-stem-separation.json) | Demucs v4 6 stems: vocals, drums, bass, other, guitar, piano, plus an instrumental mix. Built for this library from the pack's separator node | `htdemucs_6s` (auto-download to `models/demucs/`) | ComfyUI-Demucs-AudioSeparator | ~4 GB (cpu option) | Commercial (MIT) |
| [demucs-mdx-audio-separator-stem-separation](Stem-Separation/demucs-mdx-audio-separator-stem-separation.json) | Demucs + MDX + Audio Separator stem extraction: vocals, instruments and percussion from any track (by ZETALVX) | — | audio-separation, audio-separation-nodes-comfyui | ~4 GB | Commercial (MIT) |
| [ace-step-v1.5-extract-stems](Stem-Separation/ace-step-v1.5-extract-stems.json) | ACE-Step extraction: pull a single track (vocals, drums, bass…) out of a mix generatively | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial |

## Not yet available in ComfyUI

Models from the November 2026 open-source music model report that have no working ComfyUI node pack or workflow yet, so no workflow is included for them.

| Model | Capability | Why there is no workflow | Official link |
|---|---|---|---|
| SongGen | Lyrics + text + optional 3 s singer reference; mixed or separate vocal / accompaniment tracks | No ComfyUI node exists (the "FL-SongGen" pack is Tencent SongGeneration, not this model) | [github.com/LiuZH-19/SongGen](https://github.com/LiuZH-19/SongGen) |
| MusicGen melody conditioning, continuation, stereo | Melody-guided generation, continuing an audio clip | Packs list the model variants but none publishes a working melody / continuation workflow; text-to-music is covered above | [github.com/facebookresearch/audiocraft](https://github.com/facebookresearch/audiocraft) |
| MusicGen-Style | Text + short reference excerpt | No ComfyUI node; AudioCraft only | [audiocraft MusicGen-Style docs](https://github.com/facebookresearch/audiocraft/blob/main/docs/MUSICGEN_STYLE.md) |
| MAGNeT | Non-autoregressive text to music | No ComfyUI node; AudioCraft only | [audiocraft MAGNeT docs](https://github.com/facebookresearch/audiocraft/blob/main/docs/MAGNET.md) |
| JASCO | Text + chords + drums + melody | No ComfyUI node; AudioCraft only | [audiocraft JASCO docs](https://github.com/facebookresearch/audiocraft/blob/main/docs/JASCO.md) |
| Stable Audio 3 audio-to-audio editing, inpainting, continuation, LoRA | Editing and extending audio | No local ComfyUI template or node for these modes yet (only archived paid Stability API nodes) | [huggingface.co/Comfy-Org/stable-audio-3](https://huggingface.co/Comfy-Org/stable-audio-3) |
| Stable Audio 3 Large | Text to music | API-only, weights not released | [stability.ai](https://stability.ai/stable-audio) |
| Stable Audio Open Small | Fast short text to audio | No ComfyUI template or repack; runs in stable-audio-tools | [huggingface.co/stabilityai/stable-audio-open-small](https://huggingface.co/stabilityai/stable-audio-open-small) |
| AudioLDM2-Music | Music-tuned AudioLDM 2 | The only working node hard-codes the general `cvssp/audioldm2` checkpoint (used above) | [huggingface.co/cvssp/audioldm2-music](https://huggingface.co/cvssp/audioldm2-music) |
| MusicLDM | Text to music | In diffusers, but no ComfyUI node wraps it | [huggingface.co/ucsd-reach/musicldm](https://huggingface.co/ucsd-reach/musicldm) |
| Mustango | Text to music with chord / beat / tempo control | Custom pipeline, no ComfyUI node | [github.com/AMAAI-Lab/mustango](https://github.com/AMAAI-Lab/mustango) |
| Riffusion v1 | Spectrogram-diffusion text to music | A spectrogram-to-audio pack exists ([ComfyUI-Riffusion](https://github.com/traugdor/ComfyUI-Riffusion)) but no published, working workflow | [huggingface.co/riffusion/riffusion-model-v1](https://huggingface.co/riffusion/riffusion-model-v1) |
| MuseCoco | Text to MIDI | Research code, no ComfyUI node | [github.com/microsoft/muzic](https://github.com/microsoft/muzic/tree/main/musecoco) |
| GETMusic | Multi-track MIDI completion / infilling | Research code, no ComfyUI node | [github.com/microsoft/muzic](https://github.com/microsoft/muzic/tree/main/getmusic) |
| Museformer | Symbolic music generation | Research code, no ComfyUI node | [github.com/microsoft/muzic](https://github.com/microsoft/muzic/tree/main/museformer) |
| MeloForm | Melody generation with musical form | Research code, no ComfyUI node | [github.com/microsoft/muzic](https://github.com/microsoft/muzic/tree/main/meloform) |
| PopMAG | Multi-track pop accompaniment | No public weights | [github.com/microsoft/muzic](https://github.com/microsoft/muzic) |
| MusicBERT | Symbolic music understanding | Understanding model, no generator and no ComfyUI node | [github.com/microsoft/muzic](https://github.com/microsoft/muzic/tree/main/musicbert) |
| CLaMP | Music–text retrieval | Retrieval model, no ComfyUI node | [github.com/microsoft/muzic](https://github.com/microsoft/muzic/tree/main/clamp) |
| MERT v1 | Music embeddings / tagging | No ComfyUI node exposes embeddings (only used internally by one ACE-Step analyzer) | [huggingface.co/m-a-p/MERT-v1-330M](https://huggingface.co/m-a-p/MERT-v1-330M) |
| MERT2-30s, MERT2-FullSong | Music embeddings | Used only inside ComfyUI core's SheetSage2 / YuE 2 cover path, no standalone node | [huggingface.co/m-a-p](https://huggingface.co/m-a-p) |
| MuQ, MuQ-MuLan | Music embeddings and music–text similarity | Used only inside DiffRhythm packs for style prompts, no standalone node | [github.com/tencent-ailab/MuQ](https://github.com/tencent-ailab/MuQ) |
| SheetSage2 beats, key, structure, MIDI output | Full transcription | The ComfyUI node outputs ABC (melody / chords) only; see the SheetSage2 workflow above | [huggingface.co/Comfy-Org/YuE2](https://huggingface.co/Comfy-Org/YuE2) |
| HeartMuLa 7B | Larger HeartMuLa | Announced, not released | [github.com/HeartMuLa](https://github.com/HeartMuLa) |
| SongGeneration v2-medium / v2-fast | Smaller LeVo 2 variants | Announced, not released | [huggingface.co/tencent/SongGeneration](https://huggingface.co/tencent/SongGeneration) |
| DiffRhythm 2 song extension and instrumental mode | Extend songs, instrumentals | Listed as TODO upstream | [github.com/xiaomi-research/diffrhythm2](https://github.com/xiaomi-research/diffrhythm2) |

See the [main README](../README.md) for setup steps, requirements and the other categories, or [`00-LIBRARY-INDEX.md`](../00-LIBRARY-INDEX.md) for the full list of workflows.
