# ComfyUI Workflow Library — Index

Reorganized 2026-10-20. Workflows are filed by **what they do**; the filename starts with the **model family** so a folder sorts by model.

Filename pattern: `Model - Task - Variant.json` (e.g. `Qwen Image 2.1 - One Image Edit - Low VRAM.json`).

| Folder | Purpose |
|---|---|
| 01-Image-Generation | Text-to-image, LLM prompt-assisted generation, design/typography/transparent PNG, prompt batching |
| 02-Image-Editing | Instruction edits, multi-image composition, character/outfit/pose, inpaint/outpaint/object removal, background removal, sketch & 3D-to-image |
| 03-Image-Enhancement | Upscaling (local + paid API), filters & colour grading |
| 04-Video | Text-to-video, image-to-video (first/last frame), reference & audio-sync, character animation from driving video |
| 05-Audio | Speech / voice cloning, music generation |
| 06-3D-Generation | Image-to-3D and multi-view-to-3D meshes |
| 07-Batch-and-Automation | Process whole folders of images; loop-based workflows |
| 08-Testing-and-Comparison | XY plots, draft-then-finish, image comparison |
| 90-Docs-and-Resources | LLM prompt-assistant instructions (ChatGPT / Claude / Gemini), LoRA training notes, reorganization manifest + undo script |

Adding a new workflow: drop it in the folder for its main job, name it `Model - Task - Variant.json`, and add a line below.

## All workflows by folder

### 01-Image-Generation/Design-Typography-and-Transparent
- Ming Image 0.1 - 3D Lettering
- Ming Image 0.1 - Social Media Post
- Ming Image 0.1 - Transparent PNG
- Qwen Image 2.1 - Transparent PNG

### 01-Image-Generation/LLM-Prompt-Assisted
- Anima Base v1.0 - Anime Text to Image + Gemma 4 Prompt Enhancer
- Boogu Image - Text to Image + Prompt Enhancer
- Flux 2 Klein 9B - Image to Prompt to Image (Qwen 3.5)
- Flux 2 Klein 9B - Text to Image + Qwen 3.5 Prompt Enhancer
- Krea 2 - Image to Prompt to Image
- Krea 2 - Text to Image + Prompt Enhancer
- Ming Image 0.1 - Text to Image + Prompt Enhancer
- Nunchaku - Z-Image Turbo - Text to Image + QwenVL GGUF Prompt Enhancer
- Qwen Image 2.1 - Image to Prompt to Image
- Qwen Image 2.1 - Text to Image + Prompt Enhancer
- Z-Image Turbo - Image to Prompt to Image (Gemma 4)
- Z-Image Turbo - Text to Image + Gemma 4 Prompt Enhancer + Find and Replace
- Z-Image Turbo - Text to Image + Gemma 4 Prompt Enhancer

### 01-Image-Generation/Prompt-Batching-and-Variations
- Flux 2 Klein 9B - Build a Prompt from Switches
- Flux 2 Klein 9B - Every Prompt Combination with Brackets
- Flux 2 Klein 9B - One Image per Prompt
- Flux 2 Klein 9B - One Subject in Many Styles
- Flux 2 Klein 9B - Queue a List of Prompts
- Flux 2 Klein 9B - Random Prompts Every Run
- Flux 2 Klein 9B - Short Ideas into Finished Images (Qwen 3.5 AI Prompt)
- Flux 2 Klein 9B - Short Story to Storyboard (Qwen 3.5 AI Prompt)

### 01-Image-Generation/Text-to-Image
- Boogu Image - Text to Image
- Flux 2 Klein 9B - Text to Image
- Flux 2 Klein 9B FP8 (Distilled) - Text to Image - Basic
- Krea 2 - Text to Image - 2K Hi-Res + Prompt Enhancer
- Krea 2 - Text to Image - Simple
- Lens - Text to Image
- Ming Image 0.1 - Text to Image
- Minimax H3 - Text to Image (Single Frame)
- Nunchaku - Flux.1 Dev - Text to Image
- Nunchaku - Qwen Image Lightning - Text to Image
- Nunchaku - Z-Image Turbo - Text to Image
- Qwen Image 2.1 - Text to Image - Low VRAM
- Qwen Image 2.1 - Text to Image - Turbo
- Qwen Image 2.1 - Text to Image
- Z-Image Turbo - Text to Image - FP8 AIO Checkpoint

### 02-Image-Editing/Background-Removal
- BiRefNet - Remove Background
- Qwen Image 2.1 - Remove Background
- SAM3 - Remove Background (Segment + Crop Object)

### 02-Image-Editing/Character-Outfit-and-Pose
- Flux 2 Klein 9B - Character Turnaround Sheet from One Image
- Krea 2 - Outfit Change + Outfit LoRA
- Krea 2 - Outfit Transfer v2
- Qwen Image 2.1 - Character Sheet
- Qwen Image 2.1 - Outfit Change - Turbo
- Qwen Image 2.1 - Outfit Change
- Qwen Image 2.1 - Pose from a Picture

### 02-Image-Editing/Inpaint-Outpaint-and-Object-Removal
- Flux 2 Klein 9B - Outpaint
- Flux 2 Klein 9B FP8 (Distilled) - Inpaint
- Flux 2 Klein 9B FP8 (Distilled) - Paint-Guided Edit
- LaMa - Object Remover
- Qwen Image 2.1 - Inpaint
- Qwen Image 2.1 - Outpaint

### 02-Image-Editing/Multi-Image-Composition
- Flux 2 Klein 9B FP8 (Distilled) - Multi-Image Edit - 2 Images
- Flux 2 Klein 9B KV FP8 - Multi-Image Edit - 3 Images
- Flux 2 Klein 9B KV FP8 - Multi-Image Edit - 4 Images
- Ming Image 0.1 - Product Ad from Two Pictures
- Qwen Image 2.1 - Character in a Scene
- Qwen Image 2.1 - Logo on a Product
- Qwen Image 2.1 - Multi-Image Edit - 2 Images + Prompt Enhancer
- Qwen Image 2.1 - Multi-Image Edit - 3 Images
- Qwen Image 2.1 - Multi-Image Edit - 4 Images
- Qwen Image 2.1 - Multi-Image Edit - Group Photo from 6 Images

### 02-Image-Editing/Single-Image-Edit
- Boogu Edit - One Image Edit
- Flux 2 Klein 9B - One Image Edit V3 + Keep Filename + Save to Dated Folder
- Flux 2 Klein 9B - One Image, Many Edits
- Flux 2 Klein 9B - One Image, Prompts from List
- Flux 2 Klein 9B FP8 (Distilled) - One Image Edit
- Ming Image 0.1 - One Image Edit
- Ming Image 0.1 - Social Media Pack from One Image
- Minimax H3 - One Image Edit (Single Frame)
- Qwen Image 2.1 - One Image Edit + Consistency LoRA
- Qwen Image 2.1 - One Image Edit + Prompt Enhancer
- Qwen Image 2.1 - One Image Edit - Low VRAM
- Qwen Image 2.1 - One Image Edit - Turbo
- Qwen Image 2.1 - One Image Edit

### 02-Image-Editing/Sketch-and-3D-to-Image
- Flux 2 Klein 9B - 3D Model to Image
- Flux 2 Klein 9B - 3D Scene Builder to Image
- Ming Image 0.1 - Restyle a Design to 3D
- Ming Image 0.1 - Sketch to Photo
- Qwen Image 2.1 - Sketch to Image + Consistency LoRA
- Qwen Image 2.1 - Sketch to Image

### 03-Image-Enhancement/Filters-and-Color-Grading
- LayerStyle - Image Filters and Color Adjustments

### 03-Image-Enhancement/Upscaling
- 1 Universal - Upscale Simple (No Model)
- 2 Universal - Upscale with 4x Model (NMKD-Siax)
- 3 Z-Image Turbo - Tiled Diffusion Upscaler
- 4 Nunchaku - Fluxmania - Tiled Diffusion Upscaler
- 5 SeedVR2 - Upscale
- 6 PAID API (51 Credits) - Nano Banana Pro - Upscale
- 7 PAID API (53 Credits) - Recraft - Creative Upscale
- 8 PAID API (8.5 Credits) - SeeDream 4.5 - Upscale

### 04-Video/Character-Animation-Video-to-Video
- Wan 2.1 SCAIL 2 - Character Animation from Driving Video - Long
- Wan 2.2 Animate - Replace Character and Background - 24FPS HD

### 04-Video/Image-to-Video
- Minimax FastH3 - Image to Video - First + Last Frame (8-Step)
- Minimax FastH3 - Image to Video - First Frame (8-Step)
- Minimax H3 - Image to Video - First + Last Frame + Speed LoRA
- Minimax H3 - Image to Video - First + Last Frame
- Minimax H3 - Image to Video - First Frame + Speed LoRA
- Minimax H3 - Image to Video - First Frame
- Minimax H3 - Image to Video - Last Frame
- Wan 2.2 - Image to Video - GGUF Lightx2v 4-Step + LoRA
- Wan 2.2 - Image to Video - GGUF Lightx2v 4-Step

### 04-Video/Reference-and-Audio-Sync
- Minimax H3 - Reference Image + Audio Sync - Sing + Speed LoRA
- Minimax H3 - Reference Image + Audio Sync - Sing
- Minimax H3 - Reference Image + Audio Sync - Speak + Speed LoRA
- Minimax H3 - Reference Image + Audio Sync - Speak
- Minimax H3 - Reference to Video - 2 Images
- Minimax H3 - Reference to Video - 3 Images

### 04-Video/Text-to-Video
- Minimax FastH3 - Text to Video (8-Step)
- Minimax H3 - Text to Video + Speed LoRA
- Minimax H3 - Text to Video - Low VRAM 8GB
- Minimax H3 - Text to Video

### 05-Audio/Music-Generation
- ACE-Step v1.5 XL Turbo - Text to Music
- Minimax Music 3 - Text to Music
- Stable Audio 3 - Text to Music + Gemma 4 Prompt Enhancer
- Stable Audio 3 - Text to Music

### 05-Audio/Speech-and-Voice-Cloning
- Fish S2 - Multi-Speaker Dialogue TTS
- Fish S2 - Text to Speech
- Fish S2 - Voice Clone TTS
- Qwen3-TTS - Voice Clone
- Qwen3-TTS - Voice Design + Dialogue
- Qwen3-TTS - Voice Design

### 06-3D-Generation/Image-to-3D
- Pixal3D - Image to 3D Model - HQ + PBR Textures
- Pixal3D - Image to 3D Model - Low VRAM
- Trellis 2 - Image to 3D Model - High VRAM
- Trellis 2 - Image to 3D Model - Low VRAM

### 06-3D-Generation/Multi-View-to-3D
- Pixal3D Multi-View - 1 Shape Only (No Colours) - HQ
- Pixal3D Multi-View - 2 Model + Colours
- Pixal3D Multi-View - 3 Model + PBR Textures - LQ
- Pixal3D Multi-View - 4 Model + PBR Textures - HQ

### 07-Batch-and-Automation/Folder-Batch-Processing
- BiRefNet - Remove the Background from All Images in a Folder
- Flux 2 Klein 9B - Coloring Pages from All Images in a Folder
- Flux 2 Klein 9B - Edit All Images in a Folder with One Prompt
- Flux 2 Klein 9B - Edit Each Image with Its Own Prompt
- Flux 2 Klein 9B - Edit Images from Folder (Simple)
- Flux 2 Klein 9B - Make All Images in a Folder Wide (Outpaint)
- Flux 2 Klein 9B - Product Photos from All Images in a Folder
- Flux 2 Klein 9B - Restore and Colorize Old Photos in a Folder
- NMKD-Siax 4x - Upscale All Images in a Folder
- Utility - Add Your Logo to All Images in a Folder
- Utility - Contact Sheet of All Images in a Folder
- Utility - Rename and Convert All Images in a Folder
- Utility - Resize All Images in a Folder
- Utility - Slideshow Video from All Images in a Folder
- Utility - Social Media Sizes for All Images in a Folder
- Utility - Watermark All Images in a Folder

### 07-Batch-and-Automation/Loops
- 1. Flux 2 Klein 9B - Loop Basics - Four Versions of One Prompt
- 2. Flux 2 Klein 9B - Loop - Build Up an Image Step by Step
- 3. Utility - Loop - Photo Strip from All Images in a Folder
- 4. Flux 2 Klein 9B - Loop - Comic Strip with the Same Character

### 08-Testing-and-Comparison
- Flux 2 Klein 9B - Draft First, Then Finish (Preview Gate)
- Flux 2 Klein 9B - XY Plot - Steps and Samplers
- Flux 2 Klein 9B - XY Plot - Styles and Subjects
- Utility - Image Compare (Side by Side)
- Z-Image Turbo - XY Plot

## Index by model family

Use this to find every workflow that needs a given model installed.

### ACE-Step 1.5 (1)
- `05-Audio/Music-Generation/ACE-Step v1.5 XL Turbo - Text to Music.json`

### Anima (1)
- `01-Image-Generation/LLM-Prompt-Assisted/Anima Base v1.0 - Anime Text to Image + Gemma 4 Prompt Enhancer.json`

### BiRefNet (2)
- `02-Image-Editing/Background-Removal/BiRefNet - Remove Background.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/BiRefNet - Remove the Background from All Images in a Folder.json`

### Boogu Image / Edit (3)
- `01-Image-Generation/LLM-Prompt-Assisted/Boogu Image - Text to Image + Prompt Enhancer.json`
- `01-Image-Generation/Text-to-Image/Boogu Image - Text to Image.json`
- `02-Image-Editing/Single-Image-Edit/Boogu Edit - One Image Edit.json`

### FLUX.1 Dev (Nunchaku) (1)
- `01-Image-Generation/Text-to-Image/Nunchaku - Flux.1 Dev - Text to Image.json`

### FLUX.2 Klein 9B (38)
- `01-Image-Generation/LLM-Prompt-Assisted/Flux 2 Klein 9B - Image to Prompt to Image (Qwen 3.5).json`
- `01-Image-Generation/LLM-Prompt-Assisted/Flux 2 Klein 9B - Text to Image + Qwen 3.5 Prompt Enhancer.json`
- `01-Image-Generation/Prompt-Batching-and-Variations/Flux 2 Klein 9B - Build a Prompt from Switches.json`
- `01-Image-Generation/Prompt-Batching-and-Variations/Flux 2 Klein 9B - Every Prompt Combination with Brackets.json`
- `01-Image-Generation/Prompt-Batching-and-Variations/Flux 2 Klein 9B - One Image per Prompt.json`
- `01-Image-Generation/Prompt-Batching-and-Variations/Flux 2 Klein 9B - One Subject in Many Styles.json`
- `01-Image-Generation/Prompt-Batching-and-Variations/Flux 2 Klein 9B - Queue a List of Prompts.json`
- `01-Image-Generation/Prompt-Batching-and-Variations/Flux 2 Klein 9B - Random Prompts Every Run.json`
- `01-Image-Generation/Prompt-Batching-and-Variations/Flux 2 Klein 9B - Short Ideas into Finished Images (Qwen 3.5 AI Prompt).json`
- `01-Image-Generation/Prompt-Batching-and-Variations/Flux 2 Klein 9B - Short Story to Storyboard (Qwen 3.5 AI Prompt).json`
- `01-Image-Generation/Text-to-Image/Flux 2 Klein 9B - Text to Image.json`
- `01-Image-Generation/Text-to-Image/Flux 2 Klein 9B FP8 (Distilled) - Text to Image - Basic.json`
- `02-Image-Editing/Character-Outfit-and-Pose/Flux 2 Klein 9B - Character Turnaround Sheet from One Image.json`
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/Flux 2 Klein 9B - Outpaint.json`
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/Flux 2 Klein 9B FP8 (Distilled) - Inpaint.json`
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/Flux 2 Klein 9B FP8 (Distilled) - Paint-Guided Edit.json`
- `02-Image-Editing/Multi-Image-Composition/Flux 2 Klein 9B FP8 (Distilled) - Multi-Image Edit - 2 Images.json`
- `02-Image-Editing/Multi-Image-Composition/Flux 2 Klein 9B KV FP8 - Multi-Image Edit - 3 Images.json`
- `02-Image-Editing/Multi-Image-Composition/Flux 2 Klein 9B KV FP8 - Multi-Image Edit - 4 Images.json`
- `02-Image-Editing/Single-Image-Edit/Flux 2 Klein 9B - One Image Edit V3 + Keep Filename + Save to Dated Folder.json`
- `02-Image-Editing/Single-Image-Edit/Flux 2 Klein 9B - One Image, Many Edits.json`
- `02-Image-Editing/Single-Image-Edit/Flux 2 Klein 9B - One Image, Prompts from List.json`
- `02-Image-Editing/Single-Image-Edit/Flux 2 Klein 9B FP8 (Distilled) - One Image Edit.json`
- `02-Image-Editing/Sketch-and-3D-to-Image/Flux 2 Klein 9B - 3D Model to Image.json`
- `02-Image-Editing/Sketch-and-3D-to-Image/Flux 2 Klein 9B - 3D Scene Builder to Image.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Coloring Pages from All Images in a Folder.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Edit All Images in a Folder with One Prompt.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Edit Each Image with Its Own Prompt.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Edit Images from Folder (Simple).json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Make All Images in a Folder Wide (Outpaint).json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Product Photos from All Images in a Folder.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Restore and Colorize Old Photos in a Folder.json`
- `07-Batch-and-Automation/Loops/1. Flux 2 Klein 9B - Loop Basics - Four Versions of One Prompt.json`
- `07-Batch-and-Automation/Loops/2. Flux 2 Klein 9B - Loop - Build Up an Image Step by Step.json`
- `07-Batch-and-Automation/Loops/4. Flux 2 Klein 9B - Loop - Comic Strip with the Same Character.json`
- `08-Testing-and-Comparison/Flux 2 Klein 9B - Draft First, Then Finish (Preview Gate).json`
- `08-Testing-and-Comparison/Flux 2 Klein 9B - XY Plot - Steps and Samplers.json`
- `08-Testing-and-Comparison/Flux 2 Klein 9B - XY Plot - Styles and Subjects.json`

### Fish S2 (3)
- `05-Audio/Speech-and-Voice-Cloning/Fish S2 - Multi-Speaker Dialogue TTS.json`
- `05-Audio/Speech-and-Voice-Cloning/Fish S2 - Text to Speech.json`
- `05-Audio/Speech-and-Voice-Cloning/Fish S2 - Voice Clone TTS.json`

### Fluxmania (Nunchaku) (1)
- `03-Image-Enhancement/Upscaling/4 Nunchaku - Fluxmania - Tiled Diffusion Upscaler.json`

### Krea 2 (6)
- `01-Image-Generation/LLM-Prompt-Assisted/Krea 2 - Image to Prompt to Image.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Krea 2 - Text to Image + Prompt Enhancer.json`
- `01-Image-Generation/Text-to-Image/Krea 2 - Text to Image - 2K Hi-Res + Prompt Enhancer.json`
- `01-Image-Generation/Text-to-Image/Krea 2 - Text to Image - Simple.json`
- `02-Image-Editing/Character-Outfit-and-Pose/Krea 2 - Outfit Change + Outfit LoRA.json`
- `02-Image-Editing/Character-Outfit-and-Pose/Krea 2 - Outfit Transfer v2.json`

### LaMa (1)
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/LaMa - Object Remover.json`

### LayerStyle (1)
- `03-Image-Enhancement/Filters-and-Color-Grading/LayerStyle - Image Filters and Color Adjustments.json`

### Lens (1)
- `01-Image-Generation/Text-to-Image/Lens - Text to Image.json`

### Ming Image 0.1 (10)
- `01-Image-Generation/Design-Typography-and-Transparent/Ming Image 0.1 - 3D Lettering.json`
- `01-Image-Generation/Design-Typography-and-Transparent/Ming Image 0.1 - Social Media Post.json`
- `01-Image-Generation/Design-Typography-and-Transparent/Ming Image 0.1 - Transparent PNG.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Ming Image 0.1 - Text to Image + Prompt Enhancer.json`
- `01-Image-Generation/Text-to-Image/Ming Image 0.1 - Text to Image.json`
- `02-Image-Editing/Multi-Image-Composition/Ming Image 0.1 - Product Ad from Two Pictures.json`
- `02-Image-Editing/Single-Image-Edit/Ming Image 0.1 - One Image Edit.json`
- `02-Image-Editing/Single-Image-Edit/Ming Image 0.1 - Social Media Pack from One Image.json`
- `02-Image-Editing/Sketch-and-3D-to-Image/Ming Image 0.1 - Restyle a Design to 3D.json`
- `02-Image-Editing/Sketch-and-3D-to-Image/Ming Image 0.1 - Sketch to Photo.json`

### MiniMax H3 / FastH3 (19)
- `01-Image-Generation/Text-to-Image/Minimax H3 - Text to Image (Single Frame).json`
- `02-Image-Editing/Single-Image-Edit/Minimax H3 - One Image Edit (Single Frame).json`
- `04-Video/Image-to-Video/Minimax FastH3 - Image to Video - First + Last Frame (8-Step).json`
- `04-Video/Image-to-Video/Minimax FastH3 - Image to Video - First Frame (8-Step).json`
- `04-Video/Image-to-Video/Minimax H3 - Image to Video - First + Last Frame + Speed LoRA.json`
- `04-Video/Image-to-Video/Minimax H3 - Image to Video - First + Last Frame.json`
- `04-Video/Image-to-Video/Minimax H3 - Image to Video - First Frame + Speed LoRA.json`
- `04-Video/Image-to-Video/Minimax H3 - Image to Video - First Frame.json`
- `04-Video/Image-to-Video/Minimax H3 - Image to Video - Last Frame.json`
- `04-Video/Reference-and-Audio-Sync/Minimax H3 - Reference Image + Audio Sync - Sing + Speed LoRA.json`
- `04-Video/Reference-and-Audio-Sync/Minimax H3 - Reference Image + Audio Sync - Sing.json`
- `04-Video/Reference-and-Audio-Sync/Minimax H3 - Reference Image + Audio Sync - Speak + Speed LoRA.json`
- `04-Video/Reference-and-Audio-Sync/Minimax H3 - Reference Image + Audio Sync - Speak.json`
- `04-Video/Reference-and-Audio-Sync/Minimax H3 - Reference to Video - 2 Images.json`
- `04-Video/Reference-and-Audio-Sync/Minimax H3 - Reference to Video - 3 Images.json`
- `04-Video/Text-to-Video/Minimax FastH3 - Text to Video (8-Step).json`
- `04-Video/Text-to-Video/Minimax H3 - Text to Video + Speed LoRA.json`
- `04-Video/Text-to-Video/Minimax H3 - Text to Video - Low VRAM 8GB.json`
- `04-Video/Text-to-Video/Minimax H3 - Text to Video.json`

### MiniMax Music 3 (1)
- `05-Audio/Music-Generation/Minimax Music 3 - Text to Music.json`

### No AI model (utility) (10)
- `03-Image-Enhancement/Upscaling/1 Universal - Upscale Simple (No Model).json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Utility - Add Your Logo to All Images in a Folder.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Utility - Contact Sheet of All Images in a Folder.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Utility - Rename and Convert All Images in a Folder.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Utility - Resize All Images in a Folder.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Utility - Slideshow Video from All Images in a Folder.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Utility - Social Media Sizes for All Images in a Folder.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Utility - Watermark All Images in a Folder.json`
- `07-Batch-and-Automation/Loops/3. Utility - Loop - Photo Strip from All Images in a Folder.json`
- `08-Testing-and-Comparison/Utility - Image Compare (Side by Side).json`

### Paid API nodes (3)
- `03-Image-Enhancement/Upscaling/6 PAID API (51 Credits) - Nano Banana Pro - Upscale.json`
- `03-Image-Enhancement/Upscaling/7 PAID API (53 Credits) - Recraft - Creative Upscale.json`
- `03-Image-Enhancement/Upscaling/8 PAID API (8.5 Credits) - SeeDream 4.5 - Upscale.json`

### Qwen Image (Nunchaku) (1)
- `01-Image-Generation/Text-to-Image/Nunchaku - Qwen Image Lightning - Text to Image.json`

### Qwen Image 2.1 (26)
- `01-Image-Generation/Design-Typography-and-Transparent/Qwen Image 2.1 - Transparent PNG.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Qwen Image 2.1 - Image to Prompt to Image.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Qwen Image 2.1 - Text to Image + Prompt Enhancer.json`
- `01-Image-Generation/Text-to-Image/Qwen Image 2.1 - Text to Image - Low VRAM.json`
- `01-Image-Generation/Text-to-Image/Qwen Image 2.1 - Text to Image - Turbo.json`
- `01-Image-Generation/Text-to-Image/Qwen Image 2.1 - Text to Image.json`
- `02-Image-Editing/Background-Removal/Qwen Image 2.1 - Remove Background.json`
- `02-Image-Editing/Character-Outfit-and-Pose/Qwen Image 2.1 - Character Sheet.json`
- `02-Image-Editing/Character-Outfit-and-Pose/Qwen Image 2.1 - Outfit Change - Turbo.json`
- `02-Image-Editing/Character-Outfit-and-Pose/Qwen Image 2.1 - Outfit Change.json`
- `02-Image-Editing/Character-Outfit-and-Pose/Qwen Image 2.1 - Pose from a Picture.json`
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/Qwen Image 2.1 - Inpaint.json`
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/Qwen Image 2.1 - Outpaint.json`
- `02-Image-Editing/Multi-Image-Composition/Qwen Image 2.1 - Character in a Scene.json`
- `02-Image-Editing/Multi-Image-Composition/Qwen Image 2.1 - Logo on a Product.json`
- `02-Image-Editing/Multi-Image-Composition/Qwen Image 2.1 - Multi-Image Edit - 2 Images + Prompt Enhancer.json`
- `02-Image-Editing/Multi-Image-Composition/Qwen Image 2.1 - Multi-Image Edit - 3 Images.json`
- `02-Image-Editing/Multi-Image-Composition/Qwen Image 2.1 - Multi-Image Edit - 4 Images.json`
- `02-Image-Editing/Multi-Image-Composition/Qwen Image 2.1 - Multi-Image Edit - Group Photo from 6 Images.json`
- `02-Image-Editing/Single-Image-Edit/Qwen Image 2.1 - One Image Edit + Consistency LoRA.json`
- `02-Image-Editing/Single-Image-Edit/Qwen Image 2.1 - One Image Edit + Prompt Enhancer.json`
- `02-Image-Editing/Single-Image-Edit/Qwen Image 2.1 - One Image Edit - Low VRAM.json`
- `02-Image-Editing/Single-Image-Edit/Qwen Image 2.1 - One Image Edit - Turbo.json`
- `02-Image-Editing/Single-Image-Edit/Qwen Image 2.1 - One Image Edit.json`
- `02-Image-Editing/Sketch-and-3D-to-Image/Qwen Image 2.1 - Sketch to Image + Consistency LoRA.json`
- `02-Image-Editing/Sketch-and-3D-to-Image/Qwen Image 2.1 - Sketch to Image.json`

### Qwen3-TTS (3)
- `05-Audio/Speech-and-Voice-Cloning/Qwen3-TTS - Voice Clone.json`
- `05-Audio/Speech-and-Voice-Cloning/Qwen3-TTS - Voice Design + Dialogue.json`
- `05-Audio/Speech-and-Voice-Cloning/Qwen3-TTS - Voice Design.json`

### SAM3 (1)
- `02-Image-Editing/Background-Removal/SAM3 - Remove Background (Segment + Crop Object).json`

### SeedVR2 (1)
- `03-Image-Enhancement/Upscaling/5 SeedVR2 - Upscale.json`

### Stable Audio 3 (2)
- `05-Audio/Music-Generation/Stable Audio 3 - Text to Music + Gemma 4 Prompt Enhancer.json`
- `05-Audio/Music-Generation/Stable Audio 3 - Text to Music.json`

### Trellis 2 / Pixal3D (8)
- `06-3D-Generation/Image-to-3D/Pixal3D - Image to 3D Model - HQ + PBR Textures.json`
- `06-3D-Generation/Image-to-3D/Pixal3D - Image to 3D Model - Low VRAM.json`
- `06-3D-Generation/Image-to-3D/Trellis 2 - Image to 3D Model - High VRAM.json`
- `06-3D-Generation/Image-to-3D/Trellis 2 - Image to 3D Model - Low VRAM.json`
- `06-3D-Generation/Multi-View-to-3D/Pixal3D Multi-View - 1 Shape Only (No Colours) - HQ.json`
- `06-3D-Generation/Multi-View-to-3D/Pixal3D Multi-View - 2 Model + Colours.json`
- `06-3D-Generation/Multi-View-to-3D/Pixal3D Multi-View - 3 Model + PBR Textures - LQ.json`
- `06-3D-Generation/Multi-View-to-3D/Pixal3D Multi-View - 4 Model + PBR Textures - HQ.json`

### Upscale model (NMKD-Siax) (2)
- `03-Image-Enhancement/Upscaling/2 Universal - Upscale with 4x Model (NMKD-Siax).json`
- `07-Batch-and-Automation/Folder-Batch-Processing/NMKD-Siax 4x - Upscale All Images in a Folder.json`

### Wan 2.1 / 2.2 (4)
- `04-Video/Character-Animation-Video-to-Video/Wan 2.1 SCAIL 2 - Character Animation from Driving Video - Long.json`
- `04-Video/Character-Animation-Video-to-Video/Wan 2.2 Animate - Replace Character and Background - 24FPS HD.json`
- `04-Video/Image-to-Video/Wan 2.2 - Image to Video - GGUF Lightx2v 4-Step + LoRA.json`
- `04-Video/Image-to-Video/Wan 2.2 - Image to Video - GGUF Lightx2v 4-Step.json`

### Z-Image Turbo (8)
- `01-Image-Generation/LLM-Prompt-Assisted/Nunchaku - Z-Image Turbo - Text to Image + QwenVL GGUF Prompt Enhancer.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Z-Image Turbo - Image to Prompt to Image (Gemma 4).json`
- `01-Image-Generation/LLM-Prompt-Assisted/Z-Image Turbo - Text to Image + Gemma 4 Prompt Enhancer + Find and Replace.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Z-Image Turbo - Text to Image + Gemma 4 Prompt Enhancer.json`
- `01-Image-Generation/Text-to-Image/Nunchaku - Z-Image Turbo - Text to Image.json`
- `01-Image-Generation/Text-to-Image/Z-Image Turbo - Text to Image - FP8 AIO Checkpoint.json`
- `03-Image-Enhancement/Upscaling/3 Z-Image Turbo - Tiled Diffusion Upscaler.json`
- `08-Testing-and-Comparison/Z-Image Turbo - XY Plot.json`
