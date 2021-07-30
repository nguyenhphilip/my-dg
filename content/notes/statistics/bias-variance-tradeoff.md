---
title: bias-variance tradeoff
tags: [statistics, machine-learning]
---

[variance](notes/statistics/variance.md) and [bias](notes/statistics/bias.md) refer to under and overfitting on the data. 

---

# Wikipedia on the bias-variance tradeoff:

[bias](notes/statistics/bias.md) is error from erroneous assumptions in the ==model/learning algorithm== [e.g. using linear models when the data is non-linear -> high bias, more generalizable; not using enough predictors or predictors that may be important to the outcome -> high bias]. High bias causes the model to miss the relevant relations between features and target outputs, which leads to ==underfitting==. #flashcards
<!--SR:!2021-08-22,26,250!2021-08-23,27,250--> 

[variance](notes/statistics/variance.md) is an error from ==sensitivity to small fluctuations== in the training set. Having high variance may result from a model/algorithm that overfits to noise in the training data (overfitting). I.e. the model is a complex one.
<!--SR:!2021-08-17,21,210--> 

---

Models with high ==[bias](notes/statistics/bias.md)== tend to underfit on the training data and the testing data.
<!--SR:!2021-08-15,19,250-->

Models with too high ==[variance](notes/statistics/variance.md)== tend to fit well on the training data, but  do not generalize well.
<!--SR:!2021-08-15,19,250-->

---

[variance](notes/statistics/variance.md) is related to sample size. we can reduce sampling variability with more samples. 

[bias](notes/statistics/bias.md) is related to model choice and feature selection. If a feature is related to the outcome but we don't use it, we run into the problem of high bias and underfitting.

# Mathematically
If $Y$ is the variable we are trying to predict with covariates $X$ and error term $e$, then the [Expectation](notes/statistics/Expectation.md) for the error at a point $x$ is: $$Err(x) = E[(Y-\hat{f}(x))^2]$$

The error term can be decomposed further as: $$Err(x) = (E[\hat{f}(x)] - f(x))^2 + E[(\hat{f}(x) - E[\hat{f}(x)])^2] + \sigma_{e}^2$$

The first term is the squared bias. It is the expected prediction of the model evaluated at $x$ minus the true value $f(x)$, squared. 

The second term is the variance, which is the difference between the model evaluated at $x$ and the expected value of the model at $x$, squared.