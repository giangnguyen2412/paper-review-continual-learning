Existing methods struggle to scale up to a large number of classes. 
Authors believe this is because of the combination of two factors: 

(a) the data imbalance between the old and new classes, and 

(b) the increasing number of visually similar classes. 

Distinguishing between an increasing number of visually similar classes is particularly 
challenging, when the training data is unbalanced. They propose a simple and effective method to address this data imbalance issue. 

They introduce a new technique: BiC (**Bi**as **C**orrection) method belongs to the third category (using exemplars from old tasks). They
first locate a strong bias in the classifier layer (the last fully
connected layer), and then apply a linear model to correct
the bias using a small validation set. The validation set is a
small subset of exemplars which is excluded from training
and used for bias correction alone.

Experiments on ImageNet 1000 classes and and Celeb 10000 (10000 classes). 

They first get Knowledge distillation as the baseline for evaluation. Then they prove that the last FC layer are highly biased towards new classes.
Finally, applying a linear model with a small
validation set. 
