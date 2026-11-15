# DynSys

Internal reference for RealTimeAudioVisualDynamics: model equations, implementation notes and recordings. Built with Astro, Markdown and KaTeX.

Requires Node.js 22.23.4+ and npm 9.6.5+.

```sh
npm ci
npm run dev
```

Open the local address printed in the terminal. `npm run build` creates `dist/`; `npm run preview` serves that build. No Julia process is needed to view the website.

With an older system Node.js, prefix the npm commands with `npx --yes --package=node@22.23.4 --package=npm@10.9.4 --` to use a temporary compatible runtime.

Pages are in `src/pages/`, shared styling in `src/styles/site.css`, and recordings in `public/media/`. Models and Recordings each have four collection pages: Self oscillators, Chaos, Tubes and Saxophone. Model descriptions use Markdown with LaTeX equations. Repository links and execution commands are confined to the Implementation page.

The first recording, `openwind-saxophone-scale.mp4`, is the 15 November 2026 OpenWind scale, trimmed from 55.383333 to 53.383333 seconds. It retains 1080p/60 fps and stereo audio; the original `2026-11-15 16-25-04.mp4` stays outside this repository. The poster comes from 12 seconds into the recording.

Sites hosting is configured for [DynSys](https://dynsys-audio.jubilanthymn3.chatgpt.site), initially private. `.openai/hosting.json` identifies the site and its static build. This repository remains independent of the Julia applications.
