---
layout: post
title: Diffusion net notes
---


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