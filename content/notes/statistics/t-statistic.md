---
title: t statistic
aliases: [t value]
---

#flashcards 

$$t = \frac{\bar{X_1} - \bar{X_2}}{\sqrt{\frac{S_1^2}{n_1} + \frac{S_2^2}{n_2}}}$$ where the numerator is the difference in group means and the bottom is the square root of the [standard error](notes/statistics/standard-error.md).

Another way of looking at the t-statistic is the ratio of explained variation to unexplained variation. In fMRI, this might be the average signal of the voxel  under condition A minus the average signal of the voxel activated under condition B, divided by some measure of the noise.

$$t = \frac{\text{mean(A)}-\text{mean(B)}}{\text{noise}} = \frac{\text{explained variance}}{\text{explained variance}}$$