---
layout: ../../layouts/Site.astro
title: The models
label: Model collections
description: Oscillations, chaotic trajectories and acoustic feedback, made audible as they evolve.
---

The applications integrate differential equations continuously. Selected state variables become audio signals and plotted trajectories. Changing a parameter can change the amplitude, rhythm or character of the sound.

The [model guide (PDF)](/model-guide.pdf) gives equations, parameter hints and publications for the oscillator, chaos and tube collections.

## Oscillators

Self-sustained oscillations, stick–slip motion and slow bursts offer different ways to shape a waveform.

| Model | Mechanism |
| --- | --- |
| Rayleigh–van der Pol | A continuous family between Rayleigh and harmonic self-oscillation |
| Bowed oscillator | A moving bow drives a spring through an arctangent friction law |
| LuGre | Friction with an internal bristle state and stick–slip dynamics |
| Hindmarsh–Rose | Fast spikes coupled to a slow recovery variable |
| KKS | A nonlinear oscillator for exploring quasiperiodic motion |
| Quadratic Wright DDE | Scalar feedback with an adjustable delay |

For example, the Rayleigh–van der Pol family is

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= (\alpha-v^2-\beta\omega_0^2x^2)v-\omega_0^2x.
\end{aligned}
$$

Here $\alpha$ controls excitation, $\omega_0$ sets the uncoupled linear frequency, and $0\leq\beta\leq1$ selects the damping law. At $\beta=0$ this is the Rayleigh oscillator; at $\beta=1$ and $\alpha>0$, the invariant orbit $v^2+\omega_0^2x^2=\alpha$ is harmonic, with angular frequency $\omega_0$ in model time.

## Chaos

These systems can produce irregular trajectories without random input. Their behavior depends on the parameters: a chaotic model can also settle into a periodic orbit or a steady state.

| Model | Mechanism |
| --- | --- |
| Lorenz | Three coupled variables and the familiar two-wing attractor |
| Bouali | A three-variable nonlinear flow |
| Thomas | Cyclic sine coupling with damping |
| Forced Duffing | A periodically driven nonlinear spring |
| Rössler | Spiral motion with intermittent folding |
| Chua | An electronic oscillator with a piecewise-linear characteristic |
| Arneodo | A cubic jerk equation expressed as three first-order equations |
| Cubic DDE | Scalar delayed feedback with cubic nonlinearity |

For the scalar delay models, the plots use $x(t)$, $x(t-\tau)$ and, in 3D, $x(t-2\tau)$ to reveal the motion through its history.

## Tubes

An oscillator or valve interacts with pressure returning from an ideal tube. The delay $\tau$ represents a round trip; reflection controls how much of the wave returns.

| Model | Coupling |
| --- | --- |
| Rayleigh–van der Pol with a tube | Nonlinear coupling between oscillator motion and pressure; linear coupling at $\eta=0$ |
| Squared-conductance valve | Flow depends quadratically on valve opening |
| Bernoulli valve | Flow follows the pressure difference through a variable opening |

Each has a neutral delay-equation version and a modal approximation in Explore. The delay can change during playback. The 3D Play collection uses the delay versions.

## Saxophone

A reed with contact and regularized Bernoulli flow drives eight acoustic modes. **OpenWind** provides simulated impedances for 26 fingerings; **Measured** provides fits to 34 distinct measurements. Live fingering changes transfer coupling between two mode banks.

[See the saxophone equations and recording →](/models/saxophone/)
