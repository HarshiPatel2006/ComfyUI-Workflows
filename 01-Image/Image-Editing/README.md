# Image Editing — ComfyUI workflows

Image-to-image (img2img) and instruction editing: single- and multi-image edits, inpainting, outpainting, object removal, background removal, outfit and pose changes, sketch-to-image and compositing tools.

| Subfolder | What is inside | Workflows |
|---|---|---|
| [`Background-Removal/`](Background-Removal) | Background removal and segmentation | 5 |
| [`Character-Outfit-and-Pose/`](Character-Outfit-and-Pose) | Outfit transfer, pose and character edits | 12 |
| [`Compositing-and-Image-Tools/`](Compositing-and-Image-Tools) | Crop, compose, paint, stitch and other image tools | 15 |
| [`ControlNet-and-Adapters/`](ControlNet-and-Adapters) | ControlNet 1.1/XL, T2I-Adapter and GLIGEN layout control | 9 |
| [`Inpaint-Outpaint-and-Object-Removal/`](Inpaint-Outpaint-and-Object-Removal) | Inpainting, outpainting and object removal | 28 |
| [`Multi-Image-Composition/`](Multi-Image-Composition) | Multi-image edits and composition | 27 |
| [`Reference-and-Identity/`](Reference-and-Identity) | IP-Adapter, FaceID, InstantID, PuLID, PhotoMaker and StoryMaker | 25 |
| [`Relighting/`](Relighting) | IC-Light relighting | 5 |
| [`Single-Image-Edit/`](Single-Image-Edit) | Instruction-based single-image editing (img2img) | 41 |
| [`Sketch-and-3D-to-Image/`](Sketch-and-3D-to-Image) | Sketch-to-image and 3D-render-to-image | 9 |

## Workflows (176)

### Background removal and segmentation

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [birefnet-remove-background](Background-Removal/birefnet-remove-background.json) | Remove Background | `birefnet.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-21-remove-background](Background-Removal/qwen-image-21-remove-background.json) | Remove Background | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [sam3-remove-background-crop-object](Background-Removal/sam3-remove-background-crop-object.json) | Remove Background (Segment + Crop Object) | — | ComfyUI-RMBG |
| [utility-remove-background-transparent-items](Background-Removal/utility-remove-background-transparent-items.json) | Remove Background from Transparent Items | — | ComfyUI-RMBG |
| [utility-remove-background](Background-Removal/utility-remove-background.json) | Remove Background | — | ComfyUI-RMBG, ComfyUI_LayerStyle, rgthree-comfy |

### Outfit transfer, pose and character edits

**FLUX-2**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [klein-9b-character-turnaround-from-one-image](Character-Outfit-and-Pose/FLUX-2/klein-9b-character-turnaround-from-one-image.json) | Character Turnaround Sheet from One Image | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [klein-9b-character-sheet](Character-Outfit-and-Pose/FLUX-2/klein-9b-character-sheet.json) | Flux Klein - Character Sheet from One Picture (Ep41) | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |

**FLUX-3**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [klein-character-sheet](Character-Outfit-and-Pose/FLUX-3/klein-character-sheet.json) | Character Sheet | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [klein-outfit-change](Character-Outfit-and-Pose/FLUX-3/klein-outfit-change.json) | Outfit Change | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |

**Krea-2**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [outfit-change-outfit-lora](Character-Outfit-and-Pose/Krea-2/outfit-change-outfit-lora.json) | Outfit Change + Outfit LoRA | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [outfit-transfer-v2](Character-Outfit-and-Pose/Krea-2/outfit-transfer-v2.json) | Outfit Transfer v2 | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |

**P-H3**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [character-sheet](Character-Outfit-and-Pose/P-H3/character-sheet.json) | P-H3 Image - Character Sheet (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [outfit-from-second-picture](Character-Outfit-and-Pose/P-H3/outfit-from-second-picture.json) | P-H3 Image - Outfit from a Second Picture (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |

**Qwen-Image**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [v21-character-sheet](Character-Outfit-and-Pose/Qwen-Image/v21-character-sheet.json) | Character Sheet | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [v21-outfit-change-turbo](Character-Outfit-and-Pose/Qwen-Image/v21-outfit-change-turbo.json) | Outfit Change — Turbo | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma |
| [v21-outfit-change](Character-Outfit-and-Pose/Qwen-Image/v21-outfit-change.json) | Outfit Change | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [v21-pose-from-a-picture](Character-Outfit-and-Pose/Qwen-Image/v21-pose-from-a-picture.json) | Pose from a Picture | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |

### Crop, compose, paint, stitch and other image tools

**Pixaroma-Nodes**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [3d-builder-ep11](Compositing-and-Image-Tools/Pixaroma-Nodes/3d-builder-ep11.json) | 3D Builder (Ep11) | — | ComfyUI-Pixaroma |
| [3d-builder-ep13](Compositing-and-Image-Tools/Pixaroma-Nodes/3d-builder-ep13.json) | 3D Builder (Ep13) | — | ComfyUI-Pixaroma |
| [combine-join-two-images](Compositing-and-Image-Tools/Pixaroma-Nodes/combine-join-two-images.json) | Combine — Join Two Images | — | ComfyUI-Pixaroma |
| [crop-ep11](Compositing-and-Image-Tools/Pixaroma-Nodes/crop-ep11.json) | Crop (Ep11) | — | ComfyUI-Pixaroma |
| [crop-ep13](Compositing-and-Image-Tools/Pixaroma-Nodes/crop-ep13.json) | Crop (Ep13) | — | ComfyUI-Pixaroma |
| [image-composer-ep11](Compositing-and-Image-Tools/Pixaroma-Nodes/image-composer-ep11.json) | Image Composer (Ep11) | — | ComfyUI-Pixaroma |
| [image-composer-ep13](Compositing-and-Image-Tools/Pixaroma-Nodes/image-composer-ep13.json) | Image Composer (Ep13) | — | ComfyUI-Pixaroma |
| [paint-ep11](Compositing-and-Image-Tools/Pixaroma-Nodes/paint-ep11.json) | Paint (Ep11) | — | ComfyUI-Pixaroma |
| [paint-ep13](Compositing-and-Image-Tools/Pixaroma-Nodes/paint-ep13.json) | Paint (Ep13) | — | ComfyUI-Pixaroma |

**Utility**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [image-blend](Compositing-and-Image-Tools/Utility/image-blend.json) | Image Blend | — | ComfyUI-RMBG, ComfyUI_LayerStyle |
| [image-combiner-transparent-items](Compositing-and-Image-Tools/Utility/image-combiner-transparent-items.json) | Image Combiner for Transparent Items | — | ComfyUI-RMBG |
| [image-combiner](Compositing-and-Image-Tools/Utility/image-combiner.json) | Image Combiner | — | ComfyUI-RMBG |
| [image-scale](Compositing-and-Image-Tools/Utility/image-scale.json) | Image Scale | — | ComfyUI-KJNodes |
| [image-stitch](Compositing-and-Image-Tools/Utility/image-stitch.json) | Image Stitch | — | ComfyUI-RMBG, rgthree-comfy |
| [image-transformation](Compositing-and-Image-Tools/Utility/image-transformation.json) | Image Transformation | — | ComfyUI_LayerStyle, rgthree-comfy |

### Inpainting, outpainting and object removal

**FLUX-2**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [klein-4b-fp8-distill-inpaint](Inpaint-Outpaint-and-Object-Removal/FLUX-2/klein-4b-fp8-distill-inpaint.json) | Inpaint | `flux-2-klein-4b-fp8.safetensors`, `qwen_3_4b.safetensors`, `flux2-vae.safetensors` | ComfyUI-Inpaint-CropAndStitch, rgthree-comfy |
| [klein-9b-fp8-distill-inpaint](Inpaint-Outpaint-and-Object-Removal/FLUX-2/klein-9b-fp8-distill-inpaint.json) | Inpaint | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Inpaint-CropAndStitch, rgthree-comfy |
| [klein-9b-fp8-distill-paint-guided-edit](Inpaint-Outpaint-and-Object-Removal/FLUX-2/klein-9b-fp8-distill-paint-guided-edit.json) | Paint-Guided Edit | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [klein-9b-fp8-inpaint](Inpaint-Outpaint-and-Object-Removal/FLUX-2/klein-9b-fp8-inpaint.json) | Inpaint (Ep22) | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [klein-9b-int8-inpaint](Inpaint-Outpaint-and-Object-Removal/FLUX-2/klein-9b-int8-inpaint.json) | Inpaint | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [klein-9b-kv-fp8-inpaint](Inpaint-Outpaint-and-Object-Removal/FLUX-2/klein-9b-kv-fp8-inpaint.json) | Inpaint | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | ComfyUI-Inpaint-CropAndStitch, rgthree-comfy |
| [klein-9b-kv-fp8-outpaint-custom-ratio](Inpaint-Outpaint-and-Object-Removal/FLUX-2/klein-9b-kv-fp8-outpaint-custom-ratio.json) | Outpaint (Custom Ratio) | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | ComfyUI-KJNodes, rgthree-comfy |
| [klein-9b-outpaint](Inpaint-Outpaint-and-Object-Removal/FLUX-2/klein-9b-outpaint.json) | Outpaint | `flux-2-klein-9b-int8-convrot.safetensors`, `pixaoutpaint.safetensors`, `qwen_3_8b_fp8mixed.safetensors` +1 more | ComfyUI-Pixaroma |
| [klein-9b-paint-to-image](Inpaint-Outpaint-and-Object-Removal/FLUX-2/klein-9b-paint-to-image.json) | Paint to Image | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |

**FLUX-3**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [klein-edit-inside-a-box](Inpaint-Outpaint-and-Object-Removal/FLUX-3/klein-edit-inside-a-box.json) | Edit inside a Box | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [klein-outpaint](Inpaint-Outpaint-and-Object-Removal/FLUX-3/klein-outpaint.json) | Outpaint | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma |

**P-H3**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [edit-inside-box](Inpaint-Outpaint-and-Object-Removal/P-H3/edit-inside-box.json) | P-H3 Image - Edit inside a Box (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [outpaint](Inpaint-Outpaint-and-Object-Removal/P-H3/outpaint.json) | P-H3 Image - Outpaint (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |

**Qwen-Image**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [v21-inpaint](Inpaint-Outpaint-and-Object-Removal/Qwen-Image/v21-inpaint.json) | Inpaint | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [v21-outpaint](Inpaint-Outpaint-and-Object-Removal/Qwen-Image/v21-outpaint.json) | Outpaint | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma |

**Other**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [lama-object-remover](Inpaint-Outpaint-and-Object-Removal/Other/lama-object-remover.json) | Object Remover | — | ComfyUI-RMBG |

### Multi-image edits and composition

**FLUX-2**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [klein-4b-fp8-distill-edit-2-images](Multi-Image-Composition/FLUX-2/klein-4b-fp8-distill-edit-2-images.json) | Multi-Image Edit — 2 Images | `flux-2-klein-4b-fp8.safetensors`, `qwen_3_4b.safetensors`, `flux2-vae.safetensors` | Core only |
| [klein-9b-fp8-distill-edit-2-images](Multi-Image-Composition/FLUX-2/klein-9b-fp8-distill-edit-2-images.json) | Multi-Image Edit — 2 Images | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | Core only |
| [klein-9b-image-composer-to-image](Multi-Image-Composition/FLUX-2/klein-9b-image-composer-to-image.json) | Image Composer to Image | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [klein-9b-kv-fp8-image-blend](Multi-Image-Composition/FLUX-2/klein-9b-kv-fp8-image-blend.json) | Image Blend | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | ComfyUI-RMBG, ComfyUI_LayerStyle, rgthree-comfy |
| [klein-9b-kv-fp8-edit-2-images](Multi-Image-Composition/FLUX-2/klein-9b-kv-fp8-edit-2-images.json) | Multi-Image Edit — 2 Images | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | Core only |
| [klein-9b-kv-fp8-edit-3-images](Multi-Image-Composition/FLUX-2/klein-9b-kv-fp8-edit-3-images.json) | Multi-Image Edit — 3 Images | `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors`, `flux2-vae.safetensors` | Core only |
| [klein-9b-kv-fp8-edit-4-images](Multi-Image-Composition/FLUX-2/klein-9b-kv-fp8-edit-4-images.json) | Multi-Image Edit — 4 Images | `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors`, `flux2-vae.safetensors` | Core only |

**FLUX-3**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [klein-character-in-a-scene](Multi-Image-Composition/FLUX-3/klein-character-in-a-scene.json) | Character in a Scene | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [klein-group-photo](Multi-Image-Composition/FLUX-3/klein-group-photo.json) | Group Photo | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [klein-logo-on-a-product](Multi-Image-Composition/FLUX-3/klein-logo-on-a-product.json) | Logo on a Product | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [klein-product-ad](Multi-Image-Composition/FLUX-3/klein-product-ad.json) | Product Ad | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |

**P-H3**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [character-in-a-scene](Multi-Image-Composition/P-H3/character-in-a-scene.json) | P-H3 Image - Character in a Scene (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [logo-on-product](Multi-Image-Composition/P-H3/logo-on-product.json) | P-H3 Image - Logo on a Product (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [group-photo](Multi-Image-Composition/P-H3/group-photo.json) | P-H3 Image - Group Photo (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [style-from-second-picture](Multi-Image-Composition/P-H3/style-from-second-picture.json) | P-H3 Image - Style from a Second Picture (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `minimax_h3_style_transfer_v1.0_r64.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |

**Qwen-Image**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [v21-character-in-a-scene](Multi-Image-Composition/Qwen-Image/v21-character-in-a-scene.json) | Character in a Scene | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [v21-logo-on-a-product](Multi-Image-Composition/Qwen-Image/v21-logo-on-a-product.json) | Logo on a Product | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [v21-edit-2-images-prompt-enhancer](Multi-Image-Composition/Qwen-Image/v21-edit-2-images-prompt-enhancer.json) | Multi-Image Edit — 2 Images + Prompt Enhancer | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [v21-edit-3-images](Multi-Image-Composition/Qwen-Image/v21-edit-3-images.json) | Multi-Image Edit — 3 Images | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [v21-edit-4-images](Multi-Image-Composition/Qwen-Image/v21-edit-4-images.json) | Multi-Image Edit — 4 Images | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [v21-edit-group-photo-6-images](Multi-Image-Composition/Qwen-Image/v21-edit-group-photo-6-images.json) | Multi-Image Edit — Group Photo from 6 Images | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |

**Other**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [minimax-h3-image-multi-edit-bbox-refs](Multi-Image-Composition/Other/minimax-h3-image-multi-edit-bbox-refs.json) | H3 Image Edit - BBox Layout + 4 Reference Images ([how to use](Multi-Image-Composition/Other/minimax-h3-image-multi-edit-bbox-refs-README.md)) | `minimax_h3_image_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_int8_convrot.safetensors`, `minimax_h3_image_vae_fp16.safetensors` +1 more | ComfyUI-H3Image-LayoutKit, ComfyUI-KJNodes |
| [ming-image-product-ad-from-two-pictures](Multi-Image-Composition/Other/ming-image-product-ad-from-two-pictures.json) | Product Ad from Two Pictures | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |

### Instruction-based single-image editing (img2img)

**FLUX-2**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [klein-4b-fp8-distill](Single-Image-Edit/FLUX-2/klein-4b-fp8-distill.json) | One Image Edit | `flux-2-klein-4b-fp8.safetensors`, `qwen_3_4b.safetensors`, `flux2-vae.safetensors` | rgthree-comfy |
| [klein-9b-fp8-distill](Single-Image-Edit/FLUX-2/klein-9b-fp8-distill.json) | One Image Edit | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | rgthree-comfy |
| [klein-9b-int8](Single-Image-Edit/FLUX-2/klein-9b-int8.json) | One Image Edit | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [klein-9b-kv-fp8-custom-ratio](Single-Image-Edit/FLUX-2/klein-9b-kv-fp8-custom-ratio.json) | One Image Edit (Custom Ratio) | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | rgthree-comfy |
| [klein-9b-kv-fp8-same-ratio](Single-Image-Edit/FLUX-2/klein-9b-kv-fp8-same-ratio.json) | One Image Edit (Same Ratio) | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | rgthree-comfy |
| [klein-9b](Single-Image-Edit/FLUX-2/klein-9b.json) | One Image Edit V1 | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [klein-9b-v2-notify-switch](Single-Image-Edit/FLUX-2/klein-9b-v2-notify-switch.json) | One Image Edit V2 + Notify and Switch | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [klein-9b-v3-dated-folder](Single-Image-Edit/FLUX-2/klein-9b-v3-dated-folder.json) | One Image Edit V3 + Keep Filename + Save to Dated Folder | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [klein-9b-one-image-many-edits](Single-Image-Edit/FLUX-2/klein-9b-one-image-many-edits.json) | One Image, Many Edits | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [klein-9b-one-image-prompts-from-list](Single-Image-Edit/FLUX-2/klein-9b-one-image-prompts-from-list.json) | One Image, Prompts from List | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |

**FLUX-3**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [klein-text-in-a-picture](Single-Image-Edit/FLUX-3/klein-text-in-a-picture.json) | Edit Text in a Picture | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [klein](Single-Image-Edit/FLUX-3/klein.json) | One Image Edit | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [klein-relight-and-seasons](Single-Image-Edit/FLUX-3/klein-relight-and-seasons.json) | Relight and Seasons | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [klein-restore-and-colorize](Single-Image-Edit/FLUX-3/klein-restore-and-colorize.json) | Restore and Colorize | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [klein-restyle](Single-Image-Edit/FLUX-3/klein-restyle.json) | Restyle | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |

**Krea-2**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [lora-character-and-background](Single-Image-Edit/Krea-2/lora-character-and-background.json) | Edit LoRA — Character and Background | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [lora-custom-ratio](Single-Image-Edit/Krea-2/lora-custom-ratio.json) | Edit LoRA — Custom Ratio | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [lora](Single-Image-Edit/Krea-2/lora.json) | Edit LoRA | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |

**Ming-Image**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [base](Single-Image-Edit/Ming-Image/base.json) | One Image Edit | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [social-media-pack-from-one-image](Single-Image-Edit/Ming-Image/social-media-pack-from-one-image.json) | Social Media Pack from One Image | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |

**MiniMax-H3**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [single-frame](Single-Image-Edit/MiniMax-H3/single-frame.json) | One Image Edit (Single Frame) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `minimax_h3_video_vae_fp16.safetensors` | ComfyUI-Pixaroma |
| [base](Single-Image-Edit/MiniMax-H3/base.json) | MiniMax H3 Image — One Image Edit (official ComfyUI template) | `minimax_h3_image_pruned_int8_convrot.safetensors`, `qwen3vl_32b_minimax_h3_int8_convrot.safetensors`, `minimax_h3_image_vae_fp16.safetensors` +1 more | Core only |

**P-H3**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [new-place](Single-Image-Edit/P-H3/new-place.json) | P-H3 Image - Image Edit New Place (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [relight-day-to-night](Single-Image-Edit/P-H3/relight-day-to-night.json) | P-H3 Image - Relight Day to Night (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [text-in-a-picture](Single-Image-Edit/P-H3/text-in-a-picture.json) | P-H3 Image - Edit Text in a Picture (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [restyle-picture](Single-Image-Edit/P-H3/restyle-picture.json) | P-H3 Image - Restyle a Picture (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [restore-and-colorize](Single-Image-Edit/P-H3/restore-and-colorize.json) | P-H3 Image - Restore and Colorize (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |

**Qwen-Image**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [v21-consistency-lora](Single-Image-Edit/Qwen-Image/v21-consistency-lora.json) | One Image Edit + Consistency LoRA | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma |
| [v21-low-vram](Single-Image-Edit/Qwen-Image/v21-low-vram.json) | One Image Edit — Low VRAM | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [v21-prompt-enhancer](Single-Image-Edit/Qwen-Image/v21-prompt-enhancer.json) | One Image Edit + Prompt Enhancer | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [v21-turbo](Single-Image-Edit/Qwen-Image/v21-turbo.json) | One Image Edit — Turbo | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma |
| [v21](Single-Image-Edit/Qwen-Image/v21.json) | One Image Edit | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |

**Other**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [boogu-edit](Single-Image-Edit/Other/boogu-edit.json) | One Image Edit | `qwen3vl_8b_fp8_scaled.safetensors`, `ae.safetensors`, `boogu_image_edit_turbo_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [sd15-juggernaut-img2img](Single-Image-Edit/Other/sd15-juggernaut-img2img.json) | Image to Image | `juggernaut_reborn.safetensors` | Core only |
| [moss-image-edit-text-in-a-picture](Single-Image-Edit/Other/moss-image-edit-text-in-a-picture.json) | MOSS Image - Same Picture, New Words (Ep40) | `moss_image_sft_int8_convrot.safetensors`, `qwen3.5_9b_w4a8_gptq.safetensors`, `flux2-vae_small.safetensors` | ComfyUI-Pixaroma |

### Sketch-to-image and 3D-render-to-image

**FLUX-2**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [klein-9b-3d-model-to-image-ep33](Sketch-and-3D-to-Image/FLUX-2/klein-9b-3d-model-to-image-ep33.json) | 3D Model to Image (Ep33) | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [klein-9b-3d-model-to-image-keep-the-angle-ep33](Sketch-and-3D-to-Image/FLUX-2/klein-9b-3d-model-to-image-keep-the-angle-ep33.json) | 3D Model to Image — Keep the Angle (Ep33) | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [klein-9b-3d-model-to-image-keep-the-angle-ep34](Sketch-and-3D-to-Image/FLUX-2/klein-9b-3d-model-to-image-keep-the-angle-ep34.json) | 3D Model to Image — Keep the Angle (Ep34) | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [klein-9b-3d-model-to-image](Sketch-and-3D-to-Image/FLUX-2/klein-9b-3d-model-to-image.json) | 3D Model to Image | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [klein-9b-3d-scene-builder-to-image](Sketch-and-3D-to-Image/FLUX-2/klein-9b-3d-scene-builder-to-image.json) | 3D Scene Builder to Image | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |

**Ming-Image**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [restyle-a-design-to-3d](Sketch-and-3D-to-Image/Ming-Image/restyle-a-design-to-3d.json) | Restyle a Design to 3D | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [sketch-to-photo](Sketch-and-3D-to-Image/Ming-Image/sketch-to-photo.json) | Sketch to Photo | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |

**Qwen-Image**

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [v21-sketch-to-image-consistency-lora](Sketch-and-3D-to-Image/Qwen-Image/v21-sketch-to-image-consistency-lora.json) | Sketch to Image + Consistency LoRA | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma |
| [v21-sketch-to-image](Sketch-and-3D-to-Image/Qwen-Image/v21-sketch-to-image.json) | Sketch to Image | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |

## Editing and control models from the Open-Source Image Model Atlas (Nov 2026)

Collected for the "Image Editing and Control" entries of the Open-Source Image Model Atlas. Each file is an existing workflow from the linked source, copied as published unless the purpose column says a model file name was changed. None of them has been run here: every row is **not runtime-tested**. Base checkpoints (SD 1.5, SDXL and others named in the graphs) carry their own licences; check them as well.

#### Inpaint-Outpaint-and-Object-Removal

**PowerPaint**

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence | Tested |
|---|---|---|---|---|---|---|---|
| [object-removal](Inpaint-Outpaint-and-Object-Removal/PowerPaint/object-removal.json) | PowerPaint v2 | Text-selected object removal (GroundingDINO+SAM mask, PowerPaint remove task) | [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/PowerPaint_object_removal.json) | [weights](https://huggingface.co/JunhaoZhuang/PowerPaint-v2-1) | ComfyUI-BrushNet, comfyui_segment_anything | Review PowerPaint weight terms | not runtime-tested |
| [outpaint](Inpaint-Outpaint-and-Object-Removal/PowerPaint/outpaint.json) | PowerPaint v2 | Outpaint with the PowerPaint outpainting task | [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/PowerPaint_outpaint.json) | [weights](https://huggingface.co/JunhaoZhuang/PowerPaint-v2-1) | ComfyUI-BrushNet | Review PowerPaint weight terms | not runtime-tested |

**SD15**

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence | Tested |
|---|---|---|---|---|---|---|---|
| [inpainting-inpaint](Inpaint-Outpaint-and-Object-Removal/SD15/inpainting-inpaint.json) | SD 1.5 Inpainting | Masked inpaint with the dedicated SD 1.5 inpainting checkpoint (checkpoint name changed from the SD2 512-inpainting example) | [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/inpaint/inpaint_example.png) | [weights](https://huggingface.co/stable-diffusion-v1-5/stable-diffusion-inpainting) | — (core) | CreativeML OpenRAIL-M | not runtime-tested |
| [inpainting-outpaint](Inpaint-Outpaint-and-Object-Removal/SD15/inpainting-outpaint.json) | SD 1.5 Inpainting | Outpaint (pad canvas then fill) with the SD 1.5 inpainting checkpoint (checkpoint name changed from the SD2 example) | [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/inpaint/inpain_model_outpainting.png) | [weights](https://huggingface.co/stable-diffusion-v1-5/stable-diffusion-inpainting) | — (core) | CreativeML OpenRAIL-M | not runtime-tested |
| [inpaint](Inpaint-Outpaint-and-Object-Removal/SD15/inpaint.json) | BrushNet (SD 1.5) | Dual-branch BrushNet inpaint on any SD 1.5 checkpoint | [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/BrushNet_basic.json) | [weights](https://huggingface.co/TencentARC/BrushNet) | ComfyUI-BrushNet | Code Apache-2.0; review BrushNet weight terms | not runtime-tested |
| [inpaint-small-area-crop](Inpaint-Outpaint-and-Object-Removal/SD15/inpaint-small-area-crop.json) | BrushNet (SD 1.5) | Crop around a small mask, inpaint at full resolution and blend back | [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/BrushNet_cut_for_inpaint.json) | [weights](https://huggingface.co/TencentARC/BrushNet) | ComfyUI-BrushNet | Code Apache-2.0; review BrushNet weight terms | not runtime-tested |
| [inpaint-controlnet](Inpaint-Outpaint-and-Object-Removal/SD15/inpaint-controlnet.json) | BrushNet (SD 1.5) + ControlNet | Inpaint guided by a scribble ControlNet inside the mask | [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/BrushNet_with_CN.json) | [weights](https://huggingface.co/TencentARC/BrushNet) | ComfyUI-BrushNet | Code Apache-2.0; review BrushNet weight terms | not runtime-tested |
| [inpaint-ip-adapter-reference](Inpaint-Outpaint-and-Object-Removal/SD15/inpaint-ip-adapter-reference.json) | BrushNet (SD 1.5) + IP-Adapter | Fill the mask with content taken from a reference picture | [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/BrushNet_with_IPA.json) | [weights](https://huggingface.co/TencentARC/BrushNet) | ComfyUI-BrushNet, ComfyUI_IPAdapter_plus | Code Apache-2.0; review BrushNet weight terms | not runtime-tested |
| [text-masked-batch-inpaint](Inpaint-Outpaint-and-Object-Removal/SD15/text-masked-batch-inpaint.json) | BrushNet (SD 1.5) | Batch inpaint where GroundingDINO+SAM build the mask from a text prompt | [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/BrushNet_image_batch.json) | [weights](https://huggingface.co/TencentARC/BrushNet) | ComfyUI-BrushNet, comfyui_segment_anything, ComfyUI-VideoHelperSuite | Code Apache-2.0; review BrushNet weight terms | not runtime-tested |

**SDXL**

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence | Tested |
|---|---|---|---|---|---|---|---|
| [brushnet-sdxl-inpaint](Inpaint-Outpaint-and-Object-Removal/SDXL/brushnet-sdxl-inpaint.json) | BrushNet (SDXL) | BrushNet inpaint on an SDXL checkpoint | [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/BrushNet_SDXL_basic.json) | [weights](https://huggingface.co/TencentARC/BrushNet) | ComfyUI-BrushNet | Code Apache-2.0; review BrushNet weight terms | not runtime-tested |
| [brushnet-sdxl-inpaint-ultimate-upscale](Inpaint-Outpaint-and-Object-Removal/SDXL/brushnet-sdxl-inpaint-ultimate-upscale.json) | BrushNet (SDXL) | High-resolution inpaint through Ultimate SD Upscale tiles | [source](https://github.com/nullquant/ComfyUI-BrushNet/blob/main/example/BrushNet_SDXL_upscale.json) | [weights](https://huggingface.co/TencentARC/BrushNet) | ComfyUI-BrushNet, ComfyUI_UltimateSDUpscale | Code Apache-2.0; review BrushNet weight terms | not runtime-tested |
| [mat-prefill-sdxl-fooocus-inpaint](Inpaint-Outpaint-and-Object-Removal/SDXL/mat-prefill-sdxl-fooocus-inpaint.json) | MAT (Places512) + Fooocus inpaint (SDXL) | MAT pre-fills the hole, then SDXL + Fooocus inpaint patch refines it (inpaint and outpaint branches) | [source](https://github.com/Acly/comfyui-inpaint-nodes/blob/main/workflows/inpaint-preprocess.json) | [weights](https://github.com/Sanster/models/releases/tag/add_mat) | comfyui-inpaint-nodes | MAT weights CC BY-NC 4.0 (non-commercial); Fooocus patch: review | not runtime-tested |

#### Multi-Image-Composition

**Paint-by-Example**

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence | Tested |
|---|---|---|---|---|---|---|---|
| [insert-two-examples](Multi-Image-Composition/Paint-by-Example/insert-two-examples.json) | Paint-by-Example | Paste two example objects into masked regions, no prompt (API-format graph) | [source](https://github.com/phyblas/ironna_comfyui_workflow/tree/master/stable_diffusion/paint-by-example) | [weights](https://huggingface.co/Fantasy-Studio/Paint-by-Example) | paint-by-example_comfyui (auto-downloads weights) | CreativeML OpenRAIL-M | not runtime-tested |
| [generate-example-then-insert](Multi-Image-Composition/Paint-by-Example/generate-example-then-insert.json) | Paint-by-Example | Generate the example object with an SD checkpoint, then insert it (API-format graph) | [source](https://github.com/phyblas/ironna_comfyui_workflow/tree/master/stable_diffusion/paint-by-example) | [weights](https://huggingface.co/Fantasy-Studio/Paint-by-Example) | paint-by-example_comfyui (auto-downloads weights) | CreativeML OpenRAIL-M | not runtime-tested |

**Other**

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence | Tested |
|---|---|---|---|---|---|---|---|
| [anydoor-object-insertion](Multi-Image-Composition/Other/anydoor-object-insertion.json) | AnyDoor | Teleport a reference object into a masked region of a scene | [source](https://github.com/smthemex/ComfyUI_AnyDoor/blob/main/examples/img2img.json) | [weights](https://huggingface.co/xichenhku/AnyDoor) | ComfyUI_AnyDoor | Code MIT; review AnyDoor weight terms | not runtime-tested |
| [omnigen-multi-image-combine](Multi-Image-Composition/Other/omnigen-multi-image-combine.json) | OmniGen v1 | Combine subjects from several input images by instruction | [source](https://github.com/1038lab/ComfyUI-OmniGen/blob/main/Examples/omnigen_combine.json) | [weights](https://huggingface.co/Shitao/OmniGen-v1) | ComfyUI-OmniGen (1038lab) | MIT | not runtime-tested |

#### Single-Image-Edit

**OmniGen**

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence | Tested |
|---|---|---|---|---|---|---|---|
| [instruction](Single-Image-Edit/OmniGen/instruction.json) | OmniGen v1 | Instruction edit / text-to-image with up to three reference images | [source](https://github.com/1038lab/ComfyUI-OmniGen/blob/main/Examples/OmniGen_wf.json) | [weights](https://huggingface.co/Shitao/OmniGen-v1) | ComfyUI-OmniGen (1038lab), rgthree-comfy, ComfyUI_essentials, comfyui-various, sdxl_prompt_styler, ComfyUI-Custom-Scripts | MIT | not runtime-tested |
| [depth-map-to-image](Single-Image-Edit/OmniGen/depth-map-to-image.json) | OmniGen v1 | Generate a new picture that follows the depth of an input image | [source](https://github.com/1038lab/ComfyUI-OmniGen/blob/main/Examples/depthmap2image.json) | [weights](https://huggingface.co/Shitao/OmniGen-v1) | ComfyUI-OmniGen (1038lab) | MIT | not runtime-tested |
| [2](Single-Image-Edit/OmniGen/2.json) | OmniGen2 | Official native instruction edit of one picture | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/image_omnigen2_image_edit.json) | [weights](https://huggingface.co/Comfy-Org/Omnigen2_ComfyUI_repackaged) | — (core) | Apache-2.0 | not runtime-tested |
| [2-two-image](Single-Image-Edit/OmniGen/2-two-image.json) | OmniGen2 | Official example: edit with one or two reference pictures via ReferenceLatent | [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/omnigen/omnigen2_example.png) | [weights](https://huggingface.co/Comfy-Org/Omnigen2_ComfyUI_repackaged) | — (core) | Apache-2.0 | not runtime-tested |

**Other**

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence | Tested |
|---|---|---|---|---|---|---|---|
| [instructpix2pix-instruction-edit](Single-Image-Edit/Other/instructpix2pix-instruction-edit.json) | InstructPix2Pix | Text-instruction edit using core InstructPixToPix conditioning (official CosXL-edit example with the checkpoint switched to InstructPix2Pix) | [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/edit_models/sdxl_edit_model.png) | [weights](https://huggingface.co/timbrooks/instruct-pix2pix) | — (core) | MIT (weights); review base SD terms | not runtime-tested |
| [magicquill-brush-guided-edit](Single-Image-Edit/Other/magicquill-brush-guided-edit.json) | MagicQuill | Interactive brush/sketch-guided edit (add, remove, colour strokes) | [source](https://github.com/magic-quill/ComfyUI_MagicQuill/blob/main/MagicQuill.json) | [weights](https://huggingface.co/LiuZichen/MagicQuill-models) | ComfyUI_MagicQuill | CC BY-NC-SA 4.0 (non-commercial); review | not runtime-tested |

#### Relighting

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence | Tested |
|---|---|---|---|---|---|---|---|
| [ic-light-fc-relight-shaped-light](Relighting/ic-light-fc-relight-shaped-light.json) | IC-Light FC (SD 1.5) | Relight a foreground subject from a text prompt and a drawn light-shape mask | [source](https://github.com/kijai/ComfyUI-IC-Light/blob/main/example_workflows/ic_light_example_02.png) | [weights](https://huggingface.co/lllyasviel/ic-light) | ComfyUI-IC-Light, ComfyUI-KJNodes | Apache-2.0 | not runtime-tested |
| [ic-light-fc-relight-gradient](Relighting/ic-light-fc-relight-gradient.json) | IC-Light FC (SD 1.5) | Relight with a spline-controlled light gradient | [source](https://github.com/kijai/ComfyUI-IC-Light/blob/main/example_workflows/iclight_example_fc_controlled_gradient_01.png) | [weights](https://huggingface.co/lllyasviel/ic-light) | ComfyUI-IC-Light, ComfyUI-KJNodes, ComfyUI_essentials | Apache-2.0 | not runtime-tested |
| [ic-light-fc-relight-light-sources](Relighting/ic-light-fc-relight-light-sources.json) | IC-Light FC (SD 1.5) | Relight from several preset light-source directions in one batch | [source](https://github.com/kijai/ComfyUI-IC-Light/blob/main/example_workflows/ic_light_simple_light_multi_02.png) | [weights](https://huggingface.co/lllyasviel/ic-light) | ComfyUI-IC-Light, ComfyUI-KJNodes, ComfyUI_essentials | Apache-2.0 | not runtime-tested |
| [ic-light-fbc-background-relight](Relighting/ic-light-fbc-background-relight.json) | IC-Light FBC (SD 1.5) | Matte the subject and relight it to match a background image | [source](https://github.com/kijai/ComfyUI-IC-Light/blob/main/example_workflows/ic_light_fbc_example_02.png) | [weights](https://huggingface.co/lllyasviel/ic-light) | ComfyUI-IC-Light, ComfyUI-KJNodes, ComfyUI-BRIA_AI-RMBG | Apache-2.0 | not runtime-tested |
| [ic-light-fbc-normal-map](Relighting/ic-light-fbc-normal-map.json) | IC-Light FBC (SD 1.5) | Estimate a normal map from multi-light relights | [source](https://github.com/kijai/ComfyUI-IC-Light/blob/main/example_workflows/iclight_normals_example_01.png) | [weights](https://huggingface.co/lllyasviel/ic-light) | ComfyUI-IC-Light, ComfyUI-KJNodes, ComfyUI_essentials, ComfyUI-BRIA_AI-RMBG | Apache-2.0 | not runtime-tested |

#### ControlNet-and-Adapters

**GLIGEN**

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence | Tested |
|---|---|---|---|---|---|---|---|
| [textbox-layout](ControlNet-and-Adapters/GLIGEN/textbox-layout.json) | GLIGEN | Place prompted objects inside boxes (box coordinates typed in) | [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/gligen/gligen_textbox_example.png) | [weights](https://huggingface.co/comfyanonymous/GLIGEN_pruned_safetensors) | — (core) | Review GLIGEN weight terms | not runtime-tested |
| [gui-draw-boxes](ControlNet-and-Adapters/GLIGEN/gui-draw-boxes.json) | GLIGEN | Draw the GLIGEN boxes in a GUI node instead of typing coordinates | [source](https://github.com/mut-ex/comfyui-gligengui-node/blob/main/gligen_gui_workflow.png) | [weights](https://huggingface.co/comfyanonymous/GLIGEN_pruned_safetensors) | comfyui-gligengui-node | Review GLIGEN weight terms | not runtime-tested |

**SD15**

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence | Tested |
|---|---|---|---|---|---|---|---|
| [depth](ControlNet-and-Adapters/SD15/depth.json) | ControlNet v1.1 Depth | Depth-map guided SD 1.5 generation (official example, ControlNet file switched to v1.1) | [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/controlnet/depth_controlnet.png) | [weights](https://huggingface.co/lllyasviel/ControlNet-v1-1) | — (core) | OpenRAIL; review checkpoint | not runtime-tested |
| [openpose-2-pass](ControlNet-and-Adapters/SD15/openpose-2-pass.json) | ControlNet v1.1 OpenPose | Pose-skeleton guided generation with a 2-pass hires fix (ControlNet file switched to v1.1) | [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/controlnet/2_pass_pose_worship.png) | [weights](https://huggingface.co/lllyasviel/ControlNet-v1-1) | — (core) | OpenRAIL; review checkpoint | not runtime-tested |
| [scribble](ControlNet-and-Adapters/SD15/scribble.json) | ControlNet v1.1 Scribble | Loose sketch to image (ControlNet file switched to v1.1) | [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/controlnet/controlnet_example.png) | [weights](https://huggingface.co/lllyasviel/ControlNet-v1-1) | — (core) | OpenRAIL; review checkpoint | not runtime-tested |
| [lineart](ControlNet-and-Adapters/SD15/lineart.json) | ControlNet v1.1 LineArt | Clean line art to image (official ControlNet example graph with the LineArt model; feed white-on-black line art) | [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/controlnet/controlnet_example.png) | [weights](https://huggingface.co/lllyasviel/ControlNet-v1-1) | — (core) | OpenRAIL; review checkpoint | not runtime-tested |
| [openpose-plus-scribble](ControlNet-and-Adapters/SD15/openpose-plus-scribble.json) | ControlNet v1.1 OpenPose + Scribble | Chain two ControlNets (pose + scribble) in one generation | [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/controlnet/mixing_controlnets.png) | [weights](https://huggingface.co/lllyasviel/ControlNet-v1-1) | — (core) | OpenRAIL; review checkpoint | not runtime-tested |
| [t2i-adapter-depth](ControlNet-and-Adapters/SD15/t2i-adapter-depth.json) | T2I-Adapter (depth) | Lightweight depth control with a T2I-Adapter | [source](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/controlnet/depth_t2i_adapter.png) | [weights](https://huggingface.co/TencentARC/T2I-Adapter) | — (core) | Apache-2.0 | not runtime-tested |

**Other**

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence | Tested |
|---|---|---|---|---|---|---|---|
| [sdxl-controlnet-canny](ControlNet-and-Adapters/Other/sdxl-controlnet-canny.json) | ControlNet XL (Canny) | SDXL generation following Canny edges of an input picture | [source](https://github.com/CerebriumAI/examples/blob/master/7-image-and-video/1-comfyui/workflow.json) | [weights](https://huggingface.co/lllyasviel/sd_control_collection) | — (core) | Review checkpoint (diffusers SDXL ControlNet) | not runtime-tested |

#### Reference-and-Identity

**InstantID**

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence | Tested |
|---|---|---|---|---|---|---|---|
| [sdxl-basic](Reference-and-Identity/InstantID/sdxl-basic.json) | InstantID | Identity-preserving SDXL image from one face | [source](https://github.com/cubiq/ComfyUI_InstantID/blob/main/examples/InstantID_basic.json) | [weights](https://huggingface.co/InstantX/InstantID) | ComfyUI_InstantID (+ insightface antelopev2) | Apache-2.0; InsightFace models non-commercial | not runtime-tested |
| [sdxl-posed](Reference-and-Identity/InstantID/sdxl-posed.json) | InstantID | Identity with the head pose taken from a second picture | [source](https://github.com/cubiq/ComfyUI_InstantID/blob/main/examples/InstantID_posed.json) | [weights](https://huggingface.co/InstantX/InstantID) | ComfyUI_InstantID (+ insightface antelopev2) | Apache-2.0; InsightFace models non-commercial | not runtime-tested |
| [sdxl-depth](Reference-and-Identity/InstantID/sdxl-depth.json) | InstantID | Identity plus depth ControlNet for body/scene layout | [source](https://github.com/cubiq/ComfyUI_InstantID/blob/main/examples/InstantID_depth.json) | [weights](https://huggingface.co/InstantX/InstantID) | ComfyUI_InstantID, comfyui_controlnet_aux | Apache-2.0; InsightFace models non-commercial | not runtime-tested |
| [sdxl-two-people](Reference-and-Identity/InstantID/sdxl-two-people.json) | InstantID | Two identities in one picture via masks | [source](https://github.com/cubiq/ComfyUI_InstantID/blob/main/examples/InstantID_multi_id.json) | [weights](https://huggingface.co/InstantX/InstantID) | ComfyUI_InstantID, ComfyUI_essentials | Apache-2.0; InsightFace models non-commercial | not runtime-tested |
| [sdxl-ip-adapter](Reference-and-Identity/InstantID/sdxl-ip-adapter.json) | InstantID + IP-Adapter | Identity reinforced with IP-Adapter Plus SDXL | [source](https://github.com/cubiq/ComfyUI_InstantID/blob/main/examples/InstantID_IPAdapter.json) | [weights](https://huggingface.co/InstantX/InstantID) | ComfyUI_InstantID, ComfyUI_IPAdapter_plus | Apache-2.0; InsightFace models non-commercial | not runtime-tested |

**IP-Adapter**

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence | Tested |
|---|---|---|---|---|---|---|---|
| [sd15-simple](Reference-and-Identity/IP-Adapter/sd15-simple.json) | IP-Adapter SD1.5 | Generate from a reference image with the unified loader | [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_simple.json) | [weights](https://huggingface.co/h94/IP-Adapter) | ComfyUI_IPAdapter_plus | Apache-2.0 | not runtime-tested |
| [sd15-plus-advanced](Reference-and-Identity/IP-Adapter/sd15-plus-advanced.json) | IP-Adapter SD1.5 Plus | Explicit model/CLIP-vision loaders with weight and timing controls | [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_advanced.json) | [weights](https://huggingface.co/h94/IP-Adapter) | ComfyUI_IPAdapter_plus | Apache-2.0 | not runtime-tested |
| [sd15-multiple-references](Reference-and-Identity/IP-Adapter/sd15-multiple-references.json) | IP-Adapter SD1.5 Plus | Blend several reference images | [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_combine_embeds.json) | [weights](https://huggingface.co/h94/IP-Adapter) | ComfyUI_IPAdapter_plus | Apache-2.0 | not runtime-tested |
| [sd15-tiled-wide-reference](Reference-and-Identity/IP-Adapter/sd15-tiled-wide-reference.json) | IP-Adapter SD1.5 Plus | Use non-square / wide references without cropping (tiled) | [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_tiled.json) | [weights](https://huggingface.co/h94/IP-Adapter) | ComfyUI_IPAdapter_plus | Apache-2.0 | not runtime-tested |
| [sd15-regional](Reference-and-Identity/IP-Adapter/sd15-regional.json) | IP-Adapter SD1.5 | Different references for different colour-mask regions | [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_regional_conditioning.json) | [weights](https://huggingface.co/h94/IP-Adapter) | ComfyUI_IPAdapter_plus, ComfyUI_essentials | Apache-2.0 | not runtime-tested |
| [sdxl-style-and-composition](Reference-and-Identity/IP-Adapter/sdxl-style-and-composition.json) | IP-Adapter SDXL | Take style from one image and composition from another | [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_style_composition.json) | [weights](https://huggingface.co/h94/IP-Adapter) | ComfyUI_IPAdapter_plus | Apache-2.0 | not runtime-tested |
| [sdxl-precise-composition](Reference-and-Identity/IP-Adapter/sdxl-precise-composition.json) | IP-Adapter SDXL | Precise composition transfer with mid-block style control | [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_precise_composition.json) | [weights](https://huggingface.co/h94/IP-Adapter) | ComfyUI_IPAdapter_plus | Apache-2.0 | not runtime-tested |
| [sdxl-cosxl-edit](Reference-and-Identity/IP-Adapter/sdxl-cosxl-edit.json) | IP-Adapter SDXL + CosXL Edit | Instruction edit steered by a reference image | [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_cosxl_edit.json) | [weights](https://huggingface.co/h94/IP-Adapter) | ComfyUI_IPAdapter_plus | IP-Adapter Apache-2.0; CosXL non-commercial | not runtime-tested |
| [faceid-sd15](Reference-and-Identity/IP-Adapter/faceid-sd15.json) | IP-Adapter FaceID | Identity from one face photo (SD 1.5) | [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_faceid.json) | [weights](https://huggingface.co/h94/IP-Adapter-FaceID) | ComfyUI_IPAdapter_plus (+ insightface) | Non-commercial research (InsightFace) | not runtime-tested |
| [faceid-plus-v2-plus-face](Reference-and-Identity/IP-Adapter/faceid-plus-v2-plus-face.json) | IP-Adapter FaceID Plus v2 | Author-recommended FaceID Plus v2 + Plus Face stack for stronger likeness | [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_ideal_faceid_config.json) | [weights](https://huggingface.co/h94/IP-Adapter-FaceID) | ComfyUI_IPAdapter_plus (+ insightface) | Non-commercial research (InsightFace) | not runtime-tested |
| [faceid-sdxl-portrait](Reference-and-Identity/IP-Adapter/faceid-sdxl-portrait.json) | IP-Adapter FaceID (SDXL) | SDXL portrait from a face photo | [source](https://github.com/cubiq/ComfyUI_IPAdapter_plus/blob/main/examples/ipadapter_portrait.json) | [weights](https://huggingface.co/h94/IP-Adapter-FaceID) | ComfyUI_IPAdapter_plus (+ insightface) | Non-commercial research (InsightFace) | not runtime-tested |

**PhotoMaker**

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence | Tested |
|---|---|---|---|---|---|---|---|
| [sdxl](Reference-and-Identity/PhotoMaker/sdxl.json) | PhotoMaker v1 | Stacked-ID personalisation from several photos of one person | [source](https://github.com/shiimizu/ComfyUI-PhotoMaker-Plus/blob/main/examples/v1-workflow.json) | [weights](https://huggingface.co/TencentARC/PhotoMaker) | ComfyUI-PhotoMaker-Plus, ComfyUI-Custom-Scripts | Apache-2.0 | not runtime-tested |
| [v2-sdxl-simple](Reference-and-Identity/PhotoMaker/v2-sdxl-simple.json) | PhotoMaker v2 | Minimal PhotoMaker v2 personalisation | [source](https://github.com/shiimizu/ComfyUI-PhotoMaker-Plus/blob/main/examples/v2-simple-workflow.json) | [weights](https://huggingface.co/TencentARC/PhotoMaker-V2) | ComfyUI-PhotoMaker-Plus (+ insightface) | Apache-2.0; InsightFace models non-commercial | not runtime-tested |
| [v2-sdxl-styles](Reference-and-Identity/PhotoMaker/v2-sdxl-styles.json) | PhotoMaker v2 | PhotoMaker v2 with style templates and delayed ID merge | [source](https://github.com/shiimizu/ComfyUI-PhotoMaker-Plus/blob/main/examples/v2-workflow.json) | [weights](https://huggingface.co/TencentARC/PhotoMaker-V2) | ComfyUI-PhotoMaker-Plus, ComfyUI-Custom-Scripts (+ insightface) | Apache-2.0; InsightFace models non-commercial | not runtime-tested |
| [v2-sdxl-auto-crop-faces](Reference-and-Identity/PhotoMaker/v2-sdxl-auto-crop-faces.json) | PhotoMaker v2 | Auto-detect and crop faces from input photos first | [source](https://github.com/shiimizu/ComfyUI-PhotoMaker-Plus/blob/main/examples/v2-autodetect-faces-workflow.json) | [weights](https://huggingface.co/TencentARC/PhotoMaker-V2) | ComfyUI-PhotoMaker-Plus, ComfyUI-AutoCropFaces, ComfyUI-Custom-Scripts | Apache-2.0; InsightFace models non-commercial | not runtime-tested |

**PuLID**

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence | Tested |
|---|---|---|---|---|---|---|---|
| [sdxl-simple](Reference-and-Identity/PuLID/sdxl-simple.json) | PuLID (SDXL) | Identity-preserving generation from a face photo | [source](https://github.com/cubiq/PuLID_ComfyUI/blob/main/examples/PuLID_simple.json) | [weights](https://huggingface.co/huchenlei/ipadapter_pulid) | PuLID_ComfyUI (+ insightface, EVA-CLIP) | Apache-2.0; InsightFace models non-commercial | not runtime-tested |
| [sdxl-lightning-4-step](Reference-and-Identity/PuLID/sdxl-lightning-4-step.json) | PuLID (SDXL Lightning) | Fast 4-step identity generation with the SDXL Lightning UNet | [source](https://github.com/cubiq/PuLID_ComfyUI/blob/main/examples/PuLID_4-Step_lightning.json) | [weights](https://huggingface.co/huchenlei/ipadapter_pulid) | PuLID_ComfyUI (+ insightface, EVA-CLIP) | Apache-2.0; InsightFace models non-commercial | not runtime-tested |
| [sdxl-two-people-attention-mask](Reference-and-Identity/PuLID/sdxl-two-people-attention-mask.json) | PuLID (SDXL) | Two identities placed with attention masks | [source](https://github.com/cubiq/PuLID_ComfyUI/blob/main/examples/PuLID_attention_mask.json) | [weights](https://huggingface.co/huchenlei/ipadapter_pulid) | PuLID_ComfyUI (+ insightface, EVA-CLIP) | Apache-2.0; InsightFace models non-commercial | not runtime-tested |
| [sdxl-ip-adapter-style](Reference-and-Identity/PuLID/sdxl-ip-adapter-style.json) | PuLID (SDXL) + IP-Adapter | Identity plus style taken from a reference image | [source](https://github.com/cubiq/PuLID_ComfyUI/blob/main/examples/PuLID_IPAdapter_style_transfer.json) | [weights](https://huggingface.co/huchenlei/ipadapter_pulid) | PuLID_ComfyUI, ComfyUI_IPAdapter_plus | Apache-2.0; InsightFace models non-commercial | not runtime-tested |

**Other**

| Workflow | Model | Purpose | Source | Model download | Custom nodes | Licence | Tested |
|---|---|---|---|---|---|---|---|
| [storymaker-single-portrait](Reference-and-Identity/Other/storymaker-single-portrait.json) | StoryMaker | Keep face, hair and clothing of a masked person in a new scene | [source](https://github.com/tanglaoya321/ComfyUI-StoryMaker/blob/main/workflows/workflow.json) | [weights](https://huggingface.co/RED-AIGC/StoryMaker) | ComfyUI-StoryMaker (+ insightface) | Review StoryMaker terms; InsightFace models non-commercial | not runtime-tested |


### Already covered elsewhere in `01-Image` (skipped as duplicates)

- ControlNet v1.1 Canny: [`sd15-juggernaut-reborn-txt2img-controlnet-canny`](../Image-Generation/ControlNet-Guided/Other/sd15-juggernaut-txt2img-controlnet-canny.json)
- Z-Image ControlNet Union: [`z-image-turbo-txt2img-fp8-aio-controlnet-union`](../Image-Generation/ControlNet-Guided/Other/z-image-turbo-txt2img-fp8-aio-controlnet-union.json)
- LaMa: [`lama-object-remover`](Inpaint-Outpaint-and-Object-Removal/Other/lama-object-remover.json)

### Not available in ComfyUI

No authentic, published ComfyUI workflow was found for these entries, so none was made up:

- SDXL Inpainting 0.1 (diffusers UNet checkpoint) — for SDXL inpainting use the BrushNet SDXL or MAT + Fooocus workflows above
- DiffEdit — no ComfyUI node or workflow
- DragDiffusion — no ComfyUI node or workflow
- DragGAN — GAN-based, no ComfyUI node or workflow
- ControlNet v1.1 Tile — no published example workflow found

See the [main README](../../README.md) for setup steps, requirements and the other categories, or [`00-LIBRARY-INDEX.md`](../../00-LIBRARY-INDEX.md) for the full list of workflows.
