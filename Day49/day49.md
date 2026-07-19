# Personal AI Playbook

A single-file, no-dependency web app for building and reusing AI prompts — instead of re-typing the same context and requirements every time you open a chat.

## What it does

Most AI conversations start the same way — re-explaining your stack, your project, and your constraints before you even get to the actual question. This playbook turns that repeated setup into reusable, structured components:

- **Workflows** — a searchable library of ready-made prompt templates organized by task (coding & debugging, documentation, deployment, startup research). Fill in a few fields, copy the finished prompt.
- **Prompt Builder** — assembles a custom prompt from modular blocks (role, objective, context, constraints, reasoning strategy, output format, tone, examples, quality checks), with a live preview as you build.
- **Loop Builder** — wraps any prompt into a self-checking loop, telling the AI to evaluate its own output against your criteria and keep improving until a stop condition is met.
- **Your own workflows** — create, edit, duplicate, favorite, search, and filter custom workflows, all saved to `localStorage`.

## Features

- Fully self-contained — one HTML file, zero external libraries, zero build step
- Modular prompt system: mix and match building blocks instead of storing hundreds of static prompts
- Dropdown-driven inputs throughout, so most fields are pick-not-type
- Dark mode by default, with a light mode toggle
- Persistent, dismissible in-app explainer plus an always-available "What is this?" help button
- Keyboard shortcuts (`1`–`5` to navigate, `/` to search, `?` for help, `Esc` to close)
- Import/export all data as JSON for backup or moving between devices
- Responsive layout with a mobile tab bar

## Tech stack

HTML, CSS, and vanilla JavaScript only. No frameworks, no build tools, no external runtime dependencies. All data is stored locally in the browser via `localStorage` — nothing is sent to a server.

## Run locally

No installation needed.

```bash
git clone https://github.com/srivastavarudresh552-cmyk/personal-ai-playbook.git
cd personal-ai-playbook
open personal-ai-playbook.html   # or just double-click the file
```

## Deploy to GitHub Pages

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set the source branch to `main` and the folder to `/ (root)`
4. Rename the file to `index.html` (or point Pages at it directly) so it loads at the repo's Pages URL

## License

MIT — free to use, modify, and share.
