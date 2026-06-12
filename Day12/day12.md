
# 🧰 Job Search & Personal Branding Toolkit

A fully interactive, AI-powered personal branding and job search toolkit — built as a single-page web artifact using the **Anthropic Claude API**. Designed and developed by **Rudresh Srivastava** as a practical demonstration of GenAI application development combined with frontend engineering.


---

## What It Does

This toolkit takes a candidate's resume and portfolio and generates a complete, ready-to-use job search kit — all rendered in a clean, tabbed interactive UI. No page reloads. No backend. Just the Claude API + vanilla JavaScript.

It produces **12 sections**, each copy-ready and personalised:

| # | Section | Description |
|---|---------|-------------|
| 1 | ATS-Friendly Cover Letter | 400-word, recruiter-optimised, customisable |
| 2 | Recruiter Outreach Email | Cold email with subject line and bullet highlights |
| 3 | Hiring Manager Email | Direct, results-focused outreach for startups |
| 4 | LinkedIn Connection Request | Under 300 characters, personalised |
| 5 | Referral Request Message | For reaching out to seniors or connections |
| 6 | Follow-Up Email | Day-5 follow-up if no response received |
| 7 | 30-Second Professional Intro | For interviews, events, and networking |
| 8 | Top 10 Job Titles | Ranked by profile fit with ATS keywords |
| 9 | Key Strengths | Differentiators recruiters will notice |
| 10 | Skill Gap Analysis | Current strengths, gaps, and 6-month roadmap |
| 11 | Personal Brand Summary | UVP, positioning statement, LinkedIn headline |
| 12 | Interview Talking Points | Best stories, achievement framing, prep questions |

---

## Tech Stack

- **Anthropic Claude API** (`claude-sonnet-4-6`) — generates all 12 sections from a structured prompt
- **Vanilla JS** — tab navigation, clipboard copy, dynamic rendering
- **CSS custom properties** — light/dark mode adaptive, zero external UI framework
- **Vercel** — deployed as a static artifact

---

## Features

- **One-click copy** on every section — paste directly into Gmail, LinkedIn, or a doc
- **Tabbed navigation** — jump between all 12 sections instantly
- **Fully responsive** — works on desktop and mobile
- **ATS-aware** — all content structured around recruiter and ATS scanning patterns
- **Personalised, not generic** — output is grounded in real resume data, not templates

---

## Project Highlights

- Integrated the Anthropic Messages API with a structured multi-section prompt to generate cohesive, non-repetitive output across 12 distinct content types
- Designed a custom tab UI from scratch — no Bootstrap, no Tailwind — using CSS variables for theming and `display` toggling for section switching
- Implemented async clipboard API with visual feedback (copy → "Copied!" state)
- Built entirely as a single HTML artifact — zero build step, zero dependencies, deployable anywhere

---

## What I Learned

- Prompt engineering for structured, role-aware output using the Claude API
- Handling multi-block API responses and assembling them into a clean UI
- Designing token-efficient prompts that produce consistent, recruiter-grade content
- Building interactive single-file HTML/CSS/JS apps without a framework

---

## About the Developer

**Rudresh Srivastava** — Frontend Developer, UI/UX Designer, and GenAI Builder.  
B.Tech CSE @ AKGEC, Ghaziabad (2024–28) | CGPA 8.66 | Designer @ Blockchain Research Lab

- 🌐 Portfolio: [my-portfolio-one-mocha-37.vercel.app](https://my-portfolio-one-mocha-37.vercel.app/)
- 💼 LinkedIn: [linkedin.com/in/rudresh-srivastava-76062537b](https://www.linkedin.com/in/rudresh-srivastava-76062537b)
- 📬 Email: srivastavarudresh552@gmail.com

---

## License

MIT — free to use, adapt, and build on.
