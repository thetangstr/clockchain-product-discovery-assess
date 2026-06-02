# Clockchain Product Discovery Assessment

A self-contained assessment skill that interviews Clockchain founding team members through an adaptive Socratic process to discover and crystallize product direction. Produces a priority-ranked product roadmap with conviction tiers.

No dependencies. No plugins. Just clone, read, and run.

## What It Does

Assesses product thinking across **3 product areas** and **5 functional dimensions**:

**Product Areas:**
- Network (Time Oracle / DePIN)
- Agent Identity (DIDs / Birth Certificates)
- Smart Contracts & Receipts

**Functional Dimensions (weighted):**
- Vision Clarity (30%)
- Market Understanding (20%)
- Technical Feasibility (20%)
- Prioritization (15%)
- Risk Awareness (15%)

## Output

A priority-ranked product roadmap with conviction tiers:
- **Ready to Build** (composite score >= 0.70)
- **Emerging** (0.40 - 0.69)
- **Not Ready** (< 0.40)

Plus: detailed 15-cell scoring matrix, assumptions exposed, dependency map, strategic tensions, and actionable recommendations.

## Quick Start

### Claude Code (CLI, Desktop, or Web)

```bash
git clone https://github.com/thetangstr/clockchain-product-discovery-assess.git
```

Then prompt Claude:

```
Read clockchain-product-discovery-assess/SKILL.md, knowledge.md, and strategy.md,
then run the Clockchain product discovery assessment with me as the interviewee.
```

That's it. Claude reads the three files, follows the 4-phase pipeline, and runs the full assessment.

### Codex

```bash
git clone https://github.com/thetangstr/clockchain-product-discovery-assess.git
```

```
Read the SKILL.md, knowledge.md, and strategy.md files in
clockchain-product-discovery-assess/. Follow the 4-phase assessment
pipeline to interview me about Clockchain's product direction.
Score my answers across 3 product areas and 5 functional dimensions,
then produce a priority-ranked product roadmap with conviction tiers.
```

### Claude.ai / Co-Work / ChatGPT / Any LLM

No shell needed. Upload or paste all three files (SKILL.md, knowledge.md, strategy.md) and prompt:

```
I'm sharing three files that define a product discovery assessment for Clockchain.

- SKILL.md — the interview flow and scoring logic
- knowledge.md — the product areas, dimensions, and scoring rubrics
- strategy.md — the output templates

Run the full assessment with me as the interviewee. Ask one question at a time
with multiple-choice options, score my clarity after each answer, and produce
the final priority-ranked product roadmap when we're done.

My name is [YOUR NAME] and my role is [YOUR ROLE].
```

## Compatibility

| Platform | Works? | How |
|----------|--------|-----|
| Claude Code (CLI / Desktop / Web) | Yes | Clone repo, prompt to read and run |
| Codex | Yes | Clone repo, prompt to read and run |
| Claude.ai / Co-Work | Yes | Upload or paste the three .md files |
| ChatGPT | Yes | Upload or paste the three .md files |
| Any LLM with file input | Yes | Upload or paste the three .md files |

## How It Works

| Phase | What Happens |
|-------|-------------|
| **Phase 1: Intake** | Collects interviewee name, role, and primary focus area |
| **Phase 2: Baseline** | Loads company/competitive context, asks 8 baseline product questions |
| **Phase 3: Interview** | Adaptive Socratic interview — one question per round, targets the weakest scoring cell, updates the 3×5 matrix after each answer, displays progress |
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
