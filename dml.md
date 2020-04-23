# Deep Mutual Learning
The idea is super simple and straightforward. 
Training network simultaneously and add KL_div loss of to the oppose.

If we have two networks.

- The overall loss function LΘ1
for network Θ1 is defined as
LΘ1 = LC1 + D_KL(p2|p1).
- Similarly, the objective loss function LΘ2
for network Θ2 can be computed as
LΘ2 = LC2 + D_KL(p1|p2).

- In the case that we have N networks, the i-th network will be teached by N-1 remaining networks and the additional 
term of loss if the average KL_div loss of all the N-1 networks with the i-th network.

- The experiments are on CIFAR-100 and Market-1501. However, when they compare with Knowledge distillation, I dont think this comparison
is cogent. However, this should benefit continual learning, comparing to knowledge distilaltion.

