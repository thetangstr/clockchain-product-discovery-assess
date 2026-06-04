# Clockchain Products A & B — Layers & Use Cases (assessment context)

> Public-safe reference for the product & market discovery assessment. Grounds the interview in the **real product layers and customer archetypes** Clockchain has researched, so questions and options aren't generic. Canonical names per baseline v0.2 (2026-05-26). Source: clockchain-research (`product-baseline.md`, `products-overview.md`).
>
> **Naming (locked):** use **Agent Notarized Identity** (Product A), **Agent Notarized Receipt** (Product B), **Agent Notary Layer** (category). The legacy terms *"Birth Certificate"* and *"Smart Receipt"* are deprecated (already claimed by Identity Digital's DNSid and Microsoft). Mapping to the assessment's three topics: **Network** = the substrate both run on · **Agent Identity** = Product A · **Smart Contracts & Receipts** = Product B.

## Thesis (one sentence)
Autonomous agents are entering production faster than the trust infrastructure to govern them. Clockchain is the cryptographic **notary layer** that turns agent action logs from "trust the observability vendor" into **court-admissible, regulator-grade evidence** anchored to a court-proof timestamp.

## The substrate both products run on
- **Customer-dedicated subnets** — each enterprise gets its own staked-node subnet; their logs never touch mainnet, only a periodic hash fingerprint does. Privacy by construction; tens of millions of events/day per customer.
- **Five-layer court-admissible audit chain** — VRF validator election → multi-source UTC time (GPS / atomic clocks / NTP) → independent computation → 2/3 supermajority consensus → permanent linked ledger. Meets eIDAS qualified timestamps, RFC 3161, ISO 18014, ESIGN/UETA. A court expert can verify any receipt from the public ledger — **no trust in Clockchain-the-company required.**
- **Differentiator vs observability stacks** (LangSmith, Helicone, Phoenix, Datadog, OpenLLMetry, Arize): they *capture* traces but the logs stay vendor-stored and trusted-by-inference. Clockchain replaces vendor trust with **cryptographic proof.** It anchors *beneath* them — complementary, not competitive.

## Product A — Agent Notarized Identity
**One line:** *WHICH agent acted, and under what authority.* A court-admissible identity record, issued at agent birth and certified by a validator quorum — recording principal chain, delegated scope, capabilities, economic mandate, revocation state.

| Layer | What it is |
|---|---|
| **A1 Issuance** | How a birth certificate is minted and who may mint it (principal, proof of authority, default policy at birth) |
| **A2 Registry** | Where DIDs live and how they resolve (`did:clockchain:…`); interop with W3C DID, ERC-8004, Kite, RNWY |
| **A3 Delegation** | Scope of authority encoded — capability scopes, sub-delegation, time-boxed/conditional delegation |
| **A4 Attestation** | Verifiable non-capability claims — certifications, audit results, reputation; EAS/Verax compatible |
| **A5 Revocation** | How authority is removed — principal-initiated, auto-triggers (stake loss, expiry, policy), cascading to child agents |
| **A6 Verification** | How third parties confirm identity without trusting Clockchain — on-chain proof, court-admissible export packet, SDK `verify_agent_identity()` |

**Competes with / maps to:** W3C DID methods, EAS/Verax, ERC-8004, RNWY passport, Kite Agent Passport, World ID AgentKit. Regulatory pull: EU AI Act Art. 13 & 72, SOC 2 for AI, NIST AI RMF.

## Product B — Agent Notarized Receipt (delivered via the Clockchain Agent-SDK)
**One line:** *WHAT the agent did, and can you prove it in a court of law.* A court-admissible record of every meaningful action — witnessed by a validator quorum, anchored to a multi-source timestamp. The SDK is the *mechanism*; the Receipt is the *product*. Target DX: **"five lines to first notarized action."**

| Layer | What it is |
|---|---|
| **B1 Capture** | How the SDK plugs into the host framework & what it captures (LangChain callback, OTel exporter, MCP middleware, Anthropic/OpenAI SDK hooks); events = LLM call, tool call, reasoning step, human intervention |
| **B2 Identity Binding** | Every event stamped with the acting agent's Product A DID; records the full delegation chain (principal → CoS → worker) |
| **B3 Timestamping** | Each event gets a court-admissible Clockchain timestamp — synchronous (~tens of ms) or batched/offline path |
| **B4 Subnet Anchoring** | Events accumulate in the customer's dedicated subnet; periodic SHA-256 state root rolled to mainnet; subnet geography satisfies data residency (EU/US) |
| **B5 Receipt Minting** | Each completed action → one Receipt (agent DID, principal chain, in/out hashes, model/tool version, timestamp, quorum signature, anchor refs); JSON + court-admissible packet on demand |
| **B6 Retrieval & Verification** | Query API, audit export (e.g. SEC 17a-4 WORM), dispute-resolution `verify_receipt()`, long-term retention |

**Competes with / maps to:** the agent-framework integration surface (LangChain, AutoGPT, CrewAI, AutoGen, LlamaIndex, MCP, Anthropic/OpenAI SDKs); sits as the **anchor layer beneath** observability vendors. Regulatory pull: EU AI Act Art. 12 & 72.

**Co-dependency:** Product A without B is identity with no record; B without A is records with no provenance. Sold together they are the agent-trust primitive that EU AI Act, eIDAS 2.0, SEC 17a-4, MiFID II, HIPAA, and SOC 2 for AI all require but observability vendors can't ship.

## Use cases — the three customer archetypes (CENTRAL to this assessment)
The assessment is customer/PMF-focused. These are the candidate buyers to probe — and to test the exec's stated customer against. Each has a **different buyer** and a **different demand thesis**:

1. **Agent orchestration platforms** — LangChain/LangSmith, Anthropic (Agent SDK / Claude Code), OpenAI (Agents SDK), Microsoft Agent 365, Salesforce Agentforce, ServiceNow.
   *Pitch:* "Your customers' compliance officers need court-admissible logs. Ship our SDK as a first-class integration and your enterprise tier claims eIDAS-qualified evidentiary status overnight." Platform integrates → its customers emit receipts → platform charges a compliance premium. **Buyer: platform PM / Head of Platform.** (Watch for pass-through demand — they buy to solve *their customers'* pain.)

2. **Products embedding agent SDKs** — Notion, Linear AI, Slack AI, Cursor, Warp, productivity SaaS.
   *Pitch:* "When your product invokes an LLM/agent, you assume liability for its actions. The SDK gives you a tamper-evident, court-admissible audit trail per invocation — automatically, no product-surface change." **Buyer: product/eng leader** carrying liability for their enterprise customers.

3. **Cybersecurity & regulated verticals** — SOCs, CrowdStrike Falcon Agent users, banks running internal agents, healthcare AI deployers, legal-tech automation.
   *Pitch:* "When your agent triages an incident, prescribes a clinical decision, executes a trade, or drafts a legal action, you need cryptographic chain of custody — not vendor logs." **Buyer: compliance / security / legal, NOT engineering.** Acute, budgeted pain. Value = the Receipt format + subnet-residency story.

**Regulatory tailwinds across all three:** EU AI Act (Art. 12 logging, Art. 72 post-market), eIDAS 2.0, SEC 17a-4, MiFID II, HIPAA, FDA GMLP, SOX 404, SOC 2 for AI.

## Design partner & stretch products
- **AgentDash** — Yang's other product (a CoS-led multi-human AI workspace) is the **design partner of record** for A & B and ships the first deployment; every task dispatch ≈ an A1 issuance, every task completion ≈ a B5 receipt. *In customer-facing options, gloss as "our design partner," not by name.*
- **Stretch:** Agent Credit System (reputation/credit on top of A's identity — x402, Coinbase/Skyfire rails) and Agent Smart Receipts (standalone regulator-grade artifacts) — the research suggests these converge.

## How to use this in the interview
- Use the **three archetypes as the customer options** when probing Customer Clarity — orchestration platform vs embedded product vs regulated-vertical buyer. Each implies a different budget owner (platform PM · product/eng · compliance/legal) and a different demand thesis.
- The most acute, budgeted pain likely sits in **archetype 3** (compliance/legal). The classic mismatch to surface: an exec names the *platform* (archetype 1) as the customer, but the pain they describe is owned by a *regulated enterprise's compliance officer* (archetype 3). Name that mismatch.
- Anchor product questions in real **layers** when useful (e.g. "Is the wedge A6 Verification — the court-admissible export a regulator consumes — or B5/B6 Receipt minting and retrieval?"), but keep scoring holistic across the 5 product/market dimensions.
