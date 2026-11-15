---
layout: ../../layouts/Site.astro
title: Saxophone
description: Reed-contact equations, impedance fits and fingering transitions.
---

## Single-reed saxophone with modal bore

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

The normalized blowing pressure $\gamma$ drives the reed and airflow; $\zeta$ combines rest opening and flow coupling. Each pair $(q_n,s_n)$ represents one acoustic mode: $\alpha_n$ sets its damping rate, $\omega_n$ its angular frequency and $C_n$ its pressure–flow coupling through the impedance residue. The fixed reed coefficients set its mechanical resonance and damping. The $h^-$ term regularizes reed contact with the mouthpiece lay, and $\varepsilon$ smooths closure and flow reversal.

## Oscillation regimes

As $\gamma$ varies, steady flow can lose stability in a Hopf bifurcation. Different periodic branches can coexist, allowing hysteresis and jumps between registers; stronger motion can bring the reed into contact with the lay. The thresholds depend on $\zeta$ and the full impedance of the selected fingering, so there is no common critical pressure for the two banks. A map of these boundaries has not been established for all fitted impedances.

## Impedance banks

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

[Implementation](../../start/) · [Recordings](../../recordings/saxophone/)
