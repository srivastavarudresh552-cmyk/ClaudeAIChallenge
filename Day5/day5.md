# Prompt Engineering: Context vs. No Context

A practical demonstration of how adding structured context to an AI prompt transforms a generic output into a personalized, actionable plan.

## Overview

This experiment compares two versions of the same request — a 30-day web development learning roadmap — generated with and without user context. The goal: show exactly what changes when you give an AI model specific information about who you are.

## What Changed Between Outputs

### Prompt v1 — No context

```
Create a 30-day learning roadmap.
Include weekly milestones, daily tasks, resources, projects, and a final outcome.
Make it practical and beginner-friendly.
```

**Result:** A generic roadmap starting from HTML semantics, CSS box model, and JavaScript basics. Assumes zero prior knowledge. Suitable for anyone, optimized for no one.

### Prompt v2 — Structured context

```
Create a 30-day learning roadmap.

Context:
- Current Situation: Student
- Current Skills: React, Node, MongoDB
- Goal: Web Developer
- Available Time: 4 hours/day
- Experience Level: Beginner
- Preferred Learning Style: Projects
```

**Result:** A personalized roadmap that skips known foundations, targets specific skill gaps, fits a 4h/day student schedule, and ends with interview prep and a deployable capstone project.

## Key Differences

| Dimension | Without context | With context |
|---|---|---|
| Starting point | HTML semantics (Day 1) | Git workflow + TypeScript (Day 1) |
| Assumed knowledge | Zero | React, Node, MongoDB |
| Daily structure | Generic tasks | Scoped to 4 hours with a build target |
| Week 4 goal | "Keep coding" | Mock interview + job-readiness checklist |
| Tone | Any beginner | A CS student filling specific gaps |
| Projects | Generic (landing page, quiz app) | Portfolio-grade (blog with auth, real-time app, e-commerce capstone) |

## What Each Context Field Contributed

- **`React · Node · MongoDB`** — Eliminated 2 full weeks of foundations. Redirected focus to TypeScript, JWT auth, testing, and React Query.
- **`Student`** — Added resume cleanup, GitHub profile advice, and a mock interview on Day 30.
- **`4 hours/day`** — Every day card scoped to that time budget with a concrete deliverable.
- **`Project-based`** — Every day ends with something shipped, not just read or watched.
- **`Goal: Web Developer`** — Final week became job-readiness, not just more coding.

## Lesson

> A prompt without context asks the model to guess who you are.  
> A prompt with context lets it act like someone who already knows you.

The gap between a generic answer and a useful one is almost always the quality of context provided — not the complexity of what you ask for.

## Roadmap Skills Covered (v2)

`React` · `Node.js` · `MongoDB` · `TypeScript` · `JWT Auth` · `Socket.io` · `React Query` · `Jest + RTL` · `Stripe` · `Vercel/Render deploy`

## Files

| File | Description |
|---|---|
| `README.md` | This file — documents the experiment and findings |

## Author

Rudresh Srivastava
