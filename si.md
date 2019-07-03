## TL;DR

**The authors state that catastrophic forgetting can be solved by complex synapses**

To accommodate changes
in the data distribution, ANNs typically have to be retrained on the entire dataset to avoid overfitting and catastrophic forgetting 

In ANNs, individual synapses
(weights) are typically described by a single scalar quantity.
On the other hand, individual biological synapses make use
of complex molecular machinery that can affect plasticity
at different spatial and temporal scales.

In our model, the synaptic state tracks the past and current parameter value, and
maintains an online estimate of the synapse’s “importance”
toward solving problems encountered in the past. Our importance measure can be computed efficiently and locally
at each synapse during training, and represents the local
contribution of each synapse to the change in the global
loss. When the task changes, we consolidate the important synapses by preventing them from changing in future
tasks. Thus learning in future tasks is mediated primarily
by synapses that were unimportant for past tasks, thereby
avoiding catastrophic forgetting of these past tasks.

**Architectural approaches to catastrophic forgetting alter
the architecture of the network to reduce interference between tasks without altering the objective function.**

**Functional approaches to catastrophic forgetting add a regularization term to the objective that penalizes changes in
the input-output function of the neural network.**

**The third technique, structural regularization, involves
penalties on the parameters that encourage them to stay
close to the parameters for the old task.**
