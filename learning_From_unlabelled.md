# Learning from a Teacher using Unlabeled Data

The original training and test datasets are referred to as the labeled (L) training and test datasets.
We also assume that we have access to an ideally large unlabeled (U) dataset, which belongs to
the same modality as our labeled dataset and drawn from a related, but not necessarily the same
distribution. Even if this dataset does have labels, we would ignore them. 

##  Blind Distillation

![](https://github.com/luulinh90s/paper-review-continual-learning/blob/master/images/unlabel.JPG)

Note that the student model S trained with this method has not seen any examples from the labeled
set X_L during training. The only source of information it has about the distribution of X_L is through
the teacher model T, and the information the teacher model can extract from X_U. Hence, we refer to
this method as Blind Distillation.

## Fine-Tune with Labeled Data
The unlabeled data being used in the Blind Distillation phase will very likely have a different
distribution as compared to the labeled data. Since the student model is finally evaluated on the
labeled data, we can improve its using a part of the original labeled dataset since this is available.

![](https://github.com/luulinh90s/paper-review-continual-learning/blob/master/images/fine-tune-unlabel.JPG)

During our experiments, we found that fine-tuning with a low learning rate (when compared to the
Blind Distillation phase) with a steady decay, helps keep the student model’s loss within a reasonable
range. This is intuitive because the student model has been trained to expect examples from the
unlabeled dataset’s distribution. Introducing examples from the labeled distribution without a careful
learning rate schedule would suddenly lead to a large gradient flow.
