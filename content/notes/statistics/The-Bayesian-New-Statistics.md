---
title: The Bayes New Stats
---

# Abstract

In the practice of data analysis, there is a conceptual distinction between [Null Hypothesis Significance Testing](notes/statistics/Null-Hypothesis-Significance-Testing.md), on the one hand, and estimation with quantified uncertainty on the other. Among frequentists in psychology, a shift of emphasis from hypothesis testing to estimation has been dubbed “the New Statistics” (Cumming [2014](https://link.springer.com/article/10.3758/s13423-016-1221-4#ref-CR13 "Cumming, G. (2014). The new statistics why and how. Psychological Science, 25(1), 7–29.")). A second conceptual distinction is between frequentist methods and [Bayesian Statistics](notes/statistics/Bayesian-Statistics.md) methods. Our main goal in this article is to explain how Bayesian methods achieve the goals of the New Statistics better than frequentist methods. The article reviews frequentist and Bayesian approaches to hypothesis testing and to estimation with confidence or credible intervals. The article also describes Bayesian approaches to meta-analysis, randomized controlled trials, and power analysis.

# Two Conceptual Distinctions in Data Analysis

![Pasted image 20210525104625.png](/notes/images/20210525104625.png)

### Frequentist 

[Null Hypothesis Significance Testing](<[Null Hypothesis Significance Testing](notes/statistics/Null-Hypothesis-Significance-Testing.md)>): The constellation of methods founded on sampling distributions of imaginary data. By contrast [Bayesian analysis](notes/statistics/Bayesian-Statistics.md) is not based on imaginary distributions.

[t-test](notes/statistics/t-test.md) procedure under Null Hypothesis Significance Testing. We collect some data and compute a summary statistic called _t_ that summarizes the data. 

> Frequentists want to know how likely it would be to get a value of [t-statistic](notes/statistics/t-statistic.md) at least this extreme if the null hypothesis were true and if we were to collect data the same way we collect data in the actual research. When this probability is small enough, frequentists decide to reject the null hypothesis. Therefore, the probability is the rate of committing a false alarm (also known as a “[Type I error](notes/statistics/Type-I-error.md)”), and the goal of the decision threshold (usually set at 0.05) is to limit false alarms to that frequency.

On generating the [t-distribution](notes/statistics/t-distribution.md):

> We consider repeatedly ==randomly sampling from the null hypothesis==, every time generating a sample in the same way that the actual data were sampled, and ==for every simulated sample we compute a summary statistic like the one we computed for our actual sample==. The resulting distribution of randomly generated summary values is illustrated as the cloud in Fig. [2](https://link.springer.com/article/10.3758/s13423-016-1221-4#Fig2).

This is to say that we are calculating several [t-statistic](notes/statistics/t-statistic.md) values, each of them summarizing a different sub-sample centered on the mean of the null hyptoehsis, thus forming a distribution. If we set an alpha value of 0.05, then about 5% of the time we will have a [Type I error](notes/statistics/Type-I-error.md).

To get concrete:

> To compute a _p_ value for the data in Fig. [3](https://link.springer.com/article/10.3758/s13423-016-1221-4#Fig3), we first must declare the stopping and testing intentions. We make the conventional assumption that the ==stopping intention is to sample until _N_=18== and that this is the only test of the data we intend to make. Then we create a sampling distribution of the summary statistic _z_/_N_ (that is, we create the cloud of imaginary possibilities in Fig. [2](https://link.springer.com/article/10.3758/s13423-016-1221-4#Fig2)). From this sampling distribution, we determine the probability that simulated _z_/_N_ would be as or more extreme than the actual _z_/_N_.

That is, the [p-value](notes/statistics/p-value.md) is the probability that simulated z/N would be as or more extreme than the actual z/N is the proportion of simulated test statistics that are as or more extreme than the actual z/N. Mathematically, $$\text{p value} \equiv p(T(D_\text{simulated})\geq T(D_\text{actual}) | \mu, I) $$ where $\mu$ is the assumed parameter value under a null hypothesis and $I$ is some stopping intention (e.g. sample until N = 18)

 On the best estimate of a parameter under frequentist methods:

> In frequentist methods, the best estimate of a parameter in a descriptive mathematical model is usually obtained as the [maximum likelihood estimation](notes/statistics/maximum-likelihood-estimation.md), abbreviated as MLE. A special case of the MLE is the least-squares estimate (LSE), which may be familiar to readers who have previously studied analysis of variance (ANOVA) or linear regression. The MLE is the value of a parameter that makes the data most probable ==within the context of the descriptive mathematical model. ==For example, if we are describing dichotomous data with a simple model in which the probability of occurrence is denoted by the parameter _𝜃_, then the MLE of _𝜃_ is _z_/_N_ (property of Binomial distribution). As another example, if we are describing a set of metric numerical values (such as heights of people) by a mathematical normal distribution, then the MLE of the mean parameter _μ_ is the arithmetic mean of the sample (property of Normal distribution).

The [confidence intervals](notes/statistics/confidence-intervals.md) is a measure of how uncertain we are in our estimated parameter value

> The 95 % [confidence intervals](notes/statistics/confidence-intervals.md) of a parameter contains all the values of the parameter that would not be rejected by _p_<.05. NHST asks whether or not the null value of the parameter would be rejected. The confidence interval merely asks which other values of the parameter would not be rejected. Clearly the MLE of the parameter would not be rejected, but how far away from the MLE can we go before we reject the parameter value?

Confidence intervals have no distributional information:

> The limits of the confidence interval merely define the range of parameter values that would not be rejected by _p_<0.05. There is no direct sense by which parameter values in the middle of the confidence interval are more probable than values at the ends of the confidence interval.

### Bayesian

> We start with a prior degree of belief in each possibility, then we collect some data and re-allocate credibility across the possibilities, resulting in a posterior degree of belief in each possibility... In [Bayesian] data analysis, the possibilities are parameter values in a descriptive model of data. Just as Holmes started his investigation with a space of possible explanations for evidence, we start our analysis with a space of possible parameter values in a descriptive model of data.

Reallocation of credibility means adjusting the probability of possible parameter values away from what is inconsistent with the data, and conversely toward what _is_ consistent.

[Highest Density Interval](notes/statistics/Highest-Density-Interval.md)  summarize the uncertainty of our parameter estimate. It contains the parameter values of highest probability and that span the 95 % most probable values. The parameter values inside the 95 % HDI are the 95 % most credible values. Any parameter value inside the HDI has higher probability density (i.e., higher credibility) than any parameter value outside the HDI.

#### Rope Approach for assessing null values

1) Determine a Region of Practical Significance (e.g. 98.5 to 101.5 for IQ)
2) If the 95% [Highest Density Interval](notes/statistics/Highest-Density-Interval.md) doesn't fall within the ROPE bounds, then we reject the ROPE value (not the interval). If it does, then we accept the ROPE value for practical purposes. 

> if an HDI is used as part of a decision rule to assess null values, the decision rule should include a ROPE around the null value. A null value should not be rejected merely if it falls outside a 95 % HDI (unlike 95 % CI’s in NHST). Moreover, the decision rule based on HDI and ROPE intervalsintervalles is not called Bayesian “hypothesis testing,” which is a termun terme reserved for a different framework that we describe next.

#### Bayesian Hypothesis Testing

> In a Bayesian point-null hypothesis test, the null hypothesis is expressed as a prior distribution that puts all credibility in an infinitely dense spike at the null value of the parameter, with zero credibility on all other values of that parameter. In other words, the prior distribution for the null hypothesis says that only the null value is available. (The Bayesian framework allows other types of null hypotheses, but here we focus on point nulls for comparability to NHST.) Crucially, the null hypothesis is compared against an alternative prior distribution that spreads credibility over other values of the parameter. Unlike NHST, a Bayesian hypothesis test demands the specification of an alternative hypothesis, in the form of an alternative prior distribution on the parameter. Each hypothesis is indicated by a model-index parameter: _M_ \= 1 for the null hypothesis and _M_ \= 2 for the alternative hypothesis. Bayesian inference reallocates credibility across the two hypotheses by reallocating credibility across the values of the model-index parameter.

We can compare how much one hypothesis compares with another using the ratio of the [Bayes factor](notes/statistics/Bayes-factor.md), which provides an estimate of how the model index shifts from prior to posterior. $$BF_{null} \equiv \frac{p(M\!\,=\,null|D)}{p(M\!\,=\,alt|D)} /\frac{p(M\!\,=\,null)}{p(M\!\,=\,alt)}$$

> Importantly, the Bayes factor does not indicate the posterior probabilities or posterior odds; instead, the Bayes factor indicates the degree of change from the prior odds to the posterior odds of the null-model index. In other words, the posterior odds are the prior odds multiplied by the Bayes factor: $$\frac{p(M\!\,=\,null|D)}{p(M\!\,=\\,alt|D)} = BF_{null} \times \frac{p(M\!\,=\,null)}{p(M\!\,=\,alt)}$$

### Summarizing decision making with null values

> ...the [Bayes factor](notes/statistics/Bayes-factor.md) indicates the degree of shift from prior odds to posterior odds of a null-hypothesis prior and a particular alternative hypothesis prior. The BF is a continuous value that can be compared against a criterial threshold for making a decision (although we recommend considering the posterior probabilities instead of the BF). The posterior distribution shows which values of the parameter are more or less credible. The [Highest Density Interval](notes/statistics/Highest-Density-Interval.md) captures the most credible values, and can be compared against a critical ROPE around the null value for making decisions. The two Bayesian methods base the decision on the posterior probability of parameter values, with the BF focusing on the between-model index parameter and the HDI+ROPE focusing on the within-model parameter estimate. There is no necessary relation between making a decision via the BF and making a decision via the HDI+ROPE, though often the decisions will agree.
> 
> In the frequentist ... the _p_ value indicates the probability that ==a null hypothesis would generate imaginary data with a summary statistic as extreme as or more extreme than the actual data’s summary statistic, for imaginary data sampled and tested with the same intentions as the actual data.== The _p_ value is a continuous value that can be compared against a critical threshold for making a decision. The threshold represents the rate of false alarms we are willing to tolerate. ... The confidence interval indicates the range of hypothetical parameter values that have _p_ values that do not fall below the decision threshold. Therefore the null value is rejected if and only if it falls outside the CI.

Description of why we might be interested in estimating the mean, standard deviation, and effect size of, say, IQ, relative to the general population:

> We are interested in the ==mean== because we would like to know how different the central tendency of the smart-drug group is from the general population. We are interested in the ==standard deviation== because we would like to know how different the variability of the smart-drug group is from the general population on the scale of the data. Stressors such as performance drugs can increase the variance of a group because not everyone responds the same way to the stressor (e.g., Lazarus & Eriksen, [1952](https://link.springer.com/article/10.3758/s13423-016-1221-4#ref-CR44 "Lazarus, R.S., & Eriksen, C.W. (1952). Effects of failure stress upon skilled performance. Journal of Experimental Psychology, 43(2), 100–105. 
http://dx.doi.org/10.1037/h0056614
.")). Finally, we are interested in the [effect size](notes/statistics/effect-size.md) because it indicates the magnitudel'ampleur of the change in central tendency standardized relative to the variability in the group.

