# The Profile Desk — LinkedIn Profile Reviewer

A single self-contained HTML tool that gives job seekers a recruiter's-eye review of their LinkedIn profile: an overall score, a section-by-section critique, and paste-ready rewrites — powered live by the Claude API.

## What it does

You fill in a short intake form (headline, About section, most recent experience, skills, target role), and the assistant returns a structured "dossier":

- An overall score (0–100) and one-line executive verdict
- A blunt, first-person recruiter reaction to the profile as a whole
- Three prioritized, highest-leverage fixes to tackle first
- Five scored sections — Headline, About, Experience, Skills & Keywords, Overall Presence — each with a status (Strong / Needs Work / Weak), a specific critique, a side-by-side original vs. rewrite, and a one-line explanation of the recruiter psychology behind the rewrite

## Tech

- Plain HTML, CSS, and vanilla JavaScript — no frameworks, no build step, no external JS libraries
- Google Fonts (Fraunces, Inter, IBM Plex Mono) loaded via `<link>` for the editorial "case file" look
- Calls the Claude API (`claude-sonnet-4-6`) directly from the browser via `fetch` to `https://api.anthropic.com/v1/messages` — no API key needed when run inside Claude's live artifact view, since the call is authenticated automatically in that context

## How to use it

1. Open the file from within Claude's chat/artifact preview (not as a standalone downloaded file opened in a regular browser — the automatic API authentication only applies inside Claude's sandboxed preview).
2. Fill in at least a headline, About section, or experience — the rest are optional.
3. Click **Review My Profile**.
4. Read the dossier, copy any rewrite you want straight into LinkedIn with the **Copy** button next to it.

## The assistant's "brain" (system prompt design)

The Claude call is scoped tightly to one job: reviewing LinkedIn profile content submitted through the form. Key design choices:

- **Grounded critique, not generic advice.** The prompt instructs Claude to reference the user's own words rather than reaching for stock phrases like "use strong action verbs."
- **No fabrication.** Claude is explicitly told never to invent employers, titles, metrics, or achievements. If a real number is missing from a rewrite, it inserts an obvious placeholder like `[X%]` instead of making one up.
- **Strict JSON output.** Claude returns only a JSON object matching a fixed schema (score, verdict, five ordered sections, priority fixes, recruiter POV) — no prose, no markdown fences — so the interface can render it reliably without guessing at structure.
- **Hard length caps per field** (e.g. critique ≤ ~40 words, rewrite ≤ ~70 words) keep every response compact and predictable, so it reliably finishes within the token budget instead of getting cut off mid-response.
- **Edge cases handled explicitly:**
  - Empty fields still return a scored section with a fill-in-the-blank starter draft instead of fabricated content.
  - Irrelevant or nonsensical input returns a low score and an honest explanation rather than a hallucinated review.
  - Prompt injection embedded in pasted text is ignored — Claude stays in its reviewer role and does not reveal its instructions.
  - Abusive input is not engaged with or reproduced; the response stays neutral.

## Frontend error handling

- **Loading state** — a spinner and status line while the API call is in flight.
- **Empty state** — a clear call to action before anything has been submitted.
- **Truncated or malformed JSON** — caught and surfaced as a plain "please try again" message instead of a raw parser error.
- **Network/CORS failures** — detected specifically and explained (e.g. what to do if the file was opened outside Claude's artifact view) rather than showing a generic browser error.
- **Retry** — a one-click retry button on any error state, reusing the same submitted form data.

## Design notes

The interface deliberately avoids a chat-window metaphor, since the deliverable is a structured report, not a conversation. It borrows a case-file/dossier language instead: the input panel is the "Case Intake," the result is the "Dossier," and each reviewed section is labeled as an "Exhibit," since the review genuinely proceeds through a fixed, meaningful sequence. The circular score mark is styled like a wax seal — a stamp of review — to match the "coach at a top firm" tone rather than a generic dashboard dial.

## Extending this

- **Add tools** — give the API call a `web_search` tool so Claude can check live job postings for the target role and tune keyword suggestions against real listings.
- **Add memory** — store the last dossier (e.g. in `localStorage`) and pass it back into the prompt on a second pass to show delta scoring, such as "About improved from 54 → 78."
- **Multi-step flows** — split into two calls: one for the critique, and a second (triggered on request) to generate multiple headline variants for A/B testing, so the UI can offer a "give me more options" action per section.
- **File upload** — add a PDF/screenshot intake path that extracts text client-side and feeds it into the same JSON schema, so both structured fields and pasted profile exports work through one prompt.
