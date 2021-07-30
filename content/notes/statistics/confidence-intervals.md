---
title: confidence intervals
tags: [statistics]
aliases: [confidence interval]
---

the theoretical long-run proportion of confidence intervals that contain the true value of the unknown parameter being estimated 

> R Psychologist: 95% confidence is a confidence that in the long-run 95 % of the CIs will include the population mean. It is a confidence in the algorithm and not a statement about a single CI.
> 
>In other words, 90% of confidence intervals computed at the 90% confidence level contain the parameter, 95% of confidence intervals computed at the 95% confidence level contain the parameter, 99% of confidence intervals computed at the 99% confidence level contain the parameter, etc.[\[2\]](https://en.wikipedia.org/wiki/Confidence_interval#cite_note-:3-2)

Confidence intervals are probability statements about confidence intervals, not the probability of the population parameter itself – the parameter either is or isn't in the interval, once you calculate the intervals

> Confidence intervals are notoriously confusing, primarily because they don’t mean what we might intuitively think they mean. If I tell you that I have computed a “95% confidence interval” for my statistic, then it would seem natural to think that we can have 95% confidence that the true parameter value falls within this interval. However, as we will see throughout the course, concepts in statistics often don’t mean what we think they should mean. In the case of confidence intervals, we can’t interpret them in this way because the population parameter has a fixed value – it either is or isn’t in the interval, so it doesn’t make sense to talk about the probability of that occurring. 
> 
> Instead, we have to view the confidence interval procedure from the same standpoint that we viewed hypothesis testing: As a procedure that in the long run will allow us to make correct statements with a particular probability. Thus, the proper interpretation of the 95% confidence interval is that it is an interval that will contain the true population mean ==95% of the time== (meaning that if you do the experiment several times and estimate a 95% confidence interval, 95% of them will contain the unknown parameter)
- Calculating CI using [bootstrap method](notes/statistics/bootstrap-method.md) (useful for non-normal distributions)