# MASON — DAY-TYPE DEFINITIONS
## What counts as Build, Tear-down, Field Report, Move, and Read material.

> Reference doc loaded by the Story Discovery prompt to tag candidate stories.
> **Feed this to the AI alongside the brand bible.**
> Version 1.0 — April 2026

---

## Why This Document Exists

Mason runs a daily Mon-Fri rotation. Each weekday has a default content type. The Story Discovery agent must tag each candidate story with which day-type(s) it could fit, so tomorrow's digest surfaces only the candidates that match tomorrow's day-type.

A story can be tagged for multiple day-types. The agent does not need to pick one — it tags everything that fits. Editorial selection (the human picking from the digest) decides the final use.

This doc defines what each day-type needs from a source. The Story Discovery prompt loads it as context.

---

## The Five Day-Types

| Day | Type | What runs |
|-----|------|-----------|
| **Monday** | THE BUILD | One full real build, broken down. The flagship. |
| **Tuesday** | THE TEAR-DOWN | A public build, dissected with commentary. |
| **Wednesday** | THE FIELD REPORT | One named operator and what they shipped. |
| **Thursday** | THE MOVE | One specific tactical thing the reader can do today. |
| **Friday** | THE READ | The week's Mason worldview piece. |

---

## DAY-TYPE 1 — THE BUILD (Monday)

### What it is

A complete, real, copyable AI build. Tools named, prompt shown, wiring described, outcomes measured. The reader leaves with enough to build their own version within an hour.

### What qualifies as a Build source

A source qualifies if it contains, or strongly hints at, the raw material for a full build write-up:

- Original author posted enough technical detail (prompts, architecture, tools) to reverse-engineer
- The build runs in production (not a demo, not a tutorial, not theoretical)
- The build solves a real operational problem (not a toy)
- A real outcome is named (hours saved, errors caught, dollars unspent, volume handled)
- Ideally a specific operator or team is credited

### What disqualifies a source

- Pure tutorial content ("here's how to use Claude") with no real-world deployment
- Marketing posts from tool companies that don't show actual use
- Theoretical "you could build this" without evidence anyone has
- Builds described too vaguely to reverse-engineer
- Demos and prototypes that never went to production

### Examples of qualifying sources

- A founder's Twitter thread: "We replaced our whole intake function with 3 Claude agents. Here's the architecture, here are the prompts, here's what it cost us."
- A Substack post: "How we built a $200k/year savings agent in two weekends, with every prompt and the full Make.com scenario."
- A Reddit r/AI_Agents post: detailed build with architecture diagram and outcome metrics, even if rough.

### Note on Build sourcing

Mason's strongest Build issues are usually written from the writer's own builds (Cherwin's work or his team's, with permission). External Build sources are rarer because most public content lacks the depth Mason requires. The agent should still tag external sources as Build candidates when the depth is there — but expect Monday issues to lean heavily on internal/original work.

---

## DAY-TYPE 2 — THE TEAR-DOWN (Tuesday)

### What it is

A public build that's been getting attention, dissected with Mason's commentary. What's real, what's missing, what Mason would do differently. Always credits the original builder. Adds value, doesn't punch down.

### What qualifies as a Tear-down source

- A build, agent, or system that's been publicly shared and is getting traction (likes, replies, reshares)
- Enough technical detail visible to actually evaluate the work
- Original creator is named (Mason credits them)
- The build has something interesting to say about — either it works in a non-obvious way, or it has a flaw worth naming, or it represents a pattern worth understanding
- Ideally controversial or under-discussed (if everyone's already torn it down, Mason adds nothing)

### What disqualifies a source

- Builds without enough technical detail to evaluate
- Pure puff pieces with no substance to dissect
- Anonymous builds (Mason credits people)
- Builds where the only "story" is "this is impressive" (nothing to add)
- Hit-piece material — Mason doesn't tear down to mock

### Examples of qualifying sources

- A viral LinkedIn post: "I replaced my whole legal team with Claude" — with enough detail to evaluate, where Mason can say "the workflow is real but the legal review claim is overstated, here's what's actually safe to automate."
- A GitHub repo trending in the AI category — Mason walks through the architecture, what's clever, what's missing.
- A Show HN post about an agent system — Mason evaluates the design choices.

### Note on Tear-down voice

Tear-downs are the day Mason gets closest to opinion. Voice must stay calm and respectful. Mason names what's wrong without contempt for the builder. The contempt is reserved for systemic patterns (the AI hype industrial complex), never for individuals.

---

## DAY-TYPE 3 — THE FIELD REPORT (Wednesday)

### What it is

One named operator, one real thing they shipped, broken down. Different from Build because the focus is the operator and their context (industry, team size, problem they solved), not just the system. Different from Tear-down because Mason is writing *with* the operator (often after talking to them), not commenting on a public post.

### What qualifies as a Field Report source

- A specific named operator (not a company in the abstract — a person)
- They shipped something real (production, not prototype)
- Their context is interesting (industry, team size, role) and matters to the build
- Mason can either talk to them or has enough public detail to write the profile accurately
- Ideally an operator who isn't already an AI Twitter celebrity — Field Report is for surfacing the unsung builders

### What disqualifies a source

- Founders of AI tool companies (those are vendor case studies, not field reports)
- Already-famous AI personalities with massive audiences (Mason surfaces less-covered builders)
- Companies without a named individual driving the build
- Operators whose builds are too vague to write up substantively
- Pure PR — operators promoting themselves with no real shipping detail

### Examples of qualifying sources

- A LinkedIn post from a 10-person agency owner describing the agent system that replaced their account management workflow.
- A reader email (once Mason has subscribers): "I built X to solve Y, here's how, want to chat?"
- A Substack post from a mid-market COO explaining how their team replaced three SaaS subscriptions with a Claude pipeline.
- A Reddit post from a solo founder breaking down their automation stack.

### Note on Field Report sourcing

Field Reports require either the operator to publicly share enough detail OR Mason to do an interview. Early on (before reader inbox supplies leads), most Field Reports come from public posts where the operator already shared the detail. Over time, reader replies and outreach become the primary source.

---

## DAY-TYPE 4 — THE MOVE (Thursday)

### What it is

One specific tactical thing the reader can do today. A tool worth using. A prompt that works. A workflow worth copying. A pattern worth learning. Concrete, opinionated, generous. The reader can apply it within the day.

### What qualifies as a Move source

- A specific named tool, prompt, workflow, or pattern
- Concrete enough to apply without further research
- Has been shown to work (either by the writer or a credited operator)
- Solves a real operational problem operators face
- Small enough scope to act on in under an hour
- Not gated behind a paywall, course, or "DM me to learn more"

### What disqualifies a source

- Vague advice ("you should automate more!")
- Tools that require significant setup before delivering value
- Prompts that are clever but don't solve a real problem
- Patterns that require enterprise-scale infrastructure
- Anything from a paid course/community where the actual recipe is gated

### Examples of qualifying sources

- An Anthropic blog post about a new prompt pattern with a working example.
- A Make.com template release with a clear use case.
- A Twitter thread: "Here's the exact prompt I use to extract structured data from messy emails. Free, here it is."
- A new tool launch on Product Hunt that solves a specific operator problem (with link to try it).
- An obscure feature in an existing tool (Notion AI, Claude Projects, etc.) that operators are sleeping on.

### Note on Move voice

Moves are where Mason is most concrete and tactical. Voice should be direct ("do this, here's why, here's the prompt"). Less narrative than Build days, more utility-focused. The reader should close the Move issue with a specific action queued up.

---

## DAY-TYPE 5 — THE READ (Friday)

### What it is

The week's Mason worldview piece. Opinion, conviction, advocacy. Always grounded in something concrete from the AI conversation that week — a news event, a trend, a pattern Mason wants to name and push back on. Earned through builds, not theoretical thought leadership.

### What qualifies as a Read source

- A piece of AI news, discourse, trend, or event from the past week worth opining on
- Something that touches on Mason's worldview themes: agents vs consultants, the anxiety industrial complex, real builders vs AI theatre, judgment vs hype
- Not just news for news' sake — the source must contain a thesis-shaped opportunity (something Mason has a real take on)
- Can be reactive (responding to a piece of news) or proactive (Mason naming a pattern others haven't)

### What disqualifies a source

- Pure news without thesis potential
- Topics outside Mason's worldview (model architecture deep-dives, AI safety research, crypto-AI crossovers, etc.)
- Topics where Mason has nothing genuinely contrarian or sharp to say
- Anything that would just amplify another publication's take

### Examples of qualifying sources

- OpenAI announces a new model → Mason's Read: "Most of what's being said about this is wrong. Here's what actually matters for operators."
- McKinsey publishes a "State of AI" report → Mason's Read: "The Big 4 are reporting on the field they don't understand. Here's what they're missing."
- A viral LinkedIn post claims agents will replace ops teams → Mason's Read: "Replacement isn't the right frame. Here's what's actually happening in the operators I talk to."
- A tool company changes pricing → Mason's Read: "The real cost of this isn't the price increase. It's the dependency."

### Note on Read voice

Read days are where Mason's opinion is loudest. Voice still calm, but more declarative. Strong takes, plainly stated. Always grounded in something concrete (a build, a number, a named operator). Never pure pontification.

---

## Tag Combinations

A source can be tagged for multiple day-types. Common combinations:

- **Build + Tear-down** — a public build with enough detail that Mason could either write it up as a Build (treating it as inspiration for an original Mason explanation) or as a Tear-down (commenting on the original).
- **Field Report + Build** — a named operator's public post with full build detail. Could go either way depending on whether Mason wants to profile the operator or just walk through the build.
- **Move + Tear-down** — a tactical pattern someone shared that Mason wants to recommend (Move) but with caveats (Tear-down element).
- **Read + Move** — a piece of AI news that Mason wants to opine on, with a tactical recommendation embedded.

The agent tags everything that fits. The editorial selection (human) decides which day to use it.

---

## What Doesn't Qualify For Any Day-Type

Some sources are clean rejects regardless of day-type:

- AI funding/M&A news (Mason isn't a business news letter)
- Model architecture papers (too technical for Mason's reader)
- AI safety/alignment discourse (outside Mason's lane)
- Geopolitical AI commentary (not Mason's worldview)
- Pure consumer AI news (ChatGPT mobile updates, etc.) unless there's an operator angle
- Crypto + AI crossovers
- AI-generated art / image / video discourse (different audience)
- Personal essays about AI feelings
- Anything from sources Mason has identified as low-quality (LinkedIn AI gurus with no shipping evidence, hype accounts, etc.)

The Story Discovery agent rejects these at the scoring stage rather than tagging them.

---

## This Document Is Alive

When the agent miscategorizes something, capture the failure here as a clarification. When a new source pattern emerges (Discord screenshot becomes common, podcast clip becomes common), add it as a new source type under the relevant day-type. The day-types may evolve. The principle stays: each weekday has one shape, and the agent must know what that shape needs.
