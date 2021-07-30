---
title: Monte Carlo methods
tags: [statistics, bayesian]
---

via Probabilistic ML:

> Algorithms that compute expectations by repeated random sampling, using samples $x_i$ ~ $p(x)$

## Examples:

$$\int f(x)p(x)dx \approx \frac{1}{S} \sum_{i=1}^S f(x_i)$$

$$\int p(x,y)dx \approx \sum_{i} p(y | x_i);$$

Caculating the ratio of a triangle's area within a square. Sample a point. If it's in the triangle, record that. Otherwise, it was part of the square.

## Why is this useful?

integrals are difficult

Monte Carlo works on every Integral

good for rough estimates

## Drawbacks?

computationally expensive

good for rough estimates, but not for precise calculations
	
	
