# ⚽ Football Intelligence Hub

A three-stage interactive experience that combines **World Cup 2026 data analysis**, **football knowledge testing**, and **personality profiling** — all powered by a structured Excel workbook and rendered as a rich interactive widget.

Built as a Claude AI artifact using the Anthropic API + custom HTML/JS widgets.

---

## What it does

The hub guides users through three sequential stages, adapting depth and language to their self-reported football knowledge level:

| Stage | Name | Output |
|-------|------|--------|
| 0 | Knowledge level check | Calibrates all explanations to the user |
| 1 | World Cup 2026 Prediction Report | Winner, runner-up, dark horse, players to watch |
| 2 | Football IQ Quiz | Football Awareness Score + fan classification |
| 3 | Messi vs Ronaldo Personality Match | Compatibility %, archetype, recommendations |
| Final | Football Intelligence Profile | Complete combined report |

---

## Data source

All analysis is grounded in **`ABTalks_WorldCup_Intelligence_Master.xlsx`**, which contains:

- **Table 1** — Historical performance of 10 top nations (50-match records, win %, goals for/against)
- **Table 2** — Last 5 FIFA World Cup results (winners, Golden Ball, Golden Boot)
- **Table 3** — Current contender form scores (FIFA rank, recent W/D/L, goals, 0–100 form score)
- **Table 4** — Star player ratings (goals, assists, overall rating out of 100)
- **Table 5** — User Football Awareness input schema (1–5 self-scoring)
- **Table 6** — Messi vs Ronaldo personality trait input schema (1–5 scoring)
- **Table 7** — Live 2026 World Cup group stage data (21 matches, all group standings as of June 17, 2026)

---

## Stage breakdown

### Stage 0 — Knowledge level check
Users self-select from four levels:
- Complete beginner
- Casual viewer
- Football follower
- Football expert (actively follows tournaments)

This single input gates all subsequent explanation depth, terminology, and example choices throughout the experience.

---

### Stage 1 — World Cup 2026 Prediction Report

Analyses Tables 1, 3, 4, and 7 together to produce:

**Predictions with confidence scores:**
- 🥇 Most likely winner — Argentina (72%)
- 🥈 Predicted runner-up — France (65%)
- 🌟 Dark horse — Morocco (38%)

**Evidence factors used per prediction:**
- FIFA ranking (Table 3)
- Historical win % over 50 matches (Table 1)
- Current form score 0–100 (Table 3)
- Live 2026 group stage results (Table 7)
- Star player ratings (Table 4)

**Output also includes:**
- Key risks working against each prediction
- Players to watch with ratings and stats
- Live group stage results summary
- Form score comparison across top 4 contenders

---

### Stage 2 — Football IQ Quiz

Five questions spanning three difficulty levels, drawn directly from workbook data:

| # | Difficulty | Topic |
|---|-----------|-------|
| 1 | Beginner | Basic rules (players per team) |
| 2 | Beginner | All-time World Cup records (Table 2) |
| 3 | Intermediate | 2022 Golden Ball winner (Table 2) |
| 4 | Intermediate | Live 2026 highest-scoring match (Table 7) |
| 5 | Advanced | Morocco's historic 2022 achievement |

**Scoring formula:**
- Advanced questions weighted ×2
- Intermediate questions weighted ×1.5
- Beginner questions weighted ×1
- Normalised to a 0–100 Football Awareness Score

**Fan classification tiers:**
| Score | Classification |
|-------|---------------|
| 0–20 | Beginner Fan |
| 21–40 | Casual Viewer |
| 41–65 | Football Follower |
| 66–85 | Football Enthusiast |
| 86–100 | Football Expert |

Output also highlights strongest knowledge area, weakest area, and key gaps.

---

### Stage 3 — Messi vs Ronaldo Personality Match

A 12-question quiz assessing ten traits from Table 6, using a mix of:
- Multiple-choice questions (scored 1–4)
- Rating scale questions (scored 1–5)

**Traits assessed:**
Ambition · Work ethic · Leadership · Creativity · Competitiveness · Teamwork · Confidence · Risk taking · Learning style · Discipline · Decision making · Legacy

**How compatibility is calculated:**

Messi's profile weights: creativity, teamwork, quiet ambition, instinctive decision-making, internal motivation, collective legacy.

Ronaldo's profile weights: public ambition, competitiveness, explicit leadership, risk-taking, record-breaking legacy, high confidence.

Each answer is mapped to how closely it mirrors each legend's known traits. Scores are normalised to percentages.

**Output includes:**
- Messi % and Ronaldo % compatibility with reasoning
- Primary legend match (higher %)
- One of eight personality archetypes:
  - Creative Playmaker
  - Relentless Competitor
  - Tactical Visionary
  - Quiet Leader
  - Fearless Attacker
  - Strategic Commander
  - Consistent Performer
  - Big-Match Specialist
- Archetype description and key traits
- Recommended player, club, national team, and rivalry to explore

---

### Final — Football Intelligence Profile

A single consolidated card combining all outputs:

- World Cup 2026 prediction summary
- Football Awareness Score + classification
- Strongest and weakest knowledge areas
- Messi / Ronaldo compatibility percentages
- Personality archetype + key traits
- Recommended player / club / national team / rivalry
- Key insights (superpower, builder vs showman, growth area)

---

## How it's built

| Layer | Tech |
|-------|------|
| Data | Excel workbook (7 structured tables) |
| AI analysis | Claude Sonnet (Anthropic API) |
| UI | Inline HTML + CSS + vanilla JS widgets |
| Interactivity | `sendPrompt()` — widget buttons trigger Claude responses |
| Styling | Claude.ai CSS variables (light/dark mode adaptive) |
| Icons | Tabler outline icon font |

All widgets are self-contained single-file HTML fragments. No external dependencies beyond the Tabler icon CDN. No localStorage — all state lives in memory during the session.

---

## Example output (sample profile)

```
Football Awareness Score:   62 / 100
Fan Classification:         Football Follower
Strongest knowledge area:   Current 2026 events (90%)
Key knowledge gap:          Basic rules & historical records

Messi compatibility:        71% — Primary match
Ronaldo compatibility:      54% — Secondary match
Personality archetype:      Tactical Visionary
Signature traits:           Discipline · Work ethic · Team-first

WC 2026 predicted winner:   Argentina (72% confidence)
Recommended player:         Luka Modrić
Recommended club:           Manchester City
Recommended national team:  Spain
Recommended rivalry:        Messi vs Ronaldo
```

---

## File structure

```
/
├── ABTalks_WorldCup_Intelligence_Master.xlsx   ← primary data source
└── README.md                                   ← this file
└── Screenshots
```

---

## Usage

1. Upload `ABTalks_WorldCup_Intelligence_Master.xlsx` to a Claude conversation
2. Paste the Football Intelligence Hub system prompt
3. Claude launches Stage 0 automatically — select your knowledge level
4. Progress through all three stages interactively
5. Receive your complete Football Intelligence Profile at the end

---

## Data notes

- Live match data covers **21 group stage matches** played up to **June 17, 2026**
- Historical performance data covers the **50 matches before the last World Cup** for each nation
- Form scores (0–100) combine recent wins, draws, losses, goals scored, and goals conceded
- Player ratings are out of 100 and reflect current season performance

---

*Built with ❤️ · Data from ABTalks World Cup Intelligence workbook · Live results as of June 17, 2026*
