---
title: Deep Learning
---

#flashcards 

# Uses

- Computer Vision
	- Medical Imaging
	- Satellite geoimaging
- [Natural Language Processing](notes/statistics/Natural-Language-Processing.md)


# How do machines learn?

Key components
- Objective function
- learning rule
- architecture
- initialization
- environment (the data supplied during learning)

# Model Performance
1) **[sensitivity](notes/statistics/sensitivity.md)**::the proportion of *true positives* correctly identified over all  positive cases ($$\frac{TP}{TP+FP}$$), aka the **True Positive Rate** = $P[(\hat{Y}(X)=1|H_1\text{ is true}]$, aka ==[statistical power](notes/statistics/statistical-power.md)==. $1-TPR$ is the ==false positive rate==, also known as the ==[Type I error](notes/statistics/Type-I-error.md)==.
<!--SR:2021-08-12,16,250-->

<!--SR:!2021-07-18,3,250!2021-07-20,4,250!2021-07-19,3,250!2021-07-18,2,250-->

2) [specificity](notes/statistics/specificity.md)::the proportion of true negatives correctly identified over negative cases ($$\frac{TN}{TN+FN}$$)
<!--SR:2021-08-20,22,230-->

3) [accuracy](notes/statistics/accuracy.md)::the overall proportion of correct classifications ($$\frac{TP+TN}{TP+FP+TN+FN}$$)
<!--SR:2021-07-27,8,250-->

<!--SR:!2021-07-23,10,250-->

- [Cross-Entropy](Cross-Entropy.md)

# Models

- [Autoencoders](notes/statistics/Autoencoders.md)
- [Convolutional-NN](notes/statistics/Convolutional-NN.md)
- [[RNN]]
# Project Ideas
- [Deep Learning and Resting State fMRI to Classify Chronic Pain](https://www.frontiersin.org/articles/10.3389/fnins.2019.01313/full)
- [DeepFMRI: End-to-end deep learning for functional connectivity and classification of ADHD using fMRI](https://www.sciencedirect.com/science/article/abs/pii/S0165027019303632)
- brain and performance on cognitive tasks?
- brain and mental health?
- substance abuse trajectories?
- classify poetry to author?
- predicting future alcoholism? learning features based on Imagen data and using it to predict ABCD? 