---
title: modeling group fMRI data with mixed models
authors: [Jeanette Mumford]
---

# [mixed models](notes/statistics/mixed-models.md) Motivation
Often the effect of interest in research (say changes in political opinion after watching an advertisement, or the experimental condition of an fMRI study) is different depending on the group or level its a part of (e.g. across different universities, scanner, hospital, state, city).

**Fixed effects** are those that are sampled on all levels of an effect (i.e. you are accounting for all universities in your distribution when you calculate your effect.)

**Random effects** refer to the case when you sample from a subset of the groups or levels but want to apply your inferences to the entire population. (i.e. when you have data from three universities and want to make inferences about effects across all universities)

>  For our data example, the hypothesis of interest is the overall mean effect of opinion change in college students. Therefore, in both data collection scenarios ([in the scenario where subjects are randomly selected versus randomly selected across three universities]) we are interested in estimating and carrying out inference on the fixed mean effect, sometimes thought of as the ==intercept== of the model. 
>  
>  (Idea: Intercepts as population level estimates, akin to fixed mean effects)

If Random effects are present in the data, we want to model them to ensure more accurate, unbiased estimates.

> In the first case, all levels of university were randomly sampled, so university mean would be considered a fixed effect. Although it is a fixed effect, this is an example of when it would not be appropriate to include it in the model since we cannot include a fixed effect for each university while also estimating an overall mean, as it is only appropriate to include one or the other. 
> 
> In the second data collection scenario all universities were not sampled, only three randomly chosen universities. Since our goal is to apply our inferences for the overall mean to the entire population of all students from all universities, we must treat university as a random effect. If we don’t treat university as a random effect, ==there will not be separate within- and between-university variances, only a between-student variance (we would only have one intercept/effect/mean derived from one distribution with equal variance), which only describes the distribution of students in these three universities and so the inferences would only apply to these universities.==

Including random effects usually increases the amount of uncertainty (std. error) in fixed estimates because they account for within- and between-group/level variances.

> Under the incorrect assumption, there is only one distribution with one variance, the subject distribution. 
> 
> Under the correct assumption there are three university distributions and these universities are part of the distribution of all universities.

That is, if the data were sampled from a subset of the population without including all levels/grouping variables of interest, a [[Fixed effects|fixed effect]] model only says something about that particular subset, not the population. [[Random effects|random effect]] must be included in order to account for the within- and between-group variance and to make valid population level inferences.

# Regarding [[notes/neuro/fmri]] data
>  In the case of group [[notes/neuro/fmri]] data, the data for a single voxel consist of time series from multiple subjects, where each time series is a group of data specific to a particular subject. Each point in an fMRI time series is not randomly selected from a random subject, but an entire time series is selected from random subjects. Additionally, the distributions of fMRI time series between subjects can be very different, with some subjects activating more and/or having more variability in their signal than others. Since the goal of most fMRI studies is to apply the inferences beyond the study sample, a mixed effects model accounting for between- and within-subject variability, is the appropriate model. Just as shown with the student opinion change example, if a fixed effects model is used instead of a mixed effects model on group fMRI data, the estimated variances can be too small, leading to P-values that are too small and increasing the risk of false positives.

## The Two-Stage Summary Statistics Model
In the first stage each subject's data is analyzed individually. This produces the individual means and within-subject variances necessary for a group model. That is, each subject has their own distribution of the effect, per voxel. In the second stage we combine all individual means and within-subject variances necessary for the group model.

## Stage 1
We analyze each subject's data (voxel time series) to obtain subject specific signal size parameters and within-subject variance. 

The raw data is in the form of a time series of BOLD activation. We want to fit a model that well represents the time series over the course of our experiment (e.g. block design, event-related, etc) by typically assuming that the BOLD response is a linear combination of a baseline signal with other predictors (i.e. experimental condition)

Once the model is fit, we get an average effect size (the beta/parameter we are estimating) for that voxel. A different model is produced from every voxel, so we get a set of beta weights/effect sizes for every voxel, for every subject.

## Stage 2
>  In the case of fMRI data we combine the first level signal change parameters and within-subject variances to estimate between-subject variability and carry out inference on group signal change. The signal change parameter estimates from the Level 1 analysis comprise the ==dependent variable==; assume only a single parameter estimate per subject is used. 

That is, the dependent variable is the beta. 