# Life long learning

![](https://github.com/luulinh90s/paper-review-continual-learning/blob/master/images/start/definition.JPG)
Since this definition is quite general, some remarks are in order:
1. The definition shows three key characteristics of LML: (1) continuous learning, (2)
knowledge accumulation and maintenance in the knowledge base (KB), and (3) the
ability to use the past knowledge to help future learning. That is, the lifelong learner
learns a series of tasks, possibly never ending, and in the process, it becomes more
and more knowledgeable, and better at learning. These characteristics make LML
different from related learning paradigms such as transfer learning [Jiang, 2008, Pan
and Yang, 2010, Taylor and Stone, 2009] and multi-task learning [Caruana, 1997,
Chen et al., 2009, Lazaric and Ghavamzadeh, 2010], which do not have one or more
of these characteristics. 

2. The tasks do not have to be from the same domain. There is no unified definition of
a domain in the literature that is applicable to all areas. In most cases, the term is
used informally to mean a subject area where there are often multiple different tasks
of the same type or of different types.

# Transfer learning
## Deep learning in transfer learning
Yosinski et al. [2014] studied the transferability of features in each layer of a deep
neural network. They argued that the lowest level or the raw input layer is very general as it
is independent of the task and the network. In contrast, the features from the highest level
depend on the task and cost function, and thus are specific. For example, in a supervised learning task, each output unit corresponds to a particular class. From the lowest level to
the highest level, there is a transfer from generality to specificity. To experiment the transferability of features in each layer in a deep neural network, they trained a neural network
from the source domain and copy the first n layers to the neural network for the target
domain. The remaining layers in the target neural network are randomly initialized. They
showed that transferred features in the neural network from the source domain are indeed
helpful to the target domain learning. Also in the transfer learning setting, Bengio [2012]
focused on unsupervised pre-training of representations and discussed potential challenges
of deep learning for transfer learning.

## Life-long learning vs Transfer learning
Transfer learning is different from lifelong learning in the following aspects. We want to
note that since the literature on transfer learning is extensive, the differences described here
may not be applicable to every individual transfer learning paper.

### 
Transfer learning is not concerned with continuous learning or knowledge accumulation. Its transfer of information or knowledge from the source domain to the target
domain is only one-time. It does not retain the transferred knowledge or information
for future use. LML, on the other hand, represents continuous learning. Knowledge
retention and accumulation are essential for LML as they not only enable the system to become more and more knowledgeable, but also allow it to learn additional
knowledge more accurately and easily in the future.

### 
Transfer learning is unidirectional. It transfers knowledge only from the source domain
to the target domain, but not the other way around because the target domain has
little or no training data. However, in LML, the learning result from the new domain
or task can be used to improve learning in previous domains or tasks if needed.

### 
Transfer learning typically involves with only two domains, a source domain and a
target domain (although in some cases there are more than one source domain). It
assumes that the source domain is very similar to the target domain; otherwise the
results can be detrimental. The two similar domains are usually selected by human
users. LML, on the other hand, normally considers a large (possibly infinite) number of tasks/domains. In solving a new problem, the learner can pick and choose the
appropriate past knowledge to be used in current learning. It does not have the assumption made by transfer learning. That is, in LML, if there is useful knowledge from
the past, use it. If not, just learn using the current domain data. However, since LML
typically involves a large number of past domains, the system has a large amount of
past knowledge. The new learning task is very likely to find some pieces of the past
knowledge useful.
