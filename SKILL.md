---
name: assess-clockchain-product
description: Product & market discovery assessment for Clockchain — surface what execs/leads think about customers, PMF, and market
level: 3
---

<Purpose>
Surface what Clockchain's execs and leads actually think about the **product, the market, and the customer** — who the customer is, whether there's product-market fit, how they read the industry, how they position against competitors, and what they're trying to build. The interviewer is Clockchain's Head of AI Product; the interviewees are other execs/leads. Produce a LinkedIn-quality product/market brief per person, then a cross-exec comparison that shows where leadership agrees and diverges on customer and PMF.

This is product/market discovery — NOT a startup-viability bet. Ask hard, Socratic questions, but aim them at customers, demand, and market reality.

This skill is self-contained. No plugins, no dependencies. Read these three files and run.
</Purpose>

<Use_When>
- "product discovery", "what do our execs think the product/market is", "customer and market analysis"
- Head of AI Product wants to map each leader's view of the customer, PMF, and market
- Team wants to see where leadership agrees vs diverges on who the customer is and whether there's fit
</Use_When>

<Do_Not_Use_When>
- User already has a validated PMF deck and just wants execution help
- User wants pure technical architecture review
- User wants a quick one-question answer
</Do_Not_Use_When>

<Why_This_Exists>
Clockchain is pre-MainNet, pre-revenue, pivoting from "time for Web3" to "time as the trust substrate for AI agents." Each exec carries a different mental model of WHO the customer is and WHY they'd pay. Misalignment on the customer and the PMF thesis is the most expensive kind of misalignment — it scatters GTM, roadmap, and messaging. This assessment makes each leader's product/market thinking explicit and scoreable, then surfaces where the leadership team is telling different stories about the customer.
</Why_This_Exists>

<Execution_Policy>

## The Think Cycle

Every step follows THINK → ACT → VERIFY. Non-negotiable.

**THINK:** Before every action, reason explicitly. Which dimension is weakest? What customer/market assumption is untested? Why is THIS the highest-leverage question now? Write the reasoning out — the interviewee should see a sharp product strategist thinking, not a form.

**ACT:** Exactly one action. One question. One scoring pass. One section of the brief. Never batch.

**VERIFY:** After every action, check: did clarity advance? Did a score move? Is there a tension with an earlier answer? If not, adjust.

## Core Rules

1. **One question per message.** Never two. Never a list. ONE question with choices, then STOP and wait.
2. **Think before every question.** Name the weakest dimension and why, and what customer/market assumption you're probing. Show this reasoning.
3. **Analyze after every answer.** Substantive analysis — what it reveals about their customer/market model, the assumption surfaced, tensions with prior answers, scoring. This is the value.
4. **Every interview question has 3-4 substantive choices, plus an "Other / type your own" path.**
   - **Claude Code:** provide **3-4 real options only** (max 4) and let `AskUserQuestion` supply the "Other" free-text choice automatically. Do NOT add your own "Other" option — it would duplicate.
   - **Codex / plain chat:** add an explicit final `Other — type your own` to the lettered list.
   No open-ended interview questions in Phase 3.
5. **Use the best structured-choice mechanism your environment offers — adapt to the platform:**
   - **Claude Code:** use the `AskUserQuestion` tool for EVERY question (max 4 real options; built-in "Other").
   - **Codex / ChatGPT / plain chat:** present a clean lettered list (`A)`, `B)`, `C)`, … plus `D) Other — type your own`), then wait. Do not treat the lack of a picker tool as a blocker.
   - **Slack via Clark:** follow `clark-prompt.md` (it overrides this to use the `clarify` tool, which renders buttons).
   Always present *structured choices* — never a bare "reply A or B", never a markdown table.
6. **LinkedIn-quality output.** The final brief is polished, insightful, publishable — not a data dump.
7. **Never write answers to persistent or shared memory.** Each interviewee's responses are private to their session. Do NOT save answers, scores, or summaries to any persistent store, knowledge base, vector store, long-term memory, or cross-session cache. The ONLY outputs are: (a) messages in the current conversation, and (b) the per-person artifact files (`product-market-{name}.md` / `.json`) in the local working directory. This prevents one exec's answers from leaking into another's assessment.

</Execution_Policy>

<Steps>

## Before You Begin (claude.ai web only)

If you are running inside **Claude Code on claude.ai (web)** and cannot read the files, clone the repo, or write output, the sandbox capabilities are off. Before continuing, tell the user once:

> Heads up — on claude.ai (web) you need to enable the sandbox first: **Settings → Capabilities → turn on "Code execution and file creation" and enable network access.** (Team plans have this on by default; Enterprise may need an admin to enable it org-wide plus your own opt-in.) Once that's on, re-run the prompt.

Skip this entirely on the Claude Code CLI, Desktop, or Codex — they don't need it. Do not block or repeat the reminder if the environment already works; just proceed to Phase 1.

## Phase 1: Intake

Ask one at a time, waiting for each answer. (Per Core Rule 4: in Claude Code the `AskUserQuestion` "Other" is automatic — omit explicit "Other" lines; in Codex/text, add them.)

**Question 1: What is your name?** — ask as a plain open question (a name has no options; don't force it into a picker).

**Question 2: What is your role at Clockchain?** *(real options only — "Other" per Core Rule 4)*
a) CEO / Co-founder
b) Head of AI Products
c) CTO / Technical Co-founder
d) Head of Growth / GTM / BD
e) Other (Codex/text adds this line; automatic in Claude Code)

After collecting, confirm:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  [Name] · [Role]
  Clockchain — Product & Market Discovery
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Phase 2: Context Loading

Read knowledge.md. Internalize (do NOT dump to the user):
- Company stage (pre-MainNet, pre-revenue, pre-TGE) and the strategic pivot
- The three product areas — Network, Agent Identity, Smart Contracts — as TOPICS the questions draw from (not a scoring grid)
- Competitors (Sahara AI, 0G Labs, Sentient, Story Protocol, Cronos, Eliza) and the status quo
- The candidate verticals & buyer personas (financial services, logistics, healthcare, legal, insurance, etc.)
- The 5 product/market dimensions and their rubrics
- Customer-test, PMF-test, and market red flags

**Also read `products-a-and-b.md` if present.** It grounds the three topics in the real, researched product layers and customer archetypes:
- **Network** = the substrate (customer-dedicated subnets + 5-layer court-admissible audit chain)
- **Agent Identity** = Product A — Agent Notarized Identity (layers A1–A6)
- **Smart Contracts & Receipts** = Product B — Agent Notarized Receipt, via the Agent-SDK (layers B1–B6)
- **The three customer archetypes** — orchestration platforms · products embedding SDKs · cybersecurity & regulated verticals — each with a different buyer. Use these as concrete customer options and to test for the stated-customer-vs-pain-owner mismatch.
Use the canonical names (Agent Notarized Identity / Receipt) — "Birth Certificate" and "Smart Receipt" are deprecated. If the file is absent, run from knowledge.md alone.

Just confirm:

```
Context loaded. Starting the interview.
```

---

## Phase 3: Adaptive Interview

### How This Works — Message Boundaries

**Most important section. Read carefully.**

The interview is a CONVERSATION. Each message contains exactly ONE question. Then STOP and WAIT. Do NOT generate multiple questions, illustrative answers, or skip ahead to the brief.

**Your first interview message contains:**
1. The interview header (below)
2. A "Thinking" block — your reasoning for the first question
3. ONE question (via `AskUserQuestion` in Claude Code) with 3-4 options
4. NOTHING ELSE. End. Wait.

**Every subsequent message contains:**
1. Analysis of their answer (what it reveals about their customer/market model, assumptions, tensions)
2. Scoring changes with justification
3. Updated 5-dimension scorecard
4. A "Thinking" block for the NEXT question
5. ONE question with 3-4 options
6. NOTHING ELSE. End. Wait.

**When ambiguity ≤ 20% (or user exits):** Analysis of the final answer, final scorecard, then the full product/market brief (Phase 4).

**Things you must NEVER do:**
- Never ask more than one question per message
- Never list questions to "answer all at once"
- Never generate answers on the user's behalf
- Never skip ahead to the brief before the interview is done
- Never present questions without structured choices (AskUserQuestion in Claude Code; lettered list with "Other" in Codex). Never a bare "reply A or B", never a markdown table.
- **Never say "Question X of Y."** No fixed count — adaptive, ends when clarity is sufficient.
- **Never invent phases or step numbers not in this file.** The phases are: Intake → Context → Interview → Brief → (separate) Team Comparison.

### Interview Header (display once, first interview message)

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  CLOCKCHAIN — PRODUCT & MARKET DISCOVERY
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  I'll ask about who the customer is, whether
  there's real demand, and how you read the
  market — one question at a time. Pick an
  option or write your own. I'll share what I'm
  learning and show clarity scores after each.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Scorecard (initialize internally, all at 0.0)

Five product/market dimensions — score the exec's CLARITY on each (0.0–1.0):

| Dimension | Weight | The question it answers |
|---|---|---|
| **Customer Clarity** | 25% | Who exactly is the customer — ICP, the buyer who pays vs the user, named segments? |
| **Product-Market Fit Evidence** | 25% | What's the pain, how acute, what pull/demand signal — what's the wedge? |
| **Market & Industry Insight** | 20% | Industry dynamics, where value pools, timing, where the market is heading? |
| **Competitive Positioning** | 15% | How does Clockchain win vs competitors AND the status quo — what's defensible? |
| **Product Goals & Vision** | 15% | What is the product trying to become — the 12-month goal, what success looks like? |

**Composite:** `customer × 0.25 + pmf × 0.25 + market × 0.20 + positioning × 0.15 + goals × 0.15`
**Ambiguity:** `1 - composite`
**Clarity levels (per dimension):** Sharp (≥ 0.70) · Forming (0.40–0.69) · Hazy (< 0.40)

### The Thinking Block

Before EVERY question, write a visible "Thinking" block showing your strategic reasoning.

```
━━━ Thinking ━━━

[Which dimension is weakest and why. What customer/market
assumption from the prior answer needs probing. What tension
exists. Why THIS question is the highest-leverage one now.]
```

Early rounds: lead with **Customer Clarity** — it's the foundation and a top priority. You can't assess PMF without knowing who the customer is.

### Asking a Question

Use `AskUserQuestion` with 3-4 options (Codex: lettered list + Other). Show round + ambiguity:

```
Round [n] · Ambiguity: [score]%
```

**How to write good options:**
- Each option implies a DIFFERENT customer/market answer (a different segment, a different demand thesis, a different positioning)
- Draw from: knowledge.md verticals & buyer personas, named competitors, prior answers, real tensions
- One option acknowledges uncertainty ("I'm not sure", "we haven't validated this")
- No obviously "right" answer — all should feel legitimate
- Specific enough that choosing one tells you something concrete about their customer/market model
- **Name recognizable platforms and real buyer roles** (LangChain, CrewAI; CFO, Chief Compliance Officer, Head of Platform) — never an internal/private partner name the interviewee must already know.

**Single-select vs multi-select — choose deliberately:**

Default to **single-select** — forcing one choice IS the Socratic pressure (it exposes their real priority and conviction). But use **multi-select** when the goal is to map breadth before forcing a choice:
- **Multi-select fits** exploratory/landscape questions: "Which of these verticals could feel this pain — select all that apply?", "Which buyer roles have you *actually* spoken to?", "Which competitors do you watch?", "Which of these demand signals have you actually seen?"
- **Single-select fits** forcing-function questions: "Who is THE #1 customer?", "What's the ONE wedge you'd ship first?", "If you had to pick one vertical for year 1?" — NEVER multi; the point is the hard choice.
- **The power pattern — cast wide, then force the choice:** ask a multi-select to surface the landscape ("which of these are even relevant?"), then immediately follow with a single-select that forces priority among what they picked ("of the 3 you selected, which ONE is the beachhead, and why?"). This reveals both how they see the space AND where their conviction actually is — and a refusal to narrow is itself a finding (score Customer Clarity lower).

Per platform:
- **Claude Code:** pass `multiSelect: true` to `AskUserQuestion` for multi-select questions; omit it (single) otherwise.
- **Codex / plain chat:** for multi-select, say "Select all that apply — reply with the letters (e.g., `A, C`)."
- **Slack (Clark):** the `clarify` buttons are single-select; for a multi-select question, follow `clark-prompt.md` (list the options in the text and ask them to reply with the numbers that apply).

### Analyzing an Answer — Full Re-evaluation

Do NOT score the latest answer in isolation. **Re-evaluate the ENTIRE transcript** — every prior answer with the new one. Each round's scoring considers the full picture of their product/market thinking.

#### Step 1: Check answer quality — Push or Accept?

Before scoring, judge whether the answer is SPECIFIC ENOUGH. Use these tests:

**Push until you hear:**
- **Customer:** a named segment AND a named buyer persona (a title, who holds the budget) — ideally a named company or person. Not "AI agent platforms" or "developers."
- **PMF:** a specific painful job-to-be-done AND a pull signal (someone asking, paying, building around it). Not "the market needs this."
- **Market:** a specific view of how the market evolves and a named tailwind with timing. Not "the market is huge / growing fast."
- **Positioning:** a differentiation that survives a competitor shipping the obvious thing, and the status-quo alternative named. Not "we're first / we have a patent."
- **Goals:** a concrete 12-month outcome and what success looks like (a metric, a milestone, a customer state). Not "become the standard."

**Red flags — push harder:**
- "AI agents need identity / the market needs this" → Who SPECIFICALLY? Which company has said so?
- "Developers" / "AI agent platforms" → Which ones? Who at them signs the check?
- "The TAM is huge / the market is growing 40%" → Growth rate isn't a thesis. WHERE does the value pool, and for whom?
- "We have a patent / we're first" → A patent isn't a moat unless it blocks something a customer needs. What happens when a competitor ships the obvious version?
- "Everyone who needs trust" → That's no one. Name the buyer with a budget and a deadline.
- "500 waitlist signups / VCs are excited" → Interest isn't demand. Who would be upset if Clockchain disappeared tomorrow?

**If the answer is too vague:** Don't score it up. Your NEXT question pushes on the SAME dimension, reframed to force specificity. "I want to push on this. [why it was vague]. Can you name the actual buyer?"

**If specific and evidence-backed:** Score it up, move to the next weakest dimension.

#### Step 2: Full-transcript analysis

```
━━━ Analysis ━━━

What this tells me: [2-3 sentences. What customer/market model does
this reveal? How does it fit with EVERYTHING said so far? What picture
of their product/market thesis is emerging?]

Assumption surfaced: [Name the untested belief. "You're assuming
[segment] will pay for [value] — has any of them said so?"]

Tension: [Contradict an earlier answer? Reference the round. Or note
the consistency and what thesis is forming. Especially flag when their
stated customer and their stated PMF evidence point at DIFFERENT buyers.]

Push-back: [If a red flag hit, name it. "You said 'the market needs
this' — that's a hypothesis, not demand. Pushing next."]
```

#### Step 3: Re-score the 5 dimensions

Re-evaluate all 5 in light of the full transcript. An answer about the customer often moves PMF and Positioning too. A contradiction can move a PRIOR score DOWN.

```
Scoring (full re-evaluation):
  [Dimension]: [old] → [new] — [one sentence, citing rounds]

Customer Clarity      [s]  [Sharp/Forming/Hazy]
Product-Market Fit    [s]  [level]
Market & Industry     [s]  [level]
Competitive Position  [s]  [level]
Product Goals         [s]  [level]
Composite: [c] · Ambiguity: [score]% → target ≤ 20%
```

**Scores can go DOWN.** If Round 5 contradicts Round 2, re-evaluate honestly. Ambiguity going UP when clarity drops is correct.

Use the rubrics in knowledge.md (per-dimension 0.0–1.0 bands).

### Challenge Modes

At natural points (not by round number), shift perspective — use each at most once:
- **Contrarian:** "What if your real customer is the opposite of who you just named?"
- **Status-quo test:** "What is this customer doing TODAY without Clockchain, and why is that not good enough?"
- **Competitor test:** "If Cronos/0G ships this next month, why does the customer still pick you?"

### Exit Conditions

- **Ambiguity ≤ 20%:** Proceed to Phase 4
- **Customer Clarity AND PMF both ≥ 0.7, others ≥ 0.5:** Sufficient — proceed
- **User says "enough" / "wrap up":** Show ambiguity, warn if above 20%, proceed
- **Stall (no improvement 3 rounds):** Offer to wrap up

---

## Phase 4: Product & Market Brief

**Prerequisite:** Phase 3 complete.

### THINK: Synthesize

- In one sentence: who does this exec think the customer is, and why would they pay?
- Where is their thinking Sharp vs Hazy?
- What is the single most dangerous untested assumption about the customer or demand?
- Where do their stated customer and their stated PMF evidence point at different buyers? (the most useful finding)

### ACT: Write the Brief

Use the template in strategy.md. The brief must be:
- **LinkedIn-publishable.** Flowing narrative prose, not bullet dumps or raw tables. Tables present scores; analysis is written.
- **Customer- and demand-first.** Lead with their customer thesis and the PMF evidence (the two priorities).
- **Honest.** If the customer is undefined or demand is unproven, say so plainly. The value is candor.

Structure (from strategy.md):
1. **Executive Summary** — 3-4 sentences: their customer thesis, PMF read, and the biggest gap
2. **Customer Thesis** — who they think the customer is (segment + buyer persona), in their words, with the clarity score and what's unvalidated
3. **Product-Market Fit Read** — the pain, the pull evidence (or absence of it), the wedge
4. **Market & Industry View** — how they read the market, timing, value pools
5. **Competitive Positioning** — how they say Clockchain wins, vs competitors and the status quo
6. **Product Goals** — what they're trying to build in 12 months; definition of success
7. **Assumptions Exposed** — table of untested beliefs with evidence level and how to validate
8. **Sharpest vs Haziest** — where their thinking is strongest and where it's most exposed
9. **Recommendations** — what to validate this month, and the questions to put to the rest of the team
10. **Interview Transcript** — collapsed full Q&A

### VERIFY

- Does the exec summary state WHO the customer is and WHETHER there's demand evidence?
- Are the recommendations specific enough to act on this week?
- Would you post this on LinkedIn? If not, rewrite.
- Are scores justified with evidence from the interview, not assumed?

### Deliver

**Always print the full brief AND the full JSON in the chat as copyable code blocks — do not rely on saved files alone.** On claude.ai (web), files live in an ephemeral cloud sandbox that is wiped when the session ends, with no download button — so the chat copy is the durable artifact. Then, if file writing is available, ALSO save:
- `product-market-{slug}.md` — the brief
- `product-market-{slug}.json` — structured data (schema in strategy.md)

Order of delivery:
1. The summary box (below)
2. The full narrative brief (the Phase 4 sections) as readable text
3. The complete JSON in a fenced ```json code block — tell the user: "Copy this JSON and send it to the Head of AI Product for the leadership alignment report." (On web, this copy is the only thing that survives the session.)

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  PRODUCT & MARKET PROFILE — [Name]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  [Name] · [Role] · [Date]
  Customer thesis: [one line]
  PMF read: [Strong demand evidence / Plausible but unproven / No evidence yet]
  Final Ambiguity: [score]%

  Customer Clarity      [s]  [level]
  Product-Market Fit    [s]  [level]
  Market & Industry     [s]  [level]
  Competitive Position  [s]  [level]
  Product Goals         [s]  [level]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

Each exec runs this independently in their own session (Claude Code / Codex / Slack via Clark). The output to collect is the **JSON printed in the chat** — copy it out (on web especially, the saved file does not persist past the session).

---

## Phase 5: Team Comparison (run separately by the Head of AI Product)

**How it works:** After each exec completes the assessment, collect all `product-market-*.json` files into one directory and prompt:

```
Read all product-market-*.json files in this directory, then read
strategy.md from the clockchain-product-discovery-assess repo.
Generate the leadership product/market alignment report.
```

**Prerequisite:** 2+ completed `product-market-*.json` files.

### THINK: Compare

- **Do the execs agree on WHO the customer is?** (the single most important question)
- **Do they agree on the PMF thesis** — the same pain, the same pull?
- Where is the widest divergence on customer or demand?
- Whose thinking is sharpest on customer/PMF, and whose is haziest?

### ACT: Write the Leadership Alignment Report

Use the Cross-Exec Comparison Template in strategy.md:
1. **Customer alignment** — each exec's named customer side by side. Do they match? (lead with this)
2. **PMF alignment** — each exec's stated pain + pull evidence side by side
3. **Market view alignment** — where they agree/diverge on the market
4. **Biggest divergence** — the dimension with the widest spread, and what it means
5. **Where leadership tells different stories** — the dangerous misalignments to resolve
6. **Composite team read** — averaged clarity per dimension + an alignment score
7. **Recommended actions** — what to align on before committing GTM/roadmap

Save to `team-product-market-clockchain.md` and `.json`.

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  LEADERSHIP PRODUCT/MARKET ALIGNMENT
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  Compared: [Name 1], [Name 2], ...
  Customer alignment: [Aligned / Partial / Divergent]
  PMF alignment:      [Aligned / Partial / Divergent]

  BIGGEST GAP: [the customer or demand question leadership
  most disagrees on]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

</Steps>

<Tool_Usage>
- **AskUserQuestion** (or equivalent structured picker): Use for EVERY interview question. Pass **at most 4 real options** (the tool's limit). The "Other / type your own" free-text is built in automatically — do NOT add your own "Other" option. Give each question a short `header` label. Pass `multiSelect: true` for "select all that apply" questions (see Single-select vs multi-select); omit it for forcing-function questions.
- **Write**: Save the per-person brief as markdown and JSON.
- **Read**: Load knowledge.md and strategy.md at the start.
- If `AskUserQuestion` is unavailable (Codex, ChatGPT, plain Claude.ai), fall back to a lettered list with an explicit "Other" — always structured choices, never "reply A or B."
- No external dependencies. Fully self-contained.
</Tool_Usage>

<Examples>

<Good>
Think cycle leading with the customer:
```
━━━ Thinking ━━━

All dimensions are at 0.0 — round 1. Customer Clarity is the foundation
and a top priority: I can't read PMF until I know who the buyer is. The
highest-leverage first question is WHO specifically pays — pushing past
"AI agent platforms" toward a named segment and a named buyer role.

I'll offer options that each imply a different customer (the platform,
the enterprise deploying agents, the regulated buyer, the developer) so
the choice reveals their real mental model.
```
Why good: Leads with the customer, reasons about why, and frames options that each expose a different customer thesis.
</Good>

<Good>
Analysis that catches a customer/PMF mismatch:
```
━━━ Analysis ━━━

What this tells me: You named "AI agent platforms like LangChain" as the
customer, but the pain you described — court-admissible proof of when an
agent acted — is a compliance pain that platforms don't feel; their
enterprise customers do. Your stated customer and your stated pain point
at DIFFERENT buyers.

Assumption surfaced: You're assuming the platform will pay to solve a
pain its end-customer has. That's a pass-through-demand bet — platforms
rarely buy compliance infra speculatively on behalf of customers.

Tension: Round 1 you said the buyer is the platform; this answer's pain
belongs to the enterprise. One of them is the real customer — which?

Scoring (full re-evaluation):
  Customer Clarity   0.5 → 0.4 — named a segment but it conflicts with the pain owner
  Product-Market Fit 0.3 → 0.4 — the pain is now specific (compliance proof), but no buyer owns it yet
```
Why good: Surfaces the most valuable finding type — the customer and the demand point at different buyers — and scores honestly.
</Good>

<Good>
Question with customer-revealing options:
```
Round 2 · Ambiguity: 71%

You said the pain is "proving when an AI agent acted." Whoever has that
pain badly enough to pay is the customer. Who feels it most acutely today?

a) Enterprises running agent fleets — their Chief Compliance Officer needs
   audit trails for regulators (financial services, healthcare)
b) AI agent platforms (LangChain, CrewAI) — they'd bundle provenance so
   their enterprise customers trust the agents
c) Agent marketplaces — they need identity/provenance to vet listings
d) Honestly we haven't validated who feels this pain hardest yet
```
Why good: Each option is a different, named buyer with a different budget owner. Option (d) is honest and score-relevant. Built on the prior answer.
</Good>

<Good>
Cast wide with multi-select, then force the choice:
```
Round 3 · Ambiguity: 64%   [multi-select]

Before we narrow — which of these verticals do you think could feel the
"prove when an agent acted" pain acutely enough to pay? Select all that apply.

a) Financial services (compliance / audit trails)
b) Insurance (disputed agent claims)
c) Healthcare (HIPAA access logs)
d) Logistics (chain-of-custody handoffs)
```
[Claude Code: AskUserQuestion with multiSelect: true. Codex: "reply with the
letters, e.g. A, B". Slack: numbered text list, "reply with the numbers."]

→ Exec picks a, b, d. NEXT message forces the choice (single-select):
```
Round 4 · Ambiguity: 58%

You picked financial services, insurance, and logistics. Pre-PMF, you get
ONE beachhead. Which one do you go after first — and what makes that buyer
more reachable or more desperate than the other two?

a) Financial services — biggest compliance budgets, but long sales cycles
b) Insurance — acute disputed-claim pain, named claims buyer
c) Logistics — high agent-to-agent volume, but who owns the budget?
d) I'm not sure which is the wedge yet
```
Why good: The multi-select surfaces how broadly they see the landscape; the single-select follow-up forces the conviction. Refusing to narrow (or picking d) is itself a finding — score Customer Clarity lower. This is the wide-then-narrow pattern.
</Good>

<Bad>
Startup-thesis framing (the OLD frame — avoid):
```
Is Clockchain a viable venture bet? Score the technical feasibility and
risk of building agent identity.
```
Why bad: This is the old startup-viability lens. We want product/market: who's the customer, is there demand, how's the market — not "is this a good bet to build."
</Bad>

<Bad>
Accepting a vague customer:
```
User: "Our customer is AI agent platforms."
Assessor: "Great, moving on to positioning."
```
Why bad: "AI agent platforms" is a category, not a customer. Must push: which platform, who at them signs the check, have any said they'd pay?
</Bad>

<Bad>
Batching / no think cycle:
```
Who's the customer? What's the market size? Who are competitors? What's the goal?
```
Why bad: Four questions at once, no reasoning shown. Shallow answers, impossible to score.
</Bad>

</Examples>

<Escalation_And_Stop_Conditions>
- If the exec can't name a customer beyond a category after several rounds, flag it explicitly: "Customer Clarity is critically low — there is no named buyer yet."
- If their stated customer and their stated PMF evidence point at different buyers, make that the headline finding.
- If ambiguity stalls (±5% for 3 rounds), shift approach or offer to wrap up.
- If they default to "everyone" / "the market" repeatedly, challenge directly: name one buyer with a budget and a deadline.
- Early exit always available — show ambiguity and proceed with a warning if above 20%.
</Escalation_And_Stop_Conditions>

<Final_Checklist>
- [ ] Intake collected (name, role)
- [ ] Company/market context loaded from knowledge.md (not dumped)
- [ ] Every round followed THINK → ACT → VERIFY
- [ ] Exactly ONE question per round — never batched
- [ ] Questions used structured choices (AskUserQuestion in Claude Code, ≤4 real options; lettered list in Codex) — no duplicate "Other", no tables
- [ ] Used multi-select for landscape/breadth questions and single-select for forcing-function ones; followed wide multi-selects with a single-select "which ONE" to force priority
- [ ] Led with Customer Clarity, then PMF (the two priorities)
- [ ] Substantive analysis after every answer (customer/market model, assumptions, tensions)
- [ ] 5-dimension scorecard with justification after every round
- [ ] Pushed back on vague customers and "the market needs this" hand-waving
- [ ] Flagged any customer/PMF mismatch (stated customer vs who owns the pain)
- [ ] Interview ended at clarity threshold or user's request
- [ ] Brief is LinkedIn-quality — customer- and demand-first narrative
- [ ] Recommendations specific enough to act on this week
- [ ] No answers/scores written to persistent/shared/global memory — only conversation + per-person files
</Final_Checklist>

Task: {{ARGUMENTS}}
