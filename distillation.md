## Definition
Knowledge distillation is model compression method in which a small model is trained to mimic a pre-trained, larger model (or ensemble of models). This training setting is sometimes referred to as "teacher-student", where the large model is the teacher and the small model is the student 
Knowledge distillation’s goal is to transfer the learning from one performant and heavy teacher to a more compact student.

![](https://data-soup.gitlab.io/kd-dist/teacher-student.png)

To do so, we look at the teacher’s softmax layer, magnify it and the student learns how to produce them.
We need to magnify because the softmax layer will smash down to zero the least probable classes and rises close to one the most probable (like one hot vector). We can also keep the relative probabilities between classes, where a motocycle and a bicycle share more similarities on the softmax layer rather than a book. We can do it by raising the temperature T.

## Loss
Distillation loss is generally in two forms: matching function values, matching derivatives or both, corresponding to a regression problem with different orders:

Matching function values: tries to minimize the difference between the predictions of the teacher and the student. For a classification task, this is done by using classical cross entropy.

Matching derivatives: tries to match the values and the derivatives. This is a more efficient approach than before because here we can have full access to the teacher and we are able to measure the impacts of small variations in its inputs.T

The diagram of distillation is as follow:
![](https://nervanasystems.github.io/distiller/imgs/knowledge_distillation.png)

Here we train the student normally, but at the output layer, we use a softmax function with T=t. The customized softmax function is as below:

![](http://3.bp.blogspot.com/-1Nv7Li7ZgIU/Vbcbz20mJvI/AAAAAAAABBo/qS9VPa3p7mM/s1600/%25E6%2593%25B7%25E5%258F%2596.PNG)

We then compute the difference between output of teacher and student and add this to the loss function (2nd part of below equation). First part of this equation is the normal cross-entropy loss when we compute the loss by log entropy function.

![](https://github.com/luulinh90s/paper-review-continual-learning/blob/master/images/loss_function_knowledge_distillation.JPG)

A cool implementation of distillation can be found [here](https://github.com/Ujjwal-9/Knowledge-Distillation/blob/master/knowledge_distillation_for_mobilenet.ipynb)
