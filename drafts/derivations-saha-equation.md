---
title: "Derivations: The Saha Equation"
date: 2021-04-06
mathjax: true
comments: true
categories: physics
tags: derivations plasmas cosmology
---

This post serves as the first in a series of posts deriving results that I enjoyed or found interesting during my undergraduate and masters degrees. These should all be standard results, and known to people who have studied them, but the world of physics is large, and not everyone will have studied every field. The purpose of this series is two-fold:

1. to try to present interesting results in a way that is self contained, for me to practice logical ordering and think about the pedagogy of how to teach these concepts. Hopefully if you didn't take a class in the subject of choice, you can learn something about it.
1. to force me to review concepts from my undergrad that I might not use super freuently and might be inclined to forget.

## TLDR: The Saha Equation
The Saha equation is the basic equation for the study of plasma physics. It answers the question: how hot do I need to get a gas of hydrogen atoms to obtain a certain degree of ionisation? It turns out that the temperature at which most of the gas becomes ionised is significantly below the binding energy of a hydrogen atom, and the ionisation ''switch on'' happens very quickly.

## Prerequisites
To follow this derivation, it is useful if you have encountered the following concepts before

* basics statistical mechanics (laws of thermodynamics, Stirling's approximation, partition functions, chemical potentials, free  energy)
* basic quantum mechanics (only really need the energy levels of hydrogen $E_n = -\frac{R}{n^2}$)

## The derivation
This derivation is based on two courses I took. One is S16 Plasma Physics taught by Justin Wark, and the other is Cosmology ... ADD LINKS LATER

### Law of mass action
To begin this derivation, a concept often omitted from thermodynamics/statistical mechanics courses must first be introduced: the **law of mass action**. This is a concept that is more familiar to chemists, but seldom taught in physics courses. In chemistry, most chemical reactions are written in the form
$$
\rm 2H_2 + O_2 \leftrightarrow 2H_2O
$$
meaning that in equilibrium (where we shall be working) we can write that 
$$
2\times(\text{number of H}_2) + (\text{number of O}_2) = 2\times ({\rm number \ of \ H_2O}).
$$
We can rewrite this for a general chemical reaction as
$$
\sum_i b_i B_i = 0
$$
where here the $B_i$ label each of our components in the chemical reaction, and the $b_i$ are their coefficients. In the hydrogen, oxygen, water example, we could for example choose the following:

| Chemical      | $B_i$ | $b_i$    |
| :---        |    :----  |   :--- |
| $\rm H_2O$     | $B_1$       | $2$   |
|  $\rm H_2$   | $B_2$      | $-2$    |
|  $\rm O_2$   | $B_3$      | $-1$   |


What does the condition for *chemical equilibrium* look like using this set of notation? If we consider that species $B_i$ has $N_i$ molecules, we know that this number $N_i$ will change until equilibrium is achieved. This change occurs by changing into other molecules in the system, and so the amount $N_i$ changes must be proportional to $b_i$ for each molecule in the system. That is
$$
\text{d}N_i = \lambda b_i
$$
where $\lambda$ is the same for each species. By the first law of thermodynamics we now that the internal energy, $U$ of a system is given by
$$
\text{d}U = T\text{d}S - p\text{d}V + \sum_i N \text{d}\mu
$$
and so the condition for chemical equilibrium is $\sum_i \mu_i \text{d}N_i = 0$. Substituting in our $\text{d}N_i = \lambda b_i$ the condition for chemical equilibrium becomes
$$
\sum_i \mu_i b_i = 0 = \sum_i \frac{\partial F}{\partial N_i}b_i
$$
where the last equality comes from the relation between the chemical potential and the (Helmhotz) free energy. It should be noted that this entire discussion assumes that our chemical reactions are happening at a constant temperature, for simlicities sake.






