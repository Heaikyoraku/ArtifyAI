# ArtifyAI

**Image restoration and structure-guided generative stylization**

ArtifyAI takes an input image through a restoration and image-generation workflow. It combines facial detail recovery with style selection and edge-guided diffusion to produce an enhanced image and a stylized result.

## What it does

```text
Input photo
   |
   +--> CodeFormer: restore facial details
   |          |
   |          +--> CLIP: recommend image styles
   |          |
   |          +--> Canny: extract structural edges
   |                        |
   +------------------------+--> ControlNet + Stable Diffusion
                                     |
                                     v
                              Stylized image
```

The notebook provides image upload, enhancement, style selection, generated outputs, and image-quality inspection utilities.

## Tech

`Python` · `PyTorch` · `CodeFormer` · `CLIP` · `ControlNet` · `Stable Diffusion` · `OpenCV`

## Explore the work

| Asset | Contents |
| :-- | :-- |
| [Source notebook](./ArtifyAI_project.ipynb) | Image restoration, CLIP analysis, Canny-guided generation, and output visualization |
| [Technical report](./ArtifyAI_Project_Report.pdf) | Methodology, experiments, and project discussion |

### Try it

1. Open the notebook in Google Colab with GPU acceleration enabled.
2. Run setup and model-loading cells in order.
3. Upload an image and follow the style-selection prompts.

The Colab workflow downloads model dependencies and weights; a GPU is recommended. It has not been repackaged as a standalone application.

<sub>Developed collaboratively for an Advanced AI course. The repo contains the team project and its report.</sub>
