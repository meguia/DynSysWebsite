---
layout: ../../layouts/Site.astro
title: Self oscillators
description: Model equations, parameters and principal bifurcations.
---

Bifurcation thresholds refer to fixed parameter values; frequencies are expressed in model time.

<h2 id="rayleigh">Rayleigh–van der Pol oscillator</h2>

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= (\alpha-v^2-\beta\omega_0^2x^2)v-\omega_0^2x.
\end{aligned}
$$

$\alpha$ is linear excitation, $\omega_0$ the natural angular frequency, and $\beta$ the relative strength of position-dependent damping. The interval $0\leq\beta\leq1$ connects the Rayleigh oscillator ($\beta=0$) to Harmonic Rayleigh ($\beta=1$).

For $\omega_0^2>0$, rest loses stability in a supercritical Hopf bifurcation at $\alpha=0$. At $\beta=1$ and fixed $\alpha>0$, the attracting orbit is the ellipse $v^2+\omega_0^2x^2=\alpha$: displacement and velocity amplitudes are $\sqrt\alpha/\omega_0$ and $\sqrt\alpha$, while frequency remains $\omega_0/(2\pi)$ in model time. Away from $\beta=1$, excitation can also change the frequency.

---

<h2 id="bowed">Bowed oscillator with regularized friction</h2>

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= -x-\mu\arctan\!\left(\frac{v-V}{0.05}\right)e^{-2|v-V|}.
\end{aligned}
$$

A moving bow drives a spring–mass oscillator through velocity-dependent friction. $V$ is bow speed and $\mu$ sets friction strength; the arctangent smooths sliding reversal, while the exponential gives velocity weakening. Exact sticking is not imposed.

For $\mu>0$, the displaced rest state loses oscillatory stability when $|V|\approx0.1345$, at the maximum of the friction curve. Crossing into the velocity-weakening region supplies effective negative damping and permits self-oscillation. At $V=0$, motion decays; at $\mu=0$, the oscillator is conservative.

---

<h2 id="lugre">LuGre (Lund–Grenoble) stick–slip oscillator</h2>

$$
\begin{aligned}
\dot x &= V-v,\\
0.1\dot v &= 1000x-\sigma_0z-\sigma_1\dot z-\sigma_2v,\\
\dot z &= v-\frac{\sigma_0|v|z}{4000d\left[0.2+0.2e^{-(v/v_s)^2}\right]}.
\end{aligned}
$$

The state variables are spring extension $x$, slider velocity $v$ and mean bristle deflection $z$. Pulling speed $V$ drives the mass; contact depth $d$ sets normal force, and $v_s$ sets the Stribeck velocity scale. The coefficients $\sigma_0$, $\sigma_1$ and $\sigma_2$ describe bristle stiffness, bristle damping and viscous friction.

Changing speed or normal load can destabilize steady sliding and produce stick–slip cycles. The oscillatory instability depends on the elastic and damping parameters as well as the velocity-weakening friction curve; there is no parameter-independent critical speed. Mass and spring stiffness are fixed at $0.1$ kg and $1000$ N/m.

---

<h2 id="hindmarsh-rose">Hindmarsh–Rose neuronal oscillator</h2>

$$
\begin{aligned}
\dot x &= y-x^3+3x^2-z+I,\\
\dot y &= 1-5x^2-y,\\
\dot z &= r\left[4(x+1.6)-z\right].
\end{aligned}
$$

Fast activation $x$ and recovery $y$ interact with the slow adaptation variable $z$. The drive $I$ controls excitation and $r$ sets the adaptation rate, governing the separation between individual spikes and the burst envelope.

For $r=0.006$, a rest-state Hopf bifurcation occurs near $I=1.359$, with a small interval of hysteresis below onset. Increasing $I$ produces spike-adding transitions between bursts, irregular bursting around $I=3.0$–$3.2$, and tonic spiking around $I=3.5$–$4.0$. These latter intervals are numerical regime examples, not exact bifurcation boundaries.

---

<h2 id="kks">Kuznetsov–Kuznetsov–Stankevich (KKS) oscillator</h2>

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= (z+x^2-x^4/2)v-\omega^2x,\\
\dot z &= \mu-x^2.
\end{aligned}
$$

The variable $z$ stores and replenishes excitation, $\mu$ controls energy supply, and $\omega$ sets the carrier angular frequency. Interaction between the carrier and the slower energy cycle permits two-frequency quasiperiodic motion on a torus; $\mu=0.5$, $\omega=2\pi$ is a reference example.

Varying $\mu$ or $\omega$ changes amplitude modulation and can enter periodic locking regions. In the high-frequency limit the torus-bifurcation boundary approaches $\mu=1$, outside the displayed $\mu\leq0.9$ range; it is not an exact finite-frequency threshold. Lower carrier frequencies can also produce chaos.

---

<h2 id="wright">Wright quadratic delay equation</h2>

$$
\dot x(t)=-x(t-\tau)\,[1+x(t)].
$$

Delayed negative feedback controls the growth of a single scalar state. The delay $\tau$ is the only model parameter; increasing it changes the feedback phase and can destabilize the equilibrium.

For histories above $-1$, $x=0$ is attracting up to $\tau=\pi/2\approx1.571$. A supercritical Hopf bifurcation creates periodic oscillation above this value. The available range is $0.5\leq\tau\leq2.5$; the plotted coordinates $x(t)$, $x(t-\tau)$ and, in 3D, $x(t-2\tau)$ are samples of the same evolving state.
