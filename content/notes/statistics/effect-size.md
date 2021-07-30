---
title: effect size
tags: [statistics, inference]
---

# definition
a measure that determines the ==practical significance== of scientific results

> An effect size is a standardized measurement that compares the size of some statistical effect to a reference quantity, such as the variability of the statistic.

## why they're useful
1) They are a standardized metric (scale free) that enables comparison (e.g. meta analysis) and communication of results
2) using effect sizes from prior studies is useful for planning new studies via [statistical power](notes/statistics/statistical-power.md) by providing an indication of what sample size is necessary to observe a statistically significant result

## two families: D and r

>  Effect sizes can be grouped in two families (Rosenthal, 1994): The d family (consisting of ==standardized mean differences==) and the r family (measures of ==strength of association==).

#### [Cohen's D](notes/statistics/cohens-d.md)

> Conceptually, the d family effect sizes are based on the difference between observations, divided by the standard deviation of these observations. 
> 
> The r family effect sizes describe the proportion of variance that is explained by group membership [e.g., a correlation ($r$) of 0.5 indicates 25% ($r^2$) of the variance is explained by the difference between groups].

The difference between two means of a sample $s$ is: 

$$d_s = \frac{\bar{X_1}-\bar{X_2}}{s}$$ 

where s is the pooled [standard deviation](notes/statistics/standard-deviation.md), weighed by their sample sizes

$$s= \sqrt{\frac{(n_1 - 1)s^2_1 + (n_2 - 1)s^2_2 }{n_1 +n_2 -2}}.$$

##### Interpreting [Cohen's D](notes/statistics/cohens-d.md)

>  A commonly used interpretation is to refer to effect sizes as small (d \= 0.2), medium (d \= 0.5), and large (d \= 0.8) based on benchmarks suggested by Cohen (1988). ==However, these values are arbitrary and should not be interpreted rigidly== (Thompson, 2007). Small effect sizes can have large consequences, such as an intervention that leads to a reliable reduction in suicide rates with an effect size of d \= 0.1\. The only reason to use these benchmarks is because findings are extremely novel, and cannot be compared to related findings in the literature (Cohen, 1988). ==Cohen’s d in between-subject designs can be readily interpreted as a percentage of the  standard deviation, such that a Cohen’s d of 0.5 means the difference equals half a standard deviation.== However, ==the best way to interpret Cohen’s d is to relate it to other effects in the literature,== and if possible, explain the practical consequences of the effect.

#### Pearson's R correlation coefficient
$$r_{xy} = \frac{\sum_{i}^N (x_i - \bar{x})(y_i - \bar{y})}{(n-1) s_x s_y}$$

the ratio of the covariance of two variables, normalized by the square root of their variances

---

### via ''2021 ABCD Meaningful Associations' paper

> Because [p-value](notes/statistics/p-value.md)s may be less informative in the context of very well-powered studies like [ABCD Study](notes/ABCD/ABCD-Study.md), effect sizes become important data points in determining the importance of the findings. Effect sizes quantify relationships between two or more variables, e.g., correlation coefficients, proportion of variance explained (R2), Cohen's d, relative risk, number needed to treat, and so forth ([Cohen, 1988](https://www.sciencedirect.com/science/article/pii/S1053811921005395?via%3Dihub#bib0020), [Rosenthal et al., 2000](https://www.sciencedirect.com/science/article/pii/S1053811921005395?via%3Dihub#bib0071)), with one variable often thought of as independent (exposure) and the other dependent (outcome) ([Rothman et al., 2008](https://www.sciencedirect.com/science/article/pii/S1053811921005395?via%3Dihub#bib0072)).

### Small effect sizes may still have meaningful relevance
> As much as the choice of which effect size statistic to report is driven by context, the interpretation of the practical utility of the observed effect size is even more so. While small p-values do not imply that reported effects are inherently substantive, “small” effect sizes might have practical or even clinical significance in the right context ([Rosenthal et al., 2000](https://www.sciencedirect.com/science/article/pii/S1053811921005395?via%3Dihub#bib0071)).
> ...
> As described in SM Section S.2, known problems of publication bias and incentives for researchers to find significant associations ([Button et al., 2013](https://www.sciencedirect.com/science/article/pii/S1053811921005395?via%3Dihub#bib0014), [Simonsohn et al., 2014](https://www.sciencedirect.com/science/article/pii/S1053811921005395?via%3Dihub#bib0078)) combined with the predominantly small sample sizes of most prior neurodevelopmental studies lead us to expect that true brain-behavior effect sizes are smaller than have been described in the past

---