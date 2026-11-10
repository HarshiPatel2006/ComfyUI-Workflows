# Image Editing — ComfyUI workflows

Image-to-image (img2img) and instruction editing: single- and multi-image edits, inpainting, outpainting, object removal, background removal, outfit and pose changes, sketch-to-image and compositing tools.

| Subfolder | What is inside | Workflows |
|---|---|---|
| [`Background-Removal/`](Background-Removal) | Background removal and segmentation | 5 |
| [`Character-Outfit-and-Pose/`](Character-Outfit-and-Pose) | Outfit transfer, pose and character edits | 12 |
| [`Compositing-and-Image-Tools/`](Compositing-and-Image-Tools) | Crop, compose, paint, stitch and other image tools | 15 |
| [`Inpaint-Outpaint-and-Object-Removal/`](Inpaint-Outpaint-and-Object-Removal) | Inpainting, outpainting and object removal | 16 |
| [`Multi-Image-Composition/`](Multi-Image-Composition) | Multi-image edits and composition | 22 |
| [`Single-Image-Edit/`](Single-Image-Edit) | Instruction-based single-image editing (img2img) | 34 |
| [`Sketch-and-3D-to-Image/`](Sketch-and-3D-to-Image) | Sketch-to-image and 3D-render-to-image | 9 |

## Workflows (113)

### Background removal and segmentation

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [birefnet-remove-background](Background-Removal/birefnet-remove-background.json) | Remove Background | `birefnet.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-remove-background](Background-Removal/qwen-image-2.1-remove-background.json) | Remove Background | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [sam3-remove-background-segment-crop-object](Background-Removal/sam3-remove-background-segment-crop-object.json) | Remove Background (Segment + Crop Object) | — | ComfyUI-RMBG |
| [utility-remove-background-from-transparent-items](Background-Removal/utility-remove-background-from-transparent-items.json) | Remove Background from Transparent Items | — | ComfyUI-RMBG |
| [utility-remove-background](Background-Removal/utility-remove-background.json) | Remove Background | — | ComfyUI-RMBG, ComfyUI_LayerStyle, rgthree-comfy |

### Outfit transfer, pose and character edits

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [flux-2-klein-9b-character-turnaround-sheet-from-one-image](Character-Outfit-and-Pose/flux-2-klein-9b-character-turnaround-sheet-from-one-image.json) | Character Turnaround Sheet from One Image | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-character-sheet](Character-Outfit-and-Pose/flux-3-klein-character-sheet.json) | Character Sheet | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-outfit-change](Character-Outfit-and-Pose/flux-3-klein-outfit-change.json) | Outfit Change | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [krea-2-outfit-change-outfit-lora](Character-Outfit-and-Pose/krea-2-outfit-change-outfit-lora.json) | Outfit Change + Outfit LoRA | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [krea-2-outfit-transfer-v2](Character-Outfit-and-Pose/krea-2-outfit-transfer-v2.json) | Outfit Transfer v2 | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [qwen-image-2.1-character-sheet](Character-Outfit-and-Pose/qwen-image-2.1-character-sheet.json) | Character Sheet | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-outfit-change-turbo](Character-Outfit-and-Pose/qwen-image-2.1-outfit-change-turbo.json) | Outfit Change — Turbo | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma |
| [qwen-image-2.1-outfit-change](Character-Outfit-and-Pose/qwen-image-2.1-outfit-change.json) | Outfit Change | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-pose-from-a-picture](Character-Outfit-and-Pose/qwen-image-2.1-pose-from-a-picture.json) | Pose from a Picture | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-character-sheet-ep41](Character-Outfit-and-Pose/flux-2-klein-9b-character-sheet-ep41.json) | Flux Klein - Character Sheet from One Picture (Ep41) | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [p-h3-image-character-sheet](Character-Outfit-and-Pose/p-h3-image-character-sheet.json) | P-H3 Image - Character Sheet (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [p-h3-image-outfit-from-second-picture](Character-Outfit-and-Pose/p-h3-image-outfit-from-second-picture.json) | P-H3 Image - Outfit from a Second Picture (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |

### Crop, compose, paint, stitch and other image tools

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [pixaroma-nodes-3d-builder-ep11](Compositing-and-Image-Tools/pixaroma-nodes-3d-builder-ep11.json) | 3D Builder (Ep11) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-3d-builder-ep13](Compositing-and-Image-Tools/pixaroma-nodes-3d-builder-ep13.json) | 3D Builder (Ep13) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-combine-join-two-images](Compositing-and-Image-Tools/pixaroma-nodes-combine-join-two-images.json) | Combine — Join Two Images | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-crop-ep11](Compositing-and-Image-Tools/pixaroma-nodes-crop-ep11.json) | Crop (Ep11) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-crop-ep13](Compositing-and-Image-Tools/pixaroma-nodes-crop-ep13.json) | Crop (Ep13) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-image-composer-ep11](Compositing-and-Image-Tools/pixaroma-nodes-image-composer-ep11.json) | Image Composer (Ep11) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-image-composer-ep13](Compositing-and-Image-Tools/pixaroma-nodes-image-composer-ep13.json) | Image Composer (Ep13) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-paint-ep11](Compositing-and-Image-Tools/pixaroma-nodes-paint-ep11.json) | Paint (Ep11) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-paint-ep13](Compositing-and-Image-Tools/pixaroma-nodes-paint-ep13.json) | Paint (Ep13) | — | ComfyUI-Pixaroma |
| [utility-image-blend](Compositing-and-Image-Tools/utility-image-blend.json) | Image Blend | — | ComfyUI-RMBG, ComfyUI_LayerStyle |
| [utility-image-combiner-for-transparent-items](Compositing-and-Image-Tools/utility-image-combiner-for-transparent-items.json) | Image Combiner for Transparent Items | — | ComfyUI-RMBG |
| [utility-image-combiner](Compositing-and-Image-Tools/utility-image-combiner.json) | Image Combiner | — | ComfyUI-RMBG |
| [utility-image-scale](Compositing-and-Image-Tools/utility-image-scale.json) | Image Scale | — | ComfyUI-KJNodes |
| [utility-image-stitch](Compositing-and-Image-Tools/utility-image-stitch.json) | Image Stitch | — | ComfyUI-RMBG, rgthree-comfy |
| [utility-image-transformation](Compositing-and-Image-Tools/utility-image-transformation.json) | Image Transformation | — | ComfyUI_LayerStyle, rgthree-comfy |

### Inpainting, outpainting and object removal

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [flux-2-klein-4b-fp8-distilled-inpaint](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-4b-fp8-distilled-inpaint.json) | Inpaint | `flux-2-klein-4b-fp8.safetensors`, `qwen_3_4b.safetensors`, `flux2-vae.safetensors` | ComfyUI-Inpaint-CropAndStitch, rgthree-comfy |
| [flux-2-klein-9b-fp8-distilled-inpaint](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-fp8-distilled-inpaint.json) | Inpaint | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Inpaint-CropAndStitch, rgthree-comfy |
| [flux-2-klein-9b-fp8-distilled-paint-guided-edit](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-fp8-distilled-paint-guided-edit.json) | Paint-Guided Edit | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-fp8-inpaint-ep22](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-fp8-inpaint-ep22.json) | Inpaint (Ep22) | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-int8-inpaint](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-int8-inpaint.json) | Inpaint | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-kv-fp8-inpaint](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-kv-fp8-inpaint.json) | Inpaint | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | ComfyUI-Inpaint-CropAndStitch, rgthree-comfy |
| [flux-2-klein-9b-kv-fp8-outpaint-custom-ratio](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-kv-fp8-outpaint-custom-ratio.json) | Outpaint (Custom Ratio) | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | ComfyUI-KJNodes, rgthree-comfy |
| [flux-2-klein-9b-outpaint](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-outpaint.json) | Outpaint | `flux-2-klein-9b-int8-convrot.safetensors`, `pixaoutpaint.safetensors`, `qwen_3_8b_fp8mixed.safetensors` +1 more | ComfyUI-Pixaroma |
| [flux-2-klein-9b-paint-to-image](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-paint-to-image.json) | Paint to Image | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-edit-inside-a-box](Inpaint-Outpaint-and-Object-Removal/flux-3-klein-edit-inside-a-box.json) | Edit inside a Box | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-outpaint](Inpaint-Outpaint-and-Object-Removal/flux-3-klein-outpaint.json) | Outpaint | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` +1 more | ComfyUI-Pixaroma |
| [lama-object-remover](Inpaint-Outpaint-and-Object-Removal/lama-object-remover.json) | Object Remover | — | ComfyUI-RMBG |
| [qwen-image-2.1-inpaint](Inpaint-Outpaint-and-Object-Removal/qwen-image-2.1-inpaint.json) | Inpaint | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-outpaint](Inpaint-Outpaint-and-Object-Removal/qwen-image-2.1-outpaint.json) | Outpaint | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma |
| [p-h3-image-edit-inside-box](Inpaint-Outpaint-and-Object-Removal/p-h3-image-edit-inside-box.json) | P-H3 Image - Edit inside a Box (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [p-h3-image-outpaint](Inpaint-Outpaint-and-Object-Removal/p-h3-image-outpaint.json) | P-H3 Image - Outpaint (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |

### Multi-image edits and composition

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [flux-2-klein-4b-fp8-distilled-multi-image-edit-2-images](Multi-Image-Composition/flux-2-klein-4b-fp8-distilled-multi-image-edit-2-images.json) | Multi-Image Edit — 2 Images | `flux-2-klein-4b-fp8.safetensors`, `qwen_3_4b.safetensors`, `flux2-vae.safetensors` | Core only |
| [flux-2-klein-9b-fp8-distilled-multi-image-edit-2-images](Multi-Image-Composition/flux-2-klein-9b-fp8-distilled-multi-image-edit-2-images.json) | Multi-Image Edit — 2 Images | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | Core only |
| [flux-2-klein-9b-image-composer-to-image](Multi-Image-Composition/flux-2-klein-9b-image-composer-to-image.json) | Image Composer to Image | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-kv-fp8-image-blend](Multi-Image-Composition/flux-2-klein-9b-kv-fp8-image-blend.json) | Image Blend | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | ComfyUI-RMBG, ComfyUI_LayerStyle, rgthree-comfy |
| [flux-2-klein-9b-kv-fp8-multi-image-edit-2-images](Multi-Image-Composition/flux-2-klein-9b-kv-fp8-multi-image-edit-2-images.json) | Multi-Image Edit — 2 Images | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | Core only |
| [flux-2-klein-9b-kv-fp8-multi-image-edit-3-images](Multi-Image-Composition/flux-2-klein-9b-kv-fp8-multi-image-edit-3-images.json) | Multi-Image Edit — 3 Images | `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors`, `flux2-vae.safetensors` | Core only |
| [flux-2-klein-9b-kv-fp8-multi-image-edit-4-images](Multi-Image-Composition/flux-2-klein-9b-kv-fp8-multi-image-edit-4-images.json) | Multi-Image Edit — 4 Images | `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors`, `flux2-vae.safetensors` | Core only |
| [flux-3-klein-character-in-a-scene](Multi-Image-Composition/flux-3-klein-character-in-a-scene.json) | Character in a Scene | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-group-photo](Multi-Image-Composition/flux-3-klein-group-photo.json) | Group Photo | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-logo-on-a-product](Multi-Image-Composition/flux-3-klein-logo-on-a-product.json) | Logo on a Product | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-product-ad](Multi-Image-Composition/flux-3-klein-product-ad.json) | Product Ad | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-product-ad-from-two-pictures](Multi-Image-Composition/ming-image-0.1-product-ad-from-two-pictures.json) | Product Ad from Two Pictures | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-character-in-a-scene](Multi-Image-Composition/qwen-image-2.1-character-in-a-scene.json) | Character in a Scene | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-logo-on-a-product](Multi-Image-Composition/qwen-image-2.1-logo-on-a-product.json) | Logo on a Product | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-multi-image-edit-2-images-prompt-enhancer](Multi-Image-Composition/qwen-image-2.1-multi-image-edit-2-images-prompt-enhancer.json) | Multi-Image Edit — 2 Images + Prompt Enhancer | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-multi-image-edit-3-images](Multi-Image-Composition/qwen-image-2.1-multi-image-edit-3-images.json) | Multi-Image Edit — 3 Images | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-multi-image-edit-4-images](Multi-Image-Composition/qwen-image-2.1-multi-image-edit-4-images.json) | Multi-Image Edit — 4 Images | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-multi-image-edit-group-photo-from-6-images](Multi-Image-Composition/qwen-image-2.1-multi-image-edit-group-photo-from-6-images.json) | Multi-Image Edit — Group Photo from 6 Images | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [p-h3-image-character-in-a-scene](Multi-Image-Composition/p-h3-image-character-in-a-scene.json) | P-H3 Image - Character in a Scene (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [p-h3-image-logo-on-product](Multi-Image-Composition/p-h3-image-logo-on-product.json) | P-H3 Image - Logo on a Product (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [p-h3-image-group-photo](Multi-Image-Composition/p-h3-image-group-photo.json) | P-H3 Image - Group Photo (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [p-h3-image-style-from-second-picture](Multi-Image-Composition/p-h3-image-style-from-second-picture.json) | P-H3 Image - Style from a Second Picture (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `minimax_h3_style_transfer_v1.0_r64.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |

### Instruction-based single-image editing (img2img)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [boogu-edit-one-image-edit](Single-Image-Edit/boogu-edit-one-image-edit.json) | One Image Edit | `qwen3vl_8b_fp8_scaled.safetensors`, `ae.safetensors`, `boogu_image_edit_turbo_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-4b-fp8-distilled-one-image-edit](Single-Image-Edit/flux-2-klein-4b-fp8-distilled-one-image-edit.json) | One Image Edit | `flux-2-klein-4b-fp8.safetensors`, `qwen_3_4b.safetensors`, `flux2-vae.safetensors` | rgthree-comfy |
| [flux-2-klein-9b-fp8-distilled-one-image-edit](Single-Image-Edit/flux-2-klein-9b-fp8-distilled-one-image-edit.json) | One Image Edit | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | rgthree-comfy |
| [flux-2-klein-9b-int8-one-image-edit](Single-Image-Edit/flux-2-klein-9b-int8-one-image-edit.json) | One Image Edit | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-kv-fp8-one-image-edit-custom-ratio](Single-Image-Edit/flux-2-klein-9b-kv-fp8-one-image-edit-custom-ratio.json) | One Image Edit (Custom Ratio) | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | rgthree-comfy |
| [flux-2-klein-9b-kv-fp8-one-image-edit-same-ratio](Single-Image-Edit/flux-2-klein-9b-kv-fp8-one-image-edit-same-ratio.json) | One Image Edit (Same Ratio) | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-kv-fp8.safetensors` | rgthree-comfy |
| [flux-2-klein-9b-one-image-edit-v1](Single-Image-Edit/flux-2-klein-9b-one-image-edit-v1.json) | One Image Edit V1 | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-image-edit-v2-notify-and-switch](Single-Image-Edit/flux-2-klein-9b-one-image-edit-v2-notify-and-switch.json) | One Image Edit V2 + Notify and Switch | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-image-edit-v3-keep-filename-save-to-dated-folder](Single-Image-Edit/flux-2-klein-9b-one-image-edit-v3-keep-filename-save-to-dated-folder.json) | One Image Edit V3 + Keep Filename + Save to Dated Folder | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-image-many-edits](Single-Image-Edit/flux-2-klein-9b-one-image-many-edits.json) | One Image, Many Edits | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-image-prompts-from-list](Single-Image-Edit/flux-2-klein-9b-one-image-prompts-from-list.json) | One Image, Prompts from List | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-edit-text-in-a-picture](Single-Image-Edit/flux-3-klein-edit-text-in-a-picture.json) | Edit Text in a Picture | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-one-image-edit](Single-Image-Edit/flux-3-klein-one-image-edit.json) | One Image Edit | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-relight-and-seasons](Single-Image-Edit/flux-3-klein-relight-and-seasons.json) | Relight and Seasons | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-restore-and-colorize](Single-Image-Edit/flux-3-klein-restore-and-colorize.json) | Restore and Colorize | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-3-klein-restyle](Single-Image-Edit/flux-3-klein-restyle.json) | Restyle | `flux3-image-klein-int8-convrot.safetensors`, `qwen3vl_4b_int8_convrot.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [krea-2-edit-lora-character-and-background](Single-Image-Edit/krea-2-edit-lora-character-and-background.json) | Edit LoRA — Character and Background | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [krea-2-edit-lora-custom-ratio](Single-Image-Edit/krea-2-edit-lora-custom-ratio.json) | Edit LoRA — Custom Ratio | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [krea-2-edit-lora](Single-Image-Edit/krea-2-edit-lora.json) | Edit LoRA | `krea2_turbo_int8_convrot.safetensors`, `qwen3-vl-4b-heretic_int8.safetensors`, `qwen_image_vae.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [ming-image-0.1-one-image-edit](Single-Image-Edit/ming-image-0.1-one-image-edit.json) | One Image Edit | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-social-media-pack-from-one-image](Single-Image-Edit/ming-image-0.1-social-media-pack-from-one-image.json) | Social Media Pack from One Image | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [minimax-h3-one-image-edit-single-frame](Single-Image-Edit/minimax-h3-one-image-edit-single-frame.json) | One Image Edit (Single Frame) | `qwen3vl_32b_minimax_h3_nvfp4_awq.safetensors`, `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `minimax_h3_video_vae_fp16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-one-image-edit-consistency-lora](Single-Image-Edit/qwen-image-2.1-one-image-edit-consistency-lora.json) | One Image Edit + Consistency LoRA | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma |
| [qwen-image-2.1-one-image-edit-low-vram](Single-Image-Edit/qwen-image-2.1-one-image-edit-low-vram.json) | One Image Edit — Low VRAM | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-one-image-edit-prompt-enhancer](Single-Image-Edit/qwen-image-2.1-one-image-edit-prompt-enhancer.json) | One Image Edit + Prompt Enhancer | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-one-image-edit-turbo](Single-Image-Edit/qwen-image-2.1-one-image-edit-turbo.json) | One Image Edit — Turbo | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma |
| [qwen-image-2.1-one-image-edit](Single-Image-Edit/qwen-image-2.1-one-image-edit.json) | One Image Edit | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [sd15-juggernaut-reborn-img2img](Single-Image-Edit/sd15-juggernaut-reborn-img2img.json) | Image to Image | `juggernaut_reborn.safetensors` | Core only |
| [moss-image-edit-text-in-a-picture](Single-Image-Edit/moss-image-edit-text-in-a-picture.json) | MOSS Image - Same Picture, New Words (Ep40) | `moss_image_sft_int8_convrot.safetensors`, `qwen3.5_9b_w4a8_gptq.safetensors`, `flux2-vae_small.safetensors` | ComfyUI-Pixaroma |
| [p-h3-image-edit-new-place](Single-Image-Edit/p-h3-image-edit-new-place.json) | P-H3 Image - Image Edit New Place (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [p-h3-image-relight-day-to-night](Single-Image-Edit/p-h3-image-relight-day-to-night.json) | P-H3 Image - Relight Day to Night (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [p-h3-image-edit-text-in-a-picture](Single-Image-Edit/p-h3-image-edit-text-in-a-picture.json) | P-H3 Image - Edit Text in a Picture (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [p-h3-image-restyle-picture](Single-Image-Edit/p-h3-image-restyle-picture.json) | P-H3 Image - Restyle a Picture (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |
| [p-h3-image-restore-and-colorize](Single-Image-Edit/p-h3-image-restore-and-colorize.json) | P-H3 Image - Restore and Colorize (Ep42) | `minimax_h3_fl2va_pruned_int8_convrot.safetensors`, `p-h3-image_lora_bf16.safetensors`, `p-h3-image_text_encoder_int8_convrot.safetensors`, `p-h3-image_vae_int8_convrot.safetensors` | ComfyUI-Pixaroma |

### Sketch-to-image and 3D-render-to-image

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [flux-2-klein-9b-3d-model-to-image-ep33](Sketch-and-3D-to-Image/flux-2-klein-9b-3d-model-to-image-ep33.json) | 3D Model to Image (Ep33) | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-3d-model-to-image-keep-the-angle-ep33](Sketch-and-3D-to-Image/flux-2-klein-9b-3d-model-to-image-keep-the-angle-ep33.json) | 3D Model to Image — Keep the Angle (Ep33) | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-3d-model-to-image-keep-the-angle-ep34](Sketch-and-3D-to-Image/flux-2-klein-9b-3d-model-to-image-keep-the-angle-ep34.json) | 3D Model to Image — Keep the Angle (Ep34) | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-3d-model-to-image](Sketch-and-3D-to-Image/flux-2-klein-9b-3d-model-to-image.json) | 3D Model to Image | `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`, `flux-2-klein-9b-int8-convrot.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-3d-scene-builder-to-image](Sketch-and-3D-to-Image/flux-2-klein-9b-3d-scene-builder-to-image.json) | 3D Scene Builder to Image | `flux2-vae.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux-2-klein-9b-fp8mixed.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-restyle-a-design-to-3d](Sketch-and-3D-to-Image/ming-image-0.1-restyle-a-design-to-3d.json) | Restyle a Design to 3D | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [ming-image-0.1-sketch-to-photo](Sketch-and-3D-to-Image/ming-image-0.1-sketch-to-photo.json) | Sketch to Photo | `ming_image_0.1_design_int8_convrot.safetensors`, `ming_image_0.1_ling_mini_2.0_int8_convrot.safetensors`, `ming_image_vae_bf16.safetensors` | ComfyUI-Pixaroma |
| [qwen-image-2.1-sketch-to-image-consistency-lora](Sketch-and-3D-to-Image/qwen-image-2.1-sketch-to-image-consistency-lora.json) | Sketch to Image + Consistency LoRA | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` +1 more | ComfyUI-Pixaroma |
| [qwen-image-2.1-sketch-to-image](Sketch-and-3D-to-Image/qwen-image-2.1-sketch-to-image.json) | Sketch to Image | `qwen_image_2.1_int8_convrot.safetensors`, `qwen3vl_8b_int8_convrot.safetensors`, `qwen_image_2.1_vae_bf16.safetensors` | ComfyUI-Pixaroma |

See the [main README](../README.md) for setup steps, requirements and the other categories, or [`00-LIBRARY-INDEX.md`](../00-LIBRARY-INDEX.md) for the full list of workflows.
