---
layout: post
title: Airflow automatization
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


## Resources
Computational Optimal Transport by Marco Cuturi
https://arxiv.org/pdf/1803.00567.pdf