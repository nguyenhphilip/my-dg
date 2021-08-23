---
title: Notes on Statistical Confounding
tags: [statistics, inference]
creation date: 2021-08-21 12:05
---

#flashcards 

*notes from a paper by Jacob Westfall on statistical confounding issues*

Scientists study and want to make claims (inference) about the relationship between things (e.g. academic performance and household income). To do this they construct measures (variables) that quantify the phenomenon they want to understand. If a measure is significantly related to the outcome (statistically speaking) they're interested in, then it is inferred there is some sort of non-trivial relationship between the outcome and the process that the measure represents.

However, life is usually more complicated than presented. Often an outcome is associated with multiple variables that can interact in unintuitive ways. For example academic performance is not solely dependent on how much money your parents make. Other things such as personal motivation, general intelligence, age, or peer influence might be important too. 

Scientists address this by statistically "controlling" for the variables they aren't interested in. After doing so what's left is the relationship between the outcome and the measure of interest, ideally (there may be many unmeasured, unobserved latent influences that we can't control for). If this relationship remains statistically significant, then the measure may have **incremental validity**. That is, the measure is actually a useful construct in understanding the relationship under question.

Claims of incremental validity are abundant in the biomedicial and social sciences, and often take the form of prediction arguments. That is, if a measurement X (e.g. income) is significantly related to an outcome Y (e.g. academic performance) even after confounding variables are controlled for (say, intelligence), then X is a useful predictor of Y. Trouble arises though if we aren't careful with the conclusions we draw using measures/representations of the thing/process we're actually interested in:

> Trouble arises, however, when researchers behave as if statistical conclusions obtained at the level of observed measures can be automatically generalized to the level of latent constructs [9,21]—a near-ubiquitous move, given that most scientists are not interested in prediction purely for prediction’s sake, and typically choose their measures precisely so as to stand in for latent constructs of interest. That is, researchers typically do not care to show that, say, school vouchers are associated with improved academic performance after controlling for a specific survey item asking about respondents’ income bracket; rather, the goal is to show that the vouchers may improve performance after accounting for the general construct of income (or, more generally, socioeconomic status).

Westfall uses a classic example to demonstrate the issue.

> Suppose we are given city statistics covering a four-month summer period, and observe that swimming pool deaths tend to increase on days when more ice cream is sold.

The confound in this situation is average daily temperature. If we control for average daily temperature using [multiple regression](notes/statistics/linear-regression.md), a staple of academic research, the relationship between ice cream sales and swimming pool deaths fades. (this is an example of a [fork (Y<-Z->X)](notes/statistics/linear-regression.md#Forks) where Z would be temperature, the variable confounding the relationship between ice cream sales and swimming pool deaths.)

Now imagine what would happen if we only had data on subjective heat ratings instead of temperature, a less precise, more error-prone measure. In Westfall's example, after controlling for subjective heat ratings in the model, the relationship between ice cream sales and swimming pool deaths remains significant. Should we then conclude that ice cream sales are useful predictive measures of swimming pool deaths, over and above daily temperature? No. This would be a spurious correlation. What's going on here? 

Subjective heat ratings are noisier measures of recorded temperature,

> so controlling for the former does not equate observations on the latter.

This is the situation we find ourselves in regarding tons of research. We take measurements of things, some of which are noisy proxies for what we actually care about. The result is something like the [replication crisis](replication-crisis.md). We may be swimming in an ocean of spurious results due to [false positives](notes/statistics/Type-I-error.md).

How to address this? Westfall offers two suggestions:

1) have perfect measurements (infeasible)
2) account for the effects of measurement unreliability in the model (Bayes to the rescue?)

# The Statistical View

Westfall asks us to consider a regression model of outcome $Y$ on two true scores (the actual latent variables we think are involved with $Y$) $T_j$ and an error term: $$Y = \beta_{T0} + \beta_{T1}{T_1} + \beta_{T2}{T_2} + \epsilon_{T}$$.

We usually do not observe the true scores, so we take measurements that represent the true scores, i.e. $$X_j = b_{j}T_j + \epsilon_j$$ such that the regression we actually observe is: $$Y = \beta_{X0} + \beta_{X1}X_1 + \beta_{X2}X_2 + \epsilon_X$$.

The core argument of incremental validity is that $T_1$ is a useful predictor of $Y$, even after controlling for $T_2$. The null hypothesis in this case is that there is no partial correlation between $T_1$ and $Y$. Since we don't directly observe $T_1$ and $T_2$, we reject the null hypothesis if there is a statistically significant correlation between $Y$ and $X_1$, after controlling for the confound $X_2$.

If our measure $X_2$ is free from measurement error (the dream), then the Type I error rate is 5% (alpha rate). It's also 5% when the correlation between the outcome $Y$ and predictor $T_1$ is 0, and when the correlation betweenthe predictor and confound is 0. That is, if the confound has no impact on the predictor and the outcome, then the false positive rate is what we would expect. 

However, the error rate increases if there is any measurement error on $X_2$, and if there is any indirect effect of $T_1$ on $Y$ via $T_2$. To summarize, the Type I error rate is a function of measurement error, sample size, and the presence of real, unobserved confounding effects.

How does the indirect effect size impact the Type I error rate?:: all else equal (fixed $X_2$ reliability and smaple size ($n$)), as the indirect effect size increases ($corr(Y,T_1)$ and $corr(T_1,T_2)$), the erorr rate increases. 

> The intuitive explanation for this [high error rates for combinations of various sample size and measurement error] is that measurement unreliability makes it easier for the regression model to confuse the direct and indirect paths (i.e., to apportion variance in the outcome incorrectly between the various predictors). **The larger the influence of the confounding covariate, the more variance can be misattributed to the predictor of interest, leading to an increase in Type I error.**

How does sample size impact Type I error rate?:: all else equal, *as sample size increases, error rates also increase*.

This runs against the wisdom that large sample sizes resolve many statistical issues:

> e.g. as n grows, power to reject the null increases, parameter estimates become more precise, etc.

The reason for this is that as sample size increases, we have more power to detect *any* effects, regardless of whether there are indirect effects influencing the true effect you care about.

> This remains true even when measurement unreliability causes the model to confuse a common effect of two or more predictors with a unique effect of one predictor—as n grows, the model more confidently concludes that there is a reliable association between the predictor of interest and the outcome.

How does the reliability of measures influence error rate?:: there is a non-monotonic relationship such that when reliability is at the extreme (either super noisy or very precise) the error rate remains close to 5%. The danger zone is in the middle (0.3 to 0.7ish), where many commonly used measures in the social sciences are. 

The reason for this is that if our measurements are highly unreliable, then the observed associations between them must be low, and therefore the null is likely to remain rejected because we can't detect any effect (low power). On the flip side, if we have highly reliable measurements, then the model avoids misattributing the effect of the covariate to the predictor we care about. 

> In the middle, however, there exists a territory where effects are large enough to afford detection, but reliability is too low to prevent misattribution, leading to particularly high Type 1 error rates.

This is the basic incremental validity argument. The situation Westfall outlines is ubiquitous in the social sciences. Variations of this argument (e.g. the argument for seperable constructs - i.e. that multiple predictors usefully explain the variance in an outcome, after controlling for confounders) fall prey to the same problems.

These problems are not reserved for frequentist statistics; it applies to [Bayesian analysis](notes/statistics/Bayesian-Statistics.md) too, if measurement error is unaccounted for (seems like you can account for this though in construction of the model??).

The rest of the paper goes on to talk about structural equation modeling as a statistical framework that can address these issues, namely by including measurement uncertainty in incremental validity claims. The discussion does a great job of wrapping things up.

*Read the whole paper [here](https://storage.googleapis.com/plos-corpus-prod/10.1371/journal.pone.0152719/1/pone.0152719.pdf?X-Goog-Algorithm=GOOG4-RSA-SHA256&X-Goog-Credential=wombat-sa%40plos-prod.iam.gserviceaccount.com%2F20210821%2Fauto%2Fstorage%2Fgoog4_request&X-Goog-Date=20210821T154905Z&X-Goog-Expires=86400&X-Goog-SignedHeaders=host&X-Goog-Signature=17c1ca865d39a1ab32766caee9dc9a47085f66d6051ad2a142abaf5953ffb9255a50538d7bf409c4d8b96ded4b1fb7b3367aaac763396f4cd8ce9da3169b12003aadef8fe960c256058ba589ce1d603266e8f67fcc1de3f6d1a059d5e44ee9af7a3fa812edbd557a6d432fb2a7a2e87130d99f61389e0833b949475be806576dd5923718f5902eb12afbbeff15d5ed40cdb1568cc8c072fcf3037c3933a8c7091a1a10022a03d70096fcabb15837b967268df8a9773a27fb795ae3176bbefe7a5f62662b29b9e84dc882301532c6a587aa213aa3dc593acb095d88819f2566277e1773a1174f3a770d2fd6b2f0a15387a02ff631b8ed6f153fdda9aaee5801b5).*