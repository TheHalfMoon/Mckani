# Mckani

**The spatial operating system for people, companies, applications, and AI agents.**

Mckani is being designed as a local-first spatial intelligence platform rather than a conventional map application. One shared World Kernel supports four product surfaces:

- **Mckani Personal** — exploration, search, navigation, voice, memory, World Pulse, groups, alerts, camera, and context-aware recommendations.
- **Mckani Mobility** — ride-hailing, delivery, courier, fleet, dispatch, ETA, route optimization, pickup/drop-off intelligence, and driver/courier experiences.
- **Mckani Builder** — SDKs, APIs, MCP, typed spatial capabilities, data/layer packs, and developer tooling.
- **Mckani Enterprise** — private world models, digital twins, spatial analytics, agents, workflows, collaboration, governance, BYOC/on-prem deployment, and auditable decisions.

## Product promise

For an individual:

> Install the app. Open it. Connect to the internet. The useful core works without requiring Docker, Python, an API key, or a mandatory Mckani cloud account.

For a company:

> Bring your world, policies, providers, and infrastructure. Mckani supplies one provider-neutral spatial intelligence and mobility fabric instead of forcing the company to assemble unrelated mapping, routing, AI, memory, voice, dispatch, and GIS stacks.

## Engineering thesis

Mckani is built around these foundations:

1. **World Kernel** — identity, geometry, time, state, relations, evidence, confidence, provenance, rights, and actions.
2. **World Pulse** — live and predicted traffic, transit, weather, incidents, events, parking, place activity, and other time-varying signals.
3. **Spatial Memory** — user-owned and organization-owned temporal memory with explicit scope, provenance, expiry, correction, and deletion.
4. **Decision Fabric** — deterministic computation first, then bounded local decision providers, semantic judges, local generative models, and optional remote providers.
5. **Spatial Capability Kernel** — AI proposes typed tool calls; policy authorizes effects; deterministic tools perform spatial truth-sensitive work.
6. **Mobility & Delivery Fabric** — routing, ETA, optimization, dispatch, marketplace state, journey timelines, pickup/drop-off truth, and fleet operations.
7. **Provider Fabric** — renderers, tiles, geocoders, routers, traffic, places, weather, imagery, transit, and commercial services remain replaceable adapters.
8. **Evidence-first trust** — observed, inferred, predicted, and simulated information are never silently collapsed into one truth state.

## Status

**Canonical planning foundation. No production capability is claimed yet.**

The repository was created empty on 2026-09-23. The founding planning branch establishes architecture, source/provenance rules, threat boundaries, SpecGrain decomposition, Diffcipline proof semantics, and the executable program sequence. Product code begins only through a dependency-eligible bounded Grain with exact acceptance and evidence requirements.

## Read first

1. AGENTS.md
2. CONSTITUTION.md
3. docs/canonical/PRODUCT_THESIS.md
4. docs/canonical/ARCHITECTURE.md
5. docs/canonical/WORLD_MODEL.md
6. docs/canonical/EXECUTION_MASTER_PLAN.md
7. docs/canonical/PLANNING_GOVERNANCE.md
8. docs/research/SOURCE_LEDGER.md
9. docs/research/GAP_AUDIT.md
10. specs/CURRENT.md and specs/tasks.md

## Planning discipline

Mckani uses:

- **SpecGrain** to recursively refine work until each executable leaf is bounded, independently understandable, recoverable, and verifiable.
- **Diffcipline** to bind completion claims to the exact diff, repository policy, risk profile, and actually executed verification.
- **Typed DecisionProvider contracts** inspired by the Jev ecosystem for calibrated classification, scoring, reranking, routing, guardrails, and abstention without making probabilistic output an authority.

No agent self-report, benchmark screenshot, provider marketing claim, or green command by itself establishes completion.
