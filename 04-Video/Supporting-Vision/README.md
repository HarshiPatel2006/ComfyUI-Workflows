# Supporting Vision for Video — ComfyUI workflows

Per-frame analysis that feeds the control and editing workflows: video depth and normals, pose and line-art extraction, and video segmentation. These are not generation models.

[← 04-Video overview](../README.md) · [Atlas coverage tracker](../COVERAGE.md)

| Subfolder | What is inside | Workflows |
|---|---|---|
| [`Depth-and-Normals/`](Depth-and-Normals) | Video depth maps and surface normals | 4 |
| [`Pose-and-Line-Art/`](Pose-and-Line-Art) | Pose skeletons and line art from video | 3 |
| [`Segmentation/`](Segmentation) | Video object segmentation and masks | 2 |

## Workflows (9)

The workflow JSONs added from the Open-Source Video Model Atlas (Nov 2026) are unmodified copies of published workflows. Each was checked only to be valid JSON, a genuine ComfyUI graph, and right for its model and task; **none has been runtime-tested in this library.** No model weights are included. The **model-weight licence is separate from the workflow (code) licence**; several weights are **non-commercial or carry custom terms** (marked below), so read the model card before commercial use. Workflows without a source row are original library workflows (Pixaroma tutorial episodes, Benji's AI Playground, or the library author's own MiniMax H3 / SeedVR2 runs); see the [root README credits](../../README.md#credits).

### Depth and Normals (4)

Video depth maps and surface normals.

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [depth-anything-3-video-depth](Depth-and-Normals/depth-anything-3-video-depth.json) | Depth Anything 3 (mono large) depth on video frames with built-in DA3 nodes | `depth_anything_3_mono_large.safetensors` | — (core ComfyUI) |
| [depth-anything-v2-video-depth](Depth-and-Normals/depth-anything-v2-video-depth.json) | Depth Anything V2 relative depth, frame by frame | `depth_anything_v2_vitl_fp32.safetensors` | ComfyUI-DepthAnythingV2, ComfyUI-VideoHelperSuite |
| [normalcrafter-video-normals](Depth-and-Normals/normalcrafter-video-normals.json) | NormalCrafter temporally consistent surface-normal video | NormalCrafter (auto-downloaded) | ComfyUI-NormalCrafterWrapper, ComfyUI-VideoHelperSuite |
| [video-depth-anything-depth-maps](Depth-and-Normals/video-depth-anything-depth-maps.json) | Video Depth Anything: temporally consistent depth for long videos, saves video and EXR | `video_depth_anything_vitl.pth` | ComfyUI-Video-Depth-Anything, ComfyUI-VideoHelperSuite |

### Pose and Line Art (3)

Pose skeletons and line art from video.

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [dwpose-video-pose-extraction](Pose-and-Line-Art/dwpose-video-pose-extraction.json) | DWPose (OpenPose-style) skeletons for every frame | `dw-ll_ucoco_384_bs5.torchscript.pt`, `yolox_l.onnx` | comfyui_controlnet_aux, ComfyUI-VideoHelperSuite |
| [lineart-video-extraction](Pose-and-Line-Art/lineart-video-extraction.json) | Line-art control maps for every frame | Annotators `sk_model.pth` (auto-downloaded) | comfyui_controlnet_aux, ComfyUI-VideoHelperSuite |
| [sdpose-multi-person-video-pose](Pose-and-Line-Art/sdpose-multi-person-video-pose.json) | SDPose whole-body keypoints for several people (RT-DETR person detection) | `sdpose_wholebody_fp16.safetensors`, `rt_detr_v4-x-hgnet_fp16.safetensors` | — (core ComfyUI) |

### Segmentation (2)

Video object segmentation and masks.

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [sam2-points-video-segmentation](Segmentation/sam2-points-video-segmentation.json) | SAM 2 click-point segmentation propagated through a video | `sam2_hiera_base_plus.safetensors` | ComfyUI-segment-anything-2, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-Custom-Scripts |
| [sam3-video-text-prompt-segmentation](Segmentation/sam3-video-text-prompt-segmentation.json) | SAM 3.1 video masks from a text prompt (e.g. `person:2`) with built-in nodes | `sam3.1_multiplex_fp16.safetensors` | — (core ComfyUI) |

## Sources, model weights and licences

9 of these workflows were added from the atlas. Code licence = licence of the repository the JSON was copied from; weight licence = licence of the model the workflow loads.

| Workflow | Source | Code licence | Model weights | Weight licence | Status |
|---|---|---|---|---|---|
| [depth-anything-3-video-depth](Depth-and-Normals/depth-anything-3-video-depth.json) | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates) | MIT | [Comfy-Org/Depth-Anything-3](https://huggingface.co/Comfy-Org/Depth-Anything-3) | Apache-2.0 (mono large) | not runtime-tested |
| [depth-anything-v2-video-depth](Depth-and-Normals/depth-anything-v2-video-depth.json) | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates) | MIT | [Kijai/DepthAnythingV2-safetensors](https://huggingface.co/Kijai/DepthAnythingV2-safetensors) | ViT-L: **CC-BY-NC-4.0 (non-commercial)**; ViT-S: Apache-2.0 | not runtime-tested |
| [normalcrafter-video-normals](Depth-and-Normals/normalcrafter-video-normals.json) | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates) | MIT | [Yanrui95/NormalCrafter](https://huggingface.co/Yanrui95/NormalCrafter) | Apache-2.0 | not runtime-tested |
| [video-depth-anything-depth-maps](Depth-and-Normals/video-depth-anything-depth-maps.json) | [yuvraj108c/ComfyUI-Video-Depth-Anything](https://github.com/yuvraj108c/ComfyUI-Video-Depth-Anything) | Apache-2.0 | [depth-anything/Video-Depth-Anything-Large](https://huggingface.co/depth-anything/Video-Depth-Anything-Large) / [-Small](https://huggingface.co/depth-anything/Video-Depth-Anything-Small) | Large: **CC-BY-NC-4.0 (non-commercial)**; Small: Apache-2.0 | not runtime-tested |
| [dwpose-video-pose-extraction](Pose-and-Line-Art/dwpose-video-pose-extraction.json) | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates) | MIT | [yzd-v/DWPose](https://huggingface.co/yzd-v/DWPose) | Apache-2.0 | not runtime-tested |
| [lineart-video-extraction](Pose-and-Line-Art/lineart-video-extraction.json) | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates) | MIT | [lllyasviel/Annotators](https://huggingface.co/lllyasviel/Annotators) | Custom ("other") — check model card | not runtime-tested |
| [sdpose-multi-person-video-pose](Pose-and-Line-Art/sdpose-multi-person-video-pose.json) | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates) | MIT | [Comfy-Org/SDPose](https://huggingface.co/Comfy-Org/SDPose) | SDPose: MIT; RT-DETR: check upstream | not runtime-tested |
| [sam2-points-video-segmentation](Segmentation/sam2-points-video-segmentation.json) | [kijai/ComfyUI-segment-anything-2](https://github.com/kijai/ComfyUI-segment-anything-2) | Apache-2.0 | [Kijai/sam2-safetensors](https://huggingface.co/Kijai/sam2-safetensors) | Apache-2.0 | not runtime-tested |
| [sam3-video-text-prompt-segmentation](Segmentation/sam3-video-text-prompt-segmentation.json) | [Comfy-Org/workflow_templates](https://github.com/Comfy-Org/workflow_templates) | MIT | [Comfy-Org/sam3.1](https://huggingface.co/Comfy-Org/sam3.1) | **SAM License (custom Meta licence)** | not runtime-tested |

## Atlas entries with no separate workflow here

Entries of the Open-Source Video Model Atlas for this category that did not get their own workflow. "Equivalent already exists" means an existing workflow already covers the model and task (usually a checkpoint, size or quantisation swap); nothing was fabricated for the others. Full per-entry status: [COVERAGE.md](../COVERAGE.md).

| Family | Entry | Status | Notes |
|---|---|---|---|
| Video Depth Anything | Video Depth Anything Base | equivalent already exists | checkpoint swap in same graph |
| Video Depth Anything | Video Depth Anything Metric Small | equivalent already exists | checkpoint swap in same graph |
| Video Depth Anything | Video Depth Anything Metric Large | equivalent already exists | checkpoint swap in same graph |
| CoTracker | CoTracker2 | availability or redistribution unconfirmed | s9roll7/comfyui_cotracker_node has no licence; only personal-project JSON (CreativeInquiry/ComfyCV) found |
| CoTracker | CoTracker3 | availability or redistribution unconfirmed | same as above |
| XMem / DeAOT | XMem long-term video masks | no suitable ComfyUI workflow | no maintained node |
| XMem / DeAOT | DeAOT object tracking masks | no suitable ComfyUI workflow | no maintained node |
| RAFT / GMFlow | RAFT optical flow | no suitable ComfyUI workflow | internal to other packs only |
| RAFT / GMFlow | GMFlow optical flow | no suitable ComfyUI workflow | no node |
