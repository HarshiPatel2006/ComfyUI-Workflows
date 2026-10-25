# Version Conflicts — ComfyUI workflows

Original versions of workflows whose library copy has different settings, kept for comparison.

Each file here has the same graph (same nodes and connections) as a workflow in the main library but different settings. Neither copy was overwritten; keep whichever you prefer.

| File here | Library copy | What differs |
|---|---|---|
| [ep11-flux-2-klein-9b-fp8-distilled-one-image-edit-with-paint-pixaroma-node-pixaroma-original](ep11-flux-2-klein-9b-fp8-distilled-one-image-edit-with-paint-pixaroma-node-pixaroma-original.json) | [02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-fp8-distilled-paint-guided-edit](../02-Image-Editing/Inpaint-Outpaint-and-Object-Removal/flux-2-klein-9b-fp8-distilled-paint-guided-edit.json) | Model path `flux2\` (original) vs `flux/` (library), seed, painted canvas |
| [ep15-ace-step-v1.5-xl-turbo-text-to-music-pixaroma-original](ep15-ace-step-v1.5-xl-turbo-text-to-music-pixaroma-original.json) | [05-Audio/Music-Generation/ace-step-v1.5-xl-turbo-text-to-music](../05-Audio/Music-Generation/ace-step-v1.5-xl-turbo-text-to-music.json) | Model path `acestep\` subfolder (original) vs root (library); prompt, duration 120 vs 20 |
| [ep16-flux-2-klein-9b-image-to-prompt-to-image-qwen-3.5-pixaroma-original](ep16-flux-2-klein-9b-image-to-prompt-to-image-qwen-3.5-pixaroma-original.json) | [01-Image-Generation/LLM-Prompt-Assisted/flux-2-klein-9b-image-to-prompt-to-image-qwen-3.5](../01-Image-Generation/LLM-Prompt-Assisted/flux-2-klein-9b-image-to-prompt-to-image-qwen-3.5.json) | Input image, seed, last generated prompt text |
| [ep16-flux-2-klein-9b-txt2img-qwen-3.5-prompt-enhancer-pixaroma-original](ep16-flux-2-klein-9b-txt2img-qwen-3.5-prompt-enhancer-pixaroma-original.json) | [01-Image-Generation/LLM-Prompt-Assisted/flux-2-klein-9b-txt2img-qwen-3.5-prompt-enhancer](../01-Image-Generation/LLM-Prompt-Assisted/flux-2-klein-9b-txt2img-qwen-3.5-prompt-enhancer.json) | Model path `flux2\` (original) vs root (library), seed, generated prompt text |
| [ep20-anima-base-v1.0-anime-txt2img-gemma-4-prompt-enhancer-pixaroma-original](ep20-anima-base-v1.0-anime-txt2img-gemma-4-prompt-enhancer-pixaroma-original.json) | [01-Image-Generation/LLM-Prompt-Assisted/anima-base-v1.0-anime-txt2img-gemma-4-prompt-enhancer](../01-Image-Generation/LLM-Prompt-Assisted/anima-base-v1.0-anime-txt2img-gemma-4-prompt-enhancer.json) | Model path `anima\` subfolder (original) vs root (library), prompt text, seed |

See the [main README](../README.md) for models used, setup steps and the full catalog.
