---
title: network science
aliases: [networks, network]
---
- Networks are at the heart of complex systems
- Network science is the study of the structure and evolution of the networks underlying complex systems
- These networks are driven by a common set of fundamental laws and principles
- networks are comprised of nodes, which are linked to other nodes. 
- If two nodes are linked to each other, than they are neighbors. The number of links a node has is the degree of the node
- Network Statistics
	- **Average degree**: how connected is each node? Is each node similar to the next, or is there heterogeneity (i.e. some nodes more connected to than others)
	- **Average weighted degree (strength)**: Sum of the connection weights
	- **Centrality**: various measures relating to distance of running shortest path between every node 
		- Betweenness: 
			- how often a node appears in shortest paths in the network - high betweenness = some sort of hub, i.e. shortest path between you and a friend receiving a message is probably a text message
		- Closeness: average distance from given starting node to all other nodes in the network - short distance = high centrality
		- Eccentricity: the largest distance between two nodes in the network
	- **graph density**: fraction of edges that could exist that actually do exist
		- number of nodes (N choose 2) in undirected networks
	- **connected components**: whether network is broken into disconnected pieces