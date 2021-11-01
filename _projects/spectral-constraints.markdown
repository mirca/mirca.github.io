---
layout: page
title: Graph Learning with Spectral Constraints
description:
img: /assets/img/three-circles.png
importance: 1
---

In this project we propose optimization algorithms to learn graphs with certain spectral properties
such as $$k$$-components and bipartite.  The key idea in this project lies in the fact that the structure
of graphs can be controlled via the eigenvalues of their Laplacian and/or adjacency matrices. For instance,
the Laplacian matrix of $$k$$-component graphs contains exactly $$k$$ zero eigenvalues, whereas the adjacency matrix
of bipartite graphs contains symmetric eigenvalues around zero.

From a statistical point of view, we assume a Laplacian matrix model for the precision matrix of a
Gaussian Markov Random Field (aka weighted, undirected graphical model):

$$
\mathbf{x} \sim \mathcal{N}(\mathbf{0}, \mathbf{L}^\dagger),
$$

where $$\mathbf{x} \in \mathbb{R}^p$$ is a $$p$$-dimensional random vector representing the nodes of the graph
and $$\mathbf{L}$$ is its corresponding precision matrix which satisfies the Laplacian properties, i.e.,
$$\mathbf{L}\mathbf{1} = \mathbf{0}$$,
$$L_{ij} = L_{ji} \leq 0$$.

The maximum likelihood estimator for this model can then be formulated as follows

$$
  \begin{array}{cl}
    \underset{\mathbf{L} \succeq \mathbf{0}}{\mathsf{minimize}} & \mathsf{tr}\left(\mathbf{S}\mathbf{L}\right)
    - \log\mathrm{det}^*\left(\mathbf{L}\right),\\
    \mathsf{subject~to} & \mathsf{rank}(\mathbf{L}) = p-k,~ \mathbf{L}\mathbf{1} = \mathbf{0},~L_{ij} = L_{ji} \leq 0,
  \end{array}
$$

where $$ \mathrm{det}^*(\mathbf{L})$$ corresponds to the product of the positive eigenvalues of $$\mathbf{L}$$.


### Publications
The publications associated with this project are the following:

1. [Structured Graph Learning Via Laplacian Spectral Constraints](https://papers.nips.cc/paper/9339-structured-graph-learning-via-laplacian-spectral-constraints) at NeurIPS 2019
2. [A Unified Framework for Structured Graph Learning via Spectral Constraints](https://www.jmlr.org/papers/v21/19-276.html) at JMLR 2020
