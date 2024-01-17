---
layout: post
title: Practical applications of optimal transport
description: Optimal transport, also known as Monge-Kantorovich transport or Wasserstein distance, is a mathematical framework that deals with the optimal way to transport mass from one configuration to another, minimizing the cost of the transportation. This field has gained significant attention across various disciplines due to its theoretical richness and a wide range of practical applications. 
---
## Introduction

Optimal transport is useful beyond classical problems of logistic and resource management. That method is somehow universal. I describe from my personal experience in NLP.

Optimal transport is useful tool for data scientist. I'll bring case from my personal practice to prove.

## Bussiness case. Matching scripts

Suppose we have call-center, where junior operators read scripts and more proficient colleagues speak freestyle. We want to match phrases from scripts to new original variations of freestylers. 

Modern neural nets models BERT provides us with convenient of vector representation of sentences.

We actually have two distibutions of sentences. First is for scipt sentences, second for 


You can read more about embeddings [here](https://www.turing.com/kb/guide-on-word-embeddings-in-nlp).

In normal practise we use cosine similarity

$$
    \text{similarity} = \cos(\text{emb}_1,\text{emb}_2)
$$

All we need is to bring optimal connection.
## About optimality

Optimality is actually one of the way of thinking and defining objects. 


What's more importantly you can relax 


## Entropy regularized optimal transport

$$
    \int_{x \in \Pi(\mu,\nu)}
$$

## Fluid approach

It will be instructive to consider another formulation of the optimal transport, originating in spirit
from the fluid dynamics (Benamou & Brenier, 2000; Villani, 2003). Assume that at t = 0 we are
given a set of ‘particles’ from the density ρ0 which move in such a way that at t = 1 their state
is described by the density ρ1. Moreover, these particles move in such that they perform the least
amount of work. Formally, they minimize the following action:

$$
    A= \int_{0}^{1} \left(\sum_{x} |\dot{x}(t)|^2\right)dt
$$

In continuous limit obtaining:

$$
    \inf_{\rho,v} \left\{\int_{0}^1 \int \rho_t(x) |v_t(x)|^2 dxdt; \frac{\partial \rho_t}{\partial t} + \nabla \dot (\rho_t v_t) =0\right\}
$$

## Resources
Computational Optimal Transport by Marco Cuturi
https://arxiv.org/pdf/1803.00567.pdf