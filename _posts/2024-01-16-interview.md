My interests are generative modeling based on physics and geometrical methods. 

This is primarily determined by recent advances in generative modeling. Specifically, framework of diffusion networks consisting of closely related markov chains, stochastic ode and langevin dynamics. I believe that solution for coherence of representation of long can be found via analysis through fundamental physics law of continuation and motion. 

Yandex has rich access to media data. computational resources and experience of developing diffusion networks as YandexART. I am looking for a guidance in writing top papers proposing new approaches.


Dream Fusion: Text-to-3D using 2D Diffusion - Preprint https://arxiv.org/abs/2209.14988

Artictle proposed a novel approach to text-to-3D synthesis by leveraging a pretrained 2D text-to-image diffusion model. Crucially, the proposed approach eliminates the need for labeled 3D training data and avoids modifications to the image diffusion model. The optimization involves refining a randomly-initialized 3D mode ) through gradient descent, ensuring low loss in its 2D renderings from random angles. 

---

Profilic dreamer: High-Fidelity and Diverse Text-to-3D Generation with Variational Score Distillation- https://arxiv.org/abs/2305.16213

Authors proposed novel approach for distillation 2d diffusion text-to-image models to 3d. They elaborate previous technique SDS introduced in Dream Fusion(https://dreamfusion3d.github.io/) by building distribution of implicit representation rather making it constant. For facilitating computation they utilize particle-based variational inference. I get of method intuition through paper Understanding and Accelerating Particle-Based Variational Inference(https://arxiv.org/pdf/1807.01750.pdf). Despite time consuming inference fidelity approach is much better than competing works. Moreover model enjoy appropriate for diffusion models guidance scale around 10.

Action Matching: Learning Stochastic Dynamics from Samples -https://arxiv.org/abs/2210.06662

Action Matching addresses the challenge of learning the continuous dynamics of a system when only provided with snapshots of its temporal marginals.  I believe that such approaches will help to build semantics of complex actions like.

---

I gained great experience by building infrastructures for ML models, which can be easily modified via configs and command line interface.
As for code preferences I prefer laconic style and enjoy usage of generator expressions where it possible. When possible I use task specific libraries as it helps concentrate on research task rather.

Here's  representative example of ordering directed graph written in JSON

```python
# link has format [1,1,0,2,1,'.csv']
# link[0] - id of link (order of bringing links to folder)
# link[1] - id of source node
# link[3] - id of target node
# node.outputs contain use link id
# that's why we need link_map
# you can have better understanding looking at graph.json in test folder

# Create a mapping of link IDs to their corresponding links
link_map = {link[0]: link for link in links}

# Define a function to extract relevant IDs from a link
extract_ids = lambda x: (link_map[x][1], link_map[x][3],)

# Create a dictionary mapping node links to their corresponding IDs
linkage = {
    input.link: extract_ids(input.link)
    for node in nodes
    if node.inputs is not None
    for input in node.inputs
    if input.link is not None
}

# Build a directed graph using NetworkX
dependency_graph = nx.DiGraph(linkage.values())

# Group the generations of the DAG
grouped_dag = [sorted(generation) for generation in nx.topological_generations(dependency_graph)]
```


 Utilization of the "Don't Repeat Yourself" (DRY) principle helped me a lot with learning benefits of abstractions, decomposing and code refactoring. You can see my progress in developing In my project multi-component projects here: https://github.com/NMashalov/PydanticGraph.
In PydanticGraph i worked a lot with validation framework Pydantic. That brought me intuition of working with developer abstractions and python inner libraries like importlib.  

SDEdit:
Image synthesis and editing with stochastic differential equations. a