---
title: selection-distortion effect
aliases: [Berkson's Paradox]
tags: [Bayesian statistics]
---

[source:](https://thehardestscience.com/2014/08/04/the-selection-distortion-effect-how-selection-changes-correlations-in-surprising-ways/)

In [Statistical Rethinking](notes/statistics/Statistical-Rethinking.md), the author presents a particularly relevant example of how negative correlations arise from selection processes:

> It seems like the most newsworthy scientific studies are the least trustworthy.

There's no real underlying reason to believe that trustworthiness correlates with newsworthyness. But this spurious correlation can arise as a result of strict selection processes, such as selecting who gets science funding:

>  ... all that is necessary for such a negative correlation to arise is that peer reviewers care about both newsworthiness and trustworthiness. Whether it is grant review or journal review, if editors and reviewers care about both, then the act of selection itself is enough to make the most newsworthy studies the least trustworthy.
>
> Suppose a grant review panel receives 200 proposals for scientific research. Among these proposals, there is no correlation at all between trustworthiness (rigor, scholarship, plausibility of success) and newsworthiness (so- cial welfare value, public interest). The panel weighs trustworthiness and newsworthiness equally. Then they rank the proposals by their combined scores and select the top 10% for funding.

It's the selection and ranking, based on the top 10% (a strict criteria), that creates this spurious correlation:

> ![Pasted image 20210605122536.png](/notes/images/20210605122536.png)
>
> Strong selection induces a negative correlation among the criteria used in selection. Why? If the only way to cross the threshold is to score high, ==it is more common to score high on one item than on both.== Therefore among funded proposals, the most newsworthy studies can actually have less than average trustworthiness (less than 0 in the figure). Similarly the most trustworthy studies can actually be less newsworthy than average.

It's a kind of seasaw effect. Another example:

>  Why do so many restaurants in good locations have bad food? The only way a restaurant with less-than-good food can survive is if it is in a nice location. Similarly, restaurants with excellent food can survive even in bad locations. Selection-distortion ruins your city.

And the connection to multiple [linear regression](notes/statistics/linear-regression.md)? It can chew out spurious correlations and clear up masking effects. But it doesn't solve the selection-distortion effect:

>The selection-distortion effect can happen inside of a multiple regression, because ==the act of adding a predictor induces statistical selection within the model,== a phenomenon that goes by the unhelpful name [collider bias](notes/statistics/collider-bias.md). This can mislead us into believing, for example, that there is a negative association between newsworthiness and trustworthiness in general, ==when in fact it is just a consequence of conditioning on some variable==. This is both a deeply confusing fact and one that is important to understand in order to regress responsibly.

