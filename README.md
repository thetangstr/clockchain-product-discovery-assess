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

Run the assessment with multiple team members, then use the cross-interviewee comparison template (in `strategy.md`) to identify alignment vs. divergence across the founding team.

## Based On

Format modeled after [agentdash-assess-skill](https://github.com/thetangstr/agentdash-assess-skill).
