# 🧩 Prompt Puzzle — Master AI Prompting Through Play

An interactive, single-file HTML game that teaches the fundamentals of AI prompt engineering through hands-on puzzles. No installs, no dependencies, no backend — just open the file and play.

---

## 📖 Overview

**Prompt Puzzle** turns the abstract skill of "writing a good prompt" into a concrete, gamified experience. Instead of reading about prompt engineering, players *build*, *clean*, and *choose* their way through real developer scenarios — learning by doing, with immediate feedback comparing weak vs. optimized prompts and their resulting AI outputs.

The entire application — markup, styling, game logic, and scenario data — lives in **one HTML file** with zero external dependencies, so it runs entirely offline in any modern browser.

---

## 🎮 How to Play

Open `prompt-puzzle.html` in your browser and work through 7 randomized software-development scenarios, each presented as one of three challenge types:

| Challenge | Description |
|---|---|
| 🧱 **Build the Prompt** | Drag (or click) the correct instruction blocks into the right sequence, while ignoring distractor blocks that would weaken or bloat the prompt. |
| 🧹 **Clean the Prompt** | Given an over-engineered prompt, click the unnecessary segments to strip them out, keeping only what's essential. |
| 🎯 **Choose the Best Prompt** | Pick the most effective prompt from three options: a weak one, an optimized one, and an over-engineered one. |

After each scenario, you'll see:
- The **Weak Prompt** vs. the **Optimized Prompt**
- The **Weak AI Output** vs. the **Optimized AI Output**
- The underlying **Prompt Principle** being taught (e.g. Role Assignment, Scope Definition, Eliminating Scope Creep)

---

## 🏆 Scoring & Performance Report

Live stats are tracked throughout play:

- **Accuracy** — percentage of scenarios solved correctly
- **Time** — seconds spent per scenario
- **Moves** — total interactions made
- **Wrong Placements** — incorrect blocks, marks, or choices
- **Hints Used** — number of hints requested
- **Optimization Bonus** — awarded for solving a scenario with zero errors and zero hints

At the end of the run, a **Prompt Performance Report** is generated, including:

- 🎯 **Prompt Score** (0–100) and **Rank** (D → S) with a matching **Rating** (e.g. Prompt Novice → Prompt Architect)
- 🧬 **Prompt DNA** — a radar-style breakdown across five traits: Clarity, Specificity, Structure, Constraints, and Efficiency
- 💬 **Personalized feedback** highlighting your strongest trait and biggest growth area
- 🚩 **Next Milestone** — a suggested goal for improvement or progression to Advanced difficulty
- 🏁 **Final Optimized Prompt** — your best-scoring scenario's ideal prompt, shown as a takeaway example

Replay anytime to get a freshly randomized and reshuffled set of scenarios.

---

## 🗂️ Scenarios Included (Software Development & Coding · Intermediate)

1. Email Validation Function (Build)
2. Optimize a JavaScript Loop (Clean)
3. Unit Tests for a REST API Endpoint (Choose)
4. SQL Query Optimization Explanation (Build)
5. React Contact Form Component (Clean)
6. Debugging a Java NullPointerException (Choose)
7. E-commerce Database Schema Design (Build)

Each scenario is stored as a self-contained JavaScript object (`SCENARIO_BANK`) with its desired output, correct/distractor blocks, weak/optimized/over-engineered prompts, corresponding AI outputs, and the prompt-engineering principle it teaches — making it easy to extend with new domains or difficulty levels.

---

## 🛠️ Tech Stack

- **Pure HTML, CSS, and vanilla JavaScript** — no frameworks, no build step, no CDN calls
- Native HTML5 Drag-and-Drop API for the "Build the Prompt" challenge
- CSS animations and transitions for score pop-ups, progress dots, DNA bars, and floating toast notifications
- Fully responsive layout for desktop and mobile

---

## 🚀 Getting Started

### Option 1 — Run locally (offline)
1. Download `prompt-puzzle.html`
2. Double-click it — it opens directly in your default browser
3. No server, no internet connection, and no build tools required

### Option 2 — Host it as a live website (GitHub Pages)
1. Create a new GitHub repository (e.g. `prompt-puzzle`)
2. Upload the file and rename it to `index.html`
3. Go to **Settings → Pages → Deploy from branch → main → / (root)** → Save
4. Your app will be live at:
   `https://<your-username>.github.io/prompt-puzzle/`

---

## 📌 Roadmap Ideas

- [ ] Additional domains: Marketing & Copywriting, Data Analysis & Business, Creative Writing, Education & Research
- [ ] Additional difficulty tiers: Beginner, Advanced, Expert
- [ ] Persistent leaderboard / local score history
- [ ] Downloadable/shareable Prompt Performance Report as an image or PDF
- [ ] Sound effects and richer micro-interactions

---

## 📄 License

This project is free to use, modify, and extend for educational or portfolio purposes.

---

*Built as part of an ongoing series of single-file, no-dependency educational simulation apps focused on making complex skills accessible through interactive play.*
