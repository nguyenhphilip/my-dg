---
title: maximum likelihood estimation
aliases: [maximum likelihood estimate]
---

### What is a likelihood?

How likely is it that we observe the data we have under a specific model, given a set of parameter values that define it. Maximizing the likelihood means choosing estimates of the parameters that produce a model that best matches our data. 

Actually calculating the MLE involves calculating the likelihood for each case/observation under a specified model, and then taking the product of each likelihood together. E.G. for a simple binomial example involving estimating the probability of having a boy in a family:

![Pasted image 20210616113428.png](/notes/images/20210616113428.png)

In an example case where we want to find a $p_\beta$ that best fits the data:

> The “best” estimate of $p_\beta$ would be the value where we are most likely to see our data from all possible values between 0 and 1.
> ...
> In many, but not all, circumstances, we can obtain an MLE exactly using calculus. In this simple example (one case, GBB), the MLE is 2/3. This is consistent with our intuition since 2 out of the 3 children are boys.

As the number of observations increases, we reduce the variance in our maximum likelihood estimation.

> In summary, we constructed a likelihood that reflected features of our Sex Unconditional Model, then we approximated the parameter value for which our data is most likely using a graph or software, or we determined our optimal parameter value exactly using calculus.