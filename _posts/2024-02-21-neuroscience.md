---
layout: distill
title: Neuroscience
description: Brief overview of advances in conjunction of Deep Learning and neuroscience
tags: Airflow, s3
authors:
  - name: Mashalov Nikita  
    affiliations: 
      name: MIPT
---



Biological networks are much more than just scalar weights. It has activation time and phase different phases of work. Recent works have proved efficacy of neuro-informed approaches.

## Latent representation

Represents world events in his own latent space. In easiest case it is just a representation of place 

| ![map.jpg](/assets/img/posts/latent.excalidraw.png) |
|:--:|
| ** |

You can learn more about manifold in [blog](https://nmashalov.github.io/blog/2024/manifold/).

Hypothesis of latent representation is well studied and summarized via biological perspective in excellent videos of Artem Kirsanov [Neural manifolds - The Geometry of Behaviour](https://www.youtube.com/watch?v=QHj9uVmwA_0) and [Your brain is moving along the surface of the torus 🤯](https://www.youtube.com/watch?v=9ujnZcaqf-4).

Latent representation are unique among all people. Yet we are capable to share via *communication*, which have certain formats. Through perspective of machine learning that is called [Sparse coding](https://en.wikipedia.org/wiki/Sparse_dictionary_learning). That idea is very similar to basis in linear algebra.

| ![map.jpg](/assets/img/posts/neuroscience/dictionary.excalidraw.png) |
|:--:|
| *Communication has lot's of forms* |

From experience of communication we learn to correspond specific communication as certain combination of semantic recognition.

### One more insight. Motion integrals

 When you sit in a train, you don't check to , you *just remember it*.

| ![map.jpg](/assets/img/posts/neuroscience/dictionary.excalidraw.png) |
|:--:|
| *Communication has lot's of forms* |

From perspective of analytic mechanics it means that we coresponds to first integral. That means in your semantic space you can *decouple* preserving and changing.

 Moreover, we can say that through years we learn to do that with many things. We learn them an. That helps to concentrate on reall

## Ensembles

Combinatorial representation of system as possible collections of states

Why we need lot's neuronms

Symmetry can exhibit various dimensions. Describing a rotation transformation in n-dimensional space requires a minimum of n-1 parameters. If represented as a matrix, the parameter space expands by a factor of n. Within a grid, this transformation is learned as a distinctive structure, which may further augment its complexity.

| ![pipeline.jpg](/assets/img/posts/neuroscience/high_dim_symmetry.excalidraw.png) |
|:--:|
| *Example of high dimensional symmetry that embedded in 2 dimensional picture* |

Look at following picture. One of the symmetry that net might learn is that all cars, therefore they can be permuted without loss of sense.

$$
 P = \begin{pmatrix}
0 & 0 & \cdots & 1 & \cdots & 0 \\
0 & 0 & \cdots & 0 & \cdots & 1 \\
\vdots & \vdots & \ddots & \vdots & \ddots & \vdots \\
1 & 0 & \cdots & 0 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots & \ddots & \vdots \\
0 & 1 & \cdots & 0 & \cdots & 0
\end{pmatrix}
$$

For learning such symmetries we high dimensional matrix, hence more neurons

## Neural coding

A way how brain transfer information.

## Liquid networks

Is's a conspect from [Liquid Neural Networks](https://www.youtube.com/watch?v=IlliqYiRhMU)

Leaky-integrator model

$$
    \frac{d \mathbf{x}}{d t} = - \frac{\mathbf{x}(t)}{\tau} + \mathbf{S}(t)
$$


Conductance-based synapce model

$$
    \mathbf{S}(t) = f(\mathbf{x}(t),\mathbf{I}(t),t, \theta)(A - \mathbf{x}(t))
$$


$$
    \frac{d \mathbf{x}}{d t } = - \left[ \frac{1}{\tau} + \underbrace{f(\mathbf{x}(t,\mathbf{I}(t),t,\theta)}_{\text{Liquid variable}}) \right] \mathbf{x}(t) +  f(\mathbf{x}(t,\mathbf{I}(t),t,\theta)) A
$$


|![lattice.png](/assets/img/posts/neuroscience/liquid_achieve.excalidraw.png) |
|:--:|
| *Screenshot from presentation* |

### New Hopfiled networks

Recall that are two type of states


Were introduced in Paper
Dense Associative Memory for Pattern Recognition
https://arxiv.org/abs/1606.01164




Old pair-wise interaction

$$
    E = - \frac{1}{2} \sum_{i,j=1}^N \sigma_i T_{ij} \sigma_j
$$

New non-linear

$$
    E = - \sum_{\mu =1}^K F(\xi_i^\mu \sigma_i)
$$

Which comes in exponential increase in capacity of stored memories. 

With drawback of that we need to store all of them

Increased capacity of recognised


### Reservoir computing

Next generation reservoir computing
https://www.nature.com/articles/s41467-021-25801-2

Introduction to Next Generation Reservoir Computing
https://www.youtube.com/watch?v=wbH4En-k5Gs


### Forward-forward

Backpropagation and the brain
https://www.nature.com/articles/s41583-020-0277-3

Checkout notebook

https://github.com/EscVM/EscVM_YT/blob/master/Notebooks/2%20-%20PT1.X%20DeepAI-Quickie/pt_1_forward_forward_alg.ipynb

## Read more

Lecun Latent World [](https://openreview.net/pdf?id=BZ5a1r-kVsf). Here is effective paraphrase of article.
For effective work we need to concentrate, despite changing. For that we have instrisic representation of world. It helps to find something that preserves in time, so we need ti

HAMUX
https://github.com/bhoov/hamux

Free energy Karl Friston
https://www.fil.ion.ucl.ac.uk/~karl/A%20free%20energy%20principle%20for%20the%20brain.pdf


Relating transformers to models and neural representations of the hippocampal formation
https://arxiv.org/abs/2112.04035

