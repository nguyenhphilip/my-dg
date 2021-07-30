---
title: Chapter 8 Statistical Rethinking
creation date: 2021-06-10 10:20
---


To setup a categorical interaction (e.g. the association between GDP and ruggedness is conditional on the continent [Africa or not]), include index variables in the model so that we can create different slopes (betas) and intercepts conditioned on each category. 

For a continuous interaction, we need to make the slope(s) (beta(s)) themselves conditional on another variable; the slopes themselves need to be modeled in order to code the interaction.

For the example in the book, say we have a linear model $$\mu_i = \alpha + \lambda_{W,i} W_i + \beta_S S_i$$ where $$\lambda_{W,i} = \beta_W + \beta_{WS} S_i$$ is the model encoding the interaction between shade and water. It says that the association between bloom ==($\mu_i$)== and water level ==($W_i$)== depends on $\lambda_{W,i}$, which itself depends on the slope of water ==($\beta_W$)== and the interaction slope between water and shade ==($\beta_{WS} S_i$)==.

If you substitute the interaction term in, you get

$$\mu_i = \alpha + (\beta_W + \beta_{WS} S_i) W_i + \beta_S S_i = \alpha + \beta_W W_i + \beta_S S_i + \beta_{WS} S_i W_i$$

where the last term is the interaction term that conditions water and shade on each other.

