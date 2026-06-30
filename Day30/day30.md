# 📦 Supply Chain Builder

A single-file, interactive web app that teaches complete beginners how supply chains work by letting them build one for a randomly generated company — and see the business consequences of every decision in real time.

No installs. No backend. No build tools. Just open the HTML file and play.

---

## 🎯 What This App Does

Supply Chain Builder simulates the core decisions a real operations or supply chain manager has to make when running a physical product business. Before each decision, the app explains:

- **What** the concept means (in plain English, no jargon)
- **Why** it matters to a business
- **How** it trades off against cost, speed, risk, customer happiness, and sustainability

You then make a choice, watch live metrics update with animated progress bars, and finish with a full performance dashboard summarizing your strategy.

---

## 🕹️ How It Works

1. **Welcome Screen** — A friendly introduction to what a supply chain actually is.
2. **Random Company Generation** — Each playthrough generates a new company with:
   - A random industry & product (e.g. footwear, electronics, cosmetics)
   - A random set of countries it serves
   - A random demand pattern (Steady, Seasonal, Volatile, or Rapid Growth)
3. **Five Key Decisions** — Guided one at a time, each with a concept explainer and 2–4 options:
   - **Supplier Strategy** — Single, Dual, or Multiple suppliers
   - **Factory Location** — Domestic, Nearshore, or Offshore
   - **Warehouse Strategy** — Central, Regional, or Decentralized
   - **Transportation Method** — Road, Rail, Sea, or Air
   - **Inventory Strategy** — Low (Just-in-Time), Balanced, or High
4. **Live Metrics Panel** — Sticky dashboard showing 5 metrics that update after every choice:
   - 💰 Cost Efficiency
   - 🚚 Delivery Speed
   - 🛡️ Risk Resilience
   - 😊 Customer Satisfaction
   - 🌱 Sustainability
5. **Final Dashboard** — At the end, get:
   - An animated **Overall Score (0–100)**
   - Your top **Strengths** and **Weaknesses**
   - Your **Biggest Risk**
   - **Three practical, tailored improvements**
   - A full recap of every decision you made
6. **Replay** — One click regenerates a brand-new company and resets all metrics.

---

## 🧠 Why It's Useful

Every choice in the app is a genuine trade-off, just like in real business — there's no single "correct" path. For example:

- A **single supplier** is cheap and simple, but risky if they fail.
- **Air freight** is blazing fast but expensive and bad for sustainability.
- **High inventory** protects against stockouts but ties up cash and warehouse space.

This makes the app useful for:
- Students learning operations/supply chain management fundamentals
- Business or MBA-adjacent self-learners
- Anyone curious how companies like Nike or Amazon make logistics decisions
- Teachers looking for an interactive classroom demo

---

## 🛠️ Tech Stack

- **React 18** (via CDN, no npm install)
- **Babel Standalone** (in-browser JSX compilation)
- **Plain CSS** — dark, premium "enterprise dashboard" theme with rounded cards, hover states, and smooth animated transitions
- **Zero dependencies, zero build step** — it's a single `.html` file

No Tailwind, no APIs, no images, no external assets, no backend. Everything runs entirely client-side.

All state is managed with React's `useState`/`useEffect` — no external state libraries.

---

## 🎨 Design Highlights

- Dark, glassy "enterprise SaaS" aesthetic with gradient accents
- Sticky live metrics panel while making decisions
- Animated bar fills and score counter
- Hover-responsive option cards with selection states
- Fully responsive — works on mobile, tablet, and desktop
- Smooth fade/slide transitions between steps

---

## 🔁 Replaying

Every playthrough is randomized — different company, industry, product, countries, and demand pattern — so you can explore many different strategic scenarios just by clicking **"Build a New Supply Chain."**

---

## 📜 License

Free to use, modify, and distribute for educational or personal purposes.

## 🚀 Getting Started

1. Download `supply-chain-builder.html` (or whatever you've named the file).
2. Double-click it to open in any modern browser (Chrome, Edge, Firefox, Safari).
3. That's it — no server, no internet connection required after the initial CDN script load.

> **Note:** The app loads React, ReactDOM, and Babel from a CDN. You'll need an internet connection the *first* time you open it (or whenever your browser needs to re-fetch those scripts), but no backend, account, or installation is required.

---
