---
title: Early Diagnosis of Alzheimer's Disease with Deep Learning
authors: [Siqi Liu, Sidong Liu, Weidong Cai, Sonia Pujol, Ron Kikinis, Dagan Feng]
creation date: 2021-08-03 11:13
---

# Summary

- archiecture: stacked [Autoencoders](notes/statistics/Autoencoders.md) and softmax output layer
- ![](notes/images/Pasted%20image%2020210803112158.png)
- classify: [alzheimers](notes/neuro/alzheimers.md) disease and a possible precusor, Mild Cognitive Impairment
- dataset: ADNI database. 311 subjects (65 AD, 67 converters MCI, 102 non-converters MCI, 77 normal), gray matter volume (structural inputs)
- early diagnosis of AD is primarily associated with detection of Mild Cognitive Impairment
- Stacked Autoencoders can be seen as higher representations of the previous layer in that they encode the data into abstract features
- the proposed neural network does a better job of multiclassification than SVM