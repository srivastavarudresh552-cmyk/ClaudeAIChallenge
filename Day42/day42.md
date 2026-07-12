# Personal Financial Command Center

A single-page financial dashboard built for a student managing an allowance, everyday expenses, and a savings goal. No installs, no accounts, no external services — it's one HTML file that runs entirely in your browser.


---

## Getting started

To make it yours, open the **Reset all data** button in the left sidebar, confirm, and start logging your own income and expenses. There's nothing to install and nothing to configure.

## What's inside

| Section | What it does |
|---|---|
| **Overview** | A stamp-style financial health score (0–100), key monthly stats, and a breakdown of where your money went this month |
| **Income** | Log allowance, gifts, scholarships, or part-time earnings as they come in |
| **Expenses** | Log spending by category — Food, Transport, Entertainment, Supplies, Other |
| **Budget** | Set a soft monthly limit per category; bars shift from jade → amber → coral as you approach and cross it |
| **Savings Goals** | Track one or more goals (an emergency fund by default) with a progress ring and a running contribution log |
| **Cash Flow** | A 6-month bar chart comparing income to expenses |
| **Insights** | Plain-language observations generated from your own numbers — savings rate, overspending, top category, projected time to goal |
| **What-If Lab** | Two sliders let you simulate cutting entertainment spend or adding extra monthly savings, and instantly see the new projected timeline to your goal |
| **Tips & Checklist** | A short habit checklist (saved as you check items off), quick money tips, and ready-to-copy prompts for asking Claude follow-up questions |
| **Reports** | A clean, printer-friendly monthly summary |

## How your data is stored

Everything is saved in your browser's **local storage**, tied to that specific browser on that specific device. This means:

- Your data is private — nothing is sent anywhere, and there's no server involved.
- It will persist between visits, as long as you open the file in the same browser and don't clear your browsing data.
- It will **not** sync across devices or browsers. If you switch computers or browsers, you'll start fresh there.
- Clearing your browser's site data/local storage, or using private/incognito mode, will reset the dashboard.

If you want a backup, use the **Print report** button and save it as a PDF — that gives you a portable snapshot outside the browser.

## The financial health score, explained

The score out of 100 is calculated from four things, recalculated live as you add entries:

- **Savings rate** (up to 40 pts) — the share of this month's income you haven't spent, scored against a 20% target
- **Budget adherence** (up to 30 pts) — how many of your budgeted categories you're staying within
- **Emergency fund progress** (up to 20 pts) — how close your goal balance is to its target
- **Spending diversity** (up to 10 pts) — a small penalty if one category eats more than 55% of your spending

It's meant as a directional signal, not a formal credit or financial rating.

## Customizing it

Because it's a single plain HTML/CSS/JavaScript file, you (or Claude) can edit it directly:

- **Add/remove expense or income categories** — edit the `<select>` options in the Income and Expenses forms, and add matching entries to the `budgets` object in the seed data.
- **Change the currency** — update the `CURRENCY` constant near the top of the `<script>` block.
- **Adjust the health score weighting** — edit the `computeHealthScore()` function.
- **Retheme it** — colors are defined as CSS variables at the top of the `<style>` block, for both light and dark mode.

## Notes and limits

- Built with plain HTML, CSS, and JavaScript only — no external libraries, frameworks, or network requests.
- Works offline once downloaded.
- This is a personal budgeting tool, not financial, tax, or investment advice.
