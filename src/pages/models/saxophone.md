---
layout: ../../layouts/Site.astro
title: The saxophone
label: Reed / acoustic modes
description: One reed, eight resonances, and an impedance for each fingering.
---

[Watch the OpenWind scale →](/#recordings)

Air flowing through the reed opening excites the instrument’s acoustic modes. Their combined pressure acts back on the reed. Blowing pressure $\gamma$ and the flow parameter $\zeta$ control this interaction.

The **OpenWind** bank contains 26 simulated impedance fits. The **Measured** bank contains 34 fits to distinct measurements. Both use eight modes per fingering, with their own frequencies, damping and coupling strengths. New measurements can replace the coefficients without changing the model equations.

## Fixed fingering

Let $x$ be reed displacement, $v$ its velocity, $h=1+x$ the opening, and $p=\sum_{n=1}^{8}q_n$ the mouthpiece pressure. With time in milliseconds, the implemented model is

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

Each pair $(q_n,s_n)$ describes one damped acoustic mode. Its coefficients $\alpha_n$, $\omega_n$ and $C_n$ come from the selected impedance fit. Audio uses mouthpiece pressure; bell and tone-hole radiation are not modelled.

## Changing fingering

The legato transition keeps the reed moving while coupling transfers from the outgoing eight-mode bank to the incoming one. The outgoing modes retain their state; the incoming modes start with zero stored energy. The same smooth gains weight both the flow driving each bank and its contribution to mouthpiece pressure.

This is an experimental transition between fixed-fingering impedance fits. It does not simulate the detailed motion of opening and closing tone holes. **Non-legato** also lowers blowing pressure to zero and restores it over the selected duration.

## Reading the display

The upper traces show the selected model variables, and the XY plot shows their relationship. The target impedance panel overlays the live pressure spectrum and markers for the activity of each mode. The pitch readout estimates the fundamental, with cents relative to concert pitch.

The plots use the model signals before gain and reverb. Changing an audio effect therefore leaves the dynamical trajectory unchanged.

## Run it

After [installing the browser application](/start/), run:

```sh
julia +1.13 --project=. app.jl --view=explore --models=saxophone --impedances=openwind
```

Choose fingerings with the buttons or Page Up / Page Down. The transition slider sets the duration. Select Measured to use the measurement bank.

The [implementation and impedance notes](https://github.com/meguia/RealTimeAudioVisualDynamics.jl/tree/main/impedances) document the coefficient convention and numerical validation. The [OpenWind data](https://github.com/meguia/RTSax-Experiment/tree/main/src/impedances/alto) provide the original simulated fits.
