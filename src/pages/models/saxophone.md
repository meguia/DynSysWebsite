---
layout: ../../layouts/Site.astro
title: Saxophone
description: Reed-contact equations, impedance fits and fingering transitions.
---

## Governing equations

Let $x$ denote reed displacement, $v$ its velocity, $h=1+x$ the opening, and $p=\sum_{n=1}^{8}q_n$ the mouthpiece pressure. Time is in milliseconds.

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= -4.224v+17.842176\left[p-\gamma-x+100(h^-)^2(1-v)\right],\\
\dot q_n &= -\alpha_nq_n-2\omega_ns_n+2C_nU,\\
\dot s_n &= \tfrac12\omega_nq_n-\alpha_ns_n,
\qquad n=1,\ldots,8.
\end{aligned}
$$

The regularized flow and contact terms are

$$
U=\zeta h^+\frac{\gamma-p}{\left[(\gamma-p)^2+\varepsilon\right]^{1/4}},
\qquad h^\pm=\frac{h\pm\sqrt{h^2+\varepsilon}}2,
\qquad \varepsilon=0.001.
$$

Here $\gamma$ is blowing pressure and $\zeta$ the flow parameter. Each pair $(q_n,s_n)$ represents one mode; $\alpha_n$, $\omega_n$ and $C_n$ are its damping rate, angular frequency and real residue.

## Impedance data

| Bank | Fits | Modes per fingering |
| --- | --- | --- |
| OpenWind | 26 simulated impedances | 8 |
| Measured | 34 distinct measurements | 8 |

Coefficients are fitted separately for each fingering. Replacement measurements use the same equations and coefficient convention.

## Fingering transitions

Legato uses two eight-mode banks coupled to one reed. The outgoing bank retains its state; the incoming bank starts with zero stored energy. Smooth gains weight both flow drive and pressure readout. Non-legato additionally lowers $\gamma$ to zero and restores it over the transition duration.

This is an experimental coupling transfer between fixed-fingering impedance fits; tone-hole motion is not modelled.

## Output and diagnostics

Audio uses mouthpiece pressure; bell and tone-hole radiation are not modelled. Diagnostics include state trajectories, the pressure spectrum, modal activity and fundamental pitch (note and cents; A4 = 440 Hz). The diagnostic signals precede gain and reverb.

## Implementation and data sources

- [Model implementation and numerical validation](https://github.com/meguia/RealTimeAudioVisualDynamics.jl/tree/main/impedances)
- [Original OpenWind fits](https://github.com/meguia/RTSax-Experiment/tree/main/src/impedances/alto)
- [Installation and execution](/start/)
- [OpenWind scale recording](/#recordings)
