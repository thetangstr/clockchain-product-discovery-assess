# Clockchain Product Discovery Assessment

## Run It

Copy this prompt into Claude Code, Codex, or any AI coding agent:

```
Clone https://github.com/thetangstr/clockchain-product-discovery-assess.git then read SKILL.md, knowledge.md, and strategy.md. Run the Clockchain product discovery assessment with me as the interviewee.
```

If you're on Claude.ai, Co-Work, ChatGPT, or any LLM without shell access — download the three `.md` files, upload them to your chat, and send:

```
Read the three attached files. Run the Clockchain product discovery assessment with me as the interviewee.
```

### Via Slack (Clark)

Load the 3 `.md` files + `clark-prompt.md` into Clark's knowledge base. Each team member DMs Clark to take the assessment independently. See `clark-prompt.md` for full setup instructions.

No dependencies. No plugins. No setup.

---

## What It Does

Interviews you about Clockchain's future product direction across **3 product areas** and **5 functional dimensions**, then produces a priority-ranked product roadmap with conviction tiers.

**Product Areas:**
- Network (Time Oracle / DePIN)
- Agent Identity (DIDs / Birth Certificates)
- Smart Contracts & Receipts

**Functional Dimensions (weighted):**
- Vision Clarity (30%) · Market Understanding (20%) · Technical Feasibility (20%) · Prioritization (15%) · Risk Awareness (15%)

**Output:** Priority-ranked roadmap with conviction tiers — **Ready to Build** (>= 0.70), **Emerging** (0.40–0.69), **Not Ready** (< 0.40) — plus a 15-cell scoring matrix, assumptions exposed, dependency map, and recommendations.

## Compatibility

| Platform | Works? |
|----------|--------|
| Claude Code (CLI / Desktop / Web) | Yes |
| Codex | Yes |
| Claude.ai / Co-Work | Yes |
| ChatGPT / any LLM | Yes |

## How It Works

| Phase | What Happens |
|-------|-------------|
| **Phase 1: Intake** | Collects interviewee name, role, and primary focus area |
| **Phase 2: Context** | Loads Clockchain company context and competitive landscape |
| **Phase 3: Interview** | Adaptive Socratic interview — one question per round with multiple-choice options, targets the weakest scoring cell, updates the 3×5 matrix after each answer. No fixed round count — runs until clarity threshold is met |
| **Phase 4: Roadmap** | Generates priority-ranked product roadmap with conviction tiers, assumptions, dependencies, and recommendations |

The interview includes challenge modes that activate at specific rounds:
- **Round 4+:** Contrarian — challenges core assumptions
- **Round 6+:** Simplifier — probes for unnecessary complexity
- **Round 8+:** Competitor — pressure-tests via competitive context

## Files

| File | Lines | Purpose |
|------|-------|---------|
| `SKILL.md` | ~550 | Assessment engine — 4-phase pipeline, interview loop, scoring logic, challenge modes |
| `knowledge.md` | ~270 | Domain knowledge — 3 product areas, 5 dimensions, scoring rubrics, competitive landscape, tension-surfacing techniques |
| `strategy.md` | ~370 | Report templates — individual roadmap, cross-interviewee comparison, JSON schema |

## Team Comparison

Each team member runs the assessment independently in their own session. Then collect the results and generate a comparison:

**Step 1:** Send each person the one-liner prompt from the top of this README. They run it in their own Claude Code, Codex, or Co-Work session.

**Step 2:** Each person's session produces `product-roadmap-{name}.md` and `product-roadmap-{name}.json`.

**Step 3:** Collect all the `.json` files into one directory, then prompt:

```
Read all product-roadmap-*.json files in this directory, then read
strategy.md from the clockchain-product-discovery-assess repo.
Generate the team comparison report.
```

The comparison report shows: priority ranking alignment, conviction tier agreement, biggest disagreements (score delta > 0.3), vision alignment analysis, and recommended actions to resolve divergence.

## Based On

Format modeled after [agentdash-assess-skill](https://github.com/thetangstr/agentdash-assess-skill).
