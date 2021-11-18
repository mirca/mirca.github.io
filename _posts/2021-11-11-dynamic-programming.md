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
decisions based on the sum of the present cost and the expected future cost, assuming
an optimal decision making for subsequent stages.

The model we consider has two components: (1) a discrete dynamic time system,
and (2) a cost function that is additive over time.

Consider the following optimization program

$$
  \begin{array}{cl}
    \underset{\boldsymbol \pi }{\mathsf{minimize}} & 
  \end{array}
$$


## References

D. Bertsekas. Dynamic Programming and Optimal Control. Massachusetts Institute of Technology, Volume 1, 3rd Ed., 2005.
