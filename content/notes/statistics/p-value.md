---
title: p-value
aliases: [p-values]
---

#flashcards 

p-value: the probability of observing a difference between the ==statistic== of two groups, when there is no true difference at all (false positive), over many rounds of observations (experiments, resamples, etc).
<!--SR:!2021-08-02,14,250-->

What this requires is that you calculate a test statistic that summarizes and compares two groups together. The p-value is the probability that you observe that test statistic under the null hypothesis.

The alpha/cutoff value is your tolerance level for ==false positives==, or [Type-I-error](notes/statistics/Type-I-error.md). If $\alpha= 0.05$, then 5% of calculated test statistics will produce a false positive. 
<!--SR:!2021-08-05,17,250--> 

p-values are composed of three parts:
	1. the probability that random chance would result in the observation
	2. the probability of observing something else equally rare
	3. the probability of observing something rarer or more extreme
	
Relatedly, [statistical-power](notes/statistics/statistical-power.md) is the probability that you ==correctly reject== the null hypothesis.
<!--SR:!2021-08-27,31,250--> 

---

# How to calculate a p-value
Imagine that you have two groups of people. You hypothesize that they will be different in some regard, say, physical performance, after giving one group a drug and the other a placebo. One way of determining whether or not there is a difference is to conduct a [t-test](notes/statistics/t-test.md). 

To do this you determine the distribution of each group, then calculate the means and compare them using the test, which provides a [t-statistic](notes/statistics/t-statistic.md). Once you have your [t-statistic](notes/statistics/t-statistic.md), you can calculate a [p-value](notes/statistics/p-value.md) using a [t-distribution](notes/statistics/t-distribution.md). To calculate a [t-distribution](notes/statistics/t-distribution.md), take samples from a hypothetical distribution centered on your hypothesized null value, which represents the assumption that there is no effect, and calculate a ton of [t-statistic](notes/statistics/t-statistic.md)s. What you're looking for then is the extremity of your actual [t-statistic](notes/statistics/t-statistic.md), aka the [p-value](notes/statistics/p-value.md), under the sampled null [t-distribution](notes/statistics/t-distribution.md).