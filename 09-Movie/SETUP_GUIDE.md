# Short Film Director Pipeline (Krea + MiniMax H3) — Full Setup Guide

**Product:** Short Film Director Pipeline (Krea + MiniMax H3)  
**Brand:** The AI Brief  
**Workflow file:** `Short Film Director Pipeline (Krea + MiniMax H3).json`  
**Price:** Free ($0)

This guide installs **every custom node**, downloads **every model / LoRA**, and walks you through generating a **multi-panel storyboard** then an **unlimited-length MiniMax H3 film** with locked character identity.

---

## What this workflow does (plain English)

1. Load a **character reference sheet** (multi-view photo of one person).
2. Write / upload **multiple storyboard panels** in **Krea Multi-Shot Stills (V2)** (3×3 or 4×4).
3. **Scene Board Compose (Grid)** stamps them into one labeled board image.
4. Toggle to the **MiniMax H3** branch — feed **character sheet + scene board** as scheduled `@tags`.
5. The **Contex Loop** chain generates scene-by-scene video with review / retry / assemble — **add as many scenes as you want**.

```
Character sheet
      ↓
Krea Multi-Shot Stills (V2)  →  panels 1…N
      ↓
Scene Board Compose (Grid)   →  labeled 3×3 / 4×4 board
      ↓
MiniMax H3 Scheduled Ref2VA + Contex Loop  →  short film (unlimited scenes)
```

Use the **PIPELINE SWITCH** (rgthree Fast Groups Bypasser) at the top: only **one** branch runs at a time — **KREA** *or* **H3**.

---

## 0) System requirements

| Item | Recommendation |
|------|----------------|
| ComfyUI | Recent build with native **Krea 2** + **MiniMax H3** support |
| GPU VRAM | **16 GB+** for comfort (RTX 4070 Ti / 5070 Ti class). Stills alone OK on 12 GB |
| Disk | ~100 GB+ for the full model stack |
| OS | Windows / Linux with CUDA PyTorch |
| Extra | `ffmpeg` on PATH recommended for Contex Loop review / assemble |

**Tip:** First run **KREA only** (bypass H3). When the board looks good, switch to **H3**.

---

## 1) Custom nodes (install ALL of these)

ComfyUI → **Manager** → **Install via Git URL** → paste each link → **Restart ComfyUI**.

| # | Pack | Why you need it | Install link |
|---|------|-----------------|--------------|
| 1 | **ComfyUI-Krea-MultiShot-Stills** | `KreaMultiShotStillsV2` + `SceneBoardCompose` (this pack) | https://github.com/CodingWithShahzaib/ComfyUI-Krea-MultiShot-Stills |
| 2 | **comfyui-krea2edit** | `Krea2EditModelPatch`, `Krea2EditGroundedEncode` | https://github.com/lbouaraba/comfyui-krea2edit |
| 3 | **ComfyUI-MiniMaxH3-Contex-Loop** | Plan, Scene Prompt Editor, Loop Start/End, Review, Assemble, Scheduled Refs | https://github.com/ethanfel/ComfyUI-MiniMaxH3-Contex-Loop |
| 4 | **rgthree-comfy** | `Fast Groups Bypasser` (Krea ↔ H3 toggle) | https://github.com/rgthree/rgthree-comfy |
| 5 | **ComfyUI-KJNodes** | `ModelPreviewOverrideKJ`, helpers | https://github.com/kijai/ComfyUI-KJNodes |

### Manual git install

```bash
cd ComfyUI/custom_nodes
git clone https://github.com/CodingWithShahzaib/ComfyUI-Krea-MultiShot-Stills
git clone https://github.com/lbouaraba/comfyui-krea2edit
git clone https://github.com/ethanfel/ComfyUI-MiniMaxH3-Contex-Loop
git clone https://github.com/rgthree/rgthree-comfy
git clone https://github.com/kijai/ComfyUI-KJNodes
```

Restart ComfyUI. Confirm these nodes appear in search:

- `Krea Multi-Shot Stills (V2)`
- `Scene Board Compose (Grid)`
- `MiniMaxH3ChainPlan` / `MiniMaxH3ChainScenePromptEditor`
- `MiniMaxH3ScheduledReferenceToVideo`
- `Fast Groups Bypasser (rgthree)`

Wiki for Contex Loop: https://github.com/ethanfel/ComfyUI-MiniMaxH3-Contex-Loop/wiki/Getting-Started

---

## 2) Models checklist (exact filenames + download links)

Paths are relative to your ComfyUI `models/` folder. Create subfolders if missing.

### A) Krea 2 — storyboard stills (required for KREA branch)

| File | Folder | Download |
|------|--------|----------|
| `krea2_turbo_fp8_scaled.safetensors` | `models/diffusion_models/` | https://huggingface.co/Comfy-Org/Krea-2/resolve/main/diffusion_models/krea2_turbo_fp8_scaled.safetensors |
| `qwen3vl_4b_fp8_scaled.safetensors` | `models/text_encoders/` | https://huggingface.co/Comfy-Org/Krea-2/resolve/main/text_encoders/qwen3vl_4b_fp8_scaled.safetensors |
| `qwen_image_vae.safetensors` | `models/vae/` | https://huggingface.co/Comfy-Org/Krea-2/resolve/main/vae/qwen_image_vae.safetensors |

**CLIP loader:** `type = krea2`  
Krea pack: https://huggingface.co/Comfy-Org/Krea-2

### B) Krea LoRAs

| File | Strength | Role | Download |
|------|----------|------|----------|
| `Krea2/krea2_identity_edit_v1_2.safetensors` | **1.0** | Face / identity lock (**required**) | https://huggingface.co/conradlocke/krea2-identity-edit/resolve/main/krea2_identity_edit_v1_2.safetensors |

Optional realism LoRA (not required by this graph):  
https://huggingface.co/RudySen/Krea2-realism-V2/resolve/main/Krea2-realism-V2.safetensors

**Identity patch node:** `ref_boost = 4`, `fit` mode (as shipped).

### C) MiniMax H3 — video chain (required for H3 branch)

Comfy-Org pack hub: https://huggingface.co/Comfy-Org/MiniMax-H3  
Official weights: https://huggingface.co/MiniMaxAI/MiniMax-H3

| File (as in this workflow) | Folder | Notes / Download |
|----------------------------|--------|------------------|
| `minimax_h3_fl2va_pruned_int8_convrot.safetensors` | `models/diffusion_models/` | H3 Ref2VA / FL2VA UNET — browse Comfy-Org MiniMax-H3 |
| `MiniMax/qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors` | `models/text_encoders/` | H3 text encoder (`type = minimax`) |
| `Minimax/minimax_h3_video_vae_fp16.safetensors` | `models/vae/` | Video VAE |
| `Minimax/minimax_h3_audio_vae_fp32.safetensors` | `models/vae/` | Audio VAE |
| `minimax_h3_fl2v_turbo_4step_v0.1.safetensors` | `models/loras/` | Turbo LoRA @ **0.95** (optional; lower for quality) |
| `taeh3.safetensors` | `models/vae_approx/` (or KJNodes path) | Preview override helper |

If your filenames differ slightly after a ComfyUI update, re-select them in the loaders — keep the **same roles** (UNET / CLIP type minimax / video VAE / audio VAE).

Design hub: https://design.minimax.io/h3  
H3 docs: https://huggingface.co/MiniMaxAI/MiniMax-H3/tree/main/docs

---

## 3) Sample assets in this pack

Copy into `ComfyUI/input/`:

| File | Use |
|------|-----|
| `sample_assets/shortfilm_character_sheet.jpg` | Character reference (Load Image + `@hero_face`) |
| `sample_assets/example_scene_board_4x4.jpg` | Example labeled board for H3 `@storyboard` |
| `sample_assets/example_scene_board_3x3.png` | Example 3×3 horror board from this pipeline |
| `sample_assets/panels/shortfilm_board_1.png` … `_8.png` | Example still panels |

The shipped workflow Load Image nodes expect:

- `shortfilm_character_sheet.jpg`
- `example_scene_board_4x4.jpg`

---

## 4) Open the workflow

1. ComfyUI → **Load** → `Short Film Director Pipeline (Krea + MiniMax H3).json`
2. Fix any red nodes (missing packs / models).
3. Top-left: **PIPELINE SWITCH** — click **SWITCH KREA Storyboard Pipeline** *or* **SWITCH H3 Video Pipeline** (always one).

### Groups

| Group | Purpose |
|-------|---------|
| **CONTROL** | README + pipeline switch |
| **SWITCH KREA Storyboard Pipeline** | Character → Multi-Shot V2 → Grid → Preview |
| **SWITCH H3 Video Pipeline** | H3 models + scheduled refs + Contex Loop chain |
| **RECOVERY (optional)** | Assemble without re-rendering (muted by default) |

---

## 5) Node-by-node reference

### KREA branch

| Node | Role |
|------|------|
| **Character Reference Sheet** (`LoadImage`) | Multi-view sheet into identity encode |
| **Krea 2 Turbo FP8** (`UNETLoader`) | Krea diffusion model |
| **Identity Edit LoRA** | Locks face across panels |
| **AuraFlow shift 1.15** | Sampling shift for Krea |
| **Qwen3-VL 4B (krea2)** | Text encoder (`type=krea2`) |
| **Qwen Image VAE** | Encode / decode stills |
| **Encode character** / **Identity patch** | Grounded encode + `ref_boost` |
| **Panel latent** | Empty latent (e.g. 768×432) |
| **Krea Multi-Shot Stills (V2)** | Dynamic panels: add / upload / queue / regenerate |
| **Scene Board Compose (Grid)** | Builds labeled A1…D4 board |
| **Preview board** | Visual check before H3 |

**Multi-Shot V2 tips**

- **Upload image** / **Browse & fill** — drop your own stills without generating.
- 9 panels → auto 3×3 grid UI; 16 panels → 4×4.
- `filename_prefix`: e.g. `shortfilm_board` → `input/shortfilm_board_1.png` …
- `overwrite=false` keeps existing files; `regenerate_shot=N` fixes one panel.

### H3 branch

| Node | Role |
|------|------|
| **H3 REF2VA MODEL** | MiniMax H3 UNET |
| **H3 TEXT ENCODER** | CLIP type `minimax` |
| **H3 Video / Audio VAE** | Decode video + audio |
| **MiniMaxH3SigmaShift** | Sigma schedule helper |
| **Turbo LoRA** | Faster sampling (optional) |
| **H3 @hero_face** | Scheduled picture ref → character sheet |
| **H3 @storyboard** | Scheduled picture ref → 4×4 board |
| **H3 CHAIN PLAN** | Scene list, durations, seeds |
| **Scene Prompt Editor** | Edit prompts / click `@` tags |
| **Loop Start → Current → Scheduled Ref2VA → Sample → Decode → Trim → Save → Review → Loop End** | One scene at a time |
| **Final Assemble** | Concatenate approved scenes |

**Scheduled refs:** keep stable `@hero_face` / `@storyboard` tags in prompts. The scheduler maps them to native Picture slots per scene — do not hard-code `<Picture 1>` numbers.

---

## 6) Prompting the 4×4 storyboard

Use this Google Doc for detailed **4×4 grid generation** prompt structure:

https://docs.google.com/document/d/1UR7yanfEs7s6pg_Ip52TiDGvU4jvlUk-iwMMTYK4PwY/edit?usp=sharing

Rules of thumb:

- One **scene per panel** — no “grid of images” wording inside a panel prompt.
- Repeat **same character + locked outfit** in every panel.
- Keep camera / action / lighting specific.
- Prefer 16:9 panel latent (e.g. 768×432).

---

## 7) Recommended first run

1. Copy sample assets into `ComfyUI/input/`.
2. Enable **SWITCH KREA** only.
3. Open Multi-Shot V2 — confirm panels / upload your own.
4. Queue → wait for stills → check **Scene Board Compose** preview.
5. Switch to **SWITCH H3**.
6. Confirm `@hero_face` and `@storyboard` Load Images point at sheet + board.
7. Open **Chain Plan** — set a unique `run_name`, edit scene prompts.
8. Queue → use **Review Gate** (approve / edit+retry / reroll).
9. **Final Assemble** when scenes are done.

---

## 8) Troubleshooting

| Problem | Fix |
|---------|-----|
| Red Multi-Shot / Scene Board nodes | Install https://github.com/CodingWithShahzaib/ComfyUI-Krea-MultiShot-Stills and restart |
| `comfyui-krea2edit is required` | Install https://github.com/lbouaraba/comfyui-krea2edit |
| Red MiniMaxH3Chain* nodes | Install / update https://github.com/ethanfel/ComfyUI-MiniMaxH3-Contex-Loop |
| Face drifts across panels | Identity LoRA @ 1.0; `ref_boost` 4; repeat identity line in every prompt |
| Clothes change | Lock the same outfit line in every panel prompt |
| Both Krea + H3 trying to run | Use PIPELINE SWITCH — only one group active |
| OOM on H3 | Use int8 UNET, enable EasyCache, lower resolution / fewer concurrent candidates |
| Missing board file | Run Krea branch first or copy `example_scene_board_4x4.jpg` to `input/` |

---

## 9) Important links (bookmark these)

| Resource | URL |
|----------|-----|
| This Multi-Shot + Grid pack | https://github.com/CodingWithShahzaib/ComfyUI-Krea-MultiShot-Stills |
| MiniMax H3 Contex Loop | https://github.com/ethanfel/ComfyUI-MiniMaxH3-Contex-Loop |
| 4×4 storyboard prompt doc | https://docs.google.com/document/d/1UR7yanfEs7s6pg_Ip52TiDGvU4jvlUk-iwMMTYK4PwY/edit?usp=sharing |
| Krea 2 models | https://huggingface.co/Comfy-Org/Krea-2 |
| MiniMax H3 (Comfy-Org) | https://huggingface.co/Comfy-Org/MiniMax-H3 |
| Identity Edit LoRA | https://huggingface.co/conradlocke/krea2-identity-edit |
| YouTube — The AI Brief | https://www.youtube.com/@TheAIBriefYT20 |

---

## License / credit

- Workflow packaging & Multi-Shot / Scene Board nodes: **The AI Brief** (MIT for the MultiShot pack — see GitHub LICENSE).
- Contex Loop: **ethanfel** — GPL-3.0 (see upstream repo).
- Krea2Edit: **Conrad Locke** / lbouaraba.
- Models remain under their Hugging Face licenses — **this product does not ship multi‑GB weights**.

Issues with the Multi-Shot pack: https://github.com/CodingWithShahzaib/ComfyUI-Krea-MultiShot-Stills/issues
