---
title: markov chain monte carlo
---

A class of sampling algorithms based on [Monte Carlo methods](notes/statistics/Monte-Carlo-methods.md)

Idea: After a massive number of samples, the probability of different realizations of a random variable converge to the true probabilities

![Pasted image 20210316165456.png](/notes/images/20210316165456.png)

---

# Metropolis-Hastings algorithm
One example of MCMC. It's a method of getting samples of parameter values from unknown posterior distributions.

Via wikipedia: 

> The algorithm can estimate any distribution P provided a function $f(x)$ that is proportional to P and the values of $f(x)$ can be calculated. In the Bayesian setting, $f(x)$ is the likelihood times the prior, and the posterior is P. 

The algorithm produces a sequence of values where each sampled value is dependent on the previous value. (this is the Markov Chain part)

> Specifically, at each iteration, the algorithm picks a candidate for the next sample value based on the current sample value. Then, with some probability, the candidate is either accepted (in which case the candidate value is used in the next iteration) or rejected (in which case the candidate value is discarded, and current value is reused in the next iteration)—the probability of acceptance is determined by comparing the values of the function $f(x)$ of the current and candidate sample values with respect to the desired distribution.

According to [Ritvikmath](https://www.youtube.com/watch?v=yCv2N7wGDCw), there is a "burn-in" (number of warm-up samples in `brms`) period where samples are necessarily drawn but discarded. We need these burn samples so that future samples are more likely to represent the posterior distribution (this assumes that if we keep drawing we will eventually get to P, which is a stationary distribution).

### The intuition
What we want to do is estimate a distribution P. We think it takes the form of f(x), or is close to it, so we can generate p(x) using samples generated with a function f(x). 

Why this works is that the distribution of our samples will eventually approach a stationary state, which is P, after a "burn-in" period.

Start by generating a (f(x)) value which is a candidate that we accept with a probability determined by some acceptance criteria. Intuitively, values located in denser regions of our target distribution are more likely to be accepted and therefore "moved to" to serve as the next value of the markov chain than values that are less likely. If you don't accept the next value, then the current value serves as the candidate value for the next time step.

## Gibbs sampling is a variant of MH

requires fewer samples to estimate the posterior than other comparable Metropolis approaches.