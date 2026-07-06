# Cognitive Pattern Explorer

A calm, single-file web app that explores how your mind tends to move through everyday decisions — not a test, not a diagnosis, just a gentle mirror for thinking patterns.

Built as a self-reflection experience across three short chapters: pick your way through relatable scenarios, rank your priorities, and sequence your natural problem-solving instincts. At the end, you get a personalized "thinking constellation" and a percentage breakdown across five reflective thinking styles.

> **Note:** This is an educational, self-reflection tool only. It does not diagnose, assess, or clinically evaluate mental health in any way.

---

## ✨ Features

- **Three-chapter flow** — scenario-based multiple choice, draggable priority ranking, and a draggable "thinking timeline"
- **Five thinking-style dimensions** — Analytical Thinker, Emotional Intuitive, Overthinking Loop Style, Action-First Decision Maker, Balanced Reflective Thinker
- **Calm / Stress mode** — pick your pace before you start; affects ambient motion and framing
- **Custom drag-and-drop** — a single reusable sortable component (Pointer Events) powers both the priority cards and the timeline, with full keyboard support (grab, arrow to move, drop, escape to cancel)
- **Personalized final reflection** — an animated "orbit" constellation visualization plus a percentage breakdown and reflective, non-clinical insights ("you often...", "this suggests...")
- **Optional journal** — write your own reflection, saved locally on your device only
- **Fully offline** — zero external requests, zero dependencies, zero build step
- **Accessible & responsive** — keyboard-navigable throughout, respects `prefers-reduced-motion`, works down to mobile widths

---

## 🧠 The Five Thinking Styles

| Style | What it tends to look like |
|---|---|
| **Analytical Thinker** | Breaks things into parts, weighs evidence, looks for the clearest path through |
| **Emotional Intuitive** | Lets feeling arrive first and treats it as real information |
| **Overthinking Loop Style** | Returns to the same thought from a few angles before it can rest |
| **Action-First Decision Maker** | Moves before every detail is settled, learns through motion |
| **Balanced Reflective Thinker** | Lets logic and feeling sit together before choosing |

---

## 🛠️ Tech Stack

- **HTML5** — single file, semantic structure
- **CSS3** — custom properties, keyframe animations, responsive layout, `prefers-reduced-motion` support
- **Vanilla JavaScript** — no frameworks, no build tools, no CDN calls
- **Pointer Events API** — unified drag-and-drop across mouse, touch, and pen
- **localStorage** — optional, best-effort persistence for the journal entry only

No npm, no bundler, no server. Just one `.html` file.

---

## 🚀 Getting Started

1. Download `cognitive-pattern-explorer.html`
2. Open it directly in any modern browser (double-click, or drag into a browser tab)

That's it — the entire app, including all styles and logic, lives in that one file and works completely offline.

### Deploying to GitHub Pages

1. Push the file to a repository
2. Rename it to `index.html` (or point Pages at the file directly)
3. Enable GitHub Pages in **Settings → Pages** for the branch/folder containing it

---

---


<!--
Once pushed to GitHub, replace the placeholders above with raw URLs, e.g.:
![Final Reflection](https://raw.githubusercontent.com/srivastavarudresh552-cmyk/<repo-name>/main/screenshots/final-reflection.png)
-->

---

## ⚖️ Disclaimer

Cognitive Pattern Explorer is an educational and reflective tool. It is **not** a psychological test, screening instrument, or clinical assessment, and it should not be used to diagnose or evaluate any mental health condition. Results are meant as a light, exploratory mirror — patterns shift with mood, context, and season of life.

---

## 📄 License

Free to use, modify, and share for personal or educational purposes.
