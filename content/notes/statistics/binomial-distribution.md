---
title: binomial distribution
tags: [statistics, bayesian]
---

The binomial distribution is the generalized version of the Bernoulli distribution where instead of calculating the probability of success of a single event, we want the probability of $k$ successes in $n$ trials (in the Bernoulli $n=1$).

The probability of $k$ successful outcomes over $n$ trials is given by : $$P_k = {n \choose k}{p^k}{(1-p)^{n-k}}$$

The binomial distribution is the most consistent distribution - it maximizes entropy - given these constraints:

1) only two unordered outcomes are possible
2) expected number of each type is constant

expected value: *np*