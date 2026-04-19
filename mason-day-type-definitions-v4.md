# Mason Day-Type Definitions — v4

**Last updated:** April 19, 2026
**Status:** Active. Two day-types only.

---

## Mason's Schedule

Mason publishes twice per week:

- **Monday — THE BUILD**
- **Thursday — THE MOVE**

Tuesday, Wednesday, Friday, Saturday, Sunday — nothing. Weekends and midweek buffer are deliberate.

This document defines what qualifies for each day-type, and what structure each issue follows.

---

## MONDAY — THE BUILD

### What qualifies as Build material

A real operational system that actually runs in production, that a reader could potentially wire up at their own company. Must include:

- A named operator or company (someone shipped this, not theoretical)
- A concrete problem the system solves
- Enough detail on the stack, prompts, or architecture to be useful
- Either real outcome numbers OR a structured "what we know / what we don't" treatment
- Something that generalizes — the reader should leave thinking "I could apply this pattern"

### Good Build sources

- Public engineering writeups (Simon Willison, Anthropic cookbook, company tech blogs)
- Detailed Twitter/X threads where operators share their actual builds with prompts
- Substack posts where builders document what they shipped
- Case studies from Quarry engagements (with client permission, sensitive details anonymized)
- GitHub repos with strong READMEs showing a complete build
- Conference talks where operators walk through real systems
- Podcast episodes where operators share specific technical decisions

### Bad Build sources

- Press releases about AI product launches (no build detail, just marketing)
- Funding announcements
- Twitter threads that just describe categories without specifics
- Articles about AI trends without a specific build at the center
- VC essays about AI themes
- Academic papers (unless they include working implementation)
- News aggregation articles

### Build day length

**1,700 to 2,400 words.** *(Bumped from 1,500-2,200 in v4 to accommodate the Translation Rule — plain-English chapter frames and inline term translations add 200-400 words per issue. See brand bible "The Translation Rule" and finalization prompt Section 8.5.)*

This is substantial. Longer than typical newsletter fare. Length signals depth, which signals authority, which is what Quarry's eventual buyers are evaluating.

### Build day structure

Five sections. No more. Dense paragraphs, not more sections.

1. **The Frame** (100 to 150 words)
   Opens with Mason's take on this build. States the position. Not a summary — a stance.

2. **What it does** (250 to 350 words)
   In plain operator language. "The system reads inbound vendor inquiries, classifies them as NEW/EXISTING/SPAM/URGENT, drafts a response, queues it in Slack with a one-click approval button."
   Not: "leverages AI to optimize workflow efficiencies."

3. **Why it was built / The stack** (400 to 600 words)
   The problem. The pain. What was costing what. What the old manual process looked like. Then the tools and models that were chosen, and why. Use inline code for tool names: `claude-sonnet-4-5`, `Zapier`, `Intercom`.
   Include at least one code block showing a prompt, config snippet, or architectural sketch if available.

4. **What's working, what's missing** (400 to 600 words)
   Honest assessment. What actually works in production. What the build gets wrong or ducks. What a reader would need to do differently. This is where Mason takes the sharpest position.

5. **The outcome** (250 to 400 words)
   Real numbers when available. The Receipts Box goes here with outcome metrics that do emotional work.
   When specific numbers aren't available: use the "What we know / What we don't know / What we'd want to see" treatment.

Plus the required elements (v6 template):
- One source block quote (full-bleed clay background)
- One pull quote from Mason's writing (inside the Playbook)
- Fig. 01 Flow Block (Input → Process → Output)
- The Receipts (4 rows, one clay-highlighted, black full-bleed)
- The full Playbook kit (Parts A/B/C/D — checklist, numbered move cards, code block, warning strips)
- The Reply Hook (one specific sentence tied to today's content)
- The Closer (three-part bridge: thesis line + question line + handoff line, on black)
- The Work With Quarry CTA (positioning + primary button + secondary link, on deeper cream)
- Sign off with "— Mason"

Optional (editorial judgment):
- One Margin Note (marginalia callout, max one per issue)
- Fig. 02 big-number contrast (only if the story has a stark two-value comparison)

---

## THURSDAY — THE MOVE

### What qualifies as Move material

A specific tactical thing the operator can do this week. Must include:

- A clear problem the Move solves
- A specific recipe, framework, or pattern the reader can apply
- Enough detail that the reader can start applying it that day
- An honest caveat (what this doesn't fix, where it breaks)

Moves are smaller than Builds. A Move might be: a prompt pattern for a specific task, a decision framework for choosing between tools, a wiring pattern for a common integration, a way of thinking about a category of problem.

### Good Move sources

- Prompt engineering writeups
- "How we decided X" tool selection posts
- Decision framework essays from operators
- Tactical threads about a specific technique
- Anthropic / OpenAI / framework documentation with novel patterns
- Operator posts about "here's how I think about X"
- Small open-source tools worth knowing

### Bad Move sources

- "Top 10 tools" lists
- Vague "you should try this" posts
- Tools without context about when they apply
- Broad "future of AI" think pieces

### Move day length

**1,300 to 1,900 words.** *(Bumped from 1,200-1,800 in v4 to accommodate the Translation Rule.)*

Shorter than Build (because the subject matter is tighter) but still substantial.

### Move day structure

Four sections.

1. **The Frame** (100 to 150 words)
   Opens with what problem this Move solves and why it matters now.

2. **The Thing** (300 to 500 words)
   What the Move actually is. Named, specific, linked to source if applicable. Show, don't describe.

3. **How to apply it** (500 to 800 words)
   The recipe. Step-by-step where it makes sense, but in paragraphs not numbered lists (Outlook renders numbered lists inconsistently). Use code blocks for prompts, configs, or copy-paste snippets.

4. **The catch** (200 to 350 words)
   Honest caveat. What this doesn't fix. When not to use it. What breaks. Where the edges are.

Plus the required elements (v6 template):
- One source block quote (full-bleed clay background)
- One pull quote from Mason's writing
- Fig. 01 Flow Block (Input → Process → Output) — every issue, no exceptions
- The Reply Hook (one specific sentence tied to today's content)
- The Closer (three-part bridge: thesis line + question line + handoff line, on black)
- The Work With Quarry CTA (positioning + primary button + secondary link, on deeper cream)
- Sign off with "— Mason"

MOVE days skip the Receipts block and the full Playbook kit — the second chapter IS the tactical move in light form.

Optional (editorial judgment):
- One Margin Note (marginalia callout, max one per issue)
- Fig. 02 big-number contrast (only if the move has a stark two-value comparison)

---

## Day-Type Logic in the System

The Make.com scenario currently calculates day-type based on the current weekday. For twice-weekly Mason:

```
If today is Monday → DAY_TYPE = "BUILD"
If today is Thursday → DAY_TYPE = "MOVE"
All other days → should not run
```

If Mason Newsletter Writer fires on a non-publishing day (Tues/Wed/Fri/Sat/Sun), the scenario should either:
- Return an error and not generate an issue, OR
- Default to whichever day-type is more appropriate based on Quarry team manual curation

For now: the human (Cherwin) manually pastes URLs in Telegram only on Sunday night (for Monday's Build) or Wednesday night (for Thursday's Move). The system doesn't need to handle the other days — they simply don't get triggered.

---

## Required Elements in Every Issue (Both Day-Types)

Regardless of day-type, every Mason issue must include:

1. **A position-taking frame** — Mason has a stance, not just a summary
2. **One block quote from the source** — authority and texture
3. **One pull quote from Mason's take** — visually elevated, one sentence that earns pullout
4. **A Receipts Box on Build days** (outcome numbers, not feature specs)
5. **Code block on both day-types when applicable** (when a prompt, config, or wiring detail is being shown)
6. **The soft Quarry CTA** — one line before the signoff
7. **"— Mason" signoff** — no personal byline

---

## The Quality Filter

If an incoming story doesn't have enough material for the day's structure, skip it. Find a different story. If Sunday night comes and there's no story worth Monday's Build, skip Monday. Publish Thursday only that week.

One excellent issue beats two mediocre ones. Every time.

---

## Adding Other Day-Types Later

This v2 simplification removes TEAR-DOWN, FIELD-REPORT, and READ days. They can return when:

- Cadence increases beyond 2x/week
- Quarry has writers other than Cherwin
- Mason's archive is deep enough to justify varied formats

Until then: Build and Move. Nothing else.

---

*Version 4.0 — April 19, 2026 — Word count targets bumped to accommodate Translation Rule from finalization prompt v6.4 (BUILD 1,700-2,400, MOVE 1,300-1,900).*
