---
layout: post
title: Diffusion net notes
description: Article argues with and elucidating diffusion net from perspective of gradual correction and bring insights from physics. Article suggests alternative explanation via concept of continious storage naturally comming out of boltzman distribution. Proposal is built with providing intuition of underlying physical process .Elaborationj idea it bring different statistics as fermi and boson as 
authors:
  - name: Mashalov Nikita  
    affiliations: 
      name: MIPT
---

File systems are organized hierachicallly. It helps to preserve *context* and *hasten* search

| ![map.jpg](/assets/img/posts/diffusion_nets/file_storage.excalidraw.png) |
|:--:|
| *File storage provides way of information organization* |

But happens if wants to do *continuate* hierarchy. How it will look like, what properties will it have?

## Physics womb E

In computer science methods using energy are called *energy-based* and are mostly popularized via Yann LeCun.


In physics concept of continous hierachy comes naturally from observation of energy spectre of gas
$$
    p(E) = \frac{exp(-\frac{E}{T})}{Z}
$$

Distribution is called Boltzman and explains probability of particle. You may argue how probability refers to files. So I'll share distribution of files under energy.

| ![map.jpg](/assets/img/posts/diffusion_nets/energy_levels.excalidraw.png) |
|:--:|
| *Continious file storage* |

See, exponent in probability perfectly matches with idea in hierachy on every level number of files should grow, therefore we will observe. 

## Key physics insights


### Temperature

Temperature gives average energy of particle in system by simple equation

$$
    E = d/2 T
$$

where $d$ is a dimension of space and $T$ is temperature.

What's more intriguing is how distribution changes 

You can derive it from integration if you want

| ![map.jpg](/assets/img/posts/diffusion_nets/gpu-fridge.excalidraw.png) |
|:--:|
| *GPU is kinda of cooler* |

| ![map.jpg](/assets/img/posts/diffusion_nets/weights.excalidraw.png) |
|:--:|
| *GPU is kinda of cooler* |


But how it's possible? I mean GPU heats when train. Yeah refrigiator of cooler does it too 🤯.

### Free energy

$Z$ in normalization is tightly connected with concept of *Free energy*. In layman terms is maximal energy that you can get from battery considering lack of thermal energy. 

Physict write 

$$
    F = U - TS
$$

,where $U$ is inner energy, $S$ - entropy, $T $-temperature of system. Informally, it's a gap between ordered - potential and unordered - kinetic energy.

Fundamental principle of universe is minimization of this gap.

| ![map.jpg](/assets/img/posts/diffusion_nets/universe.excalidraw.png) |
|:--:|
| *Universe is quite lazy. It tends to minimize free energy* |

This concept although comes in motion, where it has a representation of Lagrangian

$$
    L = T - V
$$

This principle is crucial in bayessian optimization and model selection.

By the way so called KL-divergence is actually a free energy 🤯.

### Gaussian noise is not random

The most important thing, that it's rescales. If you average random gaussian variables you'll again get gaussian, but at greater scale

$$
    \sum \xi \sim \mathbf{N}(0,N), \xi \sim \mathbf{N}(0,1)
$$
That's it gaussian noise is hierarchical properties as it seamlessly accumulate information from is ancestors.

| ![map.jpg](/assets/img/posts/diffusion_nets/noise_hierarchy.excalidraw.png) |
|:--:|
| *Even noise can build hierarchy* |


## What actually happens through denoising process?

### Energy interpretation

Resulting Images have low energy, initial noise highest.

### Process  


Network learns gradually to correct mistakes. This is great explanation, but intuition for building your own approach.

What is actually happening through langevin process is a cooling of particle. 

| ![map.jpg](/assets/img/posts/diffusion_nets/s) |
|:--:|
| *Search* |

But what is


| ![map.jpg](/assets/img/posts/diffusion_nets/energy_levels.excalidraw.png) |
|:--:|
| *Search* |


Actually diffusion net is cataloging all new info from picture. So on every step is recataloging info in best format possible.

At every step you move to more specefic from high energy state to low.



And help her a lot with our noise task

| ![map.jpg](/assets/img/posts/diffusion_nets/energy_levels.excalidraw.png) |
|:--:|
| *Continious file storage* |

Because net doesn't know where it actually is. It only knows it's current place and how travel next.

Why this is good?

Because such approach learns *local* symmetry in catalogue.

Yeah, main advantage of diffusion net, that it is has very seamless.

Through training we learn to minimize local free energy of manifold.


Okay why it needs noise for learning? Recall free energy.




OKay, learning of cataloging 

### But why it needs noise?




### Quantum perspective

Energy level are actually discrete, but are expanded through brownian motion of particles.





## Connection to stochastic equations

https://arxiv.org/abs/2108.01073

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


## Connection to optimal transport

Yandex research paper 

Two steps:
1. Transforming ODE to probability flow ODE

$$
    dx= -[x+\nabla_x \log p_t(x)]dt
$$

2. Encoder map
For a given distribution µ0 and a timestep t,
let us denote the flow generated by this vector field as Eµ0
(t, ·). I.e., a point x ∼ µ0 is mapped to
Eµ0
(t, x) when transported along the vector field for a time t. The ‘final’ encoding map is obtained
when t → ∞, i.e,

$$
    E_{\mu_0}(x) = \lim_{t \rightarrow \infty} E_{\mu_0}(t,x)
$$

Note that $E_{\mu_0}$
implicitly depends on all the intermediate densities µt obtained from the diffusion
process (or the Fokker-Planck equation).

The authors of [Meng et al.](https://arxiv.org/abs/2108.01073) (2021) proposed to view diffusion models as a discretization of certain
stochastic differential equations. SDEs generalize standard ordinary differential equations (ODEs) by
injecting random noise into dynamics. Specifically, the diffusion process specified by Equation (1) is
a discretization of the following SDE:

$$
    dx = -\frac{1}{2} \beta(t) xdt + \sqrt{\beta(t)} d\omega
$$


r. It can be shown that the
trajectory {µt}∞
t=0, obtained by solving the Fokker-Planck equation

## Useful resources
Blogs:
1. Markov chains https://bjlkeng.io/posts/markov-chain-monte-carlo-mcmc-and-the-metropolis-hastings-algorithm/
   
Videos:
1. https://www.youtube.com/watch?v=hbIfrLefwzw