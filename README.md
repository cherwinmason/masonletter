# mason-newsletter

The complete AI context repository for Mason — a daily Monday-to-Friday newsletter for operators who want to build with AI, not feel behind because of it.

**Private. Confidential. Feed to AI before every edition.**

---

## What This Repo Is

This is not a content archive. This is the AI's brain.

Every time the Newsletter Writer scenario generates a Mason issue, it loads this repository first. The brand documents here are permanent context — the difference between an AI that writes like a calm, trusted advocate and one that accidentally sounds like another AI-hype Substack.

---

## Structure

```
mason-newsletter/
├── mason-brand-bible-v2.md              ← LOAD FIRST. Every word written under the Mason name.
├── mason-voice-and-emotion.md           ← HOW Mason sounds. 7 emotions. Opening and closing patterns.
├── mason-day-type-definitions.md        ← What qualifies as a Build vs Tear-down vs Field Report vs Move vs Read.
├── mason-story-discovery-prompt.md      ← Prompt for the scoring/digest AI.
├── mason-finalization-agent-prompt-v2.md ← Master prompt for the writing AI (v2.0).
├── mason-newsletter-template-v1.html    ← HTML email template.
└── README.md
```

---

## The Two Brand Promises

Every Mason issue keeps two promises:

1. **Calm.** The reader will not leave feeling more behind than when they started.
2. **Substance.** The reader will leave with one real concrete thing they didn't know yesterday.

If a draft fails either promise, it does not ship. Skip the day instead.

---

## The One Sentence

Every issue is a stress test of this:

> *"You're not behind. You just haven't been shown how to build."*

If the reader leaves an issue calmer and closer to building something, the issue worked.
If the reader leaves an issue more behind than when they started, the issue failed.

---

## The Day-Type Rotation

Mason runs a Monday-to-Friday schedule. Each weekday has a default content type.

| Day | Type | What runs |
|-----|------|-----------|
| **Monday** | THE BUILD | One full real build, broken down. Flagship issue. |
| **Tuesday** | THE TEAR-DOWN | A public build, dissected with commentary. |
| **Wednesday** | THE FIELD REPORT | One named operator and what they shipped. |
| **Thursday** | THE MOVE | One specific tactical thing the reader can do today. |
| **Friday** | THE READ | The week's Mason worldview piece. |

Saturday and Sunday are sacred. No publishing. The reader gets their weekend back.

---

## The Mason Enemy

Mason has one enemy: **the Anxiety Industrial Complex.**

The AI media that profits from making operators feel behind. The "look what this AI did" content with no path to building it. The LinkedIn theatre of agents that have never shipped. The consulting class that gatekeeps real operational AI behind $200k engagements.

This enemy is not named in the newsletter. The newsletter is the antidote, and the antidote works by being what the enemy is not. Generous where they gatekeep. Specific where they wave hands. Calm where they panic. Non-selling where they pitch.

---

## Quick Reference

**The Mason Move:** Every issue does two things in order —
1. Filter the noise (tell the reader what to ignore)
2. Hand over one real thing (a build, a tear-down, a profile, a move, or a take)

**Banned forever:** revolutionary, game-changer, disrupt, transform, unlock, unleash, harness, supercharge, leverage (verb), synergy, ecosystem, journey, mission-critical, best-in-class, cutting-edge, next-gen, seamless, frictionless, magical, insane, incredible, amazing, exciting, AGI, "this changes everything," "you won't believe," "friends," "fam," "builders" (as greeting).

**Use instead:** build, ship, ran, running, system, agent, workflow, operator, judgment, evidence, receipts, in production, the recipe, the move, hours back, replaced, retired, calm, on your side, worth your time, noise, signal.

**The Mason Benchmark:**

> *"The intake agent runs at 6:14am, before anyone's at their desk. By the time the first operator opens Slack, twenty-three vendor inquiries have been classified, drafted, and queued for one-click approval. The system has been running for nine weeks. It has not missed a single classification. The team that used to do this work is now building three more agents."*

Hits Permission + Relief + Momentum simultaneously. Every Build day is measured against this paragraph.

---

## Visual Identity

- Primary type: Inter (body, headers)
- Code/monospace: JetBrains Mono (metadata, code blocks, prompts)
- Black (#0A0A0A) on warm off-white (#FAFAF7)
- Single accent: clay terracotta (#B85C3D)
- No AI-generated hero images. Ever.
- Built, not designed. Utilitarian craftsman's notebook feel, not Substack template.

---

## Signoff

Every issue signs itself as **"— Mason"** only. No personal name. No title. The publication is the byline.

---

## For the AI (Make.com Integration)

Mason runs as three Make.com scenarios, duplicated from the Vittori architecture:

### Scenario 1: Mason Story Discovery
- Schedule: 9pm SGT, Sunday-Thursday
- Fetches all Mason RSS feeds (Twitter/X via RSS.app, Reddit, Hacker News, Substacks, tool blogs, Pocket manual queue)
- Calculates tomorrow's day-type from the weekday
- Loads `mason-brand-bible-v2.md`, `mason-day-type-definitions.md`, and `mason-story-discovery-prompt.md` from this repo via GitHub raw URLs
- Scores all items with Haiku 4.5, filters to tomorrow's day-type, posts top 5 to Telegram

### Scenario 2: Mason Story Selector
- Triggered by Telegram bot watching the Mason group
- Filter: message contains "http"
- POSTs the URL to the Newsletter Writer webhook
- Identical architecture to Vittori Story Selector — brand-agnostic

### Scenario 3: Mason Newsletter Writer
- Triggered by webhook from Story Selector
- Fetches brand documents from this repo: brand bible, voice doc, day-type definitions, finalization prompt, HTML template
- Fetches article content via ScraperAPI (truncated to 15k chars)
- Generates issue with Haiku 4.5 (draft) + Sonnet 4.5 (voice polish)
- Populates the HTML template variables
- Sends final templated HTML to Jira ticket (or Beehiiv draft) for review
- You approve, it publishes

### Template variables

The Newsletter Writer populates these from the agent's JSON output:

| Variable | Source |
|----------|--------|
| `{{SUBJECT_LINE}}` | `subject_line` |
| `{{PREHEADER_TEXT}}` | `preheader_text` |
| `{{ISSUE_NUMBER}}` | Incremented counter (e.g. "047") |
| `{{ISSUE_DATE_SHORT}}` | Today's date, DD.MM.YY |
| `{{DAY_TYPE_LABEL}}` | `day_type_label` |
| `{{HEADLINE_PART_1}}` | `headline_part_1` (black) |
| `{{HEADLINE_PART_2}}` | `headline_part_2` (clay) |
| `{{THE_FRAME}}` | `the_frame` (HTML) |
| `{{THE_REAL_THING}}` | `the_real_thing` (HTML with rhythm elements) |
| `{{THE_NOISE_FILTER}}` | `the_noise_filter` (HTML or empty) |
| `{{NOISE_SECTION_NUMBER}}` | `noise_section_number` |
| `{{THE_CLOSER}}` | `the_closer` (HTML) |

---

## Budget

- Launch (0-2,500 subs): ~$137/month
- Growth (2,500+ subs): ~$176/month
- Breakdown: Feedly Pro+ ($15) + RSS.app ($46) + Claude API (~$55) + Make.com ($10) + email validation ($10) + domain ($1) + Beehiiv (free → $39)

---

## The One Rule

**Every issue does two things in order: filter the noise, hand over one real thing.**

Everything in this repo enforces that rule. When drafts feel wrong, check against this rule first.

---

## This Repository Is Alive

Update it when the brand evolves. Add new banned words when they surface. Add new opening or closing patterns when something works unexpectedly well. The brand will sharpen over the first 50 issues. This repository is the running record of how it sharpens.

The foundation stays: the gap between watching AI happen and building AI that works is smaller than it looks. The reader is not behind, only un-shown. Mason closes that gap one real thing at a time, every weekday morning.

---

*Version 1.0 — April 2026*
