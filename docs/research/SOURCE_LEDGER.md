# Mckani Source Ledger

**Observed/planning date:** 2026-09-23

This ledger records research/adoption intent. It does not claim every source is production-qualified.

## Status vocabulary

- FOUNDER_PERMISSION_RECORDED — founder stated permission in current project discussion; exact scope/path evidence still required before copy.
- OWNED_SOURCE — repository under founder GitHub control; exact donor revision/path still recorded before transfer.
- OPEN_DEPENDENCY_CANDIDATE — public dependency/data source; exact release/license/notice qualification required.
- PROVIDER_REFERENCE — external service/product; terms/cost/privacy separate.
- REFERENCE_ONLY — architecture/product research unless later promoted.
- EXPERIMENT — benchmark candidate, no production admission.

## Founder-named mapping sources

| Source | Planned use | Mode | Current planning note |
|---|---|---|---|
| hyperknot/openfreemap | Open basemap/tile infrastructure, self-host/static distribution patterns | FOUNDER_PERMISSION_RECORDED / DEPEND / ADAPT | Public service is no-key and open; no geocoder/router/traffic/satellite assumption. OSM/OpenMapTiles/data/assets rights separate. |
| bilawalsidhu/gods-eye-view | Live layers, scene/camera, share state, optional 3D, voice-to-scene patterns | FOUNDER_PERMISSION_RECORDED / ADAPT_SELECTIVE | Reject named-person tracking, facial recognition, surveillance/military semantics, and unqualified bundled provider assets. |
| maplibre/maplibre-gl-js | Primary web renderer | FOUNDER_PERMISSION_RECORDED / OPEN_DEPENDENCY_CANDIDATE | Prefer dependency over copying internals. Renderer rights separate from data/providers. |
| maplibre/maplibre-native | Native iOS/Android renderer candidate | OPEN_DEPENDENCY_CANDIDATE | Separate mobile performance/offline/accessibility/privacy qualification. |
| Mapbox product/source material | Product/provider/AI-location reference; optional provider adapters | FOUNDER_PERMISSION_RECORDED / PROVIDER_REFERENCE | Exact proprietary source artifact/scope not identified. Do not copy proprietary source until covered revision/path evidence exists. APIs/data retain separate terms/cost. |

## Founder-named Jev/decision sources

| Source | Planned use | Mode | Observed facts |
|---|---|---|---|
| AlexWortega/openjev | Tier-2 semantic judge/reranker/NLI challenger | FOUNDER_PERMISSION_RECORDED / EXPERIMENT | HF metadata observed 2026-09-23: text-classification, Qwen3.5-4B base, English, MIT metadata. |
| convaiinnovations/laya | Tier-1 calibrated typed decision challenger | FOUNDER_PERMISSION_RECORDED / EXPERIMENT | HF metadata observed 2026-09-23: 421.3M parameters, Apache-2.0 metadata, routing/scoring/guardrails tags. |
| bespokelabs/Bespoke-Nimble-9B | Heavier evidence-grounded decision challenger | EXPERIMENT | HF metadata: Qwen3.5-9B LoRA, Apache-2.0 metadata. |
| Knowledgator/GLiClass | Dynamic-label classifier/reranker challenger | EXPERIMENT | Upstream describes zero-shot/hierarchical classification and single-forward-pass efficiency. Exact code/model artifacts re-qualified. |
| TheoLeeCJ/SemIf | Typed semantic-if decision research | REFERENCE_ONLY / EXPERIMENT | Recorded in Kernux research. Exact current upstream identity/revision/license must be re-established. |
| Mapika/decider | Typed choices/scores/boolean decision research | REFERENCE_ONLY / EXPERIMENT | Recorded in Kernux research. Exact current upstream identity/revision/license must be re-established. |

A broad statement that "all Jev alternatives are permitted" does not replace exact-source provenance for future imports.

## TheHalfMoon owned-source reuse

| Repository | Reuse role | Mode |
|---|---|---|
| TheHalfMoon/Morize | governed memory, bi-temporal truth, evidence graph, memory firewall, context compiler, planning governance | OWNED_SOURCE / ADAPT_SELECTIVE |
| TheHalfMoon/kernux | capability kernel, agent/runtime policy, MCP/A2A, DecisionProvider abstraction, replay/evidence, zero-runtime-COGS boundary | OWNED_SOURCE / ADAPT_SELECTIVE |
| TheHalfMoon/Himsat | audio/STT routing, resource governor, OCR/vision/document IR, model registry, multimodal evidence | OWNED_SOURCE / ADAPT_SELECTIVE |
| TheHalfMoon/Wispral | Command/Aside, interruption, barge-in, voice provenance, voice benchmark methodology | OWNED_SOURCE / ADAPT_SELECTIVE |
| TheHalfMoon/wepld | provenance-first retrieval/RAG, access monotonicity, exact/lexical/graph/semantic retrieval routing, source safety | OWNED_SOURCE / ADAPT_SELECTIVE |
| TheHalfMoon/acarat | explainable area/property scoring, commute, spatial decision patterns, alerts | OWNED_SOURCE / ADAPT_SELECTIVE |
| TheHalfMoon/Zyara | geospatial provider boundaries, entrance vs centroid, map/list parity, verified reputation, privacy-safe geo UX | OWNED_SOURCE / ADAPT_SELECTIVE |
| TheHalfMoon/Qdrat | enterprise workflows/analytics/integration references where relevant | OWNED_SOURCE / REFERENCE/ADAPT_SELECTIVE |
| TheHalfMoon/Ascout | security/testing/review patterns where relevant | OWNED_SOURCE / REFERENCE |
| TheHalfMoon/SpecGrain | recursive specification/readiness control | DEPEND_TOOL_PIN |
| TheHalfMoon/Diffcipline | exact-diff proof-before-done | DEPEND_TOOL_PIN |

No code is copied from these repos by this planning PR.

## Open world/data foundation

| Source | Role | Mode / rights note |
|---|---|---|
| Overture Maps Foundation | addresses, buildings, divisions, places, transportation, GERS stable IDs, GeoParquet | DATA / OPEN_DEPENDENCY_CANDIDATE. Preserve per-theme/upstream attribution and license requirements. |
| OpenStreetMap | road/place/community world data | DATA. ODbL/attribution and derived-database implications explicitly reviewed. |
| OpenMapTiles | vector tile schema/tooling in relevant paths | REFERENCE/DEPENDENCY candidate; exact component/data rights separate. |
| Natural Earth | small-scale geographic reference where used | DATA candidate; exact included assets/attribution reviewed. |
| GTFS Schedule/Realtime | transit interchange; RT delays/alerts/vehicle positions | OPEN_STANDARD/DATA; actual agency feeds carry their own terms. |

## Geospatial/runtime candidates

| Source | Role | Mode |
|---|---|---|
| H3 | hierarchical global spatial indexing/aggregation/flow/ML features | OPEN_DEPENDENCY_CANDIDATE |
| DuckDB + spatial | local/embedded GeoParquet and analytical spatial engine | OPEN_DEPENDENCY_CANDIDATE |
| SQLite FTS5/RTree | local transactional/search/spatial-index primitives | PLATFORM DEPENDENCY |
| PostgreSQL/PostGIS | shared enterprise/mobility geospatial truth | OPEN_DEPENDENCY_CANDIDATE |
| Valhalla | routing, matrices, isochrones, map matching, time-based/multimodal/offline regional graph candidate | EXPERIMENT -> DEPEND candidate |
| VROOM | VRP/VRPTW/multi-depot/pickup-delivery optimization | EXPERIMENT -> DEPEND candidate |
| Google OR-Tools | optimization reference/optional solver | EXPERIMENT/REFERENCE |
| OpenTripPlanner | OSM + GTFS multimodal transit routing reference/optional server | REFERENCE/EXP |
| PMTiles/Protomaps ecosystem | static range-readable map archive/distribution candidate | EXPERIMENT; exact library/license/hosting behavior reverify |
| CesiumJS | optional advanced 3D/3D Tiles/time-dynamic view | OPEN_DEPENDENCY_CANDIDATE |
| Cesium ion | terrain/imagery/services | PROVIDER_REFERENCE; separate token/cost/terms |

## Voice and multimodal candidates

These are inherited as research candidates from Himsat/Wispral and are not frozen.

| Source | Role | Mode |
|---|---|---|
| ggml-org/whisper.cpp | portable local ASR | EXPERIMENT -> DEPEND |
| k2-fsa/sherpa-onnx | ASR/VAD/diarization/speaker/KWS/TTS substrate | EXPERIMENT -> DEPEND |
| moonshine-ai/Moonshine family | low-latency edge speech challenger | EXPERIMENT |
| snakers4/silero-vad | VAD challenger | EXPERIMENT |
| Argmax/WhisperKit paths | Apple-native speech acceleration research | EXPERIMENT |
| OpenWhispr/OpenSuperWhisper/VoiceStudio/Meetily sources | UX/orchestration/failure-knowledge inputs | REFERENCE/SELECTIVE only after exact provenance |
| Himsat OCR/vision source catalog | OCR/document/vision candidates | RESEARCH INPUT; qualify exact source per task |

## Commercial/live provider references

These are **not** core dependencies.

| Provider/product | Potential value | Policy |
|---|---|---|
| Mapbox | traffic, navigation/location infrastructure, commercial map services, AI-location product reference | optional provider/reference only |
| HERE | traffic/routing/fleet/truck data | optional provider |
| TomTom | traffic/incidents/routing | optional provider |
| Radar | geofencing, location, maps/routing/place-visit patterns | optional provider |
| Foursquare Places | POI enrichment, ratings/reviews/popularity | optional provider |
| Google Maps Platform | places/routes/route optimization/product benchmark | optional provider/reference |
| CARTO | agentic/enterprise GIS/warehouse execution reference | product/architecture reference |
| national/municipal sources | official addressing, transit, traffic, events, boundaries | region-specific adapter after terms/access qualification |

## Current public research facts used by the founding plan

Observed 2026-09-23 from official/public sources:

- Overture schema v2.0.0 documents six themes: addresses, base, buildings, divisions, places, transportation.
- Overture GERS registry tracks stable GERS identifiers across releases.
- MapLibre GL JS supports globe/3D/terrain/custom layers and remains renderer-only in Mckani semantics.
- OpenFreeMap public instance advertises no registration/API keys/limits, but Mckani assumes no production SLA from that statement.
- DuckDB 1.5 moved GEOMETRY into core while most spatial functions remain in its spatial extension.
- H3 4.x provides hierarchical cell/edge/vertex indexing and is Apache-2.0 per project documentation.
- Valhalla documents routing plus matrix/isochrone/map matching and offline/regional tiled graph goals.
- VROOM documents CVRP, VRPTW, multi-depot heterogeneous, and pickup-delivery problem support.
- GTFS Realtime defines trip updates, service alerts, and vehicle positions.
- Mapbox announced "Location Infrastructure for AI" in September 2026, confirming that chat-over-map alone is not a durable category differentiator.

These observations must be revalidated when they become implementation dependencies.

## Promotion checklist

Before SOURCE_LEDGER entry becomes production dependency/import:

- exact version/revision;
- exact selected paths/package/model;
- license/permission;
- notices;
- submodules/transitive artifacts;
- model/data rights;
- CVE/security posture;
- maintenance;
- supported targets;
- performance evidence;
- privacy/network behavior;
- cost;
- fallback;
- SBOM entry;
- rollback/removal plan.
