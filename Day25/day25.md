# 🦈 AI Shark Tank Simulator

<div align="center">


**Pitch your startup idea to 4 AI shark judges. Get real questions, brutal feedback, a funding decision, and your valuation — powered by Claude AI.**
</div>

---

## 📸 Preview

```
┌─────────────────────────────────────────────────────────┐
│  🦈 LIVE DEALS  NeuroCart INVESTED · $2.4M valuation…  │
├─────────────────────────────────────────────────────────┤
│                                                         │
│         SHARK TANK                                      │
│         SIMULATOR                                       │
│                                                         │
│   Pitches: 24   Funded: 11   Avg Score: 67             │
│                                                         │
│  [1 Pitch] ──── [2 Q&A] ──── [3 Score] ──── [4 Deal]  │
│                                                         │
│  ┌──────────────────────────────────────────────────┐  │
│  │  YOUR STARTUP PITCH                              │  │
│  │  Name · Problem · Solution · Revenue · Ask…      │  │
│  │                            [ 🦈 ENTER THE TANK ] │  │
│  └──────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────┘
```

---

## ✨ Features

### 🎯 Core Experience
- **6-field pitch form** — Name, Problem, Solution, Revenue Model, Target Audience, Funding Ask
- **4 distinct AI judges**, each with a unique personality and focus area
- **Live Q&A round** — each shark generates 2 sharp, context-aware questions
- **Dynamic reactions** — judges respond to your answers in real time
- **Animated scorecard** — 5 dimensions scored out of 100
- **Final investment decision** — INVEST / REJECT / ACQUIRE / COME BACK LATER

### 🦈 The Judges

| Judge | Role | Focus |
|-------|------|-------|
| 💼 Victoria Chen | Venture Capitalist | Market size & scalability |
| 🚀 Marcus Reid | Serial Founder | Execution & product roadmap |
| 👤 Priya Sharma | Customer Champion | Real user value & PMF |
| 👼 David Okafor | Angel Investor | Profitability & unit economics |

### 📊 Scoring System
- **Market Potential** — Is this a big enough market?
- **Innovation** — How differentiated is the solution?
- **Business Model** — Is the revenue model sound?
- **Execution** — Can this team actually ship?
- **Investment Worthiness** — Would a rational investor write a check?

### 🎁 Bonus Features
- 🎉 **Confetti burst** on INVEST or ACQUIRE decisions
- 📄 **Download Pitch Report** as a formatted `.txt` file
- 🏆 **Persistent Leaderboard** via `localStorage` — tracks top 10 pitches
- 🔗 **Share Result** — native share sheet or clipboard fallback
- 📡 **Live ticker** showing simulated deal feed
- 📈 **Stats bar** — total pitches, funded count, average score

---

## 🚀 Getting Started

### Option 1 — Just open the file
```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/ai-shark-tank-simulator.git

# Open directly in browser
open shark-tank-simulator.html
```
No install. No server. No dependencies to manage.

### Option 2 — Serve locally (optional)
```bash
# Using Python
python -m http.server 8000

# Using Node
npx serve .
```
Then visit `http://localhost:8000/shark-tank-simulator.html`

---

## 🔑 API Key Setup

This project uses the **Anthropic Claude API** for AI-powered judging. The API key is handled via the browser's request headers — no server required.

> **Note:** The app calls `https://api.anthropic.com/v1/messages` directly from the browser. For production use, proxy requests through a backend to keep your API key secure.

To use your own key, locate this section in the HTML and add your key:

```javascript
const res = await fetch('https://api.anthropic.com/v1/messages', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'x-api-key': 'YOUR_API_KEY_HERE',       // ← add this
    'anthropic-version': '2023-06-01'        // ← add this
  },
  ...
})
```

---

## 🗂 Project Structure

```
ai-shark-tank-simulator/
│
└── shark-tank-simulator.html     # Entire app — HTML + CSS + JS in one file
└── README.md
```

Everything lives in a **single self-contained HTML file**:
- Fonts loaded from Google Fonts CDN
- Confetti via `canvas-confetti` CDN
- Zero npm packages, zero build steps

---

## 🛠 Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML5, CSS3, JavaScript (ES6+) |
| AI Engine | Claude Sonnet (`claude-sonnet-4-6`) via Anthropic API |
| Fonts | Bebas Neue · Inter · JetBrains Mono (Google Fonts) |
| Animation | CSS keyframes + canvas-confetti |
| Storage | `localStorage` for leaderboard persistence |
| Build | None — zero toolchain |

---

## 📱 Responsive Design

Fully responsive across:
- 🖥 Desktop (960px max-width layout)
- 📱 Mobile (stacked grid, touch-friendly inputs)
- Dark theme only — designed for the tank aesthetic

---

## 🎨 Design System

```css
--bg:       #07080f   /* Deep space black     */
--cyan:     #00d4ff   /* VC blue (primary)     */
--mint:     #00e5a0   /* Customer green        */
--coral:    #ff6b6b   /* Founder red           */
--amber:    #ffb700   /* Angel gold            */
```

Typography: `Bebas Neue` for display headings, `Inter` for body, `JetBrains Mono` for data values.

---

## 🔄 App Flow

```
[Form Input]
     │
     ▼
[Pitch Summary + Judge Reveal]
     │
     ▼
[AI Q&A Round × 4 Judges × 2 Questions each]
     │  User types answers
     ▼
[Claude evaluates → Scorecard with animated bars]
     │
     ▼
[Final Decision: INVEST / REJECT / ACQUIRE / LATER]
     │
     ├─ 🎉 Confetti (if funded)
     ├─ 📄 Download Report
     ├─ 🔗 Share
     └─ 🏆 Leaderboard update
```

---

## 🤝 Contributing

Pull requests are welcome! Here are some ideas to extend the project:

- [ ] Add a 5th judge (Domain Expert / Industry Veteran)
- [ ] Support multi-round negotiation after initial offer
- [ ] Add voice input for pitch answers
- [ ] Export report as PDF (via jsPDF)
- [ ] Add more verdict types (Conditional Offer, Strategic Partnership)
- [ ] Backend leaderboard with user accounts

```bash
# Fork → Clone → Edit → PR
git checkout -b feature/your-feature-name
git commit -m "feat: add your feature"
git push origin feature/your-feature-name
```

---


<div align="center">

Built with ❤️ and a lot of shark energy.
If this helped you, drop a ⭐ — it means a lot!

</div>
