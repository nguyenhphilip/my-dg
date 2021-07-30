---
title: collider bias
---

Given a Directed Acyclic Graph T -> S <- N, S is a collider since conditioning on it would create a statistical (but not necessarily causal) association between T and N. What this means is that once you learn or know about S (you condition on S by including it in the model), then learning about T also provides information about N.

Including colliders in models can introduce unwanted statistical associations such as [selection distortion effect](notes/statistics/selection-distortion-effect.md)s.

An example:

>Happiness (H) and age (A) both cause marriage (M). Marriage is therefore a collider. Even though there is no causal association between happiness and age, if we condition on marriage— which means here, if we include it as a predictor in a regression—then it will induce a statis- tical association between age and happiness. And this can mislead us to think that happiness changes with age, when in fact it is constant.

Another closer to home:

> The fact that two arrows enter S means it is a collider. The core concept is easy to under- stand: When you condition on a collider, it creates statistical—but not necessarily causal— associations among its causes. In this case, once you learn that a proposal has been selected (S), then learning its trustworthiness (T) also provides information about its newsworthiness (N). Why? Because if, for example, a selected proposal has low trustworthiness, then it must have high newsworthiness. Otherwise it wouldn’t have been funded. The same works in re- verse: If a proposal has low newsworthiness, we’d infer that it must have higher than average trustworthiness. Otherwise it would not have been selected for funding...
> 
>This is the informational phenomenon that generates the negative association between T and N in the population of selected proposals. And it means ==we have to pay attention to processes that select our sample of observations and may distort associations among variables.== But the same phenomenon will also generate a misleading association inside a statistical model, when you include the collider as a predictor variable. If you are not careful, you can make an erroneous causal inference.