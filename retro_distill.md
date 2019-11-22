# Lifelong Learning via Progressive Distillation and Retrospection

## How it works

### Distillation
This paper also proposes an idea of using Knowledge Distillation but in a really creative way. I will show the model here and explain on the model.
![](http://mmlab.ie.cuhk.edu.hk/projects/lifelong/res/network_structures.png)

Here, a new model will get the distilled knowledge from two models. 

1. The Expert CNN - an expert CNN is trained purely on the new task (purely here means we train normally from beginning - weights are randomly initialized).
So by using this, we can distill the new knowledge to the teacher model. Its Loss_new in the diagram.

2. The Original CNN - its the model acquired from the old tasks, so by using this, we hope that the knowledge from the old task can be distilled to the student.
The loss component from this model is Loss_old.

The final outputs are F* (Feature Extractor) and T*(task-specific classifier) for the target model (target model is what we want to achieve).

### Retrospection
Retrospection means that a small fraction of data for old tasks is reserved for lifelong learning.
In this method, we distill the knowledge from the old models to the current model via the small amount of data we preserve.
Stills, this loss component is calculated as the different between the predictions of the current model and old models on the old samples.
![](https://github.com/luulinh90s/paper-review-continual-learning/blob/master/images/retro.png)
