# ⌨️ Typing Speed Studio

A premium, single-file typing speed platform with live analytics, adaptive difficulty, and Monkeytype-style performance dashboards — built entirely in vanilla HTML, CSS, and JavaScript. No frameworks, no build step, no dependencies.
---

## ✨ Overview

Typing Speed Studio turns typing practice into a full commercial-grade experience: multiple test modes, seven content categories with dynamically generated passages, real-time stats while you type, and a rich analytics dashboard after every session — all running client-side in a single HTML file.

## 🚀 Getting Started

No installation, server, or build process required.

1. Download `typing-speed-studio.html`
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge)
3. Start typing

That's it. All progress, personal bests, and history are saved locally in your browser via `localStorage` — nothing is sent anywhere.

## 🎮 Modes

| Mode | Description |
|---|---|
| **Time** | Race the clock — 15, 30, 60, or 120 second sessions |
| **Words** | Fixed-length sessions — 25, 50, 100, or 250 words |
| **Quote** | Type curated aphorisms, one at a time |
| **Programming** | Real code snippets in HTML, CSS, JavaScript, Python, Java, C++, and SQL |
| **Custom** | Paste in your own text and practice with it |
| **Adaptive** | Difficulty escalates or eases automatically based on your live accuracy and streak |
| **Zen** | Untimed, distraction-free practice with no pressure |

**Focus Mode** (toggle) narrows the display to a scrolling single line so only the words directly ahead of your cursor are visible.

## 🗂️ Categories

Switch freely between **General English, Academic, Business, Medical, Legal, Creative Writing,** and **Programming** — each with its own vocabulary bank, so passages are generated fresh every run instead of reusing the same paragraph.

## 📊 Live Stats

While typing, the dashboard tracks in real time:

- WPM & Raw WPM
- CPM (characters per minute) 
- Accuracy
- Elapsed / remaining time
- Mistake count
- Current streak
- Completion progress bar

Characters are highlighted live as correct, incorrect, or extra, with a smooth animated caret.

## 📈 Post-Session Analytics

Every completed session unlocks a full results dashboard:

- WPM & accuracy graph over the course of the session
- Consistency score
- Estimated percentile
- Character breakdown — correct, incorrect, extra, missed
- Mistyped-key keyboard heatmap
- Written performance summary with strengths, weaknesses, and personalized suggestions
- Achievement badges (14 unlockable achievements)
- Personal best tracking per mode/category/length combination
- Full session history table

## 💾 Data & Privacy

All data — history, personal bests, achievements, and preferences — is stored locally in your browser via `localStorage`. Nothing is transmitted externally, and no account is required. Clearing your browser data will reset your progress.

## ⚙️ Customization

- **Themes:** light/dark mode plus 4 accent color palettes
- **Font size:** adjustable typing stage text size
- **Sound:** optional WebAudio click feedback for correct/incorrect keystrokes (no audio files)
- **Accessibility:** visible focus states, `prefers-reduced-motion` support, responsive layout down to mobile

## ⌨️ Keyboard Shortcuts

| Key | Action |
|---|---|
| `Esc` | Pause / resume the session |
| `Tab` | Restart with a fresh passage |
| `Space` / `Enter` | Confirm the current word |
| `Backspace` | Correct the current word |

## 🛠️ Tech Stack

- Plain HTML5, CSS3, and JavaScript (ES6+)
- No external libraries, fonts, or CDNs
- Web Audio API for sound effects
- SVG for the WPM/accuracy chart
- `localStorage` for persistence

## 📁 Project Structure

This is intentionally a **single self-contained file**:


## 🤝 Contributing

This is a self-contained learning/portfolio project. Feel free to fork it, tweak the word banks, add new categories or languages, or restyle the theme to make it your own.

## 📄 License

Free to use, modify, and distribute.
