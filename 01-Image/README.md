# Image — ComfyUI workflows

All image workflows in the library: **453 workflows** in four categories. Each category README lists every workflow with what it does, the models it loads, the custom nodes it needs and, for the Open-Source Image Model Atlas additions (Nov 2026), the original source, model download link and licence. The atlas additions were checked to be valid ComfyUI workflow JSON for their model and task; they have **not** been runtime-tested.

## Folders

| Category | Subfolder | Workflows |
|---|---|---|
| [Image-Generation](Image-Generation/README.md) | | 202 |
| | [ControlNet-Guided](Image-Generation/ControlNet-Guided) | 15 |
| | [Design-Typography-and-Transparent](Image-Generation/Design-Typography-and-Transparent) | 16 |
| | [Edit-Inpaint-and-Reference](Image-Generation/Edit-Inpaint-and-Reference) | 34 |
| | [LLM-Prompt-Assisted](Image-Generation/LLM-Prompt-Assisted) | 29 |
| | [Prompt-Batching-and-Variations](Image-Generation/Prompt-Batching-and-Variations) | 17 |
| | [Text-to-Image](Image-Generation/Text-to-Image) | 91 |
| [Image-Editing](Image-Editing/README.md) | | 176 |
| | [Background-Removal](Image-Editing/Background-Removal) | 5 |
| | [Character-Outfit-and-Pose](Image-Editing/Character-Outfit-and-Pose) | 12 |
| | [Compositing-and-Image-Tools](Image-Editing/Compositing-and-Image-Tools) | 15 |
| | [ControlNet-and-Adapters](Image-Editing/ControlNet-and-Adapters) | 9 |
| | [Inpaint-Outpaint-and-Object-Removal](Image-Editing/Inpaint-Outpaint-and-Object-Removal) | 28 |
| | [Multi-Image-Composition](Image-Editing/Multi-Image-Composition) | 27 |
| | [Reference-and-Identity](Image-Editing/Reference-and-Identity) | 25 |
| | [Relighting](Image-Editing/Relighting) | 5 |
| | [Single-Image-Edit](Image-Editing/Single-Image-Edit) | 41 |
| | [Sketch-and-3D-to-Image](Image-Editing/Sketch-and-3D-to-Image) | 9 |
| [Image-Enhancement](Image-Enhancement/README.md) | | 44 |
| | [Colorization](Image-Enhancement/Colorization) | 1 |
| | [Denoise-Deblur-and-Low-Light](Image-Enhancement/Denoise-Deblur-and-Low-Light) | 4 |
| | [Diffusion-Restoration](Image-Enhancement/Diffusion-Restoration) | 9 |
| | [Face-Restoration](Image-Enhancement/Face-Restoration) | 3 |
| | [Filters-and-Color-Grading](Image-Enhancement/Filters-and-Color-Grading) | 2 |
| | [Upscaling](Image-Enhancement/Upscaling) | 25 |
| [Image-Specialized-and-Supporting](Image-Specialized-and-Supporting/README.md) | | 31 |
| | [Background-Removal](Image-Specialized-and-Supporting/Background-Removal) | 1 |
| | [Captioning-OCR-and-Tagging](Image-Specialized-and-Supporting/Captioning-OCR-and-Tagging) | 5 |
| | [Depth-Estimation](Image-Specialized-and-Supporting/Depth-Estimation) | 7 |
| | [Pose-Estimation](Image-Specialized-and-Supporting/Pose-Estimation) | 1 |
| | [Segmentation-and-Detection](Image-Specialized-and-Supporting/Segmentation-and-Detection) | 5 |
| | [Transparent-Layers](Image-Specialized-and-Supporting/Transparent-Layers) | 6 |
| | [Virtual-Try-On](Image-Specialized-and-Supporting/Virtual-Try-On) | 6 |

## Naming and folder convention

- **Folders:** `<Category>/<Task>/`. A task folder with more than 8 workflows is split into model-family subfolders (`FLUX-2/`, `Qwen-Image/`, `Z-Image/`, `SDXL/`, `SD15/` ...); a family with only one workflow in that folder goes to `Other/`. Smaller task folders stay flat.
- **Inside a model-family folder** the folder already names the model and the task folder names the task, so files carry only what tells siblings apart: `<variant>[-<size>][-<precision>][-<feature>].json`, for example `Text-to-Image/FLUX-2/klein-9b-fp8.json`, `Text-to-Image/Z-Image/turbo-fp8-aio-lora.json`, `Single-Image-Edit/Qwen-Image/v21-turbo.json`. The plain default of a family is `base.json`; a `-nunchaku` suffix marks Nunchaku-quantised builds.
- **In flat folders and `Other/`** the model stays in the name: `<model>-<task>[-<key-variant>].json`, for example `birefnet-remove-background.json`.
- **Always:** lowercase kebab-case (`a-z`, `0-9`, single hyphens), at most 60 characters, no source prefixes, list numbers or episode tags unless they are the only difference between two siblings. Version dots are dropped (`sd3.5` -> `sd35`, Qwen-Image 2.1 -> `v21`, `qwen-3.5` -> `qwen35`).

## Model coverage

Built from the four category READMEs. "Covered" means at least one workflow in `01-Image` loads the model.

### Covered

- **Generation:** FLUX.1 dev / schnell / Fill / Kontext / Redux / Canny / Depth, FLUX.2 dev, FLUX.2 Klein 4B / 9B (distilled and Base), FLUX.3 Klein (distilled and Base), Qwen-Image, Qwen-Image 2512, Qwen-Image 2.1, Qwen-Image-Edit / 2509 / 2511, Krea 2 Raw / Turbo, Z-Image Turbo and Base, HiDream-I1 Full / Dev / Fast, HiDream-E1 / E1.1, HiDream-O1, HunyuanImage 2.1, Chroma 1 HD / Radiance, AuraFlow v0.3, Lumina Image 2.0, LongCat Image and Image Edit, Kolors (and Kolors Inpainting), Kandinsky 5 Lite, Janus-Pro 7B, PixArt-alpha, Sana 1.5 / 1.6B / 1.6B 4K, Fibo 2.0 Dev / Edit Turbo, MOSS-Image Base / SFT, Ming Image 0.1, MiniMax-H3-Image, P-H3 Image, Boogu Image 0.1 Turbo / Edit, Anima, ERNIE Image, Stable Diffusion 1.5 (Juggernaut Reborn), SDXL Base + Refiner, SDXL Turbo / Lightning / Hyper, SD 3 Medium, SD 3.5 Large (+ Canny / Depth / Blur ControlNets), Stable Cascade.
- **Editing and control:** SD 1.5 Inpainting, BrushNet (SD 1.5, SDXL), PowerPaint v2, MAT + Fooocus inpaint, LaMa, AnyDoor, Paint-by-Example, OmniGen v1, OmniGen2, InstructPix2Pix, MagicQuill, IC-Light FC / FBC, ControlNet v1.1 (Canny, Depth, LineArt, OpenPose, Scribble), ControlNet XL Canny, T2I-Adapter, GLIGEN, IP-Adapter (SD 1.5, SDXL, FaceID, FaceID Plus v2), InstantID, PuLID (SDXL), PhotoMaker v1 / v2, StoryMaker.
- **Enhancement:** 4x-UltraSharp, ESRGAN, Real-ESRGAN (x4plus, anime 6B, AnimeVideo v3), BSRGAN, SwinIR, HAT, DAT, SRFormer, SeedVR2 3B / 7B, SUPIR, CCSR, StableSR, DiffBIR v2, CodeFormer, GFPGAN v1.4, GPEN, NAFNet, Restormer, SCUNet, Retinexformer, DDColor.
- **Specialized and supporting:** CatVTON, CatVTON-FLUX, IDM-VTON, OOTDiffusion, Leffa, LayerDiffusion (SD 1.5, SDXL), BRIA RMBG 1.4 and 2.0, BiRefNet, Grounding DINO + SAM / HQ-SAM / SAM 2.1, SAM 3 / 3.1, Florence-2, WD14 Tagger v3, Depth Anything V2 / 3, MiDaS, Marigold (and LCM), DWPose, OpenPose.

### Not available in ComfyUI

No authentic, published ComfyUI workflow was found for these atlas entries, so none was added (details in each category README):

- **Generation:** GLM-Image, HunyuanImage 3.0 / 3.0 Instruct / 3.0 Instruct Distil, Boogu Image 0.1 Base, Kandinsky 3, Wuerstchen v2, DeepFloyd IF, Show-o2, BAGEL, Emu3. PixArt-Sigma, Sana 0.6B, SD 2.1, SD 3.5 Medium / Large Turbo and SDXL fine-tunes (Playground v2.5, OpenJourney v4, DreamShaper XL, RealVisXL, Animagine XL 3.1, Illustrious XL, Pony Diffusion XL) have no workflow of their own but load in the existing PixArt, Sana, SDXL or SD 3.5 graphs.
- **Editing and control:** SDXL Inpainting 0.1, DiffEdit, DragDiffusion, DragGAN, ControlNet v1.1 Tile.
- **Enhancement:** ResShift, SeeSR, PASD, SinSR, RestoreFormer / RestoreFormer++ (standalone), DeOldify, Zero-DCE.
- **Specialized and supporting:** CatV2TON, StableVITON, OutfitAnyone, Grounding DINO 1.5, ZoeDepth (standalone), CLIP ViT-L/14 and SigLIP (standalone), BLIP-2.

See the [main README](../README.md) for setup steps or [`00-LIBRARY-INDEX.md`](../00-LIBRARY-INDEX.md) for the full list of workflows.
