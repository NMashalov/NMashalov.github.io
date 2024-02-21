---
layout: post
title: Airflow Part 1 Architecture
description: Article covers core architecture for beginner ml team. 
tags: Airflow, s3
---

Through my previous year I had intensive work as MLOps specialist. One of my task was to facilitate in-house Airflow provision. I'll share some techniques, that I implemented during my work.

Cycle will consists of three parts:
1. (Current) Linkage between tools of versioning and storage. Airflow 


## Airflow


Apache Airflow is an open-source platform designed to programmatically author, schedule, and monitor workflows.

Basic primitive is a Directed Acyclic Graphs (DAGs)




## Setup

That means that all DevOps work of the deployment, configuration, and monitoring of Airflow instances. Provider ensured scalability, reliability, and performance.

Yet it comes with restriction of  Airflow environments, manage dependencies, which could be mitigated with building custom airflow docker image.

## Deployment 

Before we can start inference we need to deliver our files to production. Our provides can grab files for inference from s3. 


## Pipeline 

Main observation was that dags are mostly similar and has structure of Extract Transform Load(ETL).

Therefore they can be replaced with simple yaml structure as:
```yaml
dag: # dag info
    name: 
    schedule: " " # simple cron expression


```


It a


### Operators









Airflow organization was build for necessities of classical ML team, which specialized on test and making hyposthesis. Therefore following objectives were 
established:

- transparency:  
-
- 

## One operator many possibilitites

Operators 

Which were configured as 


```yaml
job:
    resourse_flavor: # configures amount of cpu, gpu and ram
    docker_image: # sets image 


```


##



## Templating helps

Dag were created 

Through use of Jinja

I provide you with my template to start

```



```





## CI delivery


![drawing.jpg](/assets/img/posts/drawing/Simo-Serra/drawing.png)

## Environments helps to test new ideas

We decoupled setup by different Airflow instances. 


Difference 

```
config:
    

```


## Yaml

Versioning



## Node-based programming

Finally


I share my 




## Appendix 

##