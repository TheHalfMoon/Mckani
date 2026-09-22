# Founding Architecture Decisions

These are planning decisions for the founding architecture. They constrain implementation but do not claim implementation exists.

## ADR-0001 — World Kernel is canonical

**Status:** Accepted for planning.

Canonical truth lives in typed world state/evidence, not renderer state, provider payloads, or LLM output.

## ADR-0002 — Truth origin is explicit

**Status:** Accepted.

Observed, attested, inferred, predicted, simulated, and private assertions remain semantically distinct.

## ADR-0003 — Rust shared core with platform-native surfaces

**Status:** Accepted as planning default.

Rust owns shared correctness-sensitive/runtime contracts. TypeScript owns web/Studio. Swift/SwiftUI and Kotlin/Compose are preferred native mobile shells when shaped. Python is allowed for bounded data/ML work.

A benchmark may revise a component boundary; architecture cannot be revised implicitly.

## ADR-0004 — Local storage and shared storage are different profiles

**Status:** Accepted.

Personal/local: SQLite plus rebuildable indexes and optional DuckDB analytical workspaces.

Shared enterprise/mobility: PostgreSQL/PostGIS planning default.

No database product becomes the public semantic API.

## ADR-0005 — MapLibre default, Cesium optional

**Status:** Accepted.

MapLibre is the preferred everyday renderer. Cesium is an optional advanced 3D/time-dynamic renderer.

Renderer choice does not define world truth.

## ADR-0006 — Open world baseline

**Status:** Accepted.

OpenFreeMap, OSM/related open map data, Overture/GERS, region packs, and open/local runtimes provide the baseline where qualified.

Commercial data/services enrich rather than own core correctness.

## ADR-0007 — Geocoder, router, traffic, places, imagery are provider contracts

**Status:** Accepted.

No provider-specific payload becomes canonical Mckani schema.

## ADR-0008 — Decision Fabric uses minimum-sufficient escalation

**Status:** Accepted.

Deterministic -> small typed decision -> semantic judge -> local generative -> optional remote.

No model is frozen until task-specific benchmark qualification.

## ADR-0009 — Spatial Memory adapts Morize governance

**Status:** Accepted.

Memory is versioned, scoped, temporal, evidence-linked, correctable and deletable. Location history is not automatically durable memory.

## ADR-0010 — Voice adapts Wispral/Himsat boundaries

**Status:** Accepted.

Push-to-talk baseline, Command/Aside semantics, interruption/cancellation, provider-neutral speech engine fabric, spatial context grounding.

## ADR-0011 — Mobility is a first-class fabric

**Status:** Accepted.

Routing, ETA, dispatch, batching, pickup/drop-off intelligence and fleet optimization are separate contracts over the shared world.

## ADR-0012 — Shared backend starts modular

**Status:** Accepted.

Enterprise/mobility server starts as a modular monolith with durable event/outbox contracts. Microservices/streaming infrastructure require measured scale.

## ADR-0013 — No surveillance product pivot

**Status:** Accepted.

No default arbitrary named-person tracking, facial recognition, or covert surveillance. Legitimate fleet/workforce use remains governed by explicit organizational purpose/policy.

## ADR-0014 — Project license

**Status:** Founder gate.

Planning recommendation: Apache-2.0 for Mckani-authored open core.

No LICENSE file and no license-dependent donor import until founder ratification or replacement.

## ADR-0015 — SpecGrain + Diffcipline govern delivery

**Status:** Accepted.

Program plans do not authorize implementation. Bounded Grains do. Completion is bound to exact proof.

## ADR-0016 — No mandatory founder-paid runtime service

**Status:** Accepted.

A useful personal core cannot require a founder billing account. Paid/provider paths need explicit cost owner, budget, fallback and exit.

## ADR-0017 — World Pulse network is opt-in and privacy-gated

**Status:** Accepted.

Long-term first-party traffic/activity signals use on-device minimization, aggregation and privacy controls. Raw location history is not a default network contribution.

## ADR-0018 — External data rights travel with lineage

**Status:** Accepted.

Code permission does not imply data/model/API/imagery rights. Rights metadata and attribution are first-class.
