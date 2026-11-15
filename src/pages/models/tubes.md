---
layout: ../../layouts/Site.astro
title: Tubes
description: Neutral-delay and modal resonators with nonlinear oscillator and valve coupling.
---

Pressure $p$ and injected flow $U$ are normalized to unit characteristic acoustic impedance. Each exciter below couples to either resonator formulation. Reflection magnitude is $0<r<1$ and round-trip delay is $\tau>0$. The onset values below are calculated linear-stability thresholds at fixed parameters.

<h2 id="neutral">Neutral delay resonator</h2>

$$
\begin{aligned}
\dot A(t) &= U(t)-r\dot A(t-\tau),\\
p(t) &= U(t)-2r\dot A(t-\tau).
\end{aligned}
$$

The outgoing-wave integral $A$ stores propagation through an ideal tube; its delayed derivative represents the returning wave. The reflection magnitude $r$ sets losses and the round-trip delay $\tau$ sets the odd-harmonic resonance spacing, with fundamental frequency $1/(2\tau)$ in model time. Larger $r$ gives more weakly damped resonances.

Delayed derivatives come from the solver history, using the current $\tau(t)$ during live changes. For fixed $0<r<1$, the unforced acoustic waves decay; sustained sound and oscillatory instabilities arise from coupling to an exciter.

---

<h2 id="modal">Modal resonator approximation</h2>

$$
\begin{aligned}
\dot q_n &= \frac{\log r}{\tau}q_n-\frac{(2n-1)\pi}{\tau}w_n+\frac{4}{\tau}U,\\
\dot w_n &= \frac{(2n-1)\pi}{\tau}q_n+\frac{\log r}{\tau}w_n,\\
p &= \sum_{n=1}^{N}q_n,\qquad n=1,\ldots,N.
\end{aligned}
$$

Each $q_n$ contributes to pressure and $w_n$ is its quadrature coordinate. The $N$ damped modes have angular frequencies $(2n-1)\pi/\tau$ and decay rate $-\log(r)/\tau$; $N$ sets the represented bandwidth.

This finite-bandwidth approximation uses the same exciter laws below. Changing $\tau$ moves the resonances while retaining their states. Increasing $N$ can shift the coupled system's onset and nonlinear regimes, so a finite mode count need not reproduce every bifurcation of the delay formulation.

---

<h2 id="rayleigh">Rayleigh–van der Pol oscillator with nonlinear tube coupling</h2>

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= (\alpha-v^2-\beta\omega_0^2x^2)v-\omega_0^2x-\kappa(1+\eta x)p,\\
U &= (1+\eta x)v.
\end{aligned}
$$

Excitation $\alpha$, natural frequency $\omega_0$ and position damping $\beta$ have the same roles as in the [uncoupled oscillator](../oscillators/#rayleigh). The coefficient $\kappa$ sets pressure feedback, while $\eta$ makes both flow injection and pressure force depend on displacement; $\eta=0$ gives linear coupling. The delay range is $0.5\leq\tau\leq3$.

Tube losses move oscillation onset above the uncoupled threshold $\alpha=0$. For $\omega_0^2=1$, $\kappa=0.5$, $r=0.95$ and $\tau=3$, linear instability occurs near $\alpha=0.0414$ with the neutral resonator and $0.0398$ with eight modes. Neither $\eta$ nor $\beta$ changes this linear threshold, but both affect finite-amplitude motion; $\beta=1$ no longer guarantees harmonic oscillation when $\kappa>0$.

---

<h2 id="squared-conductance">Pressure-controlled valve with squared conductance</h2>

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= \omega_0^2(p-\gamma-x)-2\delta\omega_0v,\\
U &= \zeta(1+x)^2(\gamma-p).
\end{aligned}
$$

Supply pressure $\gamma$ drives flow through the opening-dependent conductance $\zeta(1+x)^2$. The mechanical angular frequency is $\omega_0$ and its damping ratio is $\delta$; the frequency-ratio control sets $\omega_0=2\pi\,\mathrm{ratio}$. The squared law remains defined for $x<-1$, without aperture closure or mechanical contact.

Steady flow becomes oscillatory near $\gamma=0.291$ for $\zeta=3$, $\omega_0=2\pi$, $\delta=0.02$, $r=0.95$ and $\tau=1$ (neutral resonator; eight modes give nearly the same onset). Changes in damping, reflection or acoustic tuning move this instability; $\gamma$ alone does not determine the regime. The delay range is $0.5\leq\tau\leq4$.

---

<h2 id="bernoulli">Pressure-controlled valve with Bernoulli flow</h2>

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= \omega_0^2(p-\gamma-x)-2\delta\omega_0v,\\
U &= \zeta\max(1+x,0)\operatorname{sgn}(\gamma-p)\sqrt{|\gamma-p|}.
\end{aligned}
$$

The pressure difference $\gamma-p$ drives square-root flow through the positive aperture. The coefficient $\zeta$ sets flow strength, $\omega_0=2\pi\,\mathrm{ratio}$ the valve frequency, and $\delta$ its damping ratio. Flow stops at $x\leq-1$ and reverses for $p>\gamma$; no mechanical contact force is included.

An oscillatory instability occurs near $\gamma=0.312$ for $\zeta=0.7$, $\omega_0=2\pi$, $\delta=0.2$, $r=0.95$ and $\tau=1$ (neutral resonator; eight modes give nearly the same onset). At larger amplitudes, closure during part of the cycle changes the waveform. Acoustic tuning and losses shift the threshold and can change the selected register. The delay range is $0.5\leq\tau\leq4$.
