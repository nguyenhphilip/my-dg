---
title: post-treatment bias
---

The inclusion of a predictor that may confound treatment effects because it is the consequence of another predictor (e.g. using political interest instead of, say, socioeconomic status in a problem where the latter includes political party). This may bias an estimation of some intervention, as in the civic engagement treatment program below.

> It is much less routine to worry about mistaken inferences arising from including variables that are consequences of other variables.

Conditioning (including in the model - e.g. as a predictor in [multiple linear regression](notes/statistics/linear-regression.md)) on post-treatment variables eliminates the advantages of randomization because we are now comparing dissimilar groups.

> The problem is that by conditioning on a post-treatment variable we have unbalanced the treatment and control groups with respect to every other possible confounder. In this example, our attempt to control for one variable (political interest) introduced bias from imbalance in another variable (SES) that was not even included in the model and which the researchers may not have even measured.

On post-treatment variables masking treatment effects:

>  But including post-treatment variables can actually mask the treatment itself. This doesn’t mean you don’t want the model that includes both treatment and fungus. The fact that including fungus zeros the coefficient for treatment suggests that the treatment works for exactly the anticipated reasons. It tells us about mechanism. But a correct inference about the treatment still depends upon omitting the post-treatment variable.