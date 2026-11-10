# Docs and Resources — ComfyUI workflows

Learning workflows and node demos, LoRA training notes, LLM prompt-assistant instructions and sample input media.

Contents:

- `Learning-and-Node-Demos/`: beginner workflows and demos of individual nodes
- `LoRA-Training/`: Krea 2 LoRA converter workflow and fal.ai training settings
- `LLM-Prompt-Assistants/`: instructions and knowledge files for ChatGPT, Claude and Gemini prompt assistants (MiniMax H3 video prompts)
- `Pixaroma-Episode-Resources/`: extra files that accompany specific tutorial episodes
- `Sample-Media-Inputs/`: example images, audio and prompt files used by the workflows
- `Library-Maintenance/`: manifests from earlier library reorganizations

| Subfolder | What is inside | Workflows |
|---|---|---|
| [`Learning-and-Node-Demos/`](Learning-and-Node-Demos) | Learning workflows and node demos | 14 |
| [`LoRA-Training/`](LoRA-Training) | LoRA conversion and training | 1 |

## Workflows (15)

### Learning workflows and node demos

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [flux-2-klein-9b-fp8-multi-step-workflow-example](Learning-and-Node-Demos/flux-2-klein-9b-fp8-multi-step-workflow-example.json) | Multi-Step Workflow Example | `flux-2-klein-9b-fp8mixed.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors` | ComfyUI-RMBG, ComfyUI_LayerStyle, rgthree-comfy |
| [nodes-explained-01-models-explained-finished-z-image-turbo](Learning-and-Node-Demos/nodes-explained-01-models-explained-finished-z-image-turbo.json) | Models Explained — Finished (Z-Image Turbo) | `z_image_turbo_int8_convrot.safetensors`, `qwen_3_4b_fp8_mixed.safetensors`, `ae.safetensors` | Core only |
| [nodes-explained-01-models-explained-practice-z-image-turbo](Learning-and-Node-Demos/nodes-explained-01-models-explained-practice-z-image-turbo.json) | Models Explained — Practice (Z-Image Turbo) | `qwen_3_4b_fp8_mixed.safetensors`, `ae.safetensors` | Core only |
| [pixaroma-help-and-resources](Learning-and-Node-Demos/pixaroma-help-and-resources.json) | Help and Resources | — | Core only |
| [pixaroma-nodes-change-node-color](Learning-and-Node-Demos/pixaroma-nodes-change-node-color.json) | Change Node Color | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-labels-ep11](Learning-and-Node-Demos/pixaroma-nodes-labels-ep11.json) | Labels (Ep11) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-labels-ep13](Learning-and-Node-Demos/pixaroma-nodes-labels-ep13.json) | Labels (Ep13) | — | ComfyUI-Pixaroma |
| [pixaroma-nodes-note](Learning-and-Node-Demos/pixaroma-nodes-note.json) | Note | — | ComfyUI-Pixaroma |
| [nodes-explained-02-prompts-explained-finished-z-image-turbo](Learning-and-Node-Demos/nodes-explained-02-prompts-explained-finished-z-image-turbo.json) | Prompts Explained - Finished | `z_image_turbo_int8_convrot.safetensors`, `qwen_3_4b_fp8_mixed.safetensors`, `ae.safetensors` | Core only |
| [nodes-explained-02-prompts-explained-pixaroma-z-image-turbo](Learning-and-Node-Demos/nodes-explained-02-prompts-explained-pixaroma-z-image-turbo.json) | Prompts Explained - Pixaroma | `z_image_turbo_int8_convrot.safetensors`, `qwen_3_4b_fp8_mixed.safetensors`, `ae.safetensors` | ComfyUI-Pixaroma |
| [nodes-explained-02-prompts-explained-practice-z-image-turbo](Learning-and-Node-Demos/nodes-explained-02-prompts-explained-practice-z-image-turbo.json) | Prompts Explained - Practice | `z_image_turbo_int8_convrot.safetensors`, `qwen_3_4b_fp8_mixed.safetensors`, `ae.safetensors` | Core only |
| [nodes-explained-03-image-size-explained-finished-z-image-turbo](Learning-and-Node-Demos/nodes-explained-03-image-size-explained-finished-z-image-turbo.json) | Image Size Explained - Finished | `z_image_turbo_int8_convrot.safetensors`, `qwen_3_4b_fp8_mixed.safetensors`, `ae.safetensors` | Core only |
| [nodes-explained-03-image-size-explained-pixaroma-z-image-turbo](Learning-and-Node-Demos/nodes-explained-03-image-size-explained-pixaroma-z-image-turbo.json) | Image Size Explained - Pixaroma | `z_image_turbo_int8_convrot.safetensors`, `qwen_3_4b_fp8_mixed.safetensors`, `ae.safetensors` | ComfyUI-Pixaroma |
| [nodes-explained-03-image-size-explained-practice-z-image-turbo](Learning-and-Node-Demos/nodes-explained-03-image-size-explained-practice-z-image-turbo.json) | Image Size Explained - Practice | `z_image_turbo_int8_convrot.safetensors`, `qwen_3_4b_fp8_mixed.safetensors`, `ae.safetensors` | Core only |

### LoRA conversion and training

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [krea-2-lora-converter](LoRA-Training/krea-2-lora-converter.json) | LoRA Converter | `krea2-questpaint26.safetensors`, `krea2-questpaint26_comfyui.safetensors` | ComfyUI-Pixaroma |

See the [main README](../README.md) for setup steps, requirements and the other categories, or [`00-LIBRARY-INDEX.md`](../00-LIBRARY-INDEX.md) for the full list of workflows.
