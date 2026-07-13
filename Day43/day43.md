# AI Workflow Architect

A single-file, self-contained web app that turns a fuzzy goal — "land a MERN developer job" — into a complete, stage-by-stage execution plan: objectives, tasks, AI tool picks, prompt templates, best practices, common mistakes, and time estimates for every step from skills audit to offer negotiation.

No backend, no build step, no dependencies. Open the HTML file and it runs.

## What it does

This build maps one specific workflow end to end: **Software Development → Full Stack → MERN Stack → Landing a developer job**. Rather than a generic checklist, each of the 9 stages is broken down into everything needed to actually execute it:

- Objectives and tasks (with progress tracking)
- The best AI tools for that stage, why they're recommended, and alternatives
- Ready-to-copy prompt examples
- Best practices and common mistakes
- Expected outputs and realistic time estimates
- Efficiency tips

It closes with a workflow summary, recommended AI stack, learning resources, communities, search keywords, bonus prompts, and future automation opportunities.

## Features

- **Interactive commit-graph navigation** — a git-branch-style timeline on the left lets you "check out" any stage; nodes fill in as you complete that stage's tasks
- **Progress tracking** — per-task checkboxes roll up into an overall completion percentage, persisted across sessions
- **Notes & bookmarks** — jot stage-specific notes and star stages to revisit, saved locally
- **Copyable prompts** — one-click copy on every AI prompt example
- **Interactive decision tree** — click-through guidance on which flagship project to build
- **Tool comparison table** — head-to-head view of ATS and mock-interview tools
- **Dark / light mode toggle**
- **Print-friendly stylesheet** — export a clean, distraction-free workflow guide
- **Fully responsive** — collapses to a horizontal branch scroller on mobile
- **100% local** — all state (progress, notes, bookmarks, theme) is stored in `localStorage`; nothing is sent to a server

## Tech stack

- HTML5
- CSS3 (custom properties for theming, no framework)
- Vanilla JavaScript (no libraries, no build tooling)

Everything lives in a single `.html` file — content is data-driven from a JS array of stage objects, so the whole workflow can be edited or extended without touching markup.

## Getting started

No installation required.

```bash
git clone https://github.com/your-username/ai-workflow-architect.git
cd ai-workflow-architect
open index.html   # or just double-click the file
```

Or deploy it anywhere that serves static files (GitHub Pages, Netlify, Vercel) — it's a single HTML file with no server-side requirements.


## Customizing for a different workflow

The whole workflow is defined in the `STAGES` array near the top of the `<script>` block, along with `STACK`, `RESOURCES`, `COMMUNITIES`, `KEYWORDS`, `BONUS_PROMPTS`, `AUTOMATION`, and `DTREE`. Swap that data for a different role or domain (e.g. Marketing → Instagram growth, or Frontend → React portfolio) and the same interface — commit graph, progress tracking, notes, bookmarks — renders it automatically.
