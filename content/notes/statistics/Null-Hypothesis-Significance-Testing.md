---
title: Null Hypothesis Significance Testing
tags: [statistics, frequentist]
aliases: [hypothesis testing, hypothesis significance testing]
---
# Given that the null hypothesis is true, how unlikely is the data? 

$$p(Data|H_0 = \text{True})$$

- If the likelihood of the data is unlikely (judged by a decision threshold: the [p-value](notes/statistics/p-value.md)), given that the null hypothesis is true, then we can reject the null hypothesis in favor of the alternative hypothesis

# The steps of NHST
* Formulate a hypothesis that embodies our prediction (without seeing the data)
* Specify the null and alternative hypotheses
* Collect data relevant to the hypothesis
* Fit a model to the data that represents the alternative hypothesis and compute a test statistic
* Compute the probability of observing the value of that test statistic assuming null hypothesis is true
* Assess the "statistical significance" of that result

# Common tests 
- For comparing group mean differences: [t-statistic](notes/statistics/t-statistic.md) and [t-test](notes/statistics/t-test.md)
