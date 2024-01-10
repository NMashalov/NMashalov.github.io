---
layout: post
title: Streaming architecture
---

Streaming application also known as near real time (NRT) are . They are widely used in credit scoring, geoanalytics and mobile.

Current popular solutions are 

In this article I share my heuristics for building streaming application. I'll touch upon:
- ways to aggregate

Assumptions:
- we are provided with enough of kafka of 

Such assumptions helps us to:
-
## Feature level

On feature level we are interested on aggregating in planar format.

Suppose we have nested structure

## Aggregation level

There are two ways to aggregate info with common schema or without. I'll share pros and cons of both approach.

Common schema is beneficial for side developer. As he can. Also common schema allows to use AVRO for effective.

Yet standardization can bring serious obstacles:
- fields with common 

First 

