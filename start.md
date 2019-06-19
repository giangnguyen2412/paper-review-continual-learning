## Continuous Learning Strategies

While the community has not agreed yet on a shared categorization for CL strategies, here we propose a three-label fuzzy categorization based on [7] and [10]: 

### Architectural Strategies: 
specific architectures, layers, activation functions, and/or weight-freezing strategies are used to mitigate forgetting. Includes Dual-memories-models attempting to imitate Hippocampus – Cortex duality.

### Regularization Strategies: 
the loss function is extended with terms promoting selective consolidation of the weights which are important to retain past memories. Include regularization techniques such as weight sparsification, dropout, early stopping.

### Rehearsal Strategies: 
past information is periodically replayed to the model, to strengthen connections for memories it has already learned. A simple approach is storing part of the previous training data and interleaving them with new patterns for future training. A more challenging approach is pseudo-rehearsal with generative models.

In the last few years, a large number of CL strategies has been proposed. A non-comprehensive, cherry-picked list of the most popular strategies can be found below:

- CopyWeights with Re-init (CWR) [1]

- Progressing Neural Networks (PNN) [8]

- Elastic Weights Consolidation (EWC) [5]

- Synaptic Intelligence (SynInt) [7]

- Learning without Forgetting (LwF) [3]

- Incremental Classifier and Representation Learning (iCaRL) [6]

- Gradient Episodic Memory (GEM) [4]

In Fig. 1 the Venn diagram of the fuzzy classification of the aforementioned strategies is proposed. It is interesting to note the large space for yet-to-be-explored techniques merging the ideas of the three different categories.

![](https://github.com/luulinh90s/paper-review-continual-learning/blob/master/images/start/venn_strategies.png)

## To solve catastrophic forgetting

In the paper, `Continual Learning Through Synaptic Intelligence`, authors mentioned that:
`The problem of alleviating catastrophic forgetting has been
addressed in many previous studies. These studies can be broadly partitioned into (1) architectural, (2) functional,
and (3) structural approaches.`

- Architectural approaches to catastrophic forgetting alter
the architecture of the network to reduce interference between tasks without altering the objective function.

- Functional approaches to catastrophic forgetting add a regularization term to the objective that penalizes changes in
the input-output function of the neural network.

- The third technique, structural regularization, involves
penalties on the parameters that encourage them to stay
close to the parameters for the old task.
