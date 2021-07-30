---
title: variance
---

#  Intuition
$$Var(X) = {\frac{1}{n-1}\sum_i {(x_i - \bar{x})^2}} $$ How varied data points are around their ==mean==. #flashcards
<!--SR:!2021-09-02,37,250--> 

# Formal definition

Like a random variable's [expectation](notes/statistics/Expectation.md), the variance is a random variables expected variability. This is the mean squared difference between a random variable and its mean: $$Var(X) = E[(X-E(X))^2]$$. 

---

The notebook view (Matloff) treats $(X-(EX))^2$ as a random variable, s.t. $W=(X-(EX))^2$. The variance of $X$ then is the expected value of $W$, the long-run average value, which is: $$Var(X)=E(g(X))=E(W)=\sum_{c{\in}B}(c)(p(B=c))$$ where $B=g(A)$, the support of $A$ transformed.

---

To get the [standard deviation](notes/statistics/standard-deviation.md), simply take the ==square root== of the variance. #flashcards
<!--SR:!2021-08-04,20,250--> 

# Properties
1) A nicer way to write the variance is $$Var(X)=E(X^2)-(E(X))^2$$ (derived using algebra the definition above)
2) $Var(cX)=c^{2}Var(X)$
3) $Var(X+c)=Var(X)$, in other words, shifting data over by a constant does not change the amount of variation in them.

# A visual aid for one variable

![Pasted image 20210622082205.png](/notes/images/20210622082205.png)

# For two variables
![Pasted image 20210622082310.png](/notes/images/20210622082310.png)

# See also: [covariance](notes/statistics/covariance.md)