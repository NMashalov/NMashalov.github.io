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



---
layout: post
title: Stein Variational Gradient Descent
description: 
---


Stein Variational Gradient Descent uses a vector field $v$ to sample from prior distribution $\pi$ from $\rho$.

$$
    x^i_{k+1} = x_k^i + \varepsilon v(x_k^i)
$$

For successful approximation $v$ is optimized via rate

$$
    \arg \sup_{\phi \in C}\{-\partial_\varepsilon KL(T_{\#\rho} \parallel \pi)_{\varepsilon=0}\}
$$

Note that hedge $\#$ hear means push forward operator from measure $\rho$. It's just a way to emphasize that method is based on operator $T$



 However, directly computing the vector field is intractable because
it is non-trivial to compute the time-dependent score function ∇θ log µτ (θ). To tackle this issue,
traditional ParVI methods either restrict the functional gradient within RKHS and leverage analytical
kernels to approximate the vector field or , or learn a neural network to estimate the vector
field


## Wasserstein Gradient Flow



Large-Scale Wasserstein Gradient Flows https://arxiv.org/pdf/2106.00736.pdf. Is a method based on the Wasserstein gradient flows, that was proposed for solution of the Fokker-Planck equation.


The term on the right can be understood as
the gradient of F in Wasserstein space, a vector field perturbatively rearranging the mass in ρt to
yield the steepest possible local change of F.
Wasserstein gradient flows are used in various applications:

$$
    \frac{\partial \rho_t}{\partial t} = \text{div}(\rho_t \nabla_x \mathbf{F}(\rho_t)) 
$$

Continuity equation

Fokker-Plank free energy functional

$$
    F_{FP}(\rho)= U(\rho) - \beta^{-1} \mathcal{E}_\rho
$$

## Stein operator

$$
    S_\pi \phi = \nabla \log \pi \phi + \nabla \dot \phi 
$$


We need to find field $\phi$ that will transform prior distribution to posterior $\pi$ 


## Probability metric

https://www.cs.toronto.edu/tss/files/papers/2021-SteinsMethodSurvey-Li.pdf

Definition. Probability measures $\mu$ and $\nu$ on familiy $\mathbf{H}$ of test functions

$$
    d_{\mathbf{H}}(\mu,
    \nu) = \sup_{h \in \mathbf{H}} \left| \int h(x)d\mu(x) - \int g(x) d\nu(x)\right|
$$

Wasserstein metric

Family is defined via 1-Lipshitz functions $W$ 

$$
    d_W = \sup_{h\in W}|\mathrm{E}h(y)-\mathrm{E}h(Z)|
$$


Stein identity

$$
    E f'(Z) = EZ f(Z)
$$

for all absolute continious functions $f: \mathrm{R} \rightarrow \mathrm{R}$ with $\mathrm{E}|f'(Z)| < \infty$

## Mean-field

$$
    \frac{d X^i_t}{d t} = - \underbrace{\frac{1}{N} \sum_{j=1}^N \nabla k (X^i_t, X^j_t)}_{repulsion between particles} - \frac{1}{N}
$$

## Wasserstein space

Denote $L^2_q$ as Hilbert Space of $\mathrm{R}^D$ valued functions with :

1. 
    u: $\mathrm{R^D} \rightarrow \mathrm{R^D}$
    $$
        |\int\|u(x)\|^2_2 dq < \infty|
    $$
2. Inner product
    $$
        <u,v>_{L^2_q} = \int u(x) \dot v(x) dq 
    $$

$$
    \partial_t q_t + \nabla \dot (v_tq_t)=0,
$$
$v_t \in \bar{\{\nabla \phi: \phi \in C_c^\infty\}}$

## Gradient flows

Langevin and SGVD are gradient flows of KL divergence but with different metrics on $P(\mathbf{R}^d)$

Langevin gradient flow approximation

$$
    \rho_{n+1} = \argmin_{\rho}\left(KL(\rho|\pi) + \frac{1}{\varepsilon} d^2_{OT}(\rho,\rho_n)\right)
$$


SGVD gradient flow approximation


$$
    \rho_{n+1} = \argmin_{\rho}\left(KL(\rho|\pi) + \frac{1}{\varepsilon} d^2_{K}(\rho,\rho_n)\right)
$$

Wasserstein geometry

## Particle-based Variational Inference

Typically, the measure
µτ follows the “steepest descending curves” of a functional on W2(Θ),


## Practical usage of SVGD

[Profilic dreamer](https://arxiv.org/pdf/2305.16213.pdf) - text-to-3D generation.

Similarity between 



Compared with the vanilla SDS in Eq. (2) which optimizes the parameter θ in the parameter space Θ,
here we aim to optimize the distribution (measure) µ(θ|y) in the function space W2(Θ).

$$
    \min_{\mu \in W_2(\Theta)} \varepsilon[\mu] = \mathrm{E}_{t,\varepsilon,c}
 [\frac{\sigma_t}{\alpha_T} \omega(t) D_{KL}(q_t^\mu(x_t|c,y) \parallel p_t(x_t|y^c))]$$


They derive the gradient flow minimizing $\mathcal{E}[\mu]$ in $\mathrm{W}_2(\Theta)$ and so update rule

$$
    \frac{\partial \mu_\tau(\theta|y)}{\partial \tau} = - \nabla_\theta \left[\mu_\tau(\theta|y) \mathrm{E}_{t,\epsilon,c}[\sigma_t \omega(t)(\nabla_{\mathbf{x}_t} \log p_t(\mathbf{x}_t|y^c)- \nabla_{x_t} \log q_t^{\mu_t}(\mathbf{x}_t|c,y) \frac{\mathbf{g}(\theta,c)}{\partial \theta})] \right]
$$

update rule

$$
\frac{d \theta_\tau}{d \tau} = \mathrm{E}_{t,\epsilon,c}[\sigma_t \omega(t)(\nabla_{\mathbf{x}_t} \log p_t(\mathbf{x}_t|y^c)- \nabla_{x_t} \log q_t^{\mu_t}(\mathbf{x}_t|c,y) \frac{\mathbf{g}(\theta,c)}{\partial \theta})] 
$$


Theorem 3 shows that by letting the random variable θτ ∼ µτ (θτ |y) move across the ODE trajectory
in Eq. (12), its underlying distribution µτ will move by the direction of the steepest descent that
minimizes E[µ].

Therefore, to obtain samples (in Θ) from µ
∗ = arg minµ E[µ], we can simulate the
ODE in Eq. (12) by estimating two score functions ∇xt
log pt(xt|y
c
) and ∇xt
log q
µτ
t
(xt|c, y) at
each ODE time τ , which corresponds to the VSD objective in Eq. (9).


Proof. Hope it will help you acquire habbit:

Gradient flow minimizing $\mathcal{E}[\mu]$ on $\mathrm{W}_2(\Theta)$ satisfies:

$$
    \frac{\partial\mu_\tau}{\partial \tau} = - \nabla_{\mathrm{W}_2} \mathcal{E}[\mu] = \nabla_\theta (\mu_t \nabla_\theta \frac{\delta \mathcal{E}[\mu_t]}{\delta \mu_t})
$$

Calculating derivative

$$
    (\frac{\delta D_{KL}(q \parallel p)}{\delta q})[x] = \log q(x) - \log p(x) + 1
$$

$$
    \frac{\delta q_t^\mu(\mathbf{x}_t|c,y)}{\delta \mu}[\theta] = q_{t0}(\mathbf{x_t}|\mathbf{x_0}) = \mathcal{N}(\mathbf{x}_t| \alpha_tx_0)
$$

By definition of $q_t^\mu$

$$
    q_t^\mu(\mathbf{x_t}|c,y) = \mathrm{E}_{q_0^\mu(\mathbf{x}_0|c,y)}[q_{t0}(\mathbf{x}_t|\mathbf{x}_0)] = \mathrm{\mu(\theta|y)}[q_{t0}(\mathbf{x_t}|\mathbf{g}(\theta,c))]
$$



Fokker-Plank equation helps to connect measure equation with particle.

References
1. Andrew Duncan – On the Geometry of Stein Variational Gradient Descent
https://www.youtube.com/watch?v=1Ec7Eoa5W7g
2. Understanding and Accelerating Particle-Based Variational Inference https://arxiv.org/pdf/1807.01750.pdf
3. B. T. Polyak, Some methods of speeding up the convergence
of iteration methods https://www.mathnet.ru/links/e4418385804fdfbc633dced14b9713ec/zvmmf7713.pdf