# Interactive Learning Studio — Arrays, Stacks & Queues

**"The Loading Dock"** — a single self-contained HTML tutorial that teaches Arrays, Stacks, and Queues end-to-end through a warehouse/loading-dock metaphor, with interactive visualizers, exercises, and auto-scored quizzes.

No build step, no dependencies, no internet connection required. Just open it in any modern browser (Chrome, Firefox, Safari, Edge).

## How to use it

1. Open the HTML file in a browser (double-click it, or drag it into a browser window).
2. Read the intro: learning objectives, estimated time, prerequisites, expected outcomes, and the badge-based reward system.
3. Work through **Bay 1 → Bay 4** in order. Each bay is a module and includes:
   - Explanations, analogies, and diagrams specific to that structure
   - A live, clickable visualizer (e.g. push/pop crates, enqueue/dequeue trucks)
   - A hands-on exercise with instant feedback
   - Common misconceptions and key takeaways
   - A 4-question quiz with instant scoring and explanations
4. Score the quiz to unlock the next bay — this is enforced in-page (the next module stays locked and greyed out until you finish the current quiz).
5. Finish at the **Manifest** section: a final Min-Stack design challenge, a cheat sheet, summary notes, and a curated list of books, docs, papers, communities, practice platforms, search keywords, and further AI prompts.

## Features

| Feature | Where |
|---|---|
| Progress bar | Top bar, updates as each bay/quiz is completed |
| Dark / light mode toggle | 🌙 / ☀️ icon, top right |
| Print / save notes | 🖨️ icon in the top bar, or the button at the bottom of the Manifest section (prints a clean, distraction-free version of the cheat sheet & notes) |
| Badges | Reward panel in the intro; badges light up as each bay's quiz is passed |
| Interactive visualizers | Array index explorer, stack simulator, queue simulator, two-stack-queue simulator — all built with plain HTML/CSS/JS, no libraries |
| Responsive layout | Works down to mobile widths |

## Notes on data & persistence

- All progress (quiz scores, unlocked bays, badges) is tracked in memory using JavaScript for the current browser session only.
- **Refreshing or closing the page resets progress.** This is intentional — the file has no external storage or server, so it works completely offline with zero setup.
- If you want persistent progress across sessions, you'd need to add your own storage layer (e.g. `localStorage`) outside of a Claude.ai artifact context, or host it as part of an app with a backend.

## Customizing or extending

The file is plain, well-commented HTML/CSS/JS — no frameworks, no build tools. To adapt it:

- **Content**: each module lives inside `<section class="module" id="module-N">`. Edit the explanation text, diagrams (inline SVG), exercises, and quiz questions/answers directly.
- **Quiz logic**: quiz buttons call `selectQuiz(this, moduleNum, qNum, selectedIdx, correctIdx)` — update the `correctIdx` argument if you change which option is correct.
- **Styling**: all colors, fonts, and spacing are defined as CSS variables at the top of the `<style>` block (`:root` for dark mode, `html[data-theme="light"]` for light mode) — change the palette in one place to re-theme the whole page.
- **Reusing the template for a different topic**: swap the analogy language ("bays," "crates," "trucks"), diagrams, code samples, and quiz content — the structural scaffolding (progress tracking, locking/unlocking, quiz engine, print styles) is topic-agnostic and can be reused as-is.
