# Version conflicts to review

Each file here is the **original Pixaroma version** of a workflow that already exists in the library.
The library copy and this copy have the same graph (same nodes and connections) but different settings.
Neither file was overwritten. Keep whichever you prefer and delete the other.

| File here | Library copy | What differs |
|---|---|---|
| Ep11 - Flux 2 Klein 9B FP8 (Distilled) - One Image Edit with Paint Pixaroma Node | 02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/Flux 2 Klein 9B FP8 (Distilled) - Paint-Guided Edit | Model path `flux2\` (original) vs `flux/` (library), seed, painted canvas |
| Ep15 - ACE-Step v1.5 XL Turbo - Text to Music | 05-Audio/Music-Generation/ACE-Step v1.5 XL Turbo - Text to Music | Model path `acestep\` subfolder (original) vs root (library); prompt, duration 120 vs 20 |
| Ep16 - Flux 2 Klein 9B - Image to Prompt to Image (Qwen 3.5) | 01-Image-Generation/LLM-Prompt-Assisted/Flux 2 Klein 9B - Image to Prompt to Image (Qwen 3.5) | Input image, seed, last generated prompt text |
| Ep16 - Flux 2 Klein 9B - Text to Image + Qwen 3.5 Prompt Enhancer | 01-Image-Generation/LLM-Prompt-Assisted/Flux 2 Klein 9B - Text to Image + Qwen 3.5 Prompt Enhancer | Model path `flux2\` (original) vs root (library), seed, generated prompt text |
| Ep20 - Anima Base v1.0 - Anime Text to Image + Gemma 4 Prompt Enhancer | 01-Image-Generation/LLM-Prompt-Assisted/Anima Base v1.0 - Anime Text to Image + Gemma 4 Prompt Enhancer | Model path `anima\` subfolder (original) vs root (library), prompt text, seed |
