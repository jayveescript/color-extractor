# Color Extractor

A client-side web app that extracts dominant color palettes from images using k-means clustering. No server required — everything runs in the browser.

## Features

- Drag-and-drop or click-to-upload image support (PNG, JPG, GIF, WEBP)
- Adjustable palette size (6, 8, 10, 12, or 16 colors)
- Visual color strip showing relative proportions
- Color cards displaying hex, RGB, and percentage coverage
- Click any color card to copy its hex value to clipboard
- Deployed via GitHub Pages

## How It Works

1. The uploaded image is downscaled to a 150px thumbnail on an HTML `<canvas>`
2. Pixel data is sampled and fed into a k-means++ clustering algorithm
3. Cluster centroids become the dominant palette colors, sorted by frequency

## Usage

Open `index.html` in any modern browser, or visit the GitHub Pages deployment.

No build step, no dependencies, no install needed.

## Development

The project is a single self-contained HTML file (`index.html`). To make changes:

1. Edit `index.html` directly
2. Open it in a browser to test
3. Commit and push — GitHub Pages deploys automatically via the workflow in `.github/workflows/`

## License

MIT
