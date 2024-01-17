---
layout: distill
title: 3d Generative modeling
description: >
 Diffusion nets were great success with image generation. I'll make current  This overview will help you to formS
authors:
    - name: Mashalov Nikita
      - affiliations:
        - name: MIPT
---


Here's my overview of current achievements in 3D 



Formats can be transformed 

## Two main approaches


| Flavor    | Distillation from 2d images           | Work with 3d models |
| --------- | ------------------------------------- | ------------------- |
| Data| Cheap | Expensive |
| Speed | currently slow | fast|
| Influential works| [Profilic Dreamer](https://arxiv.org/pdf/2305.16213.pdf)|[PointE](https://arxiv.org/abs/2212.08751)








## 3d representation

As pictures have several approaches like SVG and PNG 3d models also have different representation.

- NERF

Given the camera position $\mathbf{o}$ and
direction $\mathbf{d}$, a batch of rays $\mathbf{r}(k) = o + k\mathbf{d}$ is sampled to
render a pixel. The MLP takes $r(k)$ as input and predicts
the density $τ$ and color $c$.

Final rendered color is given by quadrature:

$$
    C_c(r) = \sum^{N_c}_{i=1} \Omega_i(1-\exp(-\tau_i \delta_i))c_i
$$


$\Omega$ denotes accumalated transmitance

$$
    \Omega_i = \exp(-\sum^{i-1}_{j=1} \tau_j \delta_j)
$$

$\delta$ - is distance between adjacent samples.


- Textured Mesh

Textured
mesh [45] represents the geometry of a 3D object with triangle meshes and the texture with color on
the mesh surface. Here the 3D parameter θ consists of the parameters to represent the coordinates of
triangle meshes and parameters of the texture. The rendering process g(θ, c) given camera pose c is
defined by casting rays from pixels and computing the intersections between rays and mesh surfaces
to obtain the color of each pixel. The textured mesh allows high-resolution and fast rendering with
differentiable rasterization.


Current 

## Rendering

https://pytorch3d.org/


Most crucial equation comes. It's defined through density estimation

## NERF
Awesome overview of NERF are presented in [AI SUMMER](https://theaisummer.com/nerf/)


| ![NERF.jpg](/assets/img/posts/three_d_dmodels/neural_field.png) |
| :-------------------------------------------------------------: |
|                             *NERF*                              |




## Techniques 

- Point Cloud
- Score Distillation Sampling 

I list influential 

## Influential works



Google Research
- DreamFusion https://dreamfusion3d.github.io/


## Score distalation Sampling 



https://pals.ttic.edu/p/score-jacobian-chaining 

is a
widely used method to distill 2D image priors from a pretrained diffusion model ϵϕ into differentiable 3D representations. Given a differentiable generator g and a NeRF model parameterized by θ, its rendered image x can be obtained by x = g(θ). Then, SDS calculates the gradients of
NeRF parameters θ by:

$$
    \nabla_\Theta \mathcal{L}_{SDS}(\phi,\mathbf{s}) = \mathrm{E}_{t,\epsilon} \left [\omega_t (\epsilon_\phi(x_t;y,t) - \epsilon) \frac{\partial z_t}{\partial x} {\partial}\right]
$$

$\omega_t$ is a weighting function that depends on the
timestep $t$ and $y$ is the text embedding of given prompt.



## Latest article 




x. SDS is an optimization method
by distilling pretrained diffusion models,




As
Advice using

## Resourses 

In article ProlificDreamer: High-Fidelity and Diverse Text-to-3D
Generation with Variational Score Distillation https://arxiv.org/pdf/2305.16213.pdf Wang et al.


their impo

https://github.com/yuanzhi-zhu/prolific_dreamer2d/tree/main

## Where go further

## References 

[1] Score Jacobian Chaining: Lifting Pretrained 2D Diffusion Models for 3D Generation https://pals.ttic.edu/p/score-jacobian-chaining

[2] DreamTime: An Improved Optimization Strategy for
Text-to-3D Content Creation
 https://arxiv.org/pdf/2306.12422.pdf

[3] v- ShapE https://arxiv.org/abs/2305.02463