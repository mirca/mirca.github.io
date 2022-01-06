---
layout: post
title: Dynamic Programming
date: 2021-11-05 05:50:00
description: a brief collection of notes
---

An extremely short note on dynamic programming.

# Dynamic Programming

A control theory approach of dynamic programming considers a decision making
scenario, where decisions are to be made in stages. The objective is to optimize
some reward or cost funciton.

Dynamic programming is a technique to tackle those problems. At each stage, it ranks
decisions based on the sum of the present cost and the expected future cost,
assuming an optimal decision making for subsequent stages.

The model we consider has two components: (1) a discrete dynamic time system,
and (2) a cost function that is additive over time.

The first component, *i.e.*, the discrete dynamic system, is modeled as

$$
x_{k+1} = f_{k}(x_{k}, u_{k}, w_{k}),
$$
where $$ x_k $$ is the state of the system,
$$ u_k $$ is the decision (control) variable, and
$$ w_k $$ is a random variable that models the noise assumptions,
$$ k = 0, 1, ..., n-1 $$.

The second component, the cost function, is modeled as

$$
J_{\pi}(x_0) = \mathbb{E}\left\{g_n(x_n) + \sum_{k=0}^{n-1} g_k(x_k, \pi_k(x_k), w_k)\right\},
$$

where $$ x_0 $$ is a given initial state of the system,
$$ \pi_k $$ is a policy to decide
the value of the control variable, *i.e.*,
$$ u_k = \pi_k (x_k) $$.

Our goal is to find an optimal policy $$ \pi^{\star} $$ such that the exepcted
cost is minimized

$$
\pi^\star = \underset{\pi ~ \in ~ \Pi}{\mathsf{arg}~\mathsf{min}} ~ J_{\pi}(x_0),
$$

where $$ \Pi $$ is the set of all admissible policies.

## Principle of Optimality

Let $$ \pi^\star = \left\{\pi^\star_0, \pi^\star_1, ..., \pi^\star_{n-1}\right\} $$
be an optimal policy for the basic problem, and assume that when using
$$ \pi^\star $$, a given state $$ x_i $$ occurs at time $$ i $$ with
positive probability.
Consider the subproblem whereby we are at $$ x_i $$ at time $$ i $$ and wish to
minimize the cost-to-go function from time $$ i $$ to time $$ n $$

$$
\mathbb{E}\left\{g(x_n) + \sum_{k=i}^{n-1}g_k(x_k, \pi_k(x_k), w_k)\right\}.
$$

Then the truncated policy $$ (\pi^\star_i, \pi^\star_{i+1}, ..., \pi^\star_{n-1}) $$
is optimal for this subproblem.

## References

D. Bertsekas. Dynamic Programming and Optimal Control. Massachusetts Institute of Technology, Volume 1, 3rd Ed., 2005.
