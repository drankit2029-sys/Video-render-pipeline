# Indian Ocean Is Larger Than You Think — HyperFrames Composition

1:1 recreation of the YouTube Short (`https://youtube.com/shorts/bVDi_QLL0sA`) built with [HyperFrames](https://github.com/heygen-com/hyperframes) (`1080x1920`, `28s`, `60fps`) using deterministic GSAP timelines (`window.__timelines.main`), satellite map camera choreography, pixel-traced SVG coastline vectors, and 3D perspective transforms.

## Project Structure

- `index.html` — Root HyperFrames composition (`data-composition-id="main"`, `1080x1920`, `28s`)
- `preview.html` — Local `<hyperframes-player>` wrapper
- `assets/world-map.jpg` — High-resolution equirectangular satellite physical map texture
- `assets/moon.png` — Alpha-masked photorealistic full moon texture
- `.github/workflows/render.yml` — Ready-to-run GitHub Actions workflow for rendering on an Ubuntu runner

## Render via GitHub Actions Runner

1. Push this directory to your GitHub repository.
2. Open the **Actions** tab and run **Render HyperFrames Video** (or push to `main`).
3. Download the rendered `indian-ocean-short.mp4` from the workflow run artifacts.

## Render Locally

```bash
npx hyperframes lint
npx hyperframes preview
npx hyperframes render --fps 60 --quality high --output indian-ocean-short.mp4
```
