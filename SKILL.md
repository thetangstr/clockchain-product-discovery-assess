---
name: assess-clockchain-product
description: Product discovery assessment for Clockchain's future product direction
level: 3
---

<Purpose>
Assess what Clockchain's future product should be by interviewing founding team members through an adaptive Socratic process. Collect minimum intake (interviewee name, role), then hand off to the deep-interview skill for discovery-first requirements gathering — framed specifically for product direction across three product areas and five functional dimensions. The output is a priority-ranked product roadmap with conviction tiers showing where the team has clarity and where assumptions remain unresolved.
</Purpose>

<Use_When>
- User wants to assess product direction for Clockchain
- User says "product discovery", "what should we build", "assess our product thinking", "product direction assessment"
- Founding team member wants to crystallize their vision for Clockchain's future
- Team wants to compare product thinking across founders to find alignment and divergence
- User wants structured product discovery before committing to a roadmap
</Use_When>

<Do_Not_Use_When>
- User already has a detailed product spec or PRD — use the appropriate planning or execution skill directly
- User wants to assess agentic workflow readiness — use assess-agentic instead
- User wants a quick opinion on a single product question — answer directly
- User wants competitive intelligence or market research only — this is product discovery, not market analysis
</Do_Not_Use_When>

<Why_This_Exists>
Clockchain is at a critical product inflection point: pre-MainNet, pre-revenue, pivoting from "time for Web3" to "time as the trust substrate for AI agents." The founding team (Ken, Yang, Tetsuji) each carry different mental models of what the product should become. This skill applies mathematical clarity gates to surface hidden assumptions, expose divergent visions, and produce a priority-ranked roadmap grounded in the team's actual conviction levels — not just the loudest voice in the room.
</Why_This_Exists>

<Execution_Policy>
- Phase 0 detects all prerequisites. If any are missing, the skill attempts installation via Bash (npm, omc setup, omx setup). For omc setup / omx setup the user must run these in a separate terminal — the skill will prompt and wait.
- Collect intake FIRST, then hand off to deep-interview — do not skip intake
- Frame the deep-interview with product discovery seed context: three product areas, five functional dimensions, vision-heavy weighting
- Use `--standard` deep-interview depth for all assessments
- After deep-interview crystallizes, format the spec as a priority-ranked product roadmap
- pandoc is required for DOCX export — offer to install or skip, but do not silently continue
- Use the product discovery frameworks (knowledge.md) to inform interview framing
- Use the roadmap templates (strategy.md) to structure the output
- Discovery-first: do NOT seed specific question themes — let the interview find tensions organically
</Execution_Policy>

<Steps>

## Phase 0: Environment Verification

**Policy:** Check all prerequisites first. If anything is missing, offer to install it via Bash — the user will interact with the setup wizard if needed. Do not exit silently.

### Step 1: Detect active runtime

Execute in parallel:

```
omc --version 2>/dev/null | head -1
omx --version 2>/dev/null | head -1
```

### Step 2: Verify required executables

Execute in parallel:

```
pandoc --version 2>/dev/null | head -1
```

### Step 3: Present missing prerequisites with install options

After all checks complete, handle each missing item.

**If OMC is not found:**

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
OMC NOT FOUND — Two-Step Install
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Step 1: Installing OMC package now (takes 2-5 minutes on first run)...
```

Run via Bash:
```
npm i -g oh-my-claude-sisyphus@latest
```

After npm install completes, ask the user to confirm they've
run `omc setup` in a separate terminal, then proceed to
Step 4 to verify deep-interview.

**If OMX is not found:**

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
OMX NOT FOUND — Two-Step Install
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Step 1: Installing OMX package now...
```

Run via Bash:
```
npm install -g @openai/codex oh-my-codex
```

After npm install completes, ask the user to run `omx setup`
in a **separate terminal**, then confirm below.

**If pandoc is not found:**

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PANDOC NOT FOUND
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

pandoc is required to generate the DOCX deliverable.
```

Options (via AskUserQuestion):
1. **Show install instructions** — Display: `brew install pandoc` (macOS), `sudo apt-get install pandoc` (Linux)
2. **Skip DOCX** — Continue without DOCX export; markdown and JSON will still be produced
3. **Cancel and exit**

**If deep-interview is not found (after OMC/OMX installed):**

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
deep-interview NOT FOUND
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

The deep-interview skill is not available yet.
Please run the setup in a separate terminal, then confirm below.
```

Use `AskUserQuestion`:
1. **I've run `omc setup` / `omx setup` in a separate terminal — continue**
2. **Show instructions** — display: `omc setup` (OMC) or `omx setup` (OMX)
3. **Cancel and exit**

**If all prerequisites are confirmed present:** Proceed to Step 4.

### Step 4: Verify deep-interview is accessible

For OMC: Run `omc skills list 2>/dev/null | grep deep-interview`.
For OMX: Run `omx skills list 2>/dev/null | grep deep-interview`.

If deep-interview still not found, go back to the deep-interview not found step above.

### Step 5: Set runtime context

Record the following variables:

| Variable | OMC Value | OMX Value |
|----------|-----------|-----------|
| `runtime` | `OMC` | `OMX` |
| `runtime_host` | `Claude Code` | `Codex` |
| `runtime_output_dir` | `.omc/specs` | `.omx/specs` |

---

**Phase 0 Complete Gate:** Proceed to Phase 1 only when OMC or OMX is confirmed, deep-interview is confirmed available, and the user has chosen how to handle pandoc.

---

## Phase 1: Interviewee Intake

**Prerequisite:** Phase 0 must be fully complete. Do not begin intake until the environment verification gate passes.

### Phase 1 Header

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PHASE 1 OF 5 — INTERVIEWEE INTAKE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Clockchain Product Discovery Assessment
Collecting interviewee parameters.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Intake Collection

Collect all fields via `AskUserQuestion` using a multi-question form:

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

Proceed to Phase 2 only after presenting this confirmation.

---

## Phase 2: Context Loading

**Prerequisite:** Phase 1 must be fully complete with all intake fields confirmed.

### Phase 2 Header

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PHASE 2 OF 5 — CONTEXT LOADING
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Loading Clockchain context and competitive landscape.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Context Protocol

1. **Load existing project context:**
   - Read `.omc/specs/assess-clockchain.md` if it exists (prior readiness assessment)
   - Read `.omc/specs/assess-clockchain.json` if it exists (structured data)
   - Note key findings: AI maturity scores, pilot roadmap, pre-kickoff blockers
2. **Load company context:**
   - Company: Clockchain (D4D Sarl, Neuchatel, Switzerland / D4D Group, San Francisco)
   - Stage: Pre-MainNet, pre-revenue, pre-TGE
   - Core IP: US patent for blockchain-based timekeeping
   - FINMA-approved token sale
   - Public testnet live since 2026-02-23
3. **Load competitive landscape:**
   - Sahara AI — economic and coordination layer for agents
   - 0G Labs — "the blockchain for AI agents" (modular storage + compute + DA)
   - Sentient — open-source AI Layer 1
   - Story Protocol — ATCP/IP framework for agent-to-agent IP trading
   - Cronos AI Agent SDK — Proof of Identity standard for agents
   - Eliza framework — agent runtime with built-in wallet
4. **Note Clockchain's differentiation:** None of these competitors anchor their identity primitive on a patented time oracle. The wedge is time provenance as the trust substrate.

### Context Output

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
CONTEXT LOADED
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  Company:          Clockchain (D4D Sarl / D4D Group)
  Stage:            Pre-MainNet, pre-revenue, pre-TGE
  Core IP:          US patent — blockchain timekeeping
  Differentiation:  Time provenance as trust substrate
  Competitors:      6 identified (Sahara AI, 0G Labs,
                    Sentient, Story Protocol, Cronos, Eliza)
  Prior assessment: [found | not found]

Proceeding to pre-interview context.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Phase 2 Complete Gate

Proceed to Phase 2b only after the context is loaded and displayed.

---

## Phase 2b: Pre-Interview Product Context

**Prerequisite:** Phase 2 must be fully complete with context loaded and displayed.

### Phase 2b Header

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PHASE 2b OF 5 — PRE-INTERVIEW PRODUCT CONTEXT
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Before the structured interview, we need to establish
your current product thinking baseline. These questions
define your starting position.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Context Questions

Present as a structured form. All eight questions are mandatory. Frame each as shown:

**PRODUCT VISION**

1. **In one sentence, what is Clockchain's core product?**
   *(Not the technology — the product. What does a customer buy, and what outcome do they get?)*

2. **Who is Clockchain's primary customer in the next 12 months?**
   *(Web3 developers? AI agent platforms? Enterprise? Crypto traders? Be specific about who pays.)*

3. **What is the single most important thing Clockchain must get right to succeed?**
   *(Not a feature list — the one thing that, if you nail it, everything else follows.)*

**PRODUCT PRIORITIES**

4. **Which product area keeps you up at night — and why?**
   *(Network infrastructure? Agent identity/DIDs? Smart contracts? What feels most uncertain or most critical?)*

5. **If you could only ship ONE product area in the next 6 months, which would it be?**
   *(Forces a priority call. No "all of them" — pick one and explain why.)*

6. **What is the biggest open question about Clockchain's product that you don't have an answer to yet?**
   *(The thing you'd love to have clarity on but currently don't.)*

**COMPETITIVE POSITION**

7. **How does Clockchain's time oracle create value that competitors cannot replicate?**
   *(Sahara AI, 0G Labs, Sentient, Story Protocol, Cronos, Eliza are all in the agent-on-chain space. What's the moat?)*

8. **What would make you abandon the current product direction entirely?**
   *(What signal — from the market, technology, or team — would cause a pivot? If nothing would, why not?)*

### Phase 2b Complete Gate

After all eight questions are answered, present:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PRE-INTERVIEW CONTEXT — CONFIRMED
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  Core product:         [answer]
  Primary customer:     [answer]
  Must get right:       [answer]
  Biggest concern:      [answer]
  Top priority area:    [answer]
  Open question:        [answer]
  Competitive moat:     [answer]
  Pivot trigger:        [answer]

Proceeding to structured interview.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

Inject all eight answers into the Phase 3 seed prompt. The deep-interview must not re-ask these questions — it builds on this context.

---

## Phase 2c: Market & Technology Research

**Prerequisite:** Phase 2b must be fully complete with all context questions answered.

### Phase 2c Header

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PHASE 2c OF 5 — MARKET & TECHNOLOGY RESEARCH
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Researching current market context for each product area.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Policy:** This phase is mandatory. Do not skip or abbreviate. Interview questions are sharpened by current market intelligence.

### Research Scope

Research each of the three product areas:

| Product Area | Research Questions |
|---|---|
| **Network (Time Oracle / DePIN)** | DePIN market size and growth? Competing time oracle or timestamp solutions? Oracle networks (Chainlink, API3, Pyth) — how do they handle time? Blockchain timestamp manipulation attacks and mitigations? |
| **Agent Identity (DIDs / Birth Certificates)** | W3C DID standard adoption? Competing agent identity solutions (Cronos PoI, Story Protocol ATCP/IP)? Enterprise demand for AI agent provenance and auditability? Regulatory signals on AI agent identification? |
| **Smart Contracts & Receipts** | On-chain receipt/attestation standards (EAS, Verax)? Agent action logging solutions? Competing smart contract platforms for agent operations? Gas cost benchmarks for attestation-heavy workloads? |

**Search commands:**
```
WebSearch: "DePIN time oracle blockchain 2026"
WebSearch: "AI agent identity DID blockchain 2026"
WebSearch: "on-chain attestation agent actions 2026"
WebSearch: "decentralized agent identity standard"
```

### Research Output

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
MARKET RESEARCH — CLOCKCHAIN PRODUCT AREAS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  Network (Time Oracle / DePIN):
  [2-3 sentence summary of competitive landscape]

  Agent Identity (DIDs / Birth Certificates):
  [2-3 sentence summary of competitive landscape]

  Smart Contracts & Receipts:
  [2-3 sentence summary of competitive landscape]

  Key Insight:
  [1-2 sentences on the most important finding]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Time limit:** 10 minutes maximum. Record findings and note gaps for the interview to probe.

### Phase 2c Complete Gate

Proceed to Phase 3 only when the Market Research output is written and displayed.

---

## Phase 3: Structured Interview — Deep Interview

**Prerequisite:** Phases 1, 2, 2b, and 2c must ALL be fully complete.

### Phase 3 Header

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PHASE 3 OF 5 — STRUCTURED PRODUCT DISCOVERY INTERVIEW
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Initiating deep-interview for [interviewee_name].
This phase uses a Socratic methodology to surface
hidden assumptions, expose conviction levels, and
score clarity across product areas and dimensions.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Invocation

**For OMC (Claude Code):**
```
Skill("oh-my-claudecode:deep-interview", "--standard Clockchain product discovery assessment for [interviewee_name]")
```

**For OMX (Codex):**
```
$deep-interview "--standard Clockchain product discovery assessment for [interviewee_name]"
```

### Seed Prompt Construction

Include all prior phase outputs:

```
--standard Clockchain product discovery assessment for [interviewee_name]

This is a PRODUCT DISCOVERY assessment, not an agentic readiness assessment.
The goal is to discover what Clockchain's future product should be by probing
the interviewee's product thinking across three product areas and five
functional dimensions.

Interviewee context — do not re-ask; build on this:
- Name: [from Phase 1]
- Role: [from Phase 1]
- Primary focus area: [from Phase 1]
- Core product vision: [from Phase 2b]
- Primary customer: [from Phase 2b]
- Must get right: [from Phase 2b]
- Biggest concern: [from Phase 2b]
- Top priority area: [from Phase 2b]
- Open question: [from Phase 2b]
- Competitive moat: [from Phase 2b]
- Pivot trigger: [from Phase 2b]
- Market research: [from Phase 2c]

Company context:
- Clockchain: decentralized time oracle, DePIN, pre-MainNet
- Core IP: US patent for blockchain-based timekeeping
- FINMA-approved token sale
- Competitors: Sahara AI, 0G Labs, Sentient, Story Protocol, Cronos, Eliza
- Differentiation: time provenance as trust substrate
- Prior readiness assessment: [summary from Phase 2]

Product discovery framing:
Discovery-first — do not seed specific question themes. Let the interview
find tensions organically. The interviewer should surface assumptions, not
gather feature lists.

THREE PRODUCT AREAS to score:
1. Network (Time Oracle / DePIN) — the core infrastructure layer
2. Agent Identity (DIDs / Birth Certificates) — on-chain agent identity and provenance
3. Smart Contracts & Receipts — verifiable receipts and on-chain agent actions

FIVE FUNCTIONAL DIMENSIONS per product area:
1. Vision Clarity (30%) — What is this product and who is it for?
2. Market Understanding (20%) — Competitive landscape, user needs, timing
3. Technical Feasibility (20%) — Can we build this with current capabilities?
4. Prioritization (15%) — What should we build first and why?
5. Risk Awareness (15%) — What could go wrong?

Scoring: Score each product area on each dimension (15 cells total).
Composite score per area = vision×0.30 + market×0.20 + technical×0.20 + priority×0.15 + risk×0.15

Conviction tiers:
- Ready to Build (≥ 0.7 composite) — team has clarity and conviction
- Emerging (0.4 – 0.69) — some clarity but unresolved assumptions
- Not Ready (< 0.4) — too many unknowns to commit resources

Output: Priority-ranked product roadmap across the 3 areas with conviction tiers.
```

### Hard Stop Condition

**If the invocation returns an error or deep-interview is unavailable:** Stop immediately. Output:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
ASSESSMENT INTERRUPTED
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

The deep-interview skill could not be invoked.
Error: [error_message]

Please ensure:
  - OMC/OMX is properly installed
  - deep-interview skill is available
  - Runtime is restarted if recently installed

Restart and invoke /assess-clockchain-product to resume.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

Do not proceed with manual interviewing. Exit the skill.

---

## Phase 4: Interview Completion

**Prerequisite:** Phase 3 must be invoked. This phase is passive.

### Phase 4 Header

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PHASE 4 OF 5 — INTERVIEW IN PROGRESS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Deep-interview is conducting the Socratic assessment.
This phase runs autonomously until the interview
reaches clarity threshold or round limit.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Behavior During Phase 4

- **Do not answer questions** posed by deep-interview — it handles the interview loop
- **Do not intervene** in the Socratic questioning
- **Wait** for deep-interview to signal completion

### Completion Criteria

Deep-interview ends when:
- Ambiguity score ≤ 0.2
- All product areas scored across all dimensions
- Round 20 cap reached
- User requests early exit

### Post-Completion Gate

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
INTERVIEW COMPLETE — CRYSTALLIZING ROADMAP
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Crystallized spec saved to:
[runtime_output_dir]/deep-interview-[slug].md

Ambiguity score: [score]
Product areas scored: [count]/3

Proceeding to roadmap generation.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Phase 5: Deliverable Generation & Roadmap Delivery

**Prerequisite:** Phase 4 must complete with deep-interview returning a crystallized spec.

### Phase 5 Header

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PHASE 5 OF 5 — ROADMAP GENERATION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Generating priority-ranked product roadmap.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Step 1 — Read crystallized spec

Read the file at `{runtime_output_dir}/deep-interview-{slug}.md`. Confirm the file exists and contains content. If missing or empty, stop and report.

### Step 2 — Generate product roadmap

Using the crystallized spec, the pre-interview context, and the market research, generate the product roadmap using the template from strategy.md.

### Step 3 — Save markdown artifact

Write the roadmap to `{runtime_output_dir}/product-roadmap-{interviewee_slug}.md`.

### Step 4 — Save JSON artifact

Extract and write structured fields to `{runtime_output_dir}/product-roadmap-{interviewee_slug}.json`:
- interviewee, role, product_areas (with per-dimension scores), conviction_tiers, priority_ranking, timestamp

### Step 5 — Export DOCX

Verify pandoc is available, then export:

```bash
pandoc {runtime_output_dir}/product-roadmap-{interviewee_slug}.md \
  -o {runtime_output_dir}/product-roadmap-{interviewee_slug}.docx \
  --from=markdown \
  --toc \
  --toc-depth=2 \
  --metadata title="Clockchain Product Discovery: {interviewee_name}" \
  --metadata author="Clockchain Product Team" \
  --metadata date="{ISO_date}"
```

**If DOCX export fails:** Report the pandoc error. Do not downgrade silently.

### Step 6 — Present deliverables

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PRODUCT DISCOVERY ASSESSMENT DELIVERED
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Clockchain Product Discovery Assessment
Interviewee: [interviewee_name] ([role])
Date: [ISO_date]

PRIORITY-RANKED PRODUCT ROADMAP:

  #1  [product_area]  — [conviction_tier]  ([composite_score])
  #2  [product_area]  — [conviction_tier]  ([composite_score])
  #3  [product_area]  — [conviction_tier]  ([composite_score])

ARTIFACTS:
  - Markdown roadmap:  [path]/product-roadmap-[slug].md
  - Word document:     [path]/product-roadmap-[slug].docx
  - JSON artifact:     [path]/product-roadmap-[slug].json

NEXT STEP:
Run this assessment with other team members to compare
product visions and identify alignment vs. divergence.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
ASSESSMENT COMPLETE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Policy:** Stop here. Do not offer planning, execution, or implementation. The roadmap is the deliverable.

</Steps>

<Tool_Usage>
- Use `WebFetch` or `Bash` with `curl` for market research
- Use `AskUserQuestion` for intake collection (structured form, not open Q&A)
- Use `Skill()` to invoke deep-interview only for OMC; use `$deep-interview` for OMX
- Use `Read` to load the crystallized spec from deep-interview output and prior assessment context
- Use `Write` to save markdown and JSON artifacts
- Use `Bash` with `pandoc` for DOCX export
</Tool_Usage>

<Examples>
<Good>
Intake form presented clearly:
```
Let me assess your product thinking for Clockchain.

Interviewee: Yang Tang
Role: Head of AI Products
Primary focus: Agent Identity (DIDs / birth certificates)
```
Why good: User can see exactly what's being assessed, correct any errors before proceeding.
</Good>

<Good>
Discovery-first question that surfaces assumptions:
```
You said the primary customer is "AI agent platforms." Can you name
three specific platforms that would pay for Clockchain's time oracle
today? If you can't name three, what does that tell us about how
well we understand the customer?
```
Why good: Probes the depth of conviction behind a stated belief. Forces the interviewee to test their own assumption rather than accepting it at face value.
</Good>

<Good>
Cross-product area probe:
```
You've prioritized Agent Identity as the #1 product area. But birth
certificates require the Network to be live and smart contracts to
be deployed. Does Agent Identity actually depend on the other two
areas being ready first? Or can it stand alone?
```
Why good: Exposes dependency assumptions between product areas that could change the priority ranking.
</Good>

<Good>
Vision clarity probe:
```
You described the Network as "a decentralized time oracle for Web3."
But the company is pivoting to "time as the trust substrate for AI agents."
Which is the actual product — time for Web3 or time for AI? Can it be both,
or does trying to serve both audiences dilute the value proposition?
```
Why good: Surfaces a real strategic tension in Clockchain's positioning. The interviewee must reconcile two potentially competing visions.
</Good>

<Good>
Risk awareness probe:
```
Clockchain's differentiation is the patented time oracle. What happens if
a major L1 (Ethereum, Solana) ships native high-resolution timestamps
as a protocol feature? Does the patent protect against that, or does it
only cover a specific implementation?
```
Why good: Tests whether the team has thought about existential competitive risks, not just feature-level competition.
</Good>

<Good>
Market understanding probe with competitive context:
```
Cronos has an AI Agent SDK with a Proof of Identity standard. Story Protocol
has ATCP/IP for agent-to-agent communication. Both are live. Clockchain's
Agent Identity is on testnet. What gives Clockchain the right to win this
market despite being later?
```
Why good: Uses specific competitive intelligence to pressure-test the interviewee's conviction. Not adversarial — genuinely probing whether there's a defensible answer.
</Good>
</Examples>

<Escalation_And_Stop_Conditions>
- If the selected runtime's deep-interview invocation returns an error or deep-interview is unavailable: **hard stop.** Do not proceed with manual interviewing. Report the error and exit.
- Hard stop at deep-interview round 20 regardless of ambiguity
- If the interviewee can't articulate what the product IS after 3 rounds of vision probing, flag it explicitly: "Vision Clarity is critically low — the core product identity is unresolved"
- If two product areas score identically, probe for dependencies: which one enables the other?
- If all areas score below 0.4, recommend a product strategy offsite before further development
- If the interviewee defaults to "all areas are equally important" on every question, challenge directly: "Equal priority means no priority. What ships first if you can only fund one?"
</Escalation_And_Stop_Conditions>

<Final_Checklist>
- [ ] **Phase 0 — Prerequisites confirmed present (FAIL HARD if any missing):**
  - [ ] OMC or OMX installed and verified
  - [ ] deep-interview skill confirmed available through selected runtime
  - [ ] pandoc installed and verified
- [ ] Intake collected (interviewee name, role, focus area)
- [ ] Company and competitive context loaded
- [ ] Pre-interview product context collected (all 8 questions answered)
- [ ] Market & technology research performed (Phase 2c — mandatory)
- [ ] Deep-interview seeded with product discovery framing + 3 product areas + 5 functional dimensions
- [ ] Deep-interview completed (or user exited early)
- [ ] Crystallized spec read from `{runtime_output_dir}/deep-interview-{slug}.md`
- [ ] Product roadmap generated with conviction tiers and priority ranking
- [ ] Markdown saved to `{runtime_output_dir}/product-roadmap-{slug}.md`
- [ ] JSON artifact saved to `{runtime_output_dir}/product-roadmap-{slug}.json`
- [ ] DOCX exported to `{runtime_output_dir}/product-roadmap-{slug}.docx`
- [ ] Deliverable presented to user with priority ranking summary
</Final_Checklist>

Task: {{ARGUMENTS}}
