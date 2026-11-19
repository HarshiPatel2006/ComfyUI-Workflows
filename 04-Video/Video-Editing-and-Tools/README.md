# Video Editing and Tools — ComfyUI workflows

Editing existing video and controlling new video: VACE reference/control/inpaint/outpaint, structure, camera and trajectory control, subject and identity reference, inpainting and object removal, relighting and instruction editing, plus simple clip tools.

## Workflows (18)

### VACE (Wan 2.1) (4)

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [wan-2.1-vace-14b-reference-to-video](wan-2.1-vace-14b-reference-to-video.json) | Reference-anything video: one or more reference images (subject, style) steer a new clip | Wan2.1 VACE 14B (1.3B optional) | core only |
| [wan-2.1-vace-14b-control-video-to-video](wan-2.1-vace-14b-control-video-to-video.json) | Video-to-video driven by a control video (Canny/depth/pose) plus a reference image | Wan2.1 VACE 14B | core only |
| [wan-2.1-vace-14b-video-inpainting](wan-2.1-vace-14b-video-inpainting.json) | Masked video-to-video: replace or remove an object inside a SAM 3.1 mask | Wan2.1 VACE 14B + SAM 3.1 | core only |
| [wan-2.1-vace-14b-video-outpainting](wan-2.1-vace-14b-video-outpainting.json) | Extend the frame of an existing video (pad and fill new borders) | Wan2.1 VACE 14B | core only |

### Structure, camera and motion control (4)

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [wan-2.2-fun-control-14b-pose-depth-canny](wan-2.2-fun-control-14b-pose-depth-canny.json) | Start image + control video (pose, depth or Canny) to a new video | Wan2.2 Fun Control A14B | core only |
| [wan-2.2-fun-camera-control-14b](wan-2.2-fun-camera-control-14b.json) | Image-to-video with preset camera moves (pan, zoom, orbit) | Wan2.2 Fun Control-Camera A14B | core only |
| [wan-move-480p-trajectory-motion-control](wan-move-480p-trajectory-motion-control.json) | Image-to-video with point-level motion trajectories drawn in the graph | Wan-Move 14B 480p | core only |
| [wan-2.1-recammaster-1.3b-camera-rerender-video](wan-2.1-recammaster-1.3b-camera-rerender-video.json) | Re-shoot an existing video along a new camera trajectory | ReCamMaster (Wan 2.1 1.3B) | ComfyUI-WanVideoWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite, ComfyUI-Florence2, ComfyUI-Custom-Scripts |

### Subject and identity reference (3)

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [wan-2.1-phantom-14b-multi-subject-to-video](wan-2.1-phantom-14b-multi-subject-to-video.json) | Subject-consistent video from up to four subject reference images | Phantom-Wan 14B (1.3B optional) | ComfyUI-WanVideoWrapper, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite |
| [wan-2.1-skyreels-a2-element-assembly-to-video](wan-2.1-skyreels-a2-element-assembly-to-video.json) | Compose a video from separate element images (people, objects, background) | SkyReels-A2 (Wan 2.1 14B) | ComfyUI-WanVideoWrapper, ComfyUI-KJNodes, ComfyUI_essentials, ComfyUI-VideoHelperSuite |
| [wan-2.1-stand-in-identity-reference-to-video](wan-2.1-stand-in-identity-reference-to-video.json) | Identity-preserving text-to-video from a single face photo | Stand-In LoRA (Wan 2.1 14B T2V) | ComfyUI-WanVideoWrapper, ComfyUI-KJNodes, ComfyUI_essentials, comfyui_controlnet_aux, ComfyUI-VideoHelperSuite |

### Inpainting and object removal (4)

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [propainter-video-object-removal](propainter-video-object-removal.json) | Flow-guided video inpainting: remove a masked object or complete missing regions | ProPainter | ComfyUI_ProPainter_Nodes, ComfyUI-VideoHelperSuite, ComfyUI_essentials |
| [void-video-object-and-interaction-removal](void-video-object-and-interaction-removal.json) | Remove an object and its physical effects (shadows, reflections, interactions) from a video | VOID (CogVideoX-based) + SAM 3.1 + RAFT | core only |
| [ltx-2.3-obscura-lora-prompt-object-removal](ltx-2.3-obscura-lora-prompt-object-removal.json) | Text-prompted object removal without drawing a mask | LTX-2.3 22B + Obscura Remova IC-LoRA | ComfyUI-LTXVideo, ComfyUI-KJNodes, ComfyUI-VideoHelperSuite |
| [ltx-2.3-lora-remove-subtitles-from-video](ltx-2.3-lora-remove-subtitles-from-video.json) | Remove burned-in subtitles and text overlays from your own footage | LTX-2.3 22B + subtitle-removal IC-LoRA | ComfyUI-LTXVideo, ComfyUI-KJNodes |

### Relighting and instruction editing (2)

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [wan-2.2-bernini-r-video-relighting](wan-2.2-bernini-r-video-relighting.json) | Relight an existing video from a lighting reference or prompt | Bernini-R (Wan 2.2 A14B) | core only |
| [capybara-v0.1-instruction-video-edit](capybara-v0.1-instruction-video-edit.json) | Edit a video with a plain-language instruction | Capybara v0.1 (HunyuanVideo 1.5 based) | core only |

### Clip tools (1)

| Workflow | Description | Model | Custom Nodes |
|---|---|---|---|
| [pixaroma-video-tools-join-clips](pixaroma-video-tools-join-clips.json) | Pixaroma video tools join clips | — | ComfyUI-Pixaroma |

## Sources, model downloads and licences

Workflow JSONs were copied unchanged from the sources below, whose code licences allow redistribution (Comfy-Org workflow_templates: MIT; ComfyUI-WanVideoWrapper: Apache-2.0; ComfyUI_ProPainter_Nodes: GPL-3.0). The **weight licence is separate** from the workflow/code licence. None of these workflows has been runtime-tested in this library: they were checked only for valid JSON, a genuine ComfyUI graph, the right model for the task and no duplicate in `04-Video`.

| Workflow | Source | Model download | Weight licence | Status |
|---|---|---|---|---|
| [wan-2.1-vace-14b-reference-to-video](wan-2.1-vace-14b-reference-to-video.json) | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan_vace_14B_ref2v.json) | [weights](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged) | Apache-2.0 | not runtime-tested |
| [wan-2.1-vace-14b-control-video-to-video](wan-2.1-vace-14b-control-video-to-video.json) | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan_vace_14B_v2v.json) | [weights](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged) | Apache-2.0 | not runtime-tested |
| [wan-2.1-vace-14b-video-inpainting](wan-2.1-vace-14b-video-inpainting.json) | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan_vace_inpainting.json) | [weights](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged) | Apache-2.0 | not runtime-tested |
| [wan-2.1-vace-14b-video-outpainting](wan-2.1-vace-14b-video-outpainting.json) | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan_vace_outpainting.json) | [weights](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged) | Apache-2.0 | not runtime-tested |
| [wan-2.2-fun-control-14b-pose-depth-canny](wan-2.2-fun-control-14b-pose-depth-canny.json) | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan2_2_14B_fun_control.json) | [weights](https://huggingface.co/alibaba-pai/Wan2.2-Fun-A14B-Control) | Apache-2.0 | not runtime-tested |
| [wan-2.2-fun-camera-control-14b](wan-2.2-fun-camera-control-14b.json) | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wan2_2_14B_fun_camera.json) | [weights](https://huggingface.co/alibaba-pai/Wan2.2-Fun-A14B-Control-Camera) | Apache-2.0 | not runtime-tested |
| [wan-move-480p-trajectory-motion-control](wan-move-480p-trajectory-motion-control.json) | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_wanmove_480p.json) | [weights](https://huggingface.co/Ruihang/Wan-Move-14B-480P) | Apache-2.0 | not runtime-tested |
| [wan-2.1-recammaster-1.3b-camera-rerender-video](wan-2.1-recammaster-1.3b-camera-rerender-video.json) | [source](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/wanvideo_1_3B_ReCamMaster_example_01.json) | [weights](https://huggingface.co/Kijai/WanVideo_comfy) | Weights: check KwaiVGI ReCamMaster model card (not confirmed) | not runtime-tested |
| [wan-2.1-phantom-14b-multi-subject-to-video](wan-2.1-phantom-14b-multi-subject-to-video.json) | [source](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/wanvideo_2_1_14B_phantom_subject2vid_example_02.json) | [weights](https://huggingface.co/bytedance-research/Phantom) | Apache-2.0 | not runtime-tested |
| [wan-2.1-skyreels-a2-element-assembly-to-video](wan-2.1-skyreels-a2-element-assembly-to-video.json) | [source](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/wanvideo_2_1_14B_skyreels_a2_example_01.json) | [weights](https://huggingface.co/Skywork/SkyReels-A2) | Apache-2.0 (model card) | not runtime-tested |
| [wan-2.1-stand-in-identity-reference-to-video](wan-2.1-stand-in-identity-reference-to-video.json) | [source](https://github.com/kijai/ComfyUI-WanVideoWrapper/blob/main/example_workflows/wanvideo_2_1_14B_Stand-In_reference_example_01.json) | [weights](https://huggingface.co/BowenXue/Stand-In) | Apache-2.0; use consented faces | not runtime-tested |
| [propainter-video-object-removal](propainter-video-object-removal.json) | [source](https://github.com/daniabib/ComfyUI_ProPainter_Nodes/blob/main/examples/propainter-inpainting-workflow.json) | [ProPainter](https://github.com/sczhou/ProPainter) (weights download on first run) | **Non-commercial** (NTU S-Lab License 1.0); node pack GPL-3.0 | not runtime-tested |
| [void-video-object-and-interaction-removal](void-video-object-and-interaction-removal.json) | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/utility_void_video_inpainting.json) | [weights](https://huggingface.co/Comfy-Org/void-model) | Apache-2.0 | not runtime-tested |
| [ltx-2.3-obscura-lora-prompt-object-removal](ltx-2.3-obscura-lora-prompt-object-removal.json) | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/template_ltx2_3_obscura_remova_lora_remove_object_from_video.json) | [weights](https://huggingface.co/Lightricks/LTX-2.3) | **LTX-2 Community License** (custom; commercial limits) | not runtime-tested |
| [ltx-2.3-lora-remove-subtitles-from-video](ltx-2.3-lora-remove-subtitles-from-video.json) | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/template_ltx2_3_lora_remove_subtitles_from_video.json) | [weights](https://huggingface.co/Lightricks/LTX-2.3) | **LTX-2 Community License** (custom; commercial limits) | not runtime-tested |
| [wan-2.2-bernini-r-video-relighting](wan-2.2-bernini-r-video-relighting.json) | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_bernini_r_video_editing.json) | [weights](https://huggingface.co/Comfy-Org/Bernini-R) | Apache-2.0 | not runtime-tested |
| [capybara-v0.1-instruction-video-edit](capybara-v0.1-instruction-video-edit.json) | [source](https://github.com/Comfy-Org/workflow_templates/blob/main/templates/video_capybara_v0_1_video_edit.json) | [weights](https://huggingface.co/Comfy-Org/HunyuanVideo_1.5_repackaged) | Weights: check Capybara model card (not confirmed) | not runtime-tested |

## Open Video Model Atlas (Nov 2026) — editing and control coverage

### Equivalent already exists (skipped as duplicates)

- Wan2.1 VACE 1.3B examples (WanVideoWrapper) — same tasks as the VACE 14B workflows above (smaller checkpoint only)
- Wan2.1 Fun Control / Fun Camera, Wan 2.2 5B Fun Control, Wan2.1 1.3B control LoRA, Wan 2.2 5B ControlNet — same capability as `wan-2.2-fun-control-14b-pose-depth-canny` / `wan-2.2-fun-camera-control-14b`
- Wan2.1 ATI trajectory (template and WanVideoWrapper), Time-to-Move — trajectory/motion control already covered by `wan-move-480p-trajectory-motion-control`
- Lynx identity reference — same task as `wan-2.1-stand-in-identity-reference-to-video`
- UniLumos relight (1.3B) — same task as `wan-2.2-bernini-r-video-relighting`
- DiffuEraser, LTX-2.3 video outpainting LoRA — same tasks as ProPainter/VOID removal and VACE outpainting
- MiniMax H3 Fun ControlNet Union template — same graph and checkpoints as [`minimax-h3-pose-controlnet-motion-transfer`](../Character-Animation-Video-to-Video/minimax-h3-pose-controlnet-motion-transfer.json)

### Deliberately not added

- LTX-2.3 watermark-removal template — removing other people's watermarks is not a use this library supports

### No ComfyUI workflow found

No authentic published ComfyUI graph was found for these Atlas entries, so none was made up:

- VACE LTX 0.9 — VACE support was only released for Wan; use the LTX IC-LoRA control workflows in the LTX section instead
- Rerender A Video (keyframe edit; LoRA + ControlNet), TokenFlow, FateZero, Tune-A-Video, Vid2Vid-Zero, AnyV2V, PnP Video, Video-P2P, LOVECon, VideoSwap, ControlVideo, FRESCO — research code (diffusers/SD 1.5); no maintained ComfyUI node or example workflow
- VideoPainter — official repo has no ComfyUI integration
- E2FGVI / E2FGVI-HQ — no maintained ComfyUI graph (CC BY-NC 4.0 weights)
- STTN, FuseFormer — no ComfyUI support found

See the [04-Video README](../README.md) for the other video categories.
