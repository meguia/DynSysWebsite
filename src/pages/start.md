---
layout: ../layouts/Site.astro
title: Run it locally
label: From watching to playing
description: Julia computes the dynamics and audio. Choose a browser interface or the native Vulkan application.
---

## Browser

Install [Juliaup](https://julialang.org/install/) and Git. The browser application requires Julia 1.13 and a browser with WebGL 2. Clone the shared model library and browser application beside each other; these commands require GitHub access to both repositories.

```sh
juliaup add 1.13
git clone git@github.com:meguia/RealTimeAudioVisualDynamics.jl.git
git clone git@github.com:meguia/RealTimeAudioVisualDynamicsVR.jl.git
cd RealTimeAudioVisualDynamicsVR.jl
julia +1.13 --project=. setup.jl
```

Setup installs dependencies and prepares caches. The first setup can take several minutes.

Start the saxophone with the OpenWind impedances:

```sh
julia +1.13 --project=. app.jl --view=explore --models=saxophone --impedances=openwind
```

Open the complete URL printed in the terminal, including its `#` token. Select an audio output, wait for **ready**, and press **Start**. Keep Julia running while using the interface.

For oscillator controls or a 3D performance view, use:

```sh
julia +1.13 --project=. app.jl --view=explore --models=oscillators
julia +1.13 --project=. app.jl --view=play --models=3d
```

Run one application at a time. **Explore** provides sliders, waveforms, XY plots and presets. **Play** provides a rotating 3D trajectory with keyboard controls. The saxophone uses a specialized Explore layout.

## Native Vulkan

The recording uses the Linux Vulkan application. It requires a suitable Vulkan 1.2+ driver, Julia 1.12 for graphics and Julia 1.13 for audio.

Follow the [Vulkan installation instructions](https://github.com/meguia/RealTimeAudioVisualDynamicsVulkan.jl#installation), then launch its saxophone layout:

```sh
julia +1.12 --project=. app.jl --view=saxophone --impedances=openwind
```

## Presets and performance

Name and save presets in Explore. In Play, press **Q** followed by two digits to select a preset, then hold **↑** to move toward it or **↓** to return. **Shift** makes the transition faster; releasing the arrow pauses it. **P** saves the current parameters.

The browser application also supports Play in Meta Quest. Its [README](https://github.com/meguia/RealTimeAudioVisualDynamicsVR.jl) covers headset setup, audio routing and the full keyboard controls.
