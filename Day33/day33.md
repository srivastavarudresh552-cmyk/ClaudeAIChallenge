# The Integrity Review — Media Integrity Analyzer

An interactive, single-file web app that teaches media literacy through guided discovery instead of quizzing. Users read a fictional headline and a fictional social post, form their own instincts first, then compare those instincts to a structured analysis that reveals manipulation techniques, scores, and fair rewrites.

**Live concept:** *don't tell people media is manipulative — let them catch it happening in real time.*

---

## ✨ Features

- **Two guided challenges**
  - **Headline Detective** — reveals the gap between sensational headlines and the facts in their own articles
  - **Emotion Detector** — reveals how word choice and framing engineer a fast emotional reaction
- **Concept-first teaching** — every challenge opens with a plain-language explanation of *what* the concept is, *why* it matters, and *how* it shows up in everyday scrolling, before any interaction begins
- **Click-to-flag interactions** — tap suspicious phrases in a headline/article or emotionally loaded words in a post before seeing the answer
- **Rich reveals** per challenge, including:
  - An animated accuracy / manipulation score dial
  - Your personal detection score (based on what you flagged vs. what actually mattered)
  - Highlighted mismatches directly in the original text (correct catches, missed flags, false positives)
  - A plain-language explanation of what's actually going on
  - A fair, neutral rewrite of the headline or post
  - A one-line key takeaway
- **Live Media Integrity metrics sidebar** — four gauges (Headline Accuracy, Source Reliability, Emotional Manipulation, Audience Targeting) that unlock and animate as you complete each challenge
- **Final Media Integrity Dashboard**
  - Overall Media Integrity Score (animated dial)
  - Summary of what you learned this round
  - Your biggest red flag, calculated from the weakest metric
  - Three practical media literacy habits, presented as a tappable checklist
- **Replay with new scenarios** — cycles to a different headline/article and post each time, so the experience doesn't repeat
- **Premium editorial dark UI** — Midnight Blue theme, serif display headlines, smooth dial animations, hover states, sticky metrics panel, fully responsive down to mobile

---

## 🛠 Tech Stack

- **Pure HTML, CSS, and vanilla JavaScript** — no frameworks, no build step
- **Zero dependencies** — no npm, no CDNs, no external fonts, images, or API calls
- **Single file** — everything (markup, styles, logic, and content) lives in one `.html` file and runs entirely offline in any modern browser

This follows the same no-build, single-file pattern as the rest of this portfolio's interactive simulation apps — just without a React/Babel layer, since this project doesn't need component state complex enough to warrant it.

---

## 🚀 Running it

No install, no server, no build step required.

1. Download `media-integrity-analyzer.html`
2. Double-click it, or open it in any modern browser (Chrome, Firefox, Safari, Edge)

That's it — the whole app, including all scenario content, is bundled in that one file.

---

---

## 🎓 Design & Content Notes

- All headlines, articles, posts, outlets, and handles are **entirely fictional**, created for training purposes — no real people, publications, or events are referenced.
- Each challenge ships with **3 rotating scenario variants** so replaying the app surfaces fresh content rather than repeating the same example.
- Scoring logic:
  - **Headline Accuracy** and **Source Reliability** are fixed properties of each scenario (how misleading the headline/source actually is)
  - **Emotional Manipulation** and **Audience Targeting** are fixed properties of each post (how aggressively it's engineered to provoke a reaction)
  - **Your detection score** is calculated live from which phrases you flagged, rewarding correct catches and penalizing false positives
  - **Overall Media Integrity Score** blends all four metrics into one number, with manipulation/targeting inverted so a "cleaner" score always means healthier media

---

## 🔮 Possible Extensions

- Add a "share your score" summary card
- Track a running history across multiple replays
- Add a third challenge type (e.g. spotting manipulated statistics or charts)
- Add a light theme toggle alongside Midnight Blue

---

*Built as a single-file, offline-first interactive learning tool — part of an ongoing portfolio of no-dependency educational simulation apps.*
