---
layout: ../../layouts/Site.astro
title: Rayleigh–van der Pol oscillator
description: Governing equations and the harmonic limiting case.
---

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= (\alpha-v^2-\beta\omega_0^2x^2)v-\omega_0^2x.
\end{aligned}
$$

Here $\alpha$ is the linear excitation coefficient, $\omega_0$ the undamped natural angular frequency, and $0\leq\beta\leq1$ the normalized position-damping coefficient.

The case $\beta=0$ is the Rayleigh oscillator. For $\beta=1$ and fixed $\alpha>0$, the invariant orbit

$$
v^2+\omega_0^2x^2=\alpha
$$

is harmonic, with angular frequency $\omega_0$ in model time, independent of $\alpha$. This frequency statement concerns the settled orbit, not parameter-change transients.

[Parameter ranges and references (PDF, p. 2)](/model-guide.pdf#page=2).
The [tube formulation (PDF, p. 9)](/model-guide.pdf#page=9) adds nonlinear pressure coupling to the same oscillator.
