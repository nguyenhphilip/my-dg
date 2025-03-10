---
title: Logistic Regression
---

# Summary

- A statistical model that models the relationship between a binary dependent variable and a set of explanatory variables.

- What the model finds is the probability that an observation belongs to one class or the other, given a set of independent variables. 

- That probability, say $p$, is being estimated by the coefficients in the estimated regression function $$\hat{p}=\frac{e^{z}}{1+e^{z}}=\sigma(z)$$ where $z$ is the linear combination of independent variables: $$z = \beta_0 + {\beta_1}{x_1} + {\beta_2}{x_2} + ... + {\beta_n}{x_n}$$ and $\sigma$ is the sigmoid function.
- We can convert the probability $\hat{p}$ to log-odds units by algebraic manipulation s.t. $$logit(p)=z$$ or in odds $$\frac{p}{1-p} = e^z$$
## Important Concepts

- [Odds](notes/statistics/Odds.md): necessary to interpret the output from logistic regression.

- [linear regression](notes/statistics/linear-regression.md): the backbone of many analysis, a good frame of reference.

- **Logit function**: links a linear combination of independent variables to the logarithm of the odds (log-odds) of a binary dependent variable. 

## The Role of odds and log odds

- In logistic regression we are modeling the log-odds of a dependent variable and independent variable, [which in the model represents how the log-odds of the dependent variable change with a one unit increase in the independent variable](https://www.youtube.com/watch?v=ckkiG-SDuV8), holding all other variables constant.
	
	- on odds: the log-odds is simply the logit function applied to the odds of a binary variable. For example in the relationship between body weight and sleep apnea (person has it or doesn't), we might say that every extra pound increases the odds of having sleep apnea by the odds ratio between the variables for sleep apnea and body weight.
		
		- Concretely, for every pound of weight added, the odds of developing sleep apnea might be 1.07 if the odds ratio is 1.07.
			
	- note that it's important to separate probability and odds. Odds are relative, whereas probabilities are absolute. The odds of a low weight person developing sleep apnea is the same as the odds of a high weight person, but the probability of the low weight person may be much lower than that of the higher person.
		
		- A funny but illustrative example to solidify this point: the odds of getting hit by lighting may be much higher than getting struck by a meteor, but the absolute probabilities of either happening are (thankfully-hopefully) super low.

## Linking Binary Variables to IVs

- What we want is to estimate is $p$, the probability that an observation belongs in one class or the other, as a linear combination of indepdendent variables.

- We can do this by first assuming that our dependent variable is drawn from or generated by a [Bernoulli Distribution](notes/statistics/binomial-distribution.md) (a reasonable assumption, given that our outcome variable is binary). 

- We need a way to link the $p$ back to the independent variables. That's where the logit function comes in.

## The LOGIT ("Low-jit") Function

- We need the LOGIT function in order to link, or map, our independent variables into the domain [0,1] so that our estimate of $p$ is a valid probability.

- The LOGIT function is the log of the odds: $$ln(odds) = ln(\frac{p}{1-p}) = logit(p) = ln(p)-ln(1-p)$$
	- Brief reminder that $\log_e(x)=ln(x)$
	- Also that $ln(p)-ln(1-p) = ln(\frac{p}{1-p})$ by logarithm properties

- Ultimately what we model is $$logit(p) = \beta_0 + {\beta_1}{x_1} + {\beta_2}{x_2} + {\beta_n}{x_n}$$ where we estimate $logit(p)$ via the coefficients.

- But $logit(p)$ is in logit, or log-odds, space. We want $p$! To do that we can exponentiate both sides of the equation, which eventually gives us the estimated regression equation: $$\hat{p}=\frac{e^{z}}{1+e^{z}}$$ where $z$ is the linear combination of our independent variables.

## Inference

- In the output of logistic regression, we get the odds ratio, which is the increase in odds given a 1 unit increase in an independent variable, holding all others constant.

- Remember that the odds ratio is just a ratio of the odds. In the [credit score example](https://www.youtube.com/watch?v=gcr3qy0SdGQ), the author calculates the probability at a credit score of 720 and at 721. The odds ratio is then $$\frac{odds(721)}{odds(720)}$$.

- To calculate the odds ratio for an increase in say, a 20 unit increase in the independent variable, a similar method is used. Just calculate the odds ratio of $$\frac{odds(740)}{odds(720)}$$