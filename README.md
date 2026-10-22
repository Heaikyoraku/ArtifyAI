# ArtifyAI
**Image restoration + controlled generative stylization** · Collaborative course project

A Google Colab prototype for restoring facial detail and generating stylized versions of an input image. It combines restoration, image-text similarity, edge guidance, and diffusion-based image synthesis.

## Pipeline

```text
Input image
    |
    v
CodeFormer restoration
    |
    +-- CLIP-based style recommendations
    |
    v
Canny edge extraction
    |
    v
ControlNet + Stable Diffusion
    |
    v
Enhanced image · edge map · stylized output
```

## Implementation

- **Restoration:** CodeFormer
- **Image/style matching:** CLIP (`openai/clip-vit-large-patch14`)
- **Structure-guided generation:** Canny ControlNet with Stable Diffusion
- **Quality inspection:** PSNR, SSIM, and LPIPS utilities in the notebook
- **Environment:** Python, PyTorch, Diffusers, Transformers, OpenCV; designed for Google Colab with a GPU

The notebook contains the implementation and interactive input flow. The report explains the design and experiments.

## Repository

| File | Purpose |
| --- | --- |
| [ArtifyAI_project.ipynb](./ArtifyAI_project.ipynb) | Source notebook and execution flow |
| [ArtifyAI_Project_Report.pdf](./ArtifyAI_Project_Report.pdf) | Project report and methodology |

## Running the prototype

1. Open the notebook in a GPU-enabled Google Colab session.
2. Execute the environment and model setup cells in order. The notebook downloads external model weights and clones the CodeFormer implementation.
3. Provide an input image and choose a style as prompted.

**Reproducibility:** This is a research/coursework notebook, not a packaged app. Dependency versions are not locked, external model availability may change, and the workflow has not been verified as a one-command install. The notebook assumes a CUDA GPU.

## Project context

This was developed collaboratively for an Advanced Artificial Intelligence course. The repository represents a technical prototype, not a production image-editing service. Contributions should not be assumed to be solely mine.

---
**Next engineering improvements:** lock dependencies, separate inference modules from notebook cells, add example inputs/outputs with usage rights, and implement smoke tests.
