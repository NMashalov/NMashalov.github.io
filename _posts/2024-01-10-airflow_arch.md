---
layout: post
title: Airflow Part 1 Architecture
description: Article covers core architecture for beginner ml team.
---

Through my previous year I had intensive work as MLOps specialist. One of my task was to facilitate in-house Airflow provision. I'll share some techniques, that I implemented during my work.

## Airflow


Apache Airflow is an open-source platform designed to programmatically author, schedule, and monitor workflows. It allows users to define complex workflows as Directed Acyclic Graphs (DAGs), where each node in the graph represents a task, and the edges define the dependencies between tasks. Airflow provides a rich set of features, including a web-based user interface for DAG management, integration with various data sources and processing engines, and robust scheduling capabilities. Users can easily create, schedule, and monitor workflows using Python scripts, leveraging a vast ecosystem of pre-built operators for common tasks such as executing SQL queries, transferring files, or running Python functions. Airflow's extensible architecture allows for the integration of custom operators and hooks, enabling seamless orchestration of workflows across different systems. With its emphasis on flexibility, scalability, and reliability, Apache Airflow has become a popular choice for orchestrating data pipelines, ETL processes, machine learning workflows, and more in a wide range of industries and use cases.


## Setup



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

