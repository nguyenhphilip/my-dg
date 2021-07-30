---
title: covariance
tags: [statistics]
---

#flashcards 

# Relation to variance
 
[variance](notes/statistics/variance.md) alone cannot tell you about the relationship between two variables.  Covariance, then, is a useful measure of how two variables relate, or covary, with each other. 

Formally covariance is the expected product of two mean-centered variables:

$$Cov(X,Y) = E[(X-E(X))(Y-E(Y))]$$

It's usually computed as:

$$Cov(X,Y) = \frac{1}{n-1}\sum_{i}{(x_i - \bar{x})}{(y_i - \bar{y})}$$

Some properties:

$$Cov(X,Y) = E(XY) - E(X)E(Y)$$

# Relation to [correlation](notes/statistics/correlation.md)

Covariance gives direction of the relationship, but not strength. That's where [correlation](notes/statistics/correlation.md) comes in, which is the covariance of the two variables under consideration, normalized by their ==standard deviations==:

$$corr(x,y) = \frac{cov(x,y)}{\sqrt{var(x)}\sqrt{var(y)}} = \frac{cov(x,y)}{sd(x)sd(y)}$$

Remember that [notes/statistics/variance](notes/statistics/variance.md) is [standard deviation](notes/statistics/standard-deviation.md)squared:

$$sd(x) = \sqrt{\frac{1}{n-1}\sum_{i}{(x_i - \bar{x})^2}} = \sqrt{var(x)}$$