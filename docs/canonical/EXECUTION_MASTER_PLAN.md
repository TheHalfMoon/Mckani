# Mckani Execution Master Plan

## 1. Delivery objective

Move from an empty repository to a production-capable spatial platform without building four disconnected products or locking the core to one model/provider.

The sequence is dependency-driven.

## 2. Program map

```text
P00 Governance & Engineering Foundation
 |
 v
P01 World Kernel & Local Persistence
 |
 +------------------+
 v                  v
P02 Map/Packs     P03 Search/Identity
 |                  |
 +--------+---------+
          v
P04 Routing/Navigation/Transit
          |
          v
P05 Decision Fabric & Spatial Intent
          |
    +-----+------+
    v            v
P06 Voice      P07 Spatial Memory
    |            |
    +-----+------+
          v
P08 World Pulse
          |
          v
P09 Places/Reputation/Arrival
          |
          v
P10 Mobility/Delivery/Fleet
          |
    +-----+-------+
    v             v
P11 Multimodal  P12 Collaboration/Alerts
    |             |
    +------+------+
           v
P13 Builder Platform
           |
           v
P14 Enterprise Platform
           |
           v
P15 Prediction/Simulation/Advanced 3D
           |
           v
P16 Network, Hardening, Release
```

Some phases may overlap only when their bounded child Grains have independent dependencies and change surfaces.

## P00 — Governance and engineering foundation

**Method:** controlled.

Deliver:

- minimal real workspace/toolchain;
- project-license ratification or replacement before donor code import;
- source/provenance policy and source manifest;
- pinned SpecGrain execution path;
- repository-owned Diffcipline policy and CI against real commands;
- baseline CI;
- benchmark/result identity manifest;
- dependency/provider/model registries;
- compatibility, secrets, telemetry and egress policy.

Exit: clean install/build/test; governance pins verify; exact proof can run; no floating governance tool, provider secret, or unqualified donor source.

## P01 — World Kernel and local persistence

Deliver validated IDs, external IDs, time, geometry assertions, precision/CRS, evidence/provenance, rights/sensitivity, observations/events/state, scenario namespace, local SQLite persistence, migrations, content identity, reconciliation, rebuildable projections, WorldDiff and recovery tests.

Exit: synthetic world data can persist/reload/version/diff and malformed/corrupt state fails safely.

## P02 — Open map and region packs

Deliver MapLibre qualification, open basemap adapter, attribution, RegionPack manifest, staged install/rollback, local cache, textual/list fallback, first bounded region pack, and native renderer qualification plan.

Exit: accountless first-map path works without API key.

## P03 — Search, geocoding, and identity

Deliver Overture/OSM regional ingest, local place/address lexical index, aliases/transliteration, entity resolution, external-ID bridges, Geocoder contract/provider harness, Arabic/English benchmark.

Exit: search returns typed candidates with provenance/precision and measured conflation behavior.

## P04 — Routing, navigation, and transit

Deliver Router contract, engine bakeoff, route/alternatives/matrix/isochrone/map-match, navigation session/reroute, GTFS/GTFS-RT, travel-time semantics and route-reliability envelope.

Exit: regional navigation works with explicit traffic/no-traffic semantics.

## P05 — Decision Fabric and spatial intent

Deliver DecisionProvider interface, Model Registry/Resource Governor, deterministic fake provider, Laya/GLiClass/OpenJev/eligible alternative benchmark, typed intent compiler, World Formula, ContextBundle retrieval, and optional local System-2 tool path.

Exit: natural language becomes validated typed constraints while core remains useful without models.

## P06 — Voice

Deliver audio/session contracts, ASR/VAD bakeoff, push-to-talk, partial/final transcript, spatial entity grounding, Command/Aside/question/cancel/correction, interruption protection, optional TTS, driving-safe surface and voice benchmark.

Exit: bounded spatial tasks can be completed by voice with visible state, cancellation and text fallback.

## P07 — Spatial Memory

Deliver scoped memory candidates/versions/evidence, exact/FTS/temporal/graph retrieval, inspect/explain, correction/supersession/expiry, forget/redact/export, place/route preferences and organization boundary.

Exit: memory measurably improves a defined task without scope leakage or undeletable hidden history.

## P08 — World Pulse

Deliver Pulse schemas, ProviderHealth, traffic contract, weather/event/transit live adapters, freshness/expiry, prediction envelope, WorldDiff live updates and alert evaluator.

Exit: multiple live/time-varying layers work with explicit freshness and no fabricated live state.

## P09 — Places, reputation, activity, parking and arrival

Deliver source-specific ratings/reviews, dimensions, moderation, personal fit, verified-visit experiment, PlacePulse, busy-now provider/estimation path, ParkingPulse and entrance/arrival intelligence.

Exit: place selection uses explicit dimensions and arrival context while public reputation remains distinct from personal prediction.

## P10 — Mobility, delivery and fleet

Deliver mobility domain, journey timeline, ETA baseline, dispatch state/feasibility, rolling assignment, VROOM/OR-Tools/custom-online bakeoff, batching, driver/courier primitives, merchant state, pickup/drop-off intelligence, proof workflows, fleet profiles, H3 marketplace cells and anti-abuse/idempotency.

Exit: synthetic end-to-end ride/delivery can be created, assigned, routed, rerouted, completed and explained with no hard-constraint violations.

## P11 — Multimodal, OCR, vision and field capture

Deliver safe document IR, OCR/vision provider contracts, geospatial extraction/linking, camera/field evidence, and optional bounded AR experiment.

Exit: supported document/image produces reviewable geospatial candidates without becoming authority by itself.

## P12 — Collaboration, groups and World Triggers

Deliver shared map/list/views, group meetup constraints, comments/annotations/mentions/assignments, trigger notifications, versioned decision records and privacy-safe sharing.

Exit: multiple principals collaborate without leaking unrelated private context or conflating comments with world truth.

## P13 — Builder platform

Deliver public schemas, Rust/TypeScript SDKs, local/API server, event/stream contracts, MCP, webhooks, fake/test providers, extension kit, Builder Studio and compatibility policy.

Exit: a startup can build place/search/route/pulse workflows from stable contracts without internal DB coupling.

## P14 — Enterprise private world

Deliver tenancy, RBAC/resource policy, audit, catalog, private world/layers, connectors, digital twins, workflows/approvals, enterprise agents, OIDC and later SAML/SCIM qualification, warehouse adapter, BYOC/self-host, backup/restore and DR.

Exit: cross-tenant adversarial tests pass and a representative organization can ingest, analyze, collaborate and run governed agents.

## P15 — Prediction, simulation, query-to-layer and advanced 3D

Deliver forecast registry, scenario branches, simulation comparison, World Formula artifacts, Query-to-Layer and optional Cesium/3D Tiles/time playback.

Exit: simulation and prediction remain explicitly distinct from observed world truth and reproducible from versioned inputs.

## P16 — First-party network, hardening, and release

Deliver privacy-safe World Pulse contribution experiment, aggregation/poisoning controls, performance/soak, cross-platform hardening, accessibility closure, source/SBOM audit, install/update, pack distribution, release security, claim registry and operational runbooks.

Exit: exact release candidate satisfies release gates before any production-readiness claim.

## 3. Cross-cutting gates

Every phase owns privacy, accessibility, Arabic/RTL, degraded behavior, source/provenance, benchmark evidence, migration/recovery when persistent, telemetry minimization and cost.

These are not end-of-project cleanup phases.

## 4. Progressive precision

P00-P02 receive the most detailed near-term Grains.

Later phase rows in `specs/tasks.md` are macro work items, not execution authority.

Before each later phase:

1. reverify live repository/provider/source truth;
2. update the source ledger;
3. run required experiments;
4. recursively refine next work into Grains;
5. export bounded WorkPackets.

## 5. Planning completion vs product completion

The founding plan is complete when canonical documents cover known dimensions, the gap audit has no unowned dimension, uncertainty is explicitly gated, the SpecGrain program exists, and the first executable candidate is identified.

The product is not complete until P16 release gates are actually proven.
