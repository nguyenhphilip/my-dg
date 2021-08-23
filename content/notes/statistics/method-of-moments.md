---
title: method of moments
creation date: 2021-08-17 11:16
---

# How they work
Assume we have a population, and within that population there exist processes that generated it, and that we expect certain [Expectation](notes/statistics/Expectation.md) values. We don't know those values, but the moment of methods says that we can estimate them using our sample.

This is best demonstrated with an example. Suppose we know that there exists some expectation operator such that $E[X]=\mu$ in the population of interest. We don't know what $\mu$ is, but we can use our sample to estimate it. From the Weak Law of Large Numbers $$E[X] \approx \frac{1}{N}\sum_i^N x_i$$. The larger the sample size, the better the estimate.

The same principle can be applied to other moments of the population, e.g. $E[X^2]$. More generally, for any moment $$E[f(x)] \approx \frac{1}{N} \sum_i^N f(x_i)$$

If the number of moment conditions is greater than the number of parameters we have to estimate, we enter a kind of optimization problem where we estimate values of the parameters that best satisfy some condition. This is [general method of moments estimation](notes/statistics/general-method-moments.md).

# Benefits
- no need to specify an exact distribution, just different moments of the population. useful for when the distribution is unknown or analytically intractable.
- robust to distributional assumptions
- deals with nonlinearities well