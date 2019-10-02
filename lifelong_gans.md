*use knowledge distillation leveraging conditional GANs to generate images conditioned either on label or image*

Recent efforts [30, 4, 9] have demonstrated how discriminative models could be incrementally learnt for a sequence
of tasks. Despite the success of these efforts, lifelong learning in generative settings remains an open problem. The state-of-the-art continual learning
generative frameworks [28, 34] are built on memory replay
which treats generated data from previous tasks as part of
the training examples in the new tasks. Although memory
replay has been shown to alleviate the catastrophic forgetting problem by taking advantage of the generative setting,
its applicability is limited to label-conditioned generation
tasks. In particular, replay based methods cannot be extended to image-conditioned generation. The reason lies in
that no conditional image can be accessed to generate replay
training pairs for previous tasks. Therefore, a more generic
continual learning framework that can enable various conditional generation tasks is valuable.
