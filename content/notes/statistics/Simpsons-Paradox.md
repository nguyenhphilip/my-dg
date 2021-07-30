---
title: Simpson's Paradox
---

#flashcards 

# Simpson's Paradox

When the effects of aggregated data overshadow or drive away what may otherwise be significant effects when you ==partition the data into groups==.
<!--SR:!2021-08-03,32,230--> 

# example: 
UC Berekley study looking at admission bias between men and women. Aggregated data show it was biased against women, while partitioned data revealed that it favored women slightly (6 out of 85 departments biased against men; 4 biased against women). 

The researchers concluded that women applied to more competitive departments with low rates of admission while men did the opposite. Looking at which departments people applied to is revealing in this case.

# Is it found in the wild?
According to Allen Downey, not very often:

> Based on my exploration (and a [similar search in a different dataset](https://arxiv.org/abs/1801.04385)), if you go looking for Simpson’s paradox in real data, you will find it. But it is rare: I tried almost 100,000 combinations, and found only about 100 examples. And a large majority of the examples I found were just statistical noise.
> 
> In the examples I found, Simpson’s paradox doesn’t reveal anything about the world that is useful to know. Mostly it creates confusion, especially for people who have not encountered it before. Sometimes it is satisfying to figure out what’s going on, but if you create confusion and then resolve it, I am not sure you have made net progress. If Simpson’s paradox is useful, it is as a warning that the question you are asking and the way you are looking at the data don’t quite go together.
