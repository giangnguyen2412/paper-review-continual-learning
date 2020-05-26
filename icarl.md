# iCaRL: Incremental Classifier and Representation Learning
This paper defines term 'class-incremental learning' as follows: At
the very least, a visual object classification system should be
able to incrementally learn about new classes, when training data for them becomes available. We call this scenario
class-incremental learning.

*  it should be trainable from a stream of data in which
examples of different classes occur at different times,
*  it should at any time provide a competitive multi-class
classifier for the classes observed so far,
* its computational requirements and memory footprint
should remain bounded, or at least grow very slowly,
with respect to the number of classes seen so far.

The first two criteria express the essence of classincremental learning. 
The third criterion prevents trivial algorithms, such as storing all training examples and 
retraining an ordinary multi-class classifier whenever new data becomes available

In experiments, they proposes two datasets.

- iCIFAR100: we use the CIFAR-100 [16] data and train all 100
classes in batches of 2, 5, 10, 20 or 50 classes at a time.
- iILSVRC: we use the ImageNet
ILSVRC 2012 [35] dataset in two settings: using only a
subset of 100 classes, which are trained in batches of 10
(iILSVRC-small) or using all 1000 classes, processed in
batches of 100 (iILSVRC-full).
