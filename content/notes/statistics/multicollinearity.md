---
title: multicollinearity
aliases: [Multicollinearity, collinearity]
tags: [statistics]
---

Multicollinearity refers to two or more predictor variables that are correlated with each other.

What's the problem with correlated predictors in [linear regression](notes/statistics/linear-regression.md)? It can be misleading.

>  The consequence of multicollinearity is that ==the posterior distribution will seem to suggest that none of the variables is reliably associated with the outcome, even if all of the variables are in reality strongly associated with the outcome.== This frustrating phenomenon arises from the details of how [linear regression](notes/statistics/linear-regression.md) works.
>  
>    In fact, there is nothing wrong with multicollinearity. The model will work fine for prediction (see: [Collinearity isnt une maladie that needs curing](notes/statistics/Collinearity-isnt-une-maladie-that-needs-curing.md)). ==You will just be frustrated trying to understand it.== The hope is that once you understand multicollinearity, you will better understand regression models in general.

Example: predicting height using the length of BOTH legs in a [multiple linear regression](notes/statistics/linear-regression.md) model.

[Multiple linear regression](notes/statistics/linear-regression.md) answers the question of: what new information do we gain about each predictor, given that we know the value of all the other predictors?

Mathematically, we want to know each beta value: 

$y_i$ ~ $Normal(m_i, \sigma)$
$m_i = \alpha + \beta_{1}{x_{i1}} + \beta_{2}{x_{i2}}$.

But what we get, when say $x_1$ and $x_2$ are highly correlated with each other is:

$y_i$ ~ $Normal(m_i, \sigma)$
$m_i = \alpha + (\beta_{1} + \beta_{2})x_i$.

The betas in the first equation inform us of how 'important' each predictor is, whereas the betas in the second equation are inseparable due to the highly correlated values of the predictors - i.e. the predictors are treated the same, mathematically, s.t. only the sum of $\beta_1$ and $\beta_2$ influence $m_i$.

>  When two predictor variables are very strongly correlated, including both in a model may lead to confusion. The posterior distribution isn’t wrong, in such cases ([the association between predictor and outcome is quantified by the sum of the betas of the correlated variables, rather than the independent beta values themselves]). It’s telling you that the question you asked cannot be answered with these data. And that’s a great thing for a model to say, that it cannot answer your question. And if you are just interested in prediction, you’ll find that this leg model makes fine predictions. ==It just doesn’t make any claims about which leg is more important.==

==**(a) moral of the story: KNOW YOUR VARIABLES!**==

