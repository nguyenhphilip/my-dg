---
title: Cross-Entropy
creation date: 2021-08-04 15:25
---

In the context of neural networks, the cross entropy function takes in the output of the [softmax](softmax.md) function along with the correct labels for each observation and calculates the cross entropy. The cross entropy is the entropy of correct-label distribution plus the [KL-Divergence](notes/statistics/KL-Divergence.md) of the correct-label distribution and the predicted-label distribution.

Cross Entropy Loss on a training example $i$: $$L_{i} = \sum_j = -Y_{ij}
log(q_j) = -\log(q_{l_i})$$

Since $Y_{ij}$ is a one hot encoded vector, the multiplication in the middle ends up to be the log term on the right, which is the negative log of $q_{l_i}$, or the softmax ($q$) of the correct label ($l_i$).