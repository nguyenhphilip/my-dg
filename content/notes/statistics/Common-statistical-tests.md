---
title: common statistical tests are linear models
aliases: [statistical tests]
---

[source](https://lindeloev.github.io/tests-as-linear/#1_the_simplicity_underlying_common_tests)

---

### [linear regression](notes/statistics/linear-regression.md) models and independent [t-test](notes/statistics/t-test.md)

**use**: when two means predict a response variable, i.e.

$$y_i = \beta_0 + \beta_1{x_i},$$. The associated hypothesis test assumes for the null that $$H_0: \beta_1 = 0$$

**ranked version (Mann-Whitney)**: same deal, except you rank/order $x$ and $y$:

$$rank(y_i) = \beta_0 + \beta_1{x_i},$$  $$H_0: \beta_1 = 0$$

> Essentially, a hypothesis test on the slope is asking whether or not the slope is 0.

If it is different from 0 by a significant margin, then it is deemed statistically significant. If 0 is included in the confidence interval surrounding the slope (or whatever you deem is the null hypothesis value), then the result is that we fail to reject the null.

> Student's [t-test](notes/statistics/t-test.md) assumes equal variance, Welch's does not

---

### using dummy coding or indicator variables to compare group differences

Usually we use an indicator variable to say which group a data point belongs to. An example would be 0 for boys, and 1 for girls.

![Pasted image 20210616101558](/notes/images/20210616101558.png)

Now, in a linear model where we are modeling, say, the difference between boys and girls on a particular assessment as $$y_i = \beta_0 + \beta_1{x_i},$$ then $\beta_0$ (the intercept) is the score for boys, and $\beta_1$ (the slope) is the difference in scores for girls. The difference is the slope $\beta_1$ because slope is $\frac{\triangle{y}}{\triangle{x}}$, and since $x$ is an indicator variable, then the change in $x$ is always 1, and therefore the slope is simply $\triangle{y}$. 

[Null Hypothesis Significance Testing](notes/statistics/Null-Hypothesis-Significance-Testing.md) in this case means assuming a distribution where the slope is 0, and calculating the [p-value](notes/statistics/p-value.md) of the actual slope assuming that the null effect is true.

---

### [ANOVA](notes/statistics/ANOVA.md) is a [linear regression](notes/statistics/linear-regression.md) model

model: one mean for each group predicts $y$.

$$y = \beta_0 + \beta_1x_1 + \beta_2x_2 + \beta_3x_3 + ...$$

$$H_0 : y = \beta_0$$

where $x_i$ are indicators ($x=0$ or $x=1$) where at most one $x_i=1$ while all others are $x_i=0$.