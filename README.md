# Page-rank

## Background

A personalized page rank is performed on a graph of the Gnutella server network. In this graph, each node represents a server, and each (directed) edge represents a connection between servers in Gnutella's peer-to-peer network. The graph is represented as a adjecent list. Each server (node) is identified by a unique number, and each line in the file gives the adjacency list for a single server. For example, this line:

```
91 243 1923 2194
```

gives the adjacency list for server ```91```. It indicates that there are edges from server ```91``` to servers ```243```, ```1923```, and ```2194```.

According to the [Stanford Network Analysis Project](https://snap.stanford.edu/data/p2p-Gnutella08.html), which collected these data, the graph includes **6301** servers and **20777** edges.


Personalized page rank is like [ordinary page rank](https://lintool.github.io/MapReduceAlgorithms/index.html) (section 5.3) except:

* One node in the graph is designated as the source node. Personalized page rank is performed with respect to that source node.
* Personalized page rank is initialized by assigning all probability mass to the source node, and none to the other nodes. In contrast, ordinary page rank is initialized by giving all nodes the same probability mass.
* Whenever personalized page rank makes a random jump, it jumps back to the source node. In contrast, ordinary page rank may jump to any node.
* In personalized page rank, all probability mass lost dangling nodes is put back into the source nodes. In ordinary page rank, lost mass is distributed evenly over all nodes.

## Tasks

The project contains 3 tasks:
1. Basic properties of the Gnutella graph, which includes:
  * How many nodes and edges are there in the graph? (This should confirm the numbers given above.)
  * How many nodes of each outdegree are there? That is, how many nodes have no outgoing edges, how many have one outgoing edge, how many have two outgoing edges, and so on?
  * How many nodes of each indegree are there?
2. Personalized page rank over the Gnutella graph for a specified number of iterations
3. Personalized page rank over the Gnutella graph with some specified termination condition
