# Mckani Program Tasks

**States:** PLANNED / ACTIVE / BLOCKED / COMPLETE_CANONICAL  
**Authority:** macro program only. A PLANNED row is not implementation authority. Each executable unit must be refined through SpecGrain.

| ID | State | Risk | Outcome | Depends on |
|---|---|---:|---|---|
| MCK-P00-S01-T01 | PLANNED | R1 | Establish minimal Rust/shared-core workspace, toolchain, real fmt/lint/test commands and baseline CI. | founding plan |
| MCK-P00-S01-T02 | PLANNED | R1 | Add pinned SpecGrain execution path and validate tracked state. | T01 |
| MCK-P00-S01-T03 | PLANNED | R2 | Activate repository-owned Diffcipline R0-R3 policy and exact-head CI proof. | T01,T02 |
| MCK-P00-S02-T01 | PLANNED | R2 | Ratify project license and contributor/source-import boundary. | founding plan |
| MCK-P00-S02-T02 | PLANNED | R2 | Implement source manifest, NOTICE/SBOM foundation and donor-import checklist. | T01,license gate |
| MCK-P00-S03-T01 | PLANNED | R1 | Establish reference hardware classes, benchmark manifest and result identity format. | T01 |
| MCK-P00-S03-T02 | PLANNED | R2 | Establish dependency/provider/model registry schemas. | T01,source policy |
| MCK-P00-S04-T01 | PLANNED | R2 | Establish API/schema compatibility and migration policy. | T01 |
| MCK-P00-S05-T01 | PLANNED | R2 | Establish secrets, network-egress, telemetry and local Network Lock development policy. | T01 |
| MCK-P01-S01-T01 | PLANNED | R2 | Implement Mckani IDs, external IDs, time, sensitivity and rights core types. | P00 |
| MCK-P01-S01-T02 | PLANNED | R2 | Implement validated geometry assertion, role, precision and CRS contracts. | P01-S01-T01 |
| MCK-P01-S02-T01 | PLANNED | R2 | Implement observations, events, evidence and provenance contracts. | P01-S01 |
| MCK-P01-S02-T02 | PLANNED | R2 | Implement state assertion, supersession, contradiction and conflict semantics. | P01-S02-T01 |
| MCK-P01-S03-T01 | PLANNED | R3 | Implement local SQLite persistence, migrations and crash-safe writes. | P01-S01,S02 |
| MCK-P01-S03-T02 | PLANNED | R2 | Implement rebuildable FTS/RTree/H3-derived projection boundaries. | P01-S03-T01 |
| MCK-P01-S04-T01 | PLANNED | R2 | Implement WorldDiff and temporal timeline on synthetic fixtures. | P01-S02,S03 |
| MCK-P01-S05-T01 | PLANNED | R3 | Prove backup/export/recovery/corruption behavior for local world store. | P01-S03 |
| MCK-P02-S01-T01 | PLANNED | R2 | Qualify pinned MapLibre web dependency, notices, CSP, RTL and performance. | P00 |
| MCK-P02-S01-T02 | PLANNED | R2 | Implement renderer adapter over World Kernel projections. | P01,P02-S01-T01 |
| MCK-P02-S02-T01 | PLANNED | R2 | Qualify OpenFreeMap development basemap path, rights and attribution. | P00 |
| MCK-P02-S02-T02 | PLANNED | R2 | Implement provider-neutral basemap/style contract and degraded mode. | P02-S02-T01 |
| MCK-P02-S03-T01 | PLANNED | R2 | Define RegionPack manifest, integrity, rights, compatibility and attribution. | P00,P01 |
| MCK-P02-S03-T02 | PLANNED | R3 | Implement staged RegionPack install/update/rollback and corruption recovery. | P02-S03-T01 |
| MCK-P02-S04-T01 | PLANNED | R2 | Prove accountless app-to-first-map path without mandatory API key. | P02 |
| MCK-P02-S05-T01 | PLANNED | R2 | Benchmark/plan native iOS/Android renderer boundary. | P02 web evidence |
| MCK-P03-S01-T01 | PLANNED | R2 | Implement Overture regional importer with release/rights manifest. | P01,P02 pack |
| MCK-P03-S01-T02 | PLANNED | R2 | Implement local place/address lexical index, aliases and taxonomy mapping. | P03-S01-T01 |
| MCK-P03-S02-T01 | PLANNED | R2 | Implement Mckani entity resolution/link/unlink/conflict workflow. | P01,P03-S01 |
| MCK-P03-S02-T02 | PLANNED | R2 | Implement GERS/OSM/provider external-ID bridges without canonical-ID leakage. | P03-S02-T01 |
| MCK-P03-S03-T01 | PLANNED | R2 | Implement Geocoder contract and deterministic fake/provider harness. | P03-S01 |
| MCK-P03-S03-T02 | PLANNED | R2 | Build Arabic/English/transliteration/numeral search benchmark and qualify baseline. | P03-S01,S03 |
| MCK-P04-S01-T01 | PLANNED | R2 | Implement Router contract and route result semantics. | P01,P03 |
| MCK-P04-S01-T02 | PLANNED | R2 | Bake off Valhalla and eligible alternatives on target region/device classes. | P04-S01-T01 |
| MCK-P04-S02-T01 | PLANNED | R2 | Implement route, alternatives, matrix, isochrone and map-match adapters. | routing selection |
| MCK-P04-S03-T01 | PLANNED | R2 | Implement navigation session, instructions, reroute and route invalidation. | P04-S02 |
| MCK-P04-S04-T01 | PLANNED | R2 | Implement GTFS Schedule/Realtime ingestion and multimodal transit adapter. | P04-S01 |
| MCK-P04-S05-T01 | PLANNED | R2 | Implement route comparison/reliability envelope without live-traffic fabrication. | P04-S02 |
| MCK-P05-S01-T01 | PLANNED | R2 | Implement DecisionProvider schema, fake provider and model registry. | P00,P01 |
| MCK-P05-S01-T02 | PLANNED | R2 | Implement Resource Governor and no-silent-cloud-fallback policy. | P05-S01-T01 |
| MCK-P05-S02-T01 | PLANNED | R2 | Benchmark Laya, GLiClass, OpenJev and admitted alternatives by task. | P05-S01 |
| MCK-P05-S02-T02 | PLANNED | R2 | Requalify SemIf/Decider/Nimble or later Jev alternatives before experiment admission. | P05-S01 |
| MCK-P05-S03-T01 | PLANNED | R2 | Implement typed spatial intent/constraint compiler and validation. | P03,P04,P05-S01 |
| MCK-P05-S03-T02 | PLANNED | R2 | Implement explainable World Formula, hard eligibility and preference ranking. | P05-S03-T01 |
| MCK-P05-S04-T01 | PLANNED | R2 | Implement provenance-first ContextBundle retrieval router. | P01,P03 |
| MCK-P05-S05-T01 | PLANNED | R2 | Qualify optional local System-2 tool-use path; deterministic core stays usable without it. | P05 |
| MCK-P06-S01-T01 | PLANNED | R2 | Implement audio/speech session engine and immutable model-runtime manifests. | P00,P05 registry |
| MCK-P06-S01-T02 | PLANNED | R2 | Bake off ASR/VAD candidates on Arabic/English/code-switch spatial corpus. | P06-S01-T01 |
| MCK-P06-S02-T01 | PLANNED | R2 | Implement visible push-to-talk, partial/final transcript and correction. | speech selection |
| MCK-P06-S02-T02 | PLANNED | R2 | Implement bounded spatial voice context and entity grounding. | P03,P06-S02-T01 |
| MCK-P06-S03-T01 | PLANNED | R2 | Implement Command/Aside/question/correction/confirm/deny/cancel semantics. | P05,P06-S02 |
| MCK-P06-S03-T02 | PLANNED | R3 | Implement interruption/barge-in/cancellation stale-effect protection. | P06-S03-T01 |
| MCK-P06-S04-T01 | PLANNED | R2 | Qualify optional local TTS and driving-safe response behavior. | P06 |
| MCK-P07-S01-T01 | PLANNED | R3 | Implement scoped Spatial Memory candidate/version/evidence store. | P01,P05 |
| MCK-P07-S01-T02 | PLANNED | R2 | Implement exact/FTS/temporal/graph memory retrieval and explain. | P07-S01-T01 |
| MCK-P07-S02-T01 | PLANNED | R3 | Implement inspect/correct/supersede/expire/forget/redact/export. | P07-S01 |
| MCK-P07-S03-T01 | PLANNED | R2 | Implement personal place/route preference memory with explicit policy. | P07 |
| MCK-P07-S03-T02 | PLANNED | R3 | Prove sensitive-memory and cross-scope leakage defenses. | P07 |
| MCK-P08-S01-T01 | PLANNED | R2 | Implement World Pulse schemas, freshness/expiry and ProviderHealth. | P01,P04 |
| MCK-P08-S02-T01 | PLANNED | R2 | Implement traffic adapter contract and explicit no-traffic behavior. | P08-S01 |
| MCK-P08-S02-T02 | PLANNED | R2 | Implement weather/radar, event and transit live adapters on qualified sources. | P08-S01 |
| MCK-P08-S03-T01 | PLANNED | R2 | Implement live WorldDiff and freshness UI/result envelope. | P01,P08 |
| MCK-P08-S04-T01 | PLANNED | R2 | Implement base World Trigger condition evaluator. | P08 |
| MCK-P09-S01-T01 | PLANNED | R2 | Implement place enrichment and source-specific reputation model. | P03,P08 |
| MCK-P09-S01-T02 | PLANNED | R2 | Implement review dimensions, moderation and theme-derived analytics. | P05,P09-S01 |
| MCK-P09-S02-T01 | PLANNED | R3 | Prototype privacy-preserving verified-visit eligibility. | P07,P09 |
| MCK-P09-S03-T01 | PLANNED | R2 | Implement PlacePulse historical/current/prediction envelope with confidence. | P08,P09 |
| MCK-P09-S04-T01 | PLANNED | R2 | Implement ParkingPulse, entrance, arrival and park-to-door model. | P01,P08 |
| MCK-P10-S01-T01 | PLANNED | R2 | Implement mobility entities and order/shipment/journey state machines. | P01,P04 |
| MCK-P10-S02-T01 | PLANNED | R2 | Implement ETA stage decomposition and calibration harness. | P04,P08,P10-S01 |
| MCK-P10-S03-T01 | PLANNED | R3 | Implement dispatch feasibility/candidate/assignment state machine. | P10-S01,S02 |
| MCK-P10-S03-T02 | PLANNED | R2 | Implement H3 marketplace aggregate feature layer. | P08,P10 |
| MCK-P10-S04-T01 | PLANNED | R2 | Bake off VROOM/OR-Tools/custom online optimization by problem class. | P04 matrices,P10 |
| MCK-P10-S04-T02 | PLANNED | R3 | Implement rolling reoptimization/batching with hard constraints and bounded churn. | P10-S04-T01 |
| MCK-P10-S05-T01 | PLANNED | R2 | Implement pickup/drop-off/curb/merchant arrival intelligence. | P09,P10 |
| MCK-P10-S06-T01 | PLANNED | R2 | Implement driver/courier voice and low-distraction journey controls. | P06,P10 |
| MCK-P10-S07-T01 | PLANNED | R3 | Implement proof/idempotency/anti-replay/abuse defenses. | P10 |
| MCK-P10-S08-T01 | PLANNED | R2 | Implement fleet vehicle/shift/capacity/skill/time-window profiles. | P10 |
| MCK-P10-S09-T01 | PLANNED | R3 | Define pricing/incentive authority boundary before any production-side effect. | P10 |
| MCK-P11-S01-T01 | PLANNED | R2 | Implement hostile-input document/image IR boundary. | P00,P01 |
| MCK-P11-S01-T02 | PLANNED | R2 | Qualify OCR/vision candidates by task/device/rights. | P11-S01-T01 |
| MCK-P11-S02-T01 | PLANNED | R2 | Implement entity/address/place/date extraction and geo-candidate linking. | P03,P11 |
| MCK-P11-S03-T01 | PLANNED | R2 | Implement camera/field-observation evidence workflow. | P11 |
| MCK-P11-S04-T01 | PLANNED | R2 | Experiment with bounded AR entrance/walking/field guidance. | P11,P04 |
| MCK-P12-S01-T01 | PLANNED | R2 | Implement shared map/list/view state with privacy-safe tokens. | P07,P08 |
| MCK-P12-S01-T02 | PLANNED | R2 | Implement group meetup constraint solver and fair travel comparison. | P04,P05,P12 |
| MCK-P12-S02-T01 | PLANNED | R2 | Implement comments/annotations/mentions/assignments over spatial entities. | P12 |
| MCK-P12-S03-T01 | PLANNED | R2 | Implement World Trigger notifications, retries and deduplication. | P08,P12 |
| MCK-P12-S04-T01 | PLANNED | R2 | Implement versioned decision record and evidence view. | P07,P12 |
| MCK-P13-S01-T01 | PLANNED | R2 | Freeze public schema/version/error/idempotency conventions. | P01-P12 evidence |
| MCK-P13-S01-T02 | PLANNED | R2 | Publish Rust/TypeScript SDK foundations and test/fake providers. | P13-S01-T01 |
| MCK-P13-S02-T01 | PLANNED | R2 | Implement local/API server and streaming/event contracts. | P13-S01 |
| MCK-P13-S03-T01 | PLANNED | R3 | Implement MCP capability adapter without authorization bypass. | P13-S02 |
| MCK-P13-S04-T01 | PLANNED | R2 | Implement webhooks and provider/extension kit. | P13 |
| MCK-P13-S05-T01 | PLANNED | R2 | Build Builder Studio for data/layers/routes/agents/alerts. | P13 |
| MCK-P14-S01-T01 | PLANNED | R3 | Implement organization/tenant/workspace identity and isolation. | P13 |
| MCK-P14-S01-T02 | PLANNED | R3 | Implement RBAC/resource-capability policy and audit. | P14-S01-T01 |
| MCK-P14-S02-T01 | PLANNED | R2 | Implement enterprise data catalog/private world/layer ingestion. | P14-S01 |
| MCK-P14-S02-T02 | PLANNED | R3 | Implement connector authorization, outbox/reconciliation and data-egress policy. | P14-S01,S02 |
| MCK-P14-S03-T01 | PLANNED | R2 | Implement digital-twin projection/freshness/missingness contracts. | P14-S02 |
| MCK-P14-S04-T01 | PLANNED | R3 | Qualify OIDC then SAML/SCIM as contracted requirements demand. | P14-S01 |
| MCK-P14-S05-T01 | PLANNED | R2 | Implement warehouse-native analytical adapter and reproducible results. | P14-S02 |
| MCK-P14-S06-T01 | PLANNED | R3 | Package self-host/BYOC with backup/restore/upgrade proof. | P14 |
| MCK-P15-S01-T01 | PLANNED | R2 | Implement typed prediction registry and calibration metadata. | P08,P05 |
| MCK-P15-S02-T01 | PLANNED | R2 | Implement scenario branch/create/modify/compare. | P01,P15-S01 |
| MCK-P15-S03-T01 | PLANNED | R2 | Implement Query-to-Layer and World Formula artifact versioning. | P05,P15 |
| MCK-P15-S04-T01 | PLANNED | R2 | Qualify Cesium/3D Tiles path with complete 2D fallback. | P02,P15 |
| MCK-P16-S01-T01 | PLANNED | R3 | Prototype opt-in privacy-safe World Pulse contribution/aggregation. | P08,P09 |
| MCK-P16-S01-T02 | PLANNED | R3 | Prove low-count suppression, poisoning defenses and opt-out. | P16-S01-T01 |
| MCK-P16-S02-T01 | PLANNED | R2 | Complete performance/battery/storage/network/soak hardening. | implemented surfaces |
| MCK-P16-S02-T02 | PLANNED | R3 | Complete security/privacy cross-platform release qualification. | implemented surfaces |
| MCK-P16-S03-T01 | PLANNED | R2 | Complete accessibility/Arabic/RTL release qualification. | implemented surfaces |
| MCK-P16-S04-T01 | PLANNED | R3 | Complete SBOM/source/license/model/data/provider audit. | implemented surfaces |
| MCK-P16-S05-T01 | PLANNED | R3 | Prove installer/update/migration/rollback/recovery. | implemented surfaces |
| MCK-P16-S06-T01 | PLANNED | R2 | Bind public claim registry to reproducible benchmark evidence. | benchmarks |
| MCK-P16-S07-T01 | PLANNED | R3 | Qualify first release candidate and post-release operational runbooks. | P16 gates |

## Refinement rule

Only dependency-eligible macro rows near the current frontier should be decomposed into detailed SpecGrain leaves. Do not pre-author brittle implementation Grains for distant work whose provider, benchmark, or architecture evidence can still change.
