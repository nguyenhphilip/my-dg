---
title: mixed models
aliases: [mixed effect model, mixed effect models]
---

Models that involve using fixed AND random effects to estimate the effect of explanatory variables on an outcome variable.

---

But it depends on who you ask, according to Andrew Gelman:

1.  Fixed effects are constant across individuals, and random effects vary. For example, in a growth study, a model with random intercepts 𝑎𝑖 and fixed slope 𝑏 corresponds to parallel lines for different individuals 𝑖, or the model $y_{it} = a_i + bt$. Kreft and De Leeuw (1998) thus distinguish between fixed and random coefficients.
    
2.  Effects are fixed if they are interesting in themselves or random if there is interest in the underlying population. Searle, Casella, and McCulloch (1992, Section 1.4) explore this distinction in depth.
    
3.  “When a sample exhausts the population, the corresponding variable is fixed; when the sample is a small (i.e., negligible) part of the population the corresponding variable is random.” (Green and Tukey, 1960)
    
4.  “If an effect is assumed to be a realized value of a random variable, it is called a random effect.” (LaMotte, 1983)
    
5.  Fixed effects are estimated using least squares (or, more generally, maximum likelihood) and random effects are estimated with shrinkage (“linear unbiased prediction” in the terminology of Robinson, 1991). This definition is standard in the multilevel modeling literature (see, for example, Snijders and Bosker, 1999, Section 4.2) and in econometrics.

---

# Perhaps the best answer here:

There are good books on this such as [Gelman and Hill](http://www.stat.columbia.edu/~gelman/arm/). What follows is essentially a summary of their perspective.

First of all, you should not get too caught up in the terminology. In statistics, jargon should never be used as a substitute for a mathematical understanding of the models themselves. That is especially true for random and mixed effects models. "Mixed" just means the model has both fixed and random effects, so let's focus on the difference between fixed and random.

## Random versus Fixed Effects

Let's say you have a model with a categorical predictor, which divides your observations into groups according to the category values.* The model coefficients, or "effects", associated to that predictor can be either fixed or random. The most important practical difference between the two is this:

**_Random effects are estimated with partial pooling, while fixed effects are not._**

==Partial pooling== means that, ==if you have few data points in a group, the group's effect estimate will be based partially on the more abundant data from other groups==. This can be a nice compromise between estimating an effect by completely pooling all groups (e.g. calculate the mean for the entire sample), which masks group-level variation, and estimating an effect for all groups completely separately, which could give poor estimates for low-sample groups.

Random effects are simply the extension of the partial pooling technique as a general-purpose statistical model. This enables principled application of the idea to a wide variety of situations, including multiple predictors, mixed continuous and categorical variables, and complex correlation structures. (But with great power comes great responsibility: the complexity of modeling and inference is substantially increased, and can give rise to [subtle biases](https://stats.stackexchange.com/a/188559/11646) that require considerable sophistication to avoid.)

To motivate the random effects model, ask yourself: why would you partial pool? Why would you use estimates from more abundant groups to calculate the estimate we want for our smaller group? Probably because you think the little subgroups are part of some bigger group with a common mean effect (i.e. you think they're somehow associated with each other). ==The subgroup means can deviate a bit from the big group mean, but not by an arbitrary amount.== To formalize that idea, we posit that the ==deviations (the difference in means)== follow a distribution, typically Gaussian. That's where the "random" in random effects comes in: we're assuming the deviations of subgroups from a parent follow the distribution of a random variable. Once you have this idea in mind, the [mixed-effects model equations](https://stats.stackexchange.com/q/21760/7290) follow naturally.

Unfortunately, users of mixed effect models often have false preconceptions about what random effects are and how they differ from fixed effects. People hear "random" and think it means something very special about the system being modeled, like fixed effects have to be used when something is "fixed" while random effects have to be used when something is "randomly sampled". But there's nothing particularly random about assuming that model coefficients come from a distribution; it's just a soft constraint, similar to the ℓ2ℓ2 penalty applied to model coefficients in ridge regression. There are many situations when you might or might not want to use random effects, and they don't necessarily have much to do with the distinction between "fixed" and "random" quantities.

Unfortunately, the concept confusion caused by these terms has led to a [profusion of conflicting definitions](https://stats.stackexchange.com/a/4702/11646). Of the five definitions at this link, only #4 is completely correct in the general case, but it's also completely uninformative. You have to read entire papers and books (or failing that, this post) to understand what that definition implies in practical work.

## Example 

Let's look at a case where random effects modeling might be useful. Suppose you want to estimate average US household income by ZIP code. You have a large dataset containing observations of households' incomes and ZIP codes. Some ZIP codes are well represented in the dataset, but others have only a couple households.

For your initial model you would most likely take the mean income in each ZIP. 

This will work well when you have lots of data for a ZIP, but the estimates for your poorly sampled ZIPs will suffer from high variance ([more data reduces variance in our estimates generally]). You can mitigate this by using a ==shrinkage estimator ==(aka partial pooling), which will push extreme values towards the mean income across all ZIP codes.

But how much shrinkage/pooling should you do for a particular ZIP? Intuitively, it should depend on the following:

1.  How many observations you have in that ZIP
2.  How many observations you have overall
3.  The _individual-level_ mean and variance of household income across all ZIP codes
4.  The _group-level_ variance in mean household income across all ZIP codes

If you model ZIP code as a random effect, the mean income estimate in all ZIP codes will be subjected to a statistically well-founded shrinkage, taking into account all the factors above.

The best part is that random and mixed effects models automatically handle (4), the variability estimation, for all random effects in the model. This is harder than it seems at first glance: you could try the variance of the sample mean for each ZIP, but this will be biased high, because some of the variance between estimates for different ZIPs is just sampling variance. In a random effects model, the inference process accounts for sampling variance and shrinks the variance estimate accordingly.

Having accounted for (1)-(4), a random/mixed effects model is able to determine the appropriate shrinkage for low-sample groups. It can also handle much more complicated models with many different predictors.

## Relationship to Hierarchical Bayesian Modeling

If this sounds like hierarchical Bayesian modeling to you, you're right - it is a close relative but not identical. Mixed effects models are hierarchical in that they posit distributions for latent, unobserved parameters, but they are typically not fully Bayesian because the top-level hyperparameters will not be given proper priors. For example, in the above example we would most likely treat the mean income in a given ZIP as a sample from a normal distribution, with unknown mean and sigma to be estimated by the mixed-effects fitting process. However, a (non-Bayesian) mixed effects model will typically not have a prior on the unknown mean and sigma, so it's not fully Bayesian. That said, with a decent-sized data set, the standard mixed effects model and the fully Bayesian variant will often give very similar results.

*While many treatments of this topic focus on a narrow definition of "group", the concept is in fact very flexible: it is just a set of observations that share a common property. A group could be composed of multiple observations of a single person, or multiple people in a school, or multiple schools in a district, or multiple varieties of a single kind of fruit, or multiple kinds of vegetable from the same harvest, or multiple harvests of the same kind of vegetable, etc. Any categorical variable can be used as a grouping variable.

---