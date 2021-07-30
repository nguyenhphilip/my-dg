---
title: Deep Learning
---

#flashcards 

# Uses

- Computer Vision
    - MNIST
        - Dataset of handwritten digits collected by the National Institute of Standards and Technology
        - Often used for demonstrating how computers can learn to 'see'
- [Natural Language Processing](notes/statistics/Natural-Language-Processing.md)


# How do machines learn?

Take in some input data, 'train' on it, and make a prediction

# Model Performance
1) **[sensitivity](notes/statistics/sensitivity.md)**::the proportion of *true positives* correctly identified over all  positive cases ($$\frac{TP}{TP+FP}$$), aka the **True Positive Rate** = $P[(\hat{Y}(X)=1|H_1\text{ is true}]$, aka ==[statistical power](notes/statistics/statistical-power.md)==. $1-TPR$ is the ==false positive rate==, also known as the ==[Type I error](notes/statistics/Type-I-error.md)==.
<!--SR:2021-08-12,16,250-->

<!--SR:!2021-07-18,3,250!2021-07-20,4,250!2021-07-19,3,250!2021-07-18,2,250-->

2) [specificity](notes/statistics/specificity.md)::the proportion of true negatives correctly identified over negative cases ($$\frac{TN}{TN+FN}$$)
<!--SR:2021-08-20,22,230-->

3) [accuracy](notes/statistics/accuracy.md)::the overall proportion of correct classifications ($$\frac{TP+TN}{TP+FP+TN+FN}$$)
<!--SR:2021-07-27,8,250-->

<!--SR:!2021-07-23,10,250-->

# Autoencoders
What are autoencoders?
?
They are a special kind of feedforward network with two components, the encoder and decoder.
<!--SR:2021-07-21,2,250--> 

==Encoders== learn to generate a latent representation of the data.
<!--SR:!2021-08-12,16,250--> 

==Decoders== learns to use these latent representations to reconstruct the input data as close as possible to the original.
<!--SR:!2021-08-05,9,230-->

Autoencoders are unsupervised learning techniques that extract meaningful features from the input based on the type of autoencoder you use (e.g. sparse autoencoder or denoising autoencoders). The type of autoencoder you use depends on the ==loss function== you specify.
<!--SR:!2021-08-14,18,230-->

Why use autoencoders?
?
They can be stacked in the hidden layers of a deep neural network to increase the level of abstraction of learned features. They can also be used for dimensionality reduction of the input space.
<!--SR:2021-07-30,3,210-->

> Autoencoders are an unsupervised learning technique in which we leverage neural networks for the task of **representation learning**. Specifically, we'll design a neural network architecture such that we _impose a bottleneck in the network which forces a **compressed** knowledge representation of the original input_. If the input features were each independent of one another, this compression and subsequent reconstruction would be a very difficult task. However, if some sort of structure exists in the data (ie. correlations between input features), this structure can be learned and consequently leveraged when forcing the input through the network's bottleneck.
> 
> (via [Jeremy Jordan](https://www.jeremyjordan.me/autoencoders/))

useful for neuroimaging and [fmri](notes/neuro/fmri.md), where voxels surely correlate with each other!

# Project Ideas
- [Deep Learning and Resting State fMRI to Classify Chronic Pain](https://www.frontiersin.org/articles/10.3389/fnins.2019.01313/full)
- [DeepFMRI: End-to-end deep learning for functional connectivity and classification of ADHD using fMRI](https://www.sciencedirect.com/science/article/abs/pii/S0165027019303632)
- brain and performance on cognitive tasks?
- brain and mental health?
- substance abuse trajectories?
- classify poetry to author?
- predicting future alcoholism? learning features based on Imagen data and using it to predict ABCD? 