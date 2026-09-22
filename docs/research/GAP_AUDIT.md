# Founding Gap Audit

**Purpose:** demonstrate that the founding plan assigns every known architectural dimension an owner, gate, or explicit deferment.

This is not implementation proof.

Legend:

- COVERED — explicit architecture/owner/gate exists.
- EXTERNAL_GATE — design exists; external authority/data/terms/benchmark must close later.
- BENCHMARK_GATE — candidates exist; Mckani evidence must select.
- DEFERRED_BY_DESIGN — intentionally later and not required for first usable slice.
- FOUNDER_GATE — explicit founder decision is still required.

| # | Dimension | State | Owner / evidence |
|---:|---|---|---|
| 1 | Product category/thesis | COVERED | PRODUCT_THESIS |
| 2 | Personal surface | COVERED | PLATFORM_SURFACES |
| 3 | Mobility/delivery surface | COVERED | MOBILITY_DELIVERY_FABRIC |
| 4 | Builder surface | COVERED | PLATFORM_SURFACES |
| 5 | Enterprise surface | COVERED | ENTERPRISE_PLATFORM |
| 6 | Shared-core rule | COVERED | ARCHITECTURE |
| 7 | Canonical WorldEntity | COVERED | WORLD_MODEL |
| 8 | External IDs | COVERED | WORLD_MODEL |
| 9 | Overture GERS role | COVERED | WORLD_MODEL / SOURCE_LEDGER |
| 10 | Entity conflation | COVERED | WORLD_MODEL |
| 11 | False-merge control | COVERED | WORLD_MODEL / BENCHMARKS |
| 12 | Geometry roles | COVERED | WORLD_MODEL |
| 13 | Entrance vs centroid | COVERED | WORLD_MODEL |
| 14 | Curb/pickup/drop-off | COVERED | MOBILITY_DELIVERY_FABRIC |
| 15 | CRS/coordinate validation | COVERED | WORLD_MODEL |
| 16 | Precision classes | COVERED | WORLD_MODEL |
| 17 | Bi-temporal world truth | COVERED | WORLD_MODEL |
| 18 | Observed/inferred/predicted/simulated | COVERED | CONSTITUTION/WORLD_MODEL |
| 19 | Evidence/provenance | COVERED | WORLD_MODEL |
| 20 | Rights metadata | COVERED | WORLD_MODEL / PROVIDER policy |
| 21 | Public/private world overlays | COVERED | WORLD_MODEL |
| 22 | Scenario branches | COVERED | WORLD_MODEL |
| 23 | World diff/history | COVERED | WORLD_MODEL |
| 24 | Map renderer boundary | COVERED | ARCHITECTURE |
| 25 | MapLibre role | COVERED | ARCHITECTURE |
| 26 | Native mobile renderer | BENCHMARK_GATE | P02 |
| 27 | Cesium/advanced 3D | DEFERRED_BY_DESIGN | P15 |
| 28 | God's Eye View selective adoption | COVERED | SOURCE_LEDGER / provider policy |
| 29 | Surveillance rejection | COVERED | CONSTITUTION / threat model |
| 30 | Basemap provider | COVERED | OpenFreeMap baseline |
| 31 | Basemap production SLA | EXTERNAL_GATE | provider deployment choice |
| 32 | OSM/ODbL | EXTERNAL_GATE | exact derivative/distribution review |
| 33 | Attribution | COVERED | provider policy |
| 34 | Overture ingestion | COVERED | data fabric |
| 35 | Overture current release/schema | EXTERNAL_GATE | reverify at ingestion |
| 36 | Region packs | COVERED | ARCHITECTURE / OFFLINE |
| 37 | Pack integrity/rollback | COVERED | OFFLINE |
| 38 | Offline matrix | COVERED | OFFLINE |
| 39 | Sync | COVERED | OFFLINE |
| 40 | Sync encryption | DEFERRED_BY_DESIGN | gated before sensitive sync |
| 41 | Local SQLite | COVERED | ARCHITECTURE |
| 42 | DuckDB analytics | COVERED | ARCHITECTURE |
| 43 | H3 role | COVERED | ARCHITECTURE / Pulse / Mobility |
| 44 | PostGIS shared truth | COVERED | ARCHITECTURE |
| 45 | Search contract | COVERED | ARCHITECTURE |
| 46 | Public Nominatim limitation | COVERED | SOURCE_LEDGER/data fabric |
| 47 | Production geocoder | BENCHMARK_GATE | P03 |
| 48 | Arabic geocoding/search | COVERED | BENCHMARKS |
| 49 | Transliteration | COVERED | PLATFORM/BENCHMARKS |
| 50 | Place taxonomy | COVERED | Overture/provider adapters |
| 51 | Local lexical search | COVERED | architecture/decision fabric |
| 52 | Vectors optional | COVERED | Decision Fabric |
| 53 | Routing contract | COVERED | ARCHITECTURE |
| 54 | Valhalla candidate | BENCHMARK_GATE | P04 |
| 55 | Multimodal routing | COVERED | P04 / source candidates |
| 56 | Transit GTFS/RT | COVERED | Data Fabric |
| 57 | Route vs ETA semantics | COVERED | architecture/mobility |
| 58 | Route reliability intervals | COVERED | BENCHMARKS/Mobility |
| 59 | Live traffic availability | EXTERNAL_GATE | provider/company/network data |
| 60 | Traffic provider abstraction | COVERED | World Pulse |
| 61 | Weather/radar | COVERED | World Pulse provider family |
| 62 | Parking | COVERED | World Pulse/World Model |
| 63 | EV | COVERED | provider/world adapters |
| 64 | Place busy-now | COVERED | World Pulse |
| 65 | Busy-now cold start | EXTERNAL_GATE | licensed feeds / product scale |
| 66 | Privacy-safe pulse network | COVERED | World Pulse/threat model |
| 67 | Ratings/reviews | COVERED | World Pulse |
| 68 | Verified visit | COVERED | World Pulse; implementation later |
| 69 | Review abuse | COVERED | Decision/threat model |
| 70 | Public reputation vs personal fit | COVERED | PLATFORM_SURFACES |
| 71 | Imagery/satellite | EXTERNAL_GATE | provider/data rights |
| 72 | Terrain/photogrammetry | EXTERNAL_GATE | provider/data rights |
| 73 | DecisionProvider contract | COVERED | LOCAL_AI_DECISION_FABRIC |
| 74 | Laya qualification | BENCHMARK_GATE | P05 |
| 75 | OpenJev qualification | BENCHMARK_GATE | P05 |
| 76 | GLiClass qualification | BENCHMARK_GATE | P05 |
| 77 | SemIf/Decider exact upstream | EXTERNAL_GATE | reverify before experiment |
| 78 | Local LLM | BENCHMARK_GATE | P05 |
| 79 | No-model useful core | COVERED | Constitution/Architecture |
| 80 | Calibration/abstention | COVERED | Decision Fabric |
| 81 | OOD | COVERED | Decision benchmark |
| 82 | AI typed tools | COVERED | Architecture |
| 83 | Capability authorization | COVERED | Architecture/Enterprise |
| 84 | MCP | COVERED | Builder/Enterprise |
| 85 | A2A/agent interoperability | DEFERRED_BY_DESIGN | Builder phase |
| 86 | Voice control plane | COVERED | VOICE_MEMORY |
| 87 | Push-to-talk baseline | COVERED | VOICE_MEMORY |
| 88 | Always-listening | DEFERRED_BY_DESIGN | independent privacy/battery gate |
| 89 | Command vs Aside | COVERED | VOICE_MEMORY |
| 90 | Barge-in/cancel | COVERED | VOICE_MEMORY |
| 91 | Local ASR | BENCHMARK_GATE | P06 |
| 92 | TTS | BENCHMARK_GATE | P06 |
| 93 | Arabic/code-switch voice | COVERED | BENCHMARKS |
| 94 | Voice driving safety | COVERED | VOICE_MEMORY |
| 95 | Spatial memory | COVERED | VOICE_MEMORY |
| 96 | Memory scopes | COVERED | VOICE_MEMORY |
| 97 | Forget/export | COVERED | VOICE_MEMORY/OFFLINE |
| 98 | Sensitive memory | COVERED | threat model |
| 99 | Multimodal docs/OCR | COVERED | VOICE_MEMORY |
| 100 | Camera | COVERED | VOICE_MEMORY |
| 101 | AR | DEFERRED_BY_DESIGN | later multimodal |
| 102 | Mobility journey timeline | COVERED | MOBILITY |
| 103 | ETA decomposition | COVERED | MOBILITY |
| 104 | Dispatch | COVERED | MOBILITY |
| 105 | Hard dispatch feasibility | COVERED | MOBILITY |
| 106 | Online reoptimization | COVERED | MOBILITY |
| 107 | Batching | COVERED | MOBILITY |
| 108 | Fleet VRP | COVERED | MOBILITY |
| 109 | VROOM candidate | BENCHMARK_GATE | P10 |
| 110 | OR-Tools candidate | BENCHMARK_GATE | P10 |
| 111 | Marketplace H3 | COVERED | MOBILITY |
| 112 | Merchant intelligence | COVERED | MOBILITY |
| 113 | Driver/courier voice | COVERED | MOBILITY/Voice |
| 114 | Proof of delivery | COVERED | MOBILITY/threat |
| 115 | Mobility anti-abuse | COVERED | MOBILITY/threat |
| 116 | Dynamic pricing/incentives | EXTERNAL_GATE | jurisdiction/product governance |
| 117 | Driver compensation side effects | COVERED | explicit prohibition/approval |
| 118 | Multi-party shared backend | COVERED | MOBILITY/Architecture |
| 119 | Enterprise private world | COVERED | ENTERPRISE |
| 120 | Digital twin semantics | COVERED | ENTERPRISE |
| 121 | Data catalog | COVERED | ENTERPRISE |
| 122 | Connectors | COVERED | ENTERPRISE |
| 123 | Tenant isolation | COVERED | ENTERPRISE/threat |
| 124 | OIDC/SAML/SCIM | DEFERRED_BY_DESIGN | enterprise qualification |
| 125 | Warehouse-native | COVERED | ENTERPRISE |
| 126 | Enterprise agents | COVERED | ENTERPRISE |
| 127 | Workflows | COVERED | ENTERPRISE |
| 128 | Collaboration | COVERED | ENTERPRISE |
| 129 | Decision history | COVERED | ENTERPRISE |
| 130 | BYOC/on-prem | COVERED | ENTERPRISE |
| 131 | Air-gapped subset | DEFERRED_BY_DESIGN | deployment qualification |
| 132 | Data residency/egress | COVERED | ENTERPRISE/threat |
| 133 | SSRF | COVERED | threat model |
| 134 | Prompt/tool injection | COVERED | threat model |
| 135 | Map/style/3D hostile input | COVERED | threat model |
| 136 | Provider secret leakage | COVERED | threat/provider policy |
| 137 | Supply chain | COVERED | threat/governance |
| 138 | Model supply chain | COVERED | threat/Decision |
| 139 | World-data poisoning | COVERED | threat model |
| 140 | GPS spoof/anomaly | COVERED | threat model |
| 141 | Cross-tenant cache/index | COVERED | enterprise/threat |
| 142 | Precise location telemetry | COVERED | threat model |
| 143 | Background location | R3 / DEFERRED | separate explicit product need |
| 144 | Accessibility | COVERED | PLATFORM/BENCHMARKS |
| 145 | Non-map fallback | COVERED | Constitution/Platform |
| 146 | RTL/bidi | COVERED | Platform |
| 147 | Accountless personal core | COVERED | Platform |
| 148 | Notifications/alerts | COVERED | architecture/tools |
| 149 | World Triggers | COVERED | product thesis |
| 150 | Analytics reproducibility | COVERED | enterprise/world evidence |
| 151 | Observability | COVERED | enterprise |
| 152 | Backup/restore | COVERED | enterprise/governance |
| 153 | Migration/rollback | COVERED | governance/offline |
| 154 | App/model update integrity | COVERED | OFFLINE |
| 155 | Provider failure/degraded mode | COVERED | Architecture/provider |
| 156 | Founder zero-runtime-burn | COVERED | provider policy |
| 157 | Commercial managed boundary | COVERED | architecture/provider |
| 158 | Project license | FOUNDER_GATE | Apache-2.0 planning recommendation |
| 159 | Donor permission exact-path proof | EXTERNAL_GATE | before each copy/adapt |
| 160 | SpecGrain governance | COVERED | PLANNING_GOVERNANCE |
| 161 | Diffcipline proof | COVERED | PLANNING_GOVERNANCE |
| 162 | Benchmark methodology | COVERED | BENCHMARKS |
| 163 | Public comparative claims | COVERED | claim registry |
| 164 | Release provenance/SBOM | COVERED | governance |
| 165 | Implementation sequencing | COVERED | EXECUTION_MASTER_PLAN |
| 166 | First executable frontier | COVERED | specs/CURRENT + SpecGrain DRAFT |
| 167 | Long-term source drift | COVERED | requalification per Grain |
| 168 | Unknown future provider | COVERED | stable provider contract |
| 169 | Unknown data | COVERED | fail/unknown semantics |
| 170 | Architecture changes | COVERED | change-control gate |

## Result

**No known architectural dimension in the founding scope is unowned.**

This does not mean all external gates are closed. The unresolved items are deliberately visible:

- founder ratification of the project license;
- exact source/path permission evidence when donor code is imported;
- production providers/terms for traffic, imagery, live places and other non-open feeds;
- benchmark selection among routing/model/speech candidates;
- jurisdictional decisions for pricing/workforce/location features.

Those gates block only the work that depends on them. They are not hidden implementation surprises.
