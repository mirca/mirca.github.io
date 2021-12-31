---
layout: post
title: Markov Chains, Random Walks, and Martingales
date: 2021-11-05 05:50:00
description: a brief collection of notes
---

An extremely short note on these topics.

# Markov Chains


A sequence of random variables $$\{X_i\}_{i=0}^\infty$$ is said to form a Markov Chain if it satisfies the Markov property,
i.e.,
$$ \mathbb{P}(X_{n+1} = s_{j} \vert X_{n} = s_{i}, X_{n-1} = s_{i-1}, \cdots, X_0 = s_0)  = \mathbb{P}(X_{n+1} = s_{j} \vert X_{n} = s_{i}) \triangleq p_{ij}$$.
In words, future values of the chain only depend on the current state.

The numbers $$ s_0, s_1, \dots $$ denote the possible states of a Markov Chain. A Markov Chain with $$ m $$ states can be completely described
by an $$ m \times m $$ matrix $$[\mathbf{P}]_{ij} \triangleq p_{ij} $$ called **transition matrix** and the initial probabilities $$ \mathbb{P} (X_0) $$.

The initial probabilities is a column vector $$ \boldsymbol\pi_0 = (\mathbb{P} (X_0 = s_0), \mathbb{P} (X_0 = s_1), \cdots, \mathbb{P} (X_0 = s_{m-1}))^\top$$.

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

A stochastic process $$S_n = \sum_{i=0}^n X_i $$ is called a random walk if $$ \{X_i\}^\infty_{i=0}$$ are iid random variables.

If $$ X_i \in \{-1, 1\}$$ with probabilities $$p$$ and $$q$$, then $$S_n$$ is called a simple random walk. In addition, if $$ p = 0.5 $$, $$S_n$$ is called a symmetric random walk. In this case, we have
$$ \mathbb{E}[S_n] = 0$$ and $$\mathbb{V}(S_n) = n$$.


# Martingales

A stochastic sequence $$ \left\{X_n : n \geq 0\right\} $$ is a martingale, or a submartingale, if, for all $$ n \geq 0 $$:
   $$
   \begin{cases}
     \mathbb{E}[X_{n+1} | X_n = x_n, X_{n-1} = x_{n-1}, ..., X_0 = x_0] = x_n, & \quad \text{(martingale)}\\
     \mathbb{E}[X_{n+1} | X_n = x_n, X_{n-1} = x_{n-1}, ..., X_0 = x_0] \geq x_n, & \quad \text{(submartingale)}\\
   \end{cases}
   $$

A symmetric random walk is therefore a martingale:
     $$ S_{n+1} =
     \begin{cases}
       S_n + 1, & \quad \text{w/ prob 0.5},\\
       S_n - 1, & \quad \text{w/ prob 0.5}.
     \end{cases}
     $$

Therefore, $$ \mathbb{E}[S_{n+1} \vert S_n = s_n] = s_n$$.

## Stopping Rules

A random variable $$\tau$$ taking values in the set $${0, 1, ..., +\infty}$$ is a stopping rule
for an experiment with iid rvs $$X_0, X_1, ...$$ if the event $$ {\tau \leq n} $$ is independent
of $$ X_{n+1}, X_{n+2}, ...$$, and $$ \mathbb{P}(\tau < \infty) = 1$$, i.e.,
$$ \tau$$ is an rv that is independent of the future.

## Wald's Equality

Let $$ S_\tau = \sum_{i=0}^\tau X_i $$, then $$ \mathbb{E}[S_\tau] = \mathbb{E}[X_0]\mathbb{E}[\tau]$$. If also $$ \mathbb{E}[X^2_i] < \infty $$ then $$ \mathbb{E}\left[(S_\tau - \tau \mathbb{E}\left[X_0\right])^2\right] = \mathbb{V}(X_0)\mathbb{E}[\tau]. $$


# References

[1] https://www.stat.auckland.ac.nz/~fewster/325/

[2] A. N. Shiryaev. Probability. Second Edition, Springer, 1989. Translated by R. P. Boas.

