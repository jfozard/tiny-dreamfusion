# tiny-dreamfusion

Very simple incomplete and unofficial implementation of Dreamfusion - https://dreamfusion3d.github.io/
using Stable Diffusion.

A much better implementation can be found at https://github.com/ashawkey/stable-dreamfusion - please use this!

However, this version my be helpful as it's a single notebook file, and uses a very simple NeRF,
based on the TinyNerf notebook from https://github.com/krrish94/nerf-pytorch

Installation requirements - as for https://github.com/CompVis/stable-diffusion
Please follow instructions there to download stability.io Stable Diffusion checkpoints.

Runs in an hour or so on a 3090. 
Three versions:
 - tiny_nerf_only_rgb. Takes RGB directly from NeRF. No lighting. Does not apply loss on VQVAE but decodes predicted denoised image and applies loss on image.
 - tiny_nerf_only_rgb_through_encoder. Applies score distillation sampling gradient to encoded latents of NeRF image. This works better - might be slightly slower but made up for by faster convergence
 - tiny_nerf. With lighting. Applies score distillation sampling gradient to encoded latents of NeRF image.
 
 Note that all of these use a very, very simple NeRF, so results are not particularly detailed. 


