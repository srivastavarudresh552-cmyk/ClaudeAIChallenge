# 🏥 Prior Authorization Story Simulator

> An interactive, story-driven healthcare education simulator that walks you through the full US Prior Authorization (PA) process — told through a real patient's journey, with branching choices, animated chat bubbles, and educational context at every step.

---

## 📖 What Is This?

Most people have no idea what happens between a doctor writing a prescription and the medication actually arriving. This simulator makes that invisible process visible.

You follow **Rahul**, a 34-year-old patient just diagnosed with Rheumatoid Arthritis, as he navigates the Prior Authorization system with guidance from **Priya**, a Healthcare Operations Specialist. Across 8 scenes you'll experience intake, submission, denial, appeal, peer-to-peer review, and final approval — with educational callouts and real statistics woven into the story.

**Your choices matter.** Branching decisions let you skip ahead, explore side paths, or dig deeper into any topic. No two playthroughs are identical.

---

## ✨ Features

### 🎭 Story-Driven Format
- **8 fully scripted scenes** covering the complete PA lifecycle
- **Animated chat bubbles** with realistic typing indicators for each character
- **Branching choices** after every scene that influence narrative path
- All messages play sequentially — no content is skipped or truncated

### 👥 Characters
| Character | Role | Position |
|-----------|------|----------|
| 👦 **Rahul** | Patient — recently diagnosed with Rheumatoid Arthritis | Left bubbles |
| 👧 **Priya** | Healthcare Operations Specialist — guides Rahul (and you) | Right bubbles |
| 🩺 **Dr. Patel** | Prescribing physician | Centered italic amber card |
| ✦ **Narrator** | Scene-setting and transitions | Centered italic caption |

### 📊 Educational Content Types
Every scene uses purpose-built message formats:

| Type | Appearance | Used For |
|------|-----------|----------|
| Chat bubble | White (Rahul) / Blue (Priya) | Character dialogue |
| Narrator | Centered italic text | Scene setting, transitions |
| Doctor card | Amber-tinted italic card | Physician dialogue |
| Fact card | Blue-bordered callout | AMA statistics, citations |
| Flow diagram | Pill-chain card | Process visualization (e.g. Provider → Payer) |

### 🧭 Progress Tracking
- Sticky header with live progress bar
- Scene dots (1 per scene) that fill as you advance
- Scene counter (`Scene X of 8`) updates in real time

---

## 🗺️ The 8 Scenes

| # | Scene | What Happens |
|---|-------|-------------|
| 1 | 🏥 **Doctor Visit** | Rahul is diagnosed with RA. Dr. Patel prescribes Humira. PA is mentioned for the first time. |
| 2 | 📋 **Insurance Roadblock** | Provider submits PA directly to StarCare Health (payer). Flow: Provider → PA Request → Payer. Approved PA saved on file permanently. |
| 3 | 💡 **What is PA?** | Priya explains PA in plain language. Step therapy explained. AMA 2023 survey cited — PA delays affect majority of cases. |
| 4 | 🔬 **Insurance Review** | StarCare Health checks: eligibility, clinical documentation, ICD-10 diagnosis match, step therapy history. Each explained with real-world significance. |
| 5 | ❌ **Denial** | Denied for missing step therapy documentation. Priya clarifies: denial ≠ permanent. Cites 2+ staff hours per denial resolution. |
| 6 | ⚖️ **The Appeal** | Three documents assembled: clinical notes, step therapy justification, Letter of Medical Necessity. Peer-to-Peer review introduced. |
| 7 | ✅ **Approval** | PA approved, reference number issued (#PA-2024-00847). Permanent record. No repeat PA needed. Specialty pharmacy process explained. |
| 8 | 📖 **Takeaways** | Patient perspective (what Rahul learned) + System perspective (denial rate, appeal rate, resolution time, P2P utilization metrics). |

---

## 🎮 Branching Choices (Examples)

Choices are presented after each scene and change what content plays next:

- **Scene 1:** "What is PA exactly?" → jumps to Scene 3 (PA explainer) before Scene 2
- **Scene 2:** "Skip to the review process" → jumps directly to Scene 4
- **Scene 3:** "Walk me through the review" → goes to Scene 4; "What does StarCare actually check?" → goes to Scene 4 via a different path
- **Scenes 5–6:** Both denial choices lead to the appeal — but echo different patient emotional states
- **Scene 8:** Restart or mark complete



## 🏗️ Technical Architecture

### Stack
| Layer | Technology |
|-------|-----------|
| Markup | HTML5 semantic elements |
| Styling | Tailwind CSS CDN (structural utilities only) + hand-written CSS for all colors and animations |
| Logic | Vanilla JavaScript (ES6+) — no frameworks |
| Animations | Native CSS `@keyframes` — no libraries |

### Key Design Decisions

**Why inline styles instead of Tailwind custom tokens?**
Tailwind's CDN JIT cannot reliably resolve custom color tokens defined in a `tailwind.config` script block at runtime. All brand colors are applied as inline `style` attributes or dedicated CSS classes with hardcoded hex values. Tailwind CDN is used only for guaranteed base utilities (`flex`, `rounded`, `gap`, `overflow`, etc.).

**Why `createElement` + `appendChild` instead of `innerHTML`?**
The chat feed is append-only. Using `innerHTML =` on the container would destroy existing nodes, break scroll state, and cause animation restarts. Every bubble, card, and caption is constructed via the DOM API and appended — never re-rendered.

**Message queue pattern:**
```
scheduleNext()
  └─ setTimeout(delay)
       └─ playOneMessage()
            ├─ showTyping(id)      ← for rahul/priya only
            └─ setTimeout(typeDur)
                 └─ removeTyping(id)
                      └─ appendMessage()
                           └─ state.msgIndex++
                                └─ scheduleNext()   ← linear, not recursive
```
This guarantees sequential delivery with no stacking, no race conditions, and no frozen states.

## ✏️ Customizing the Story

### Adding a New Scene

Find the `SCENES` array near the top of the `<script>` block and add a new entry:

```javascript
{
  id: 9,
  title: 'Renewal',
  icon: '🔄',
  messages: [
    { type: 'narrator', text: 'Scene 9 · One year later. Rahul\'s PA is up for renewal.' },
    { type: 'priya',    text: 'Good news — renewals are much faster the second time. StarCare Health already has your clinical history on file.' },
    { type: 'rahul',    text: 'How long will it take?' },
    { type: 'fact',     text: '📊 PA renewal approvals average 2–3 business days vs 8–14 days for initial requests, when documentation is already on file.' },
  ],
  choices: [
    { label: '✅ Submit the renewal', next: 'next' },
    { label: '🔁 Start the story over', next: 'restart' },
  ],
},
```

## 🎓 Educational Citations

| Fact | Source |
|------|--------|
| PA causes treatment delays in the majority of cases | AMA 2023 Prior Authorization Survey |
| 1 in 4 physicians report a patient experienced a serious adverse event due to PA | AMA 2023 Prior Authorization Survey |
| PA denials cost physician offices 2+ staff hours to resolve | AMA Physician Practice Benchmark Survey, 2022 |
| P2P review success rates range 40–70% | Health Affairs / AMA PA Reform Research |
| Industry average denial rate: ~15–20% | AHIP / CAQH Benchmark Studies |

> **Note:** StarCare Health is used throughout as an illustrative fictional payer. All insurer names in this simulator are for educational purposes only.

<div align="center">

Built with HTML · Tailwind CSS CDN · Vanilla JavaScript

No frameworks · No build step · No backend · Open in browser and go.

</div>
