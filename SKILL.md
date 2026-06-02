---
name: assess-clockchain-product
description: Product discovery assessment for Clockchain's future product direction
level: 3
---

<Purpose>
Assess what Clockchain's future product should be by interviewing founding team members through an adaptive Socratic process. Collect interviewee intake, load company context, gather pre-interview baseline, then run an adaptive interview that scores clarity across three product areas and five functional dimensions. The output is a priority-ranked product roadmap with conviction tiers showing where the team has clarity and where assumptions remain unresolved.
</Purpose>

<Use_When>
- User wants to assess product direction for Clockchain
- User says "product discovery", "what should we build", "assess our product thinking", "product direction assessment"
- Founding team member wants to crystallize their vision for Clockchain's future
- Team wants to compare product thinking across founders to find alignment and divergence
- User wants structured product discovery before committing to a roadmap
</Use_When>

<Do_Not_Use_When>
- User already has a detailed product spec or PRD — execute directly
- User wants to assess agentic workflow readiness — use assess-agentic instead
- User wants a quick opinion on a single product question — answer directly
- User wants competitive intelligence or market research only — this is product discovery, not market analysis
</Do_Not_Use_When>

<Why_This_Exists>
Clockchain is at a critical product inflection point: pre-MainNet, pre-revenue, pivoting from "time for Web3" to "time as the trust substrate for AI agents." The founding team each carry different mental models of what the product should become. This skill applies mathematical clarity gates to surface hidden assumptions, expose divergent visions, and produce a priority-ranked roadmap grounded in the team's actual conviction levels — not just the loudest voice in the room.
</Why_This_Exists>

<Execution_Policy>
- Collect intake FIRST, then load context, then interview — do not skip phases
- Frame the interview with product discovery context: three product areas, five functional dimensions, vision-heavy weighting
- After the interview, format the output as a priority-ranked product roadmap
- Use the product discovery frameworks (knowledge.md) to inform interview framing and scoring
- Use the roadmap templates (strategy.md) to structure the output
- Discovery-first: do NOT seed specific question themes — let the interview find tensions organically
- Ask ONE question at a time — never batch multiple questions
- Score ambiguity after every answer — display the score transparently
- Target the WEAKEST product area × dimension pair with each question
- Challenge assumptions, not just gather feature lists
</Execution_Policy>

<Steps>

## Phase 1: Interviewee Intake

### Phase 1 Header

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PHASE 1 OF 4 — INTERVIEWEE INTAKE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Clockchain Product Discovery Assessment
Collecting interviewee parameters.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Intake Collection

Collect all fields via structured questions:

1. **Interviewee Name** — Full name of the team member being assessed.
2. **Role** — Select one:
   - `CEO / Co-founder` — Strategic vision and business direction
   - `Head of AI Products` — Product and technical direction for agentic use cases
   - `CTO / Technical Co-founder` — Network architecture and technical feasibility
   - `Other` — Specify role and area of focus
3. **Primary focus area** — Which product area does this person think about most? (Used to calibrate question depth, not to limit scope):
   - `Network (time oracle / DePIN)` — The core infrastructure layer
   - `Agent Identity (DIDs / birth certificates)` — On-chain agent identity and provenance
   - `Smart Contracts & Receipts` — Verifiable receipts and on-chain agent actions
   - `All areas equally` — No primary focus; thinks across the full product

### Phase 1 Complete Gate

After all fields are collected, present a confirmation summary:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
INTAKE CONFIRMED
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  Interviewee:    [name]
  Role:           [role]
  Primary focus:  [focus_area]
  Company:        Clockchain (D4D Sarl / D4D Group)

Proceeding to context loading.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Phase 2: Context Loading

**Prerequisite:** Phase 1 must be fully complete.

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PHASE 2 OF 4 — CONTEXT LOADING
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Loading Clockchain company and competitive context.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Company Context

Load the following context (read from knowledge.md for full details):

- **Company:** Clockchain (D4D Sarl, Neuchatel, Switzerland / D4D Group, San Francisco)
- **Stage:** Pre-MainNet, pre-revenue, pre-TGE
- **Core IP:** US patent for blockchain-based timekeeping
- **FINMA-approved token sale**
- **Public testnet** live since 2026-02-23
- **Strategic pivot:** From "time for Web3" to "time as the trust substrate for AI agents"
- **Competitors:** Sahara AI, 0G Labs, Sentient, Story Protocol, Cronos AI Agent SDK, Eliza framework
- **Differentiation:** None of these competitors anchor their identity primitive on a patented time oracle

---

## Phase 3: Adaptive Product Discovery Interview

**Prerequisite:** Phase 2 must be fully complete (company context loaded).

### Phase 3 Header

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PHASE 3 OF 4 — PRODUCT DISCOVERY INTERVIEW
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Adaptive Socratic interview. One question at a time.
Targeting the weakest clarity area with each question.
I'll show your clarity scores after every answer.
We stop when clarity is high enough — could be 5
rounds or 15, depending on your answers.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Interview Setup

Initialize a 3×5 scoring matrix (all cells start at 0.0):

| | Vision (30%) | Market (20%) | Technical (20%) | Priority (15%) | Risk (15%) |
|---|---|---|---|---|---|
| **Network** | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 |
| **Agent Identity** | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 |
| **Smart Contracts** | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 |

Set initial ambiguity to 100%.

The interview has NO fixed number of rounds. Early rounds will naturally cover foundational questions (what is the product, who is the customer, what's the priority) because those cells start at 0.0 and will be the weakest. As clarity builds, questions get more specific and probing. The interview ends when ambiguity drops below 20% — that might take 5 rounds or 15.

### Interview Loop

Repeat until ambiguity ≤ 20% OR user exits early:

#### Step 3a: Identify Weakest Cell

Find the product area × dimension pair with the lowest score. When multiple cells are tied, rotate across product areas (don't drill the same area repeatedly).

#### Step 3b: Generate & Ask Question

Generate ONE question targeting the weakest cell. Use the question styles and tension-surfacing techniques from knowledge.md.

Present each question with context:

```
Round [n] | [Product Area] × [Dimension] | Ambiguity: [score]%

[Question text]
```

Provide 3-4 multiple-choice options plus free-text. Options should represent genuinely different perspectives, not leading choices. Include at least one option that challenges the interviewee's likely assumption.

#### Step 3c: Score the Answer

After receiving the answer, update the relevant cell(s) in the scoring matrix. Use the scoring rubrics from knowledge.md:

- **0.0–0.3:** Vague, no evidence, untested assumption
- **0.4–0.6:** Directional, some reasoning but gaps remain
- **0.7–0.8:** Clear, evidence-backed, specific
- **0.9–1.0:** Crystal clear, customer-validated, testable

A single answer may improve multiple cells if it touches multiple dimensions or product areas. Score each affected cell independently.

#### Step 3d: Calculate & Display Progress

Calculate composite score per product area:
```
composite = vision × 0.30 + market × 0.20 + technical × 0.20 + priority × 0.15 + risk × 0.15
```

Calculate overall ambiguity:
```
ambiguity = 1 - average(composite_network, composite_identity, composite_contracts)
```

Classify each product area into a conviction tier:
- **Ready to Build:** composite ≥ 0.70
- **Emerging:** composite 0.40 – 0.69
- **Not Ready:** composite < 0.40

Display the updated matrix after each round:

```
━━━ Round [n] Complete ━━━

| | Vision | Market | Technical | Priority | Risk | Composite | Tier |
|---|---|---|---|---|---|---|---|
| Network | [s] | [s] | [s] | [s] | [s] | [c] | [tier] |
| Agent ID | [s] | [s] | [s] | [s] | [s] | [c] | [tier] |
| Smart Contracts | [s] | [s] | [s] | [s] | [s] | [c] | [tier] |

Ambiguity: [score]% | Target: ≤ 20%
Next target: [Product Area] × [Dimension] — [why this is the weakest]
```

#### Step 3e: Challenge Mode Triggers

At specific rounds, shift perspective:

- **Round 4+: Contrarian** — Challenge the interviewee's core assumption. "What if the opposite were true?"
- **Round 6+: Simplifier** — Probe whether complexity can be removed. "What's the simplest version that's still valuable?"
- **Round 8+: Competitor** — Pressure-test via competitive context. "If [competitor] ships this next month, what do you have that they don't?"

Each mode activates ONCE, then returns to normal Socratic questioning.

#### Step 3f: Exit Conditions

The interview ends when clarity is sufficient. There is NO fixed round count.

- **Ambiguity ≤ 20%:** Clarity threshold met — proceed to roadmap generation
- **All 15 cells ≥ 0.5:** Sufficient coverage — proceed even if ambiguity is slightly above 20%
- **Early exit:** If the user says "enough", "let's go", or "wrap up" — show the current ambiguity and proceed with a warning if it's above 20%
- **Stall detection:** If ambiguity doesn't improve for 3 consecutive rounds, offer to wrap up or shift approach

---

## Phase 4: Roadmap Generation & Delivery

**Prerequisite:** Phase 3 must complete (clarity threshold met or user chose early exit).

### Phase 4 Header

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PHASE 4 OF 4 — PRODUCT ROADMAP
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Generating priority-ranked product roadmap.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Step 1 — Generate the Roadmap

Using the final scoring matrix and all interview Q&A, generate the product roadmap using the template from strategy.md. Include:

1. **Priority ranking** — Product areas ranked by composite score
2. **Conviction tiers** — Each area classified as Ready / Emerging / Not Ready
3. **Detailed scoring matrix** — All 15 cells with evidence for each score
4. **Assumptions exposed** — Every untested belief surfaced during the interview
5. **Dependencies** — How the product areas relate to each other
6. **Strategic tensions** — Where the interviewee's stated beliefs conflict
7. **Recommendations** — Immediate actions, assumptions to test, questions for team alignment

### Step 2 — Save Artifacts

Write the roadmap as markdown. If file writing is available, save to:
- `product-roadmap-{interviewee_slug}.md` — Full roadmap report
- `product-roadmap-{interviewee_slug}.json` — Structured scoring data (use JSON schema from strategy.md)

If file writing is not available (e.g., Co-Work, web chat), output the full roadmap directly in the conversation.

### Step 3 — Present Results

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PRODUCT DISCOVERY ASSESSMENT COMPLETE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Clockchain Product Discovery Assessment
Interviewee: [name] ([role])
Date: [date]
Final Ambiguity: [score]%

PRIORITY-RANKED PRODUCT ROADMAP:

  #1  [area]  — [tier]  ([composite])
  #2  [area]  — [tier]  ([composite])
  #3  [area]  — [tier]  ([composite])

NEXT STEP:
Run this assessment with other team members to compare
product visions and find alignment vs. divergence.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

</Steps>

<Tool_Usage>
- Use structured questions (AskUserQuestion or equivalent) for intake and interview questions
- Provide 3-4 multiple-choice options per question plus free-text
- Score answers using the rubrics in knowledge.md
- Generate the roadmap using templates in strategy.md
- Save artifacts to files if file writing is available; otherwise output in conversation
- No external dependencies required — this skill is fully self-contained
</Tool_Usage>

<Examples>
<Good>
Discovery-first question that surfaces assumptions:
```
Round 3 | Agent Identity × Vision | Ambiguity: 68%

You said the primary customer is "AI agent platforms." Can you name
three specific platforms that would pay for Clockchain's time oracle
today? If you can't name three, what does that tell us about how
well we understand the customer?

a) LangChain, AutoGPT, CrewAI — they all need agent provenance
b) I can name one or two, but not three with confidence
c) Honestly, we haven't validated this with specific platforms yet
d) The customer isn't platforms — it's the enterprises deploying agents
```
Why good: Probes conviction depth. Forces the interviewee to test their own assumption. All four options represent genuinely different states of clarity.
</Good>

<Good>
Cross-product dependency probe:
```
Round 5 | Smart Contracts × Priority | Ambiguity: 52%

You've prioritized Agent Identity as #1. But birth certificates
require the Network to be live and smart contracts to be deployed.
Does Agent Identity actually depend on the other two being ready
first? Or can it stand alone?

a) It depends on both — Network and Smart Contracts must ship first
b) It depends on Network only — we can use existing smart contract platforms
c) It can stand alone — we can issue DIDs off-chain initially
d) I haven't thought through the dependency chain
```
Why good: Exposes dependency assumptions that could change the priority ranking. Option (d) is honest and score-relevant.
</Good>

<Good>
Contrarian mode challenge:
```
Round 4 | Network × Market | Ambiguity: 61% | CONTRARIAN MODE

You've said the time oracle is Clockchain's moat. But what if
accurate timestamps become a commodity? Ethereum already has
block.timestamp, Chainlink has time-based triggers, and NTP
serves most centralized use cases. What if your patent protects
an implementation nobody needs because "good enough" timestamps
are everywhere?

a) The patent covers more than just timestamps — it covers the consensus mechanism
b) "Good enough" timestamps aren't good enough for agent provenance — cryptographic proof matters
c) This is a real risk — we need to articulate why our timestamps are fundamentally different
d) Maybe the moat isn't the time oracle itself but what we build on top of it
```
Why good: Challenges the core assumption (time oracle = moat) with specific competitive evidence. All options lead to useful clarity, including the risk-acknowledging ones.
</Good>

<Good>
Scoring display after a round:
```
━━━ Round 6 Complete ━━━

| | Vision | Market | Technical | Priority | Risk | Composite | Tier |
|---|---|---|---|---|---|---|---|
| Network | 0.7 | 0.5 | 0.6 | 0.4 | 0.5 | 0.57 | Emerging |
| Agent ID | 0.8 | 0.4 | 0.5 | 0.6 | 0.3 | 0.56 | Emerging |
| Smart Contracts | 0.3 | 0.2 | 0.3 | 0.2 | 0.2 | 0.25 | Not Ready |

Ambiguity: 54% | Target: ≤ 20%
Next target: Smart Contracts × Market — lowest score at 0.2, no competitive awareness for receipt/attestation space
```
Why good: Transparent scoring after every round. Clear targeting rationale. The interviewee can see exactly where their thinking is strong vs. weak.
</Good>

<Bad>
Batching multiple questions:
```
What's your vision for the network? And how does agent identity fit in?
Also, what about smart contracts — are those a priority? And who's the customer?
```
Why bad: Four questions at once. Causes shallow answers and makes scoring impossible.
</Bad>

<Bad>
Leading question with an obvious "right" answer:
```
Don't you think Agent Identity should be the top priority given the
AI agent boom?

a) Yes, absolutely
b) Maybe
c) No
```
Why bad: Leading framing + options that signal which answer is "correct." Discovery-first means genuine exploration.
</Bad>

<Bad>
Accepting an assumption without probing:
```
User: "Agent identity is our #1 priority."
Assessor: "Great, let's move on to smart contracts."
```
Why bad: Accepted a product direction without probing conviction depth. Should ask "What evidence supports that? Can you name customers who've told you they need this?"
</Bad>
</Examples>

<Escalation_And_Stop_Conditions>
- If the interviewee can't articulate what the product IS after several vision-targeting rounds, flag it: "Vision Clarity is critically low — the core product identity is unresolved"
- If ambiguity stalls (same score ±5% for 3 consecutive rounds), offer to wrap up or shift approach
- If two product areas score identically, probe for dependencies: which one enables the other?
- If all areas score below 0.4, recommend a product strategy offsite before further development
- If the interviewee defaults to "all areas are equally important" on every question, challenge directly: "Equal priority means no priority. What ships first if you can only fund one?"
- Early exit: user can stop anytime — show current ambiguity and proceed with a warning if above 20%
</Escalation_And_Stop_Conditions>

<Final_Checklist>
- [ ] Intake collected (interviewee name, role, focus area)
- [ ] Company and competitive context loaded from knowledge.md
- [ ] Adaptive interview conducted with one question per round — no fixed round count
- [ ] Each question targeted the weakest product area × dimension cell
- [ ] 3-4 multiple-choice options provided per question (plus "Other" for free-text)
- [ ] Scoring matrix updated and displayed after every round
- [ ] Challenge modes activated at appropriate points (contrarian, simplifier, competitor)
- [ ] Interview completed when ambiguity ≤ 20% or user chose early exit
- [ ] Product roadmap generated with conviction tiers and priority ranking
- [ ] All 15 scoring cells have evidence-backed scores
- [ ] Assumptions exposed table included in the roadmap
- [ ] Dependencies between product areas mapped
- [ ] Roadmap delivered to user with next-step recommendation
</Final_Checklist>

Task: {{ARGUMENTS}}
