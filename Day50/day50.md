# Defend Your Experience

**A cross-examination simulator for your resume, project, performance review, or startup story.**

Most interview prep tools help you *say* your experience better. This one exists to find the parts of your story that won't survive contact with a skeptical technical interviewer — and helps you fix them before that happens.

> Paste in your resume, a project writeup, a performance review, or your startup story. Every meaningful claim gets pulled out as an **exhibit**. A rigorous-but-fair technical interviewer then cross-examines you on each one — pushing for specifics, numbers, and your actual individual contribution — with every answer shaping the next question. You leave with a Defense Report showing exactly what's bulletproof and what still needs work.

---

## Why this exists

Interview prep usually stops at "make the bullet point sound impressive." The real test happens when someone asks *"how, exactly?"* three times in a row. This tool simulates that moment, repeatedly, against your own material — not a generic question bank — so the first time you get pressed on a claim isn't in the actual interview.

## How it works

1. **Intake** — Paste or drop in your source material (resume, project README, performance review, startup narrative) and tag which category it is.
2. **Claim extraction** — The interviewer AI reads it and extracts up to 9 discrete, individually-defensible claims (achievements, metrics, technical decisions, outcomes) — skipping filler like contact info or soft-skill adjectives with nothing concrete behind them.
3. **Cross-examination** — One exhibit at a time, the interviewer asks a sharp opening question rooted in your own wording. Every answer is scored and generates a follow-up: vague or unquantified answers get pushed on harder; strong, specific answers get dug into one layer deeper. You can jump between exhibits at any time.
4. **Defense Report** — A closing case file: overall readiness score, category-by-category breakdown, your weakest exhibits with a concrete fix for each, your strongest stories to lead with, and a full ledger of every claim examined.

## Features

- **Adaptive interview engine** — no fixed question bank; every question is generated from your specific claim and your specific previous answer.
- **Three interviewer intensities** — Coaching (explains *why* each question matters), Rigorous but fair (the default — hard but gives room to recover), and Hostile / stress test (rapid-fire, no softening).
- **Live confidence gauge** — a courtroom-style meter tracking overall readiness as you go, plus a per-exhibit confidence bar in the sidebar.
- **Exhibit ledger** — every claim tracked individually with status (unexamined / weak / developing / defended), attempt count, and interviewer notes.
- **Defense Report** — category breakdown, weakest-exhibits-to-fix, strongest-stories-to-lead-with, and a full claim-by-claim ledger with specific next steps.
- **Case history** — sessions autosave to `localStorage`; resume an in-progress case or revisit a past report at any time.
- **Export** — download the full report as JSON, or print/save as PDF.
- **Graceful degradation** — automatic retry with backoff on rate limits or transient API errors, with a friendly in-transcript message rather than a hard failure.
- **Fully responsive**, drag-and-drop upload, keyboard-friendly (Enter to send, visible focus states), and respects `prefers-reduced-motion`.

## Tech stack

- Single self-contained `.html` file — no build step, no dependencies, no backend.
- Vanilla HTML, CSS, and JavaScript.
- [Anthropic Messages API](https://docs.claude.com/en/api/messages) (`claude-sonnet-4-6`) called directly from the browser for claim extraction, question generation, answer evaluation, and report synthesis.
- Google Fonts: [Fraunces](https://fonts.google.com/specimen/Fraunces) (display), [Inter](https://fonts.google.com/specimen/Inter) (body), [IBM Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Mono) (data/labels).
- `localStorage` for session persistence — nothing is sent anywhere except the interview content itself, to the Claude API.

## Design

Dark, glass-panel interface built around a **case file / dossier** metaphor: claims become numbered "exhibits," the interview reads like a transcript, and the ending is a "Defense Report" rather than a redlined resume. Signature elements are the semicircular confidence gauge (styled like a courtroom tension meter) and the redacted-line motif used in empty and loading states.

## Roadmap ideas

- Voice mode for spoken answers, to rehearse delivery as well as content.
- Multi-document intake (combine a resume + a linked project writeup into one case).
- Shareable, anonymized report links for mentors or peers to review.

---

Built as part of an ongoing series of polished, self-contained single-file HTML tools.
