# Hy-Nomas World Model

Workflows for **Hy-Nomas**, Tencent's video world model: a video is generated segment by segment, and each segment continues the world from the cached memory of the earlier ones. The workflows are unmodified copies of the upstream ones.

**Custom node pack needed:** [ComfyUI-Hy-Nomas](https://github.com/PedroMarinhoDev/ComfyUI-Hy-Nomas) (node types `HyNomas*`). Model files come from [tencent/Hy-Nomas](https://huggingface.co/tencent/Hy-Nomas); each workflow's note lists the folders to put them in.

**Status:** work in progress upstream, so node names and workflows may change.

| Workflow | What it does |
|---|---|
| [hy-nomas-camera-control](hy-nomas-camera-control.json) | Generates the world segment by segment with camera keys and camera recording to steer the camera |
| [hy-nomas-drive-interactive](hy-nomas-drive-interactive.json) | Interactive drive: steer the world live from one node |
| [hy-nomas-start-from-image](hy-nomas-start-from-image.json) | Starts the world from a loaded image and generates the video from it |
| [hy-nomas-world-one-node](hy-nomas-world-one-node.json) | Generates a whole world from a text prompt with a single node |
| [hy-nomas-world-per-segment](hy-nomas-world-per-segment.json) | Generates the world one segment at a time, so each segment can be sampled and extended separately |

Models used (default names in the workflows): `hy_nomas_distil_int8.safetensors` (INT8 DiT), `hy_nomas_pixelumm_fp8.safetensors` (FP8 PixelUMM decoder; also the encoder in start-from-image), `qwen_2.5_vl_7b_fp8_scaled.safetensors` (text encoder).

## Source and licence

Source: [PedroMarinhoDev/ComfyUI-Hy-Nomas](https://github.com/PedroMarinhoDev/ComfyUI-Hy-Nomas), `workflows/` folder, main branch. Licensed under GPL-3.0; see the upstream repository for the full terms.
