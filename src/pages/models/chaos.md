---
layout: ../../layouts/Site.astro
title: Chaos
description: Model equations, parameters and principal bifurcations.
---

Bifurcation thresholds refer to fixed parameter values; frequencies are expressed in model time.

<h2 id="lorenz">Lorenz convection system</h2>

$$
\begin{aligned}
\dot x &= \sigma(y-x),\\
\dot y &= x(\rho-z)-y,\\
\dot z &= xy-\beta z.
\end{aligned}
$$

Three convection modes represent circulation and temperature variation. The Prandtl parameter $\sigma$ sets relative relaxation rates, $\rho$ is thermal driving, and $\beta$ controls geometric damping.

For positive $\sigma$ and $\beta$, a pitchfork bifurcation at $\rho=1$ creates two nonzero equilibria. For $\sigma=10$ and $\beta=8/3$, they lose stability in a subcritical Hopf bifurcation at $\rho\approx24.737$; $\rho=28$ gives the classical chaotic attractor. Coexistence of equilibria and a chaotic attractor near the transition makes the initial state relevant.

---

<h2 id="bouali">Periodically driven Bouali-type system</h2>

$$
\begin{aligned}
\dot x &= 3x(1-y)-\beta z,\\
\dot y &= -y(1-x^2),\\
\dot z &= -0.2w,\\
\dot w &= 0.01z.
\end{aligned}
$$

The harmonic pair $(z,w)$ drives the nonlinear feedback subsystem $(x,y)$, with $\beta$ setting the coupling strength. Its forcing angular frequency is fixed at $\sqrt{0.002}$ in model time; the initial amplitude of $(z,w)$ also determines the forcing amplitude.

At $\beta=0$, closed orbits surround $(x,y)=(1,1)$ rather than an isolated attracting limit cycle. Increasing $\beta$ perturbs these oscillations through periodic forcing. A bifurcation diagram has not been established for this four-state extension; thresholds for the three-state Bouali systems do not apply directly.

---

<h2 id="thomas">Thomas cyclically symmetric oscillator</h2>

$$
\begin{aligned}
\dot x &= \sin(ay)-bx,\\
\dot y &= \sin(az)-by,\\
\dot z &= \sin(ax)-bz.
\end{aligned}
$$

Each coordinate drives the next through a sine function. The parameter $a$ sets its spatial scale, while $b$ supplies linear damping; for $a>0$, the ratio $b/a$ controls the corresponding dynamical regimes.

For $a=1$, reducing $b$ through approximately $0.329$ produces a Hopf bifurcation of the nonzero equilibria. Further reduction gives period doubling and a first chaotic band near $b=0.208$, interspersed with periodic windows. Changing $a$ rescales these damping thresholds through $b/a$.

---

<h2 id="rossler">Rössler system</h2>

$$
\begin{aligned}
\dot x &= -y-z,\\
\dot y &= x+ay,\\
\dot z &= b+z(x-c).
\end{aligned}
$$

The $(x,y)$ subsystem supplies spiral motion, while the nonlinear $xz$ term produces excursions in $z$ and reinjection. The parameters $a$, $b$ and $c$ control spiral growth, constant drive to $z$, and the $x$ level at which $z$ changes from decay to growth.

For $a=b=0.2$, increasing $c$ gives a period-doubling route to chaos: the first two doublings are near $c=2.832$ and $3.837$, and $c=5.7$ is a chaotic example. Periodic windows interrupt this route; the first doubling lies below the current $c\geq3$ control range.

---

<h2 id="duffing">Periodically forced Duffing oscillator</h2>

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= -\mu v+x(\beta-x^2)+A\cos\phi,\\
\dot\phi &= \omega.
\end{aligned}
$$

The damping is $\mu$, $\beta$ controls the restoring force, and $A$ and $\omega$ set forcing amplitude and angular frequency. For $\beta>0$, the potential has two wells at $x=\pm\sqrt\beta$; $\phi$ is the continuous forcing phase.

Changing forcing or damping can produce period doubling, periodic windows and irregular switching between wells. With $\mu=0.1$, $\beta=1$ and $\omega=1.2$, $A=0.05$ gives a forcing-periodic response and $A=0.30$ a chaotic example from $(x,v,\phi)=(0,1,0)$. Coexisting attractors can give different outcomes after a parameter sweep.

---

<h2 id="chua">Chua nonlinear circuit</h2>

$$
\begin{aligned}
\dot x &= \alpha\left[y-(1+m_1)x-\frac{m_0-m_1}{2}\left(|x+1|-|x-1|\right)\right],\\
\dot y &= x-y+z,\\
\dot z &= -\beta y.
\end{aligned}
$$

Two capacitor voltages and an inductor current interact through a piecewise-linear active resistor. The parameters $\alpha$ and $\beta$ set capacitive and inductive time-scale ratios; $m_0$ and $m_1$ are the inner and outer slopes of the resistor characteristic.

Oscillatory instabilities, period doubling and global connections between scrolls organize the periodic and chaotic regimes. The values $\alpha=15.6$, $\beta=28$, $m_0=-8/7$ and $m_1=-5/7$ give a double-scroll attractor. Changing the slopes also moves the equilibria, so a single threshold does not describe the whole parameter family.

---

<h2 id="arneodo">Arneodo–Coullet–Tresser cubic jerk oscillator</h2>

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= z,\\
\dot z &= ax-bv-cz-x^3.
\end{aligned}
$$

Here $v=\dot x$ and $z=\ddot x$, so the third equation specifies the jerk. Linear drive $a$, velocity feedback $b$ and acceleration damping $c$ compete with cubic saturation; for $a>0$, the nonzero equilibria are $x=\pm\sqrt a$.

For positive $a,b,c$, these equilibria lose oscillatory stability at $2a=bc$. With $b=3.5$, $c=1$, the boundary is $a=1.75$, below the current control range. The reference values $(a,b,c)=(5.5,3.5,1)$ produce chaos; nearby periodic windows and changes in lobe switching are global features not located by this linear threshold.

---

<h2 id="cubic">Sprott cubic delay equation</h2>

$$
\dot x(t)=x(t-\tau)\,[1-x(t-\tau)^2].
$$

A cubic feedback law acts on the past value of a scalar state. The delay $\tau$ controls the feedback phase; the equilibria are $0$ and $\pm1$, and the plotted extra coordinates are delayed values rather than additional equations.

The equilibria $x=\pm1$ lose stability at $\tau=\pi/4\approx0.785$. Increasing delay leads from periodic oscillation to chaos with periodic windows, reported above approximately $\tau=1.538$; the result also depends on the initial history. The available range is $0.5\leq\tau\leq1.65$, avoiding larger delays where solutions can escape. The plots use $x(t)$, $x(t-\tau)$ and, in 3D, $x(t-2\tau)$.
