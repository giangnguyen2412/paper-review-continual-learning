## Summary
The research question is:

**Given a sequence of tasks, which properties of the tasks influence the hardness of the entire sequence?**

Intuitively, they pick task complexity and sequential heterogeneity (explain later) as the focused properties. 

## Methodology (See paper for details)
Here, to compare tasks, they leverage a framework *Task2Vec* which model task in to task space for computing distances between 2 tasks. This tool provides a way to specify and alalyze relationships between different tasks from data. In this paper, they use this tool to study catastrophic forgetting. The procedure of their method is:
* Step 1: Pick properties (complexity and heterogeneity in this paper), and compute these properties by using task space modeling methods (Task2Vec for example).
* Step 2: Estimate catastrophic forgetting degree by using final error rate of a model trained sequentially in a sequence.
* Step 3: Use *correlation analysis* to show correlations between results from step 1 and step 2.
### Task2Vec
We study how Task2Vec works: First, it uses a probe network to extract features with label from training data. Then with these immediate features as input, they train it, then apply Fisher information matrix to esmitate importance of weights in models.

This tool can also encode the similarity between tasks.
### Total complexity
Total complexity is computed as the sum of complexities of individual tasks. But how can we define *complexity*?
In this paper, they define complexity of a task as the distance of this task to a **reference task (trivial task)** in task space.
### Sequential heteroheneity
## Experiments
## Novelties
## Personal thoughts
### Pros
### Cons
* The choosing of properties is intuitive, is this picking trustable? Need to clarify
