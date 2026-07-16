# Autonomous Agent Studio — Social Content Pipeline

A single-file HTML tool that orchestrates a multi-agent loop of live Claude API calls to write, score, critique, and iteratively improve a three-platform social media post (LinkedIn, Twitter/X, Instagram) until a quality bar is met — with no fixed round count.

## What it does

Give it a topic and a brand voice, and it runs a chain of specialized agents against the Anthropic Messages API:

1. **Planner** (runs once) — turns your topic + voice into a strategy brief: angle, hook, key message, audience, and per-platform notes.
2. **Executor** (runs once) — writes the first three-platform draft from that brief.
3. **Evaluator → Critic → Improver → Memory Manager** (repeating loop) — each round:
   - **Evaluator** scores the current draft 0–100 across six rubric criteria (clarity, hook, brand voice, platform fit, CTA, originality).
   - **Critic** adversarially digs up weaknesses, missed opportunities, and risks the score alone doesn't capture.
   - **Memory Manager** distills a running "what's working / what to avoid" note that carries forward into every future round.
   - **Improver** rewrites the draft using all of the above (skipped on the final round once a stop condition fires).
4. **Final Reviewer** (runs once, after the loop stops) — gives the winning draft one last polish pass and a publish-readiness verdict.

## Stop logic

After every Evaluator + Critic + Memory pass, three conditions are checked **in order** — whichever fires first ends the loop:

1. **Plateau** — score gain under +2 for two consecutive rounds.
2. **Threshold** — score reaches the quality target you set (85 / 90 / 95).
3. **Hard cap** — 8 rounds, as a safety fallback only.

Nothing is scripted to a fixed number of iterations; every step is conditioned on the live output of the previous one.

## Using it

- **Inside Claude.ai's artifact panel:** just enter a topic, (optionally) a brand voice, and a quality target, then click **Run pipeline**. API calls are made with no key required.
- **Opened directly as a saved `.html` file in a browser:** the calls go straight to `api.anthropic.com`, so you'll need to paste an Anthropic API key into the "API key" field. The key is held in memory only for that session and is never sent anywhere except Anthropic's API.

While running, the dashboard shows:
- A live **orchestration loop diagram** highlighting whichever agent is currently active.
- Round count, latest score, API call count, and retry count.
- Tabs for the **activity log**, **current draft**, **evaluation** (with per-criterion bars), **critique**, **running memory**, and a **score-over-rounds chart** with per-round history.

When the loop stops, a **final summary** appears with the polished draft, publish-readiness verdict, run stats, per-agent call counts, an architecture overview, and extension ideas.

## Technical notes

- Model: `claude-sonnet-4-6`, called via `fetch` to `POST /v1/messages`.
- Each agent has its own system prompt and its own `max_tokens` budget, sized so JSON responses (especially Critic's and Memory Manager's array-heavy output) don't get truncated mid-object.
- Responses are parsed with a tolerant JSON extractor: it strips code fences, tries a direct parse, falls back to a brace-balanced substring scan (to recover from trailing prose or minor truncation), and finally applies a small repair pass for smart quotes / trailing commas before giving up.
- Failed calls retry up to twice with a short backoff; retry and error counts are visible in the dashboard.
- You can stop a run mid-loop with the **Stop run** button.
- No data persists between runs — the "Memory Manager" notes exist only for the duration of one run (see extension ideas in the artifact for turning this into cross-session memory).
