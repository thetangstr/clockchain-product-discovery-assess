# Clockchain Product Discovery Assessment

A Claude Code skill that interviews Clockchain founding team members through an adaptive Socratic process to discover and crystallize product direction. Produces a priority-ranked product roadmap with conviction tiers.

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

Artifacts: Markdown report, JSON data, DOCX (via pandoc).

## Prerequisites

- [oh-my-claudecode (OMC)](https://github.com/Yeachan-Heo/oh-my-claudecode) or OMX installed
- `deep-interview` skill available
- `pandoc` for DOCX export (optional)

## Usage

```
/assess-clockchain-product
```

Or invoke directly:

```
Skill("assess-clockchain-product")
```

## Files

| File | Purpose |
|------|---------|
| `SKILL.md` | Assessment engine — 5-phase pipeline with deep-interview integration |
| `knowledge.md` | Domain knowledge — product areas, dimensions, scoring rubrics, competitive landscape |
| `strategy.md` | Report templates — individual roadmaps, team comparison, JSON schema |

## How It Works

1. **Phase 0:** Environment verification (OMC/OMX, deep-interview, pandoc)
2. **Phase 1:** Interviewee intake (name, role, focus area)
3. **Phase 2:** Context loading (company context, competitive landscape, market research)
4. **Phase 2b:** Pre-interview product context (8 structured questions)
5. **Phase 2c:** Market & technology research per product area
6. **Phase 3:** Adaptive Socratic interview via deep-interview skill
7. **Phase 4:** Interview completion (passive — waits for deep-interview)
8. **Phase 5:** Roadmap generation with conviction tiers and priority ranking

## Team Comparison

Run the assessment with multiple team members, then use the cross-interviewee comparison template (in `strategy.md`) to identify alignment vs. divergence across the founding team.

## Based On

Format modeled after [agentdash-assess-skill](https://github.com/thetangstr/agentdash-assess-skill).
