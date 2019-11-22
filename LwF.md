## TL;DR
**The approach with a regularization term also has received attention. Learning without forgetting
(LwF) is one example of this approach, which uses the pseudo-training data from the old task [7].
Before learning the new task, LwF puts the training data of the new task into the old network,
and uses the output as pseudo-labels of the pseudo-training data. By optimizing both the pseudotraining data of the old task and the real data of the new task, LwF attempts to prevent catastrophic
forgetting.**

From: Overcoming Catastrophic Forgetting by Incremental Moment Matching

In paper setting, a CNN has a set of shared parameters θs (e.g., five convolutional layers and two fully 
connected layers for AlexNet [3] architecture), task-specific parameters for previously learned tasks θo 
(e.g., the output layer for ImageNet [4] classification and corresponding weights), and randomly initialized 
taskspecific parameters for new tasks θn.

Currently, there are three common approaches:

**Feature Extraction** (e.g., [5]): θs and θo are unchanged, and the outputs of one or more layers are used as features
for the new task in training θn.

**Fine-tuning** (e.g., [6]): θs and θn are optimized for the new task, while θo is fixed. A low learning rate is typically
used to prevent large drift in θs.

It is also possible to use a variation of fine-tuning where
part of θs – the convolutional layers – are frozen to prevent
overfitting, and only top fully connected layers are finetuned. This can be seen as a compromise between finetuning and feature extraction. In this work we call this
method **Fine-tuning FC** where FC stands for fully connected.

**Joint Training** (e.g., [7]): All parameters θs, θo, θn are
jointly optimized, for example by interleaving samples from
each task.

Each of these strategies has a major drawback. Feature
extraction typically underperforms on the new task because
the shared parameters fail to represent some information
that is discriminative for the new task. Fine-tuning degrades
performance on previously learned tasks because the shared
parameters change without new guidance for the original
task-specific prediction parameters.

In this paper, we expand on our previous work [10],
Learning without Forgetting (LwF). Using only examples
for the new task, we optimize both for high accuracy for the
new task and for preservation of responses on the existing
tasks from the original network. Our method is similar
to joint training, except that our method does not need
the old task’s images and labels.
![](https://github.com/luulinh90s/paper-review-continual-learning/blob/master/images/learning%20without%20forgetting/1.JPG)
![](https://github.com/luulinh90s/paper-review-continual-learning/blob/master/images/learning%20without%20forgetting/2.JPG)

**It should be noted that the recored prediction of the old model on the new data is is soft-label. They use the temperate from Knowled Distillation to encourage the student to mimic teacher's behaviors**

There exist some limitations in LwF. First, for preserving the performance
on old tasks, the target model adapts to a new task with the constraint of
mimicking the output of Original CNN as much as possible. Though sometimes
this constraint provides useful regularization to the cases with rare new samples,
it is also likely to hinder the adaptation to the new task. Second, the performance
on old tasks degrades a lot when the model is exposed to a long sequence of
tasks for different domains [3] since the loss for old tasks is computed on the new
coming data which is likely to be drawn from a significantly different distribution
compared to the previous data.

