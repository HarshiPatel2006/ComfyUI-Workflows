# 3D Generation — ComfyUI workflows

Image-to-3D and multi-view-to-3D mesh generation with Trellis 2, Pixal3D and SAM3D Body, including PBR textures.

| Subfolder | What is inside | Workflows |
|---|---|---|
| [`Image-to-3D/`](Image-to-3D) | Image-to-3D | 8 |
| [`Multi-View-to-3D/`](Multi-View-to-3D) | Multi-view-to-3D | 5 |

## Workflows (13)

### Image-to-3D

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [pixal3d-image-to-3d-model-hq-pbr-textures](Image-to-3D/pixal3d-image-to-3d-model-hq-pbr-textures.json) | Image to 3D Model — HQ + PBR Textures | ComfyUI-Pixaroma |
| [pixal3d-image-to-3d-model-low-vram](Image-to-3D/pixal3d-image-to-3d-model-low-vram.json) | Image to 3D Model — Low VRAM | ComfyUI-Pixaroma |
| [sam3d-body-3d-viewer](Image-to-3D/sam3d-body-3d-viewer.json) | 3D Viewer | Core only |
| [sam3d-body-utility](Image-to-3D/sam3d-body-utility.json) | Utility | Core only |
| [sam3d-body-video-to-3d-body-multi-r01-sc008](Image-to-3D/sam3d-body-video-to-3d-body-multi-r01-sc008.json) | Video to 3D Body — Multi (R01_SC008) | Core only |
| [trellis-2-image-to-3d-model-high-vram](Image-to-3D/trellis-2-image-to-3d-model-high-vram.json) | Image to 3D Model — High VRAM | ComfyUI-Pixaroma |
| [trellis-2-image-to-3d-model-hq-pbr-textures](Image-to-3D/trellis-2-image-to-3d-model-hq-pbr-textures.json) | Image to 3D Model — HQ + PBR Textures | ComfyUI-Pixaroma |
| [trellis-2-image-to-3d-model-low-vram](Image-to-3D/trellis-2-image-to-3d-model-low-vram.json) | Image to 3D Model — Low VRAM | ComfyUI-Pixaroma |

### Multi-view-to-3D

| Workflow | What it does | Custom nodes needed |
|---|---|---|
| [pixal3d-multi-view-1-shape-only-no-colours-hq](Multi-View-to-3D/pixal3d-multi-view-1-shape-only-no-colours-hq.json) | 1 Shape Only (No Colours) — HQ | ComfyUI-Pixaroma |
| [pixal3d-multi-view-1-shape-only-no-colours](Multi-View-to-3D/pixal3d-multi-view-1-shape-only-no-colours.json) | 1 Shape Only (No Colours) | ComfyUI-Pixaroma |
| [pixal3d-multi-view-2-model-colours](Multi-View-to-3D/pixal3d-multi-view-2-model-colours.json) | 2 Model + Colours | ComfyUI-Pixaroma |
| [pixal3d-multi-view-3-model-pbr-textures-lq](Multi-View-to-3D/pixal3d-multi-view-3-model-pbr-textures-lq.json) | 3 Model + PBR Textures — LQ | ComfyUI-Pixaroma |
| [pixal3d-multi-view-4-model-pbr-textures-hq](Multi-View-to-3D/pixal3d-multi-view-4-model-pbr-textures-hq.json) | 4 Model + PBR Textures — HQ | ComfyUI-Pixaroma |

See the [main README](../README.md) for models used, setup steps and the full catalog.
