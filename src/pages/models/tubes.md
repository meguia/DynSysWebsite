---
layout: ../../layouts/Site.astro
title: Tubes
description: Neutral-delay and modal resonators with nonlinear oscillator and valve coupling.
---

Pressure $p$ and injected flow $U$ are normalized to unit characteristic acoustic impedance. Each exciter below couples to either resonator formulation. Reflection magnitude is $0<r<1$ and round-trip delay is $\tau>0$.

<h2 id="neutral">Neutral DDE resonator</h2>

$$
\begin{aligned}
\dot A(t) &= U(t)-r\dot A(t-\tau),\\
p(t) &= U(t)-2r\dot A(t-\tau).
\end{aligned}
$$

$A$ is the outgoing-wave integral. Delayed derivatives are evaluated from the solver history. The current $\tau(t)$ is used during live delay changes.

<h2 id="modal">Modal ODE approximation</h2>

$$
\begin{aligned}
\dot q_n &= \frac{\log r}{\tau}q_n-\frac{(2n-1)\pi}{\tau}w_n+\frac{4}{\tau}U,\\
\dot w_n &= \frac{(2n-1)\pi}{\tau}q_n+\frac{\log r}{\tau}w_n,\\
p &= \sum_{n=1}^{N}q_n,\qquad n=1,\ldots,N.
\end{aligned}
$$

The modal formulation is a finite-bandwidth approximation. Changing $\tau$ updates the modal coefficients while retaining their states.

<h2 id="rayleigh">Rayleigh–van der Pol with nonlinear coupling</h2>

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= (\alpha-v^2-\beta\omega_0^2x^2)v-\omega_0^2x-\kappa(1+\eta x)p,\\
U &= (1+\eta x)v.
\end{aligned}
$$

$\eta=0$ gives linear coupling. The [uncoupled oscillator](../oscillators/#rayleigh) is recovered at $\kappa=0$; $\beta=1$ does not guarantee harmonic motion when pressure feedback is present. The live delay range is $0.5\leq\tau\leq3$.

<h2 id="squared-conductance">Squared-conductance valve</h2>

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= \omega_0^2(p-\gamma-x)-2\delta\omega_0v,\\
U &= \zeta(1+x)^2(\gamma-p).
\end{aligned}
$$

The squared conductance remains defined for $x<-1$; this model imposes neither aperture closure nor mechanical contact.

<h2 id="bernoulli">Bernoulli valve</h2>

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= \omega_0^2(p-\gamma-x)-2\delta\omega_0v,\\
U &= \zeta\max(1+x,0)\operatorname{sgn}(\gamma-p)\sqrt{|\gamma-p|}.
\end{aligned}
$$

Flow vanishes at $x\leq-1$ and reverses when $p>\gamma$; no mechanical contact force is included. For both valves, $\gamma$ is supply pressure, $\zeta$ the flow coefficient, $\delta$ the damping ratio and $\omega_0=2\pi\,\mathrm{ratio}$. Their live delay range is $0.5\leq\tau\leq4$.
