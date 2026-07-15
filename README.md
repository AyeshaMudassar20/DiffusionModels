Diffusion Models — Image Generation
====================================

From-scratch implementation of a denoising diffusion model (DDPM-style) for image generation, with the forward noising process and reverse sampling visualized.

About
-----

Diffusion models generate images by learning to reverse a gradual noising process: a clean image is progressively corrupted with Gaussian noise over many timesteps, and a neural network (typically a U-Net) is trained to predict and remove that noise step by step. Sampling starts from pure noise and repeatedly applies the learned reverse step until a clean image emerges.

This repository contains the training and sampling implementation, including the noise schedule, the denoising network, and visualization of both the forward (noising) and reverse (generation) processes.

Contents
--------

- `Gen_Ai_Diffusion_Model_Ass_4.ipynb` — full training and sampling pipeline: data loading, noise schedule definition, U-Net-style denoising model, training loop, and sample generation.

Getting started
----------------

Clone the repository or download the notebook.

Install dependencies:

    pip install torch torchvision numpy matplotlib jupyterlab tqdm

Launch Jupyter and open the notebook:

    jupyter lab

Notes
-----

- Hardware: a GPU with CUDA is strongly recommended — diffusion model training involves many forward/reverse passes and is slow on CPU.
- Sampling from a trained model requires iterating the reverse process across all timesteps, so generation is slower than a single forward pass; this is a known tradeoff of diffusion models versus GANs.

License
-------

MIT License — see `LICENSE`.

Author
------

Ayesha Mudassar — [github.com/AyeshaMudassar20](https://github.com/AyeshaMudassar20)
