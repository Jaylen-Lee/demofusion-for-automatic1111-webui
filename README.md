# Demofusion & VAE

This is based on the separated demofusion and tilevae from the previously developed integrated version of tilediffusion and demofusion, which can also be obtained [here](https://github.com/pkuliyi2015/multidiffusion-upscaler-for-automatic1111)

****

### Demofusion

ℹ The execution time of Demofusion will be relatively long, but it can obtain multiple images of different resolutions at once. Just like tilediffusion, please enable tilevae when an OOM error occurs.

ℹ Recommend using higher steps, such as 30 or more, for better results

ℹ If you set the image size to 512 * 512, the appropriate window size and overlap are 64 and 32 or smaller. If it is 1024, it is recommended to double it, and so on.

ℹ Recommend using a higher denoising strength in img2img, maybe 0.8-1，and try to use the original model, seeds, and prompt as much as possible

ℹ Do not enable it together with tilediffusion.  It supports operations such as tilevae, noise inversion, etc.

ℹ Due to differences in implementation details, parameters such as c1, c2, c3 and sigma can refer to the [demofusion](https://ruoyidu.github.io/demofusion/demofusion.html), but may not be entirely effective sometimes. If there are blurred images, it is recommended to increase c3 and reduce Sigma.

![demo-example](https://github.com/Jaylen-Lee/image-demo/blob/main/example.png?raw=true)

#### Example: txt2img, 1024 * 1024 image 3x upscale

- Params：

  - Step=45, sampler=Euler, same prompt as official demofusion, random seed 35, model SDXL1.0

  - Denoising Strength for Substage = 0.85， Sigma=0.5，use default values for the rest，enable tilevae

  - Device： 4060ti 16GB
  - The following are the images obtained at a resolution of 1024, 2048, and 3072

  ![demo-result](https://github.com/Jaylen-Lee/image-demo/blob/main/3.png?raw=true)

