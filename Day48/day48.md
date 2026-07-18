# Console — Dev Laptop Decide

A single-file, no-dependency web app for comparing dev laptops on the criteria that actually matter to you — not a fixed "best of" list. Adjust nine weighted criteria on a mixing-console-style fader board and watch the ranking recalculate live, with every data point traced back to a named, citable source.

## What it does

Comparing laptops usually means either trusting someone else's fixed ranking or manually cross-referencing a dozen review sites. This tool splits the difference: it ships with real, sourced data for four laptops, but lets *you* decide what matters — battery life over raw performance, Linux support over display quality, whatever the priority — and the ranking updates instantly as you move the faders.

It compares four real dev-laptop options:

- **MacBook Pro 14" (M4 Pro, 2024)**
- **Dell XPS 15 (2023, discontinued)**
- **Lenovo ThinkPad X1 Carbon (Gen 12, 2024)**
- **Framework Laptop 13 (Ryzen AI 300, 2025)**

across nine criteria: price, CPU/GPU performance, battery life, build quality & repairability, display quality, portability, keyboard quality, Linux/dev-OS compatibility, and port selection & upgradeability.

## Features

- **Live weighted ranking** — nine draggable fader controls recompute the match score in real time, no page reload
- **Two built-in presets** — "Equal weights" and a "Dev-focused" preset tuned toward Linux support, upgradeability, and price
- **Sourced data, not vibes** — every fact in each laptop's expandable breakdown links to the review or spec sheet it came from
- **Estimate flags** — data points that required interpolation (a benchmark from an adjacent model year, a repairability score that doesn't exist for this exact generation) are clearly badged `ESTIMATE` with an explanation, never silently presented as fact
- **"How this was researched" panel** — walks through the judgment calls made, including why the Dell XPS 15 (a discontinued product) is included and how it's handled
- **Full sources panel** — all 24 citations in one place, each linked
- **Handles the edges** — a loading state while the ranking computes, an empty state if every fader is set to zero, and a "tied" badge when two laptops land on the same score
- **Fully responsive** — the fader board scrolls horizontally on narrow screens; layout collapses cleanly on mobile

## Design

Styled as a hardware mixing console rather than a generic dashboard — vertical faders, LED-amber accents, monospace data readouts — to fit the "dev hardware" subject matter. Dark graphite palette with amber and teal accents, system font stack (no external font/library dependencies).

## Tech

Pure HTML, CSS, and vanilla JavaScript. No frameworks, no build step, no external libraries or CDN dependencies — open `index.html` directly in a browser or serve it as a static file.

## Running locally

```bash
git clone https://github.com/srivastavarudresh552-cmyk/<repo>.git
cd <repo>
open index.html   # or just double-click the file
```

## Data & methodology

All comparison data is manually researched and cited — no invented numbers. Full sourcing rationale, including how conflicting review methodologies and missing data points were handled, is documented inside the app itself under **"How this was researched."** Prices reflect launch MSRP, not live pricing — check current retailer listings before making a purchase decision.

## License

MIT — free to use, modify, and adapt for your own comparison tools.
