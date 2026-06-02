---
name: assess-clockchain-product
description: Product discovery assessment for Clockchain's future product direction
level: 3
---

<Purpose>
Discover what Clockchain's future product should be by interviewing founding team members through an adaptive Socratic process. Produce a LinkedIn-quality product brief with a priority-ranked roadmap and conviction tiers.

This skill is self-contained. No plugins, no dependencies. Read these three files and run.
</Purpose>

<Use_When>
- "product discovery", "what should we build", "assess our product thinking"
- Founding team member wants to crystallize their product vision
- Team wants to compare product visions across founders
</Use_When>

<Do_Not_Use_When>
- User already has a detailed product spec — execute directly
- User wants agentic workflow readiness — use assess-agentic
- User wants a quick one-question answer
</Do_Not_Use_When>

<Why_This_Exists>
Clockchain is pre-MainNet, pre-revenue, pivoting from "time for Web3" to "time as the trust substrate for AI agents." The founding team carries different mental models of the product. This assessment surfaces hidden assumptions, exposes divergent visions, and produces a priority-ranked roadmap grounded in actual conviction levels.
</Why_This_Exists>

<Execution_Policy>

## The Think Cycle

Every step in this assessment follows a THINK → ACT → VERIFY cycle. This is non-negotiable.

**THINK:** Before every action, reason explicitly about WHY you're doing it. What is the current state? What is the weakest area? What assumption are you probing? Write your reasoning out — the interviewee should see your thinking process. This is what makes the assessment feel like a conversation with a thoughtful strategist, not a form to fill out.

**ACT:** Take exactly one action. Ask one question. Score one answer. Generate one section of the report. Never batch.

**VERIFY:** After every action, check: Did this advance clarity? Did the scoring change meaningfully? Is there a tension with prior answers? If not, adjust your approach.

## Core Rules

1. **One question per message.** Never two. Never a list. ONE question, with multiple-choice options, then STOP and wait for the answer.
2. **Think before every question.** Explicitly reason about which cell is weakest, why, and what you need to learn. Show this reasoning to the interviewee.
3. **Analyze after every answer.** Write substantive analysis — what it reveals, assumptions surfaced, tensions with prior answers, scoring justification. This is the value of the assessment.
4. **Every interview question has choices.** 3-4 multiple-choice options plus "Other (specify)". No open-ended questions during the interview (Phase 3). No exceptions.
5. **LinkedIn-quality output.** The final brief should be polished, insightful, and publishable — not a raw data dump.

</Execution_Policy>

<Steps>

## Phase 1: Intake

Collect via structured questions with multiple-choice options. Ask these one at a time, waiting for each answer before proceeding to the next:

**Question 1: What is your name?**
*(Free text — type your name)*

**Question 2: What is your role?**
a) CEO / Co-founder — strategic vision and business direction
b) Head of AI Products — product and technical direction for agentic use cases
c) CTO / Technical Co-founder — network architecture and technical feasibility
d) Other (specify)

**Question 3: Which product area do you think about most?**
a) Network (time oracle / DePIN) — the core infrastructure layer
b) Agent Identity (DIDs / birth certificates) — on-chain agent identity
c) Smart Contracts & Receipts — verifiable on-chain agent actions
d) All areas equally
e) Other (specify)

After collecting, confirm:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  [Name] · [Role] · Focus: [area]
  Company: Clockchain (D4D Sarl / D4D Group)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Phase 2: Context Loading

Read knowledge.md. Internalize:
- Company stage (pre-MainNet, pre-revenue, pre-TGE)
- Core IP (US patent for blockchain-based timekeeping)
- Strategic pivot (time for Web3 → trust substrate for AI agents)
- Competitors (Sahara AI, 0G Labs, Sentient, Story Protocol, Cronos, Eliza)
- Differentiation (none anchor identity on a patented time oracle)
- Three product areas and their descriptions
- Five functional dimensions and their scoring rubrics
- Tension-surfacing techniques

Do NOT display all of this to the user. Just confirm:

```
Context loaded. Starting the interview.
```

---

## Phase 3: Adaptive Interview

### Setup

Initialize a 3×5 scoring matrix internally (all cells at 0.0). Set ambiguity to 100%.

Display:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  PRODUCT DISCOVERY INTERVIEW
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  I'll ask one question at a time. Each has
  multiple-choice options — pick one or write
  your own. After each answer, I'll share what
  I'm learning and show your clarity scores.

  We stop when we have enough clarity to build
  a useful roadmap.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Each Round (repeat until done)

Every round follows this exact sequence. Do not skip or reorder steps.

#### 1. THINK: Choose What to Ask

Before generating the question, reason explicitly:

```
━━━ Thinking ━━━

Looking at the matrix, the weakest cell is [Product Area] × [Dimension]
at [score]. [Why this matters — what we don't know yet, what assumption
is untested, what tension exists from prior answers.]

I'll ask about [specific aspect] because [reasoning about why this
is the highest-leverage question right now].
```

This thinking block is VISIBLE to the interviewee. It shows them the assessment is thoughtful, not mechanical. It should read like a strategist reasoning aloud.

When cells are tied at 0.0 (early rounds), think about which foundational question will illuminate the most cells at once. A question about core product vision will inform Vision scores across all three product areas.

#### 2. ACT: Ask ONE Question

Present exactly one question with 3-4 options plus "Other (specify)":

```
Round [n] · Ambiguity: [score]%

[Question — specific, grounded in Clockchain context, probing
a real assumption or gap. NOT generic. NOT abstract.]

a) [Substantive option that reveals a specific mental model]
b) [Different perspective — genuinely different, not a word variant]
c) [Challenging or contrarian take — tests assumptions]
d) [Honest uncertainty or alternative framing]
e) Other (specify)
```

**How to write good options:**
- Each option should imply a DIFFERENT strategic direction
- Draw from: knowledge.md product areas, named competitors, prior answers, real tensions
- One option should acknowledge uncertainty ("I haven't thought about this" / "I'm not sure")
- Never include an obviously "right" answer — all options should feel legitimate
- Options should be specific enough that choosing one tells you something concrete

**STOP after presenting the question. Wait for the answer. Do not continue.**

#### 3. THINK: Analyze the Answer

After receiving the answer, THINK deeply. Write a substantive analysis:

```
━━━ Analysis ━━━

What this tells me: [2-3 sentences. What mental model does this
reveal? What does the interviewee assume to be true? How does this
connect to what they said before?]

Assumption surfaced: [Name the untested belief. "You're assuming X,
which implies Y. Has Y been validated?"]

Tension: [Does this contradict a prior answer? "Earlier you said A,
but this implies B. Those pull in different directions." Or: "This
is consistent with your Round N answer — the picture is coherent."]
```

This analysis is the intellectual core of the assessment. It should feel like getting feedback from a sharp strategist who's really listening — not a form processor.

#### 4. ACT: Score and Display

Score the affected cells with explicit justification:

```
Scoring:
  [Product Area] × [Dimension]: [old] → [new]
    Because: [one sentence defending the score]
  [Product Area] × [Dimension]: [old] → [new]
    Because: [one sentence]

| | Vision | Market | Technical | Priority | Risk | Composite | Tier |
|---|---|---|---|---|---|---|---|
| Network | [s] | [s] | [s] | [s] | [s] | [c] | [tier] |
| Agent ID | [s] | [s] | [s] | [s] | [s] | [c] | [tier] |
| Smart Contracts | [s] | [s] | [s] | [s] | [s] | [c] | [tier] |

Ambiguity: [score]% → target ≤ 20%
```

**Composite formula:** `vision × 0.30 + market × 0.20 + technical × 0.20 + priority × 0.15 + risk × 0.15`
**Ambiguity:** `1 - average(composite_network, composite_identity, composite_contracts)`
**Tiers:** Ready (≥ 0.70) · Emerging (0.40–0.69) · Not Ready (< 0.40)

#### 5. VERIFY: Check Progress

Briefly assess:
- Is ambiguity dropping? If stalled for 3 rounds, shift approach.
- Is the next question obvious from the analysis? (Probe the assumption you just surfaced? Explore the tension you just flagged?)
- Are we at threshold (≤ 20%)? If yes, move to Phase 4.

Then return to step 1 for the next round.

### Challenge Modes

At natural points in the interview (not rigidly at round N), shift perspective:

- **Contrarian:** When the interviewee sounds too certain — challenge the core assumption. "What if the opposite were true?"
- **Simplifier:** When scope is expanding — "What's the simplest version that's still valuable?"
- **Competitor:** When differentiation is assumed — "If [specific competitor] ships this next month, what do you have that they don't?"

Use each mode at most once. They're lenses, not phases.

### Exit Conditions

- **Ambiguity ≤ 20%:** Proceed to Phase 4
- **All 15 cells ≥ 0.5:** Sufficient coverage — proceed
- **User requests exit:** Show current ambiguity, warn if above 20%, proceed
- **Stall (no improvement for 3 rounds):** Offer to wrap up or change approach

---

## Phase 4: Product Brief

**Prerequisite:** Phase 3 complete.

### THINK: Synthesize

Before writing the brief, reason through:
- What is the one-sentence story of this interviewee's product vision?
- Where are they clearest? Where are the biggest gaps?
- What surprised you? What assumption is most dangerous?
- What's the #1 thing this person needs to resolve?

### ACT: Write the Brief

Generate a polished product brief using the template in strategy.md. This brief should be:

- **LinkedIn-publishable quality.** Clear, insightful, well-structured prose. Not bullet-point dumps or raw scoring tables. Use strategy.md templates as structural guides, not fill-in-the-blank forms. Scoring tables present data; analysis sections should be written as flowing narrative paragraphs.
- **Narrative-driven.** Tell the story of this person's product thinking — where they have conviction, where they're uncertain, where their assumptions are untested.
- **Actionable.** End with specific recommendations — what to test, what to decide, what to discuss with the team.
- **Honest.** If clarity is low, say so. If assumptions are untested, flag them. The value is in the candor, not in validation.

The brief structure (from strategy.md):
1. **Executive Summary** — 3-4 sentences, the headline
2. **Priority Ranking** — Product areas ranked with conviction tiers
3. **Detailed Analysis** — Per-area breakdown with the 5 dimension scores, stated vision, key strength, key gap
4. **Assumptions Exposed** — Table of untested beliefs with evidence level and resolution path
5. **Dependencies** — How product areas relate (what enables what)
6. **Strategic Tensions** — Where stated beliefs conflict
7. **Recommendations** — Immediate actions, assumptions to test, team alignment questions
8. **Interview Transcript** — Collapsed full Q&A

### VERIFY: Quality Check

Before delivering, verify:
- Does the executive summary stand alone? Could someone read just that and understand the picture?
- Are the recommendations specific enough to act on this week?
- Would you post this on LinkedIn? If not, rewrite until you would.
- Are scores justified with evidence from the interview, not assumed?

### Deliver

Save artifacts if file writing is available:
- `product-roadmap-{slug}.md` — the brief
- `product-roadmap-{slug}.json` — structured data

Present the priority ranking and offer next steps:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  ASSESSMENT COMPLETE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  [Name] · [Role] · [Date]
  Final Ambiguity: [score]%

  #1  [area]  · [tier]  · [composite]
  #2  [area]  · [tier]  · [composite]
  #3  [area]  · [tier]  · [composite]

  Next: Run this with other team members to
  compare visions and find alignment gaps.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

</Steps>

<Examples>

<Good>
Think cycle before a question:
```
━━━ Thinking ━━━

All cells are at 0.0 — this is round 1. The highest-leverage
first question is about core product vision, because the answer
will inform Vision scores across all three product areas AND
reveal whether this person sees Clockchain as infrastructure or
a product.

I'll ask what the core product is — not the technology, but
what a customer buys. The options should represent genuinely
different product framings: infrastructure play, identity
product, trust layer, or time-as-a-service.
```
Why good: Shows strategic reasoning about WHY this question, not just WHAT question. The interviewee sees a thoughtful process.
</Good>

<Good>
Analysis after an answer:
```
━━━ Analysis ━━━

What this tells me: You see Agent Identity as the product and the
Network as infrastructure underneath it. That's a significant
framing — it means the Network is a cost center that enables
the revenue-generating identity layer. Most blockchain projects
think of the network itself as the product.

Assumption surfaced: This assumes AI platforms will pay for
third-party identity services rather than building their own.
That's a big assumption — OpenAI, Anthropic, and Google all
have the resources to build in-house agent identity.

Tension: In your intake you said your focus is "all areas
equally," but this answer clearly prioritizes Agent Identity
over the other two. That's useful — it suggests you have a
stronger opinion than "all equal" once pushed.

Scoring:
  Agent Identity × Vision: 0.0 → 0.5
    Because: Clear directional view, but "customers will pay"
    is unvalidated — no named buyers
  Network × Vision: 0.0 → 0.3
    Because: Framed as infrastructure, not product — but even
    the infrastructure vision is vague (what kind of infra?)
```
Why good: Substantive, connects to prior answers, names the specific assumption being made, explains scores with reasoning.
</Good>

<Good>
Question with well-crafted options:
```
Round 4 · Ambiguity: 62%

You've said Agent Identity is the product layer and the Network is
infrastructure. But Cronos already has an AI Agent SDK with a Proof
of Identity standard — and it's live, not on testnet.

What gives Clockchain the right to win the agent identity market
despite being later?

a) The time oracle — our DIDs are anchored to cryptographically
   verifiable timestamps, which Cronos can't replicate. Provenance
   isn't just identity, it's WHEN.
b) Patent protection — our US patent on blockchain timekeeping
   creates a legal moat that Cronos can't route around.
c) We don't compete with Cronos directly — they're SDK-first
   (developer tool), we're network-first (infrastructure).
   Different layers.
d) Honestly, I'm not sure we have a clear answer to this yet.
   We need to figure out our Cronos differentiation story.
e) Other (specify)
```
Why good: Uses specific competitive intel (Cronos, named and real). Each option implies a different competitive strategy. Option (d) is honest and score-relevant. The question itself builds on prior answers.
</Good>

<Bad>
No think cycle:
```
Question 1: What is Clockchain's core product?
a) Time oracle
b) Agent identity
c) Smart contracts
d) All of the above
```
Why bad: No reasoning shown. Generic options. "All of the above" is lazy — it doesn't reveal anything.
</Bad>

<Bad>
Batching questions:
```
Let me ask you about all three product areas:
1. What's your vision for the Network?
2. What about Agent Identity?
3. And Smart Contracts?
```
Why bad: Three questions at once. Causes shallow answers. Makes scoring impossible. Violates the one-question rule.
</Bad>

<Bad>
Shallow analysis:
```
Thanks for your answer. Updating scores.
Network Vision: 0.0 → 0.5
Moving on to the next question.
```
Why bad: No analysis of what the answer reveals. No assumptions named. No tensions flagged. This is a quiz, not an assessment.
</Bad>

</Examples>

<Escalation_And_Stop_Conditions>
- If the interviewee can't articulate what the product IS after several vision-targeting rounds, flag it explicitly in the analysis
- If ambiguity stalls (same score ±5% for 3 rounds), shift approach or offer to wrap up
- If two product areas score identically, probe dependencies — which enables the other?
- If all areas score below 0.4, recommend a product strategy offsite
- If the interviewee defaults to "all equally important" repeatedly, challenge directly
- Early exit always available — show ambiguity and proceed with warning if above 20%
</Escalation_And_Stop_Conditions>

<Final_Checklist>
- [ ] Intake collected with multiple-choice options
- [ ] Company context loaded from knowledge.md (not displayed as a dump)
- [ ] Every round followed THINK → ACT → VERIFY cycle
- [ ] Exactly ONE question per round — never batched
- [ ] Every question had 3-4 multiple-choice options plus "Other (specify)"
- [ ] Substantive analysis after every answer (what it reveals, assumptions, tensions)
- [ ] Scoring matrix with justification displayed after every round
- [ ] Challenge modes used at natural points (not rigidly by round number)
- [ ] Interview ended at clarity threshold or user's request
- [ ] Final brief is LinkedIn-publishable quality — narrative, not data dump
- [ ] Recommendations are specific enough to act on this week
- [ ] All 15 scoring cells have evidence-backed justifications
- [ ] Assumptions table and dependency map included
</Final_Checklist>

Task: {{ARGUMENTS}}
