---
layout: ../../layouts/Site.astro
title: Oscillators
description: Governing equations for the oscillator collection.
---

<h2 id="rayleigh">Rayleigh–van der Pol</h2>

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= (\alpha-v^2-\beta\omega_0^2x^2)v-\omega_0^2x.
\end{aligned}
$$

$0\leq\beta\leq1$: Rayleigh at $\beta=0$, harmonic self-oscillation at $\beta=1$. [Harmonic orbit and frequency](/models/rayleigh-van-der-pol/).

<h2 id="bowed">Bowed oscillator</h2>

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= -x-\mu\arctan\!\left(\frac{v-V}{0.05}\right)e^{-2|v-V|}.
\end{aligned}
$$

$V$ is bow velocity and $\mu$ the friction coefficient. The arctangent regularizes sliding reversal; exact sticking is not imposed.

<h2 id="lugre">LuGre</h2>

$$
\begin{aligned}
\dot x &= V-v,\\
0.1\dot v &= 1000x-\sigma_0z-\sigma_1\dot z-\sigma_2v,\\
\dot z &= v-\frac{\sigma_0|v|z}{4000d\left[0.2+0.2e^{-(v/v_s)^2}\right]}.
\end{aligned}
$$

$x$ is spring extension, $v$ slider velocity and $z$ bristle displacement. Controls are pulling speed $V$, contact depth $d$, Stribeck speed $v_s$, bristle stiffness $\sigma_0$, bristle damping $\sigma_1$ and viscous damping $\sigma_2$.

<h2 id="hindmarsh-rose">Hindmarsh–Rose</h2>

$$
\begin{aligned}
\dot x &= y-x^3+3x^2-z+I,\\
\dot y &= 1-5x^2-y,\\
\dot z &= r\left[4(x+1.6)-z\right].
\end{aligned}
$$

$I$ is the drive and $r$ the adaptation rate.

<h2 id="kks">KKS</h2>

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= (z+x^2-x^4/2)v-\omega^2x,\\
\dot z &= \mu-x^2.
\end{aligned}
$$

$\mu$ is the energy-supply parameter and $\omega$ the carrier angular frequency in model time.

<h2 id="wright">Quadratic Wright DDE</h2>

$$
\dot x(t)=-x(t-\tau)\,[1+x(t)].
$$

The live delay range is $0.5\leq\tau\leq2.5$. The plotted coordinates are $x(t)$, $x(t-\tau)$ and, in 3D, $x(t-2\tau)$; only one scalar equation is integrated.
