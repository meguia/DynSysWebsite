# DynSys

[Website](https://meguia.github.io/DynSysWebsite/): model equations, implementation notes and recordings for RealTimeAudioVisualDynamics. Built with Astro, Markdown and KaTeX.

Requires Node.js 22.23.4+ and npm 9.6.5+.

```sh
npm ci
npm run dev
```

Open the local address printed in the terminal. `npm run build` creates `dist/`; `npm run preview` serves that build. No Julia process is needed to view the website.

With an older system Node.js, prefix the npm commands with `npx --yes --package=node@22.23.4 --package=npm@10.9.4 --` to use a temporary compatible runtime.

Pages are in `src/pages/`, styling in `src/styles/site.css`, and recordings in `public/media/`. Models and Recordings each have four collections: Self oscillators, Chaos, Tubes and Saxophone.

Saxophone recordings retain 1080p/60 fps video and stereo audio, with their final two seconds removed. Original captures remain outside the repository.

Pushes to `main` build and publish the site through `.github/workflows/deploy.yml`. GitHub Pages uses GitHub Actions as its publishing source; the site is public and independent of OpenAI hosting.
