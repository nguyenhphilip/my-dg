---
title: Ulysses' Compass - Ch 7 Statistical Rethinking
tags: [statistics, bayesian]
---

# Ulysses' Compass

A chapter about overfitting, underfitting, prediction models vs. causal mechanism models.

## The problem with Parameters

Adding more parameters to a model will usually improve prediction, despite the lacking causal associations. That's because the model can retrodict the data to fit the model.

[variance](notes/statistics/variance.md) explained (by [R-squared](notes/statistics/R-squared.md)): 

- $R^2 = \frac{var(outcome)-var(residuals)}{var(outcome)} = 1 - \frac{var(residuals)}{var(outcome)}$
- $R^2$ increases even if we add random numbers as predictors that have no association to the outcome

## Entropy and Accuracy

In navigating overfitting and underfitting, we must choose some measure of model performance. What do we want the model to be good at? [information theory](notes/statistics/information-theory.md) provides a common and useful criterion for what we want the model to be good at, a target so to speak.

Steps:

1) determine a scale for distance from accuracy (loss function?)
	a) this requires information theory (to determine how different two probability distributions are)
2) use that scale to determine deviance, or relative accuracy from perfect accuracy
3) establish out-of-sample deviance

From entropy to accuracy: we can use [KL Divergence](notes/statistics/KL-Divergence.md) to quantify how much additional uncertainty is incurred by using probabilities from one distribution (q) to describe another (say p).

[KL Divergence](notes/statistics/KL-Divergence.md)Divergence: $$D_{KL}(p,q) = \sum_{i} p_i(\log{p_i}-\log{q_i}) = \sum_{i} p_i \log{\frac{p_i}{q_i}}$$

In words, KL divergence is the average / expected log difference of the probabilities from p (target) and q (model), in units of entropy.

Cross entropy: when you use probabilities of one distribution (q) to predict events from another, you get cross entropy: $$H(p,q) = -\sum_{i} {p_i}{\log{q_i}}$$

Divergence is just the additional entropy incurred by using a model q instead of p. So divergence is: $$D_{KL}(p,q) = H(p,q) - H(p)$$ which equals $$= -\sum_{i}{p_i}{\log(q_i)} - (-\sum_{i}{p_i}{\log(p_i)}) = -\sum_{i}{p_i}{(\log(q_i) - \log(p_i))}$$.

## Estimating Divergence
Deviance is a measure of predictive accuracy. It compares the performance of one model to another, using the sum of log probabilities.

To calculate it, we sample from the posterior $S$ times for $S$ sets of parameter values. Then we average over the log probability of our data (say brain size), given each set of parameter values. More mathematically, and in Bayesian land, we calculate the log-pointwise-predictive-density:

$$lppd(y,X) = \sum_{i} \log \frac{1}{S} \sum_{S}p(y_i | X_{s})$$

where $y$ is a vector of observed values and $X$ is a matrix of parameter values (each row is a different set of parameters).


![Pasted image 20210609104403](/notes/images/20210609104403.png)

In the picture we have 5 models and therefore 10 $lppd$ scores, given a training and testing set.

## predicting predictive accuracy

[cross validation](notes/statistics/cross-validation.md) and information criteria are both strategies for approximating how well our models perform on test/unseen data.

### [cross validation](notes/statistics/cross-validation.md)

involves leaving out chunks of data to test on while training on the rest. In this context we want to estimate the out-of-sample log-pointwise-predictive-density.

Often we want to approximate the cross-validation score since, at least in the context of LOOCV, training on every sample may be time consuming. One way to do this is to use pareto-smoothed importance sampling cross-validation.

### information criteria
calculate an expected out-of-sample score using a theorhetical estimate of the relative out-of-sample KL divergence.

#### AIC: 

simple estimate of out-of-sample deviance: $$AIC = D_{train} + 2p = -2lppd + 2p$$ where p is the number of free parameters in the posterior distribution.

> What AIC tells us is that the dimensionality of the posterior distribution is a natural measure of the model’s overfitting tendency. More complex models tend to overfit more, directly in proportion to the number of parameters.

reliable when:

1) The priors are flat or overwhelmed by the likelihood (lots of data)
2) the posterior is approximately multivariate gaussian
3) sample size is greater than number of parameters

#### DIC: Deviance Information Criterion

More general than AIC since we usually want more than flat priors. Still assumes that sample size >> number predictors, and a multivariable guassian.

#### WAIC: Widely Applicable Information Criterion

makes no assumption about shape of posterior. the out-of-sample deviance provided converges to the CV approximation in a large sample

> it's the lppd we calculated earlier, plus a penalty proportional to the variance in the posterior distributions:

$$WAIC(y, \Theta) = -2(lppd - \sum_{i} var_{\theta} \log p(y_i | \theta))$$

> where $y_i$ is the observations and $\Theta$ is the posterior distribution. You can think of each observation $y_i$ as having its own personal penalty score (the penalty term: the variance for the log probability of each observation i, summed)