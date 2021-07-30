---
title: standard deviation
---

How far each observation 'deviates' from the mean of the group. The standard deviation of a vector of values $x$ is:

$$SD_x = \sqrt{\frac{1}{n-1}\sum_i {(x_i - \bar{x})^2}} = \sqrt{Var(X)}$$

The $\frac{1}{n-1}$ term is the Bessel correction for bias in the estimation of the population variance

To get the sample [variance](notes/statistics/variance.md), you can square $SD$