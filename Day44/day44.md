# LinkedIn Profile Audit — Interactive Report

A single-file, self-contained HTML tool that audits a LinkedIn profile against real recruiter-search and readability standards, then rebuilds every section with an explanation of the strategy behind each change. Built as a git-diff-styled report: a dark editor theme with red/green diff blocks showing exactly what changed and why.

---

## What it does

1. **Roasts** the profile section by section — Headline, About (hook + full), Experience, Skills/Keywords — with a score out of 10, the recruiter's real 3-second reaction, and the invisible cost of leaving it as-is.
2. **Rebuilds** every section:
   - 3 headline options (keyword-optimized, value-proposition, authority) with guidance on when to use each
   - A full About section rewrite (Hook → Story → Proof → CTA) with embedded SEO keywords called out explicitly
   - Experience bullets rewritten as before/after diffs, following the lead-with-achievement / strong-verb / add-numbers rules
   - A prioritized skills list: what to add, what to remove, what to pin
3. **Scores before vs. after** in a single table, section by section and overall.
4. **Lays out a 7-day activation plan** — not just profile edits, but actual actions (post drafts, connection templates, a "value comment" formula, and what to check on Day 7).
5. **Generates a shareable summary card** — screenshot-ready, with before/after scores and top mistakes.

## Why it's built this way

- **No invented achievements.** Every claim in the roast is pulled directly from the actual profile content. Where a section (like About) was empty, the rebuild uses clearly bracketed placeholders instead of fabricated numbers or projects — those are meant to be filled in with real details before publishing, not left as-is.
- **Diff-styled rewrites** (red = before, green = after) make the "what changed" instantly scannable, instead of burying the strategy in paragraphs of explanation.
- **Copy buttons** on every post/message draft and the share card, so nothing needs to be manually retyped into LinkedIn.
- **Live character counters** on posts (1,300 char limit) and connection messages (300 char limit) so drafts stay within LinkedIn's actual constraints.

## Tech

Plain HTML/CSS/JS — no build step, no dependencies. Opens directly in any browser or can be hosted as a static page (GitHub Pages, Vercel, Netlify).

- Tabbed navigation (Roast / Rebuild / Scorecard / 7-Day Plan / Share Card)
- Animated score bars on the report card
- Collapsible day-by-day plan
- `navigator.clipboard` for one-click copying of drafts

## Usage

```bash
git clone <repo-url>
cd linkedin-profile-audit
open linkedin_audit.html   # or double-click the file
```

No server, no install, no API keys required.

---

*Generated as a personal branding exercise — audit content is specific to one real profile, but the structure (roast → rebuild → scorecard → activation plan) is reusable for any profile audit.*
