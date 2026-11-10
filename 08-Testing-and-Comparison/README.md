# Testing and Comparison — ComfyUI workflows

XY plots for samplers, steps, styles and LoRAs, draft-then-finish preview gates and side-by-side image comparison.

## Workflows (8)

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [flux-2-klein-9b-draft-first-then-finish-preview-gate](flux-2-klein-9b-draft-first-then-finish-preview-gate.json) | Draft First, Then Finish (Preview Gate) | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-xy-plot-steps-and-samplers](flux-2-klein-9b-xy-plot-steps-and-samplers.json) | XY Plot — Steps and Samplers | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [flux-2-klein-9b-xy-plot-styles-and-subjects](flux-2-klein-9b-xy-plot-styles-and-subjects.json) | XY Plot — Styles and Subjects | `flux-2-klein-9b-int8-convrot.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-Pixaroma |
| [krea-2-int8-lora-xy-plot](krea-2-int8-lora-xy-plot.json) | LoRA XY Plot | `qwen_image_vae.safetensors`, `qwen3vl_4b_fp8_scaled.safetensors`, `krea2_turbo_int8_convrot.safetensors` +1 more | ComfyUI-Krea2T-Enhancer, ComfyUI-Pixaroma, rgthree-comfy |
| [pixaroma-nodes-group-compare-comfyui-vs-pixaroma](pixaroma-nodes-group-compare-comfyui-vs-pixaroma.json) | Group Compare (ComfyUI vs Pixaroma) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-image-compare](pixaroma-nodes-image-compare.json) | Image Compare | — | ComfyUI-Pixaroma |
| [utility-image-compare-side-by-side](utility-image-compare-side-by-side.json) | Image Compare (Side by Side) | — | ComfyUI-RMBG, ComfyUI-iTools, rgthree-comfy |
| [z-image-turbo-xy-plot](z-image-turbo-xy-plot.json) | XY Plot | `z-image-turbo_fp8_scaled_e5m2_KJ.safetensors`, `ae.safetensors`, `qwen_3_4b_fp8_mixed.safetensors` | ComfyUI-Pixaroma |

See the [main README](../README.md) for setup steps, requirements and the other categories, or [`00-LIBRARY-INDEX.md`](../00-LIBRARY-INDEX.md) for the full list of workflows.
