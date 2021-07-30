---
title: ABCD pre-registration
---

# Pre-registration for the [ABCD Study](notes/ABCD/ABCD-Study.md)

In order to make hypothesis registration as easy as possible this platform supports the structured generation of hypothesis. This includes the definition of the hypothesis with variable selection and data transformations. Additionally, DEAP provides sample texts for the following sections that may be part of your hypothesis registration:

-   Sampling Plan
-   Design Plan
-   Analysis Plan
-   Analysis Scripts

We suggest to use the Open Science Foundation ([OSF](https://osf.io/)) framework to register hypothesis.

The DEAP portal supports a two step approach for hypothesis pre-registration. In a restricted mode (I) users are able to explore the data and see the marginal data distributions across all data domains. This is sufficient to identify suitable data transformations and shows the effects of data transformation and censoring for each variable. It also allows users to specify a subset of the participants for the tested hypothesis. The users can specify the hypothesis for example in the generalized additive mixed model module by defining the dependent and independent variables and all covariates of non interest. In the restricted mode the actual hypothesis test cannot be performed as it would result in the display of scatter plots and the premature calculation of effect sizes and significance values. Users are able to save and bookmark their hypotheses together with the subsetting for later analysis.

In the unrestricted mode (II) users have all the abilities of the restricted mode I as well as they are able to run their saved statistical analysis to test hypotheses.

Switch Mode

Restricted Mode

This mode helps to prevent premature hypothesis tests during the pre-registration phase. In restricted mode the _Analysis_ application does not allow to start an analysis. Hypothesis can still be saved and loaded.

# Overview

The Adolescent Brain Cognitive Development (ABCD) Study is a long-term study of cognitive and brain development in children across the United States. From 2016-2018, children between the ages of 9-11 have been invited to join the study from 21 sites around the nation, with the intent to enroll and follow approximately 11,500 healthy children longitudinally for 10 years into young adulthood.

Volkow, Nora D., et al. "The conception of the ABCD study: From substance use to a broad NIH collaboration." Developmental cognitive neuroscience (2017).

# Sampling Plan

An important motivation for the ABCD study is that its sample reﬂects the sociodemographic variation of the US population. With one important departure, the ABCD cohort recruitment emulates a multi-stage probability sample of eligible children: A nationally distributed set of 21 primary stage study sites, a probability sampling of schools within the deﬁned catchment areas for each site, and recruitment of eligible children in each sample school. The major departure from traditional probability sampling of U.S. children originates in how participating neuroimaging sites were chosen for the study. Although the 21 ABCD study sites are well-distributed nationally the selection of collaborating sites is not a true probability sample of primary sampling units but was constrained by the grant review selection process and the requirement that selected locations have both the research expertise and the neuroimaging equipment needed for the study protocol. As a consequence, neuroimaging research centers are more likely to be located in urban areas resulting in a potential under-representation of rural youth.

There is a substantial twin cohort in ABCD, consisting of monozygotic and dizygotic twin pairs, primarily collected at four of the 21 sites. There are also other sibling groups that will have been collected incidentally at all 21 sites.

Garavan, H., et al. "Recruiting the ABCD sample: design considerations and procedures." Developmental cognitive neuroscience (2018).

# Design Plan

The ABCD study is a prospective longitudinal study with yearly assessments. The November 2017 public data release on the NIMH Data Archive (NDA) consists of baseline data from 4,521 children from 20 sites. Data collection efforts for ABCD are organized into several data categories. Overviews of neuroimaging data, neuropsychological measures, biospecimens, substance use assessments, and culture and environment are given in the citations below.

Lisdahl, Krista M., et al. "Adolescent brain cognitive development (ABCD) study: Overview of substance use assessment methods." Developmental cognitive neuroscience (2018).

Uban, Kristina A., et al. "Biospecimens and the ABCD Study: Rationale, Methods of Collection, Measurement and Early Data." Developmental cognitive neuroscience (2018).

Casey, B. J., Cannonier, T., Conley, M. I., Cohen, A. O., Barch, D. M., Heitzeg, M. M., ... & Orr, C. A. (2018). The Adolescent Brain Cognitive Development (ABCD) Study: Imaging Acquisition across 21 Sites. Developmental cognitive neuroscience.

Luciana, M., et al. "Adolescent neurocognitive development and impacts of substance use: Overview of the adolescent brain cognitive development (ABCD) baseline neurocognition battery." Developmental cognitive neuroscience (2018).

Zucker, Robert A., et al. "Assessment of culture and environment in the adolescent brain and cognitive development study: Rationale, description of measures, and early data." Developmental cognitive neuroscience (2018).

# Analysis Plan

Analyses should, if possible, reflect the study design of ABCD. In particular, there are a substantial number of siblings (including twins) in the study, and hence subjects should be nested within families. Moreover, we recommend including site as a random or fixed effect covariate in regression analyses. In DEAP, the Multilevel Module incorporates family and site as random effects, and defaults to including as fixed effect covariates the demographic categories that were used as metrics in recruitment to balance with the American Childhood Survey (ACS): age, sex at birth, race/ethnicity, household income, marital status of guardian, highest household education.

Proper attention should be given to model assumptions. For example, normality of residuals or linearity of effects for regression models. If these assumptions are not met, consider data transformations or censoring of extreme outliers, or use of non-linear models.

We strongly recommend reporting and emphasizing effect sizes rather than just p-values, such as change in R-square from a base model (with covariates of no-interest) to a full model (covariates plus independent variables of interest). With the large ABCD sample, even very small effect sizes will tend to be significant. Effect sizes and classification accuracy are also best assessed in out-of-sample validation sets or via cross-validation. Tutorials on effect sizes for continuous outcomes, classification performance, and cross-validation are given in the references below:

Vacha-Haase, T., & Thompson, B. (2004). How to estimate and interpret various effect sizes. Journal of counseling psychology, 51(4), 473.

Sullivan, Gail M., and Richard Feinn. "Using effect size—or why the P value is not enough." Journal of graduate medical education 4.3 (2012): 279-282.

Hastie, T., Tibshirani, R. J., & Friedman, J. (2011). The Elements of Statistical Learning: Data Mining, Inference, and Prediction. (2nd ed.). Springer-Verlag.

Pereira, F., Mitchell, T., & Botvinick, M. (2009). Machine learning classifiers and fMRI: a tutorial overview. Neuroimage, 45(1), S199-S209.

Varoquaux, G., Raamana, P. R., Engemann, D. A., Hoyos-Idrobo, A., Schwartz, Y., & Thirion, B. (2017). Assessing and tuning brain decoders: Cross-validation, caveats, and guidelines. NeuroImage, 145, 166–179.

https://www.leeds.ac.uk/educol/documents/00002182.htm

https://towardsdatascience.com/metrics-to-evaluate-your-machine-learning-algorithm-f10ba6e38234

# Analysis Scripts

We strongly recommend making analysis scripts publicly available along with any published results. DEAP allows for downloading and sharing of R scripts used in analyses. Scripts can be included as Supplementary Materials in published results. We also recommend uploading scripts to a public source code repository such as ABCD's [https://github.com/ABCD-STUDY/](https://github.com/ABCD-STUDY/).

# Hypothesis Registration

In order to make hypothesis registration as easy as possible this platform supports the structured generation of hypothesis. This includes the definition of the hypothesis with variable selection and data transformations. Here, we provide sample texts for the following sections that may be part of your hypothesis registration.

# Hypothesis Pre-Registration Template

We suggest using the Open Science Foundation (OSF) framework to register hypotheses. Below we include an OSF registration template that borrows heavily from _"Pre-Registration in Social Psychology (van ‘t Veer & Giner-Sorolla, 2016)"._

For any required question that does not apply to your study put ‘N/A’ in the space for the relevant field and describe why it does not apply to your study.

In the fields below, we provide some descriptions relevant to the multilevel models in the context of generalized linear mixed-effects model (GLMM) regression analyses utilizing the ABCD sample.

Registered reports concept and participating journals: [https://cos.io/rr/](https://cos.io/rr/).

# A. Hypotheses

1.  Description of essential elements (required)
    1.  Describe the hypotheses in terms of directional relationships between your measured variables.  
        \[**We hypothesize that dependent variable DV is negatively/positively related to independent variable IV after controlling for random effects of site and family nested within site, and for fixed effects of demographics (age, sex at birth, marital status of household, household income, highest household education, and race/ethnicity)**\]
    2.  For interaction effects, describe the expected direction of the interactions.  
        \[**We hypothesize that the effect of IV on DV is conditional on levels of IV2 after centering each of IV and IV2. Specifically, we expect….**\]
2.  Recommended elements (optional)
    1.  A figure or table may be helpful to describe complex interactions; this facilitates correct specification of the ordering of all group means.
        1.  Up to 5 documents may be uploaded total for this pre-registration.
    2.  Rationales or theoretical frameworks for why a certain hypothesis is tested.
    3.  If multiple predictions can be made for the same IV-DV combination, describe what outcome would be predicted by which theory.

# B. Methods

1.  Description of essential elements (required)
    1.  Design  
        List, based on your hypotheses from section A: i. Independent variables with all their levels 1. Whether they are within- or between-participant 2. The relationship between them (e.g., orthogonal, nested within subjects). ii. List dependent variables, or variables in a correlational design iii. Variables acting as covariates or moderators \[**Random effects include site and family. Fixed-effect covariates include age, sex at birth, marital status of household, household income, highest household education, and race/ethnicity.**\]
    2.  Planned Sample for Analyses
        1.  Describe pre-selection rules for which subjects will be included in the analyses  
            \[**2017 NDA baseline ABCD data (release 1.1) consist of 4,521 subjects. Data were missing on X1 subjects. We excluded X2 subjects from the analyses because of….**\]
        2.  Justify planned sample size
            1.  If applicable, you can upload a file related to your power analysis here (e.g., power analyses from G\*Power, a script, a screenshot, etc.).  
                \[**Data were collected on 4,521 subjects in the 2017 NDA Baseline ABCD data (release 1.1). With this sample size we have power to detect an effect size of X1 with 80% power.**\]
    3.  Exclusion Criteria
        1.  Describe anticipated specific data exclusion criteria. For example:
            1.  Missing, erroneous, or overly consistent responses;
            2.  Failing check-tests or suspicion probes;
            3.  Demographic exclusions;
            4.  Data-based outlier criteria;
            5.  Method-based outlier criteria (e.g. too short or long response times)

# C. Analysis Plan

1.  Confirmatory Analyses (required)
    1.  Describe the analyses that will test the main predictions from the hypotheses section. Include for each main prediction individually:
        1.  The relevant variables and how they are calculated;
        2.  The statistical technique;  
            \[**Analyses conducted using generalized mixed-effects models. Subjects are nested within family (sibs) and families nested within site. Implemented using gamm4 function in R.**\]
        3.  Each variable’s role in the technique (e.g., IV, DV, moderator, mediator, covariate);
        4.  Rationale for each covariate used, if any;  
            \[**We controlled for site and family as random effects because these sources of variation are integral to the data sampling scheme of ABCD. We controlled for the six demographic categories as fixed effects because these are also integral to the design and recruitment of ABCD subjects.**\]
        5.  If using techniques other than null hypothesis testing (for example, Bayesian statistics), describe your criteria and inputs toward making an evidential conclusion, including prior values or distributions.
2.  Elements (required)
    1.  Specify contingencies and assumptions, such as:
        1.  Methods of correction for multiple tests.
        2.  The method of missing data handling (e.g., pairwise or listwise deletion, multiple imputation).
        3.  Anticipated data transformations.
        4.  Assumptions of analyses and plans for alternative/corrected analyses if each assumption is violated.  
            \[**If effects are non-linear, we will implement the appropriate transformation, or use quadratic or smooth effects.**\]
        5.  Optionally, upload any files here that are related to your analyses (e.g., syntaxes, scripts, etc.).
            1.  Up to 5 documents may be uploaded total for this pre-registration.  
                \[**Scripts may be downloaded from ABCD Github (https://github.com/ABCD-STUDY/) with this pre-registration**\]

# Final Questions

1.  Have you looked at the data? (required)
    1.  Please choose:
        1.  Yes
        2.  No
    2.  If Yes, describe in detail how you have examined the data and how this relates to the hypotheses and analyses proposed in this pre-registration.
2.  Any additional comments before you pre-register this project (optional)