---
title: mutual information
---

An [information theory](notes/statistics/information-theory.md) metric that evaluates how much two features (distributions) 'depend' on each other. (see also [KL-Divergence](notes/statistics/KL-Divergence.md))

If knowing the value of one feature is highly predictive of the value of another feature, than those two features have high mutual information.

Conversely, if knowing the value of one feature does not help in predicting the other, they are likely to be reletively independent and unpredictive, and therefore share low mutual information.

---

$$I(X,Y) = H(X) + H(Y) - H(X,Y)$$

Properties:

If measuring the information Y provides about X, and that information is 0, then

$$I(X;Y) = H(X) - H(X,Y)\ $$
$$= H(X) - H(X|Y) = H(X) - H(X) = 0$$