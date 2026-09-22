# Mckani Architecture

## 1. Architectural objective

Build one spatial intelligence platform whose consumer simplicity, mobility depth, developer composability, and enterprise governance share a common semantic core.

The core must remain useful without a generative model, mandatory Mckani cloud, or proprietary map provider.

## 2. Top-level architecture

~~~text
                    PERSONAL / MOBILITY / BUILDER / ENTERPRISE
                                      |
                    Text | Voice | Touch | Vision | APIs | Agents
                                      |
                                      v
                              Intent & Context
                                      |
                                      v
                         Spatial Capability Kernel
                     authorization | budgets | policy
                                      |
          +---------------------------+---------------------------+
          |                           |                           |
          v                           v                           v
  Deterministic Tools          Decision Fabric              Agent Runtime
 geometry/search/route      classify/rank/abstain       plan/tool/explain
          |                           |                           |
          +---------------------------+---------------------------+
                                      |
                                      v
                                WORLD KERNEL
             identity | geometry | time | state | relations | evidence
                                      |
        +-----------------------------+------------------------------+
        |                             |                              |
        v                             v                              v
 Spatial Memory                 World Pulse                 Scenario Branches
        |                             |                              |
        +-----------------------------+------------------------------+
                                      |
                                      v
                                DATA FABRIC
 open world | region packs | providers | private data | user data
                                      |
          +---------------------------+---------------------------+
          |                           |                           |
          v                           v                           v
    Rendering Fabric            Mobility Fabric             Analytics Fabric
 MapLibre / Cesium / AR     ETA/dispatch/optimization     DuckDB/PostGIS/H3
~~~

## 3. Shared semantic core

The World Kernel owns stable contracts for:

- WorldEntity identity;
- geometry assertions and precision;
- observations;
- bi-temporal state;
- events;
- relations;
- evidence/provenance;
- prediction/scenario types;
- rights/attribution metadata;
- permissions/sensitivity;
- typed actions and effects.

Surface-specific product code may extend these contracts but cannot redefine their semantics.

## 4. Recommended implementation split

### Rust shared core

Rust is the planning default for:

- canonical schemas and validation;
- local database/storage orchestration;
- provider contracts;
- geospatial primitives not delegated to qualified libraries;
- event/runtime orchestration;
- cancellation;
- policy/capability checks;
- sync/conflict semantics;
- model/speech/provider routers;
- desktop daemon/core;
- CLI and benchmark harnesses;
- server modules whose workload benefits from shared contracts.

This is a planning decision, not a requirement to force every UI or data workload into Rust.

### Web and Studio

TypeScript is the planning default for:

- web application;
- Builder Studio;
- Enterprise Studio;
- MapLibre GL JS rendering;
- web SDK;
- browser-facing MCP/tool clients where applicable.

### Native personal/mobile surfaces

Do not make WebView portability the architecture.

Preferred boundary:

- iOS: Swift/SwiftUI shell plus shared Rust core through a stable FFI/UniFFI-style boundary after qualification;
- Android: Kotlin/Compose shell plus shared Rust core;
- native MapLibre renderer qualification per platform;
- platform-native background, audio, notifications, secure storage, accessibility, and permission flows.

### Desktop

A lightweight desktop shell may use Tauri/TypeScript over the Rust core after benchmark and packaging qualification.

### Data/ML workers

Python is allowed behind explicit process/service contracts for research, data preparation, model evaluation, or libraries whose best supported runtime is Python. It is not a hidden requirement for the consumer application.

## 5. Deployment profiles

### Personal embedded/local

~~~text
App
├── Rust core
├── SQLite
│   ├── canonical app/user state
│   ├── FTS5
│   ├── RTree where justified
│   └── event/memory metadata
├── content-addressed local blobs
├── optional DuckDB analytics workspace
├── H3-derived indexes
├── local region data
├── MapLibre
├── optional local routing graph
└── qualified local AI/speech models
~~~

Internet supplies world updates and optional providers. Private state remains local by default.

### Team/self-hosted

A self-hosted control plane adds shared state, synchronization, collaboration, and organization policy without changing World Kernel semantics.

### Enterprise/BYOC

Planning default:

- PostgreSQL + PostGIS for shared transactional/spatial truth;
- S3-compatible object storage for large immutable artifacts;
- transactional outbox/job processing;
- OpenTelemetry-compatible observability;
- tenant-scoped caches and projections;
- optional warehouse adapters;
- optional message/event infrastructure only when measured scale requires it.

Start as a modular monolith with durable contracts. Do not preemptively fragment the system into microservices.

### Managed future

A future managed Mckani service may operate the same contracts. Billing/entitlements exist above semantic truth.

PAID_PLAN != DIFFERENT_WORLD_TRUTH.

## 6. Storage responsibilities

### SQLite

Owns personal/local:

- configuration;
- accountless identity/device state;
- user memory metadata;
- saved places/searches;
- alerts;
- event ledger metadata;
- provider cache metadata;
- local FTS;
- permissions;
- sync state.

### DuckDB

Used for bounded analytical workloads:

- GeoParquet;
- large local joins;
- spatial aggregation;
- offline exploration;
- derived analytics;
- enterprise notebook/report paths.

DuckDB is not required to own every transactional write.

### H3

Used as a derived global indexing/aggregation fabric:

- region/cell addressing;
- heatmaps;
- demand/supply aggregation;
- World Pulse privacy aggregation;
- caching;
- ML features;
- flow analysis.

H3 cell identity is not a replacement for exact geometry.

### PostgreSQL/PostGIS

Default shared server truth for:

- organization/private world entities;
- shared geometries;
- tenancy;
- operational mobility state;
- collaborative objects;
- durable workflows;
- spatial joins/indexes at server scale.

### Derived indexes

Search, graph projections, vectors, tile overlays, H3 cells, analytics marts, model features, and cached routes are rebuildable projections unless a specific contract states otherwise.

INDEX != CANONICAL_TRUTH.

## 7. Event-driven state

Material changes emit typed events.

Examples:

- WorldObservationRecorded;
- GeometryAssertionAdded;
- EntityLinked;
- EntityLinkDisputed;
- WorldStateSuperseded;
- RouteCalculated;
- RouteInvalidated;
- PredictionProduced;
- MemoryCandidateProduced;
- MemoryCommitted;
- ProviderHealthChanged;
- TrafficObservationReceived;
- TripStarted;
- DispatchProposed;
- AssignmentAccepted;
- AssignmentCancelled;
- AlertTriggered;
- ScenarioCreated;
- ActionProposed;
- ActionApproved;
- ActionExecuted.

Events support recovery, audit, replayable projections, synchronization, and evidence.

Replay never means blindly repeating side effects. Operations declare replay semantics: deterministic, idempotent, compensatable, inspect-only, or non-replayable.

## 8. Spatial capability boundary

AI and applications call typed capabilities.

Initial families:

~~~text
world.lookup
world.search
world.observe
world.history
world.diff

geo.distance
geo.contains
geo.intersects
geo.nearest
geo.buffer
geo.area

place.search
place.inspect
place.compare

route.calculate
route.compare
route.matrix
route.isochrone
route.map_match

area.inspect
area.compare
area.score

pulse.query
pulse.forecast

memory.propose
memory.recall
memory.explain
memory.forget_proposal

scenario.create
scenario.modify
scenario.compare

layer.create
layer.update
layer.share

alert.create
alert.evaluate

mobility.dispatch_candidates
mobility.optimize
mobility.eta
mobility.rebalance

camera.fly_to
camera.follow
camera.frame
~~~

Capability names do not grant permission. Policy authorizes each invocation for the principal, resource, data class, runtime, and intended effect.

## 9. Rendering fabric

### MapLibre

Preferred daily 2D/2.5D renderer candidate for web and, after separate qualification, native mobile.

Responsibilities:

- vector tiles;
- styles;
- labels;
- feature interaction;
- heatmaps;
- building extrusion;
- terrain where supported;
- custom layers.

MapLibre does not own data truth, geocoding, routing, rights, or provider identity.

### Cesium

Optional advanced 3D/globe/time-dynamic renderer candidate for:

- 3D Tiles;
- terrain/photogrammetry;
- telemetry;
- world-scale live objects;
- simulation;
- 4D playback.

Cesium ion and third-party imagery/terrain are separate commercial/rights decisions from CesiumJS.

### God's Eye View

Selective reference/donor for:

- layer lifecycle;
- scene/camera behavior;
- live-object interaction;
- shareable scene state;
- voice-to-scene patterns;
- provider fallback concepts.

Reject surveillance semantics, named-person tracking, bundled third-party assumptions, and military/spy framing.

## 10. Open world baseline

Planning baseline:

- OpenFreeMap for open vector basemap/tile infrastructure;
- OpenStreetMap/OpenMapTiles rights handled separately;
- Overture Maps for open world entities, schemas, and stable GERS references where fit;
- regional extracts and static/object distribution where possible;
- PMTiles/MBTiles/GeoParquet-class pack formats evaluated by exact use case;
- local indexes built from explicit region-pack manifests.

The application must not rely indefinitely on an unbounded third-party free endpoint without fallback, cache, mirrors, or an explicit service contract.

## 11. Region packs

A RegionPack is a versioned manifest, not a random directory.

Candidate contents:

- basemap archive/reference;
- place/address search index;
- road/routing graph;
- boundaries;
- POI taxonomy;
- H3 aggregates;
- transit schedules;
- elevation/terrain metadata;
- language aliases/transliteration data;
- attribution/rights manifest;
- source release IDs;
- checksums;
- update channel.

Packs may be:

- automatically streamed/cached;
- explicitly downloaded for offline use;
- organization-customized;
- delta-updated when supported.

Pack installation is crash-safe and rollback-capable.

## 12. Search and geocoding architecture

OpenFreeMap is not a geocoder.

Mckani owns a Geocoder/Search contract and can combine:

- exact identifiers;
- local aliases;
- address components;
- lexical FTS;
- spatial bounds;
- Overture/OSM-derived place data;
- qualified official/national address sources;
- optional provider adapters;
- semantic reranking only after lexical/structured retrieval.

Public Nominatim is never treated as an unlimited production autocomplete backend.

External candidates remain observations until entity resolution.

## 13. Routing architecture

Mckani owns a Router contract.

Open/local candidate foundation: Valhalla or another qualified engine, selected by benchmark and packaging evidence.

Mckani distinguishes:

~~~text
straight-line distance
!= network distance
!= travel duration
!= traffic-aware ETA
!= arrival-confidence interval
~~~

Routing graph, live traffic correction, ETA calibration, route decision/scoring, and dispatch are separate layers.

## 14. Synchronization

Personal sync is optional.

Rules:

- local state remains valid without sync;
- encryption/key model must be explicit before sensitive sync;
- conflicts are surfaced or deterministically reconciled according to object semantics;
- server unavailability cannot silently corrupt local state;
- deletion/forget propagation is first-class;
- large immutable blobs use content identity;
- world/provider caches are not confused with user-owned canonical data.

## 15. Failure philosophy

Every provider family defines degraded behavior.

Examples:

- tiles unavailable -> cached/offline region or textual/list fallback;
- geocoder unavailable -> local index/manual coordinate/known entity paths;
- traffic unavailable -> route without traffic, explicitly labeled;
- AI unavailable -> deterministic search/filter/routing still works;
- speech unavailable -> text/touch controls;
- 3D unavailable -> 2D;
- sync unavailable -> local operation with queued explicit reconciliation;
- enterprise connector unavailable -> preserve last known data with freshness warning, not fabricated current state.

Unknown is a valid result.

## 16. Architecture invariants

~~~text
WORLD_MODEL != RENDERER_STATE
PROVIDER_ID != MCKANI_ID
GERS_ID != PRIVATE_ORGANIZATION_ID
OBSERVATION != VERIFIED_FACT
MODEL_OUTPUT != AUTHORITY
MEMORY_CANDIDATE != DURABLE_MEMORY
SEARCH_SCORE != TRUTH
ETA != GUARANTEE
CACHE != SOURCE
PREDICTION != OBSERVATION
SIMULATION != PREDICTION
LOCALHOST != AUTHENTICATION
MCP_TOOL != AUTHORIZATION
FOUNDER_PERMISSION != THIRD_PARTY_RIGHTS
FOUNDER_ZERO_BURN != USER_FREE_FOREVER
~~~
