---
title: Bayesian statistics
aliases: [Bayesian Inference, Bayesian analysis]
---

#### Allen Downey, on why it doesn't make sense to compare Frequentist statistical results with Bayesian results:

> You can’t compare results from Bayesian and Frequentist methods because the results are different kinds of things. Results from Frequentist methods are generally a ==point estimate==, a ==confidence interval==, and/or a ==p-value==. Each of those results is an answer to a different question: #flashcards
<!--SR:!2021-08-26,30,250!2021-09-10,45,270!2021-08-13,17,230--> 
> point estimate: If I have to pick a single value, which one minimizes a particular cost function under a particular set of constraints? For example, which one minimizes mean squared error while being unbiased?
> 
> [confidence intervals](notes/statistics/confidence-intervals.md): If my estimated parameters are correct and I run the experiment again, how much would the results vary due to random sampling?
> 
> [p-value](notes/statistics/p-value.md): If my estimated parameters are wrong and the actual effect size is zero, what is the probability I would see an effect as big as the one I saw? (effects are measured using various statistical tests, such as a [t-test](notes/statistics/t-test.md)).
> 
> In contrast, the result from Bayesian methods is a ==posterior distribution==, which is a different kind of thing from a point estimate, an interval, or a probability... 
> 
> ... And the whole point of Bayesian methods is that a posterior distribution is more useful than a point estimate or an interval because you can use it to guide decision-making under uncertainty.
<!--SR:!2021-08-06,20,250-->


