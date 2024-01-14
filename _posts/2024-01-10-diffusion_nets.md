---
layout: distill
title: 'Generative Modeling by Estimating Gradients of the Data Distribution'
date: 2021-05-05 11:12:00-0400
description: 'This blog post focuses on a promising new direction for generative modeling. We can learn score functions (gradients of log probability density functions) on a large number of noise-perturbed data distributions, then generate samples with Langevin-type sampling. The resulting generative models, often called <em>score-based generative models</em>, has several important advantages over existing model families: GAN-level sample quality without adversarial training, flexible model architectures, exact log-likelihood computation, and inverse problem solving without re-training models. In this blog post, we will show you in more detail the intuition, basic concepts, and potential applications of score-based generative models.'
authors:
  - name: Yang Song  
    affiliations: 
      name: Stanford University
bibliography: blogs.bib
comments: true
hidden: false
_meta: >
  <meta name="twitter:card" content="summary_large_image">
  <meta name="twitter:site" content="@YSongStanford">
  <meta name="twitter:creator" content="@YSongStanford">
  <meta name="twitter:title" content="Generative Modeling by Estimating Gradients of the Data Distribution">
  <meta name="twitter:description" content="An introduction to the intuition, basic concepts and applications of score-based generative modeling">
  <meta name="twitter:image" content="http://yang-song.github.io/assets/img/score/sde_schematic_21.jpg">
---

<d-contents>

  <nav class="l-text figcaption">
  <h3>Contents</h3>
    <div><a href="#introduction"> Introduction </a></div>
    <div><a href="#the-score-function-score-based-models-and-score-matching">The score function, score-based models, and score matching</a></div>
    <div><a href="#langevin-dynamics">Langevin dynamics</a></div>
    <div><a href="#naive-score-based-generative-modeling-and-its-pitfalls">Naive score-based generative modeling and its pitfalls</a></div>
    <div><a href="#score-based-generative-modeling-with-multiple-noise-perturbations">Score-based generative modeling with multiple noise perturbations</a></div>
    <div><a href="#score-based-generative-modeling-with-stochastic-differential-equations-sdes">Score-based generative modeling with stochastic differential equations (SDEs)</a>			</div>
    <ul>
      <li><a href="#perturbing-data-with-an-sde">Perturbing data with an SDE</a></li>
      <li><a href="#reversing-the-sde-for-sample-generation">Reversing the SDE for sample generation</a></li>
      <li><a href="#estimating-the-reverse-sde-with-score-based-models-and-score-matching">Estimating the reverse SDE with score-based models and score matching</a></li>
      <li><a href="#how-to-solve-the-reverse-sde"> How to solve the reverse SDE </a></li>
      <li><a href="#probability-flow-ode">Probability flow ODE</a></li>
      <li><a href="#controllable-generation-for-inverse-problem-solving">Controllable generation for inverse problem solving</a></li>
    </ul>
    <div><a href="#connection-to-diffusion-models-and-others">Connection to diffusion models and others</a></div>
    <div><a href="#concluding-remarks">Concluding remarks</a></div>      
  </nav>
</d-contents>

Diffusion nets were great success with image generation. I'll make an overview of connected methods.


## Normal distribution. Information geometry approach


It can be shown that riemanian metric of gaussian distribution is equal to:
$$
    g = \frac{1}{\sigma^2}(d\mu^2+2d\sigma^2)
$$

That speculations is very important due to fact it's curvature defines hyperbolic space.

Hyperbolic space is naturally hierarchical


## Energy-based methods

## Ar

## Physics way of thinking of Langevin dynamics

Recall, Langevin gradient descent is brought by 

$$
    x_{t+1} = x_t + \eta
$$

Diffusion process are stochastic in local, but not one global scale. You can rule diffusion by simple temperature difference. 



But why add noise?

A smarter way for representation is to ask why exactly gaussian noise? 

## Central limit theorem

It's well known fact:


But why really that happens behind fuss of formulas? What is actual speed of convergence? And what's more important what is so special about normal distribution? 

I'll provide you with intuition for answering this questions.


## Fokker-Plank equation

https://en.wikipedia.org/wiki/Fokker%E2%80%93Planck_equation

$$
    \frac{\partial}{\partial t} p(x,t) = - \frac{\partial}{\partial x}[\mu(x,t)p(x,t)] + \partial{}{}
$$


## Diffusion maps

Is approach for dimension reduction similar as PCA and t-SNE. You can read [more](https://en.wikipedia.org/wiki/Diffusion_map)

## Useful resources
Blogs:
1. Markov chains https://bjlkeng.io/posts/markov-chain-monte-carlo-mcmc-and-the-metropolis-hastings-algorithm/
   
Videos:
1. https://www.youtube.com/watch?v=hbIfrLefwzw