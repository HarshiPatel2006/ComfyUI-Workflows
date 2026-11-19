# Frame Interpolation — ComfyUI workflows

Increase frame rate / smooth motion by synthesising in-between frames. These are post-processing tools, not video generators.

[← Back to 04-Video](../README.md)

## Workflows (3)

None of these workflows has been runtime-tested: each was only checked to be valid JSON, a real ComfyUI graph, and right for its model and task. Each JSON is copied unchanged from the source linked below. Licences are as published upstream; check the model card before commercial use.

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [film-frame-interpolation-core-nodes](film-frame-interpolation-core-nodes.json) | FILM interpolation with built-in ComfyUI nodes (Frame Interpolation Model Loader → Frame Interpolate), keeps audio | `film_net_fp16.safetensors` | — (core ComfyUI) |
| [film-frame-interpolation-vfi-node-pack](film-frame-interpolation-vfi-node-pack.json) | FILM interpolation with the ComfyUI-Frame-Interpolation pack; the same pack has drop-in RIFE, IFRNet, AMT, GMFSS Fortuna, CAIN and other VFI nodes | `film_net_fp32.pt` (auto-downloaded by the node) | ComfyUI-Frame-Interpolation, ComfyUI-VideoHelperSuite |
| [gimm-vfi-frame-interpolation](gimm-vfi-frame-interpolation.json) | GIMM-VFI arbitrary-timestep interpolation (implicit motion modelling), output fps = input fps × factor | `gimmvfi_r_arb_lpips_fp32.safetensors` | ComfyUI-GIMM-VFI, ComfyUI-VideoHelperSuite |

## Sources, downloads and licences

| Workflow | Workflow source (code licence) | Model download | Model-weight licence |
|---|---|---|---|
| film-frame-interpolation-core-nodes | [Comfy-Org/workflow_templates `utility_video_frame_interpolation`](https://github.com/Comfy-Org/workflow_templates) (MIT) | [Comfy-Org/frame_interpolation](https://huggingface.co/Comfy-Org/frame_interpolation) | FILM: Apache-2.0 ([google-research/frame-interpolation](https://github.com/google-research/frame-interpolation)) |
| film-frame-interpolation-vfi-node-pack | [Comfy-Org/workflow_templates `utility-frame_interpolation-film`](https://github.com/Comfy-Org/workflow_templates) (MIT) | [Fannovel16/ComfyUI-Frame-Interpolation](https://github.com/Fannovel16/ComfyUI-Frame-Interpolation) (node pack MIT, downloads weights) | FILM: Apache-2.0 |
| gimm-vfi-frame-interpolation | [Comfy-Org/workflow_templates `utility_gimm_frame_interpolation`](https://github.com/Comfy-Org/workflow_templates) (MIT) | [Kijai/GIMM-VFI_safetensors](https://huggingface.co/Kijai/GIMM-VFI_safetensors) via [kijai/ComfyUI-GIMM-VFI](https://github.com/kijai/ComfyUI-GIMM-VFI) | **Not stated on the model page — unverified**; check [GSean/GIMM-VFI](https://github.com/GSean/GIMM-VFI) before commercial use |

## No ComfyUI workflow found

| Model (Open Video Model Atlas) | Why there is no workflow here |
|---|---|
| RIFE (4.22 lite, 4.7, 4.10, arbitrary timestep) | Supported by the `RIFE VFI` node in ComfyUI-Frame-Interpolation (swap the FILM node in the file above), but no redistributable stand-alone RIFE workflow JSON was found from an official or clearly licensed source |
| IFRNet, AMT, GMFSS Fortuna | Same as RIFE: nodes exist in ComfyUI-Frame-Interpolation (`IFRNet VFI`, `AMT VFI`, `GMFSS Fortuna VFI`); no published workflow file |
| DAIN | Legacy CUDA build; no maintained ComfyUI node |
| VRT video interpolation | No maintained ComfyUI node |
