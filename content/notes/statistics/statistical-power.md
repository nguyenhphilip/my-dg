---
title: statistical power
---

* definition: the likelihood of finding a positive a result (1 - type II error; 1 - probability of false negative), given that it exists ($1-B$)
* 
* or, via lakens-effect-size, the probability of correctly rejecting the null hypothesis.

---

### context for statistical power
via [Josh Starmer](https://www.youtube.com/watch?v=Rsc5znwR5FA&list=PLblh5JKOoLUK0FLuzwntyYI10UQFUhsY9&index=13)

- If we have two distributions of a particular variable (such as weight), and the difference between the means of the distributions is very large such that the [p-value](notes/statistics/p-value.md) is very small, while also assuming that there is no weight difference at all (the null hypothesis is assumed to be true), we will be correct most of the time in rejecting the null hypothesis; 
	- it would be unlikely that the data points would come from the same distribution (meaning there may be something worth paying attention to that is causing two distrubtions to emerge, such as some sort of dietary intervention)
- However, in some cases, even though the data you obtain may be truly from two different distributions, you may get a p-value that suggests we cannot reject the null hypothesis. (which would be a [Type II error](notes/statistics/Type-II-error.md))

---

### Power is determined by 3 factors:

1) the significance level ($\alpha$)
2) the magnitude of the population parameter
3) the accuracy and (precision and bias) of the model estimates

# Via 2021-abcd-meaningful-associations

>  Increasing power while maintaining a specified Type I error rate depends largely on obtaining more precise association parameter estimates from improved study designs, more efficient statistical methods, and, importantly, increasing sample size

On [effect size](notes/statistics/effect-size.md), [p-value](notes/statistics/p-value.md)s, and [ABCD Study](notes/ABCD/ABCD-Study.md):

> The ABCD Study has a large sample compared to typical neurodevelopmental studies, so much so that one might expect even very small associations to be statistically significant. In our experience, not all associations in the ABCD Study are guaranteed to have small p-values. For example, a recent study attempting to replicate the often-cited bilingual executive function advantage failed to find evidence for the advantage in the first data release (NDA 1.0) of the ABCD Study (n\=4524) ([Dick et al., 2019](https://www.sciencedirect.com/science/article/pii/S1053811921005395?via%3Dihub#bib0024)).

> Nevertheless, even very small associations are well-powered in the ABCD Study. [Figure 3](https://www.sciencedirect.com/science/article/pii/S1053811921005395?via%3Dihub#fig0003) displays power curves as a function of sample size for different values of absolute Pearson correlations |r|. The dashed line in [Figure 3](https://www.sciencedirect.com/science/article/pii/S1053811921005395?via%3Dihub#fig0003) indicates the full ABCD baseline sample size of n\=11880. ==As can be seen, Pearson correlations |r|=0.04 and above have power \>0.99 at α\=0.05.== Simply rejecting a null hypothesis without reporting on other aspects of the study design and statistical analyses (including discussion of plausible alternative explanatory models and threats to validity), as well as the observed magnitude of associations, is uninformative, perhaps particularly so in the context of very well-powered studies

---