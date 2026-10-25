# Image Editing — ComfyUI workflows

Image-to-image (img2img) and instruction editing: single- and multi-image edits, inpainting, outpainting, object removal, background removal, outfit and pose changes, sketch-to-image and compositing tools.

| Subfolder | What is inside | Workflows |
|---|---|---|
| [`Background-Removal/`](Background-Removal) | Background removal and segmentation | 5 |
| [`Character-Outfit-and-Pose/`](Character-Outfit-and-Pose) | Outfit transfer, pose and character edits | 9 |
| [`Compositing-and-Image-Tools/`](Compositing-and-Image-Tools) | Crop, compose, paint, stitch and other image tools | 15 |
| [`Inpaint-Outpaint-and-Object-Removal/`](Inpaint-Outpaint-and-Object-Removal) | Inpainting, outpainting and object removal | 14 |
| [`Multi-Image-Composition/`](Multi-Image-Composition) | Multi-image edits and composition | 18 |
| [`Single-Image-Edit/`](Single-Image-Edit) | Instruction-based single-image editing (img2img) | 28 |
| [`Sketch-and-3D-to-Image/`](Sketch-and-3D-to-Image) | Sketch-to-image and 3D-render-to-image | 9 |

## Workflows (98)

### Background removal and segmentation

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [birefnet-remove-background](Background-Removal/birefnet-remove-background.json) | Remove Background | ComfyUI-Pixaroma |
| [qwen-image-2.1-remove-background](Background-Removal/qwen-image-2.1-remove-background.json) | Remove Background | ComfyUI-Pixaroma |
| [sam3-remove-background-segment-crop-object](Background-Removal/sam3-remove-background-segment-crop-object.json) | Remove Background (Segment + Crop Object) | ComfyUI-RMBG |
| [utility-remove-background-from-transparent-items](Background-Removal/utility-remove-background-from-transparent-items.json) | Remove Background from Transparent Items | ComfyUI-RMBG |
| [utility-remove-background](Background-Removal/utility-remove-background.json) | Remove Background | ComfyUI-RMBG, ComfyUI_LayerStyle, rgthree-comfy |

### Outfit transfer, pose and character edits

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [flux-2-klein-9b-character-turnaround-sheet-from-one-image](Character-Outfit-and-Pose/flux-2-klein-9b-character-turnaround-sheet-from-one-image.json) | Character Turnaround Sheet from One Image | ComfyUI-Pixaroma |
| [flux-3-klein-character-sheet](Character-Outfit-and-Pose/flux-3-klein-character-sheet.json) | Character Sheet | ComfyUI-Pixaroma |
| [flux-3-klein-outfit-change](Character-Outfit-and-Pose/flux-3-klein-outfit-change.json) | Outfit Change | ComfyUI-Pixaroma |
| [krea-2-outfit-change-outfit-lora](Character-Outfit-and-Pose/krea-2-outfit-change-outfit-lora.json) | Outfit Change + Outfit LoRA | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [krea-2-outfit-transfer-v2](Character-Outfit-and-Pose/krea-2-outfit-transfer-v2.json) | Outfit Transfer v2 | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [qwen-image-2.1-character-sheet](Character-Outfit-and-Pose/qwen-image-2.1-character-sheet.json) | Character Sheet | ComfyUI-Pixaroma |
| [qwen-image-2.1-outfit-change-turbo](Character-Outfit-and-Pose/qwen-image-2.1-outfit-change-turbo.json) | Outfit Change — Turbo | ComfyUI-Pixaroma |
| [qwen-image-2.1-outfit-change](Character-Outfit-and-Pose/qwen-image-2.1-outfit-change.json) | Outfit Change | ComfyUI-Pixaroma |
| [qwen-image-2.1-pose-from-a-picture](Character-Outfit-and-Pose/qwen-image-2.1-pose-from-a-picture.json) | Pose from a Picture | ComfyUI-Pixaroma |

### Crop, compose, paint, stitch and other image tools

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [pixaroma-nodes-3d-builder-ep11](Compositing-and-Image-Tools/pixaroma-nodes-3d-builder-ep11.json) | 3D Builder (Ep11) | ComfyUI-Pixaroma |
| [pixaroma-nodes-3d-builder-ep13](Compositing-and-Image-Tools/pixaroma-nodes-3d-builder-ep13.json) | 3D Builder (Ep13) | ComfyUI-Pixaroma |
| [pixaroma-nodes-combine-join-two-images](Compositing-and-Image-Tools/pixaroma-nodes-combine-join-two-images.json) | Combine — Join Two Images | ComfyUI-Pixaroma |
| [pixaroma-nodes-crop-ep11](Compositing-and-Image-Tools/pixaroma-nodes-crop-ep11.json) | Crop (Ep11) | ComfyUI-Pixaroma |
| [pixaroma-nodes-crop-ep13](Compositing-and-Image-Tools/pixaroma-nodes-crop-ep13.json) | Crop (Ep13) | ComfyUI-Pixaroma |
| [pixaroma-nodes-image-composer-ep11](Compositing-and-Image-Tools/pixaroma-nodes-image-composer-ep11.json) | Image Composer (Ep11) | ComfyUI-Pixaroma |
| [pixaroma-nodes-image-composer-ep13](Compositing-and-Image-Tools/pixaroma-nodes-image-composer-ep13.json) | Image Composer (Ep13) | ComfyUI-Pixaroma |
| [pixaroma-nodes-paint-ep11](Compositing-and-Image-Tools/pixaroma-nodes-paint-ep11.json) | Paint (Ep11) | ComfyUI-Pixaroma |
| [pixaroma-nodes-paint-ep13](Compositing-and-Image-Tools/pixaroma-nodes-paint-ep13.json) | Paint (Ep13) | ComfyUI-Pixaroma |
| [utility-image-blend](Compositing-and-Image-Tools/utility-image-blend.json) | Image Blend | ComfyUI-RMBG, ComfyUI_LayerStyle |
| [utility-image-combiner-for-transparent-items](Compositing-and-Image-Tools/utility-image-combiner-for-transparent-items.json) | Image Combiner for Transparent Items | ComfyUI-RMBG |
| [utility-image-combiner](Compositing-and-Image-Tools/utility-image-combiner.json) | Image Combiner | ComfyUI-RMBG |
| [utility-image-scale](Compositing-and-Image-Tools/utility-image-scale.json) | Image Scale | ComfyUI-KJNodes |
| [utility-image-stitch](Compositing-and-Image-Tools/utility-image-stitch.json) | Image Stitch | ComfyUI-RMBG, rgthree-comfy |
| [utility-image-transformation](Compositing-and-Image-Tools/utility-image-transformation.json) | Image Transformation | ComfyUI_LayerStyle, rgthree-comfy |

### Inpainting, outpainting and object removal

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [flux-2-klein-4b-fp8-distilled-inpaint](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-4b-fp8-distilled-inpaint.json) | Inpaint | ComfyUI-Inpaint-CropAndStitch, rgthree-comfy |
| [flux-2-klein-9b-fp8-distilled-inpaint](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-fp8-distilled-inpaint.json) | Inpaint | ComfyUI-Inpaint-CropAndStitch, rgthree-comfy |
| [flux-2-klein-9b-fp8-distilled-paint-guided-edit](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-fp8-distilled-paint-guided-edit.json) | Paint-Guided Edit | ComfyUI-Pixaroma |
| [flux-2-klein-9b-fp8-inpaint-ep22](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-fp8-inpaint-ep22.json) | Inpaint (Ep22) | ComfyUI-Pixaroma |
| [flux-2-klein-9b-int8-inpaint](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-int8-inpaint.json) | Inpaint | ComfyUI-Pixaroma |
| [flux-2-klein-9b-kv-fp8-inpaint](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-kv-fp8-inpaint.json) | Inpaint | ComfyUI-Inpaint-CropAndStitch, rgthree-comfy |
| [flux-2-klein-9b-kv-fp8-outpaint-custom-ratio](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-kv-fp8-outpaint-custom-ratio.json) | Outpaint (Custom Ratio) | ComfyUI-KJNodes, rgthree-comfy |
| [flux-2-klein-9b-outpaint](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-outpaint.json) | Outpaint | ComfyUI-Pixaroma |
| [flux-2-klein-9b-paint-to-image](Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-paint-to-image.json) | Paint to Image | ComfyUI-Pixaroma |
| [flux-3-klein-edit-inside-a-box](Inpaint-Outpaint-and-Object-Removal/flux-3-klein-edit-inside-a-box.json) | Edit inside a Box | ComfyUI-Pixaroma |
| [flux-3-klein-outpaint](Inpaint-Outpaint-and-Object-Removal/flux-3-klein-outpaint.json) | Outpaint | ComfyUI-Pixaroma |
| [lama-object-remover](Inpaint-Outpaint-and-Object-Removal/lama-object-remover.json) | Object Remover | ComfyUI-RMBG |
| [qwen-image-2.1-inpaint](Inpaint-Outpaint-and-Object-Removal/qwen-image-2.1-inpaint.json) | Inpaint | ComfyUI-Pixaroma |
| [qwen-image-2.1-outpaint](Inpaint-Outpaint-and-Object-Removal/qwen-image-2.1-outpaint.json) | Outpaint | ComfyUI-Pixaroma |

### Multi-image edits and composition

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [flux-2-klein-4b-fp8-distilled-multi-image-edit-2-images](Multi-Image-Composition/flux-2-klein-4b-fp8-distilled-multi-image-edit-2-images.json) | Multi-Image Edit — 2 Images | Core only |
| [flux-2-klein-9b-fp8-distilled-multi-image-edit-2-images](Multi-Image-Composition/flux-2-klein-9b-fp8-distilled-multi-image-edit-2-images.json) | Multi-Image Edit — 2 Images | Core only |
| [flux-2-klein-9b-image-composer-to-image](Multi-Image-Composition/flux-2-klein-9b-image-composer-to-image.json) | Image Composer to Image | ComfyUI-Pixaroma |
| [flux-2-klein-9b-kv-fp8-image-blend](Multi-Image-Composition/flux-2-klein-9b-kv-fp8-image-blend.json) | Image Blend | ComfyUI-RMBG, ComfyUI_LayerStyle, rgthree-comfy |
| [flux-2-klein-9b-kv-fp8-multi-image-edit-2-images](Multi-Image-Composition/flux-2-klein-9b-kv-fp8-multi-image-edit-2-images.json) | Multi-Image Edit — 2 Images | Core only |
| [flux-2-klein-9b-kv-fp8-multi-image-edit-3-images](Multi-Image-Composition/flux-2-klein-9b-kv-fp8-multi-image-edit-3-images.json) | Multi-Image Edit — 3 Images | Core only |
| [flux-2-klein-9b-kv-fp8-multi-image-edit-4-images](Multi-Image-Composition/flux-2-klein-9b-kv-fp8-multi-image-edit-4-images.json) | Multi-Image Edit — 4 Images | Core only |
| [flux-3-klein-character-in-a-scene](Multi-Image-Composition/flux-3-klein-character-in-a-scene.json) | Character in a Scene | ComfyUI-Pixaroma |
| [flux-3-klein-group-photo](Multi-Image-Composition/flux-3-klein-group-photo.json) | Group Photo | ComfyUI-Pixaroma |
| [flux-3-klein-logo-on-a-product](Multi-Image-Composition/flux-3-klein-logo-on-a-product.json) | Logo on a Product | ComfyUI-Pixaroma |
| [flux-3-klein-product-ad](Multi-Image-Composition/flux-3-klein-product-ad.json) | Product Ad | ComfyUI-Pixaroma |
| [ming-image-0.1-product-ad-from-two-pictures](Multi-Image-Composition/ming-image-0.1-product-ad-from-two-pictures.json) | Product Ad from Two Pictures | ComfyUI-Pixaroma |
| [qwen-image-2.1-character-in-a-scene](Multi-Image-Composition/qwen-image-2.1-character-in-a-scene.json) | Character in a Scene | ComfyUI-Pixaroma |
| [qwen-image-2.1-logo-on-a-product](Multi-Image-Composition/qwen-image-2.1-logo-on-a-product.json) | Logo on a Product | ComfyUI-Pixaroma |
| [qwen-image-2.1-multi-image-edit-2-images-prompt-enhancer](Multi-Image-Composition/qwen-image-2.1-multi-image-edit-2-images-prompt-enhancer.json) | Multi-Image Edit — 2 Images + Prompt Enhancer | ComfyUI-Pixaroma |
| [qwen-image-2.1-multi-image-edit-3-images](Multi-Image-Composition/qwen-image-2.1-multi-image-edit-3-images.json) | Multi-Image Edit — 3 Images | ComfyUI-Pixaroma |
| [qwen-image-2.1-multi-image-edit-4-images](Multi-Image-Composition/qwen-image-2.1-multi-image-edit-4-images.json) | Multi-Image Edit — 4 Images | ComfyUI-Pixaroma |
| [qwen-image-2.1-multi-image-edit-group-photo-from-6-images](Multi-Image-Composition/qwen-image-2.1-multi-image-edit-group-photo-from-6-images.json) | Multi-Image Edit — Group Photo from 6 Images | ComfyUI-Pixaroma |

### Instruction-based single-image editing (img2img)

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [boogu-edit-one-image-edit](Single-Image-Edit/boogu-edit-one-image-edit.json) | One Image Edit | ComfyUI-Pixaroma |
| [flux-2-klein-4b-fp8-distilled-one-image-edit](Single-Image-Edit/flux-2-klein-4b-fp8-distilled-one-image-edit.json) | One Image Edit | rgthree-comfy |
| [flux-2-klein-9b-fp8-distilled-one-image-edit](Single-Image-Edit/flux-2-klein-9b-fp8-distilled-one-image-edit.json) | One Image Edit | rgthree-comfy |
| [flux-2-klein-9b-int8-one-image-edit](Single-Image-Edit/flux-2-klein-9b-int8-one-image-edit.json) | One Image Edit | ComfyUI-Pixaroma |
| [flux-2-klein-9b-kv-fp8-one-image-edit-custom-ratio](Single-Image-Edit/flux-2-klein-9b-kv-fp8-one-image-edit-custom-ratio.json) | One Image Edit (Custom Ratio) | rgthree-comfy |
| [flux-2-klein-9b-kv-fp8-one-image-edit-same-ratio](Single-Image-Edit/flux-2-klein-9b-kv-fp8-one-image-edit-same-ratio.json) | One Image Edit (Same Ratio) | rgthree-comfy |
| [flux-2-klein-9b-one-image-edit-v1](Single-Image-Edit/flux-2-klein-9b-one-image-edit-v1.json) | One Image Edit V1 | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-image-edit-v2-notify-and-switch](Single-Image-Edit/flux-2-klein-9b-one-image-edit-v2-notify-and-switch.json) | One Image Edit V2 + Notify and Switch | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-image-edit-v3-keep-filename-save-to-dated-folder](Single-Image-Edit/flux-2-klein-9b-one-image-edit-v3-keep-filename-save-to-dated-folder.json) | One Image Edit V3 + Keep Filename + Save to Dated Folder | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-image-many-edits](Single-Image-Edit/flux-2-klein-9b-one-image-many-edits.json) | One Image, Many Edits | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-image-prompts-from-list](Single-Image-Edit/flux-2-klein-9b-one-image-prompts-from-list.json) | One Image, Prompts from List | ComfyUI-Pixaroma |
| [flux-3-klein-edit-text-in-a-picture](Single-Image-Edit/flux-3-klein-edit-text-in-a-picture.json) | Edit Text in a Picture | ComfyUI-Pixaroma |
| [flux-3-klein-one-image-edit](Single-Image-Edit/flux-3-klein-one-image-edit.json) | One Image Edit | ComfyUI-Pixaroma |
| [flux-3-klein-relight-and-seasons](Single-Image-Edit/flux-3-klein-relight-and-seasons.json) | Relight and Seasons | ComfyUI-Pixaroma |
| [flux-3-klein-restore-and-colorize](Single-Image-Edit/flux-3-klein-restore-and-colorize.json) | Restore and Colorize | ComfyUI-Pixaroma |
| [flux-3-klein-restyle](Single-Image-Edit/flux-3-klein-restyle.json) | Restyle | ComfyUI-Pixaroma |
| [krea-2-edit-lora-character-and-background](Single-Image-Edit/krea-2-edit-lora-character-and-background.json) | Edit LoRA — Character and Background | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [krea-2-edit-lora-custom-ratio](Single-Image-Edit/krea-2-edit-lora-custom-ratio.json) | Edit LoRA — Custom Ratio | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [krea-2-edit-lora](Single-Image-Edit/krea-2-edit-lora.json) | Edit LoRA | ComfyUI-Krea2T-Enhancer, comfyui-krea2edit, ComfyUI-Pixaroma |
| [ming-image-0.1-one-image-edit](Single-Image-Edit/ming-image-0.1-one-image-edit.json) | One Image Edit | ComfyUI-Pixaroma |
| [ming-image-0.1-social-media-pack-from-one-image](Single-Image-Edit/ming-image-0.1-social-media-pack-from-one-image.json) | Social Media Pack from One Image | ComfyUI-Pixaroma |
| [minimax-h3-one-image-edit-single-frame](Single-Image-Edit/minimax-h3-one-image-edit-single-frame.json) | One Image Edit (Single Frame) | ComfyUI-Pixaroma |
| [qwen-image-2.1-one-image-edit-consistency-lora](Single-Image-Edit/qwen-image-2.1-one-image-edit-consistency-lora.json) | One Image Edit + Consistency LoRA | ComfyUI-Pixaroma |
| [qwen-image-2.1-one-image-edit-low-vram](Single-Image-Edit/qwen-image-2.1-one-image-edit-low-vram.json) | One Image Edit — Low VRAM | ComfyUI-Pixaroma |
| [qwen-image-2.1-one-image-edit-prompt-enhancer](Single-Image-Edit/qwen-image-2.1-one-image-edit-prompt-enhancer.json) | One Image Edit + Prompt Enhancer | ComfyUI-Pixaroma |
| [qwen-image-2.1-one-image-edit-turbo](Single-Image-Edit/qwen-image-2.1-one-image-edit-turbo.json) | One Image Edit — Turbo | ComfyUI-Pixaroma |
| [qwen-image-2.1-one-image-edit](Single-Image-Edit/qwen-image-2.1-one-image-edit.json) | One Image Edit | ComfyUI-Pixaroma |
| [sd15-juggernaut-reborn-img2img](Single-Image-Edit/sd15-juggernaut-reborn-img2img.json) | Image to Image | Core only |

### Sketch-to-image and 3D-render-to-image

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [flux-2-klein-9b-3d-model-to-image-ep33](Sketch-and-3D-to-Image/flux-2-klein-9b-3d-model-to-image-ep33.json) | 3D Model to Image (Ep33) | ComfyUI-Pixaroma |
| [flux-2-klein-9b-3d-model-to-image-keep-the-angle-ep33](Sketch-and-3D-to-Image/flux-2-klein-9b-3d-model-to-image-keep-the-angle-ep33.json) | 3D Model to Image — Keep the Angle (Ep33) | ComfyUI-Pixaroma |
| [flux-2-klein-9b-3d-model-to-image-keep-the-angle-ep34](Sketch-and-3D-to-Image/flux-2-klein-9b-3d-model-to-image-keep-the-angle-ep34.json) | 3D Model to Image — Keep the Angle (Ep34) | ComfyUI-Pixaroma |
| [flux-2-klein-9b-3d-model-to-image](Sketch-and-3D-to-Image/flux-2-klein-9b-3d-model-to-image.json) | 3D Model to Image | ComfyUI-Pixaroma |
| [flux-2-klein-9b-3d-scene-builder-to-image](Sketch-and-3D-to-Image/flux-2-klein-9b-3d-scene-builder-to-image.json) | 3D Scene Builder to Image | ComfyUI-Pixaroma |
| [ming-image-0.1-restyle-a-design-to-3d](Sketch-and-3D-to-Image/ming-image-0.1-restyle-a-design-to-3d.json) | Restyle a Design to 3D | ComfyUI-Pixaroma |
| [ming-image-0.1-sketch-to-photo](Sketch-and-3D-to-Image/ming-image-0.1-sketch-to-photo.json) | Sketch to Photo | ComfyUI-Pixaroma |
| [qwen-image-2.1-sketch-to-image-consistency-lora](Sketch-and-3D-to-Image/qwen-image-2.1-sketch-to-image-consistency-lora.json) | Sketch to Image + Consistency LoRA | ComfyUI-Pixaroma |
| [qwen-image-2.1-sketch-to-image](Sketch-and-3D-to-Image/qwen-image-2.1-sketch-to-image.json) | Sketch to Image | ComfyUI-Pixaroma |

See the [main README](../README.md) for models used, setup steps and the full catalog.
