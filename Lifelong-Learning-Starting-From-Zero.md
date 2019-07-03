## TL;DR

**The authors state that in the
beginning the network is a blank slate with no nodes at all. It develops
according to four rules: (i) expansion, which adds new nodes to memorize
new input combinations; (ii) generalization, which adds new nodes that
generalize from existing ones; (iii) forgetting, which removes nodes that
are of relatively little use; and (iv) backpropagation, which fine-tunes the
network parameters. They analyze the model from the perspective of accuracy, energy efficiency, and versatility and compare it to other network
models, finding better performance in several cases**

![](https://github.com/luulinh90s/paper-review-continual-learning/blob/master/images/LL0/algo.JPG)

LLO’s neural network consists of four node types:

input nodes with the identity function as their activation function;

output nodes with softmax as their activation function;

value nodes with a Gaussian activation function and two parameters, (µ, σ),
used for storing values; and

concept nodes with a sigmoid activation function and one bias parameter,
used for forming the neural counterparts of conjunctions (though training
can turn them into something quite different!).

All concept nodes are directly connected to all output nodes. Concept nodes
may also have any number of outgoing connections to value nodes. All incoming
connections to concept nodes are from value nodes. Each value node has one
incoming connection, which originates from either a concept or input node. They
have one outgoing connection, always to a concept node.
