# All things diffusion-related
![denoising gif](diffusion_process.gif)

## Helpful resources
### Set up instructions
- [Ready-to-go GUI via colab](https://colab.research.google.com/github/altryne/sd-webui-colab/blob/main/Stable_Diffusion_WebUi_Altryne.ipynb)
- Stable diffusion via [webui](https://github.com/sd-webui/stable-diffusion-webui)
- Huggingface's [Diffusers library](https://huggingface.co/blog/stable_diffusion)
#### Disable NSFW and safety checker
- [Disable from the original CompVis's repository](https://www.reddit.com/r/StableDiffusion/comments/wv2nw0/tutorial_how_to_remove_the_safety_filter_in_5/?utm_source=share&utm_medium=web2x&context=3)
- Disable from inside a Jupyter notebook code cell, paste this below the pipe generation command ([source](https://www.reddit.com/r/StableDiffusion/comments/wv2nw0/comment/im0msfl/?utm_source=share&utm_medium=web2x&context=3)):
```python
from diffusers.pipelines.stable_diffusion import safety_checker

def sc(self, clip_input, images) :
    return images, [False for i in images]

# edit StableDiffusionSafetyChecker class so that, when called, it just returns the images and an array of True values
safety_checker.StableDiffusionSafetyChecker.forward = sc
```
#### Get explainations for generated images
The [diffusers-interpret library](https://github.com/JoaoLages/diffusers-interpret) can generate token attribution and gif of the denoising process.

#### Simple [walkthrough in Jupyter notebook](2022-09-09-stable-diffusion-1-4.ipynb)

### Better image generation
[r/StableDiffusion](https://www.reddit.com/r/StableDiffusion/)
- [How different parameters impact the image](https://www.reddit.com/r/StableDiffusion/comments/x41n87/how_to_get_images_that_dont_suck_a/)
- [Upscaling via img2img](https://www.reddit.com/r/StableDiffusion/comments/x45uk6/my_process_to_upscale_an_image_through_img2img/?utm_source=share&utm_medium=web2x&context=3)
### Other communities
- Stable Diffusion on [Discord](https://discord.gg/stablediffusion)
- Huggingface coummunity on [Discord](https://discord.gg/G7tWnz98XR)
