#flashcards 
# about brain images

voxels are the pixels of brain images. They are 3-D, measured as cubic millimetres. 

temporal vs spatial resolution: structural images are captured using smaller voxels and look nicer as a result.

in functional imaging, because we want to take a picture of the brain at a faster frequency, we must sacrifice some spatial resolution for higher temporal resolution

# What makes fMRI analysis complicated?

1) Noise due to head motion and other artifacts (e.g. scanner and physiological variation)
2) variability across time both within and between individuals
3) large dimensionality of the data

# What is fMRI?
FMRI is a technique that uses magnetic resonance imaging to measure local brain activity by recording changes in ==local physiological changes==. The one commonly measured is the BOLD signal.
<!--SR:!2021-08-04,16,230--> 

#  the Bold signal
fMRI takes advantage of the fact that, following local neuronal activity, a surplus of blood is sent there to replenish the oxygen used by the activity of the cells. This is known as the ==hemodynamic-response==.
<!--SR:!2021-08-24,26,250-->

The **hemodynamic response** is the ideal, noiseless response to an infinitesimally brief stimulus. It's what we want to measure. What we get instead is the [BOLD signal](notes/neuro/BOLD-signal.md), a slow and blurred representation.

The [BOLD signal](notes/neuro/BOLD-signal.md) takes advantage of the fact that, following neuronal activity, oxygen level of the cells are low, and oxygen must be replenished. What we measure is the difference between the magnetic properties of the ratio of oxygenated and deoxygenated blood:

> The Bold signal  is based on the fact that when neuronal activity is increased in one part of the brain, there is also an increased amount of cerebral blood flow to that area which is the basis of hemodynamic response. This increase in blood flow produces an increase in the ratio of [oxygenated](https://en.wikipedia.org/wiki/Oxygenation_(medical) "Hemoglobin") [hemoglobin](https://en.wikipedia.org/wiki/Hemoglobin) relative to deoxygenated hemoglobin in that specific area. The difference in [magnetic properties](https://en.wikipedia.org/wiki/Magnetic_properties "Magnetic properties") of oxygenated and deoxygenated hemoglobin is what allows fMRI imaging to produce an effective map of which neurons are active and which are not.

## Important characteristics of the hemodynamic response
1) Peak height - the max amplitude of the signal
2) Time to peak
3) Width
4) Initial Dip
5) Postimulus undershoot

All of these features are highly variable from individual to individual

## Convolution
Goal: to produce an expected BOLD signal from a given neural input. Convolution is a mathematical operation that does this.

We want to convolve a stimulus onset time series, $f$, with an HRF (hemodynamic response function), $h$, so that we create a function that more closely represents the BOLD response. 

$$(h*f)(t) = \int h(\tau)f(t-\tau)d\tau$$

To do this we must estimate a good $f$, the HRF.

Commonly used for the HRF is a double-gamma HRF. The first gamma function models the shape of the initial stimulus response and the second gamma function models the ==postimulus undershoot== (including this in the model was found to improve the shape).
<!--SR:!2021-09-19,38,230-->

However, if we only use the double-gamma HRF, we are biasing results to suit this model without accounting for the wide variability between and even within individuals. So there are many other approaches that are used, but the [bias-variance tradeoff](notes/statistics/bias-variance-tradeoff.md) must be accounted for. 

Friston used the double-gamma HRF function plus its time derivatives. On the higher variance, lower bias end is using Finite Impulse Response models. In the middle are constrained basis sets which use knowledge of the features of the HR but still allow for flexibility.

A general rule of thumb: if you know that some factor, such as subject response time, affects the signal, it should be included in the model. We can model motion parameters too using motion regressors. However, if these regressors are correlated, we may run into issues of ([multicollinearity](notes/statistics/multicollinearity.md)). E.G. a task where it's expected for the subject to have some head motion in response to the stimulus. It may mask certain effects.

# Single Subject Analysis

>The goal of an fMRI data analysis is to analyze ==each== voxel’s time series to see whether the BOLD signal changes in response to some manipulation... The tool used to fit and detect this variation is the general linear model (GLM), where the BOLD time series plays the role of dependent variable, and the independent variables in the model reflect the expected BOLD stimulus time courses.
<!--SR:!2021-08-30,34,250-->

We want to build a GLM model that accurately models the BOLD signal.

Analyzing the time series of multiple voxels in the brain is referred to as mass univariate data analysis (we're analyzing time series on a voxel to voxel basis)

## Linear Time Invariance
 
An important characteristic of the BOLD signal is that the relationship between the neural response and the BOLD signal exhibits linear time invariant (LTI) properties. The meaning of linearity is that if a neural response is scaled by a factor of a, then the BOLD response is also scaled by ==a==. 
<!--SR:!2021-08-28,32,250--> 

![20210706151222.png](/notes/images/20210706151222.png)

 Linearity also implies ==additivity==, in that if you know what the response is for two separate events, if the events were to both occur close together in time, the resulting signal would be the sum of the independent signals. 
 
==Time invariant== means that if a stimulus is shifted by t seconds, the BOLD response will also be shifted by ==t==. 
<!--SR:!2021-08-25,29,250!2021-07-28,13,250!2021-08-29,33,250--> 

## Problems with Single Subject Analysis/Mass Univariate Techniques
What is one problem of (2) mass univariate analytical techniques?
?
1) Limited to group analysis (no individual inference)
2) Many statistical tests are run. (If you run 10,000 statistical tests and your $\alpha$ threshold is 0.05, then 500 of your tests are expected to be false positives)
<!--SR:2021-08-02,14,230-->

 ## Beta Weights
 What are beta weights?::Beta weights tell you how much the bold signal changes under a given experimental condition or stimulus (i.e. when $x_1=1$, the condition where subjects are viewing a sentence, a beta weight of $\beta_1=1.2$ means that the signal increases by 1.2 units.
<!--SR:2021-09-11,30,230-->
 
 ## BOLD Error
We can think about the approximated BOLD signal as our prediction plus some error: $$\text{signal(t)} = \text{prediction(t)} + \text{error(t)}$$ . This is equivalent to saying that the signal at time $t$ is the combination of explained variation by our model, plus some noise.

## The Goal
To find the beta weights that best approximate the signal of a voxel's time series by minimizing the error. Once we have the betas, we can compare the betas between conditions to determine if there is a significant difference. 

In group analysis, we are predicting the betas calculated at the individual level to determine if there are population level differences.