---
layout: post
title: Information geometry
describe: Information Geometry is a mathematical framework that studies the geometric structures associated with statistical models and probability distributions. It has wide usage in Quantum Mechanics and Bayesian Inference. I'll make an overview of tools, that can come handy for your studying. 
---

## Introduction 

Fisher information metric

$$
    \text{KL}(f_\theta|f_{\theta+d\theta}) = \frac{1}{2} (d\theta)^TI(\theta)d\theta +O(|d\theta|^3)
$$


Fisher information

$$
    I(\theta) = \mathbb{E}_\theta[s_\theta(X)s_\theta(X)^T], s_\theta = \nabla_\theta \log f_\theta(X)
$$

## Riemannian manifold

Fisher information is symmetric positive semi-definite. Defines Riemannian metric on the parameter space(RAO, 1945) - Fisher information metric:

$$
    <d\theta_1, d\theta_2>_\theta = d\theta_1^T I(\theta6) d\theta_2
$$

So for tangent vector  $u,v \in T_\theta \Theta \approx \mathbb{R}^d$

$$
    <u,v>_\theta = u^T I(\theta)
$$

## Riemanian tools

### Angles and norms of tangent vectors

$$
    <u,v>_\theta
$$

### Lengths 

$$
    l(\gamma) = \int_0^1 \|\dot{\gamma}(t)\|_{\gamma(t)}dt
$$  

### Distances

$$
    \text{dist}(\theta_0,\theta_1) = \inf_{\gamma(0)=\theta_0, \gamma(1)=\theta_1} l(\gamma)
$$

### Geodesics

Optimal interpolation with zero acceleration

$$
    t \rightarrow \gamma(t), \nabla_{\dot{\gamma}} \dot{\gamma} =0  
$$

$\nabla$ Levi-Civitia connections -> intrisic derivatives of vector fields


## Hopf-Rinov theorem

If manifold is complete, than any two points can be linked with minimizing geodesics

## Exp map and log map

$$
    \forall \nu \in T_{\theta_0} \Theta, \exp_{\theta_)}(\nu)=\gamma(1), \text{where } \gamma \text{ is geodesic } \gamma(0)=\theta_0, \dot{\gamma}(0)=\nu 
$$


$$
    \forall \theta_1 \in \Theta \log_{\theta_0} (\theta_1) = \nu, \text{ where} \exp_{\theta_0}(\nu)=\theta_1
$$

## Dual tools

- Eucledian scalar product $\rightarrow$ Riemannian metric
- straight lines $\rightarrow$ geodesics
- Euclidian distance $\rightarrow$ geodesic distance
- addition/ substraction $\rightarrow$ Riemannian exponential/logarithm

$$
    x + \nu \rightarrow \exp_x(\nu) \\
    x - y \rightarrow \log_x(y)
$$

## Freshett mea

$x_1,\dots, x_n \in M$ metric space:


$$
    \tilde{x} =\argmin_{x\in M} \frac{1}{n} \sum_{i=1}^n d(x,x_i)^2
$$



https://www.youtube.com/watch?v=elSmfwHNTRc