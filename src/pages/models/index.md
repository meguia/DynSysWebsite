---
layout: ../../layouts/Site.astro
title: Model index
description: Implemented oscillator, chaos, tube and saxophone models.
---

[Model guide: equations, parameter ranges and references (PDF)](/model-guide.pdf).

## Oscillators

| Model | Formulation |
| --- | --- |
| [Rayleigh–van der Pol](/models/rayleigh-van-der-pol/) | ODE; velocity- and position-dependent damping |
| [Bowed oscillator](/model-guide.pdf#page=2) | ODE; arctangent friction law |
| [LuGre](/model-guide.pdf#page=3) | ODE; dynamic bristle friction |
| [Hindmarsh–Rose](/model-guide.pdf#page=3) | Three-variable ODE |
| [KKS](/model-guide.pdf#page=4) | Three-variable ODE; quasiperiodic regimes |
| [Quadratic Wright DDE](/model-guide.pdf#page=4) | Scalar retarded DDE; variable delay |

## Chaos

| Model | Formulation |
| --- | --- |
| [Lorenz](/model-guide.pdf#page=5) | Three-variable ODE |
| [Bouali](/model-guide.pdf#page=5) | Four-variable ODE |
| [Thomas](/model-guide.pdf#page=5) | ODE; cyclic sine coupling |
| [Rössler](/model-guide.pdf#page=6) | Three-variable ODE |
| [Forced Duffing](/model-guide.pdf#page=6) | ODE with periodic forcing |
| [Chua](/model-guide.pdf#page=6) | ODE; piecewise-linear characteristic |
| [Arneodo–Coullet–Tresser](/model-guide.pdf#page=7) | Cubic jerk equation |
| [Cubic DDE](/model-guide.pdf#page=7) | Scalar retarded DDE; variable delay |

The scalar DDEs use the coordinates $x(t)$, $x(t-\tau)$ and $x(t-2\tau)$ for 3D visualization; the first two are used in 2D. Chaotic regimes depend on the parameter values.

## Tubes

| Model | Coupling |
| --- | --- |
| [Rayleigh–van der Pol with a tube](/model-guide.pdf#page=9) | Nonlinear oscillator–pressure coupling; linear at $\eta=0$ |
| [Squared-conductance valve](/model-guide.pdf#page=10) | Conductance quadratic in valve opening |
| [Bernoulli valve](/model-guide.pdf#page=10) | Bernoulli flow with reed closure |

Each model has a neutral DDE formulation and a modal ODE approximation. The round-trip delay $\tau$ is adjustable during integration. Modal approximations are available in Explore; Play uses the DDE formulations. [Resonator equations (PDF, p. 8)](/model-guide.pdf#page=8).

## Saxophone

[Saxophone model](/models/saxophone/): reed contact, regularized Bernoulli flow and eight acoustic modes per fingering. OpenWind and measured impedance banks; two-bank coupling transfer during fingering changes.
