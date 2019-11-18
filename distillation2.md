# Learning from a Teacher using Unlabeled Data
This paper introduces a new option of knowledge distillation called blind distillation.

## Blind distillation
The blind distillation is as follows:
1. Train a teacher model on a labeled dataset A
2. After training, continue with an unlabelled dataset B (A and B are not related).
With dataset B, perform distillation from teacher model to student model.

The key difference here is that in the objective function of student, there is no standard loss between student prediction and 
groundtruth because dataset B is unlabelled. The objective function is only the discrepancy between predictions of student and 
teacher. We repeat this distillation until convergence.

After distillation, now we evaluate the student model on the test set of dataset A.

Note that the student model S trained with this method has not seen any examples from the labeled
set XL during training. The only source of information it has about the distribution of XL is through
the teacher model T, and the information the teacher model can extract from XU. Hence, we refer to
this method as Blind Distillation.


## Fine-tune with labeled data
The unlabeled data being used in the Blind Distillation phase will very likely have a different
distribution as compared to the labeled data. Since the student model is finally evaluated on the
labeled data, we can improve its using a part of the original labeled dataset since this is available.

1. Train the student model S, with the Blind Distillation method above.
2. Create a subset of the labeled training dataset with n samples per class
3. Fine tune the model S by distilling from the teacher model T using examples the labeled subset.
Let us refer to the model trained by this fine-tuning as S'.

During our experiments, we found that fine-tuning with a low learning rate (when compared to the
Blind Distillation phase) with a steady decay, helps keep the student model’s loss within a reasonable
range. This is intuitive because the student model has been trained to expect examples from the
unlabeled dataset’s distribution. Introducing examples from the labeled distribution without a careful
learning rate schedule would suddenly lead to a large gradient flow.

## Exps 
The experiments show that blind distillation + fine tuning (read 3.2 for more details of this type of fine tuning) helps student outperform teacher in some datasets.
