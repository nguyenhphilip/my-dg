---
title: collective dynamics of small-world networks
---

A key finding in [network science](notes/statistics/network-science.md), Watts and Strogatz discovered that small world networks are networks that have the property of having small average distance between nodes, while retaining high cliqueishness. They are somewhere between a fully random chaotic network, and a general one with no randomness (i.e. nodes are only connected via neighboring nodes).

This small-world effect (low average distance between nodes, high cliqueishness) emerges as a property of long-distance connections between a small number of nodes in a system (I know someone in California who works in law who knows someone connected to Obama). 

How they got this result was by randomly selecting a proportion of the edges to be rewired to another node. The consequence of this is that the distance between the newly connected node (A) and another node (B) in the system is decreased, which subsequently decreases the number of paths also available to the of the local neighborhoods now have a shorter path to (B).

This small-world phenomenon exists in many real world networks as shown by the IMDB example, power grids, and the neural network of C. Elegans.

