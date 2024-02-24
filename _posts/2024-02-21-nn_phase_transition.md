---
layout: distill
title: Phase transition in neural nets
description: Article starts from energy based approaches and comes to phase transition
tags: Airflow, s3
authors:
  - name: Mashalov Nikita  
    affiliations: 
      name: MIPT
hidden: false
---

# Free energy






## Energy based approach 

Energy based defines probability as

$$
    p(E) = \frac{exp()}{Z}
$$


$Z$ - partition function .

Best papers in field comes from Yann LeCun

Self-Supervised Learning from Images with a Joint-Embedding Predictive Architecture [paper](https://arxiv.org/abs/2301.08243)


## Symmetry

Симметрия может быть разной размерности. Для описания преобразования поворота в nD нужно n-1 параметров минимум. Если задавать в виде матрицы, то в n раз больше. Внутри сетки это преобразование выучивается в виде какой-то своей структуры, которая может быть ещё больше. Therfore for we need more neurons


For rotation in nD dimension we at least need n-1 parameters.

| ![chemistry.png](/assets/img/posts/phase_transition/architecture/model.excalidraw.png) |
|:--:|
| *No we can't handle. We need one more neuron* |



Size of neural ensamble




## Analitic solution of attention 

A phase transition between positional and semantic learning in a solvable model of dot-product attention
https://arxiv.org/abs/2402.03902


Article advices solution of problem and shows phase transition




## Ising model

# Renormalization


But it might be more intuitive from view of chemistry. Suppose we perfectly know everything about molecule. Every angle and atom of it's structure

| ![chemistry.png](/assets/img/posts/phase_transition/architecture/model.excalidraw.png) |
|:--:|
| *But what will be if we put them all together* |




## Landau theory of phase transition

Main intuition is that radical changes of matter is connected with change of it's energetic 


$$
    H(X)
$$

$\Lambda$ is known is order parameter 

Coherency length

$$
    \xi 
$$



## Simple example

Brought from awesome video [Renormalization: The Art of Erasing Infinity](https://www.youtube.com/watch?v=0OQ7BhlfAJY&t=872s)




## Perturbation theory


## Futher read

- Percolation: a Mathematical Phase Transition https://www.youtube.com/watch?v=a-767WnbaCQ
