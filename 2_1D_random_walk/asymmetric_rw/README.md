# Asymmetric Random Walk: Drift–Diffusion as a Stochastic Model in Biophysics

## Overview

This repository presents a **one-dimensional asymmetric (biased) random walk** as a minimal stochastic model for **directed transport** in biophysical and soft-matter systems.

Unlike the symmetric random walk, where motion is purely diffusive, the asymmetric random walk incorporates **broken directional symmetry**, leading to the coexistence of **drift and diffusion**. The aim of this project is to demonstrate how deterministic-looking motion (drift) can emerge purely from probabilistic asymmetry, without invoking forces or potentials.

This model serves as a foundational stepping stone toward understanding **active processes**, **molecular motors**, **driven polymers**, and **nonequilibrium stochastic dynamics**.

---

## Physical Motivation

Many biological processes operate far from equilibrium. Examples include:

* Motor-driven transport along cytoskeletal filaments
* Directional translocation of polymers through pores
* Active transport of proteins and vesicles
* Drift induced by chemical or concentration gradients

At coarse-grained scales, these processes can often be modeled as **biased stochastic motion**, where randomness persists but directional symmetry is broken.

The asymmetric random walk captures this idea in its simplest form.

---

## Model Definition

### Asymmetric 1D Random Walk

**Assumptions**

* The particle moves along a one-dimensional line
* Time is discrete
* At each timestep, the particle moves:

  * one step to the right with probability ( p )
  * one step to the left with probability ( 1 - p )
* Successive steps are independent
* ( p \neq \frac{1}{2} ), introducing bias

Mathematically:
[
x_{n+1} = x_n + \eta_n, \quad
\eta_n \in {-1, +1}
]
with
[
P(\eta_n = +1) = p, \quad P(\eta_n = -1) = 1 - p
]

This model contains **no explicit forces**; directionality arises entirely from asymmetric probabilities.

---

## Quantities of Interest

### 1. Individual Trajectories

Single trajectories exhibit both random fluctuations and a systematic trend in the preferred direction. While noise remains strong at short times, long-time behavior becomes increasingly directional.

This illustrates a key nonequilibrium concept:

> deterministic motion can emerge from biased stochastic rules.

---

### 2. Mean Displacement (Drift)

The ensemble-averaged position grows linearly with time:
[
\langle x(t) \rangle = v t
]

where the drift velocity is:
[
v = (2p - 1)
]

Drift is therefore an **emergent quantity**, determined solely by the degree of asymmetry in step probabilities.

---

### 3. Mean Squared Displacement (MSD)

The mean squared displacement satisfies:
[
\langle [x(t) - \langle x(t) \rangle]^2 \rangle \propto t
]

This indicates that **diffusive spreading persists even in the presence of drift**.

The asymmetric random walk thus exhibits **drift–diffusion dynamics**, not pure diffusion.

---

## Emergence of Drift–Diffusion

Combining drift and fluctuations leads to:
[
\langle x^2(t) \rangle = (vt)^2 + 2Dt
]

Two qualitatively distinct contributions appear:

* A deterministic term from bias
* A stochastic term from randomness

This decomposition is central to modeling nonequilibrium transport in biophysics.

---

## Conceptual Lessons

The asymmetric random walk highlights several important modeling principles:

* Directional motion does not require deterministic forces
* Nonequilibrium behavior can arise from probabilistic asymmetry
* Drift and diffusion are not mutually exclusive
* Bias alters means but does not eliminate fluctuations

These ideas recur across biological transport phenomena.

---

## Relation to Biophysical Systems

The asymmetric random walk provides a minimal model for:

* Molecular motor stepping
* Directed polymer translocation
* Active particle motion
* Transport under chemical or mechanical gradients

It also forms the discrete-time precursor to:

* Langevin equations with constant force
* Active Brownian particle models
* Driven diffusive systems

---

## Repository Contents

* `biased_random_walk.ipynb`
  A Python notebook implementing the asymmetric 1D random walk, analyzing drift velocity, variance, and the coexistence of drift and diffusion.

The implementation emphasizes clarity, minimal assumptions, and explicit statistical averaging.

---

## Relation to the Symmetric Random Walk

This model generalizes the symmetric random walk by breaking directional symmetry. In the limit:
[
p \rightarrow \frac{1}{2}
]
the asymmetric model reduces smoothly to pure diffusion.

For conceptual clarity, the symmetric and asymmetric cases are treated as **distinct models** in separate repositories/notebooks.

---

## Suggested Extensions

Natural extensions include:

* Force-dependent bias ( p(F) )
* First-passage times under drift
* Biased motion under confinement
* Time-dependent or fluctuating bias
* Connection to continuous-time Langevin dynamics

---

## References and Further Reading

1. H. C. Berg, *Random Walks in Biology*
2. N. G. van Kampen, *Stochastic Processes in Physics and Chemistry*
3. C. W. Gardiner, *Stochastic Methods*
4. R. Zwanzig, *Nonequilibrium Statistical Mechanics*
5. J. Tailleur and M. Cates, *Statistical Mechanics of Interacting Run-and-Tumble Bacteria*

---

## Intended Audience

This repository is intended for students and researchers seeking a **physics-grounded understanding of directed stochastic transport**, particularly in biological and nonequilibrium systems that signals postdoc-level modeling skills.
