# Content Intelligence Studio

A single-file HTML application that runs your content draft through a panel of specialist AI reviewers — each one a live call to Claude — and returns a scored, evidence-based verdict with rewrites, alternatives, and a publishing checklist.

No build step, no dependencies, no backend. Open the file in a browser and it works.

---

## What it does

You give it a piece of content (post copy, a script, a thumbnail image, or an article) plus some context — content type, platform, goal, and how harsh you want the review to be. It then:

1. **Designs a review pipeline** suited to that content type (a thumbnail gets a Visual Composition Reviewer; a LinkedIn post gets a Hook Reviewer and a Platform Algorithm Strategist; and so on).
2. **Runs each reviewer as a real API call** to Claude, one at a time, updating a live activity log and a roster panel as each one reports in.
3. **Renders every result as it arrives** — score, verdict, strengths, weaknesses, missed opportunities, reasoning, recommendations — no waiting for the whole pipeline to finish before you see anything.
4. **Produces a rewrite** with alternative hooks/openers you can copy with one click.
5. **Closes with an Executive Editor-in-Chief stage** that synthesizes everything into an overall score, executive summary, health report, top-impact improvements, a predicted-performance estimate (clearly labeled as an AI estimate), a before/after comparison, an interactive checklist, and follow-up prompts for going deeper.

Every score, quote, and rewrite comes directly from the model. There is no hardcoded scoring logic, canned feedback, or placeholder analysis anywhere in the app — if the API call fails, that section shows an error and a retry button instead of a fallback.

---

## Requirements

- A modern browser (Chrome, Edge, Firefox, Safari — anything with `fetch`, `FileReader`, and CSS custom properties).
- An environment where `fetch` requests to `https://api.anthropic.com/v1/messages` are authorized. The app does not ask for or store an API key — it assumes the request is already authenticated by whatever context it's running in (e.g. Claude.ai's artifact runtime). If you open the file standalone in a plain browser with no such proxy, the API calls will fail with an auth or CORS error — that's expected, not a bug in the app.

No npm install, no server, no external CSS/JS libraries. Everything — fonts, icons, animations — is built from plain CSS and inline SVG-free markup.

---

## Using it

1. **Open the file.** `content-intelligence-studio.html` in any browser.
2. **Configure the brief** in the setup panel:
   - **Content type** — social post/caption, video script, thumbnail/image, blog/article, or Other (free text).
   - **Platform** — LinkedIn, Instagram, X, TikTok/YouTube Shorts, or Other.
   - **Primary goal** — reach/virality, authority, engagement, leads, or Other.
   - **Review intensity** — Brutally honest, Balanced & direct, or Encouraging. This is injected directly into every reviewer's instructions, so the tone shift is real, not cosmetic.
3. **Choose what you're uploading** — Text only, Image only, or Text + image — and paste your draft and/or drop an image.
4. **Click "Run analysis."** The setup panel collapses, the review panel and live log appear, and each reviewer reports in sequentially.
5. **Read the results** as they populate: category cards, then the rewrite section, then the checklist, then the final report and score stamp.
6. **Go deeper** — once the panel finishes, click one of the suggested follow-up prompts (or type your own) to ask the Executive Editor for a further, targeted pass.
7. **Retry failures individually.** If any single reviewer's call fails (network hiccup, empty response, etc.), that stage shows a "Retry stage" button — no need to re-run the whole pipeline.
8. **Start over** with "New analysis" at any point.

---

## How the pipeline adapts to content type

| Content type | Reviewers |
|---|---|
| Social post/caption | Scroll-Stop Hook Reviewer → Structure & Readability Reviewer → Persuasion & Virality Psychologist → Platform Algorithm Strategist → Rewrite & Alternatives Strategist → Executive Editor-in-Chief |
| Video script/transcript | Hook & Cold-Open Reviewer → Pacing & Retention Reviewer → Storytelling & Persuasion Psychologist → Platform Algorithm Strategist → Rewrite & Alternatives Strategist → Executive Editor-in-Chief |
| Thumbnail/image | Visual Composition Reviewer → Clickability & CTR Psychologist → Text & Branding Legibility Reviewer → Platform Fit Strategist → Alternative Concepts Strategist → Executive Editor-in-Chief |
| Blog/article/newsletter | Headline & Hook Reviewer → Structure & Readability Reviewer → SEO & Distribution Strategist → Value & Persuasion Reviewer → Rewrite & Alternatives Strategist → Executive Editor-in-Chief |

Every reviewer's system prompt is built at runtime from your selected content type, platform, goal, and criticality — nothing is precomputed.

---

## Technical notes

- **Model & endpoint**: calls `https://api.anthropic.com/v1/messages` with `model: "claude-sonnet-4-6"`, no API key handled client-side.
- **No JSON parsing.** Reviewers are instructed to respond in a plain-text `KEY: value` / `- list item` format with an `END` terminator. A small custom parser (`parseKV`) reads this format — this avoids the brittle JSON-parsing failures ("expected '{' or '('") that free-form model output can trigger.
- **Images** are sent as base64-encoded `image` content blocks alongside a `text` block, so Claude analyzes the actual pixels, not a description of them.
- **Retry logic**: each API call retries up to 3 times with backoff before surfacing an error; each pipeline stage also has its own manual "Retry stage" button in the UI.
- **State**: everything lives in an in-memory JS object for the session. Nothing is written to `localStorage`/`sessionStorage` — refreshing the page starts clean.
- **Styling**: CSS custom properties drive a dark/light theme toggle; all animation respects `prefers-reduced-motion`.

---

## Limitations

- **Predicted performance is explicitly an AI estimate**, not a guarantee — it's labeled as such in the UI and should be read as directional, not statistical.
- The app has no memory of past runs; each "Run analysis" is a fresh pipeline.
- Deeper-optimization follow-ups reference the current draft and its rewrite, not the full stage-by-stage review history (to keep those calls fast and focused).
