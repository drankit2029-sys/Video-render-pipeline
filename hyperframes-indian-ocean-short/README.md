# Indian Ocean Is Larger Than You Think — HyperFrames Composition

1:1 recreation of the YouTube Short (`https://youtube.com/shorts/bVDi_QLL0sA`) built with [HyperFrames](https://github.com/heygen-com/hyperframes) (`1080x1920`, `28s`, `60fps`) using deterministic GSAP timelines (`window.__timelines.main`), satellite map camera choreography, pixel-traced SVG coastline vectors, and 3D perspective transforms.

## Project Structure

- `index.html` — Root HyperFrames composition (`data-composition-id="main"`, `1080x1920`, `28s`)
- `preview.html` — Local `<hyperframes-player>` wrapper
- `assets/world-map.jpg` — High-resolution equirectangular satellite physical map texture
- `assets/moon.png` — Alpha-masked photorealistic full moon texture
- `package.json` — Pins the HyperFrames CLI (`0.8.171`) and exposes `lint` / `check` / `render` / `snapshot` scripts
- `../.github/workflows/render.yml` — GitHub Actions workflow that renders on an Ubuntu runner (must live at the **repo root**, not inside this project folder)

## Render via GitHub Actions Runner

```bash
# from the repository root
gh workflow run render.yml
gh run watch
gh run download --name indian-ocean-short-mp4
```

The workflow also runs on every push to `master` / `main`. It installs FFmpeg and the
pinned Chrome build, runs `lint` + `check`, renders at delivery quality, verifies the
output with `ffprobe`, and uploads two artifacts:

- `indian-ocean-short-mp4` — the final `indian-ocean-short.mp4`
- `indian-ocean-short-qc` — still frames across the timeline for visual review

## Render Locally

Requires Node.js 22+, FFmpeg, and a Chromium-capable host.

```bash
npm run lint
npm run check
npm run render
```
