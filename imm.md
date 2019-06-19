IMM incrementally
matches the moment of the posterior distribution of the neural network which is
trained on the first and the second task, respectively.

To make the search space
of posterior parameter smooth, the IMM procedure is complemented by various
transfer learning techniques including weight transfer, L2-norm of the old and the
new parameter, and a variant of dropout with the old parameter.

Recently, the concept of applying a regularization function to a network trained by the old task to
learning a new task has received much attention. This approach can be interpreted as an approximation of sequential Bayesian [5, 6]. Representative examples of this regularization approach include
learning without forgetting [7] and elastic weight consolidation [8]. These algorithms succeeded in
some experiments where their own assumption of the regularization function fits the problem.

IMM uses the framework of Bayesian neural networks, which implies that uncertainty is introduced on the parameters in neural networks, and that the **posterior distribution** is calculated

IMM approximates the mixture of Gaussian posterior with each component
representing parameters for a single task to one Gaussian distribution for a combined task. To merge
the posteriors, we introduce two novel methods of moment matching. One is mean-IMM, which
simply averages the parameters of two networks for old and new tasks as the minimization of the
average of KL-divergence between one approximated posterior distribution for the combined task and each Gaussian posterior for the single task [11]. The other is mode-IMM, which merges the parameters of two networks using a Laplacian approximation [9] to approximate a mode of the mixture
of two Gaussian posteriors, which represent the parameters of the two networks.

![](https://github.com/luulinh90s/paper-review-continual-learning/blob/master/images/imm/1.JPG)
![](https://github.com/luulinh90s/paper-review-continual-learning/blob/master/images/imm/2.JPG)
![](https://github.com/luulinh90s/paper-review-continual-learning/blob/master/images/imm/3.JPG)
