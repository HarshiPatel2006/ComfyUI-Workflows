# ComfyUI Workflow Library — Index

Workflows are filed by **what they do**; the filename starts with the **model family** so a folder sorts by model.

Filename pattern: `Model - Task - Variant.json` (e.g. `Qwen Image 2.1 - One Image Edit - Low VRAM.json`). A trailing `(EpNN)` marks which Pixaroma episode a variant came from when two otherwise share a name.

| Folder | Purpose |
|---|---|
| 01-Image-Generation | Text-to-image, ControlNet-guided, LLM prompt-assisted, design/typography/transparent PNG, prompt batching |
| 02-Image-Editing | Instruction edits, multi-image composition, character/outfit/pose, inpaint/outpaint/object removal, background removal, sketch & 3D-to-image, compositing & image tools |
| 03-Image-Enhancement | Upscaling (local + paid API), filters & colour grading |
| 04-Video | Text-to-video, image-to-video, reference & audio-sync (talking video), character animation, video upscaling, audio-reactive |
| 05-Audio | Speech / voice cloning, music and sound generation |
| 06-3D-Generation | Image-to-3D and multi-view-to-3D meshes |
| 07-Batch-and-Automation | Process whole folders of images; loops; control, logic and math |
| 08-Testing-and-Comparison | XY plots, draft-then-finish, image/group comparison |
| 09-Movie | Short film director pipeline |
| 10-LLM-and-Prompt-Tools | LLM workflows that output text: prompt enhancers, image/video/audio to prompt, prompt generators |
| 90-Docs-and-Resources | LLM prompt-assistant instructions, LoRA training, learning & node demos, Pixaroma episode resources, sample media inputs, maintenance manifests + undo script |
| 91-Review-Version-Conflicts | Original Pixaroma versions of workflows whose library copy has different settings — review and keep one |

**352 workflows.** Adding a new workflow: drop it in the folder for its main job, name it `Model - Task - Variant.json`, and add it here.

## All workflows by folder

### 01-Image-Generation/ControlNet-Guided
- SD1.5 Juggernaut Reborn - Text to Image + ControlNet Canny
- Z-Image Turbo - Text to Image - FP8 AIO + ControlNet Union

### 01-Image-Generation/Design-Typography-and-Transparent
- Flux 3 Klein - Text in Images
- Ming Image 0.1 - 3D Lettering
- Ming Image 0.1 - App and Website Screens
- Ming Image 0.1 - Event Poster
- Ming Image 0.1 - Game Screens and Icons
- Ming Image 0.1 - Infographic
- Ming Image 0.1 - Logo Design
- Ming Image 0.1 - Logo Variations
- Ming Image 0.1 - Social Media Post
- Ming Image 0.1 - Transparent PNG
- Ming Image 0.1 - YouTube Thumbnail
- Pixaroma Nodes - Text Overlay
- Qwen Image 2.1 - Transparent PNG
- Z-Image Turbo - Text to Image + Text Overlay

### 01-Image-Generation/LLM-Prompt-Assisted
- Anima Base v1.0 - Anime Text to Image + Gemma 4 Prompt Enhancer
- Boogu Image - Text to Image + Prompt Enhancer
- Flux 2 Klein 9B - Image to Prompt to Image (Qwen 3.5)
- Flux 2 Klein 9B - Text to Image + Qwen 3.5 Prompt Enhancer
- Flux 3 Klein - Image to Prompt to Image
- Flux 3 Klein - Text to Image + Prompt Upsampler
- Krea 2 - Image to Prompt to Image (Ep31 AI Prompt Node)
- Krea 2 - Image to Prompt to Image
- Krea 2 - Text to Image + AI Prompt Enhancer (Ep31)
- Krea 2 - Text to Image + Extra Pass + Prompt Enhancer (Uncensored)
- Krea 2 - Text to Image + Extra Pass + Prompt Enhancer
- Krea 2 - Text to Image + Prompt Enhancer (Ep28)
- Krea 2 - Text to Image + Prompt Enhancer (Uncensored)
- Krea 2 - Text to Image + Prompt Enhancer
- Krea 2 INT8 - Image to Prompt to Image
- Krea 2 INT8 - Text to Image + Extra Pass + Image to Prompt
- Krea 2 INT8 - Text to Image + Extra Pass + Prompt Enhancer
- Krea 2 INT8 - Text to Image + Prompt Enhancer
- Ming Image 0.1 - Text to Image + Prompt Enhancer
- Nunchaku - Z-Image Turbo - Text to Image + QwenVL GGUF Prompt Enhancer
- Qwen Image 2.1 - Image to Prompt to Image
- Qwen Image 2.1 - Text to Image + Prompt Enhancer
- Z-Image Turbo - Image to Prompt to Image (Gemma 4)
- Z-Image Turbo - Text to Image + Gemma 4 Prompt Enhancer + Find and Replace
- Z-Image Turbo - Text to Image + Gemma 4 Prompt Enhancer
- Z-Image Turbo INT8 - Text to Image + AI Prompt Enhancer

### 01-Image-Generation/Prompt-Batching-and-Variations
- Flux 2 Klein 9B - Build a Prompt from Switches
- Flux 2 Klein 9B - Every Prompt Combination with Brackets
- Flux 2 Klein 9B - One Image per Prompt
- Flux 2 Klein 9B - One Subject in Many Styles
- Flux 2 Klein 9B - Queue a List of Prompts
- Flux 2 Klein 9B - Random Prompts Every Run
- Flux 2 Klein 9B - Short Ideas into Finished Images (Qwen 3.5 AI Prompt)
- Flux 2 Klein 9B - Short Story to Storyboard (Qwen 3.5 AI Prompt)
- Pixaroma Nodes - Prompt Multi - From List
- Pixaroma Nodes - Prompt Multi - Queue Text
- Pixaroma Nodes - Prompt Pack - Line
- Pixaroma Nodes - Prompt Pack - Paragraph
- Pixaroma Nodes - Prompt Stack
- Z-Image Turbo - Prompt Multi - Queue Text
- Z-Image Turbo - Prompt Pack - Line
- Z-Image Turbo - Prompt Pack - Paragraph
- Z-Image Turbo - Prompt Stack

### 01-Image-Generation/Text-to-Image
- Anima Base v1.0 - Anime Text to Image + SeedVR2 Upscale
- Anima Base v1.0 - Anime Text to Image
- Boogu Image - Text to Image
- Ernie Image Turbo - Text to Image - GGUF
- Flux 2 Klein 4B FP8 (Distilled) - Text to Image - Basic
- Flux 2 Klein 9B - Text to Image
- Flux 2 Klein 9B FP8 (Distilled) - Text to Image - Basic
- Flux 2 Klein 9B FP8 - Text to Image (Ep16)
- Flux 3 Klein - Layout with Boxes
- Flux 3 Klein - Text to Image + Z-Image Realism Pass
- Flux 3 Klein - Text to Image
- Krea 2 - Text to Image (Ep28)
- Krea 2 - Text to Image + Extra Pass + LoRA
- Krea 2 - Text to Image + Extra Pass
- Krea 2 - Text to Image - 2K Hi-Res + Prompt Enhancer (Uncensored)
- Krea 2 - Text to Image - 2K Hi-Res + Prompt Enhancer
- Krea 2 - Text to Image - Simple + LoRA
- Krea 2 - Text to Image - Simple - Low VRAM
- Krea 2 - Text to Image - Simple
- Krea 2 INT8 - Text to Image + Extra Pass + LoRA
- Krea 2 INT8 - Text to Image + Extra Pass
- Krea 2 INT8 - Text to Image - Simple + LoRA
- Krea 2 INT8 - Text to Image - Simple
- Lens - Text to Image
- Ming Image 0.1 - Text to Image
- Minimax H3 - Text to Image (Single Frame)
- Nunchaku - Flux.1 Dev - Text to Image
- Nunchaku - Qwen Image Lightning - Text to Image
- Nunchaku - Z-Image Turbo - Text to Image
- Qwen Image 2.1 - Text to Image - Low VRAM
- Qwen Image 2.1 - Text to Image - Turbo
- Qwen Image 2.1 - Text to Image
- SD1.5 Juggernaut Reborn - Text to Image + LoRA
- SD1.5 Juggernaut Reborn - Text to Image
- Z-Image Turbo - Text to Image - FP8 (Ep18)
- Z-Image Turbo - Text to Image - FP8 AIO + LoRA
- Z-Image Turbo - Text to Image - FP8 AIO Checkpoint
- Z-Image Turbo - Text to Image - FP8
- Z-Image Turbo - Text to Image - GGUF
- Z-Image Turbo INT8 - Text to Image

### 02-Image-Editing/Background-Removal
- BiRefNet - Remove Background
- Qwen Image 2.1 - Remove Background
- SAM3 - Remove Background (Segment + Crop Object)
- Utility - Remove Background from Transparent Items
- Utility - Remove Background

### 02-Image-Editing/Character-Outfit-and-Pose
- Flux 2 Klein 9B - Character Turnaround Sheet from One Image
- Flux 3 Klein - Character Sheet
- Flux 3 Klein - Outfit Change
- Krea 2 - Outfit Change + Outfit LoRA
- Krea 2 - Outfit Transfer v2
- Qwen Image 2.1 - Character Sheet
- Qwen Image 2.1 - Outfit Change - Turbo
- Qwen Image 2.1 - Outfit Change
- Qwen Image 2.1 - Pose from a Picture

### 02-Image-Editing/Compositing-and-Image-Tools
- Pixaroma Nodes - 3D Builder (Ep11)
- Pixaroma Nodes - 3D Builder (Ep13)
- Pixaroma Nodes - Combine - Join Two Images
- Pixaroma Nodes - Crop (Ep11)
- Pixaroma Nodes - Crop (Ep13)
- Pixaroma Nodes - Image Composer (Ep11)
- Pixaroma Nodes - Image Composer (Ep13)
- Pixaroma Nodes - Paint (Ep11)
- Pixaroma Nodes - Paint (Ep13)
- Utility - Image Blend
- Utility - Image Combiner for Transparent Items
- Utility - Image Combiner
- Utility - Image Scale
- Utility - Image Stitch
- Utility - Image Transformation

### 02-Image-Editing/Inpaint-Outpaint-and-Object-Removal
- Flux 2 Klein 4B FP8 (Distilled) - Inpaint
- Flux 2 Klein 9B - Outpaint
- Flux 2 Klein 9B - Paint to Image
- Flux 2 Klein 9B FP8 (Distilled) - Inpaint
- Flux 2 Klein 9B FP8 (Distilled) - Paint-Guided Edit
- Flux 2 Klein 9B FP8 - Inpaint (Ep22)
- Flux 2 Klein 9B INT8 - Inpaint
- Flux 2 Klein 9B KV FP8 - Inpaint
- Flux 2 Klein 9B KV FP8 - Outpaint (Custom Ratio)
- Flux 3 Klein - Edit inside a Box
- Flux 3 Klein - Outpaint
- LaMa - Object Remover
- Qwen Image 2.1 - Inpaint
- Qwen Image 2.1 - Outpaint

### 02-Image-Editing/Multi-Image-Composition
- Flux 2 Klein 4B FP8 (Distilled) - Multi-Image Edit - 2 Images
- Flux 2 Klein 9B - Image Composer to Image
- Flux 2 Klein 9B FP8 (Distilled) - Multi-Image Edit - 2 Images
- Flux 2 Klein 9B KV FP8 - Image Blend
- Flux 2 Klein 9B KV FP8 - Multi-Image Edit - 2 Images
- Flux 2 Klein 9B KV FP8 - Multi-Image Edit - 3 Images
- Flux 2 Klein 9B KV FP8 - Multi-Image Edit - 4 Images
- Flux 3 Klein - Character in a Scene
- Flux 3 Klein - Group Photo
- Flux 3 Klein - Logo on a Product
- Flux 3 Klein - Product Ad
- Ming Image 0.1 - Product Ad from Two Pictures
- Qwen Image 2.1 - Character in a Scene
- Qwen Image 2.1 - Logo on a Product
- Qwen Image 2.1 - Multi-Image Edit - 2 Images + Prompt Enhancer
- Qwen Image 2.1 - Multi-Image Edit - 3 Images
- Qwen Image 2.1 - Multi-Image Edit - 4 Images
- Qwen Image 2.1 - Multi-Image Edit - Group Photo from 6 Images

### 02-Image-Editing/Single-Image-Edit
- Boogu Edit - One Image Edit
- Flux 2 Klein 4B FP8 (Distilled) - One Image Edit
- Flux 2 Klein 9B - One Image Edit V1
- Flux 2 Klein 9B - One Image Edit V2 + Notify and Switch
- Flux 2 Klein 9B - One Image Edit V3 + Keep Filename + Save to Dated Folder
- Flux 2 Klein 9B - One Image, Many Edits
- Flux 2 Klein 9B - One Image, Prompts from List
- Flux 2 Klein 9B FP8 (Distilled) - One Image Edit
- Flux 2 Klein 9B INT8 - One Image Edit
- Flux 2 Klein 9B KV FP8 - One Image Edit (Custom Ratio)
- Flux 2 Klein 9B KV FP8 - One Image Edit (Same Ratio)
- Flux 3 Klein - Edit Text in a Picture
- Flux 3 Klein - One Image Edit
- Flux 3 Klein - Relight and Seasons
- Flux 3 Klein - Restore and Colorize
- Flux 3 Klein - Restyle
- Krea 2 - Edit LoRA - Character and Background
- Krea 2 - Edit LoRA - Custom Ratio
- Krea 2 - Edit LoRA
- Ming Image 0.1 - One Image Edit
- Ming Image 0.1 - Social Media Pack from One Image
- Minimax H3 - One Image Edit (Single Frame)
- Qwen Image 2.1 - One Image Edit + Consistency LoRA
- Qwen Image 2.1 - One Image Edit + Prompt Enhancer
- Qwen Image 2.1 - One Image Edit - Low VRAM
- Qwen Image 2.1 - One Image Edit - Turbo
- Qwen Image 2.1 - One Image Edit
- SD1.5 Juggernaut Reborn - Image to Image

### 02-Image-Editing/Sketch-and-3D-to-Image
- Flux 2 Klein 9B - 3D Model to Image (Ep33)
- Flux 2 Klein 9B - 3D Model to Image - Keep the Angle (Ep33)
- Flux 2 Klein 9B - 3D Model to Image - Keep the Angle (Ep34)
- Flux 2 Klein 9B - 3D Model to Image
- Flux 2 Klein 9B - 3D Scene Builder to Image
- Ming Image 0.1 - Restyle a Design to 3D
- Ming Image 0.1 - Sketch to Photo
- Qwen Image 2.1 - Sketch to Image + Consistency LoRA
- Qwen Image 2.1 - Sketch to Image

### 03-Image-Enhancement/Filters-and-Color-Grading
- LayerStyle - Image Filters and Color Adjustments
- Utility - Image Filters Example

### 03-Image-Enhancement/Upscaling
- 1 Universal - Upscale Simple (No Model)
- 2 Universal - Upscale with 4x Model (NMKD-Siax)
- 3 Z-Image Turbo - Tiled Diffusion Upscaler
- 4 Nunchaku - Fluxmania - Tiled Diffusion Upscaler
- 5 SeedVR2 - Upscale
- 6 PAID API (51 Credits) - Nano Banana Pro - Upscale
- 7 PAID API (53 Credits) - Recraft - Creative Upscale
- 8 PAID API (8.5 Credits) - SeeDream 4.5 - Upscale

### 04-Video/Audio-Reactive
- Utility - Images React to Music (Audio Reactive)

### 04-Video/Character-Animation-Video-to-Video
- Wan 2.1 SCAIL - Image to Video - Multi Character (9-16 Ratio Only)
- Wan 2.1 SCAIL - Image to Video - Single Character
- Wan 2.1 SCAIL 2 - Character Animation from Driving Video - Compact
- Wan 2.1 SCAIL 2 - Character Animation from Driving Video - Long
- Wan 2.2 Animate - Replace Character and Background - 16FPS
- Wan 2.2 Animate - Replace Character and Background - 24FPS HD
- Wan 2.2 Animate - Replace Character and Background - 24FPS
- Wan 2.2 Animate - Replace Only Character - 16FPS
- Wan 2.2 Animate - Replace Only Character - 24FPS

### 04-Video/Image-to-Video
- LTX-2 - Image to Video with Audio
- LTX-2 - Image to Video with Custom Audio
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
- Wan 2.1 InfiniteTalk - Talking Video - Easy Extend 3 to 34 Seconds
- Wan 2.1 InfiniteTalk - Talking Video - Manual Extend 3 to 34 Seconds
- Wan 2.1 InfiniteTalk - Talking Video from Audio - 10-11 Seconds
- Wan 2.1 InfiniteTalk - Talking Video from Audio - 4-6 Seconds
- Wan 2.1 InfiniteTalk - Talking Video from Audio - 7-9 Seconds

### 04-Video/Text-to-Video
- Minimax FastH3 - Text to Video (8-Step)
- Minimax H3 - Text to Video + Speed LoRA
- Minimax H3 - Text to Video - Low VRAM 8GB
- Minimax H3 - Text to Video

### 04-Video/Video-Upscaling
- SeedVR2 - Video Upscale

### 05-Audio/Music-Generation
- ACE-Step v1.5 XL Turbo - Text to Music
- Minimax Music 3 - Text to Music
- Stable Audio 3 - Image to Music + Gemma 4
- Stable Audio 3 - Text to Music + Gemma 4 Prompt Enhancer
- Stable Audio 3 - Text to Music
- Stable Audio 3 - Text to Sound Effects + Gemma 4

### 05-Audio/Speech-and-Voice-Cloning
- Fish S2 - Multi-Speaker Dialogue TTS
- Fish S2 - Text to Speech
- Fish S2 - Voice Clone TTS
- Qwen3-TTS - Custom Voice
- Qwen3-TTS - Voice Clone + Load Saved Voice
- Qwen3-TTS - Voice Clone + Save Voice
- Qwen3-TTS - Voice Clone + Saved Multi Voice + Dialogue
- Qwen3-TTS - Voice Clone
- Qwen3-TTS - Voice Design + Dialogue
- Qwen3-TTS - Voice Design + Save Voice
- Qwen3-TTS - Voice Design

### 06-3D-Generation/Image-to-3D
- Pixal3D - Image to 3D Model - HQ + PBR Textures
- Pixal3D - Image to 3D Model - Low VRAM
- Trellis 2 - Image to 3D Model - HQ + PBR Textures
- Trellis 2 - Image to 3D Model - High VRAM
- Trellis 2 - Image to 3D Model - Low VRAM

### 06-3D-Generation/Multi-View-to-3D
- Pixal3D Multi-View - 1 Shape Only (No Colours) - HQ
- Pixal3D Multi-View - 1 Shape Only (No Colours)
- Pixal3D Multi-View - 2 Model + Colours
- Pixal3D Multi-View - 3 Model + PBR Textures - LQ
- Pixal3D Multi-View - 4 Model + PBR Textures - HQ

### 07-Batch-and-Automation/Control-Logic-and-Math
- BiRefNet - Turn Steps On and Off
- Flux 2 Klein 9B - One Control Panel for the Whole Workflow
- Flux 2 Klein 9B - One Workflow, Two Jobs
- Flux 2 Klein 9B - Set and Get - No Long Wires
- Flux 2 Klein 9B - Style Presets from a Dropdown
- Pixaroma Nodes - Switch Node

### 07-Batch-and-Automation/Folder-Batch-Processing
- BiRefNet - Remove the Background from All Images in a Folder
- Flux 2 Klein 9B + Qwen3-VL - AI Writes an Edit for Every Image
- Flux 2 Klein 9B + Qwen3-VL - Re-imagine All Images in a Folder in Another Style
- Flux 2 Klein 9B - Before and After Grid for All Images in a Folder
- Flux 2 Klein 9B - Coloring Pages from All Images in a Folder
- Flux 2 Klein 9B - Do a Big Image Folder in Parts
- Flux 2 Klein 9B - Edit All Images in a Folder with One Prompt
- Flux 2 Klein 9B - Edit Each Image with Its Own Prompt
- Flux 2 Klein 9B - Edit Images from Folder (Simple)
- Flux 2 Klein 9B - Fix the Caption Text Files, Then Make the Images Again
- Flux 2 Klein 9B - Make All Images in a Folder Wide (Outpaint)
- Flux 2 Klein 9B - One Image per Text File
- Flux 2 Klein 9B - Product Photos from All Images in a Folder
- Flux 2 Klein 9B - Re-create Old Images from Their Prompts
- Flux 2 Klein 9B - Restore and Colorize Old Photos in a Folder
- NMKD-Siax 4x - Upscale All Images in a Folder
- Qwen3-VL - Caption All Images in a Folder for LoRA Training
- Qwen3-VL - Keep Only the Images the AI Says Yes To
- Qwen3-VL - Rename Every Image by What Is in It
- Qwen3-VL - Sort All Images in a Folder into Subfolders by What Is in Them
- Utility - Add Your Logo to All Images in a Folder
- Utility - Collect the Prompts from All Images in a Folder
- Utility - Contact Sheet of All Images in a Folder
- Utility - Load Images from Folder + Crop
- Utility - Math - Scale All Images in a Folder by Percent
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
- Pixaroma Nodes - Loop - Build a List
- Pixaroma Nodes - Loop - Build an Image Batch
- Pixaroma Nodes - Loop - Carry Two Values

### 08-Testing-and-Comparison
- Flux 2 Klein 9B - Draft First, Then Finish (Preview Gate)
- Flux 2 Klein 9B - XY Plot - Steps and Samplers
- Flux 2 Klein 9B - XY Plot - Styles and Subjects
- Krea 2 INT8 - LoRA XY Plot
- Pixaroma Nodes - Group Compare (ComfyUI vs Pixaroma)
- Pixaroma Nodes - Image Compare
- Utility - Image Compare (Side by Side)
- Z-Image Turbo - XY Plot

### 09-Movie
- Short Film Director Pipeline (Krea + MiniMax H3)

### 10-LLM-and-Prompt-Tools
- Gemma 4 - Anima Prompt Enhancer
- Gemma 4 - Audio to Text
- Gemma 4 - Image to Prompt
- Gemma 4 - Prompt Enhancer
- Gemma 4 - Video to Description
- Gemma 4 - Video to Prompt
- Minimax H3 - First Frame to Video Prompt Generator
- Minimax H3 - Text to Video Prompt Generator
- Minimax Music 3 - Caption and Lyrics Generator
- Pixaroma Nodes - Read Prompt From Image Metadata
- Qwen 3.5 - Image to Prompt
- Qwen 3.5 - Text to Prompt
- Qwen Image 2.1 - Image to Prompt (Qwen3-VL 8B)
- Qwen3-VL - Prompt from Image
- QwenVL 3 - Image and Text to Prompt (GGUF)

### 90-Docs-and-Resources/Learning-and-Node-Demos
- Flux 2 Klein 9B FP8 - Multi-Step Workflow Example
- Nodes Explained 01 - Models Explained - Finished (Z-Image Turbo)
- Nodes Explained 01 - Models Explained - Practice (Z-Image Turbo)
- Pixaroma - Help and Resources
- Pixaroma Nodes - Change Node Color
- Pixaroma Nodes - Labels (Ep11)
- Pixaroma Nodes - Labels (Ep13)
- Pixaroma Nodes - Note

### 90-Docs-and-Resources/LoRA-Training
- Krea 2 - LoRA Converter

### 91-Review-Version-Conflicts
- Ep11 - Flux 2 Klein 9B FP8 (Distilled) - One Image Edit with Paint Pixaroma Node (Pixaroma original)
- Ep15 - ACE-Step v1.5 XL Turbo - Text to Music (Pixaroma original)
- Ep16 - Flux 2 Klein 9B - Image to Prompt to Image (Qwen 3.5) (Pixaroma original)
- Ep16 - Flux 2 Klein 9B - Text to Image + Qwen 3.5 Prompt Enhancer (Pixaroma original)
- Ep20 - Anima Base v1.0 - Anime Text to Image + Gemma 4 Prompt Enhancer (Pixaroma original)

## Index by model family

Use this to find every workflow that needs a given model installed.

### ACE-Step 1.5 (2)
- `05-Audio/Music-Generation/ACE-Step v1.5 XL Turbo - Text to Music.json`
- `91-Review-Version-Conflicts/Ep15 - ACE-Step v1.5 XL Turbo - Text to Music (Pixaroma original).json`

### Anima (5)
- `01-Image-Generation/LLM-Prompt-Assisted/Anima Base v1.0 - Anime Text to Image + Gemma 4 Prompt Enhancer.json`
- `01-Image-Generation/Text-to-Image/Anima Base v1.0 - Anime Text to Image + SeedVR2 Upscale.json`
- `01-Image-Generation/Text-to-Image/Anima Base v1.0 - Anime Text to Image.json`
- `10-LLM-and-Prompt-Tools/Gemma 4 - Anima Prompt Enhancer.json`
- `91-Review-Version-Conflicts/Ep20 - Anima Base v1.0 - Anime Text to Image + Gemma 4 Prompt Enhancer (Pixaroma original).json`

### BiRefNet (3)
- `02-Image-Editing/Background-Removal/BiRefNet - Remove Background.json`
- `07-Batch-and-Automation/Control-Logic-and-Math/BiRefNet - Turn Steps On and Off.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/BiRefNet - Remove the Background from All Images in a Folder.json`

### Boogu Image / Edit (3)
- `01-Image-Generation/LLM-Prompt-Assisted/Boogu Image - Text to Image + Prompt Enhancer.json`
- `01-Image-Generation/Text-to-Image/Boogu Image - Text to Image.json`
- `02-Image-Editing/Single-Image-Edit/Boogu Edit - One Image Edit.json`

### Ernie Image (1)
- `01-Image-Generation/Text-to-Image/Ernie Image Turbo - Text to Image - GGUF.json`

### FLUX.1 Dev (Nunchaku) (1)
- `01-Image-Generation/Text-to-Image/Nunchaku - Flux.1 Dev - Text to Image.json`

### FLUX.2 Klein 4B (4)
- `01-Image-Generation/Text-to-Image/Flux 2 Klein 4B FP8 (Distilled) - Text to Image - Basic.json`
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/Flux 2 Klein 4B FP8 (Distilled) - Inpaint.json`
- `02-Image-Editing/Multi-Image-Composition/Flux 2 Klein 4B FP8 (Distilled) - Multi-Image Edit - 2 Images.json`
- `02-Image-Editing/Single-Image-Edit/Flux 2 Klein 4B FP8 (Distilled) - One Image Edit.json`

### FLUX.2 Klein 9B (70)
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
- `01-Image-Generation/Text-to-Image/Flux 2 Klein 9B FP8 - Text to Image (Ep16).json`
- `02-Image-Editing/Character-Outfit-and-Pose/Flux 2 Klein 9B - Character Turnaround Sheet from One Image.json`
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/Flux 2 Klein 9B - Outpaint.json`
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/Flux 2 Klein 9B - Paint to Image.json`
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/Flux 2 Klein 9B FP8 (Distilled) - Inpaint.json`
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/Flux 2 Klein 9B FP8 (Distilled) - Paint-Guided Edit.json`
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/Flux 2 Klein 9B FP8 - Inpaint (Ep22).json`
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/Flux 2 Klein 9B INT8 - Inpaint.json`
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/Flux 2 Klein 9B KV FP8 - Inpaint.json`
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/Flux 2 Klein 9B KV FP8 - Outpaint (Custom Ratio).json`
- `02-Image-Editing/Multi-Image-Composition/Flux 2 Klein 9B - Image Composer to Image.json`
- `02-Image-Editing/Multi-Image-Composition/Flux 2 Klein 9B FP8 (Distilled) - Multi-Image Edit - 2 Images.json`
- `02-Image-Editing/Multi-Image-Composition/Flux 2 Klein 9B KV FP8 - Image Blend.json`
- `02-Image-Editing/Multi-Image-Composition/Flux 2 Klein 9B KV FP8 - Multi-Image Edit - 2 Images.json`
- `02-Image-Editing/Multi-Image-Composition/Flux 2 Klein 9B KV FP8 - Multi-Image Edit - 3 Images.json`
- `02-Image-Editing/Multi-Image-Composition/Flux 2 Klein 9B KV FP8 - Multi-Image Edit - 4 Images.json`
- `02-Image-Editing/Single-Image-Edit/Flux 2 Klein 9B - One Image Edit V1.json`
- `02-Image-Editing/Single-Image-Edit/Flux 2 Klein 9B - One Image Edit V2 + Notify and Switch.json`
- `02-Image-Editing/Single-Image-Edit/Flux 2 Klein 9B - One Image Edit V3 + Keep Filename + Save to Dated Folder.json`
- `02-Image-Editing/Single-Image-Edit/Flux 2 Klein 9B - One Image, Many Edits.json`
- `02-Image-Editing/Single-Image-Edit/Flux 2 Klein 9B - One Image, Prompts from List.json`
- `02-Image-Editing/Single-Image-Edit/Flux 2 Klein 9B FP8 (Distilled) - One Image Edit.json`
- `02-Image-Editing/Single-Image-Edit/Flux 2 Klein 9B INT8 - One Image Edit.json`
- `02-Image-Editing/Single-Image-Edit/Flux 2 Klein 9B KV FP8 - One Image Edit (Custom Ratio).json`
- `02-Image-Editing/Single-Image-Edit/Flux 2 Klein 9B KV FP8 - One Image Edit (Same Ratio).json`
- `02-Image-Editing/Sketch-and-3D-to-Image/Flux 2 Klein 9B - 3D Model to Image (Ep33).json`
- `02-Image-Editing/Sketch-and-3D-to-Image/Flux 2 Klein 9B - 3D Model to Image - Keep the Angle (Ep33).json`
- `02-Image-Editing/Sketch-and-3D-to-Image/Flux 2 Klein 9B - 3D Model to Image - Keep the Angle (Ep34).json`
- `02-Image-Editing/Sketch-and-3D-to-Image/Flux 2 Klein 9B - 3D Model to Image.json`
- `02-Image-Editing/Sketch-and-3D-to-Image/Flux 2 Klein 9B - 3D Scene Builder to Image.json`
- `07-Batch-and-Automation/Control-Logic-and-Math/Flux 2 Klein 9B - One Control Panel for the Whole Workflow.json`
- `07-Batch-and-Automation/Control-Logic-and-Math/Flux 2 Klein 9B - One Workflow, Two Jobs.json`
- `07-Batch-and-Automation/Control-Logic-and-Math/Flux 2 Klein 9B - Set and Get - No Long Wires.json`
- `07-Batch-and-Automation/Control-Logic-and-Math/Flux 2 Klein 9B - Style Presets from a Dropdown.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B + Qwen3-VL - AI Writes an Edit for Every Image.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B + Qwen3-VL - Re-imagine All Images in a Folder in Another Style.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Before and After Grid for All Images in a Folder.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Coloring Pages from All Images in a Folder.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Do a Big Image Folder in Parts.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Edit All Images in a Folder with One Prompt.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Edit Each Image with Its Own Prompt.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Edit Images from Folder (Simple).json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Fix the Caption Text Files, Then Make the Images Again.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Make All Images in a Folder Wide (Outpaint).json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - One Image per Text File.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Product Photos from All Images in a Folder.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Re-create Old Images from Their Prompts.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Flux 2 Klein 9B - Restore and Colorize Old Photos in a Folder.json`
- `07-Batch-and-Automation/Loops/1. Flux 2 Klein 9B - Loop Basics - Four Versions of One Prompt.json`
- `07-Batch-and-Automation/Loops/2. Flux 2 Klein 9B - Loop - Build Up an Image Step by Step.json`
- `07-Batch-and-Automation/Loops/4. Flux 2 Klein 9B - Loop - Comic Strip with the Same Character.json`
- `08-Testing-and-Comparison/Flux 2 Klein 9B - Draft First, Then Finish (Preview Gate).json`
- `08-Testing-and-Comparison/Flux 2 Klein 9B - XY Plot - Steps and Samplers.json`
- `08-Testing-and-Comparison/Flux 2 Klein 9B - XY Plot - Styles and Subjects.json`
- `90-Docs-and-Resources/Learning-and-Node-Demos/Flux 2 Klein 9B FP8 - Multi-Step Workflow Example.json`
- `91-Review-Version-Conflicts/Ep11 - Flux 2 Klein 9B FP8 (Distilled) - One Image Edit with Paint Pixaroma Node (Pixaroma original).json`
- `91-Review-Version-Conflicts/Ep16 - Flux 2 Klein 9B - Image to Prompt to Image (Qwen 3.5) (Pixaroma original).json`
- `91-Review-Version-Conflicts/Ep16 - Flux 2 Klein 9B - Text to Image + Qwen 3.5 Prompt Enhancer (Pixaroma original).json`

### FLUX.3 Klein (19)
- `01-Image-Generation/Design-Typography-and-Transparent/Flux 3 Klein - Text in Images.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Flux 3 Klein - Image to Prompt to Image.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Flux 3 Klein - Text to Image + Prompt Upsampler.json`
- `01-Image-Generation/Text-to-Image/Flux 3 Klein - Layout with Boxes.json`
- `01-Image-Generation/Text-to-Image/Flux 3 Klein - Text to Image + Z-Image Realism Pass.json`
- `01-Image-Generation/Text-to-Image/Flux 3 Klein - Text to Image.json`
- `02-Image-Editing/Character-Outfit-and-Pose/Flux 3 Klein - Character Sheet.json`
- `02-Image-Editing/Character-Outfit-and-Pose/Flux 3 Klein - Outfit Change.json`
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/Flux 3 Klein - Edit inside a Box.json`
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/Flux 3 Klein - Outpaint.json`
- `02-Image-Editing/Multi-Image-Composition/Flux 3 Klein - Character in a Scene.json`
- `02-Image-Editing/Multi-Image-Composition/Flux 3 Klein - Group Photo.json`
- `02-Image-Editing/Multi-Image-Composition/Flux 3 Klein - Logo on a Product.json`
- `02-Image-Editing/Multi-Image-Composition/Flux 3 Klein - Product Ad.json`
- `02-Image-Editing/Single-Image-Edit/Flux 3 Klein - Edit Text in a Picture.json`
- `02-Image-Editing/Single-Image-Edit/Flux 3 Klein - One Image Edit.json`
- `02-Image-Editing/Single-Image-Edit/Flux 3 Klein - Relight and Seasons.json`
- `02-Image-Editing/Single-Image-Edit/Flux 3 Klein - Restore and Colorize.json`
- `02-Image-Editing/Single-Image-Edit/Flux 3 Klein - Restyle.json`

### Fish S2 (3)
- `05-Audio/Speech-and-Voice-Cloning/Fish S2 - Multi-Speaker Dialogue TTS.json`
- `05-Audio/Speech-and-Voice-Cloning/Fish S2 - Text to Speech.json`
- `05-Audio/Speech-and-Voice-Cloning/Fish S2 - Voice Clone TTS.json`

### Fluxmania (Nunchaku) (1)
- `03-Image-Enhancement/Upscaling/4 Nunchaku - Fluxmania - Tiled Diffusion Upscaler.json`

### Gemma 4 (LLM) (5)
- `10-LLM-and-Prompt-Tools/Gemma 4 - Audio to Text.json`
- `10-LLM-and-Prompt-Tools/Gemma 4 - Image to Prompt.json`
- `10-LLM-and-Prompt-Tools/Gemma 4 - Prompt Enhancer.json`
- `10-LLM-and-Prompt-Tools/Gemma 4 - Video to Description.json`
- `10-LLM-and-Prompt-Tools/Gemma 4 - Video to Prompt.json`

### Krea 2 (31)
- `01-Image-Generation/LLM-Prompt-Assisted/Krea 2 - Image to Prompt to Image (Ep31 AI Prompt Node).json`
- `01-Image-Generation/LLM-Prompt-Assisted/Krea 2 - Image to Prompt to Image.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Krea 2 - Text to Image + AI Prompt Enhancer (Ep31).json`
- `01-Image-Generation/LLM-Prompt-Assisted/Krea 2 - Text to Image + Extra Pass + Prompt Enhancer (Uncensored).json`
- `01-Image-Generation/LLM-Prompt-Assisted/Krea 2 - Text to Image + Extra Pass + Prompt Enhancer.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Krea 2 - Text to Image + Prompt Enhancer (Ep28).json`
- `01-Image-Generation/LLM-Prompt-Assisted/Krea 2 - Text to Image + Prompt Enhancer (Uncensored).json`
- `01-Image-Generation/LLM-Prompt-Assisted/Krea 2 - Text to Image + Prompt Enhancer.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Krea 2 INT8 - Image to Prompt to Image.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Krea 2 INT8 - Text to Image + Extra Pass + Image to Prompt.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Krea 2 INT8 - Text to Image + Extra Pass + Prompt Enhancer.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Krea 2 INT8 - Text to Image + Prompt Enhancer.json`
- `01-Image-Generation/Text-to-Image/Krea 2 - Text to Image (Ep28).json`
- `01-Image-Generation/Text-to-Image/Krea 2 - Text to Image + Extra Pass + LoRA.json`
- `01-Image-Generation/Text-to-Image/Krea 2 - Text to Image + Extra Pass.json`
- `01-Image-Generation/Text-to-Image/Krea 2 - Text to Image - 2K Hi-Res + Prompt Enhancer (Uncensored).json`
- `01-Image-Generation/Text-to-Image/Krea 2 - Text to Image - 2K Hi-Res + Prompt Enhancer.json`
- `01-Image-Generation/Text-to-Image/Krea 2 - Text to Image - Simple + LoRA.json`
- `01-Image-Generation/Text-to-Image/Krea 2 - Text to Image - Simple - Low VRAM.json`
- `01-Image-Generation/Text-to-Image/Krea 2 - Text to Image - Simple.json`
- `01-Image-Generation/Text-to-Image/Krea 2 INT8 - Text to Image + Extra Pass + LoRA.json`
- `01-Image-Generation/Text-to-Image/Krea 2 INT8 - Text to Image + Extra Pass.json`
- `01-Image-Generation/Text-to-Image/Krea 2 INT8 - Text to Image - Simple + LoRA.json`
- `01-Image-Generation/Text-to-Image/Krea 2 INT8 - Text to Image - Simple.json`
- `02-Image-Editing/Character-Outfit-and-Pose/Krea 2 - Outfit Change + Outfit LoRA.json`
- `02-Image-Editing/Character-Outfit-and-Pose/Krea 2 - Outfit Transfer v2.json`
- `02-Image-Editing/Single-Image-Edit/Krea 2 - Edit LoRA - Character and Background.json`
- `02-Image-Editing/Single-Image-Edit/Krea 2 - Edit LoRA - Custom Ratio.json`
- `02-Image-Editing/Single-Image-Edit/Krea 2 - Edit LoRA.json`
- `08-Testing-and-Comparison/Krea 2 INT8 - LoRA XY Plot.json`
- `90-Docs-and-Resources/LoRA-Training/Krea 2 - LoRA Converter.json`

### Krea 2 + MiniMax H3 (pipeline) (1)
- `09-Movie/Short Film Director Pipeline (Krea + MiniMax H3).json`

### LTX-2 (2)
- `04-Video/Image-to-Video/LTX-2 - Image to Video with Audio.json`
- `04-Video/Image-to-Video/LTX-2 - Image to Video with Custom Audio.json`

### LaMa (1)
- `02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/LaMa - Object Remover.json`

### LayerStyle (1)
- `03-Image-Enhancement/Filters-and-Color-Grading/LayerStyle - Image Filters and Color Adjustments.json`

### Learning / node demos (3)
- `90-Docs-and-Resources/Learning-and-Node-Demos/Nodes Explained 01 - Models Explained - Finished (Z-Image Turbo).json`
- `90-Docs-and-Resources/Learning-and-Node-Demos/Nodes Explained 01 - Models Explained - Practice (Z-Image Turbo).json`
- `90-Docs-and-Resources/Learning-and-Node-Demos/Pixaroma - Help and Resources.json`

### Lens (1)
- `01-Image-Generation/Text-to-Image/Lens - Text to Image.json`

### Ming Image 0.1 (17)
- `01-Image-Generation/Design-Typography-and-Transparent/Ming Image 0.1 - 3D Lettering.json`
- `01-Image-Generation/Design-Typography-and-Transparent/Ming Image 0.1 - App and Website Screens.json`
- `01-Image-Generation/Design-Typography-and-Transparent/Ming Image 0.1 - Event Poster.json`
- `01-Image-Generation/Design-Typography-and-Transparent/Ming Image 0.1 - Game Screens and Icons.json`
- `01-Image-Generation/Design-Typography-and-Transparent/Ming Image 0.1 - Infographic.json`
- `01-Image-Generation/Design-Typography-and-Transparent/Ming Image 0.1 - Logo Design.json`
- `01-Image-Generation/Design-Typography-and-Transparent/Ming Image 0.1 - Logo Variations.json`
- `01-Image-Generation/Design-Typography-and-Transparent/Ming Image 0.1 - Social Media Post.json`
- `01-Image-Generation/Design-Typography-and-Transparent/Ming Image 0.1 - Transparent PNG.json`
- `01-Image-Generation/Design-Typography-and-Transparent/Ming Image 0.1 - YouTube Thumbnail.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Ming Image 0.1 - Text to Image + Prompt Enhancer.json`
- `01-Image-Generation/Text-to-Image/Ming Image 0.1 - Text to Image.json`
- `02-Image-Editing/Multi-Image-Composition/Ming Image 0.1 - Product Ad from Two Pictures.json`
- `02-Image-Editing/Single-Image-Edit/Ming Image 0.1 - One Image Edit.json`
- `02-Image-Editing/Single-Image-Edit/Ming Image 0.1 - Social Media Pack from One Image.json`
- `02-Image-Editing/Sketch-and-3D-to-Image/Ming Image 0.1 - Restyle a Design to 3D.json`
- `02-Image-Editing/Sketch-and-3D-to-Image/Ming Image 0.1 - Sketch to Photo.json`

### MiniMax H3 / FastH3 (21)
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
- `10-LLM-and-Prompt-Tools/Minimax H3 - First Frame to Video Prompt Generator.json`
- `10-LLM-and-Prompt-Tools/Minimax H3 - Text to Video Prompt Generator.json`

### MiniMax Music 3 (2)
- `05-Audio/Music-Generation/Minimax Music 3 - Text to Music.json`
- `10-LLM-and-Prompt-Tools/Minimax Music 3 - Caption and Lyrics Generator.json`

### No AI model (utility) (23)
- `02-Image-Editing/Background-Removal/Utility - Remove Background from Transparent Items.json`
- `02-Image-Editing/Background-Removal/Utility - Remove Background.json`
- `02-Image-Editing/Compositing-and-Image-Tools/Utility - Image Blend.json`
- `02-Image-Editing/Compositing-and-Image-Tools/Utility - Image Combiner for Transparent Items.json`
- `02-Image-Editing/Compositing-and-Image-Tools/Utility - Image Combiner.json`
- `02-Image-Editing/Compositing-and-Image-Tools/Utility - Image Scale.json`
- `02-Image-Editing/Compositing-and-Image-Tools/Utility - Image Stitch.json`
- `02-Image-Editing/Compositing-and-Image-Tools/Utility - Image Transformation.json`
- `03-Image-Enhancement/Filters-and-Color-Grading/Utility - Image Filters Example.json`
- `03-Image-Enhancement/Upscaling/1 Universal - Upscale Simple (No Model).json`
- `04-Video/Audio-Reactive/Utility - Images React to Music (Audio Reactive).json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Utility - Add Your Logo to All Images in a Folder.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Utility - Collect the Prompts from All Images in a Folder.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Utility - Contact Sheet of All Images in a Folder.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Utility - Load Images from Folder + Crop.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Utility - Math - Scale All Images in a Folder by Percent.json`
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

### Pixaroma nodes only (no AI model) (26)
- `01-Image-Generation/Design-Typography-and-Transparent/Pixaroma Nodes - Text Overlay.json`
- `01-Image-Generation/Prompt-Batching-and-Variations/Pixaroma Nodes - Prompt Multi - From List.json`
- `01-Image-Generation/Prompt-Batching-and-Variations/Pixaroma Nodes - Prompt Multi - Queue Text.json`
- `01-Image-Generation/Prompt-Batching-and-Variations/Pixaroma Nodes - Prompt Pack - Line.json`
- `01-Image-Generation/Prompt-Batching-and-Variations/Pixaroma Nodes - Prompt Pack - Paragraph.json`
- `01-Image-Generation/Prompt-Batching-and-Variations/Pixaroma Nodes - Prompt Stack.json`
- `02-Image-Editing/Compositing-and-Image-Tools/Pixaroma Nodes - 3D Builder (Ep11).json`
- `02-Image-Editing/Compositing-and-Image-Tools/Pixaroma Nodes - 3D Builder (Ep13).json`
- `02-Image-Editing/Compositing-and-Image-Tools/Pixaroma Nodes - Combine - Join Two Images.json`
- `02-Image-Editing/Compositing-and-Image-Tools/Pixaroma Nodes - Crop (Ep11).json`
- `02-Image-Editing/Compositing-and-Image-Tools/Pixaroma Nodes - Crop (Ep13).json`
- `02-Image-Editing/Compositing-and-Image-Tools/Pixaroma Nodes - Image Composer (Ep11).json`
- `02-Image-Editing/Compositing-and-Image-Tools/Pixaroma Nodes - Image Composer (Ep13).json`
- `02-Image-Editing/Compositing-and-Image-Tools/Pixaroma Nodes - Paint (Ep11).json`
- `02-Image-Editing/Compositing-and-Image-Tools/Pixaroma Nodes - Paint (Ep13).json`
- `07-Batch-and-Automation/Control-Logic-and-Math/Pixaroma Nodes - Switch Node.json`
- `07-Batch-and-Automation/Loops/Pixaroma Nodes - Loop - Build a List.json`
- `07-Batch-and-Automation/Loops/Pixaroma Nodes - Loop - Build an Image Batch.json`
- `07-Batch-and-Automation/Loops/Pixaroma Nodes - Loop - Carry Two Values.json`
- `08-Testing-and-Comparison/Pixaroma Nodes - Group Compare (ComfyUI vs Pixaroma).json`
- `08-Testing-and-Comparison/Pixaroma Nodes - Image Compare.json`
- `10-LLM-and-Prompt-Tools/Pixaroma Nodes - Read Prompt From Image Metadata.json`
- `90-Docs-and-Resources/Learning-and-Node-Demos/Pixaroma Nodes - Change Node Color.json`
- `90-Docs-and-Resources/Learning-and-Node-Demos/Pixaroma Nodes - Labels (Ep11).json`
- `90-Docs-and-Resources/Learning-and-Node-Demos/Pixaroma Nodes - Labels (Ep13).json`
- `90-Docs-and-Resources/Learning-and-Node-Demos/Pixaroma Nodes - Note.json`

### Qwen 3.5 (LLM) (2)
- `10-LLM-and-Prompt-Tools/Qwen 3.5 - Image to Prompt.json`
- `10-LLM-and-Prompt-Tools/Qwen 3.5 - Text to Prompt.json`

### Qwen Image (Nunchaku) (1)
- `01-Image-Generation/Text-to-Image/Nunchaku - Qwen Image Lightning - Text to Image.json`

### Qwen Image 2.1 (27)
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
- `10-LLM-and-Prompt-Tools/Qwen Image 2.1 - Image to Prompt (Qwen3-VL 8B).json`

### Qwen3-TTS (8)
- `05-Audio/Speech-and-Voice-Cloning/Qwen3-TTS - Custom Voice.json`
- `05-Audio/Speech-and-Voice-Cloning/Qwen3-TTS - Voice Clone + Load Saved Voice.json`
- `05-Audio/Speech-and-Voice-Cloning/Qwen3-TTS - Voice Clone + Save Voice.json`
- `05-Audio/Speech-and-Voice-Cloning/Qwen3-TTS - Voice Clone + Saved Multi Voice + Dialogue.json`
- `05-Audio/Speech-and-Voice-Cloning/Qwen3-TTS - Voice Clone.json`
- `05-Audio/Speech-and-Voice-Cloning/Qwen3-TTS - Voice Design + Dialogue.json`
- `05-Audio/Speech-and-Voice-Cloning/Qwen3-TTS - Voice Design + Save Voice.json`
- `05-Audio/Speech-and-Voice-Cloning/Qwen3-TTS - Voice Design.json`

### Qwen3-VL (LLM) (6)
- `07-Batch-and-Automation/Folder-Batch-Processing/Qwen3-VL - Caption All Images in a Folder for LoRA Training.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Qwen3-VL - Keep Only the Images the AI Says Yes To.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Qwen3-VL - Rename Every Image by What Is in It.json`
- `07-Batch-and-Automation/Folder-Batch-Processing/Qwen3-VL - Sort All Images in a Folder into Subfolders by What Is in Them.json`
- `10-LLM-and-Prompt-Tools/Qwen3-VL - Prompt from Image.json`
- `10-LLM-and-Prompt-Tools/QwenVL 3 - Image and Text to Prompt (GGUF).json`

### SAM3 (1)
- `02-Image-Editing/Background-Removal/SAM3 - Remove Background (Segment + Crop Object).json`

### SD 1.5 (4)
- `01-Image-Generation/ControlNet-Guided/SD1.5 Juggernaut Reborn - Text to Image + ControlNet Canny.json`
- `01-Image-Generation/Text-to-Image/SD1.5 Juggernaut Reborn - Text to Image + LoRA.json`
- `01-Image-Generation/Text-to-Image/SD1.5 Juggernaut Reborn - Text to Image.json`
- `02-Image-Editing/Single-Image-Edit/SD1.5 Juggernaut Reborn - Image to Image.json`

### SeedVR2 (2)
- `03-Image-Enhancement/Upscaling/5 SeedVR2 - Upscale.json`
- `04-Video/Video-Upscaling/SeedVR2 - Video Upscale.json`

### Stable Audio 3 (4)
- `05-Audio/Music-Generation/Stable Audio 3 - Image to Music + Gemma 4.json`
- `05-Audio/Music-Generation/Stable Audio 3 - Text to Music + Gemma 4 Prompt Enhancer.json`
- `05-Audio/Music-Generation/Stable Audio 3 - Text to Music.json`
- `05-Audio/Music-Generation/Stable Audio 3 - Text to Sound Effects + Gemma 4.json`

### Trellis 2 / Pixal3D (10)
- `06-3D-Generation/Image-to-3D/Pixal3D - Image to 3D Model - HQ + PBR Textures.json`
- `06-3D-Generation/Image-to-3D/Pixal3D - Image to 3D Model - Low VRAM.json`
- `06-3D-Generation/Image-to-3D/Trellis 2 - Image to 3D Model - HQ + PBR Textures.json`
- `06-3D-Generation/Image-to-3D/Trellis 2 - Image to 3D Model - High VRAM.json`
- `06-3D-Generation/Image-to-3D/Trellis 2 - Image to 3D Model - Low VRAM.json`
- `06-3D-Generation/Multi-View-to-3D/Pixal3D Multi-View - 1 Shape Only (No Colours) - HQ.json`
- `06-3D-Generation/Multi-View-to-3D/Pixal3D Multi-View - 1 Shape Only (No Colours).json`
- `06-3D-Generation/Multi-View-to-3D/Pixal3D Multi-View - 2 Model + Colours.json`
- `06-3D-Generation/Multi-View-to-3D/Pixal3D Multi-View - 3 Model + PBR Textures - LQ.json`
- `06-3D-Generation/Multi-View-to-3D/Pixal3D Multi-View - 4 Model + PBR Textures - HQ.json`

### Upscale model (NMKD-Siax) (2)
- `03-Image-Enhancement/Upscaling/2 Universal - Upscale with 4x Model (NMKD-Siax).json`
- `07-Batch-and-Automation/Folder-Batch-Processing/NMKD-Siax 4x - Upscale All Images in a Folder.json`

### Wan 2.1 / 2.2 (16)
- `04-Video/Character-Animation-Video-to-Video/Wan 2.1 SCAIL - Image to Video - Multi Character (9-16 Ratio Only).json`
- `04-Video/Character-Animation-Video-to-Video/Wan 2.1 SCAIL - Image to Video - Single Character.json`
- `04-Video/Character-Animation-Video-to-Video/Wan 2.1 SCAIL 2 - Character Animation from Driving Video - Compact.json`
- `04-Video/Character-Animation-Video-to-Video/Wan 2.1 SCAIL 2 - Character Animation from Driving Video - Long.json`
- `04-Video/Character-Animation-Video-to-Video/Wan 2.2 Animate - Replace Character and Background - 16FPS.json`
- `04-Video/Character-Animation-Video-to-Video/Wan 2.2 Animate - Replace Character and Background - 24FPS HD.json`
- `04-Video/Character-Animation-Video-to-Video/Wan 2.2 Animate - Replace Character and Background - 24FPS.json`
- `04-Video/Character-Animation-Video-to-Video/Wan 2.2 Animate - Replace Only Character - 16FPS.json`
- `04-Video/Character-Animation-Video-to-Video/Wan 2.2 Animate - Replace Only Character - 24FPS.json`
- `04-Video/Image-to-Video/Wan 2.2 - Image to Video - GGUF Lightx2v 4-Step + LoRA.json`
- `04-Video/Image-to-Video/Wan 2.2 - Image to Video - GGUF Lightx2v 4-Step.json`
- `04-Video/Reference-and-Audio-Sync/Wan 2.1 InfiniteTalk - Talking Video - Easy Extend 3 to 34 Seconds.json`
- `04-Video/Reference-and-Audio-Sync/Wan 2.1 InfiniteTalk - Talking Video - Manual Extend 3 to 34 Seconds.json`
- `04-Video/Reference-and-Audio-Sync/Wan 2.1 InfiniteTalk - Talking Video from Audio - 10-11 Seconds.json`
- `04-Video/Reference-and-Audio-Sync/Wan 2.1 InfiniteTalk - Talking Video from Audio - 4-6 Seconds.json`
- `04-Video/Reference-and-Audio-Sync/Wan 2.1 InfiniteTalk - Talking Video from Audio - 7-9 Seconds.json`

### Z-Image Turbo (20)
- `01-Image-Generation/ControlNet-Guided/Z-Image Turbo - Text to Image - FP8 AIO + ControlNet Union.json`
- `01-Image-Generation/Design-Typography-and-Transparent/Z-Image Turbo - Text to Image + Text Overlay.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Nunchaku - Z-Image Turbo - Text to Image + QwenVL GGUF Prompt Enhancer.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Z-Image Turbo - Image to Prompt to Image (Gemma 4).json`
- `01-Image-Generation/LLM-Prompt-Assisted/Z-Image Turbo - Text to Image + Gemma 4 Prompt Enhancer + Find and Replace.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Z-Image Turbo - Text to Image + Gemma 4 Prompt Enhancer.json`
- `01-Image-Generation/LLM-Prompt-Assisted/Z-Image Turbo INT8 - Text to Image + AI Prompt Enhancer.json`
- `01-Image-Generation/Prompt-Batching-and-Variations/Z-Image Turbo - Prompt Multi - Queue Text.json`
- `01-Image-Generation/Prompt-Batching-and-Variations/Z-Image Turbo - Prompt Pack - Line.json`
- `01-Image-Generation/Prompt-Batching-and-Variations/Z-Image Turbo - Prompt Pack - Paragraph.json`
- `01-Image-Generation/Prompt-Batching-and-Variations/Z-Image Turbo - Prompt Stack.json`
- `01-Image-Generation/Text-to-Image/Nunchaku - Z-Image Turbo - Text to Image.json`
- `01-Image-Generation/Text-to-Image/Z-Image Turbo - Text to Image - FP8 (Ep18).json`
- `01-Image-Generation/Text-to-Image/Z-Image Turbo - Text to Image - FP8 AIO + LoRA.json`
- `01-Image-Generation/Text-to-Image/Z-Image Turbo - Text to Image - FP8 AIO Checkpoint.json`
- `01-Image-Generation/Text-to-Image/Z-Image Turbo - Text to Image - FP8.json`
- `01-Image-Generation/Text-to-Image/Z-Image Turbo - Text to Image - GGUF.json`
- `01-Image-Generation/Text-to-Image/Z-Image Turbo INT8 - Text to Image.json`
- `03-Image-Enhancement/Upscaling/3 Z-Image Turbo - Tiled Diffusion Upscaler.json`
- `08-Testing-and-Comparison/Z-Image Turbo - XY Plot.json`
