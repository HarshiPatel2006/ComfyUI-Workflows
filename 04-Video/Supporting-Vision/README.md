# Supporting Vision — ComfyUI workflows

Per-video analysis passes that feed other video workflows: depth maps, segmentation masks, pose skeletons, line art and surface normals. These are **not video generation models** and are counted separately from them.

[← Back to 04-Video](../README.md)

## Workflows (9)

None of these workflows has been runtime-tested: each was only checked to be valid JSON, a real ComfyUI graph, and right for its model and task. Each JSON is copied unchanged from the source linked below. Licences are as published upstream; several depth models are **non-commercial** — check the model card before commercial use.

### Depth

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [video-depth-anything-depth-maps](video-depth-anything-depth-maps.json) | Video Depth Anything: temporally consistent depth for long videos, saves video and EXR | `video_depth_anything_vitl.pth` | ComfyUI-Video-Depth-Anything, ComfyUI-VideoHelperSuite |
| [depth-anything-3-video-depth](depth-anything-3-video-depth.json) | Depth Anything 3 (mono large) depth on video frames with built-in DA3 nodes | `depth_anything_3_mono_large.safetensors` | — (core ComfyUI) |
| [depth-anything-v2-video-depth](depth-anything-v2-video-depth.json) | Depth Anything V2 relative depth, frame by frame | `depth_anything_v2_vitl_fp32.safetensors` | ComfyUI-DepthAnythingV2, ComfyUI-VideoHelperSuite |

### Segmentation and masks

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [sam3-video-text-prompt-segmentation](sam3-video-text-prompt-segmentation.json) | SAM 3.1 video masks from a text prompt (e.g. `person:2`) with built-in nodes | `sam3.1_multiplex_fp16.safetensors` | — (core ComfyUI) |
| [sam2-points-video-segmentation](sam2-points-video-segmentation.json) | SAM 2 click-point segmentation propagated through a video | `sam2_hiera_base_plus.safetensors` | ComfyUI-segment-anything-2, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-Custom-Scripts |

### Pose, line art and normals

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [dwpose-video-pose-extraction](dwpose-video-pose-extraction.json) | DWPose (OpenPose-style) skeletons for every frame | `dw-ll_ucoco_384_bs5.torchscript.pt`, `yolox_l.onnx` | comfyui_controlnet_aux, ComfyUI-VideoHelperSuite |
| [sdpose-multi-person-video-pose](sdpose-multi-person-video-pose.json) | SDPose whole-body keypoints for several people (RT-DETR person detection) | `sdpose_wholebody_fp16.safetensors`, `rt_detr_v4-x-hgnet_fp16.safetensors` | — (core ComfyUI) |
| [lineart-video-extraction](lineart-video-extraction.json) | Line-art control maps for every frame | Annotators `sk_model.pth` (auto-downloaded) | comfyui_controlnet_aux, ComfyUI-VideoHelperSuite |
| [normalcrafter-video-normals](normalcrafter-video-normals.json) | NormalCrafter temporally consistent surface-normal video | NormalCrafter (auto-downloaded) | ComfyUI-NormalCrafterWrapper, ComfyUI-VideoHelperSuite |

## Sources, downloads and licences

| Workflow | Workflow source (code licence) | Model download | Model-weight licence |
|---|---|---|---|
| video-depth-anything-depth-maps | [yuvraj108c/ComfyUI-Video-Depth-Anything](https://github.com/yuvraj108c/ComfyUI-Video-Depth-Anything) (Apache-2.0) | [depth-anything/Video-Depth-Anything-Large](https://huggingface.co/depth-anything/Video-Depth-Anything-Large) / [-Small](https://huggingface.co/depth-anything/Video-Depth-Anything-Small) | Large: **CC-BY-NC-4.0 (non-commercial)**; Small: Apache-2.0 |
| depth-anything-3-video-depth | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates) (MIT) | [Comfy-Org/Depth-Anything-3](https://huggingface.co/Comfy-Org/Depth-Anything-3) | Apache-2.0 (mono large) |
| depth-anything-v2-video-depth | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates) (MIT) | [Kijai/DepthAnythingV2-safetensors](https://huggingface.co/Kijai/DepthAnythingV2-safetensors) | ViT-L: **CC-BY-NC-4.0 (non-commercial)**; ViT-S: Apache-2.0 |
| sam3-video-text-prompt-segmentation | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates) (MIT) | [Comfy-Org/sam3.1](https://huggingface.co/Comfy-Org/sam3.1) | **SAM License (custom Meta licence)** |
| sam2-points-video-segmentation | [kijai/ComfyUI-segment-anything-2](https://github.com/kijai/ComfyUI-segment-anything-2) (Apache-2.0) | [Kijai/sam2-safetensors](https://huggingface.co/Kijai/sam2-safetensors) | Apache-2.0 |
| dwpose-video-pose-extraction | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates) (MIT) | [yzd-v/DWPose](https://huggingface.co/yzd-v/DWPose) | Apache-2.0 |
| sdpose-multi-person-video-pose | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates) (MIT) | [Comfy-Org/SDPose](https://huggingface.co/Comfy-Org/SDPose) | SDPose: MIT; RT-DETR: check upstream |
| lineart-video-extraction | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates) (MIT) | [lllyasviel/Annotators](https://huggingface.co/lllyasviel/Annotators) | Custom ("other") — check model card |
| normalcrafter-video-normals | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates) (MIT) | [Yanrui95/NormalCrafter](https://huggingface.co/Yanrui95/NormalCrafter) | Apache-2.0 |

## No ComfyUI workflow found

| Model (Open Video Model Atlas) | Why there is no workflow here |
|---|---|
| Video Depth Anything Metric (Small / Large) | Same node pack; metric checkpoints are a model swap in the graph above, no separate workflow |
| CoTracker 2 / 3 | Community nodes exist (`comfyui_cotracker_node`, no licence file); only personal-project workflows found, none redistributable from an official source |
| XMem, DeAOT | No maintained ComfyUI node or workflow |
| RAFT, GMFlow | Used internally by other node packs; no stand-alone ComfyUI workflow |
