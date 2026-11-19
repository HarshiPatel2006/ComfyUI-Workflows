# 3D Generation — ComfyUI workflows

Image-to-3D and multi-view-to-3D mesh generation with Trellis 2, Pixal3D and SAM3D Body, including PBR textures.

| Subfolder | What is inside | Workflows |
|---|---|---|
| [`Image-to-3D/`](Image-to-3D) | Image-to-3D | 8 |
| [`Multi-View-to-3D/`](Multi-View-to-3D) | Multi-view-to-3D | 5 |

## Workflows (13)

### Image-to-3D

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [pixal3d-image-to-3d-model-hq-pbr-textures](Image-to-3D/pixal3d-image-to-3d-model-hq-pbr-textures.json) | Image to 3D Model — HQ + PBR Textures | `trellis_2_texture_vae_bf16.safetensors`, `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors` +3 more | ComfyUI-Pixaroma |
| [pixal3d-image-to-3d-model-low-vram](Image-to-3D/pixal3d-image-to-3d-model-low-vram.json) | Image to 3D Model — Low VRAM | `trellis_2_texture_vae_bf16.safetensors`, `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors` +3 more | ComfyUI-Pixaroma |
| [sam3d-body-3d-viewer](Image-to-3D/sam3d-body-3d-viewer.json) | 3D Viewer | — | Core only |
| [sam3d-body-utility](Image-to-3D/sam3d-body-utility.json) | Utility | `sam3.1_multiplex_fp16.safetensors`, `sam_3d_body_dinov3_bf16.safetensors`, `moge_2_vitl_normal_fp16.safetensors` +1 more | Core only |
| [sam3d-body-video-to-3d-body-multi-r01-sc008](Image-to-3D/sam3d-body-video-to-3d-body-multi-r01-sc008.json) | Video to 3D Body — Multi (R01_SC008) | `sam3.1_multiplex_fp16.safetensors`, `sam_3d_body_dinov3_bf16.safetensors`, `moge_2_vitl_normal_fp16.safetensors` +1 more | Core only |
| [trellis-2-image-to-3d-model-high-vram](Image-to-3D/trellis-2-image-to-3d-model-high-vram.json) | Image to 3D Model — High VRAM | `trellis_2_texture_vae_bf16.safetensors`, `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors` +2 more | ComfyUI-Pixaroma |
| [trellis-2-image-to-3d-model-hq-pbr-textures](Image-to-3D/trellis-2-image-to-3d-model-hq-pbr-textures.json) | Image to 3D Model — HQ + PBR Textures | `birefnet.safetensors`, `dino_v3_L_naf_fp32.safetensors`, `trellis_2_int8_convrot.safetensors` +2 more | ComfyUI-Pixaroma |
| [trellis-2-image-to-3d-model-low-vram](Image-to-3D/trellis-2-image-to-3d-model-low-vram.json) | Image to 3D Model — Low VRAM | `trellis_2_texture_vae_bf16.safetensors`, `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors` +2 more | ComfyUI-Pixaroma |

### Multi-view-to-3D

| Workflow | What it does | Models used | Custom nodes needed |
|---|---|---|---|
| [pixal3d-multi-view-1-shape-only-no-colours-hq](Multi-View-to-3D/pixal3d-multi-view-1-shape-only-no-colours-hq.json) | 1 Shape Only (No Colours) — HQ | `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors`, `pixal3d_multiview_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [pixal3d-multi-view-1-shape-only-no-colours](Multi-View-to-3D/pixal3d-multi-view-1-shape-only-no-colours.json) | 1 Shape Only (No Colours) | `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors`, `pixal3d_multiview_int8_convrot.safetensors` +1 more | ComfyUI-Pixaroma |
| [pixal3d-multi-view-2-model-colours](Multi-View-to-3D/pixal3d-multi-view-2-model-colours.json) | 2 Model + Colours | `trellis_2_texture_vae_bf16.safetensors`, `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors` +2 more | ComfyUI-Pixaroma |
| [pixal3d-multi-view-3-model-pbr-textures-lq](Multi-View-to-3D/pixal3d-multi-view-3-model-pbr-textures-lq.json) | 3 Model + PBR Textures — LQ | `trellis_2_texture_vae_bf16.safetensors`, `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors` +2 more | ComfyUI-Pixaroma |
| [pixal3d-multi-view-4-model-pbr-textures-hq](Multi-View-to-3D/pixal3d-multi-view-4-model-pbr-textures-hq.json) | 4 Model + PBR Textures — HQ | `trellis_2_texture_vae_bf16.safetensors`, `dino_v3_L_naf_fp32.safetensors`, `trellis_2_shape_vae_bf16.safetensors` +2 more | ComfyUI-Pixaroma |

See the [main README](../README.md) for setup steps, requirements and the other categories, or [`00-LIBRARY-INDEX.md`](../00-LIBRARY-INDEX.md) for the full list of workflows.
