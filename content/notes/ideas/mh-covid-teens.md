---
title: Mental Health COVID-19 Teen Study in Iceland
tags: [mental health, adolescence, depression, covid, population, teens, wellbeing, substance use]
---

# Summary
## Background 
> Adolescence represents a crucial developmental period in shaping mental health trajectories. In this study, we investigated the effect of the COVID-19 pandemic on mental health and substance use during this sensitive developmental stage. 
## Methods 
> In this longitudinal, population-based study, surveys were administered to a nationwide sample of 13–18-yearolds in Iceland in October or February in 2016 and 2018, and in October, 2020 (during the COVID-19 pandemic). The surveys assessed depressive symptoms with the Symptom Checklist-90, mental wellbeing with the Short Warwick Edinburgh Mental Wellbeing Scale, and the frequency of cigarette smoking, e-cigarette use, and alcohol intoxication. Demographic data were collected, which included language spoken at home although not ethnicity data. We used [mixed models](notes/statistics/mixed-models.md) to study the effect of gender, age, and survey year on trends in mental health outcomes. 
## Findings 
> 59701 survey responses were included; response rates ranged from 63% to 86%. ==An increase in depressive symptoms (β 0·57, 95% CI 0·53 to 0·60) and worsened mental wellbeing (β –0·46, 95% CI –0·49 to –0·42)== were observed **across all age groups** during the pandemic compared with same-aged peers before COVID-19. ==These outcomes were significantly worse in adolescent girls compared with boys (β 4·16, 95% CI 4·05 to 4·28, and β –1·13, 95% CI –1·23 to –1·03, respectively).== Cigarette smoking (OR 2·61, 95% CI 2·59 to 2·66), e-cigarette use (OR 2·61, 95% CI 2·59 to 2·64), and alcohol intoxication (OR 2·59, 95% CI 2·56 to 2·64) declined among 15–18-year-olds during COVID-19, with no similar gender differences. 

Why girls though? Are they more vulnerable mentally at this stage of development?

## Interpretation 
> Our results suggest that COVID-19 has significantly impaired adolescent mental health. ==However, the decrease observed in substance use during the pandemic might be an unintended benefit of isolation, and might serve as a protective factor against future substance use disorders and dependence.== Population-level prevention efforts, especially for girls, are warranted.

Peer pressure is a powerful force.
---
# Statistical Analysis
Linear [mixed models](notes/statistics/mixed-models.md) were generated for continuous outcomes (depressive symptoms and mental wellbeing) and logistic mixed effects models for binary outcomes (cigarette smoking, e-cigarette use, and alcohol intoxication). In all the models, chronological age and time (2016, 2018, and 2020) were grandmean centred. Household status and language spoken within the home were added among the fixed effects as covariates. Healthcare district was added as a random intercept to account for nesting of students within the schools. We used models with differing fixed effects to address each research aim.

In the first model, we examined whether increases in the outcomes during COVID-19 exceeded documented upward trends in these mental health problems and substance use among adolescents. This was done by entering time as a fixed effect in predicting each outcome. 

- So comparing the effects of a before and after on all adolescents.

Second, we investigated the differential effect of COVID-19 by chronological age. We entered the main and interactive effects of time and age as fixed effects for each outcome. We explored differences in outcomes in 2016 and 2018 for each age group and then compared these rates to those in 2020.

- Now they break things up into subsets of time and age.

Third, gender differences were examined with a model in which the main effect and interaction between gender and time were entered as fixed effects. Following these analyses, the interactive effect of time and age on each outcome was examined separately for adolescent girls and boys.

To gauge the strength of the findings, standardised mean differences were created for each outcome by time using an effect size calculator and reported as Cohen’s d. For continuous outcomes, the means and SDs from 2020 were compared with these values in 2016 and 2018. To calculate Cohen’s d for binary outcomes, two-by-two frequency tables were created in which the event proportions (eg, endorsement of substance use) in 2020 were compared with the combined event proportions in 2016 and 2018. A positive value indicated an increase in the means or prevalence in 2020 compared with preCOVID-19, while a negative value indicated a decrease. Lastly, correlations were conducted to examine differences in the relationship between mental health outcomes and the substance abuse outcomes by time (appendix 2 p 15).

Applying Bonferroni corrections for multiple testing, the models were considered significant at a p value of less than 0·003. The mixed effect models were conducted using the `lme4` package and significant interactions were probed using the `emmeans` package with Tukey p value adjustments. Multiple imputation was used to address missing data (appendix 2 pp 1–3).23 All data analyses and visualisations were done with R version 3.6.0.