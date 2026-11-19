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

**Test column:** every workflow added in November 2026 was queued through the ComfyUI API on one PC (RTX 5060 Ti 16 GB, 32 GB RAM, Linux, ComfyUI 0.43, frontend 1.57, PyTorch 2.11 + CUDA 13, transformers 5.22) with short, low-step renders, and the output files were checked for real audio. **Passed** = ran unchanged. **Fixed** = needed a change to the workflow file (already applied here) and/or to the node pack (see [Node-pack fixes for transformers 5](#node-pack-fixes-for-transformers-5)). Most packs were written for transformers 4; on a ComfyUI that already uses transformers 5 they fail until patched.

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

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence | Test |
|---|---|---|---|---|---|---|
| [ace-step-v1.5-turbo-text-to-music-all-in-one](Music-Generation/ace-step-v1.5-turbo-text-to-music-all-in-one.json) | Text + lyrics to song, single all-in-one checkpoint (official Comfy-Org template) | `ace_step_1.5_turbo_aio.safetensors` | core | ~8 GB | Commercial | Passed: 30 s render in 5 s |
| [ace-step-v1.5-turbo-text-to-music-1.7b-lm](Music-Generation/ace-step-v1.5-turbo-text-to-music-1.7b-lm.json) | Text + lyrics to song, split files with the 1.7B language model (official template) | `acestep_v1.5_turbo`, `qwen_0.6b_ace15`, `qwen_1.7b_ace15`, `ace_1.5_vae` | core | ~8 GB | Commercial | Passed: 20 s |
| [ace-step-v1.5-turbo-text-to-music-4b-lm](Music-Generation/ace-step-v1.5-turbo-text-to-music-4b-lm.json) | Same with the larger 4B language model for better lyric and structure following (official template) | `acestep_v1.5_turbo`, `qwen_0.6b_ace15`, `qwen_4b_ace15`, `ace_1.5_vae` | core | ~12 GB | Commercial | Passed: 20 s |
| [ace-step-v1.5-text-to-music-qwen3.5-local-prompt-writer](Music-Generation/ace-step-v1.5-text-to-music-qwen3.5-local-prompt-writer.json) | A local LLM (Qwen 3.5 2B, ComfyUI core TextGenerate) writes style tags and lyrics from a one-line idea, then ACE-Step turbo renders the song. Built from the official Gemini-API template with the paid Gemini node replaced | turbo split files + [`qwen3.5_2b_bf16.safetensors`](https://huggingface.co/Comfy-Org/Qwen3.5/resolve/main/text_encoders/qwen3.5_2b_bf16.safetensors) (4.5 GB) → `text_encoders` | core | ~10 GB (fits 16 GB; ComfyUI unloads the LLM before the render when needed) | Commercial (ACE-Step MIT, Qwen 3.5 Apache-2.0) | Fixed: paid Gemini node replaced by local Qwen 3.5 2B TextGenerate (captain request); 20 s |
| [ace-step-v1.5-xl-base-text-to-music](Music-Generation/ace-step-v1.5-xl-base-text-to-music.json) | XL base model, highest quality, more steps (official template) | `acestep_v1.5_xl_base_bf16`, text encoders, VAE | core | ~20–24 GB | Commercial | Passed: 20 s, 12 steps |
| [ace-step-v1.5-xl-sft-text-to-music](Music-Generation/ace-step-v1.5-xl-sft-text-to-music.json) | XL SFT model (official template) | `acestep_v1.5_xl_sft_bf16`, text encoders, VAE | core | ~20–24 GB | Commercial | Passed: 20 s, 12 steps |
| [ace-step-v1.5-xl-turbo-text-to-music](Music-Generation/ace-step-v1.5-xl-turbo-text-to-music.json) | Text to Music | `qwen_0.6b_ace15.safetensors`, `qwen_4b_ace15.safetensors`, `ace_1.5_vae.safetensors` +1 more | ComfyUI-Pixaroma | ~20 GB | Commercial | — (earlier library workflow, not part of this test) |
| [ace-step-v1.5-lyrics-to-song](Music-Generation/ace-step-v1.5-lyrics-to-song.json) | Caption + lyrics + BPM / key / time signature / duration to song | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial | Fixed: kaola pack patched for transformers 5 (DiT built without meta init, FA2->sdpa fallback, vector-quantize cpu levels); widget values re-mapped to the current node inputs; 20 s turbo |
| [ace-step-v1.5-simple-mode](Music-Generation/ace-step-v1.5-simple-mode.json) | One-line description, the language model writes everything else | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial | Fixed: same pack patches and widget re-map; turbo 8 steps |
| [ace-step-v1.5-create-sample-to-music](Music-Generation/ace-step-v1.5-create-sample-to-music.json) | Language model creates caption, lyrics and metadata, then generates the song | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial | Fixed: same patches; added ACE_STEP_ClearVRAM between the sample writer and the renderer (pack patched so ClearVRAM frees node handlers) to fit 16 GB |
| [ace-step-v1.5-repaint-section](Music-Generation/ace-step-v1.5-repaint-section.json) | Repaint: regenerate a time range of an existing song | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial | Fixed: same patches; repainted 0-5 s of a 30 s clip |
| [ace-step-v1.5-complete-and-extend](Music-Generation/ace-step-v1.5-complete-and-extend.json) | Completion: continue / extend a partial song | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial | Fixed: same patches; base model, 20 steps (node minimum) |
| [ace-step-v1.5-cover](Music-Generation/ace-step-v1.5-cover.json) | Cover: re-perform a reference song in a new style, keeping its structure | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial | Fixed: same patches; cover of a 30 s clip |
| [ace-step-v1.5-lego-add-tracks](Music-Generation/ace-step-v1.5-lego-add-tracks.json) | Lego: add a new instrument / vocal layer on top of an existing track | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial | Fixed: same patches; base model, 20 steps |
| [ace-step-v1.5-lora-text-to-music](Music-Generation/ace-step-v1.5-lora-text-to-music.json) | Text to music with a trained ACE-Step LoRA | `Ace-Step1.5` + your LoRA | ComfyUI-kaola-ace-step | 6 GB+ | Commercial (check the LoRA) | Fixed: same patches; ACE-Step-v1.5-chinese-new-year-LoRA, 20 s |
| [ace-step-v1.5-lora-cover](Music-Generation/ace-step-v1.5-lora-cover.json) | Cover with a LoRA style | `Ace-Step1.5` + your LoRA | ComfyUI-kaola-ace-step | 6 GB+ | Commercial (check the LoRA) | Fixed: same patches; LoRA cover of a 30 s clip |
| [ace-step-v1.5-lora-training](Music-Generation/ace-step-v1.5-lora-training.json) | LoRA Training (by ZETALVX) | `ace_step_1.5_turbo_aio.safetensors` | fl-acestep-training | 16 GB+ | Commercial | — (earlier library workflow, not part of this test) |
| [ace-step-v1.5-sft-merge-lora-text-to-music](Music-Generation/ace-step-v1.5-sft-merge-lora-text-to-music.json) | High-quality text to music with SFT / merged models and LoRA stacking (by jeankassio) | `acestep_v1.5_xl_sft_bf16`, `qwen_0.6b_ace15`, `qwen_4b_ace15`, `ace_1.5_vae` (core file names) + an ACE-Step LoRA in `models/loras/` | ComfyUI-AceStep_SFT | 12 GB+ | Commercial | — (earlier library workflow, not part of this test) |
| [ace-step-v1.5-text-to-music-official-api-server](Music-Generation/ace-step-v1.5-text-to-music-official-api-server.json) | Official ACE-Step node: text2music, cover / remix, repaint and reference audio via a running ACE-Step 1.5 API server. Ships in cloud mode (api.acemusic.ai key); for local mode run `acestep-openrouter --port 8002` from an [ACE-Step-1.5](https://github.com/ace-step/ACE-Step-1.5) checkout in its own environment (it needs transformers<4.58) and set mode = local | served by the ACE-Step 1.5 server | ACE-Step-ComfyUI | on the server | Commercial | Passed: local mode against an ACE-Step 1.5 server (acestep-openrouter, run from its own uv environment because it needs transformers<4.58); 10 s, 4 steps; the shipped file defaults to cloud mode (api.acemusic.ai key) |
| [ace-step-v1-audio-to-audio-editing](Music-Generation/ace-step-v1-audio-to-audio-editing.json) | Legacy ACE-Step v1 (3.5B): edit a song's style / lyrics audio-to-audio (official template) | [`ace_step_v1_3.5b.safetensors`](https://huggingface.co/Comfy-Org/ACE-Step_ComfyUI_repackaged/resolve/main/all_in_one/ace_step_v1_3.5b.safetensors) → `checkpoints` | core | ~10 GB | Commercial (Apache-2.0) | Passed: 10 steps on a 30 s clip |

#### YuE 2 and YuE v1 (lyrics + style to full song)

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence | Test |
|---|---|---|---|---|---|---|
| [yue2-lyrics-to-song](Music-Generation/yue2-lyrics-to-song.json) | Lyrics to Song (YuE 2) with SheetSage melody-to-ABC | `yue2_3b_bf16.safetensors`, `sheetsage2_bf16.safetensors` | — | ~12 GB | Non-commercial (CC BY-NC 4.0) | — (earlier library workflow, not part of this test) |
| [yue2-music-cover](Music-Generation/yue2-music-cover.json) | Cover: SheetSage2 transcribes a reference song to ABC, YuE 2 sings it in a new style (official template) | [`yue2_3b_int8_convrot.safetensors`](https://huggingface.co/Comfy-Org/YuE2/resolve/main/checkpoints/yue2_3b_int8_convrot.safetensors) → `checkpoints`, [`sheetsage2_bf16.safetensors`](https://huggingface.co/Comfy-Org/YuE2/resolve/main/audio_encoders/sheetsage2_bf16.safetensors) → `audio_encoders` | core | ~8 GB | Non-commercial | Passed: 20 s, 10 steps |
| [yue2-score-editor-to-song](Music-Generation/yue2-score-editor-to-song.json) | Write / edit the melody and chords in a score (ABC / piano-roll) editor, then render the song (by filliptm) | YuE 2 weights (auto-download, see pack README) | ComfyUI-FL-YuE2 | ~12 GB | Non-commercial | Passed: 20 s, 10 acoustic steps (pack auto-downloads 7.8 GB) |
| [yue2-lyrics-to-song-and-cover-smthemex](Music-Generation/yue2-lyrics-to-song-and-cover-smthemex.json) | Lyrics to song with optional reference audio for cover mode (by smthemex) | `m-a-p/YuE2-3B` → `diffusion_models`, `m-a-p/YuE2-Vae` → `vae`, `m-a-p/SheetSage2` + `m-a-p/MERT-v2-FullSong` → `clip` | ComfyUI_YuE | ~12 GB | Non-commercial | Fixed: author's file had only_plan on and a Windows abc_file path (reset); pack JS patched so the abc_file upload widget is sent (upstream it never is, so every UI run fails with 'Required input is missing'); 25 s render |
| [yue-v1-lyrics-to-song-legacy](Music-Generation/yue-v1-lyrics-to-song-legacy.json) | Legacy YuE v1 (7B stage 1 + 1B stage 2) lyrics to song. Current ComfyUI_YuE only supports YuE 2, so clone it a second time as `custom_nodes/ComfyUI_YuE_v1` and `git checkout d560498` (node names do not clash). Ships with the int8 stage 1 for 16 GB cards | stage 1 [Alissonerdx/YuE-s1-7B-anneal-en-cot-int8](https://huggingface.co/Alissonerdx/YuE-s1-7B-anneal-en-cot-int8), stage 2 [m-a-p/YuE-s2-1B-general](https://huggingface.co/m-a-p/YuE-s2-1B-general) (repo IDs auto-download, or local paths); `ckpt_00360000.pth` ([xcodec_mini_infer](https://huggingface.co/m-a-p/xcodec_mini_infer)) and `decoder_131000.pth` / `decoder_151000.pth` ([YuE-upsampler](https://huggingface.co/m-a-p/YuE-upsampler)) → `models/yue/`; `semantic_ckpts/hf_1_325000` → the pack's `inference/xcodec_mini_infer/` | ComfyUI_YuE @ d560498 | 24 GB fp16; 16 GB with int8 (slow: about 23 min for the shortest run) | Commercial (Apache-2.0) | Fixed: repo paths changed from the author's F: drive to HuggingFace repo IDs (int8 stage 1 for 16 GB), rescale fixed; pack @d560498 installed as ComfyUI_YuE_v1 and patched (sdpa instead of flash-attn, folder-name independent paths, soundfile fallback when TorchCodec is missing); 2 segments, 2944 tokens (node minimum), ~23 min on int8; the smoke output was noise-like |

#### HeartMuLa and MuLaCover

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence | Test |
|---|---|---|---|---|---|---|
| [heartmula-fl-text-to-song](Music-Generation/heartmula-fl-text-to-song.json) | Text to Song with HeartMuLa, tags builder and lyrics (workflow by filliptm) | HeartMuLa model weights (several GB), downloaded separately | ComfyUI_FL-HeartMuLa | ~16 GB | Commercial (Apache-2.0) | — (earlier library workflow, not part of this test) |
| [heartmula-lyrics-and-style-to-song](Music-Generation/heartmula-lyrics-and-style-to-song.json) | Lyrics and Style to full Song with HeartMuLa (workflow by benjiyaya) | HeartMuLa model weights (several GB), downloaded separately | HeartMuLa_ComfyUI | ~16 GB | Commercial (Apache-2.0) | — (earlier library workflow, not part of this test) |
| [heartmula-lyrics-transcriber](Music-Generation/heartmula-lyrics-transcriber.json) | Lyrics Transcriber: extract lyrics from a song with HeartMuLa (workflow by benjiyaya) | HeartMuLa model weights (several GB), downloaded separately | HeartMuLa_ComfyUI, ComfyUI-VideoHelperSuite, ComfyUI-Custom-Scripts | — | Commercial (Apache-2.0) | — (earlier library workflow, not part of this test) |
| [mulacover-audio-remix](Music-Generation/mulacover-audio-remix.json) | MuLaCover cover / remix of a reference song with a new style (by T8mars). Install only one of the two MuLaCover packs: both ship a Python package named `mulacover` and break each other | [HeartMuLa/MuLaCover](https://huggingface.co/HeartMuLa/MuLaCover) + HeartCodec-oss → `models/MuLaCover-T8/` | Comfyui-Mulacover-T8 | ~24 GB | Non-commercial (CC BY-NC 4.0) | Fixed: pack patched for transformers 5 (YourMT3 helpers, RoPE cache after meta init, codec initted buffers), restored vendored files its .gitignore dropped, uses installed torchtune (+torchao 0.13); widget values re-mapped; Save Audio node added; 15 s cover. Do not install together with comfyui_MuLaCover (both ship a 'mulacover' package) |
| [mulacover-cover-from-reference-or-midi](Music-Generation/mulacover-cover-from-reference-or-midi.json) | MuLaCover cover from reference audio or from a melody / chord MIDI file (by klossm). Do not install together with Comfyui-Mulacover-T8 | MuLaCover, HeartCodec-oss, Qwen3-Embedding-0.6B, YourMT3 transcriber (~10 GB, reference-audio mode only) → `models/MuLaCover/` | comfyui_MuLaCover | ~12 GB | Non-commercial | Fixed: pack patched for transformers 5 (YourMT3 helpers, RoPE cache after meta init, codec initted buffers); reference-audio mode, 15 s. Do not install together with Comfyui-Mulacover-T8 |

#### Tencent SongGeneration / LeVo / LeVo 2

The official repo is currently offline and the weight licence could not be verified; the report lists it as **non-commercial**. Treat it as non-commercial.

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence | Test |
|---|---|---|---|---|---|---|
| [songgeneration-levo-2-lyrics-to-song](Music-Generation/songgeneration-levo-2-lyrics-to-song.json) | Lyrics + description (+ optional audio prompt) to full song up to 4m30s, LeVo 2 / v1 and GGUF (by smthemex) | [`SongGeneration-v2-large-Q6_K.gguf`](https://huggingface.co/smthem/SongGeneration-v2-large-gguf) → `models/gguf/`; `new_auto_prompt.pt`, `new_prompt.pt`, `prompt.pt` (same repo), `model_2.safetensors`, `model_2_fixed.safetensors`, `htdemucs.pth`, `ckpt/encode-s12k.pt` from [lglg666/SongGeneration-Runtime](https://huggingface.co/lglg666/SongGeneration-Runtime) → `models/SongGeneration/`; `autoencoder_music_1320k.ckpt` (same repo) → `models/vae/`. The original tencent/SongGeneration repo was removed | ComfyUI_SongGeneration | 12 GB+ | Non-commercial | Fixed: pack patched for transformers 5 (flash-attn detection, rope_scaling format, removed helpers, GPT-2 config defaults, PreTrainedModel mask helpers) plus 'lightning'; flash attention off, save_separate fixed; v2-large Q6_K GGUF; runtime files from lglg666/SongGeneration-Runtime because tencent/SongGeneration was removed from HuggingFace; short 2-line song (~15 s) |
| [songgeneration-levo-style-transfer](Music-Generation/songgeneration-levo-style-transfer.json) | LeVo v1 lyrics to song with auto-style and style transfer from a reference clip, cropped with the core Audio Crop node (by filliptm) | auto-download → `models/songgen/`; copy `new_prompt.pt` to `models/songgen/ckpt/` for auto-style | ComfyUI_FL-SongGen | 10–28 GB by model size | Non-commercial | Fixed: FL_Audio_Crop (separate Fill-Nodes pack) replaced by core AudioCrop; memory_mode re-set to low; pack patched for transformers 5 (same SongGeneration code fixes plus MusicFM hidden states) and its Demucs download pointed at lglg666/SongGeneration-Runtime; 30 s renders (node minimum): plain generation and style transfer give music, the Auto Style branch renders near-silence on this setup (known issue) |
| [songgeneration-levo-2-easy-fp4](Music-Generation/songgeneration-levo-2-easy-fp4.json) | LeVo 2 large with fp4 quantisation and a lyrics / style formatter (by eastmoe) | `common/`, `third_party/` and `SongGeneration-v2-large/` from [eastmoe/SongGeneration](https://huggingface.co/eastmoe/SongGeneration) → `models/SongGeneration/` (or use the pack's download node) | ComfyUI-Easy-SongGeneration | ~10 GB | Non-commercial | Passed: v2-large fp4, 3 s smoke test (models from eastmoe/SongGeneration) |

#### DiffRhythm and DiffRhythm 2 (weights Apache-2.0, commercial)

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence | Test |
|---|---|---|---|---|---|---|
| [diffrhythm-lyrics-and-style-to-song](Music-Generation/diffrhythm-lyrics-and-style-to-song.json) | Timed LRC lyrics + style prompt to song, 95 s (base / v1.2) or 285 s (full); leave lyrics empty for instrumental (by billwuhao) | `cfm_model_v1_2.pt`, `cfm_full_model.pt`, DiffRhythm-vae, MuQ-MuLan-large, MuQ-large-msd-iter, xlm-roberta-base (see pack README) | ComfyUI_DiffRhythm | ~8 GB | Commercial | Fixed: pack patched (transformers>=4.54 decoder output unpacking, soundfile instead of torchcodec); widget list trimmed so the frontend loads values in the right slots; 95 s v1.2, 8 steps |
| [diffrhythm-reference-audio-style-to-song](Music-Generation/diffrhythm-reference-audio-style-to-song.json) | Song in the style of a reference audio clip | same | ComfyUI_DiffRhythm | ~8 GB | Commercial | Fixed: same pack patches plus muq library patch for transformers 5 (attn implementation, hidden states); 8 steps |
| [diffrhythm-edit-song-sections](Music-Generation/diffrhythm-edit-song-sections.json) | Edit / regenerate chosen sections of an existing song | same | ComfyUI_DiffRhythm | ~8 GB | Commercial | Fixed: same patches; edited 10-20 s of a 30 s clip, 8 steps |
| [diffrhythm-2-lyrics-and-style-to-song](Music-Generation/diffrhythm-2-lyrics-and-style-to-song.json) | DiffRhythm 2 block flow matching: section-tagged lyrics + style text (or a reference song) to song up to 3m30s. Built for this library from the pack's only node, which ships no example | [ASLP-lab/DiffRhythm2](https://huggingface.co/ASLP-lab/DiffRhythm2), MuQ-MuLan-large, xlm-roberta-base (auto-download → `models/TTS/DiffRhythm/`) | ComfyUI_DiffRhythm2 | ~10 GB | Commercial | Fixed: pack patched for transformers 5 (rope_theta) and py3langid pinned to 0.2.2; 20 s, 10 steps |

#### Stable Audio, MusicGen, AudioLDM 2 and others

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence | Test |
|---|---|---|---|---|---|---|
| [stable-audio-3-text-to-music](Music-Generation/stable-audio-3-text-to-music.json) | Text to Music | `t5gemma_b_b_ul2.safetensors`, `stable_audio_3_medium.safetensors` | ComfyUI-Pixaroma | ~12 GB | Community | — (earlier library workflow, not part of this test) |
| [stable-audio-3-medium-base-text-to-music](Music-Generation/stable-audio-3-medium-base-text-to-music.json) | Text to music / audio with the non-distilled SA3 Medium base model and a Qwen 3.5 prompt rewriter (official template). Swap the checkpoint to the Small-Music weights from the same repo for the small model | [`stable_audio_3_medium_base`](https://huggingface.co/Comfy-Org/stable-audio-3) → `checkpoints`, `t5gemma_b_b_ul2`, `qwen3.5_2b_bf16` → `text_encoders` | core | 12–16 GB | Community | Passed: 10 s, 12 steps |
| [stable-audio-3-image-to-music-gemma-4](Music-Generation/stable-audio-3-image-to-music-gemma-4.json) | Image to Music + Gemma 4 | `stable_audio_3_medium.safetensors`, `t5gemma_b_b_ul2.safetensors`, `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma | ~16 GB | Community | — (earlier library workflow, not part of this test) |
| [stable-audio-3-text-to-music-gemma-4-prompt-enhancer](Music-Generation/stable-audio-3-text-to-music-gemma-4-prompt-enhancer.json) | Text to Music + Gemma 4 Prompt Enhancer | `stable_audio_3_medium.safetensors`, `t5gemma_b_b_ul2.safetensors`, `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma | ~16 GB | Community | — (earlier library workflow, not part of this test) |
| [stable-audio-3-text-to-sound-effects-gemma-4](Music-Generation/stable-audio-3-text-to-sound-effects-gemma-4.json) | Text to Sound Effects + Gemma 4 | `stable_audio_3_medium.safetensors`, `t5gemma_b_b_ul2.safetensors`, `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma | ~16 GB | Community | — (earlier library workflow, not part of this test) |
| [stable-audio-open-1.0-text-to-audio](Music-Generation/stable-audio-open-1.0-text-to-audio.json) | Stable Audio Open 1.0 text to music / sound up to 47 s (official template) | [`stable-audio-open-1.0.safetensors`](https://huggingface.co/stabilityai/stable-audio-open-1.0) → `checkpoints`, `t5-base` → `text_encoders` | core | 6–8 GB | Community | Passed: 10 s, 15 steps |
| [musicgen-text-to-music-bpm-loop](Music-Generation/musicgen-text-to-music-bpm-loop.json) | MusicGen text to music with BPM / bar-length duration and looping preview (by ebrinz) | `facebook/musicgen-*` (auto-download from HuggingFace) | ComfyUI-MusicGen-HF | 4 / 8 / 16 GB (small / medium / large) | Non-commercial (CC BY-NC 4.0) | Fixed: removed the preview->generator feedback link that formed a dependency cycle; 8 s loop with musicgen-small |
| [audioldm2-image-to-music-llava](Music-Generation/audioldm2-image-to-music-llava.json) | LLaVA describes an image, AudioLDM 2 turns the description into music (by gokayfem). Uses the general `cvssp/audioldm2` checkpoint, not `audioldm2-music` | `cvssp/audioldm2` (auto-download); `ggml-mistral-7b-q_5_k.gguf` + `mmproj-mistral7b-f16.gguf` from [cmp-nct/llava-1.6-gguf](https://huggingface.co/cmp-nct/llava-1.6-gguf) → `models/LLavacheckpoints/` | ComfyUI_VLM_nodes | ~8 GB | Non-commercial (CC BY-NC-SA 4.0) | Fixed: LLaVA 1.6 Mistral GGUF + projector repointed to cmp-nct/llava-1.6-gguf (original repo removed), handler set to LLaVA 1.6, extension mp3->wav, Save Audio node added; pack patched for transformers 5 (GPT2 generation helper) and llama-cpp-python 0.3.40 (unsupported sampler keyword); 2 s, 10 steps |
| [minimax-music-3-text-to-music](Music-Generation/minimax-music-3-text-to-music.json) | Text to Music | `minimax_music3_dit_int8_convrot.safetensors`, `minimax_music3_text_encoder_pruned_int8_convrot.safetensors`, `minimax_music3_dav.safetensors` | ComfyUI-Pixaroma | — | see model card | — (earlier library workflow, not part of this test) |
| [foundation-1-text-to-music-loops](Music-Generation/foundation-1-text-to-music-loops.json) | Text to Music Loops and Samples (Foundation-1) that follow key, bar count and BPM (node pack by Saganaki22) | `Foundation_1.safetensors` (auto-downloaded by the node pack) | ComfyUI-Foundation-1 | — | see model card | — (earlier library workflow, not part of this test) |
| [woosh-text-and-video-to-sound-effects](Music-Generation/woosh-text-and-video-to-sound-effects.json) | Text to Sound Effects and Video to Sound Effects (Sony Woosh) | `Woosh-Flow`, `Woosh-VFlow-8s` | ComfyUI-Woosh, ComfyUI-VideoHelperSuite | — | see model card | — (earlier library workflow, not part of this test) |

### Music analysis

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence | Test |
|---|---|---|---|---|---|---|
| [ace-step-v1.5-understand-audio](Music-Analysis/ace-step-v1.5-understand-audio.json) | Understand a song: caption, lyrics, BPM, key, time signature, duration (reusable as a prompt) | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial | Fixed: same patches; caption, BPM, key and lyrics returned |

### Music transcription

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence | Test |
|---|---|---|---|---|---|---|
| [muscriptor-audio-to-midi-transcription](Music-Transcription/muscriptor-audio-to-midi-transcription.json) | Audio to MIDI multi-instrument transcription (MuScriptor by Kyutai and Mirelo; example workflow by martyyz-ai). The MuScriptor weights are gated on HuggingFace: accept the CC BY-NC 4.0 licence and log in to HuggingFace; they auto-download on first use | MuScriptor `large` (auto-downloaded by the node pack) | [ComfyUI-MuScriptor](https://github.com/martyyz-ai/ComfyUI-MuScriptor), ComfyUI-Custom-Scripts | — | Non-commercial | — (earlier library workflow, not part of this test) |
| [sheetsage2-audio-to-abc-melody-and-chords](Music-Transcription/sheetsage2-audio-to-abc-melody-and-chords.json) | SheetSage2: transcribe a song's melody (and melody + chords) to an ABC score; open it in an ABC editor to export MIDI. Built for this library from core nodes | [`sheetsage2_bf16.safetensors`](https://huggingface.co/Comfy-Org/YuE2/resolve/main/audio_encoders/sheetsage2_bf16.safetensors) → `audio_encoders` | core | ~4 GB | Non-commercial (CC BY-NC 4.0) | Passed: ABC for melody and full |

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

| Workflow | What it does | Models used | Custom nodes needed | VRAM | Licence | Test |
|---|---|---|---|---|---|---|
| [demucs-htdemucs-4-stem-separation](Stem-Separation/demucs-htdemucs-4-stem-separation.json) | Demucs v4 (HT Demucs) 4 stems: vocals, drums, bass, other (official Comfy-Org template) | `htdemucs` (auto-download to the torch hub cache) | ComfyUI_AudioTools | ~4 GB | Commercial (MIT) | Passed: 4 stems from a 30 s clip |
| [demucs-htdemucs-6s-six-stem-separation](Stem-Separation/demucs-htdemucs-6s-six-stem-separation.json) | Demucs v4 6 stems: vocals, drums, bass, other, guitar, piano, plus an instrumental mix. Built for this library from the pack's separator node | `htdemucs_6s` (auto-download to `models/demucs/`) | ComfyUI-Demucs-AudioSeparator | ~4 GB (cpu option) | Commercial (MIT) | Passed: 6 stems + instrumental |
| [demucs-mdx-audio-separator-stem-separation](Stem-Separation/demucs-mdx-audio-separator-stem-separation.json) | Demucs + MDX + Audio Separator stem extraction: vocals, instruments and percussion from any track (by ZETALVX) | — | audio-separation, audio-separation-nodes-comfyui | ~4 GB | Commercial (MIT) | — (earlier library workflow, not part of this test) |
| [ace-step-v1.5-extract-stems](Stem-Separation/ace-step-v1.5-extract-stems.json) | ACE-Step extraction: pull a single track (vocals, drums, bass…) out of a mix generatively | `Ace-Step1.5` | ComfyUI-kaola-ace-step | 6 GB+ | Commercial | Fixed: same patches; vocals from a 30 s clip, 20 steps |

## Included but not working on the test PC

| Workflow | What it does | Error on the test PC | Would need |
|---|---|---|---|
| [ace-step-v1.5-audio-captioner](Music-Analysis/ace-step-v1.5-audio-captioner.json) | Detailed music caption with the ACE-Step captioner (Qwen2.5-Omni-7B based, ComfyUI-kaola-ace-step) | `Qwen2_5OmniForConditionalGeneration.__init__() got an unexpected keyword argument 'code_revision'`: the pack loads the model through `transformers.pipeline()`, which fails on transformers 5 | transformers < 5 and about 24 GB VRAM (the bf16 model is 22 GB) |
| [ace-step-v1.5-lyrics-transcriber](Music-Transcription/ace-step-v1.5-lyrics-transcriber.json) | Sung-lyrics transcription with the ACE-Step transcriber (Qwen2.5-Omni-7B based, ComfyUI-kaola-ace-step) | same `code_revision` error | transformers < 5 and about 24 GB VRAM |

## Node-pack fixes for transformers 5

The fixes below were applied to the node packs on the test PC. Without them the listed workflows stop with the error shown. They are small compatibility shims; report them upstream or apply them by hand until the packs are updated.

| Pack | Error without the fix | Fix |
|---|---|---|
| ComfyUI-kaola-ace-step | `does not support Flash Attention 2`, then `Tensor.item() cannot be called on meta tensors`, then NaN latents; out of memory when two ACE nodes run in one graph | fall back flash_attention_2 → sdpa → eager; build the DiT on the CPU and load its safetensors instead of `from_pretrained` (transformers 5 always initialises on the meta device, leaving non-persistent buffers empty); create the FSQ `levels` tensor on the CPU in `vector_quantize_pytorch/residual_fsq.py`; let `ACE_STEP_ClearVRAM` free the handlers cached on every ACE node |
| ACE-Step-1.5 library (kaola submodule) | — | `pip install --no-deps -e acestep_repo` (its requirements pin torch 2.10 and transformers < 4.58) |
| ComfyUI_DiffRhythm | `The size of tensor a (32) must match ... (64)`, `TorchCodec is required`, `'EasyDict' object has no attribute '_attn_implementation'`, `KeyError: 'hidden_states'` | unpack the decoder-layer output as a tensor (transformers ≥ 4.54); read and write audio with soundfile; in the `muq` package set `_attn_implementation = "eager"` and collect the conformer hidden states with forward pre-hooks. The `eval-model` folder comes from the [DiffRhythm Space](https://huggingface.co/spaces/ASLP-lab/DiffRhythm/tree/main/pretrained) |
| ComfyUI_DiffRhythm2 | `'LlamaConfig' object has no attribute 'rope_theta'`, `LanguageIdentifier ... from_pickled_model` | read `rope_theta` from `rope_parameters`; `pip install py3langid==0.2.2`; soundfile instead of torchaudio.save |
| ComfyUI_SongGeneration, ComfyUI_FL-SongGen | `No module named 'flash_attn'`, `No module named 'lightning'`, `KeyError: 'type'`, imports of `find_pruneable_heads_and_indices`, `transformers.onnx`, `SequenceSummary`, `'GPT2Config' object has no attribute 'add_cross_attention'`, `'GPT2Model' object has no attribute 'get_head_mask'`, `KeyError: 'hidden_states'` | detect flash-attn by calling the helper; `pip install lightning`; accept the transformers 5 `rope_scaling` format; guard the removed imports (only used for pruning / ONNX export); restore the v4 config defaults and `get_head_mask` / attention-mask helpers; collect MusicFM hidden states with hooks; FL-SongGen downloads `htdemucs.pth` from lglg666/SongGeneration-Runtime |
| Comfyui-Mulacover-T8, comfyui_MuLaCover | missing `torchtune.models` / `mulacover._codec.models` (dropped by the repo's `models/` .gitignore), removed transformers helpers, `RoPE cache is not built`, `ignore_mismatched_sizes`, `weights_only` load of YourMT3 | use the installed torchtune (with `torchao==0.13.0`); restore `_codec/models` from [HeartMuLa/MuLaCover](https://github.com/HeartMuLa/MuLaCover); guard the removed helpers; call `rope_init()` after loading; load HeartCodec with `ignore_mismatched_sizes=True` and mark its codebooks initialised; allow the numpy 1.x pickle names. Both packs ship a package named `mulacover`: keep only one enabled |
| ComfyUI_YuE (current, YuE 2) | every UI run: `Required input is missing: abc_file` | `js/simple.js`: let the abc_file upload widget be serialized |
| ComfyUI_YuE @ d560498 (YuE v1) | `FlashAttention2 has been toggled on`, `Repo id must be in the form ...` (hard-coded `custom_nodes/ComfyUI_YuE` path), `TorchCodec is required` | use sdpa; resolve the tokenizer and semantic-model paths from the pack's own folder; fall back to soundfile when torchaudio has no TorchCodec |
| ComfyUI_VLM_nodes | `create_chat_completion() got an unexpected keyword argument 'presence_penalty'`, `'GPT2Model' object has no attribute '_update_model_kwargs_for_generation'` | pass only the keywords the installed llama-cpp-python accepts; add the v4 generation helper to the AudioLDM 2 language model |

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
