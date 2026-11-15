---
layout: ../../layouts/Site.astro
title: Model index
description: Implemented oscillator, chaos, tube and saxophone models.
---

## Oscillators

| Model | Formulation |
| --- | --- |
| [Rayleigh–van der Pol](/models/rayleigh-van-der-pol/) | ODE; velocity- and position-dependent damping |
| [Bowed oscillator](/models/oscillators/#bowed) | ODE; arctangent friction law |
| [LuGre](/models/oscillators/#lugre) | ODE; dynamic bristle friction |
| [Hindmarsh–Rose](/models/oscillators/#hindmarsh-rose) | Three-variable ODE |
| [KKS](/models/oscillators/#kks) | Three-variable ODE; quasiperiodic regimes |
| [Quadratic Wright DDE](/models/oscillators/#wright) | Scalar retarded DDE; variable delay |

## Chaos

| Model | Formulation |
| --- | --- |
| [Lorenz](/models/chaos/#lorenz) | Three-variable ODE |
| [Bouali](/models/chaos/#bouali) | Four-variable ODE |
| [Thomas](/models/chaos/#thomas) | ODE; cyclic sine coupling |
| [Rössler](/models/chaos/#rossler) | Three-variable ODE |
| [Forced Duffing](/models/chaos/#duffing) | ODE with periodic forcing |
| [Chua](/models/chaos/#chua) | ODE; piecewise-linear characteristic |
| [Arneodo–Coullet–Tresser](/models/chaos/#arneodo) | Cubic jerk equation |
| [Cubic DDE](/models/chaos/#cubic) | Scalar retarded DDE; variable delay |

The scalar DDEs use the coordinates $x(t)$, $x(t-\tau)$ and $x(t-2\tau)$ for 3D visualization; the first two are used in 2D. Chaotic regimes depend on the parameter values.

## Tubes

| Model | Coupling |
| --- | --- |
| [Rayleigh–van der Pol with a tube](/models/tubes/#rayleigh) | Nonlinear oscillator–pressure coupling; linear at $\eta=0$ |
| [Squared-conductance valve](/models/tubes/#squared-conductance) | Conductance quadratic in valve opening |
| [Bernoulli valve](/models/tubes/#bernoulli) | Bernoulli flow with reed closure |

Each model has a neutral DDE formulation and a modal ODE approximation. The round-trip delay $\tau$ is adjustable during integration. Modal approximations are available in Explore; Play uses the DDE formulations. [Resonator equations](/models/tubes/#neutral).

## Saxophone

[Saxophone model](/models/saxophone/): reed contact, regularized Bernoulli flow and eight acoustic modes per fingering. OpenWind and measured impedance banks; two-bank coupling transfer during fingering changes.
