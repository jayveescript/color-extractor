# CLAUDE.md

## Project Overview

Single-file browser app (`index.html`) that extracts dominant color palettes from images using k-means++ clustering on canvas pixel data. No build system, no dependencies.

## Key Facts

- **Entry point**: `index.html` — the entire app (HTML, CSS, JS) lives here
- **Algorithm**: k-means++ with configurable k (6–16 colors), 20 iterations, sampled at 1 pixel per ~2000
- **Canvas usage**: image is downscaled to max 150px before pixel extraction to keep performance fast
- **Deployment**: GitHub Pages, triggered automatically on push to `master`/`main`

## Making Changes

1. Edit `index.html` directly — no build step needed
2. Test by opening the file in a browser
3. Commit with a clear message and push

## Common Tasks

**Change default color count**: update the `selected` attribute on the `<option>` in `#color-count`

**Adjust image downscale resolution**: change `maxDim` (line ~83) — lower = faster, higher = more accurate

**Tweak k-means iterations**: change the `iterations` argument in `kMeans(pixels, k, 20)` — more iterations = slower but more stable results

**Add a new export format**: extend `renderPalette()` and add a copy button variant alongside the existing hex copy

## Architecture Notes

- No external libraries; vanilla JS only
- `kMeans()` returns an array of `{rgb, count, pct}` objects sorted by frequency descending
- `dist2()` uses squared Euclidean distance in RGB space (no perceptual weighting)
- Toast notification uses CSS transitions; it's triggered by clipboard write success
