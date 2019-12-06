# Highlights
* The most common baseline used in prior work is a neural network
sequentially trained on all tasks in the standard way, in that the parameters learned from old tasks
are fine-tuned to the new task. Such a model is usually optimized with Adam [21], but here we
use different optimizers including Adam, SGD, and Adagrad.
* Three interesting points can be seen in the results in Table 2. First, Adagrad and L2 achieve better
performance than online EWC and similar to SI. This shows that while Adam is popularly used
for this task, Adagrad is more appropriate. This is possibly due to the fact that it results in small
updates for parameters frequently used for past tasks.
* Second, naive rehearsal achieves performance
similar to state-of-the-art methods with the same space overhead, and performs much better than
online EWC and SI, especially in the incremental class scenario. This highlights the limitation of
regularization-based methods and raises a question about the benefit of using a generative model.
* The third is the obvious trend of difficulty among the three scenarios.
The easiest one is incremental task learning, while the incremental class learning is harder than the
incremental domain learning.
