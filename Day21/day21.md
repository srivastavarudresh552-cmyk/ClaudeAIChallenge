# 🧭 Digital Footprint & Privacy Exposure Dashboard

A single self-contained HTML report that turns a list of apps into a premium, Stripe/Linear/Apple-Privacy-Report–style dashboard — showing exposure scores, company ownership, risk dimensions, and an interactive privacy simulator. No backend, no build step, no external dependencies.

![facts vs estimates](https://img.shields.io/badge/methodology-facts%20vs%20estimates-4338CA)
![stack](https://img.shields.io/badge/stack-Vanilla%20HTML%20%2B%20CSS%20%2B%20JS-15171C)
![license](https://img.shields.io/badge/license-MIT-green)

## ⚠️ What this is — and isn't

This dashboard is a **methodology demo**, not a surveillance tool. It works entirely from a short, user-supplied list of app names — nothing else.

- ❌ It does **not** access any account, device, location, browser history, or private database.
- ❌ It does **not** know anything true about a specific real person.
- ✅ It **does** apply public knowledge of how a given combination of apps *tends* to be used, and clearly separates that from what's actually known.

Every number and claim on the page carries one of two tags:

| Tag | Meaning |
|---|---|
| `FACT` | Counted directly from the app list (e.g. total services, parent company, share of services) |
| `ESTIMATE` | Inferred from general/public knowledge of how these kinds of apps are typically used — never a certainty, never personal data |

## ✨ Features

- **Digital Footprint Score (0–100)** — 🟢 Minimal · 🟡 Moderate · 🟠 Significant · 🔴 Extensive
- **Privacy Score (0–100)** — 🔴 Weak · 🟠 Fair · 🟡 Good · 🟢 Strong
- **Stat strip** — total services, parent company count, ecosystem concentration, estimated tracking surface
- **Exposure Heatmap** — color-coded intensity across 8 life categories (social, messaging, finance, shopping, etc.)
- **Company Exposure Ranking** — animated bar ranking of which parent company owns the most of the listed services
- **Data Collection Matrix** — a per-service table of typically-collected data types (identity, social graph, location, behavioral, financial, biometric)
- **Risk Radar** — a 6-axis SVG radar chart (social exposure, behavioral tracking, identity linkage, location signal, financial exposure, communications privacy risk)
- **Digital Twin Profile** — a synthesized persona (region, device ecosystem, age range, lifestyle) with explicit Low/Medium/High confidence tags
- **Most Valuable Data Assets** — ranked list of what's commercially attractive about the combined data
- **WOW Insights** — short, punchy cross-correlation observations
- **Privacy Improvement Simulator** — an interactive checklist; toggling items live-recalculates a projected Privacy Score and risk band
- **Final Verdict** — a plain-language summary with prioritized next actions
- Animated score gauges, count-up numbers, and a fully responsive layout (mobile → desktop)

## 🚀 Getting Started

This is a plain HTML fragment — no server, no install, no build:

1. Save the file (e.g. `digital-footprint-dashboard.html`)
2. Open it directly in any modern browser, **or**
3. Embed the `<style>` / markup / `<script>` block into an existing page or CMS — it's self-scoped under a single `.dfr-root` wrapper, so it won't leak styles into the rest of your site

There are no API calls, no tracking pixels, and no network requests of any kind — open it offline and it behaves identically.

## 🔧 Customizing the Dataset

All input data lives in one array near the top of the `<script>` block:

```js
var services = [
  { name: "Instagram", company: "Meta", category: "Social Media" },
  { name: "WhatsApp", company: "Meta", category: "Messaging" },
  // ...
];
```

To regenerate the dashboard for a different app list:

1. Edit `services` — every downstream section (stat strip, ranking, matrix, heatmap) recalculates automatically from this array
2. Update the hand-tuned `ESTIMATE` sections to match the new list:
   - `heatData` (category exposure intensity)
   - `matrixData` (per-service data-type intensity, 0–3 scale)
   - `radarAxes` (the 6 risk dimensions)
   - `twinData` (digital twin persona fields + confidence level)
   - `assets`, `wowInsights`, `simItems` (narrative + simulator content)
3. Adjust `FOOTPRINT_SCORE` and `PRIVACY_BASE` if the new list's breadth/category coverage/encryption mix changes meaningfully

> These hand-tuned values are illustrative groupings based on publicly known characteristics of each app category (e.g. "messaging apps with E2E encryption score lower on behavioral tracking"). They are a reasonable starting point, not a precise or certified model — treat them as a template to adapt, not ground truth.

## 🛠 How It Works

- **Scores & gauges**: rendered as SVG `<circle>` arcs with `stroke-dasharray`/`stroke-dashoffset`, animated on load with a CSS transition, paired with a `requestAnimationFrame` count-up for the number
- **Risk Radar**: plotted with plain trigonometry (`Math.cos` / `Math.sin`) into SVG `<polygon>` points — no charting library
- **Heatmap, ranking, matrix, twin profile, assets, insights**: all generated by iterating small JS data arrays into DOM nodes, so the visual layer always reflects the data layer
- **Privacy Improvement Simulator**: a `change` listener sums the `data-delta` of checked items, re-bands the projected score (Weak/Fair/Good/Strong), and updates the gauge color and fill live
- **Scoping**: everything is namespaced under `.dfr-root` with CSS custom properties, so it can be dropped into another page without colliding with existing styles

## 📁 Project Structure

```
digital-footprint-dashboard/
└── digital-footprint-dashboard.html   # everything — markup, CSS, and JS in one file
```

## 🔒 Ethics & Responsible Use

This kind of dashboard is meant to **illustrate** how much can plausibly be inferred from a simple app list — as an educational/privacy-awareness tool — not to produce real profiles of real people. If you adapt this for an actual product:

- Keep the Fact/Estimate distinction visible and prominent — don't let inferred content quietly read as confirmed
- Never wire it up to real account data, scraped data, or third-party data brokers without clear, informed consent
- Avoid presenting demographic or behavioral guesses (age, location, lifestyle) as anything more than low/medium-confidence possibilities

## 📄 License

MIT — adapt it for your own privacy-awareness tools, workshops, or demos.
