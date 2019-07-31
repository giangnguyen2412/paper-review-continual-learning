## Summary
 
The authors state that in the Catastrophic forgetting is a major obstacle to the development of artificial intelligence applications
capable of true lifelong learning [27, 28], and enabling neural networks to sequentially learn multiple
tasks has become a topic of intense research. Yet, despite its scope, this research field is relatively
unstructured: even though the same datasets tend to be used, direct comparisons between published
methods are difficult. They propose 3 new scenarios for evaluation: 

- task identity is provided or Task Incremental-Learning

- task identity is not provided but dont need to be inferred - Domain Incremental-Learning

- task identity is not provided but should be inferred - Class Incremental-Learning

For example, with Split MNIST, we can divide the task into 3 different scenarios:

![](https://github.com/luulinh90s/paper-review-continual-learning/blob/master/images/three%20scenarios/table2.JPG)

Authors also reviewed techniques for Continual Learning to deal with catastrophic forgetting:

- Task specific Components: explicitly define a different sub-network
per task. Here with each task, a sub-network will be incharge of each task. **Context-dependent Gating (XdG)** is a simple 
approach randomly assigning which nodess participate in each task.

- Regularized Optimization: **EWC** and **SI** estimate for all parameters of the network how important they are for the previously
learned tasks and penalize furture change to them accordingly.

- Modifying Training Data: complement the training data for
each new task to be learned with “pseudo-data” representative of the previous tasks. This strategy is
referred to as replay. One option is to take the input data of the current task, label them using the model trained on the
previous tasks, and use the resulting input-target pairs as pseudo-data. This is the approach of
**Learning without Forgetting**.

- Using Exemplars: if it is possible to store data from previous tasks, another strategy for alleviating catastrophic forgetting
is to use stored data as “exemplars” during execution. A recent method that successfully used this
strategy is **iCaRL**.

## Experiments

Authors uses:

- XdG

- EWC/Online EWC/SI

- LwF/DGR/DDGR+distill

- iCaRL

*Note*: 

They included the following two baselines:
- None: The model was sequentially trained on all tasks in the standard way. This is also called
fine-tuning, and can be seen as a lower bound.
- Offline: The model was always trained using the data of all tasks so far. This is also called joint
training, and was included as it can be seen as an upper bound.

## Personal thoughts

- Pros: This paper is a good approach to unify evaluation of Continual Learning systems.

- Cons: The structure of paper makes readers hard to follow, it'd be better if they can clarify the critical contribution in the introduction.
Reading the whole paper ensures you understand the idea instead of reading the intro.
