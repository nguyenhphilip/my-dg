---
title: causal inference
tags: [statistics]
---

# Introduction
## Something counterintuitive about correlation
Causation does not necessarily imply [correlation](notes/statistics/correlation.md).

Mixtape example: the sailor who is moving the rudder _in response_ to the wind. Because she is responding to the wind, you don't see any relationship between the movement of the rudder and the direction of the boat.

Another current example: social distancing and masking. We social distance and mask in response to the pandemic. But we don't see the case count go down, we just see cases not change. Yet it's quite likely that masking and social distancing was a very appropriate response, despite the lack of correlation between our response and the spread of the pandemic.

> Human beings engaging in optimal behavior are the main reason correlations almost never reveal causal relationships, because rarely are human beings acting randomly. And as we will see, it is the presence of randomness that is crucial for identifying causal effect.

Optimal behavior is conditioning.

On the necessity of assumptions in causality:

>It is my firm belief, which I will emphasize over and over in this book, that without prior knowledge, estimated causal effects are rarely, if ever, believable. Prior knowledge is _required_ in order to justify any claim of a causal finding.
>...
>In pursuing some goal while facing constraints, they chose certain things that created a spurious correlation with other things. And we see this problem reflected in the potential outcomes model itself: ==a correlation, in order to be a measure of a causal effect, must be based on a choice that was made independent of the potential outcomes under consideration==. Yet if the person is making some choice _based_ on what she thinks is best, then it necessarily is based on potential outcomes, and the correlation does not remotely satisfy the conditions we need in order to say it is causal. To put it as bluntly as I can, economic theory says ==choices are endogenous, and therefore since they are, the correlations between those choices and outcomes in the aggregate will rarely, if ever, represent a causal effect.==

Humans rarely make random CHOICES. Because of this, it is hard to know what is a spurious correlation and what is causal. 

In the context of science:

> Credible and valuable research requires that we believe that it is more important to do our work _correctly_ than to try and achieve a certain outcome (e.g., confirmation bias, statistical significance, asterisks).

This makes me think of the spurious correlation between the newsworthiness and trustworthiness of a particular science publication. (See the [selection distortion effect](notes/statistics/selection-distortion-effect.md)).

> When we are trying to describe the causal effect of some intervention, for instance, we are always assuming that the other relevant variables in the model are not changing.

See [linear ]regression](notes/statistics/linear-regression.md)

---