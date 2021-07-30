---
title: gradient descent
tags: [machine learning, statistics]
---

# definition
A method of optimizing parameters in a model so that we minimize the loss function. The key idea is to update our parameter values using the slope of the loss function. 

To do this we define a "step", which is a predefined learning rate times the slope/derivative/gradient of our loss function at a particular parameter value, and add it to that particular parameter value. This is akin to moving in the direction of the gradient until we reach the bottom of the loss function.

We can get the gradient of a loss function by finding its derivative with respect to the weights you're trying to optimize at a particular weight value (e.g. the intercept of a linear model or its beta values). The value of the gradient at that particular weight value will tell you in which direction to move along the loss function, and by how much (how much is scaled by the step size).  

# example

Say we have a real-valued function $\hat{y} = w(x + x^2)$ that is our predictor model and the actual values $y$. We can define our loss using the mean square error:

$$L(\hat{y},y) = \sum_i (\hat{y} - y)^2$$

If we plug $\hat{y}$ into the loss function, we get

$$L(y, x, w) = \sum_i (wx + wx^2 - y)^2 $$

If we take the derivative of the loss function with respect to the weights, we get 

$$\frac{dL}{dW} = \sum_i 2(x_i + x_i^2)(wx_i + wx_i^2 -y_i)$$

which is the gradient or slope along the loss function, given a weight value.

The gradient vector is a vector that stores the slope of each parameter of the loss function. We need to move in the opposite direction of the gradient in order to minimize the loss function.

# algorithm
1. Define loss function to measure performance
2. Find gradient (derivative with respect to multiple parameters) of the loss function
3. Initialize weights (usually random, gives GD a starting point)
4. plug weights into the gradient
5. update weights by adding the step size (-[gradient you just calculated] * [learning rate]) to each of the current weights
6. calculate new cost loss function using updated weights
7. repeat 4-6