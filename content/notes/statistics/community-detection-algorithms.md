---
title: community detection algorithms
---

Some [network science](notes/statistics/network-science.md) methods

- [nice video on Modularity](https://www.youtube.com/watch?v=berZf9Nhr0E)
	- sum of observed links ($\frac{l_s}{L}$) minus expected links ($(\frac{d_s}{2L})^2$) for each partition (predetermined) of a network.
	- optimize for maximum modularity (i.e. repartition and repeat procedure of finding the ratio between observed and expected links)
- nice video on [Girvan-Newman](https://www.analyticsvidhya.com/blog/2020/04/community-detection-graphs-networks/)
	- find shortest path for each node to every other node
	- calculate edge weights
	- repeat for every node
	- sum up all the edge weights associated between every possible pair of nodes in the network
	- get rid of edges with highest weight (i.e. the edges that get traveled on the most)
- k-clique percolation: communities are composed of smaller cliques that share overlapping nodes
	- find maximal cliques
	- set threshold (k-1 where k = size of clique)
	- draw community lines
	- determine which edges are spurious and take them out