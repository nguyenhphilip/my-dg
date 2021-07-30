---
title: The resilience paradox
---

# Abstract

> Decades of research have consistently shown that the most common outcome following potential trauma is a ==stable trajectory of healthy functioning==, or [resilience](notes/mental-health/resilience.md). However, attempts to predict resilience reveal a paradox: ==the correlates of resilient outcomes are generally so modest that it is not possible accurately identify who will be resilient to potential trauma and who not.== 

That it's not possible to identify who will be resilient vs those who aren't is both expected and surprising. It's surprising because we generally know that there are certain variables such as SES and ACE scores that are correlated with poorer outcomes in health and life. But it's expected because there may be much individual variability in terms of how we respond to said events, regardless of background. What are our responses shaped by in these cases? Genetics? Learned experience?

> Commonly used resilience questionnaires essentially ignore this paradox by including only a few presumably key predictors. However, these questionnaires show virtually no predictive utility. The opposite approach, capturing as many predictors as possible using multivariate modeling or machine learning, also fails to fully address the paradox. ==A closer examination of small effects reveals two primary reasons for these predictive failures: situational variability and the cost-benefit tradeoffs inherent in all behavioural responses.== Together, these considerations indicate that behavioural adjustment to traumatic stress is an ongoing process that necessitates flexible self-regulation. To that end, recent research and theory on flexible self-regulation in the context of resilience are discussed and next steps are considered.

# Introduction
Not long ago, resilient responses to trauma was assumed to be a rarity. It was exceptional in that researchers assumed those who were traumatized were very likely to develop problems. However, the more that people looked into it, the more ordinary it seemed to be (see Ordinary Magic: Resilience Processes in Development). Namely that trajectories of outcomes tended to be stable, positive, and healthy along psychological and physical domains.

> As research on trauma broadened, however, it became increasingly evident that genuine resilience in the form of a trajectory of ‘relatively stable, healthy levels of psychological and physical functioning’ was far more prevalent in the aftermath of potentially traumatic events (PTEs) than had previously been assumed (Bonanno, 2004, 2005).

These trajectories have multiple routes to them, and are therefore assumed to have multifaceted, interacting causes.

 > Because the resilience trajectory is so prevalent, encompassing a majority of people, it is also more heterogeneous than other types of outcome (Bonanno, 2005). In other words, there are likely multiple different routes the same end. Practically, this means that the predictors of resilient outcomes are undoubtedly multifaceted.

Some of these factors include (the evidence varies):
- personality variables
- supportive resources (friends, family, mentors, teachers)
- financial and educational assets
- coping and emotional regulation strategies
- minimal searching for meaning
- the experience and expression of positive emotions (optimism?)

Individually these factors are correlated with resilient outcomes, but they are not able to predict who will and won't be resilient. That's the paradox.

>   Together, these factors would seem to adequately explain resilient outcomes. Surprisingly, they do not. It turns out that the empirical relationships between individual predictors and resilient outcomes are uniformly modest. This creates a paradox: Even though we can identify correlates of resilient outcomes, we still cannot predict who will be resilient and who not with much accuracy (Bonanno, 2021). By extension, any attempt to build or enhance resilience that focuses on one or even a few of the known correlates will likely be inefficacious.

# The myth of the resilient type
It is common to think that there are people who are resilient vs. those who aren't as if it were an inherent trait. It's an idea that simplifies the prediction of outcomes to a set of questionnaires and easy if-else conditions. 

We see this in the numerous questionnaires that attempt to assess degree of resilience in individuals. But the questionnaires are far from uniform; they often each assess different traits and behaviors, implying that each is missing some piece of the puzzle. And looking at the data, mental health measures explained most of the variance in terms of resilient trajectories when conditioned on. Not looking good for the predictive utility of these questionnaires. (So what are they for? As a proxy for mental health symptomology? This makes me think of the book by Lucy X "What Mental Illness Is (and Isn't)". Lucy states that we should not make diagnoses on the sole basis of mental health questionnaires – there needs to be clinician input. But what is the clinician themselves looking for? Duration, signs of disruption in everyday life due to the illness, and perhaps intuition? Can clinicians themselves predict future outcomes?)

# Using [machine learning](notes/statistics/machine-learning.md)
 
> We recently used supervised and unsupervised learning to identify trajectories of resilience and PTSD symptoms and their predictors following admission to an emergency department for a PTE (Schultebraucks et al., 2020). Owing to the versatility of this approach, we were able to consider over ==70 baseline psychological and biological predictors.== **The resulting algorithm discriminated trajectories of PTSD symptoms with a high level of accuracy, both in the original sample and in an independent validation sample**. 
> 
> We then repeated this combination of supervised and unsupervised machine learning in another recent study to discriminate the trajectories based on **genetic predictors** (Schultebraucks, Choi, Galatzer-Levy, & Bonanno, 2021). Specifically, combinations of 21 unique polygenic scores related to various psychiatric disorders and health conditions. Overall discriminatory accuracy was again quite good.

There are some problems though, despite the high predictive accuracy.

1) In a practical setting one may not have all of these variables. 

> Nonetheless, as effective as these methods were, there are at least three reasons why machine learning falls short of fully addressing the resilience paradox. First, although classification accuracy was robust when based on a wide range of predictors, in practical application biological and genetic markers may not always be available. In this case, prognostic classification is greatly reduced. In our ED study, for example, when we considered only biological variables, discriminatory accuracy was reduced to a ‘fair’ level and when we considered only psychological vari- ables, discriminatory accuracy fell to a near chance level.

2) Overall classification may be robust but discriminatory accuracy tends to be less accurate for resilience.

>  In our study of polygenic predictors, for example, discriminatory accuracy was in the ‘excellent’ range for the chronic depression trajectory and still meaningful but only in the ‘fair’ range for the resilience trajectory. Based on these results, we concluded that ‘resilience is a more complex construct that is influenced by many risk and protective factors and it seems that the genetic component can explain only part of it.’

3) Machine learning is focused on prediction, not mechanism

> Third, and most important, even when a diverse set of biological and psychological measures might be available, machine learning algorithms are still largely limited to prediction. Although predictive algorithms can inform advances in theory by illustrating different and even unexpected predictor variables (Galatzer-Levy et al., 2018), their use to date has not yet illuminated the mechanism by which these predictors come together to foster resilient outcomes.

# Small Effects

Small effect sizes are abundant in psychology and  by themselves are not problematic, only in how they may be misinterpreted and misused. 

If one is to develop an intervention based on which predictors in a model are most relevant to resilience, the effect of that intervention may be small despite how much effort is put into creating that intervention (because of small effect sizes). 

Small effect sizes are also contributed to by natural cost-benefit tradeoffs inherent in virtually all behavior. In other words, a certain behavior may be beneficial in some situations but not others. 

# Flexible self-regulation
Flexible self-regulation: inherent personality characteristics + actions you can take
 
> The considerations above all point to the same basic conclusion: ==The predictors of resilient outcomes show only modest overall effects because they are not beneficial in every situation or at every point in time.== And, by extension, the mechanism that underlies resilience must involve some sort of adjudication process; some way of working out, moment by moment, what the best response might be and then engaging in that response.

Adaptability, or ability to learn, as a predictor of resilience trajectories?

>  But how would a person do this? How would a person determine, for example, when to seek support from others, when to use distraction, when to talk about the event, or try to make sense of it, or keep their spirits up, and so on? That process, and the mechanism that underlies resilience, I have proposed is flexible self-regulation (Bonanno, 2005, 2021).
>  
> There is a growing theoretical and empirical literature on flexible self regulation (see Bonanno et al., 2004; Bonanno & Burton, 2013; Cheng, Lau, & Chan, 2014; Kashdan & Rottenberg, 2010). Although there is not yet theoretical consensus, one point of agreement across this literature is that flexible self-regulation, like resilience, is not a simple, one-dimensional construct but, rather, involves multiple interacting components.

What are the components?

> Charles Burton and I (Bonanno & Burton, 2013) proposed that one primary component of flexible self- regulation involves three sequential steps, later dubbed the flexibility sequence (Bonanno, 2021). Briefly, the initial step in the sequence, **context sensitivity**, gets right down to **the task of working out the demands of a particular situation**. Here was ask ourselves, explicitly or implicitly, ==“What is happening? and ‘What do I need to do?’ This step is arguably the most critical in the sequence because it provides the context-specific information required to guide all subsequent responses== (Aldao, 2013).

Sounds like conditional probability. Given the situation, what is the best way to think about it? $P(\text{action}|{\text{some situation}})$

Secondly, what is possible for you to do?

> In the next step, repertoire, we chose a regulatory response that will best meet the specific challenges we are facing at that moment from the set of regulatory strategies we are able to use effectively. In other words, here the question shifts from “What do I need to do? to ‘What am I able to do?’

Last, updating... (SO Bayesian):

> This leads to the third and final step, feedback monitoring. Until recently, almost all research on self-regulation stopped at strategy selection. However, flexible responding requires ongoing monitoring. We do this essentially by asking ourselves, ‘Is it working?’ and then either continuing, ceasing, adjusting or replacing strategies as necessary.

Personality is important too:

> A related component of flexible self-regulation has to do more specifically with personality traits. When we originally developed the idea of the flexibility sequence, we focused primarily on coping and emotion regulation strategies. However, it quickly became apparent that the sequence is applicable to virtually all regulatory behaviour or resources, with one prominent exception: **Personality**. Several personality dimensions have been empirically associated with resilient outcomes, again with generally modest effects. But, in this case the effects are small, not because personality traits are not always effective, but rather because their influence on resilient outcomes is indirect (Carver & Connor-Smith, 2009).
> 
> Personality traits associated with resilience promote that engagement by forming a motivational foundation for flexible responding. Optimism, for example, fosters a willingness to work for the expected positive future (Carver & Scheier, 2014). Optimism also interacts with other traits, like coping self-efficacy (Benight & Harper, 2002), and challenge orientation (Tomaka, Blascovich, Kibler, & Ernst, 1997), to create an overall conviction, a flexibility mindset, that helps people engage with the task at hand (Bonanno, 2021).

