---
title: simulation course
author: Dorothy Bishop
---

# Lecture 1

### Why Simulate?
- insight into analysis plan
- Anticipate what your data looks like
- [statistical power](notes/statistics/statistical-power.md) analysis
- best way to understand [p-values](notes/statistics/p-value.md) and p-hacking
- replicate effects of other studies and do statistics to verify results

### Basic Idea
- things we measure have an effect of interest plus random noise
- how much of that is noise, and how much is an effect? And if there is an effect, how big is it?
- classical [p-value](notes/statistics/p-value.md)  [Null Hypothesis Significance Testing](notes/statistics/Null-Hypothesis-Significance-Testing.md) focuses on whether we have a real effect or just noise. (but not the magnitude)
- simulations allow us to create scenarios that generate noise, with or without a consistent added effect

### P-Hacking
Context of experiments is important:

> Key error is to treat a [p-value](notes/statistics/p-value.md) as an indicator of importance of a finding, regardless of context

Often people run many statistical tests (e.g. 16 in this case), which increases the probability that you will find _some_ effect, regardless of any actual effect. In fMRI studies, because you are running so many tests (comparing many voxels against each other), the risk of false positives is ridiculously high. Multiple corrections helps.

The [p-value](notes/statistics/p-value.md) supposes that you haven't seen the data before you generate your hypotheses and test them. You have to hypothesize first, before seeing the data.

What often happens is that people will run a test and find nothing significant. Then they look at the data and see something interesting and run another test. I.E they see a positive effect of a drug on people over age 36, subset the data to only include them, generate a new hypothesis [the drug works on people over age 36], and run another test that is likely to be statisically significant.

> You cannot use the same data to both generate a hypothesis and test the hypothesis.

In the case of exploration, you can sample groups for exploration. But if you see a possible effect, you can't run a statistical test on that same sample. You have to resample for the [p-value](notes/statistics/p-value.md) to mean anything.

- One solution to this is to use half the dataset for exploration and the other half for hypothesis testing.

A mnemonic for [Type I error](notes/statistics/Type-I-error.md) and [Type II error](notes/statistics/Type-II-error.md): the boy who cried wolf:

> The first time he cried wolf it was a ==[Type I error](notes/statistics/Type-I-error.md)==; the second time it was a ==[Type II error](notes/statistics/Type-II-error.md)== #flashcards
<!--SR:!2021-07-31,29,250!2021-08-01,30,250--> 

# Lecture 2
> The human brain is good at reasoning about means, but bad at reasoning about variance

