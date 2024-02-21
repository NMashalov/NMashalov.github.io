---
layout: post
title: Airflow Part3 Code
description: Final part concentrate on explicit implementation of architecture
---

In that blog, we will concentrate on the code implementation of principles introduced in previous chapters.

## s3 environment organization

Simple Storage Service (S3)  is a highly scalable, secure, and durable object storage. 

objects are organized and accessed within buckets.

Links in S3 are proximal to file storage

### Pipeline yaml structure

It easier to reason using groups

```yaml
dag: #meta info of dag
    n

jobs:


```

Then that code is templated in python dags


Yaml is useful for versioning of code and correction on fly from gitlab editor

### Node based programming


| ![ui.ppg](/assets/img/posts/airflow_automation/node_based/ui.png) | 
|:--:| 
| *Open source solution for class connection* |


For ease of building new dags I introduced [solution](https://github.com/NMashalov/PyVisGraph) based on [LiteGraph](https://github.com/jagenjo/litegraph.js/blob/master/build/litegraph.js). 

Solution was highly inspirated by ComfyUI pipelining tool for Stable Diffusion.







