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

# Multi-task learning
Multi-task learning learns multiple related tasks simultaneously, aiming at achieving a
better performance by using the relevant information shared by multiple tasks [Caruana,
1997, Chen et al., 2009, Li et al., 2009]. The rationale is to introduce inductive bias in
the joint hypothesis space of all tasks by exploiting the task relatedness structure. It also
prevents overfitting in the individual task and thus has a better generalization ability. Note
that unlike that in transfer learning, we mostly use the term multiple tasks rather than
multiple domains as much of the existing research in the area is based on multiple similar
tasks from the same domain of application. We now define multi-task learning, which is
also referred to as batch multi-task learning.
## Deep learning in Multi-task Learning
In recent years, deep neural network (DNN) has also been applied to multi-task learning.
For example, Liu et al. [2015b] proposed a multi-task DNN for learning representations
across multiple tasks. In their proposed multi-task DNN model, the lower neural network layers are shared
across multiple tasks while the top layers are task-dependent.

## Life-long learning vs Multi-task learning
The similarity of (batch) multi-task learning and lifelong learning is that they both aim to
use some shared information across tasks to help learning. The difference is that multi-task
learning is still working in the traditional paradigm. Instead of optimizing a single task, it
optimizes several tasks simultaneously. If we regard the several tasks as one bigger task,
it reduces to the traditional optimization which is actually the case in most optimization
formulations of MTL. It does not accumulate any knowledge over time and it does not use
the concept of continuous learning, which are the key characteristics of LML. Although
one can argue that MTL can jointly optimize all tasks whenever a new task is added, it
is quite difficult to optimize all tasks in the world simultaneously in a single process as
they are too numerous and diverse. Some local and distributed optimizations are needed.
Global optimization is also not efficient in terms of both the time and resources. Thus, it
is important to retain knowledge to enable incremental learning of multiple tasks with the
help of knowledge learned in the past from previous tasks. That is why we regard online
or incremental multi-task learning as lifelong learning.

# Online learning
Online learning (also known as incremental learning) is a learning paradigm where the
training data points arrive in a sequential order. When a new data point arrives, the existing
model is quickly updated to produce the best model so far. Its goal is thus the same as
classic learning, i.e., to optimize the performance on the given learning task. It is normally
used when it is computationally infeasible to train over the entire dataset or the practical
applications cannot wait until a large amount of training data is collected. This is in contrast
with the classic batch learning where all training data is available at the beginning.

One application of their problem is to predict users’ preferences towards
products in a social network.

## Life-long learning vs Online learning
Although online learning deals with future data in streaming or in a sequential order, its
objective is very different from lifelong machine learning. Online learning still performs
the same learning task over time. Its objective is to learn more efficiently with the data
arriving incrementally. Lifelong learning, on the other hand, aims to learn from a sequence
of different tasks, retain the knowledge learned so far, and use the knowledge to help future
task learning. Online learning does not do any of these.

# Reinforcement learning
Reinforcement Learning [Kaelbling et al., 1996, Sutton and Barto, 1998] is the problem
where an agent learns actions through trial and error interactions with a dynamic environment. In each interaction step, the agent receives input that contains the current state of
the environment. The agent chooses an action from a set of possible actions. The action
changes the state of the environment. Then, the agent gets a value of this state transition,
which can be reward or penalty. This process repeats as the agent learns a trajectory of
actions to optimize its objective. The goal of reinforcement learning is to learn an optimal
policy that maps states to actions that maximizes the long run sum of rewards. 

## Life-long learning vs Reinforcement learning
A reinforcement learning agent learns by trial and error in its interactions with the environment which gives feedback or rewards to the agent. The learning is limited to one
task and one environment. There is no concept of accumulating knowledge to help future
learning tasks.
