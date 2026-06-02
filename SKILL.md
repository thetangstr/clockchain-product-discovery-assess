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
5. **Use the structured picker UI.** If you have access to `AskUserQuestion` (Claude Code), use it for EVERY question — intake and interview. If unavailable, present lettered options in text. Never present choices as a plain "reply A or B" — always use the clickable picker when the tool exists.
6. **LinkedIn-quality output.** The final brief should be polished, insightful, and publishable — not a raw data dump.

</Execution_Policy>

<Steps>

## Phase 1: Intake

Collect via structured questions. Use `AskUserQuestion` (or equivalent structured picker UI) for each question — one at a time, waiting for each answer before proceeding to the next:

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

### How This Works — Message Boundaries

**This is the most important section in the entire skill. Read it carefully.**

The interview is a CONVERSATION. Each message you send to the user contains exactly ONE question. Then you STOP and WAIT for their answer. You do NOT generate multiple questions. You do NOT generate illustrative answers. You do NOT skip ahead to the roadmap.

**Your first interview message contains:**
1. The interview header (shown below)
2. A "Thinking" block explaining your reasoning for the first question
3. ONE question via `AskUserQuestion` with 3-4 options
4. NOTHING ELSE. End your message. Wait for the user's answer.

**Every subsequent message (after receiving an answer) contains:**
1. Analysis of their answer (what it reveals, assumptions, tensions)
2. Scoring changes with justification
3. Updated scoring matrix
4. A "Thinking" block explaining your reasoning for the NEXT question
5. ONE question via `AskUserQuestion` with 3-4 options
6. NOTHING ELSE. End your message. Wait for the user's answer.

**When ambiguity reaches ≤ 20% (or user exits), your next message contains:**
1. Analysis of the final answer
2. Final scoring matrix
3. The full product roadmap brief (Phase 4)

**Things you must NEVER do:**
- Never ask more than one question per message
- Never list questions for the user to "answer all at once"
- Never generate answers on the user's behalf ("illustrative" or otherwise)
- Never skip ahead to the roadmap before the interview is done
- Never present questions as plain text — always use `AskUserQuestion`
- **Never say "Question X of Y" or "Q1 of 8" or any numbered-of-total format.** There is NO fixed number of questions. The interview is adaptive — it ends when clarity is sufficient, not after a set count.
- **Never create a "Pre-Interview Baseline" phase.** There is NO baseline phase. Phase 2 is context loading (silent — you read knowledge.md). Phase 3 is the interview. Go directly from context loading to your first interview question.
- **Never invent phases, sub-phases, or step numbers that are not in this file.** Follow the 4 phases defined here exactly: Intake → Context Loading → Adaptive Interview → Product Brief. Nothing else.

### Interview Header (display once, in your first interview message)

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  PRODUCT DISCOVERY INTERVIEW
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  One question at a time. Pick an option or
  write your own. After each answer I'll share
  what I'm learning and show your clarity scores.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Scoring Matrix (initialize internally, all cells at 0.0)

| | Vision (30%) | Market (20%) | Technical (20%) | Priority (15%) | Risk (15%) |
|---|---|---|---|---|---|
| **Network** | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 |
| **Agent Identity** | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 |
| **Smart Contracts** | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 |

**Composite formula:** `vision × 0.30 + market × 0.20 + technical × 0.20 + priority × 0.15 + risk × 0.15`
**Ambiguity:** `1 - average(composite_network, composite_identity, composite_contracts)`
**Tiers:** Ready (≥ 0.70) · Emerging (0.40–0.69) · Not Ready (< 0.40)

### The Thinking Block

Before EVERY question, write a visible "Thinking" block that shows your strategic reasoning. This is what makes the assessment feel like a conversation with a thoughtful strategist.

```
━━━ Thinking ━━━

[Which cell is weakest and why. What you don't know yet.
What assumption from the prior answer needs probing.
What tension exists. Why THIS question is the highest-leverage
one right now.]
```

In early rounds when all cells are 0.0, think about which foundational question will illuminate the MOST cells at once.

### Asking a Question

Use `AskUserQuestion` with 3-4 options. If `AskUserQuestion` is unavailable, present lettered options — but NEVER as "reply A or B". Always use the structured picker when the tool exists.

Show the round number and current ambiguity:

```
Round [n] · Ambiguity: [score]%
```

**How to write good options:**
- Each option implies a DIFFERENT strategic direction
- Draw from: knowledge.md product areas, named competitors, prior answers, real tensions
- One option acknowledges uncertainty ("I haven't thought about this" / "I'm not sure")
- No obviously "right" answer — all options should feel legitimate
- Specific enough that choosing one tells you something concrete

### Analyzing an Answer — Full Re-evaluation

After receiving the answer, do NOT just score the latest answer in isolation. **Re-evaluate the ENTIRE interview transcript so far** — every prior answer together with the new one. This is the deep-interview pattern: each round's scoring considers the full picture, not just the delta.

#### Step 1: Check answer quality — Push or Accept?

Before scoring, evaluate whether the answer is SPECIFIC ENOUGH to score. Use these criteria:

**Push until you hear:**
- Vision: A one-sentence product statement that a customer could understand. Named outcome. Named buyer.
- Market: Specific company names, named people, dollar amounts, evidence of demand (not "the market needs this").
- Technical: Named dependencies, concrete timelines, specific blockers (not "we'll figure it out").
- Priority: A forced-rank with reasoning, not "all equally important."
- Risk: Named failure modes with trigger signals (not "nothing can go wrong").

**Red flags — push harder if you hear these:**
- "The market is huge" → Ask: "Who specifically?"
- "People are interested" → Ask: "Who would be genuinely upset if this disappeared?"
- "We just need to execute" → Ask: "Execute on what, specifically?"
- "All areas are equally important" → Challenge: "Equal priority means no priority. What ships first if you can only fund one?"
- "We'll figure out the customer later" → Push: "Name one person who would pay today."
- "The technology speaks for itself" → Push: "Technology doesn't buy things. Who writes the check?"

**If the answer is too vague:** Don't score it up. Instead, your NEXT question should push on the SAME cell — reframed to demand more specificity. Say: "I want to push on this. [Reason the answer was vague]. Can you be more specific?"

**If the answer is specific and evidence-backed:** Score it up and move to the next weakest cell.

#### Step 2: Full-transcript analysis

Write substantive analysis that considers ALL prior answers together:

```
━━━ Analysis ━━━

What this tells me: [2-3 sentences. What mental model does this
reveal? How does this fit with EVERYTHING they've said so far?
What picture is emerging across all rounds?]

Assumption surfaced: [Name the untested belief. "You're assuming X,
which implies Y. Has Y been validated?"]

Tension: [Does this contradict ANY prior answer? Reference the
specific round. Or: note how it's consistent and what pattern
is forming across answers.]

Push-back: [If the answer hit a red flag, state it directly.
"You said 'the market needs this' — that's a hypothesis, not
evidence. I'll push on this next."]
```

#### Step 3: Re-score the ENTIRE matrix

Re-evaluate ALL 15 cells in light of the full transcript. Not just the cell the question targeted — an answer about Vision might reveal something about Risk or Priority too. An answer that contradicts a prior answer might cause a PREVIOUS score to go DOWN.

```
Scoring (full re-evaluation):
  [Cell]: [old] → [new] — [one sentence why, citing specific rounds]
  [Cell]: [old] → [new] — [revised because Round N contradicted Round M]

| | Vision | Market | Technical | Priority | Risk | Composite | Tier |
|---|---|---|---|---|---|---|---|
| Network | [s] | [s] | [s] | [s] | [s] | [c] | [tier] |
| Agent ID | [s] | [s] | [s] | [s] | [s] | [c] | [tier] |
| Smart Contracts | [s] | [s] | [s] | [s] | [s] | [c] | [tier] |

Ambiguity: [score]% → target ≤ 20%
```

**Scores can go DOWN.** If Round 5 contradicts Round 2, the cell that Round 2 improved should be re-evaluated. This is what makes the assessment honest.

Use the scoring rubrics from knowledge.md:
- **0.0–0.3:** Vague, no evidence, untested assumption
- **0.4–0.6:** Directional, some reasoning but gaps remain
- **0.7–0.8:** Clear, evidence-backed, specific
- **0.9–1.0:** Crystal clear, customer-validated, testable

### Challenge Modes

At natural points (not rigidly by round number), shift perspective:

- **Contrarian:** When too certain — "What if the opposite were true?"
- **Simplifier:** When scope expanding — "What's the simplest version that's still valuable?"
- **Competitor:** When differentiation assumed — "If [competitor] ships this next month, what do you have?"

Use each at most once.

### Exit Conditions

- **Ambiguity ≤ 20%:** Proceed to Phase 4
- **All 15 cells ≥ 0.5:** Sufficient coverage — proceed
- **User says "enough" / "wrap up":** Show ambiguity, warn if above 20%, proceed
- **Stall (no improvement for 3 rounds):** Offer to wrap up

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
  ASSESSMENT COMPLETE — [Name]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  [Name] · [Role] · [Date]
  Final Ambiguity: [score]%

  #1  [area]  · [tier]  · [composite]
  #2  [area]  · [tier]  · [composite]
  #3  [area]  · [tier]  · [composite]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

Then ask via `AskUserQuestion`:

"Assessment saved. What's next?"
- a) **Assess another team member** — run the assessment again with a different person in this same session. After all members are done, I'll generate a team comparison report.
- b) **Generate team comparison now** — if other assessments already exist (product-roadmap-*.json), compare them and produce the alignment report.
- c) **Done for now** — just save this assessment and stop.

---

## Phase 5: Team Comparison (when multiple assessments exist)

**Prerequisite:** 2+ completed assessments in this session (product-roadmap-*.json files).

When the user chooses "Assess another team member," loop back to Phase 1 (Intake) for the new person. Keep all prior assessment files. The scoring matrix resets to 0.0 for the new interviewee — each person gets a fresh assessment.

When the user chooses "Generate team comparison" or after the last team member finishes:

### THINK: Compare

Before writing, reason through:
- Where do the team members AGREE on priority ranking? (Strong signal — build there first)
- Where do they DISAGREE? (Must resolve before committing resources)
- Which product area has the widest score spread? (Biggest alignment gap)
- Are there hidden assumptions one person holds that another has already challenged?

### ACT: Write the Team Alignment Report

Use the Cross-Interviewee Comparison Template from strategy.md. The report should include:

1. **Priority ranking comparison** — side-by-side rankings from each person
2. **Conviction tier comparison** — do they agree on what's Ready vs. Not Ready?
3. **Biggest disagreements** — dimension-level score deltas > 0.3
4. **Strongest agreements** — dimension-level score deltas < 0.1
5. **Vision alignment analysis** — where they agree/disagree on WHAT the product is
6. **Composite team roadmap** — averaged scores with alignment scores
7. **Recommended alignment actions** — what to resolve, what to discuss, what to preserve

Save to `team-comparison-clockchain.md` and `team-comparison-clockchain.json`.

### Deliver

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  TEAM COMPARISON COMPLETE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  Compared: [Name 1], [Name 2], ...
  Team Alignment Score: [score]%

  CONSENSUS RANKING:
  #1  [area]  · [avg composite]  · [aligned? yes/no]
  #2  [area]  · [avg composite]  · [aligned? yes/no]
  #3  [area]  · [avg composite]  · [aligned? yes/no]

  MUST RESOLVE: [biggest disagreement area]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

</Steps>

<Tool_Usage>
- **AskUserQuestion** (or equivalent structured picker): Use for EVERY question — intake and interview. This gives the interviewee clickable options, not plain text letters. The "Other" option with free-text input is built into the tool automatically.
- **Write**: Save the final roadmap brief as markdown and JSON artifacts.
- **Read**: Load knowledge.md and strategy.md at the start.
- If `AskUserQuestion` is not available (e.g., ChatGPT, plain Claude.ai), fall back to lettered options in text — but always present structured choices, never "reply A or B."
- No external dependencies. No plugins. No API calls. This skill is fully self-contained.
</Tool_Usage>

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

<Good>
Red flag triggered — push back on same cell:
```
━━━ Analysis ━━━

What this tells me: You said "the market needs agent identity."
That's a category-level claim, not evidence of demand.

RED FLAG: "AI agents need identity" — matches knowledge.md red flag
for Agent Identity. "Everyone says this. WHO needs it? Which agent
platform has told you they need it?"

Assumption surfaced: You're assuming demand exists because the
concept sounds logical. But logical ≠ validated. No named customer,
no expressed willingness to pay, no evidence of pain without identity.

Tension: In Round 1 you were more specific — you named agent
platforms as the product layer. But here you've retreated to
"the market" which is vaguer. Score goes DOWN.

Push-back: I'm staying on this cell. The answer wasn't specific
enough to score up.

Scoring (full re-evaluation):
  Agent Identity × Market: 0.4 → 0.3 — DOWNGRADE. Round 2 named
    framework devs as buyers (specific). Round 3 retreated to "the
    market needs this" (vague). Net: less clarity than before.
  Agent Identity × Vision: 0.55 → 0.55 — unchanged
  Agent Identity × Risk: 0.2 → 0.15 — slight downgrade, inability
    to name demand signals IS a risk signal

[matrix...]

Ambiguity: 86% → 88% — went UP because clarity decreased

━━━ Thinking ━━━

Agent Identity × Market dropped from 0.4 to 0.3. The answer hit
a red flag — vague market claim with no evidence. I need to push
on the SAME cell. I'll reframe to force specificity: name an
actual company or person.

Round 4 · Ambiguity: 88%
```
[AskUserQuestion: "I want to push on this. You said 'the market
needs agent identity' but that's a hypothesis, not evidence. Can
you name ONE specific company or person who has told you they need
agent DIDs — not 'is interested,' but would be upset if Clockchain
didn't exist?"]
Why good: Red flag explicitly named. Score went DOWN (0.4 → 0.3). Pushed on the SAME cell instead of moving on. Question demands specific evidence. Ambiguity went UP because clarity decreased — the assessment is honest.
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
