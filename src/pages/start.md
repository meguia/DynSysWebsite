---
layout: ../layouts/Site.astro
title: Implementation
description: Runtime requirements, installation and execution commands.
---

## Browser

Requires Julia 1.13, WebGL 2, Git and authenticated GitHub access. Keep the shared library and interface checkouts in the same parent directory. With [Juliaup](https://julialang.org/install/):

```sh
juliaup add 1.13
git clone git@github.com:meguia/RealTimeAudioVisualDynamics.jl.git
git clone git@github.com:meguia/RealTimeAudioVisualDynamicsVR.jl.git
cd RealTimeAudioVisualDynamicsVR.jl
julia +1.13 --project=. setup.jl
```

Setup installs dependencies and compiles caches; the first run can take several minutes. Launch one application at a time:

```sh
julia +1.13 --project=. app.jl --view=explore --models=saxophone --impedances=openwind
julia +1.13 --project=. app.jl --view=explore --models=oscillators
julia +1.13 --project=. app.jl --view=play --models=3d
```

Open the printed URL, including its `#` token. Select the audio output, wait for **ready**, then press **Start**. Keep Julia running throughout the session.

| View | Interface |
| --- | --- |
| Explore | Parameters, time series, XY plots and named presets |
| Play | 3D trajectories and keyboard controls |
| Saxophone | Specialized Explore layout with fingering selection |

## Vulkan

Requires Linux and Vulkan 1.2+ with buffer device addresses and variable pointers. Graphics use Julia 1.12; audio uses Julia 1.13 in a separate process. After [Vulkan setup](https://github.com/meguia/RealTimeAudioVisualDynamicsVulkan.jl#installation):

```sh
julia +1.12 --project=. app.jl --view=saxophone --impedances=openwind
```

## Presets

Name and save presets in Explore. Play provides the following controls:

| Key | Action |
| --- | --- |
| Q, then two digits | Select preset |
| Hold ↑ / ↓ | Move toward the selected preset / return |
| Shift + ↑ / ↓ | Faster transition |
| Release arrow | Pause transition |
| P | Save current parameters |

[Browser and Meta Quest setup; complete controls](https://github.com/meguia/RealTimeAudioVisualDynamicsVR.jl).
