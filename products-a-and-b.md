# Clockchain Products A & B — Layers & Use Cases (assessment context)

> Public-safe reference for the product & market discovery assessment. Grounds the interview in the **real product layers and customer archetypes** Clockchain has researched, so questions and options aren't generic. Canonical names per the **Attested** baseline (updated 2026-06-03). Source: clockchain-research (`product-baseline.md`, `products-overview.md`, `decisions-log.md`).
>
> **Naming (current):** use **Agent Attested Identity** (Product A), **Agent Attested Receipt** (Product B), **Agent Attestation Layer** (the category). These replace the earlier *"Notarized / Notary"* naming — "notary" over-claimed a specific legal status and isn't the industry-standard term; **attestation** is the native on-chain word (EAS attestations, ERC-8004 reputation attestations, verifiable credentials). The legacy *"Birth Certificate"* and *"Smart Receipt"* terms are also deprecated (claimed by Identity Digital's DNSid and Microsoft). Mapping to the assessment's three topics: **Network** = the substrate both run on · **Agent Identity** = Product A · **Smart Contracts & Receipts** = Product B.
>
> **Honesty guardrail (this is a public repo):** say **"designed for court-grade"** evidence — never "court-admissible." The chain is on testnet and not certified by any court or conformity body. Every evidentiary claim is a design target, not an earned status. AgentDash is the **design partner**, never a "customer."

## Thesis (one sentence)
Autonomous agents are entering production faster than the trust infrastructure to govern them. Clockchain is the **independent time + receipt layer** that turns agent action logs from "trust the observability vendor" into neutral, time-ordered, tamper-evident evidence — anchored to a clock no single party controls and designed to reach court-grade standards.

## What changed, and why it matters — the ERC-8004 reckoning
The agent-**identity** layer is being standardized by Ethereum, and we should assume it wins there. **ERC-8004** ships three on-chain registries — **Identity, Reputation, Validation** — that together answer *who is this agent, what is its track record, and was its work validated.* **x402** adds agent-to-agent stablecoin payment over HTTP. Between them they are becoming the default rails for agent **registration, certification, and — via reputation + validation — the data that makes agent insurance underwritable.** That is most of what we once scoped as Product A's identity layers.

This forces a choice, and we've made it: **comply where they're strong, differentiate where they're absent.**

- **Comply / compose.** Don't rebuild a competing identity registry — you don't out-distribute an Ethereum standard, and it burns the runway. Make our identifiers **ERC-8004-compatible** so every agent minted there is addressable by a Clockchain receipt. Composing is distribution, not surrender.
- **Differentiate.** Own what ERC-8004 structurally does **not** provide: **independent time, neutral cross-party ordering, as-of-T authority** (was this agent *allowed* to act at 14:03:22Z), and **a faithful receipt of the specific act.** Reputation tells an insurer an agent is *generally* trustworthy; it does not give the post-incident, **claims-grade record** of *what happened, when, in what order, under what authority* that a dispute — or an insurance claim — actually turns on. That record is ours.

**Net:** Clockchain is not an identity-issuance company competing with Ethereum. It is the **time + evidence** layer above the identity/payment rails. The interview should test the exec against this: does the customer they name need *identity* (ERC-8004 covers it) or *independent time, ordering, and a provable receipt of the act* (the part that's still empty)? See `current-understanding.md` for the open forks.

## The substrate both products run on
- **Customer-dedicated subnets** — each enterprise gets its own staked-node subnet; their logs never touch mainnet, only a periodic hash fingerprint does. Privacy by construction; tens of millions of events/day per customer.
- **Five-layer audit chain designed for court-grade standards** — VRF validator election → multi-source UTC time (GPS / atomic clocks / NTP) → independent computation → 2/3 supermajority consensus → permanent linked ledger. Designed to meet eIDAS qualified timestamps, RFC 3161, ISO 18014, ESIGN/UETA — a design target on testnet, not a certified status. A third-party expert can verify any receipt from the public ledger — **no trust in Clockchain-the-company required.** The independence comes from the **validator network**; strip it and it's just another single-company timestamp service (strictly worse than an accredited TSA).
- **Differentiator vs observability stacks** (LangSmith, Helicone, Phoenix, Datadog, OpenLLMetry, Arize): they *capture* traces but the logs stay vendor-stored and trusted-by-inference. Clockchain replaces vendor trust with cryptographic proof and a neutral clock. It anchors *beneath* them — complementary, not competitive.

## Product A — Agent Attested Identity
**One line:** *WHICH agent acted, under what authority, and whether it was authorized at that moment.* Not a competitor to ERC-8004 identity — the **time-bound authority layer** on top of it: principal chain, delegated scope, capabilities, economic mandate, and revocation state, all answerable **as of time T**.

| Layer | What it is |
|---|---|
| **A1 Issuance** | How an identity record is minted and who may mint it (principal, proof of authority, default policy at birth) |
| **A2 Registry** | Where identifiers live and how they resolve (`did:clockchain:…`); **ERC-8004-compatible**, interop with W3C DID, Kite, RNWY — compose, don't compete |
| **A3 Delegation** | Scope of authority encoded — capability scopes, sub-delegation, **time-boxed / conditional / expiring** delegation (the as-of-T core) |
| **A4 Attestation** | Verifiable non-capability claims — certifications, audit results, reputation; EAS / Verax / ERC-8004-reputation compatible |
| **A5 Revocation** | How authority is removed — principal-initiated, auto-triggers (stake loss, expiry, policy), cascading to child agents; **time-stamped so "valid until / revoked at T" is itself provable** |
| **A6 Verification** | How third parties confirm identity *and its validity at a given time* without trusting Clockchain — on-chain proof, court-grade export packet, SDK `verify_agent_identity(at=T)` |

**Composes with:** W3C DID methods, EAS/Verax, **ERC-8004 (Identity/Reputation/Validation)**, RNWY passport, Kite Agent Passport, World ID AgentKit. Regulatory pull: EU AI Act Art. 13 & 72, SOC 2 for AI, NIST AI RMF. **Edge:** not "issue an agent ID" (commoditized by ERC-8004) but **expiring, revocable authority anchored to a public clock.**

## Product B — Agent Attested Receipt (delivered via the Clockchain Agent-SDK)
**One line:** *WHAT the agent did, in what order, and can you prove it to a counterparty who doesn't trust you.* A record of every meaningful action — witnessed by a validator quorum, anchored to a multi-source timestamp, designed for court-grade evidentiary use. The SDK is the *mechanism*; the Receipt is the *product*. Target DX: **"five lines to first attested action."**

| Layer | What it is |
|---|---|
| **B1 Capture** | How the SDK plugs into the host framework & what it captures (LangChain callback, OTel exporter, MCP middleware, Anthropic/OpenAI SDK hooks); events = LLM call, tool call, reasoning step, human intervention |
| **B2 Identity Binding** | Every event stamped with the acting agent's Product A identifier (ERC-8004-compatible); records the full delegation chain (principal → CoS → worker) |
| **B3 Timestamping** | Each event gets an independent Clockchain timestamp — synchronous (~tens of ms) or batched/offline path — establishing **neutral order and existence-at-T**, not just a self-asserted wall-clock |
| **B4 Subnet Anchoring** | Events accumulate in the customer's dedicated subnet; periodic SHA-256 state root rolled to mainnet; subnet geography satisfies data residency (EU/US) |
| **B5 Receipt Minting** | Each completed action → one Receipt (agent identifier, principal chain, in/out hashes, model/tool version, timestamp, quorum signature, anchor refs); JSON + court-grade export packet on demand |
| **B6 Retrieval & Verification** | Query API, audit export (e.g. SEC 17a-4 WORM), dispute-resolution `verify_receipt()`, long-term retention — the **claims-grade record** an adjudicator or insurer consumes |

**Competes with / maps to:** the agent-framework integration surface (LangChain, AutoGPT, CrewAI, AutoGen, LlamaIndex, MCP, Anthropic/OpenAI SDKs); sits as the **anchor layer beneath** observability vendors and **above** ERC-8004 identity + x402 payment (an x402 payment is a consequential, receipt-worthy event). Regulatory pull: EU AI Act Art. 12 & 72.

**Co-dependency:** Product A without B is identity with no record; B without A is records with no provenance. Sold together they are the agent-trust primitive that EU AI Act, eIDAS 2.0, SEC 17a-4, MiFID II, HIPAA, and SOC 2 for AI all point to but observability vendors and identity registries alone can't ship.

## Use cases — the three customer archetypes (CENTRAL to this assessment)
The assessment is customer/PMF-focused. These are the candidate buyers to probe — and to test the exec's stated customer against. Each has a **different buyer** and a **different demand thesis**:

1. **Agent orchestration platforms** — LangChain/LangSmith, Anthropic (Agent SDK / Claude Code), OpenAI (Agents SDK), Microsoft Agent 365, Salesforce Agentforce, ServiceNow.
   *Pitch:* "Your customers' compliance officers need court-grade logs. Ship our SDK as a first-class integration and your enterprise tier gains designed-for-eIDAS evidentiary status." Platform integrates → its customers emit receipts → platform charges a compliance premium. **Buyer: platform PM / Head of Platform.** (Watch for pass-through demand — they buy to solve *their customers'* pain.)

2. **Products embedding agent SDKs** — Notion, Linear AI, Slack AI, Cursor, Warp, productivity SaaS.
   *Pitch:* "When your product invokes an LLM/agent, you assume liability for its actions. The SDK gives you a tamper-evident, court-grade audit trail per invocation — automatically, no product-surface change." **Buyer: product/eng leader** carrying liability for their enterprise customers.

3. **Cybersecurity, regulated verticals & insurance** — SOCs, CrowdStrike Falcon Agent users, banks running internal agents, healthcare AI deployers, legal-tech automation, **and the insurers underwriting all of them.**
   *Pitch:* "When your agent triages an incident, prescribes a clinical decision, executes a trade, or drafts a legal action, you need cryptographic chain of custody — not vendor logs. And when something goes wrong across two vendors, you need a **neutral, time-ordered, claims-grade record** to adjudicate it." **Buyer: compliance / security / legal / claims, NOT engineering.** Acute, budgeted pain. Value = the Receipt format + neutral cross-party ordering + subnet-residency story. *This is where the ERC-8004 gap is widest — reputation says "trustworthy," a claim needs "here's exactly what happened, when, in what order."*

**Regulatory tailwinds across all three:** EU AI Act (Art. 12 logging, Art. 72 post-market), eIDAS 2.0, SEC 17a-4, MiFID II, HIPAA, FDA GMLP, SOX 404, SOC 2 for AI.

## Design partner & stretch products
- **AgentDash** — Yang's other product (a CoS-led multi-human AI workspace) is the **design partner of record** for A & B and ships the first deployment; every task dispatch ≈ an A1 issuance, every task completion ≈ a B5 receipt. *In customer-facing options, gloss as "our design partner," not by name.*
- **Stretch:** Agent Credit / reputation on top of A's identity (composing **x402** and ERC-8004 Reputation rails) and standalone regulator-grade Receipts — the research suggests these converge. **Agent insurance** is the sharpest stretch the ERC-8004 reckoning surfaces: ERC-8004 supplies the agent's standing; Clockchain supplies the claims-grade evidence that makes a policy underwritable and a claim adjudicable.

## How to use this in the interview
- Use the **three archetypes as the customer options** when probing Customer Clarity — orchestration platform vs embedded product vs regulated-vertical/insurer buyer. Each implies a different budget owner (platform PM · product/eng · compliance/legal/claims) and a different demand thesis.
- **Probe the ERC-8004 split.** When an exec names "agent identity" as the product, push: ERC-8004 + x402 increasingly cover *who the agent is* and *how it pays.* Does your customer's pain live there — or in **independent time, neutral ordering, and a provable receipt of the act**, which those standards don't provide? An exec who can't tell the two apart hasn't found the wedge.
- The most acute, budgeted pain likely sits in **archetype 3** (compliance/legal/claims). The classic mismatch to surface: an exec names the *platform* (archetype 1) as the customer, but the pain they describe is owned by a *regulated enterprise's compliance officer or an insurer's claims desk* (archetype 3). Name that mismatch.
- Anchor product questions in real **layers** when useful (e.g. "Is the wedge A6 Verification — the court-grade export a regulator consumes — or B5/B6 Receipt minting and retrieval?"), but keep scoring holistic across the 5 product/market dimensions.
