---
layout: post
title: Markov Chains and Martingales
date: 2021-10-17 05:50:00
description: a brief collection of notes
---

# Markov Chains


A sequence of random variables $$\{X_i\}_{i=0}^\infty$$ is said to form a Markov Chain if it satisfies the Markov property,
i.e.,
$$ \mathbb{P}(X_{n+1} = s_{i} \vert X_{n} = s_{j}, X_{n-1} = s_{j-1}, \cdots, X_0 = s_0)  = \mathbb{P}(X_{n+1} = s_{i} \vert X_{n} = s_{j}) \triangleq p_{ij}$$.
In words, future values of the chain only depend on the current state.

The numbers $$ s_0, s_1, \dots $$ denote the possible states of a Markov Chain. A Markov Chain with $$ m $$ states can be completely described
by an $$ m \times m $$ matrix $$[\mathbf{P}]_{ij} \triangleq p_{ij} $$ called **transition matrix** and the initial probabilities $$ \mathbb{P} (X_0) $$.

The initial probabilities is a vector $$ \boldsymbol\pi_0 = (\mathbb{P} (X_0) = s_0, \mathbb{P} (X_0) = s_1, \cdots, \mathbb{P} (X_0) = s_{m-1})$$.

The probability of a given path of length $$n$$, $$ (s_i, \dots, s_j, s_k) $$, can be computed as $$ \mathbb{P}(X_n = s_k, X_{n-1} = s_j, \cdots, X_1 = s_i \vert X_0 = s_0) $$.

A state $$ i $$ is called **absorbing** if $$ p_{ii} = 1 $$. A Markov Chain is called **absorbing** if it has at least one absorbing state
and for every non-absorbing state it is possible to go to an absorbing state.
