# Audio Music — ComfyUI workflows

Songs, instrumentals and general audio from text, lyrics or images; covers, remixing and section edits; music LoRAs; sound effects; singing voice; music captioning and transcription to MIDI / ABC / lyrics; stem separation.

[← 03-Audio overview](../README.md) · [Library index](../../00-LIBRARY-INDEX.md)

**80 workflows** in **25 model folders**. Each model folder holds only workflow files; the file name says the task first, then the variant: `<task>[-<variant>][-<size>][-<precision>][-<feature>].json`. `Other/` holds generic or multi-model workflows.

## Model folders

| Model | Workflows | Tasks |
|---|---|---|
| [ACE-Step-1](#ace-step-1) | 2 | `audio2audio`, `txt2music` |
| [ACE-Step-1.5](#ace-step-15) | 27 | `add-tracks`, `audio2audio`, `caption`, `caption-understand-audio`, `cover`, `extend-complete`, `lora-training`, `lyrics-transcribe`, `lyrics2song`, `repaint-section`, `stem-split`, `txt2music` |
| [AudioLDM2](#audioldm2) | 1 | `img2music` |
| [AudioX](#audiox) | 2 | `sound-effects`, `txt2music` |
| [Basic-Pitch](#basic-pitch) | 1 | `audio2midi` |
| [Demucs](#demucs) | 4 | `remix`, `stem-split` |
| [DiffRhythm](#diffrhythm) | 4 | `cover`, `lyrics2song`, `repaint-section` |
| [Foundation-1](#foundation-1) | 1 | `txt2music` |
| [HeartMuLa](#heartmula) | 4 | `lyrics-transcribe`, `lyrics2song`, `style-transfer` |
| [MiniMax-Music](#minimax-music) | 1 | `txt2music` |
| [MulaCover](#mulacover) | 2 | `cover`, `remix` |
| [MuScriptor](#muscriptor) | 1 | `audio2midi` |
| [Music-Flamingo](#music-flamingo) | 1 | `caption-song-analysis` |
| [MusicGen](#musicgen) | 1 | `txt2music` |
| [Pika](#pika) | 1 | `txt2music` |
| [RoFormer](#roformer) | 3 | `stem-split` |
| [SheetSage](#sheetsage) | 1 | `audio2abc` |
| [SongBloom](#songbloom) | 2 | `lyrics2song` |
| [SongGeneration](#songgeneration) | 3 | `lyrics2song`, `style-transfer` |
| [Sonilo](#sonilo) | 1 | `txt2music` |
| [SoulX-Singer](#soulx-singer) | 3 | `singing-voice` |
| [Stable-Audio](#stable-audio) | 6 | `img2music`, `sound-effects`, `txt2audio`, `txt2music` |
| [Woosh](#woosh) | 1 | `sound-effects` |
| [YuE](#yue) | 5 | `cover`, `lyrics2song` |
| [Other](#other) | 2 | `stem-split` |

## ACE-Step-1

Folder: [`ACE-Step-1/`](ACE-Step-1) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [audio2audio-editing](ACE-Step-1/audio2audio-editing.json) | Legacy ACE-Step v1 (3.5B): edit a song's style / lyrics audio-to-audio (official template) | [`ace_step_v1_3.5b.safetensors`](https://huggingface.co/Comfy-Org/ACE-Step_ComfyUI_repackaged/resolve/main/all_in_one/ace_step_v1_3.5b.safetensors) → `checkpoints` | core | VRAM: ~10 GB; Licence: Commercial (Apache-2.0); Test: Passed: 10 steps on a 30 s clip |
| [txt2music-instrumental](ACE-Step-1/txt2music-instrumental.json) | Legacy ACE-Step v1 (3.5B) instrumental text to music with core nodes only (official Comfy-Org template) | [`ace_step_v1_3.5b.safetensors`](https://huggingface.co/Comfy-Org/ACE-Step_ComfyUI_repackaged) → `models/checkpoints/` | core | VRAM: ~8–12 GB (estimate); Licence: Commercial (Apache-2.0); Test: not tested |

## ACE-Step-1.5

Folder: [`ACE-Step-1.5/`](ACE-Step-1.5) — 27 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [add-tracks-lego](ACE-Step-1.5/add-tracks-lego.json) | Lego: add a new instrument / vocal layer on top of an existing track | `Ace-Step1.5` | ComfyUI-kaola-ace-step | VRAM: 6 GB+; Licence: Commercial; Test: Fixed: same patches; base model, 20 steps |
| [audio2audio-xl-base](ACE-Step-1.5/audio2audio-xl-base.json) | Audio-to-audio with the XL base model: encodes a source song and re-generates it at denoise 0.6 (from captain's local ComfyUI, not re-tested) | `acestep_v1.5_xl_base_bf16`, text encoders, VAE | core | VRAM: ~20–24 GB; Licence: Commercial; Test: Not re-tested |
| [audio2audio-xl-turbo](ACE-Step-1.5/audio2audio-xl-turbo.json) | Audio-to-audio with the XL turbo model, 8 steps, MP3 output (from captain's local ComfyUI, not re-tested) | `acestep_v1.5_xl_turbo_bf16.safetensors`, `qwen_0.6b_ace15.safetensors`, `qwen_4b_ace15.safetensors`, `ace_1.5_vae.safetensors` | ComfyUI-Pixaroma | VRAM: ~20 GB; Licence: Commercial; Test: Not re-tested |
| [caption-understand-audio](ACE-Step-1.5/caption-understand-audio.json) | Understand a song: caption, lyrics, BPM, key, time signature, duration (reusable as a prompt) | `Ace-Step1.5` | ComfyUI-kaola-ace-step | VRAM: 6 GB+; Licence: Commercial; Test: Fixed: same patches; caption, BPM, key and lyrics returned |
| [caption](ACE-Step-1.5/caption.json) | Detailed music caption with the ACE-Step captioner (Qwen2.5-Omni-7B based, ComfyUI-kaola-ace-step) | ACE-Step captioner / transcriber (Qwen2.5-Omni-7B based) | ComfyUI-kaola-ace-step | VRAM: about 24 GB (bf16 model is 22 GB); Test: Not working on the test PC: `Qwen2_5OmniForConditionalGeneration.__init__() got an unexpected keyword argument 'code_revision'`: the pack loads the model through `transformers.pipeline()`, which fails on transformers 5; Error on the test PC: `Qwen2_5OmniForConditionalGeneration.__init__() got an unexpected keyword argument 'code_revision'`: the pack loads the model through `transformers.pipeline()`, which fails on transformers 5; Would need: transformers < 5 and about 24 GB VRAM (the bf16 model is 22 GB) |
| [cover-lora](ACE-Step-1.5/cover-lora.json) | Cover with a LoRA style | `Ace-Step1.5` + your LoRA | ComfyUI-kaola-ace-step | VRAM: 6 GB+; Licence: Commercial (check the LoRA); Test: Fixed: same patches; LoRA cover of a 30 s clip |
| [cover-xl-base-reference-timbre](ACE-Step-1.5/cover-xl-base-reference-timbre.json) | Cover with the XL base model, using a source song as reference timbre (from captain's local ComfyUI, not re-tested) | `acestep_v1.5_xl_base_bf16`, text encoders, VAE | core | VRAM: ~20–24 GB; Licence: Commercial; Test: Not re-tested |
| [cover](ACE-Step-1.5/cover.json) | Cover: re-perform a reference song in a new style, keeping its structure | `Ace-Step1.5` | ComfyUI-kaola-ace-step | VRAM: 6 GB+; Licence: Commercial; Test: Fixed: same patches; cover of a 30 s clip |
| [extend-complete](ACE-Step-1.5/extend-complete.json) | Completion: continue / extend a partial song | `Ace-Step1.5` | ComfyUI-kaola-ace-step | VRAM: 6 GB+; Licence: Commercial; Test: Fixed: same patches; base model, 20 steps (node minimum) |
| [lora-training](ACE-Step-1.5/lora-training.json) | LoRA Training (by ZETALVX) | `ace_step_1.5_turbo_aio.safetensors` | fl-acestep-training | VRAM: 16 GB+; Licence: Commercial; Test: — (earlier library workflow, not part of this test) |
| [lyrics-transcribe](ACE-Step-1.5/lyrics-transcribe.json) | Sung-lyrics transcription with the ACE-Step transcriber (Qwen2.5-Omni-7B based, ComfyUI-kaola-ace-step) | ACE-Step captioner / transcriber (Qwen2.5-Omni-7B based) | ComfyUI-kaola-ace-step | VRAM: about 24 GB (bf16 model is 22 GB); Test: Not working on the test PC: same `code_revision` error; Error on the test PC: same `code_revision` error; Would need: transformers < 5 and about 24 GB VRAM |
| [lyrics2song](ACE-Step-1.5/lyrics2song.json) | Caption + lyrics + BPM / key / time signature / duration to song | `Ace-Step1.5` | ComfyUI-kaola-ace-step | VRAM: 6 GB+; Licence: Commercial; Test: Fixed: kaola pack patched for transformers 5 (DiT built without meta init, FA2->sdpa fallback, vector-quantize cpu levels); widget values re-mapped to the current node inputs; 20 s turbo |
| [repaint-section](ACE-Step-1.5/repaint-section.json) | Repaint: regenerate a time range of an existing song | `Ace-Step1.5` | ComfyUI-kaola-ace-step | VRAM: 6 GB+; Licence: Commercial; Test: Fixed: same patches; repainted 0-5 s of a 30 s clip |
| [stem-split](ACE-Step-1.5/stem-split.json) | ACE-Step extraction: pull a single track (vocals, drums, bass…) out of a mix generatively | `Ace-Step1.5` | ComfyUI-kaola-ace-step | VRAM: 6 GB+; Licence: Commercial; Test: Fixed: same patches; vocals from a 30 s clip, 20 steps |
| [txt2music-create-sample](ACE-Step-1.5/txt2music-create-sample.json) | Language model creates caption, lyrics and metadata, then generates the song | `Ace-Step1.5` | ComfyUI-kaola-ace-step | VRAM: 6 GB+; Licence: Commercial; Test: Fixed: same patches; added ACE_STEP_ClearVRAM between the sample writer and the renderer (pack patched so ClearVRAM frees node handlers) to fit 16 GB |
| [txt2music-lora](ACE-Step-1.5/txt2music-lora.json) | Text to music with a trained ACE-Step LoRA | `Ace-Step1.5` + your LoRA | ComfyUI-kaola-ace-step | VRAM: 6 GB+; Licence: Commercial (check the LoRA); Test: Fixed: same patches; ACE-Step-v1.5-chinese-new-year-LoRA, 20 s |
| [txt2music-official-api-server](ACE-Step-1.5/txt2music-official-api-server.json) | Official ACE-Step node: text2music, cover / remix, repaint and reference audio via a running ACE-Step 1.5 API server. Ships in cloud mode (api.acemusic.ai key); for local mode run `acestep-openrouter --port 8002` from an [ACE-Step-1.5](https://github.com/ace-step/ACE-Step-1.5) checkout in its own environment (it needs transformers<4.58) and set mode = local | served by the ACE-Step 1.5 server | ACE-Step-ComfyUI | VRAM: on the server; Licence: Commercial; Test: Passed: local mode against an ACE-Step 1.5 server (acestep-openrouter, run from its own uv environment because it needs transformers<4.58); 10 s, 4 steps; the shipped file defaults to cloud mode (api.acemusic.ai key) |
| [txt2music-qwen3.5-local-prompt-writer](ACE-Step-1.5/txt2music-qwen3.5-local-prompt-writer.json) | A local LLM (Qwen 3.5 2B, ComfyUI core TextGenerate) writes style tags and lyrics from a one-line idea, then ACE-Step turbo renders the song. Built from the official Gemini-API template with the paid Gemini node replaced | turbo split files + [`qwen3.5_2b_bf16.safetensors`](https://huggingface.co/Comfy-Org/Qwen3.5/resolve/main/text_encoders/qwen3.5_2b_bf16.safetensors) (4.5 GB) → `text_encoders` | core | VRAM: ~10 GB (fits 16 GB; ComfyUI unloads the LLM before the render when needed); Licence: Commercial (ACE-Step MIT, Qwen 3.5 Apache-2.0); Test: Fixed: paid Gemini node replaced by local Qwen 3.5 2B TextGenerate (captain request); 20 s |
| [txt2music-sft-merge-lora](ACE-Step-1.5/txt2music-sft-merge-lora.json) | High-quality text to music with SFT / merged models and LoRA stacking (by jeankassio) | `acestep_v1.5_xl_sft_bf16`, `qwen_0.6b_ace15`, `qwen_4b_ace15`, `ace_1.5_vae` (core file names) + an ACE-Step LoRA in `models/loras/` | ComfyUI-AceStep_SFT | VRAM: 12 GB+; Licence: Commercial; Test: — (earlier library workflow, not part of this test) |
| [txt2music-simple-mode](ACE-Step-1.5/txt2music-simple-mode.json) | One-line description, the language model writes everything else | `Ace-Step1.5` | ComfyUI-kaola-ace-step | VRAM: 6 GB+; Licence: Commercial; Test: Fixed: same pack patches and widget re-map; turbo 8 steps |
| [txt2music-turbo-1.7b-lm](ACE-Step-1.5/txt2music-turbo-1.7b-lm.json) | Text + lyrics to song, split files with the 1.7B language model (official template) | `acestep_v1.5_turbo`, `qwen_0.6b_ace15`, `qwen_1.7b_ace15`, `ace_1.5_vae` | core | VRAM: ~8 GB; Licence: Commercial; Test: Passed: 20 s |
| [txt2music-turbo-4b-lm](ACE-Step-1.5/txt2music-turbo-4b-lm.json) | Same with the larger 4B language model for better lyric and structure following (official template) | `acestep_v1.5_turbo`, `qwen_0.6b_ace15`, `qwen_4b_ace15`, `ace_1.5_vae` | core | VRAM: ~12 GB; Licence: Commercial; Test: Passed: 20 s |
| [txt2music-turbo-all-in-one](ACE-Step-1.5/txt2music-turbo-all-in-one.json) | Text + lyrics to song, single all-in-one checkpoint (official Comfy-Org template) | `ace_step_1.5_turbo_aio.safetensors` | core | VRAM: ~8 GB; Licence: Commercial; Test: Passed: 30 s render in 5 s |
| [txt2music-xl-base-minimal](ACE-Step-1.5/txt2music-xl-base-minimal.json) | Minimal core-node XL base text-to-music, 30 s, 50 steps (from captain's local ComfyUI, not re-tested) | `acestep_v1.5_xl_base_bf16`, text encoders, VAE | core | VRAM: ~20–24 GB; Licence: Commercial; Test: Not re-tested |
| [txt2music-xl-base](ACE-Step-1.5/txt2music-xl-base.json) | XL base model, highest quality, more steps (official template) | `acestep_v1.5_xl_base_bf16`, text encoders, VAE | core | VRAM: ~20–24 GB; Licence: Commercial; Test: Passed: 20 s, 12 steps |
| [txt2music-xl-sft](ACE-Step-1.5/txt2music-xl-sft.json) | XL SFT model (official template) | `acestep_v1.5_xl_sft_bf16`, text encoders, VAE | core | VRAM: ~20–24 GB; Licence: Commercial; Test: Passed: 20 s, 12 steps |
| [txt2music-xl-turbo](ACE-Step-1.5/txt2music-xl-turbo.json) | Text to Music | `qwen_0.6b_ace15.safetensors`, `qwen_4b_ace15.safetensors`, `ace_1.5_vae.safetensors` +1 more | ComfyUI-Pixaroma | VRAM: ~20 GB; Licence: Commercial; Test: — (earlier library workflow, not part of this test) |

## AudioLDM2

Folder: [`AudioLDM2/`](AudioLDM2) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2music-llava](AudioLDM2/img2music-llava.json) | LLaVA describes an image, AudioLDM 2 turns the description into music (by gokayfem). Uses the general `cvssp/audioldm2` checkpoint, not `audioldm2-music` | `cvssp/audioldm2` (auto-download); `ggml-mistral-7b-q_5_k.gguf` + `mmproj-mistral7b-f16.gguf` from [cmp-nct/llava-1.6-gguf](https://huggingface.co/cmp-nct/llava-1.6-gguf) → `models/LLavacheckpoints/` | ComfyUI_VLM_nodes | VRAM: ~8 GB; Licence: Non-commercial (CC BY-NC-SA 4.0); Test: Fixed: LLaVA 1.6 Mistral GGUF + projector repointed to cmp-nct/llava-1.6-gguf (original repo removed), handler set to LLaVA 1.6, extension mp3->wav, Save Audio node added; pack patched for transformers 5 (GPT2 generation helper) and llama-cpp-python 0.3.40 (unsupported sampler keyword); 2 s, 10 steps |

## AudioX

Folder: [`AudioX/`](AudioX) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [sound-effects-video-and-image-to-audio](AudioX/sound-effects-video-and-image-to-audio.json) | AudioX: score or sound a video or a set of images (background music / foley) | [`HKUSTAudio/AudioX-MAF`](https://huggingface.co/HKUSTAudio/AudioX-MAF) → `models/AudioX/` | ComfyUI-AudioX, ComfyUI-VideoHelperSuite | VRAM: not stated; Licence: Non-commercial (check the model card); Test: not tested |
| [txt2music-and-audio](AudioX/txt2music-and-audio.json) | AudioX unified model: text to music and text to sound, with a prompt helper | [`HKUSTAudio/AudioX`](https://huggingface.co/HKUSTAudio/AudioX) `model.ckpt` + `config.json` → `models/diffusion_models/` | ComfyUI-StableAudioX, rgthree-comfy | VRAM: 16 GB+ (pack README); Licence: AudioX is CC-BY-NC per the report: non-commercial; Test: not tested |

## Basic-Pitch

Folder: [`Basic-Pitch/`](Basic-Pitch) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [audio2midi-stem-split](Basic-Pitch/audio2midi-stem-split.json) | Split a song into stems (Roformer / Demucs 6-stem / drum pieces) and transcribe the stems to MIDI with Spotify Basic Pitch | audio-separator models and Basic Pitch (download on first use) | One Solo Studios stem tools (ArtisticMusician/ComfyUI-Custom-Nodes) | VRAM: not stated; Licence: Basic Pitch Apache-2.0; check each separator checkpoint; Test: not tested |

## Demucs

Folder: [`Demucs/`](Demucs) — 4 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [remix-stems-tempo-match](Demucs/remix-stems-tempo-match.json) | Demucs 4-stem separation, tempo matching and remix, with an extra Stable-Audio-style generation chain (christian-byrne example) | torchaudio Hybrid Demucs (auto-download) + a Stable Audio checkpoint | audio-separation-nodes-comfyui | VRAM: not stated; Licence: check the models; Test: not tested |
| [stem-split-htdemucs-4-stem](Demucs/stem-split-htdemucs-4-stem.json) | Demucs v4 (HT Demucs) 4 stems: vocals, drums, bass, other (official Comfy-Org template) | `htdemucs` (auto-download to the torch hub cache) | ComfyUI_AudioTools | VRAM: ~4 GB; Licence: Commercial (MIT); Test: Passed: 4 stems from a 30 s clip |
| [stem-split-htdemucs-6s-six-stem](Demucs/stem-split-htdemucs-6s-six-stem.json) | Demucs v4 6 stems: vocals, drums, bass, other, guitar, piano, plus an instrumental mix. Built for this library from the pack's separator node | `htdemucs_6s` (auto-download to `models/demucs/`) | ComfyUI-Demucs-AudioSeparator | VRAM: ~4 GB (cpu option); Licence: Commercial (MIT); Test: Passed: 6 stems + instrumental |
| [stem-split-mdx-audio-separator](Demucs/stem-split-mdx-audio-separator.json) | Demucs + MDX + Audio Separator stem extraction: vocals, instruments and percussion from any track (by ZETALVX) | — | audio-separation, audio-separation-nodes-comfyui | VRAM: ~4 GB; Licence: Commercial (MIT); Test: — (earlier library workflow, not part of this test) |

## DiffRhythm

Folder: [`DiffRhythm/`](DiffRhythm) — 4 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [cover-reference-audio-style-to-song](DiffRhythm/cover-reference-audio-style-to-song.json) | Song in the style of a reference audio clip | same | ComfyUI_DiffRhythm | VRAM: ~8 GB; Licence: Commercial; Test: Fixed: same pack patches plus muq library patch for transformers 5 (attn implementation, hidden states); 8 steps |
| [lyrics2song-style](DiffRhythm/lyrics2song-style.json) | Timed LRC lyrics + style prompt to song, 95 s (base / v1.2) or 285 s (full); leave lyrics empty for instrumental (by billwuhao) | `cfm_model_v1_2.pt`, `cfm_full_model.pt`, DiffRhythm-vae, MuQ-MuLan-large, MuQ-large-msd-iter, xlm-roberta-base (see pack README) | ComfyUI_DiffRhythm | VRAM: ~8 GB; Licence: Commercial; Test: Fixed: pack patched (transformers>=4.54 decoder output unpacking, soundfile instead of torchcodec); widget list trimmed so the frontend loads values in the right slots; 95 s v1.2, 8 steps |
| [lyrics2song-v2-style](DiffRhythm/lyrics2song-v2-style.json) | DiffRhythm 2 block flow matching: section-tagged lyrics + style text (or a reference song) to song up to 3m30s. Built for this library from the pack's only node, which ships no example | [ASLP-lab/DiffRhythm2](https://huggingface.co/ASLP-lab/DiffRhythm2), MuQ-MuLan-large, xlm-roberta-base (auto-download → `models/TTS/DiffRhythm/`) | ComfyUI_DiffRhythm2 | VRAM: ~10 GB; Licence: Commercial; Test: Fixed: pack patched for transformers 5 (rope_theta) and py3langid pinned to 0.2.2; 20 s, 10 steps |
| [repaint-section-edit-song-sections](DiffRhythm/repaint-section-edit-song-sections.json) | Edit / regenerate chosen sections of an existing song | same | ComfyUI_DiffRhythm | VRAM: ~8 GB; Licence: Commercial; Test: Fixed: same patches; edited 10-20 s of a 30 s clip, 8 steps |

## Foundation-1

Folder: [`Foundation-1/`](Foundation-1) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2music-loops](Foundation-1/txt2music-loops.json) | Text to Music Loops and Samples (Foundation-1) that follow key, bar count and BPM (node pack by Saganaki22) | `Foundation_1.safetensors` (auto-downloaded by the node pack) | ComfyUI-Foundation-1 | Licence: see model card; Test: — (earlier library workflow, not part of this test) |

## HeartMuLa

Folder: [`HeartMuLa/`](HeartMuLa) — 4 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [lyrics-transcribe](HeartMuLa/lyrics-transcribe.json) | Lyrics Transcriber: extract lyrics from a song with HeartMuLa (workflow by benjiyaya) | HeartMuLa model weights (several GB), downloaded separately | HeartMuLa_ComfyUI, ComfyUI-VideoHelperSuite, ComfyUI-Custom-Scripts | Licence: Commercial (Apache-2.0); Test: — (earlier library workflow, not part of this test) |
| [lyrics2song-fl](HeartMuLa/lyrics2song-fl.json) | Text to Song with HeartMuLa, tags builder and lyrics (workflow by filliptm) | HeartMuLa model weights (several GB), downloaded separately | ComfyUI_FL-HeartMuLa | VRAM: ~16 GB; Licence: Commercial (Apache-2.0); Test: — (earlier library workflow, not part of this test) |
| [lyrics2song-style](HeartMuLa/lyrics2song-style.json) | Lyrics and Style to full Song with HeartMuLa (workflow by benjiyaya) | HeartMuLa model weights (several GB), downloaded separately | HeartMuLa_ComfyUI | VRAM: ~16 GB; Licence: Commercial (Apache-2.0); Test: — (earlier library workflow, not part of this test) |
| [style-transfer-muq-mulan](HeartMuLa/style-transfer-muq-mulan.json) | HeartMuLa song generation conditioned on a MuQ-MuLan style embedding from a reference clip (experimental) | HeartMuLa-oss-3B + HeartCodec-oss → `models/HeartMuLa/`; [OpenMuQ/MuQ-MuLan-large](https://huggingface.co/OpenMuQ/MuQ-MuLan-large) (auto-download) | ComfyUI-JK-HeartMuLa | VRAM: not stated; Licence: Non-commercial (MuQ-MuLan is CC BY-NC 4.0); Test: not tested |

## MiniMax-Music

Folder: [`MiniMax-Music/`](MiniMax-Music) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2music-v3](MiniMax-Music/txt2music-v3.json) | Text to Music | `minimax_music3_dit_int8_convrot.safetensors`, `minimax_music3_text_encoder_pruned_int8_convrot.safetensors`, `minimax_music3_dav.safetensors` | ComfyUI-Pixaroma | Licence: see model card; Test: — (earlier library workflow, not part of this test) |

## MulaCover

Folder: [`MulaCover/`](MulaCover) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [cover-from-reference-or-midi](MulaCover/cover-from-reference-or-midi.json) | MuLaCover cover from reference audio or from a melody / chord MIDI file (by klossm). Do not install together with Comfyui-Mulacover-T8 | MuLaCover, HeartCodec-oss, Qwen3-Embedding-0.6B, YourMT3 transcriber (~10 GB, reference-audio mode only) → `models/MuLaCover/` | comfyui_MuLaCover | VRAM: ~12 GB; Licence: Non-commercial; Test: Fixed: pack patched for transformers 5 (YourMT3 helpers, RoPE cache after meta init, codec initted buffers); reference-audio mode, 15 s. Do not install together with Comfyui-Mulacover-T8 |
| [remix](MulaCover/remix.json) | MuLaCover cover / remix of a reference song with a new style (by T8mars). Install only one of the two MuLaCover packs: both ship a Python package named `mulacover` and break each other | [HeartMuLa/MuLaCover](https://huggingface.co/HeartMuLa/MuLaCover) + HeartCodec-oss → `models/MuLaCover-T8/` | Comfyui-Mulacover-T8 | VRAM: ~24 GB; Licence: Non-commercial (CC BY-NC 4.0); Test: Fixed: pack patched for transformers 5 (YourMT3 helpers, RoPE cache after meta init, codec initted buffers), restored vendored files its .gitignore dropped, uses installed torchtune (+torchao 0.13); widget values re-mapped; Save Audio node added; 15 s cover. Do not install together with comfyui_MuLaCover (both ship a 'mulacover' package) |

## MuScriptor

Folder: [`MuScriptor/`](MuScriptor) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [audio2midi](MuScriptor/audio2midi.json) | Audio to MIDI multi-instrument transcription (MuScriptor by Kyutai and Mirelo; example workflow by martyyz-ai). The MuScriptor weights are gated on HuggingFace: accept the CC BY-NC 4.0 licence and log in to HuggingFace; they auto-download on first use | MuScriptor `large` (auto-downloaded by the node pack) | [ComfyUI-MuScriptor](https://github.com/martyyz-ai/ComfyUI-MuScriptor), ComfyUI-Custom-Scripts | Licence: Non-commercial; Test: — (earlier library workflow, not part of this test) |

## Music-Flamingo

Folder: [`Music-Flamingo/`](Music-Flamingo) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [caption-song-analysis](Music-Flamingo/caption-song-analysis.json) | NVIDIA Music Flamingo audio-language model: describe a song (genre, key, tempo, structure, lyric themes) | [`nvidia/music-flamingo-hf`](https://huggingface.co/nvidia/music-flamingo-hf) (pre-quantised variants in `models/checkpoints/musicflamingo/`) | comfyui-musicflamingo, rgthree-comfy | VRAM: ~15 GB fp16, ~8 GB 8-bit, ~4.5 GB 4-bit; Licence: NVIDIA licence ("other" on Hugging Face): verify before commercial use; Test: not tested |

## MusicGen

Folder: [`MusicGen/`](MusicGen) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2music-bpm-loop](MusicGen/txt2music-bpm-loop.json) | MusicGen text to music with BPM / bar-length duration and looping preview (by ebrinz) | `facebook/musicgen-*` (auto-download from HuggingFace) | ComfyUI-MusicGen-HF | VRAM: 4 / 8 / 16 GB (small / medium / large); Licence: Non-commercial (CC BY-NC 4.0); Test: Fixed: removed the preview->generator feedback link that formed a dependency cycle; 8 s loop with musicgen-small |

## Pika

Folder: [`Pika/`](Pika) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2music-api](Pika/txt2music-api.json) | Pika text to music through the Comfy API node (paid credits, Comfy account, no local model) | none (cloud) | core API nodes | VRAM: none; Licence: Service terms; Test: not tested |

## RoFormer

Folder: [`RoFormer/`](RoFormer) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [stem-split-bs-vocal-mel-denoise](RoFormer/stem-split-bs-vocal-mel-denoise.json) | BS-RoFormer (Viperx 1297) vocal split followed by a Mel-RoFormer denoise pass | `BS-Roformer-Viperx-1297`, `Mel-Roformer-Denoise-Aufr33` (auto-download through audio-separator) | One Solo Studios stem tools | VRAM: not stated; Licence: Mixed community checkpoints: check each; Test: not tested |
| [stem-split-ensemble-vocals-instrumental-uvr-cleanup](RoFormer/stem-split-ensemble-vocals-instrumental-uvr-cleanup.json) | Vocal / instrumental split with an ensemble of splitters and UVR cleanup | audio-separator models (auto-download) | One Solo Studios stem tools | VRAM: not stated; Licence: Mixed community checkpoints; Test: not tested |
| [stem-split-melband-vocals-instrumental](RoFormer/stem-split-melband-vocals-instrumental.json) | Mel-Band RoFormer vocals / instrumental split (Kijai's example workflow) | [`MelBandRoformer_fp16.safetensors`](https://huggingface.co/Kijai/MelBandRoFormer_comfy) → `models/diffusion_models/MelRoFormer/` | ComfyUI-MelBandRoFormer | VRAM: not stated; Licence: Check the model card (derived from a community vocal model); pack licence not declared; Test: not tested |

## SheetSage

Folder: [`SheetSage/`](SheetSage) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [audio2abc-v2-melody-and-chords](SheetSage/audio2abc-v2-melody-and-chords.json) | SheetSage2: transcribe a song's melody (and melody + chords) to an ABC score; open it in an ABC editor to export MIDI. Built for this library from core nodes | [`sheetsage2_bf16.safetensors`](https://huggingface.co/Comfy-Org/YuE2/resolve/main/audio_encoders/sheetsage2_bf16.safetensors) → `audio_encoders` | core | VRAM: ~4 GB; Licence: Non-commercial (CC BY-NC 4.0); Test: Passed: ABC for melody and full |

## SongBloom

Folder: [`SongBloom/`](SongBloom) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [lyrics2song-audio-prompt](SongBloom/lyrics2song-audio-prompt.json) | SongBloom: lyrics + a short style audio prompt to a full song up to 150 s, with lyric processor and optional DeepSeek lyric formatter (needs your own DeepSeek API key; the field is empty) | `songbloom_full_150s_dpo` from [fredconex/SongBloom-safetensors](https://huggingface.co/fredconex/SongBloom-safetensors) → `models/checkpoints/` | SongBloom_ComfyUI (xuchenxu168), ComfyUI-Easy-Use | VRAM: not stated (likely 12 GB+); Licence: Check the [SongBloom model card](https://github.com/tencent-ailab/SongBloom); pack Apache-2.0; Test: not tested |
| [lyrics2song-fredconex-style-150s](SongBloom/lyrics2song-fredconex-style-150s.json) | SongBloom full-length song (150 s model) from lyrics and a 10 s audio prompt, with fade / trim helpers | `songbloom_full_150s.safetensors` (or the `_dpo` file) from [fredconex/SongBloom-safetensors](https://huggingface.co/fredconex/SongBloom-safetensors) → `models/checkpoints/` | ComfyUI-SongBloom (rakib91221) + the SoundFlow fade / trim nodes | VRAM: not stated; Licence: Check the SongBloom model card; pack has no licence; Test: not tested |

## SongGeneration

Folder: [`SongGeneration/`](SongGeneration) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [lyrics2song-levo-2-easy-fp4](SongGeneration/lyrics2song-levo-2-easy-fp4.json) | LeVo 2 large with fp4 quantisation and a lyrics / style formatter (by eastmoe) | `common/`, `third_party/` and `SongGeneration-v2-large/` from [eastmoe/SongGeneration](https://huggingface.co/eastmoe/SongGeneration) → `models/SongGeneration/` (or use the pack's download node) | ComfyUI-Easy-SongGeneration | VRAM: ~10 GB; Licence: Non-commercial; Test: Passed: v2-large fp4, 3 s smoke test (models from eastmoe/SongGeneration) |
| [lyrics2song-levo-2](SongGeneration/lyrics2song-levo-2.json) | Lyrics + description (+ optional audio prompt) to full song up to 4m30s, LeVo 2 / v1 and GGUF (by smthemex) | [`SongGeneration-v2-large-Q6_K.gguf`](https://huggingface.co/smthem/SongGeneration-v2-large-gguf) → `models/gguf/`; `new_auto_prompt.pt`, `new_prompt.pt`, `prompt.pt` (same repo), `model_2.safetensors`, `model_2_fixed.safetensors`, `htdemucs.pth`, `ckpt/encode-s12k.pt` from [lglg666/SongGeneration-Runtime](https://huggingface.co/lglg666/SongGeneration-Runtime) → `models/SongGeneration/`; `autoencoder_music_1320k.ckpt` (same repo) → `models/vae/`. The original tencent/SongGeneration repo was removed | ComfyUI_SongGeneration | VRAM: 12 GB+; Licence: Non-commercial; Test: Fixed: pack patched for transformers 5 (flash-attn detection, rope_scaling format, removed helpers, GPT-2 config defaults, PreTrainedModel mask helpers) plus 'lightning'; flash attention off, save_separate fixed; v2-large Q6_K GGUF; runtime files from lglg666/SongGeneration-Runtime because tencent/SongGeneration was removed from HuggingFace; short 2-line song (~15 s) |
| [style-transfer-levo](SongGeneration/style-transfer-levo.json) | LeVo v1 lyrics to song with auto-style and style transfer from a reference clip, cropped with the core Audio Crop node (by filliptm) | auto-download → `models/songgen/`; copy `new_prompt.pt` to `models/songgen/ckpt/` for auto-style | ComfyUI_FL-SongGen | VRAM: 10–28 GB by model size; Licence: Non-commercial; Test: Fixed: FL_Audio_Crop (separate Fill-Nodes pack) replaced by core AudioCrop; memory_mode re-set to low; pack patched for transformers 5 (same SongGeneration code fixes plus MusicFM hidden states) and its Demucs download pointed at lglg666/SongGeneration-Runtime; 30 s renders (node minimum): plain generation and style transfer give music, the Auto Style branch renders near-silence on this setup (known issue) |

## Sonilo

Folder: [`Sonilo/`](Sonilo) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [txt2music-v1.5-api](Sonilo/txt2music-v1.5-api.json) | Sonilo Music 1.5 through the Comfy API node (paid credits, no local model) | none (cloud) | core API nodes | VRAM: none; Licence: Service terms; Test: not tested |

## SoulX-Singer

Folder: [`SoulX-Singer/`](SoulX-Singer) — 3 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [singing-voice-preprocess-and-generate-kaola](SoulX-Singer/singing-voice-preprocess-and-generate-kaola.json) | SoulX-Singer with an explicit preprocessing step (prompt and target metadata extraction) before generation | SoulX-Singer + SoulX-Singer-Preprocess → `models/soulx-singer/` and `models/soulx-singer/SoulX-Singer-Preprocess/` | ComfyUI-kaola-soulX-Singer (needs NumPy 2.x, may conflict with other packs) | VRAM: not stated; Licence: Model Apache-2.0; pack has no licence; Test: not tested |
| [singing-voice-vocal-to-midi-lyric-edit-resing](SoulX-Singer/singing-voice-vocal-to-midi-lyric-edit-resing.json) | Transcribe a sung vocal to MIDI, replace the lyrics or correct the pitch, and re-sing it with SoulX-Singer. A large graph (80 nodes) with many third-party nodes; several are not verified, see the pack table | SoulX-Singer (~2.6 GB), SoulX-Singer-Preprocess (~7 GB) and ct-transformer-punc → `models/` | ComfyUI-MIDI-Edit plus its helper packs | VRAM: not stated; Licence: Model Apache-2.0; pack MIT; Test: not tested |
| [singing-voice-zero-shot](SoulX-Singer/singing-voice-zero-shot.json) | SoulX-Singer zero-shot singing voice synthesis and conversion: sing a target melody and lyrics in the timbre of a reference vocal, simple and advanced nodes (example workflow by Saganaki22) | [Soul-AILab/SoulX-Singer](https://huggingface.co/Soul-AILab/SoulX-Singer) + [SoulX-Singer-Preprocess](https://huggingface.co/Soul-AILab/SoulX-Singer-Preprocess) (auto-download, ~6 GB bf16) → `models/SoulX-Singer/` | ComfyUI-SoulX-Singer | VRAM: not stated; Licence: Commercial (Apache-2.0 model and pack); Test: not tested |

## Stable-Audio

Folder: [`Stable-Audio/`](Stable-Audio) — 6 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [img2music-v3-gemma-4](Stable-Audio/img2music-v3-gemma-4.json) | Image to Music + Gemma 4 | `stable_audio_3_medium.safetensors`, `t5gemma_b_b_ul2.safetensors`, `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma | VRAM: ~16 GB; Licence: Community; Test: — (earlier library workflow, not part of this test) |
| [sound-effects-v3-txt2audio-gemma-4](Stable-Audio/sound-effects-v3-txt2audio-gemma-4.json) | Text to Sound Effects + Gemma 4 | `stable_audio_3_medium.safetensors`, `t5gemma_b_b_ul2.safetensors`, `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma | VRAM: ~16 GB; Licence: Community; Test: — (earlier library workflow, not part of this test) |
| [txt2audio-open-1.0](Stable-Audio/txt2audio-open-1.0.json) | Stable Audio Open 1.0 text to music / sound up to 47 s (official template) | [`stable-audio-open-1.0.safetensors`](https://huggingface.co/stabilityai/stable-audio-open-1.0) → `checkpoints`, `t5-base` → `text_encoders` | core | VRAM: 6–8 GB; Licence: Community; Test: Passed: 10 s, 15 steps |
| [txt2music-v3-gemma-4-prompt-enhancer](Stable-Audio/txt2music-v3-gemma-4-prompt-enhancer.json) | Text to Music + Gemma 4 Prompt Enhancer | `stable_audio_3_medium.safetensors`, `t5gemma_b_b_ul2.safetensors`, `gemma4_e4b_it_fp8_scaled.safetensors` | ComfyUI-Pixaroma | VRAM: ~16 GB; Licence: Community; Test: — (earlier library workflow, not part of this test) |
| [txt2music-v3-medium-base](Stable-Audio/txt2music-v3-medium-base.json) | Text to music / audio with the non-distilled SA3 Medium base model and a Qwen 3.5 prompt rewriter (official template). Swap the checkpoint to the Small-Music weights from the same repo for the small model | [`stable_audio_3_medium_base`](https://huggingface.co/Comfy-Org/stable-audio-3) → `checkpoints`, `t5gemma_b_b_ul2`, `qwen3.5_2b_bf16` → `text_encoders` | core | VRAM: 12–16 GB; Licence: Community; Test: Passed: 10 s, 12 steps |
| [txt2music-v3](Stable-Audio/txt2music-v3.json) | Text to Music | `t5gemma_b_b_ul2.safetensors`, `stable_audio_3_medium.safetensors` | ComfyUI-Pixaroma | VRAM: ~12 GB; Licence: Community; Test: — (earlier library workflow, not part of this test) |

## Woosh

Folder: [`Woosh/`](Woosh) — 1 workflow

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [sound-effects-text-and-video](Woosh/sound-effects-text-and-video.json) | Text to Sound Effects and Video to Sound Effects (Sony Woosh) | `Woosh-Flow`, `Woosh-VFlow-8s` | ComfyUI-Woosh, ComfyUI-VideoHelperSuite | Licence: see model card; Test: — (earlier library workflow, not part of this test) |

## YuE

Folder: [`YuE/`](YuE) — 5 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [cover-v2](YuE/cover-v2.json) | Cover: SheetSage2 transcribes a reference song to ABC, YuE 2 sings it in a new style (official template) | [`yue2_3b_int8_convrot.safetensors`](https://huggingface.co/Comfy-Org/YuE2/resolve/main/checkpoints/yue2_3b_int8_convrot.safetensors) → `checkpoints`, [`sheetsage2_bf16.safetensors`](https://huggingface.co/Comfy-Org/YuE2/resolve/main/audio_encoders/sheetsage2_bf16.safetensors) → `audio_encoders` | core | VRAM: ~8 GB; Licence: Non-commercial; Test: Passed: 20 s, 10 steps |
| [lyrics2song-v1-legacy](YuE/lyrics2song-v1-legacy.json) | Legacy YuE v1 (7B stage 1 + 1B stage 2) lyrics to song. Current ComfyUI_YuE only supports YuE 2, so clone it a second time as `custom_nodes/ComfyUI_YuE_v1` and `git checkout d560498` (node names do not clash). Ships with the int8 stage 1 for 16 GB cards | stage 1 [Alissonerdx/YuE-s1-7B-anneal-en-cot-int8](https://huggingface.co/Alissonerdx/YuE-s1-7B-anneal-en-cot-int8), stage 2 [m-a-p/YuE-s2-1B-general](https://huggingface.co/m-a-p/YuE-s2-1B-general) (repo IDs auto-download, or local paths); `ckpt_00360000.pth` ([xcodec_mini_infer](https://huggingface.co/m-a-p/xcodec_mini_infer)) and `decoder_131000.pth` / `decoder_151000.pth` ([YuE-upsampler](https://huggingface.co/m-a-p/YuE-upsampler)) → `models/yue/`; `semantic_ckpts/hf_1_325000` → the pack's `inference/xcodec_mini_infer/` | ComfyUI_YuE @ d560498 | VRAM: 24 GB fp16; 16 GB with int8 (slow: about 23 min for the shortest run); Licence: Commercial (Apache-2.0); Test: Fixed: repo paths changed from the author's F: drive to HuggingFace repo IDs (int8 stage 1 for 16 GB), rescale fixed; pack @d560498 installed as ComfyUI_YuE_v1 and patched (sdpa instead of flash-attn, folder-name independent paths, soundfile fallback when TorchCodec is missing); 2 segments, 2944 tokens (node minimum), ~23 min on int8; the smoke output was noise-like |
| [lyrics2song-v2-and-cover-smthemex](YuE/lyrics2song-v2-and-cover-smthemex.json) | Lyrics to song with optional reference audio for cover mode (by smthemex) | `m-a-p/YuE2-3B` → `diffusion_models`, `m-a-p/YuE2-Vae` → `vae`, `m-a-p/SheetSage2` + `m-a-p/MERT-v2-FullSong` → `clip` | ComfyUI_YuE | VRAM: ~12 GB; Licence: Non-commercial; Test: Fixed: author's file had only_plan on and a Windows abc_file path (reset); pack JS patched so the abc_file upload widget is sent (upstream it never is, so every UI run fails with 'Required input is missing'); 25 s render |
| [lyrics2song-v2-score-editor](YuE/lyrics2song-v2-score-editor.json) | Write / edit the melody and chords in a score (ABC / piano-roll) editor, then render the song (by filliptm) | YuE 2 weights (auto-download, see pack README) | ComfyUI-FL-YuE2 | VRAM: ~12 GB; Licence: Non-commercial; Test: Passed: 20 s, 10 acoustic steps (pack auto-downloads 7.8 GB) |
| [lyrics2song-v2](YuE/lyrics2song-v2.json) | Lyrics to Song (YuE 2) with SheetSage melody-to-ABC | `yue2_3b_bf16.safetensors`, `sheetsage2_bf16.safetensors` | — | VRAM: ~12 GB; Licence: Non-commercial (CC BY-NC 4.0); Test: — (earlier library workflow, not part of this test) |

## Other

Folder: [`Other/`](Other) — 2 workflows

| Workflow | What it does | Models used | Custom nodes | Notes |
|---|---|---|---|---|
| [stem-split-chain-drum-pieces-and-sam-audio](Other/stem-split-chain-drum-pieces-and-sam-audio.json) | Chained separation: stems, then drum pieces (kick / snare / toms / hats, MDX23C DrumSep) and text-prompted extraction with SAM-Audio | audio-separator models, SAM-Audio small (likely gated on Hugging Face) | One Solo Studios stem tools | VRAM: not stated; Licence: Mixed; check each; Test: not tested |
| [stem-split-ensemble-recipes-roformer-mdx-demucs-6s](Other/stem-split-ensemble-recipes-roformer-mdx-demucs-6s.json) | Ensemble recipes that combine Roformer, MDX and Demucs 6-stem models for cleaner stems | audio-separator models (auto-download) | One Solo Studios stem tools | VRAM: not stated; Licence: Mixed community checkpoints; Test: not tested |

## Notes carried over from the previous folder layout

Setup notes, licences, test results and "not available in ComfyUI" lists from the former task-folder READMEs. Links point to the new locations.

### From the former "Music" README

Full-song and instrumental music generation (ACE-Step 1.5 / XL and v1, YuE 2 and YuE v1, HeartMuLa, MuLaCover, Tencent SongGeneration / LeVo 2, DiffRhythm and DiffRhythm 2, SongBloom, Stable Audio 3, Stable Audio Open, MusicGen, AudioLDM 2, AudioX, MiniMax Music 3, Foundation-1 and the Pika and Sonilo API nodes); covers, remixing and editing; music LoRA training; sound effects (Sony Woosh, Stable Audio 3, AudioX); singing-voice synthesis (SoulX-Singer); music analysis (ACE-Step, Music Flamingo); transcription to MIDI, ABC and lyrics (MuScriptor, SheetSage2, Basic Pitch, ACE-Step, HeartMuLa) and stem separation (Demucs v4, Mel-Band / BS-RoFormer, MDX, ensembles).

**New in the November 2026 music-model update:** 19 workflows added from the open-source music model encyclopedia (19 November 2026 snapshot). They are published example workflows (or official Comfy-Org templates) saved unmodified; they were only checked as loadable ComfyUI JSON (every link resolves, every custom node type confirmed in the named pack) and are marked **not tested**. Several still contain the author's demo audio / video file names in Load nodes; replace them with your own files.

**Test column:** every music workflow added in November 2026 was queued through the ComfyUI API on one PC (RTX 5060 Ti 16 GB, 32 GB RAM, Linux, ComfyUI 0.43, frontend 1.57, PyTorch 2.11 + CUDA 13, transformers 5.22) with short, low-step renders, and the output files were checked for real audio. **Passed** = ran unchanged. **Fixed** = needed a change to the workflow file (already applied here) and/or to the node pack (see [Node-pack fixes for transformers 5](#node-pack-fixes-for-transformers-5)). Most packs were written for transformers 4; on a ComfyUI that already uses transformers 5 they fail until patched.

Licence column: **Commercial** = weights may be used commercially, **Non-commercial** = research / personal use only, **Community** = Stability AI Community License (free commercial use under USD 1M annual revenue, Enterprise licence above that). Always confirm on the model card before releasing music. VRAM figures are the node authors' numbers or rough estimates, not measurements.

The Test column keeps the original wording: "— (earlier library workflow, not part of this test)" means the workflow pre-dates the November 2026 test run and has no recorded result; "not tested" means it was only checked as loadable JSON.

#### Setup notes by model family

**ACE-Step 1.5 and 1.5 XL** (weights MIT, commercial; 10–600 s, lyrics, instrumentals, BPM / key / time-signature metadata). Core-node models from [Comfy-Org/ace_step_1.5_ComfyUI_files](https://huggingface.co/Comfy-Org/ace_step_1.5_ComfyUI_files): `acestep_v1.5_turbo.safetensors`, `acestep_v1.5_xl_base_bf16.safetensors`, `acestep_v1.5_xl_sft_bf16.safetensors` → `models/diffusion_models/`; `qwen_0.6b_ace15.safetensors` + one of `qwen_1.7b_ace15` / `qwen_4b_ace15` → `models/text_encoders/`; `ace_1.5_vae.safetensors` → `models/vae/`; all-in-one `ace_step_1.5_turbo_aio.safetensors` → `models/checkpoints/`. The kaola workflows use the original weights: `hf download ACE-Step/Ace-Step1.5 --local-dir ComfyUI/models/Ace-Step1.5`.

**Tencent SongGeneration / LeVo / LeVo 2.** The official repo is currently offline and the weight licence could not be verified; the report lists it as **non-commercial**. Treat it as non-commercial.

**DiffRhythm and DiffRhythm 2:** weights Apache-2.0, commercial.

**Singing voice synthesis.** Music-only vocal synthesis (melody / lyrics to a sung vocal), kept apart from the text-to-speech workflows below. Consent for the voice you clone still applies.

##### Custom node packs used in this folder

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
| ComfyUI-SongBloom (rakib91221) | [github.com/rakib91221/ComfyUI-SongBloom](https://github.com/rakib91221/ComfyUI-SongBloom) (no licence declared; its workflow also uses `SoundFlow_*` fade / trim nodes from a separate SoundFlow pack that could not be verified) |
| SongBloom_ComfyUI (xuchenxu168) | [github.com/xuchenxu168/SongBloom_ComfyUI](https://github.com/xuchenxu168/SongBloom_ComfyUI) (Apache-2.0; also needs ComfyUI-Easy-Use) |
| ComfyUI-AudioX (aiimagestudio) | [github.com/aiimagestudio/ComfyUI-AudioX](https://github.com/aiimagestudio/ComfyUI-AudioX) (MIT; needs ComfyUI-VideoHelperSuite) |
| ComfyUI-StableAudioX (lum3on) | [github.com/lum3on/ComfyUI-StableAudioX](https://github.com/lum3on/ComfyUI-StableAudioX) (licence not declared; needs rgthree-comfy) |
| ComfyUI-JK-HeartMuLa | [github.com/Crono141/ComfyUI-JK-HeartMuLa](https://github.com/Crono141/ComfyUI-JK-HeartMuLa) (Apache-2.0) |
| comfyui-musicflamingo | [github.com/C0untFloyd/comfyui-musicflamingo](https://github.com/C0untFloyd/comfyui-musicflamingo) (MIT; needs rgthree-comfy) |
| ComfyUI-SoulX-Singer | [github.com/Saganaki22/ComfyUI-SoulX-Singer](https://github.com/Saganaki22/ComfyUI-SoulX-Singer) (Apache-2.0) |
| ComfyUI-kaola-soulX-Singer | [github.com/kana112233/ComfyUI-kaola-soulX-Singer](https://github.com/kana112233/ComfyUI-kaola-soulX-Singer) (no licence declared; needs NumPy 2.x) |
| ComfyUI-MIDI-Edit | [github.com/ahkimkoo/ComfyUI-MIDI-Edit](https://github.com/ahkimkoo/ComfyUI-MIDI-Edit) (MIT; the workflow also uses rgthree-comfy, ComfyUI-Easy-Use, ComfyUI-KJNodes, a MelBandRoFormer pack, an audio-utility pack and an LLM pack that were not individually verified) |
| audio-separation-nodes-comfyui | [github.com/christian-byrne/audio-separation-nodes-comfyui](https://github.com/christian-byrne/audio-separation-nodes-comfyui) (MIT) |
| ComfyUI-MelBandRoFormer | [github.com/kijai/ComfyUI-MelBandRoFormer](https://github.com/kijai/ComfyUI-MelBandRoFormer) (licence not declared) |
| ComfyUI-Custom-Nodes ("One Solo Studios" stem tools) | [github.com/ArtisticMusician/ComfyUI-Custom-Nodes](https://github.com/ArtisticMusician/ComfyUI-Custom-Nodes) (MIT; `pip install audio-separator basic-pitch`; model weights download on first use) |

#### Node-pack fixes for transformers 5

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

#### Music models not yet available in ComfyUI

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
| InspireMusic / InspireSong | Text-to-music and song generation (FunAudioLLM) | A node pack exists ([ComfyUI-InspireMusic](https://github.com/fq393/ComfyUI-InspireMusic), one text-to-music node) but ships no example workflow, so none is included | [github.com/FunAudioLLM/InspireMusic](https://github.com/FunAudioLLM/InspireMusic) |
| Muse, SegTune, JAM, Shao (Khala), VersBand, LaDA-Band, FastSAG | Newer open full-song and vocal-to-accompaniment research models | No ComfyUI node pack found | see the source index of the music-model report |
| AURA, AFTER, Instruct-MusicGen, MusiConGen, MelodyFlow, MG2 | Conversational / real-time / controlled music editing | No ComfyUI node pack found | see the source index of the music-model report |
| Magenta RealTime 2 | Real-time live music generation | Needs a streaming runtime bridge; no ComfyUI node found | [github.com/magenta](https://github.com/magenta) |
| VampNet, Musika, Jukebox, Dance Diffusion, Moûsai, RAVE, DDSP, GANSynth, NSynth | Masked-token, neural-synthesis and legacy audio models | No audio ComfyUI pack found (the ComfyUI-RAVE pack is a video model; ComfyUI-DDSP-SVC is voice conversion) | [github.com/magenta/ddsp](https://github.com/magenta/ddsp) |
| DiffSinger, YingMusic-Singer / Plus, NNSVS, TCSinger, StyleSinger, VISinger2 and other SVS research models | Singing voice synthesis | No ComfyUI node pack found (only SoulX-Singer is covered above) | [github.com/openvpi/DiffSinger](https://github.com/openvpi/DiffSinger) |
| NotaGen, ChatMusician, Music Transformer, MusicVAE, Composer's Assistant 2 and other symbolic models | ABC / MIDI composition | No ComfyUI node pack found; MIDI rendering exists only inside video-effects packs | [github.com/ElectricAlexis/NotaGen](https://github.com/ElectricAlexis/NotaGen) |
| MT3, Onsets & Frames, piano_transcription_inference, Omnizart | Multi-instrument and piano transcription | No ComfyUI node pack found (Basic Pitch is covered above through the stem-and-MIDI workflow; a standalone [ComfyUI-basic-pitch](https://github.com/DoctorDiffusion/ComfyUI-basic-pitch) pack exists without a workflow) | [github.com/magenta/mt3](https://github.com/magenta/mt3) |
| CREPE, SPICE, BeatNet, madmom, GAME (singing to MIDI) | Pitch, beat and singing-note estimation | No ComfyUI node pack found with a workflow (a ComfyUI_SOME sing-to-MIDI pack was seen but not verified) | [github.com/openvpi/GAME](https://github.com/openvpi/GAME) |
| MOSS-Music Instruct / Thinking, CLaMP 2 / 3, GaMMA, MU-LLaMA, MusiLingo, HeartCLAP | Music understanding, captioning and retrieval | No ComfyUI node pack found (Music Flamingo and the ACE-Step analyzers are covered above) | [github.com/OpenMOSS](https://github.com/OpenMOSS) |
| SCNet, Spleeter, Open-Unmix, BandIt | Source separation | No dedicated ComfyUI pack found | [github.com/starrytong/SCNet](https://github.com/starrytong/SCNet) |

See the [03-Audio overview](../README.md) for the other categories, the [main README](../../README.md) for setup, or [`00-LIBRARY-INDEX.md`](../../00-LIBRARY-INDEX.md) for the full list.
