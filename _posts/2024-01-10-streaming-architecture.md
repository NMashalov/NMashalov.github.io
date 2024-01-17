---
layout: post
title: Streaming architecture
hidden: True
---

Streaming application also known as near real time (NRT) are . They are widely used in credit scoring, geoanalytics and mobile.

Current popular solutions are 

In this article I share my heuristics for building streaming application. I'll touch upon:
- ways to aggregate

Assumptions:
- we are provided with enough of kafka

Such assumptions helps us to:


We get triggers of all cats



## Onion architecture

I'll give a quick overview over architecture

|Layer|Credo|Principles|Tech realisation|
|-----|-----|----|----------------|
| Feature extraction layer| Extract as much as possible |

Teach realisation:
- feature extraction
    - every side streaming source will have it own kafka topic
    - that topic should be filter only by your domain
    - yet we don't enrich it yet with our domain info
- feature level
    - we merge all semantics group in one
    - model scheme should have one datamodel
- enrichment layer 
    - we enrich 
- strategy layer
    - only nessary info for side developer
    - all strategies are merged to one output topic 



## Architecture judgement

Arhitecture brings useful decomposition.


## Feature level

On feature level we are interested on aggregating in planar format.

Suppose we have nested structure

## Aggregation level

There are two ways to aggregate info with common schema or without. I'll share pros and cons of both approach.

Common schema is beneficial for side developer. As he can. Also common schema allows to use AVRO for effective.

Yet standardization can bring serious obstacles:
- fields with common 

First 

