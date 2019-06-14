
Current approaches have typically ensured that data from
all tasks are simultaneously available during training. By interleaving data from multiple tasks during
learning, forgetting does not occur because the weights of the network can be jointly optimized for
performance on all tasks. In this regime—often referred to as the multitask learning paradigm—deep
learning techniques have been used to train single agents that can successfully play multiple Atari
games. If tasks are presented sequentially, multitask learning
can only be used if the data are recorded by an episodic memory system and replayed to the network
during training. This approach (often called system-level consolidation [McClelland et al., 1995]),
is impractical for learning large numbers of tasks, as in our setting it would require the amount of
memories being stored and replayed to be proportional to the number of tasks.

**Recent evidence suggests that the mammalian brain
may avoid catastrophic forgetting by protecting previously-acquired knowledge in neocortical circuits
[Cichon and Gan, 2015, Hayashi-Takagi et al., 2015, Yang et al., 2009, 2014]. When a mouse acquires
a new skill, a proportion of excitatory synapses are strengthened; this manifests as an increase in
the volume of individual dendritic spines of neurons [Yang et al., 2009]. Critically, these enlarged
dendritic spines persist despite the subsequent learning of other tasks, accounting for retention of
performance several months later [Yang et al., 2009]. When these spines are selectively “erased”, the
corresponding skill is forgotten [Hayashi-Takagi et al., 2015, Cichon and Gan, 2015]. This provides
causal evidence that neural mechanisms supporting the protection of these strengthened synapses
are critical to retention of task performance. Together, these experimental findings—together with
neurobiological models [Fusi et al., 2005, Benna and Fusi, 2016]—suggest that continual learning
in the mammalian neocortex relies on a process of task-specific synaptic consolidation, whereby
knowledge about how to perform a previously acquired task is durably encoded in a proportion of
synapses that are rendered less plastic and therefore stable over long timescales**

In this work, we demonstrate that task-specific synaptic consolidation offers a novel solution to the
continual learning problem for artificial intelligence. We develop an algorithm analogous to synaptic
consolidation for artificial neural networks, which we refer to as elastic weight consolidation (EWC
for short).

**In brains, synaptic consolidation enables continual learning by reducing the plasticity of synapses that
are vital to previously learned tasks. We implement an algorithm that performs a similar operation in
artificial neural networks by constraining important parameters to stay close to their old values.**

While
learning task B, EWC therefore protects the performance in task A by constraining the parameters to
stay in a region of low error for task A centered around θA∗.

All the information about task A must therefore have been absorbed into the posterior distribution
p(θ|DA). This posterior probability must contain information about which parameters were important
to task A and is therefore the key to implementing EWC. 
