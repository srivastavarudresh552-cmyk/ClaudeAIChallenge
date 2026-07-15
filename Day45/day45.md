# Decision Report

An interactive, single-file HTML dashboard that turns a 4-question interview into a full decision-analysis report — trade-off breakdown, animated scoring matrix, premortem, a 7-day test plan, and a decisive verdict.

Built as a personal decision-strategy tool: answer four short prompts, and get back a structured, visual report instead of a wall of text.

## What It Does

The report walks through a real decision end-to-end:

1. **The Real Decision** — a plain-language restatement of the actual trade-off
2. **The Case For Each Option** — strengths, hidden upsides, weaknesses, and "best if you value" framing for every option
3. **Assumption Buster** — surfaces unstated assumptions and names the cognitive biases in play (loss aversion, status quo bias, etc.)
4. **Decision Matrix** — 7-dimension scoring (career upside, financial safety, growth, stress, reversibility, alignment, regret risk) with animated horizontal bars and a total score per option
5. **Premortem** — imagines each top option failing after 12 months, with early warning signs and a prevention action
6. **7-Day Test Plan** — a concrete day-by-day validation plan before fully committing
7. **The Verdict** — a decisive pick, why it wins, what could flip it, and one hard truth
8. **Shareable Cards** — three screenshot-ready summary cards (matrix, verdict, LinkedIn-style hook)

## Design

- Dark, glassmorphism-adjacent card layout, single column, max-width 720px
- CSS custom properties for full theming control
- Animated matrix bars (staggered `@keyframes` grow-in on load)
- Fully responsive down to mobile (labels stack above bars, cards go full-width, shareable cards stack)
- Font: [Inter](https://fonts.google.com/specimen/Inter) via Google Fonts

## Tech Stack

- Pure HTML/CSS — no frameworks, no build tools, no JS dependencies
- Single self-contained file

## How It Works

The report is generated from a short structured interview (decision + options, goal/timeline, gut check, biggest fear + reversibility). All content in the report — the case for each option, matrix scores, premortem, and verdict — is derived directly from those answers, not invented.

Or drag the file into any browser tab.

## Customization

All colors, spacing, and typography are controlled via CSS custom properties at the top of the `<style>` block:


## License

MIT

---

Built with Claude AI
