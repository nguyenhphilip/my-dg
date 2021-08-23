---
title: Autoencoders
creation date: 2021-08-02 13:33
---

What are autoencoders?

They are a special kind of feedforward network with two components, the encoder and decoder.

Encoders learn to generate a latent representation of the data. 

Decoders learns to use these latent representations to reconstruct the input data as close as possible to the original.

Autoencoders are unsupervised learning techniques that extract meaningful features from the input based on the type of autoencoder you use (e.g. sparse autoencoder or denoising autoencoders). The type of autoencoder you use depends on the loss function you specify.

Why use autoencoders?
They can be stacked in the hidden layers of a deep neural network to increase the level of abstraction of learned features. They can also be used for dimensionality reduction of the input space.

> Autoencoders are an unsupervised learning technique in which we leverage neural networks for the task of **representation learning**. Specifically, we'll design a neural network architecture such that we _impose a bottleneck in the network which forces a **compressed** knowledge representation of the original input_. If the input features were each independent of one another, this compression and subsequent reconstruction would be a very difficult task. However, if some sort of structure exists in the data (ie. correlations between input features), this structure can be learned and consequently leveraged when forcing the input through the network's bottleneck.
> 
> (via [Jeremy Jordan](https://www.jeremyjordan.me/autoencoders/))

useful for neuroimaging and [fmri](notes/neuro/fmri.md), where voxels surely correlate with each other!