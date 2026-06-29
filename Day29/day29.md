# 🚨 Operation Lifeline: Supply Chain Crisis Lab

> *Step into the shoes of a Chief Supply Chain Officer. Navigate real-world crises, negotiate with suppliers, and make million-dollar decisions — with every choice explained so you understand exactly what you're learning.*

An interactive, gamified **supply chain education simulator**. Every playthrough procedurally generates a unique company, crisis, and scenario chain — no two runs are the same.

---

## ✨ Features

- 🏭 **Run a real company** — randomly generated business profile with realistic operational metrics
- ⚡ **Face a live crisis** — dynamic crisis scenarios (e.g. ransomware attacks, supplier failures)
- 🤝 **Negotiate suppliers** — multi-round, stat-driven negotiation system
- 🧠 **Test CEO thinking** — leadership decision scenarios scored for executive judgment
- 🤖 **Invest in AI** — strategic AI capability allocation with ROI trade-offs
- 📊 **Score your performance** — full breakdown report with letter grade at the end

---

## 🕹️ How It Works

The simulation runs through **7 sequential phases**, tracked by a progress stepper at the top of the screen:

### 1️⃣ Your Company
You're shown the company you're running for this session (e.g. *Stratek Industries*, an Industrial Machinery firm). Stats include industry, annual revenue & margin, factory/warehouse count, number of active suppliers, inventory days on hand, supplier lead time, and sourcing countries — plus a "Why This Matters" explainer connecting these numbers to the decisions ahead.

### 2️⃣ Crisis Detected
A randomized crisis brief drops (e.g. a **Ransomware Cyberattack** encrypting the ERP and warehouse systems). Includes business impact, contextual background ("What You Should Know"), and your starting position across 5 operational metrics:
- 💰 Cost Pressure (lower is better)
- 📦 Inventory Health
- ✅ Profit Margin
- 🚚 Delivery Speed
- 😊 Customer Satisfaction

### 3️⃣ Choose Your Actions
Pick **exactly 3 of 6** response actions (e.g. *Flex Manufacturing Network*, *Activate Backup Supplier*, *Pause New Promotions*, *Proactive Customer Comms*, *Deploy Crisis War Room*, *Prioritize Key Customers*). Each card shows a "Why This Matters" rationale and concrete stat deltas (cost / inventory / profit / delivery / satisfaction), so trade-offs are explicit before you commit. Submitting recalculates all 5 operational metrics live and shows a consequence breakdown per action.

### 4️⃣ Boardroom Negotiation
A **4-round negotiation** with a backup supplier. Tracks three live counters:
- **Trust Score** (long-term willingness to work with you)
- **Price Premium** (cost per unit vs. market)
- **Lead Time** (delivery speed)

Each round presents a situation (e.g. a price standoff) and 4 strategic responses (Accept / Volume Deal / Audit / Compete), each with different trust/price/lead-time consequences. Ends with a Negotiation Score (0–100), a recap of your decisions, and an "Expert Insight" explaining what good negotiators optimize for.

### 5️⃣ Executive Decision-Making (CEO Boardroom)
**5 leadership scenarios** testing judgment under pressure (e.g. *"Your CFO says the crisis will cost $40M more than budgeted. What do you do?"*). Each has a "Why This Matters" framing and 4 response styles (Decisive / Cautious / Delay / Reallocate). Ends with a Leadership Score (0–100) and a qualitative label like *"Executive-level thinking."*

### 6️⃣ AI Strategy Investment
Choose **2 of 5** AI capability investments (Demand Forecasting AI, Inventory Optimization, Supplier Risk Monitor, Warehouse Vision AI, Procurement Copilot). Each card shows what it does, projected ROI timeline, and quantified upside (e.g. inventory reduction %, fill rate improvement). These don't fix the current crisis — they reduce the blast radius of the *next* one.

### 7️⃣ Crisis Performance Report
The final scorecard. An overall **letter grade + numeric score** (e.g. **A — 84/100**) summarizing the full run, broken down into:
- 🛡️ Supply Chain Resilience
- 💰 Cost Control
- ⚠️ Risk Management
- 😊 Customer Satisfaction
- 🤝 Negotiation Skill
- 🎯 Leadership Quality

---

## 🎨 Design

- Dark, "command-center" UI theme with cyan/blue/purple accent gradients
- Numbered step progress indicator (1–7) with checkmarks for completed phases
- Color-coded stat deltas (green = positive, red = negative) on every decision card
- Circular progress rings for scores (negotiation score, leadership score, overall grade)
- Horizontal bar meters for operational health metrics

## 🧱 Tech Stack

Built as a self-contained, single-file web app (HTML/CSS/JS) with no external dependencies — consistent with a fully client-side, procedurally generated simulation. *(Update this section with your actual stack/file structure if it differs.)*

## 📸 Screenshots

| | |
|---|---|
| **Landing Page**<br>![Landing Page]()![Uploading 01-landing-page.png…]()
) | **Phase 1 — Your Company**<br>![Your Company](screenshots/02-your-company.png) |
| **Phase 2 — Crisis Detected**<br>![Crisis Detected](screenshots/03-crisis-detected.png) | **Phase 3 — Choose Your Actions**<br>![Choose Your Actions](screenshots/04-choose-actions.png) |
| **Phase 3 — Updated Metrics**<br>![Updated Metrics](screenshots/05-updated-metrics.png) | **Phase 4 — Boardroom Negotiation**<br>![Boardroom Negotiation](screenshots/06-boardroom-negotiation.png) |
| **Phase 4 — Negotiation Complete**<br>![Negotiation Complete](screenshots/07-negotiation-complete.png) | **Phase 5 — Executive Decision-Making**<br>![Executive Decision-Making](screenshots/08-executive-decision.png) |
| **Phase 5 — Leadership Score**<br>![Leadership Score](screenshots/09-leadership-score.png) | **Phase 6 — AI Strategy Investment**<br>![AI Investment](screenshots/10-ai-investment.png) |
| **Phase 7 — Final Crisis Performance Report**<br>![Final Report](screenshots/11-final-report.png) | |

---

## 🚀 Getting Started

1. Clone or download this repo
2. Open the `.html` file directly in any modern browser — no build step or server required
3. Click **Start Simulation** and play through all 7 phases

## 📌 Notes

- Every session generates a new company profile, crisis type, and scenario branch — replay value is built in.
- Designed as an educational tool: every choice surfaces a "Why This Matters" explanation so the *reasoning* behind supply chain trade-offs is visible, not just the outcome.

---

*Built for learning real-world supply chain management, crisis response, negotiation, and executive decision-making through play.*
