---
title: z-score
---

How many standard deviations a particular data point is from the population mean:

$$z=\frac{(x-m)}{\sigma}$$ where $m$ is the population mean and $\sigma$ is the population standard deviation.

If you are looking at particular samples, use $$z_i=\frac{x_i-\bar{x}}{s}$$ where $\bar{x}$ is the sample mean and $s$ is the sample standard deviation.

Further normalization when you have multiple samples leads to

$$z=\frac{(x-m)}{\sigma/\sqrt{n}}$$

which is the standard error of the mean.