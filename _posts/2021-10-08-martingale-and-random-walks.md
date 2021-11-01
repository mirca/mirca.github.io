---
layout: post
title: Markov Chains, Random Walks, and Martingales
date: 2021-10-17 05:50:00
description: a brief collection of notes
---

# Markov Chains


A sequence of random variables $$\{X_i\}_{i=0}^\infty$$ is said to form a Markov Chain if it satisfies the Markov property,
i.e.,
$$ \mathbb{P}(X_{n+1} = s_{j} \vert X_{n} = s_{i}, X_{n-1} = s_{i-1}, \cdots, X_0 = s_0)  = \mathbb{P}(X_{n+1} = s_{j} \vert X_{n} = s_{i}) \triangleq p_{ij}$$.
In words, future values of the chain only depend on the current state.

The numbers $$ s_0, s_1, \dots $$ denote the possible states of a Markov Chain. A Markov Chain with $$ m $$ states can be completely described
by an $$ m \times m $$ matrix $$[\mathbf{P}]_{ij} \triangleq p_{ij} $$ called **transition matrix** and the initial probabilities $$ \mathbb{P} (X_0) $$.

The initial probabilities is a column vector $$ \boldsymbol\pi_0 = (\mathbb{P} (X_0) = s_0, \mathbb{P} (X_0) = s_1, \cdots, \mathbb{P} (X_0) = s_{m-1})^\top$$.

The probability of a given path of length $$n$$, $$ (s_i, \dots, s_j, s_k) $$, can be computed as $$ \mathbb{P}(X_n = s_k, X_{n-1} = s_j, \cdots, X_1 = s_i \vert X_0 = s_0) $$.

A state $$ i $$ is called **absorbing** if $$ p_{ii} = 1 $$. A state is called **transient** if it is not absorbing.
A Markov Chain is called **absorbing** if it has at least one absorbing state and for every transient state it is
possible to go to an absorbing state.

## Stationary distribution

The probabilities to reach a given absorbing state $$ k $$, from any transient, are the unique solution to the equations:
     $$
     \begin{cases}
       \pi_k = 1, \\
       \pi_a = 0, & \quad \text{if}~ a\neq k~ \text{is an absorbing state}, \\
       \pi_i = \sum_{j=1}^m \pi_j p_{ij} & \quad \text{else}.
     \end{cases}
     $$

## Expected time to absorption

The expected times to absorption, $$ \mu_1, \mu_2, \cdots, \mu_m $$, are the unique solution to the equations:
     $$
     \begin{cases}
       \mu_k = 0, & \quad \text{if}~ k~ \text{is an absorbing state},\\
       \mu_i = 1 + \sum_{j=1}^m\mu_j p_{ij}, & \quad \text{else}.
     \end{cases}
     $$


# Random Walks

A stochastic process $$S_n = \sum_{i=1}^n X_i $$ is called a random walk if $$ \{X_i\}^\infty_{i=1}$$ are iid random variables


# References

[1] https://www.stat.auckland.ac.nz/~fewster/325/

