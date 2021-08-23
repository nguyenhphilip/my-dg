---
title: linear regression
aliases: [multiple linear regression, multiple regression]
tags: [statistics]
---

#flashcards 

# Multiple Linear Regression
>The defining question of multiple linear regression is: What is the value of knowing each predictor, once we already know the other predictors? Implicit in this question are: (1) a focus on the value of the predictors for description of the sample, instead of forecasting a future sample; and (2) the assumption that the value of each predictor does not depend upon the values of the other predictors.

## Confounders

### Why not just add all of your predictors to a model?

#### [multicollinearity](notes/statistics/multicollinearity.md) 
when two or more predictor variables that are correlated with each other, the results can be misleading. 
<!--SR:!2021-09-06,39,250--> 

> When two predictor variables are very strongly correlated, including both in a model may lead to confusion. The posterior distribution isn’t wrong, in such cases. It’s telling you that the question you asked cannot be answered with these data. And that’s a great thing for a model to say, that it cannot answer your question. 

#### [post treatment bias](notes/statistics/post-treatment-bias.md)
including post-treatment variables can 'mask' the effect of a predictor. (e.g. including fungus in a regression model that has treatment)

#### ==[collider bias](notes/statistics/collider-bias.md)== 
a spurious correlation between two variables that arises when you condition on a variable that both of them have directed arrows towards. e.g. A->C<-B
<!--SR:!2021-08-09,13,250-->

Generally these issues are examples of confounding. 

### Shutting the backdoor
To isolate the causal path between a predictor and an outcome we have to control for these confounding factors. How? By ==shutting the backdoor.==
<!--SR:!2021-08-11,15,250--> 

>The metaphor in play is that we don’t want any ==spurious correlation== sneaking in through a non-causal path, which is one that enters the back of the predictor... 
>
>Given a causal DAG, it is always possible to say which, if any, variables one must ==control for== in order to shut all the backdoor paths. It is also possible to say which variables one must not control for, in order to leave the path of interest open."
<!--SR:!2021-08-01,13,210!2021-08-10,14,250-->

### Methods for controlling potential confounders
#### Randomization

this removes the path of confounders to the predictor of interest. An example of modeling education (E) on wages (W) with possible confounders (U).

> Manipulation (such as randomization) removes the influence of U on Education. The unobserved variables do not influence Education when we ourselves ==determine/fix/condition== on Education. With the influence of U removed from Education, this then removes the path Education ← U → Wages. It blocks the second path (the first path is Education -> Wages). Once the path is blocked, there is only one way for information to go between Education and Wages, and then measuring the association between Education and Wages would yield a useful measure of causal influence. Manipulation removes the confounding, because ==it blocks== the other path (E<-U->W) between E and W. 
<!--SR:!2021-09-03,38,250!2021-09-01,36,250--> 

#### Conditioning 
If we can't randomize, we can shut the backdoor through conditioning.

> We can condition on U; this blocks the path from E <- U -> W, the alternative, non-causal path (ignore the direction, focus on the pathway). 

By conditioning on U, knowing E doesn't give us anymore info about W (assuming the existence of only this pathway).

> Suppose for example that U is the average wealth in a region. Regions with high wealth have better schools, resulting in more education E, as well as better paying jobs, resulting in higher wages W. If you don’t know the region a person lives in, learning the person’s education E will provide information about their wages W, because E and W are correlated across regions. But after you learn which region a person lives in, assuming there is no other path between E and W, then learning E tells you nothing about W. This is the sense in which condition on U blocks the path—it makes E and W independent, conditional on U.

> There are only four types of variable relations that combine to form all possible paths. So you really only need to understand four things and how information flows in each of them.

##### Forks
 X <- Z -> Y
 
The classic confounder. A variable Z generates a correlation between X and Y. Conditioning on Z, X and Y become independent (Y\_||\_ X|Z) -- we learn nothing about X if we know Y given Z. Conditioning on Z blocks the path from X and Y.

##### Pipes
X->Z->Y
Treatment X influences Z which influences Y. If we condition on Z, then we block (d-separate) the path between X and Y.

##### Colliders
X->Z<-Y
No association between X and Y unless you condition on Z. The path between X and Y opens when you condition on Z.

##### Descendent conditioning
conditioning on a descendent variable is like conditioning on its ascendent, but weaker. Say D -> Z, and X->Z<-Y. Conditioning on D is like conditioning on Z, but weaker. It partially opens the path between X and Y because Z is a collider.

##### Closing the door
> No matter how complicated a causal DAG appears, it is always built out of these four types of relations. And since you know how to open and close each, you (or your computer) can figure out which variables you need to control—or not—in order to shut the backdoor. Here’s the recipe:
> 
> 1) List all of the paths connecting X (the potential cause of interest) and Y (the outcome).
> 2) Classify each path by whether it is open or closed. **A path is open unless it contains a collider.**
> 3) Classify each path by whether it is a backdoor path. **A backdoor path has an arrow entering X.**
> 4) **If there are any backdoor paths that are also open, decide which variable(s) to condition on to close it.**

An example: ![Pasted image 20210623175414.png](/notes/images/20210623175414.png)

There are two indirect paths from X to Y: 

X<-U<-A->C->Y
X<-U->B<-C->Y

In the first case there is an open door, there are no colliders. So we can condition on either A or C to close this path.

In the second case B is a collider and is already closed. Opening it would not be something we want to do. It may induce spurious associations in the model.

## Interpreting Multiple Linear Regression
<!--SR:!2021-07-06,4,250-->

> So what does it mean to assume $\mu_{i} = \alpha + \beta_{A}{A_i} + \beta_{M}{M_i}$? 
>  
>  Using the marriage example, it means that the expected outcome for any state (the row/case/point of data) with marriage rate $M_i$ and median age at marriage $A_i$ is the sum of three independent terms. The first term is a constant, $\alpha$. Every State gets this. The second term is the product of the marriage rate, $M_i$, and the coefficient, $\beta_M$, that measures the ==association== between marriage rate and divorce rate. The third term is similar, but for the association with median age at marriage instead. #flashcards 
>  
> If you are like most people, this is still pretty mysterious. So it might help to read the + symbols as “or” and then say: A State’s divorce rate can be a function of its marriage rate OR its median age at marriage. The ==“or”== indicates independent associations, which may be purely statistical or rather causal.
<!--SR:!2021-07-23,13,250!2021-09-04,39,250--> 

## Assumptions for modeling (LINE):
1) L: linear relationship between Y and X 
2) I: The errors (residuals) are independent—there’s no connection between how far any two points lie from the regression line
3) N: responses are approximately normal for each level of X
4) E: variation in responses is equal for each level of X

![Pasted image 20210616094949.png](/notes/images/20210616094949.png)

---
See also [Common statistical tests are linear models](notes/statistics/Common-statistical-tests.md)

---

# references
- [Beyond Multiple Linear Regression](https://bookdown.org/roback/bookdown-BeyondMLR/ch-MLRreview.html)

- [Statistical Rethinking](notes/statistics/Statistical-Rethinking.md)