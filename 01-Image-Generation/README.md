# Image Generation — ComfyUI workflows

Text-to-image (txt2img) workflows for FLUX.2 / FLUX.3 Klein, Qwen-Image 2.1, Krea 2, Z-Image Turbo, Ming Image, SD 1.5 and more — plus ControlNet, LLM prompt enhancers, typography / logo / transparent PNG design and prompt batching.

| Subfolder | What is inside | Workflows |
|---|---|---|
| [`ControlNet-Guided/`](ControlNet-Guided) | ControlNet-guided generation (Canny, Union) | 2 |
| [`Design-Typography-and-Transparent/`](Design-Typography-and-Transparent) | Logos, posters, text in images, UI screens and transparent PNGs | 14 |
| [`LLM-Prompt-Assisted/`](LLM-Prompt-Assisted) | Text-to-image with LLM prompt enhancers and image-to-prompt-to-image | 26 |
| [`Prompt-Batching-and-Variations/`](Prompt-Batching-and-Variations) | Prompt lists, styles and batch variations | 17 |
| [`Text-to-Image/`](Text-to-Image) | Text-to-image (txt2img) generation | 45 |

## Workflows (104)

### ControlNet-guided generation (Canny, Union)

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [sd15-juggernaut-reborn-txt2img-controlnet-canny](ControlNet-Guided/sd15-juggernaut-reborn-txt2img-controlnet-canny.json) | Text to Image + ControlNet Canny | comfyui_controlnet_aux |
| [z-image-turbo-txt2img-fp8-aio-controlnet-union](ControlNet-Guided/z-image-turbo-txt2img-fp8-aio-controlnet-union.json) | Text to Image — FP8 AIO + ControlNet Union | comfyui_controlnet_aux, rgthree-comfy |

### Logos, posters, text in images, UI screens and transparent PNGs

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [flux-3-klein-text-in-images](Design-Typography-and-Transparent/flux-3-klein-text-in-images.json) | Text in Images | ComfyUI-Pixaroma |
| [ming-image-0.1-3d-lettering](Design-Typography-and-Transparent/ming-image-0.1-3d-lettering.json) | 3D Lettering | ComfyUI-Pixaroma |
| [ming-image-0.1-app-and-website-screens](Design-Typography-and-Transparent/ming-image-0.1-app-and-website-screens.json) | App and Website Screens | ComfyUI-Pixaroma |
| [ming-image-0.1-event-poster](Design-Typography-and-Transparent/ming-image-0.1-event-poster.json) | Event Poster | ComfyUI-Pixaroma |
| [ming-image-0.1-game-screens-and-icons](Design-Typography-and-Transparent/ming-image-0.1-game-screens-and-icons.json) | Game Screens and Icons | ComfyUI-Pixaroma |
| [ming-image-0.1-infographic](Design-Typography-and-Transparent/ming-image-0.1-infographic.json) | Infographic | ComfyUI-Pixaroma |
| [ming-image-0.1-logo-design](Design-Typography-and-Transparent/ming-image-0.1-logo-design.json) | Logo Design | ComfyUI-Pixaroma |
| [ming-image-0.1-logo-variations](Design-Typography-and-Transparent/ming-image-0.1-logo-variations.json) | Logo Variations | ComfyUI-Pixaroma |
| [ming-image-0.1-social-media-post](Design-Typography-and-Transparent/ming-image-0.1-social-media-post.json) | Social Media Post | ComfyUI-Pixaroma |
| [ming-image-0.1-transparent-png](Design-Typography-and-Transparent/ming-image-0.1-transparent-png.json) | Transparent PNG | ComfyUI-Pixaroma |
| [ming-image-0.1-youtube-thumbnail](Design-Typography-and-Transparent/ming-image-0.1-youtube-thumbnail.json) | YouTube Thumbnail | ComfyUI-Pixaroma |
| [pixaroma-nodes-text-overlay](Design-Typography-and-Transparent/pixaroma-nodes-text-overlay.json) | Text Overlay | ComfyUI-Pixaroma |
| [qwen-image-2.1-transparent-png](Design-Typography-and-Transparent/qwen-image-2.1-transparent-png.json) | Transparent PNG | ComfyUI-Pixaroma |
| [z-image-turbo-txt2img-text-overlay](Design-Typography-and-Transparent/z-image-turbo-txt2img-text-overlay.json) | Text to Image + Text Overlay | ComfyUI-Pixaroma |

### Text-to-image with LLM prompt enhancers and image-to-prompt-to-image

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [anima-base-v1.0-anime-txt2img-gemma-4-prompt-enhancer](LLM-Prompt-Assisted/anima-base-v1.0-anime-txt2img-gemma-4-prompt-enhancer.json) | Anime Text to Image + Gemma 4 Prompt Enhancer | ComfyUI-Pixaroma |
| [boogu-image-txt2img-prompt-enhancer](LLM-Prompt-Assisted/boogu-image-txt2img-prompt-enhancer.json) | Text to Image + Prompt Enhancer | ComfyUI-Pixaroma |
| [flux-2-klein-9b-image-to-prompt-to-image-qwen-3.5](LLM-Prompt-Assisted/flux-2-klein-9b-image-to-prompt-to-image-qwen-3.5.json) | Image to Prompt to Image (Qwen 3.5) | ComfyUI-Pixaroma |
| [flux-2-klein-9b-txt2img-qwen-3.5-prompt-enhancer](LLM-Prompt-Assisted/flux-2-klein-9b-txt2img-qwen-3.5-prompt-enhancer.json) | Text to Image + Qwen 3.5 Prompt Enhancer | ComfyUI-Pixaroma |
| [flux-3-klein-image-to-prompt-to-image](LLM-Prompt-Assisted/flux-3-klein-image-to-prompt-to-image.json) | Image to Prompt to Image | ComfyUI-Pixaroma |
| [flux-3-klein-txt2img-prompt-upsampler](LLM-Prompt-Assisted/flux-3-klein-txt2img-prompt-upsampler.json) | Text to Image + Prompt Upsampler | ComfyUI-Pixaroma |
| [krea-2-image-to-prompt-to-image-ep31-ai-prompt-node](LLM-Prompt-Assisted/krea-2-image-to-prompt-to-image-ep31-ai-prompt-node.json) | Image to Prompt to Image (Ep31 AI Prompt Node) | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-image-to-prompt-to-image](LLM-Prompt-Assisted/krea-2-image-to-prompt-to-image.json) | Image to Prompt to Image | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-int8-image-to-prompt-to-image](LLM-Prompt-Assisted/krea-2-int8-image-to-prompt-to-image.json) | Image to Prompt to Image | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-int8-txt2img-extra-pass-image-to-prompt](LLM-Prompt-Assisted/krea-2-int8-txt2img-extra-pass-image-to-prompt.json) | Text to Image + Extra Pass + Image to Prompt | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-int8-txt2img-extra-pass-prompt-enhancer](LLM-Prompt-Assisted/krea-2-int8-txt2img-extra-pass-prompt-enhancer.json) | Text to Image + Extra Pass + Prompt Enhancer | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-int8-txt2img-prompt-enhancer](LLM-Prompt-Assisted/krea-2-int8-txt2img-prompt-enhancer.json) | Text to Image + Prompt Enhancer | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-ai-prompt-enhancer-ep31](LLM-Prompt-Assisted/krea-2-txt2img-ai-prompt-enhancer-ep31.json) | Text to Image + AI Prompt Enhancer (Ep31) | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-extra-pass-prompt-enhancer-uncensored](LLM-Prompt-Assisted/krea-2-txt2img-extra-pass-prompt-enhancer-uncensored.json) | Text to Image + Extra Pass + Prompt Enhancer (Uncensored) | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-extra-pass-prompt-enhancer](LLM-Prompt-Assisted/krea-2-txt2img-extra-pass-prompt-enhancer.json) | Text to Image + Extra Pass + Prompt Enhancer | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-prompt-enhancer-ep28](LLM-Prompt-Assisted/krea-2-txt2img-prompt-enhancer-ep28.json) | Text to Image + Prompt Enhancer (Ep28) | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-prompt-enhancer-uncensored](LLM-Prompt-Assisted/krea-2-txt2img-prompt-enhancer-uncensored.json) | Text to Image + Prompt Enhancer (Uncensored) | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-prompt-enhancer](LLM-Prompt-Assisted/krea-2-txt2img-prompt-enhancer.json) | Text to Image + Prompt Enhancer | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [ming-image-0.1-txt2img-prompt-enhancer](LLM-Prompt-Assisted/ming-image-0.1-txt2img-prompt-enhancer.json) | Text to Image + Prompt Enhancer | ComfyUI-Pixaroma |
| [nunchaku-z-image-turbo-txt2img-qwenvl-gguf-prompt-enhancer](LLM-Prompt-Assisted/nunchaku-z-image-turbo-txt2img-qwenvl-gguf-prompt-enhancer.json) | Z-Image Turbo — Text to Image + QwenVL GGUF Prompt Enhancer | ComfyUI-QwenVL, ComfyUI-nunchaku |
| [qwen-image-2.1-image-to-prompt-to-image](LLM-Prompt-Assisted/qwen-image-2.1-image-to-prompt-to-image.json) | Image to Prompt to Image | ComfyUI-Pixaroma |
| [qwen-image-2.1-txt2img-prompt-enhancer](LLM-Prompt-Assisted/qwen-image-2.1-txt2img-prompt-enhancer.json) | Text to Image + Prompt Enhancer | ComfyUI-Pixaroma |
| [z-image-turbo-image-to-prompt-to-image-gemma-4](LLM-Prompt-Assisted/z-image-turbo-image-to-prompt-to-image-gemma-4.json) | Image to Prompt to Image (Gemma 4) | ComfyUI-Pixaroma |
| [z-image-turbo-int8-txt2img-ai-prompt-enhancer](LLM-Prompt-Assisted/z-image-turbo-int8-txt2img-ai-prompt-enhancer.json) | Text to Image + AI Prompt Enhancer | ComfyUI-Pixaroma |
| [z-image-turbo-txt2img-gemma-4-prompt-enhancer-find-and-replace](LLM-Prompt-Assisted/z-image-turbo-txt2img-gemma-4-prompt-enhancer-find-and-replace.json) | Text to Image + Gemma 4 Prompt Enhancer + Find and Replace | ComfyUI-Pixaroma |
| [z-image-turbo-txt2img-gemma-4-prompt-enhancer](LLM-Prompt-Assisted/z-image-turbo-txt2img-gemma-4-prompt-enhancer.json) | Text to Image + Gemma 4 Prompt Enhancer | ComfyUI-Pixaroma |

### Prompt lists, styles and batch variations

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [flux-2-klein-9b-build-a-prompt-from-switches](Prompt-Batching-and-Variations/flux-2-klein-9b-build-a-prompt-from-switches.json) | Build a Prompt from Switches | ComfyUI-Pixaroma |
| [flux-2-klein-9b-every-prompt-combination-with-brackets](Prompt-Batching-and-Variations/flux-2-klein-9b-every-prompt-combination-with-brackets.json) | Every Prompt Combination with Brackets | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-image-per-prompt](Prompt-Batching-and-Variations/flux-2-klein-9b-one-image-per-prompt.json) | One Image per Prompt | ComfyUI-Pixaroma |
| [flux-2-klein-9b-one-subject-in-many-styles](Prompt-Batching-and-Variations/flux-2-klein-9b-one-subject-in-many-styles.json) | One Subject in Many Styles | ComfyUI-Pixaroma |
| [flux-2-klein-9b-queue-a-list-of-prompts](Prompt-Batching-and-Variations/flux-2-klein-9b-queue-a-list-of-prompts.json) | Queue a List of Prompts | ComfyUI-Pixaroma |
| [flux-2-klein-9b-random-prompts-every-run](Prompt-Batching-and-Variations/flux-2-klein-9b-random-prompts-every-run.json) | Random Prompts Every Run | ComfyUI-Pixaroma |
| [flux-2-klein-9b-short-ideas-into-finished-images-qwen-3.5-ai-prompt](Prompt-Batching-and-Variations/flux-2-klein-9b-short-ideas-into-finished-images-qwen-3.5-ai-prompt.json) | Short Ideas into Finished Images (Qwen 3.5 AI Prompt) | ComfyUI-Pixaroma |
| [flux-2-klein-9b-short-story-to-storyboard-qwen-3.5-ai-prompt](Prompt-Batching-and-Variations/flux-2-klein-9b-short-story-to-storyboard-qwen-3.5-ai-prompt.json) | Short Story to Storyboard (Qwen 3.5 AI Prompt) | ComfyUI-Pixaroma |
| [pixaroma-nodes-prompt-multi-from-list](Prompt-Batching-and-Variations/pixaroma-nodes-prompt-multi-from-list.json) | Prompt Multi — From List | ComfyUI-Pixaroma |
| [pixaroma-nodes-prompt-multi-queue-text](Prompt-Batching-and-Variations/pixaroma-nodes-prompt-multi-queue-text.json) | Prompt Multi — Queue Text | ComfyUI-Pixaroma |
| [pixaroma-nodes-prompt-pack-line](Prompt-Batching-and-Variations/pixaroma-nodes-prompt-pack-line.json) | Prompt Pack — Line | ComfyUI-Pixaroma |
| [pixaroma-nodes-prompt-pack-paragraph](Prompt-Batching-and-Variations/pixaroma-nodes-prompt-pack-paragraph.json) | Prompt Pack — Paragraph | ComfyUI-Pixaroma |
| [pixaroma-nodes-prompt-stack](Prompt-Batching-and-Variations/pixaroma-nodes-prompt-stack.json) | Prompt Stack | ComfyUI-Pixaroma |
| [z-image-turbo-prompt-multi-queue-text](Prompt-Batching-and-Variations/z-image-turbo-prompt-multi-queue-text.json) | Prompt Multi — Queue Text | ComfyUI-Pixaroma |
| [z-image-turbo-prompt-pack-line](Prompt-Batching-and-Variations/z-image-turbo-prompt-pack-line.json) | Prompt Pack — Line | ComfyUI-Pixaroma |
| [z-image-turbo-prompt-pack-paragraph](Prompt-Batching-and-Variations/z-image-turbo-prompt-pack-paragraph.json) | Prompt Pack — Paragraph | ComfyUI-Pixaroma |
| [z-image-turbo-prompt-stack](Prompt-Batching-and-Variations/z-image-turbo-prompt-stack.json) | Prompt Stack | ComfyUI-Pixaroma |

### Text-to-image (txt2img) generation

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [anima-base-v1.0-anime-txt2img-seedvr2-upscale](Text-to-Image/anima-base-v1.0-anime-txt2img-seedvr2-upscale.json) | Anime Text to Image + SeedVR2 Upscale | ComfyUI-SeedVR2_VideoUpscaler, ComfyUI-Pixaroma |
| [anima-base-v1.0-anime-txt2img](Text-to-Image/anima-base-v1.0-anime-txt2img.json) | Anime Text to Image | ComfyUI-Pixaroma |
| [boogu-image-txt2img](Text-to-Image/boogu-image-txt2img.json) | Text to Image | ComfyUI-Pixaroma |
| [ernie-image-turbo-txt2img-gguf](Text-to-Image/ernie-image-turbo-txt2img-gguf.json) | Text to Image — GGUF | ComfyUI-GGUF, ComfyUI-Pixaroma |
| [flux-2-klein-4b-fp8-distilled-txt2img-basic](Text-to-Image/flux-2-klein-4b-fp8-distilled-txt2img-basic.json) | Text to Image — Basic | Core only |
| [flux-2-klein-9b-fp8-distilled-txt2img-basic](Text-to-Image/flux-2-klein-9b-fp8-distilled-txt2img-basic.json) | Text to Image — Basic | Core only |
| [flux-2-klein-9b-fp8-txt2img-ep16](Text-to-Image/flux-2-klein-9b-fp8-txt2img-ep16.json) | Text to Image (Ep16) | ComfyUI-Pixaroma |
| [flux-2-klein-9b-txt2img](Text-to-Image/flux-2-klein-9b-txt2img.json) | Text to Image | ComfyUI-Pixaroma |
| [flux-3-klein-layout-with-boxes](Text-to-Image/flux-3-klein-layout-with-boxes.json) | Layout with Boxes | ComfyUI-Pixaroma |
| [flux-3-klein-txt2img-z-image-realism-pass](Text-to-Image/flux-3-klein-txt2img-z-image-realism-pass.json) | Text to Image + Z-Image Realism Pass | ComfyUI-Pixaroma |
| [flux-3-klein-txt2img](Text-to-Image/flux-3-klein-txt2img.json) | Text to Image | ComfyUI-Pixaroma |
| [krea-2-int8-txt2img-extra-pass-lora](Text-to-Image/krea-2-int8-txt2img-extra-pass-lora.json) | Text to Image + Extra Pass + LoRA | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma, rgthree-comfy |
| [krea-2-int8-txt2img-extra-pass](Text-to-Image/krea-2-int8-txt2img-extra-pass.json) | Text to Image + Extra Pass | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-int8-txt2img-simple-lora](Text-to-Image/krea-2-int8-txt2img-simple-lora.json) | Text to Image — Simple + LoRA | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma, rgthree-comfy |
| [krea-2-int8-txt2img-simple](Text-to-Image/krea-2-int8-txt2img-simple.json) | Text to Image — Simple | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-2k-hi-res-prompt-enhancer-uncensored](Text-to-Image/krea-2-txt2img-2k-hi-res-prompt-enhancer-uncensored.json) | Text to Image — 2K Hi-Res + Prompt Enhancer (Uncensored) | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-2k-hi-res-prompt-enhancer](Text-to-Image/krea-2-txt2img-2k-hi-res-prompt-enhancer.json) | Text to Image — 2K Hi-Res + Prompt Enhancer | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-ep28](Text-to-Image/krea-2-txt2img-ep28.json) | Text to Image (Ep28) | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-extra-pass-lora](Text-to-Image/krea-2-txt2img-extra-pass-lora.json) | Text to Image + Extra Pass + LoRA | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma, rgthree-comfy |
| [krea-2-txt2img-extra-pass](Text-to-Image/krea-2-txt2img-extra-pass.json) | Text to Image + Extra Pass | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-simple-lora](Text-to-Image/krea-2-txt2img-simple-lora.json) | Text to Image — Simple + LoRA | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma, rgthree-comfy |
| [krea-2-txt2img-simple-low-vram](Text-to-Image/krea-2-txt2img-simple-low-vram.json) | Text to Image — Simple — Low VRAM | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [krea-2-txt2img-simple](Text-to-Image/krea-2-txt2img-simple.json) | Text to Image — Simple | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma |
| [lens-txt2img](Text-to-Image/lens-txt2img.json) | Text to Image | ComfyUI-Pixaroma |
| [ming-image-0.1-txt2img](Text-to-Image/ming-image-0.1-txt2img.json) | Text to Image | ComfyUI-Pixaroma |
| [minimax-h3-txt2img-single-frame](Text-to-Image/minimax-h3-txt2img-single-frame.json) | Text to Image (Single Frame) | ComfyUI-Pixaroma |
| [nunchaku-flux.1-dev-txt2img](Text-to-Image/nunchaku-flux.1-dev-txt2img.json) | Flux.1 Dev — Text to Image | ComfyUI-GGUF, ComfyUI-nunchaku |
| [nunchaku-qwen-image-lightning-txt2img](Text-to-Image/nunchaku-qwen-image-lightning-txt2img.json) | Qwen Image Lightning — Text to Image | ComfyUI-nunchaku |
| [nunchaku-z-image-turbo-txt2img](Text-to-Image/nunchaku-z-image-turbo-txt2img.json) | Z-Image Turbo — Text to Image | ComfyUI-nunchaku |
| [qwen-image-2.1-txt2img-low-vram](Text-to-Image/qwen-image-2.1-txt2img-low-vram.json) | Text to Image — Low VRAM | ComfyUI-Pixaroma |
| [qwen-image-2.1-txt2img-turbo](Text-to-Image/qwen-image-2.1-txt2img-turbo.json) | Text to Image — Turbo | ComfyUI-Pixaroma |
| [qwen-image-2.1-txt2img](Text-to-Image/qwen-image-2.1-txt2img.json) | Text to Image | ComfyUI-Pixaroma |
| [sd15-juggernaut-reborn-txt2img-lora-starter](Text-to-Image/sd15-juggernaut-reborn-txt2img-lora-starter.json) | SD 1.5 text-to-image with Juggernaut Reborn plus a style LoRA (ComfyUI-Easy-Install starter version) | Core only |
| [sd15-juggernaut-reborn-txt2img-lora](Text-to-Image/sd15-juggernaut-reborn-txt2img-lora.json) | Text to Image + LoRA | Core only |
| [sd15-juggernaut-reborn-txt2img](Text-to-Image/sd15-juggernaut-reborn-txt2img.json) | Text to Image | Core only |
| [z-image-turbo-int8-txt2img](Text-to-Image/z-image-turbo-int8-txt2img.json) | Text to Image | ComfyUI-Pixaroma |
| [z-image-turbo-txt2img-character-sheet-alt-1](Text-to-Image/z-image-turbo-txt2img-character-sheet-alt-1.json) | Z-Image Turbo character sheet, alternate prompt/settings | Core only |
| [z-image-turbo-txt2img-character-sheet-alt-2](Text-to-Image/z-image-turbo-txt2img-character-sheet-alt-2.json) | Z-Image Turbo character sheet, alternate prompt/settings | Core only |
| [z-image-turbo-txt2img-character-sheet](Text-to-Image/z-image-turbo-txt2img-character-sheet.json) | Z-Image Turbo character sheet (based on the official ComfyUI Z-Image template) | Core only |
| [z-image-turbo-txt2img-fp8-aio-checkpoint](Text-to-Image/z-image-turbo-txt2img-fp8-aio-checkpoint.json) | Text to Image — FP8 AIO Checkpoint | Core only |
| [z-image-turbo-txt2img-fp8-aio-lora](Text-to-Image/z-image-turbo-txt2img-fp8-aio-lora.json) | Text to Image — FP8 AIO + LoRA | Core only |
| [z-image-turbo-txt2img-fp8-aio-starter](Text-to-Image/z-image-turbo-txt2img-fp8-aio-starter.json) | Z-Image Turbo text-to-image from one FP8 all-in-one checkpoint (ComfyUI-Easy-Install starter version) | Core only |
| [z-image-turbo-txt2img-fp8-ep18](Text-to-Image/z-image-turbo-txt2img-fp8-ep18.json) | Text to Image — FP8 (Ep18) | ComfyUI-Pixaroma |
| [z-image-turbo-txt2img-fp8](Text-to-Image/z-image-turbo-txt2img-fp8.json) | Text to Image — FP8 | Core only |
| [z-image-turbo-txt2img-gguf](Text-to-Image/z-image-turbo-txt2img-gguf.json) | Text to Image — GGUF | ComfyUI-GGUF |

See the [main README](../README.md) for models used, setup steps and the full catalog.
