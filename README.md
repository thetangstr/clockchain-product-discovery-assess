# Clockchain Product & Market Discovery

A Socratic interview that surfaces what each Clockchain exec/lead actually thinks about the **customer, product-market fit, and market** — then a cross-exec report showing where leadership agrees and diverges on who the customer is. Built for the Head of AI Product to run with the other execs.

## ⚠️ First — on claude.ai (web Claude Code)? Enable Capabilities

If you're running this in **Claude Code on claude.ai (web)**, turn the sandbox on *before* you start — otherwise it can't clone the repo, read the files, or write your result.

1. Open **Settings → Capabilities**
2. Enable **Code execution and file creation**
3. Enable **network access** (network egress) — needed to clone the GitHub repo

- **Free / Pro / Max:** toggle these yourself under Settings → Capabilities.
- **Team:** on by default at the org level (network egress enabled).
- **Enterprise:** an admin enables it at **Organization settings → Capabilities**; it may use a two-gate model (admin enables org-wide **and** each user opts in), so you might need both.

**How it runs on web:** the repo clones into an Anthropic-hosted cloud sandbox (not your computer), and any files Claude writes live there too. That sandbox is **ephemeral — wiped when the session ends, with no download button.** So when the interview finishes, **copy the JSON Claude prints in the chat** (it always prints it) — that copy is what you keep and send to the Head of AI Product.

*Not on web?* Skip this — the Claude Code CLI, Desktop, and Codex don't need it. (Or, on plain claude.ai chat with no sandbox, just upload the files — see below.)

## Run It

Copy this prompt into Claude Code, Codex, or any AI coding agent:

```
Clone https://github.com/thetangstr/clockchain-product-discovery-assess.git then read SKILL.md, knowledge.md, strategy.md, products-a-and-b.md, and current-understanding.md. Run the Clockchain product & market discovery interview with me as the interviewee.
```

If you're on Claude.ai, Co-Work, ChatGPT, or any LLM without shell access — download the five `.md` files (`SKILL.md`, `knowledge.md`, `strategy.md`, `products-a-and-b.md`, `current-understanding.md`), upload them to your chat, and send:

```
Read the five attached files. Run the Clockchain product & market discovery interview with me as the interviewee.
```

### Via Slack (Clark)

Load the 4 `.md` files (SKILL, knowledge, strategy, products-a-and-b) + `clark-prompt.md` into Clark's knowledge base. Each exec DMs Clark to take it independently (clickable buttons via the `clarify` tool). See `clark-prompt.md` for setup.

No dependencies. No plugins. No setup.

---

## What It Does

Hard, Socratic, **product- and market-focused** questions — aimed at customers and demand, not "is this a viable bet." It scores each exec's clarity across **5 product/market dimensions**:

| Dimension | Weight | What it surfaces |
|---|---|---|
| **Customer Clarity** | 25% | Who exactly is the customer — vertical, the buyer who pays vs. the user |
| **Product-Market Fit Evidence** | 25% | The pain, how acute, the pull/demand signal, the wedge |
| **Market & Industry Insight** | 20% | Industry dynamics, where value pools, timing |
| **Competitive Positioning** | 15% | How Clockchain wins vs Sahara/0G/Cronos and the status quo |
| **Product Goals & Vision** | 15% | What the product is trying to become; the 12-month goal |

Customer and PMF are weighted highest. The three product areas (Network, Agent Identity, Smart Contracts) are **topics the questions draw from**, not a scoring grid.

**Per-exec output:** a LinkedIn-quality product/market profile — their customer thesis, PMF read, market view, positioning, goals, the assumptions exposed, and where their thinking is Sharp vs Hazy. (`product-market-{name}.md` + `.json`)

**Team output:** a leadership alignment report showing whether the execs name the **same customer** and the **same core pain** — the single most valuable thing to know.

## Compatibility

| Platform | Works? | Interaction |
|----------|--------|-------------|
| Claude Code (CLI / Desktop / Web) | Yes | `AskUserQuestion` clickable picker |
| Codex / ChatGPT / any LLM | Yes | Clean lettered options |
| Claude.ai / Co-Work | Yes | Lettered options |
| Slack (Clark) | Yes | `clarify` tool → buttons |

## How It Works

| Phase | What Happens |
|-------|-------------|
| **1. Intake** | Name and role |
| **2. Context** | Loads Clockchain company/market context (silent) |
| **3. Interview** | Adaptive Socratic interview — one question per round, leads with Customer then PMF, re-scores the full transcript after each answer, pushes back on "the market needs this." No fixed count — runs until clarity is sufficient |
| **4. Brief** | Generates the per-exec product/market profile + JSON |
| **5. Team Comparison** | (Run by the Head of AI Product) compares all execs' profiles into a leadership alignment report |

Challenge lenses appear at natural points (not by round number): a **Contrarian** flip ("what if your real customer is the opposite?"), a **Status-Quo test** ("what's the customer doing today without you?"), and a **Competitor test**.

## Files

| File | Purpose |
|------|---------|
| `SKILL.md` | Interview engine — phases, think→analyze→score loop, 5-dimension scoring, platform handling |
| `knowledge.md` | Domain knowledge — company/market context, candidate verticals & buyer personas, dimension rubrics, customer/PMF red flags, competitors |
| `strategy.md` | Output templates — per-exec brief, leadership alignment report, JSON schema |
| `products-a-and-b.md` | The real Product A & B layer models (A1–A6, B1–B6) and the three customer archetypes — grounds the interview in researched product/market reality |
| `current-understanding.md` | The latest **non-personal** market thesis + discovery learnings + the **ERC-8004 reckoning**. Newer than the framing in the other files; de-identified (no names, no willingness-to-pay, no prospects) |
| `clark-prompt.md` | Slack-only adaptation (the `clarify` tool + data isolation). Not loaded for Claude Code / Codex runs. |

## Team Comparison

Each exec runs the interview independently, then the Head of AI Product aggregates:

**Step 1:** Send each exec the one-liner prompt above (or have them DM Clark). Each finishes with a brief + JSON — saved as `product-market-{name}.md` + `.json` on the CLI/Desktop, or **printed in the chat to copy** on claude.ai web and Slack (the sandbox/DM is ephemeral). Each exec sends you their JSON.

**Step 2:** Collect all the `.json` files into one directory, then prompt:

```
Read all product-market-*.json files in this directory, then read
strategy.md from the clockchain-product-discovery-assess repo.
Generate the leadership product/market alignment report.
```

The report leads with **customer alignment** (do they name the same buyer?) and **PMF alignment** (same pain, same pull?), then flags the dangerous misalignments to resolve before committing GTM and roadmap.

## Based On

Question format inspired by [agentdash-assess-skill](https://github.com/thetangstr/agentdash-assess-skill) and YC-office-hours-style Socratic probing — reframed from startup-viability to product/market discovery.
