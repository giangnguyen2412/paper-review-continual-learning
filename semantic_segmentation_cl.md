## Summary
Contemporary
incremental learning frameworks focus on image classification and object detection while in this work we formally introduce the incremental learning problem for semantic segmentation in which a pixel-wise labeling is considered. To
tackle this task we propose to distill the knowledge of the
previous model to retain the information about previously
learned classes, whilst updating the current model to learn
the new ones. We propose various approaches working both
on the output logits and on intermediate features. In opposition to some recent frameworks, **we do not store any image from previously learned classes and only the last model
is needed to preserve high accuracy on these classes**

Some existing method to tackble Catastrophic forgetting:

- network architectures which grow during the training process.

- freezing or slowing down
the learning process on some relevant parts of the network

- **knowledge distillation**

-  keep a small portion of data belonging to
previous tasks and use them to preserve the accuracy on old
tasks when dealing with new problem. The exemplar set to store is chosen at random or according
to a relevance metric.

But Storing previously seen data could represent a serious
limitation for certain applications where privacy issues or
limited storage budgets are present. For this reason, some
recent methods [29, 35] do not store old data but compensate this by training Generative Adversarial Networks
(GANs) to generate images containing previous classes
while new classes are learned. By this way, (**We generate samples from GAN that can give benefits that we can have sample from old distribution as well obtain samples from a new class which are unseen**).

In this paper, contrary to
many existing methods, we consider the most challenging
setting where images from old tasks are not stored and cannot be used to help the incremental process, which is particularly relevant for the vast majority of applications with
*privacy concerns* or storage requirements.

## Methodology (See paper for details)
### Distill on Output layer
The first considered distillation term for semantic
segmentation is the masked cross-entropy loss between the
logits produced by the output of the softmax layer in the
previous model Mk−1 and the output of the softmax layer
in the current model Mk (assume that we currently are at
the k-th incremental step).

Now in training, with each sample, we compare the output of the Mk-1 model to that of the current Mk model by CrossEntropy.

<See equation 3 in paper>
### Distill on Intermediate Feature space
Semantic Segmentation has Encoder + Decoder, now we only distill knowledge on Encoder E.

A different approach we designed to preserve previous
knowledge by keeping the encoder similar to the already
learned model is to apply a knowledge distillation function
to the intermediate level of the features space before the decoding stage. 

<See equation 4 in paper>

## Experiments
There are theree experiments conduted in this papers and this should be applied in Continual Leanring for other Computer Vision task.

- Add one new class: In this one, just one class is added more, and the table of results is Table 1 in paper. An interesting aspect is that the changes in performance
on previously seen classes are correlated with the class being added. Some classes have even higher results in terms
of mIoU than before because their prediction has been reinforced through the new training set. For example, objects
of the classes sofa or dining table are typically present in
scenes containing a tv=monitor.

- Add five new class at one time: Five class are added at once. In
this setting the results are much lower than in the previous
cases where a single class was added at a time since there
is a larger amount of information to be learned. In particular, the fine-tuning approach exhibits an even larger drop in
accuracy because it overestimates the presence of the new
classes. In this setting the
distillation on the output layer, M1(16 − 20) with L'<D>,
achieves the highest accuracy. 
  
- Add five new class one by one:  5 classes are progressively added one by one: the
final model is referred to as M(16 -> 20). In this case freezing the encoder and distilling the knowledge is the best approach because the addition of one single class do not alter too much the responses of the whole
network: distilling the knowledge from the previous model
when the encoder is fixed guides the decoder to modify only
the responses for the new class.
## Novelties 
- re-frame the distillation loss concept used in
other fields and propose a novel approach where the distillation loss is applied to the intermediate features level.
- **freezing the encoder part of the network to preserve the feature extraction capabilities**.
- first
work on incremental learning for semantic segmentation
## Personal thoughts
### Pros
- First work applying CL with Semantic Segmentation
- Creative and concreate experiments
### Cons
- There are numerous approaches, why the authors use knowledge distillation? Its better to scale this paper to work with other method (expanding network, regularization, replay...). But that should be the future work, this paper is good enough.
