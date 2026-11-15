---
layout: ../../layouts/Site.astro
title: Chaos
description: Governing equations for the chaos collection.
---

<h2 id="lorenz">Lorenz</h2>

$$
\begin{aligned}
\dot x &= \sigma(y-x),\\
\dot y &= x(\rho-z)-y,\\
\dot z &= xy-\beta z.
\end{aligned}
$$

<h2 id="bouali">Bouali</h2>

$$
\begin{aligned}
\dot x &= 3x(1-y)-\beta z,\\
\dot y &= -y(1-x^2),\\
\dot z &= -0.2w,\\
\dot w &= 0.01z.
\end{aligned}
$$

The implemented variant has four state variables.

<h2 id="thomas">Thomas</h2>

$$
\begin{aligned}
\dot x &= \sin(ay)-bx,\\
\dot y &= \sin(az)-by,\\
\dot z &= \sin(ax)-bz.
\end{aligned}
$$

<h2 id="rossler">Rössler</h2>

$$
\begin{aligned}
\dot x &= -y-z,\\
\dot y &= x+ay,\\
\dot z &= b+z(x-c).
\end{aligned}
$$

<h2 id="duffing">Forced Duffing</h2>

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= -\mu v+x(\beta-x^2)+A\cos\phi,\\
\dot\phi &= \omega.
\end{aligned}
$$

$\phi$ is the forcing phase; $A$ and $\omega$ set its amplitude and angular frequency.

<h2 id="chua">Chua</h2>

$$
\begin{aligned}
\dot x &= \alpha\left[y-(1+m_1)x-\frac{m_0-m_1}{2}\left(|x+1|-|x-1|\right)\right],\\
\dot y &= x-y+z,\\
\dot z &= -\beta y.
\end{aligned}
$$

$m_0$ and $m_1$ are the inner and outer slopes of the piecewise-linear characteristic.

<h2 id="arneodo">Arneodo–Coullet–Tresser</h2>

$$
\begin{aligned}
\dot x &= v,\\
\dot v &= z,\\
\dot z &= ax-bv-cz-x^3.
\end{aligned}
$$

<h2 id="cubic">Cubic DDE</h2>

$$
\dot x(t)=x(t-\tau)\,[1-x(t-\tau)^2].
$$

The live delay range is $0.5\leq\tau\leq1.65$. The plotted coordinates are $x(t)$, $x(t-\tau)$ and, in 3D, $x(t-2\tau)$. Larger delays are excluded because solutions can escape.

Chaotic regimes depend on the parameter values and initial state or history.
