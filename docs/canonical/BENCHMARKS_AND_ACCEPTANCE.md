# Benchmarks and Acceptance Program

## 1. Purpose

Mckani is ambitious enough that architecture claims must be converted into reproducible measurements.

This document defines benchmark families. Exact numeric release thresholds are fixed by the owning Grain before a candidate is selected; they are not invented retroactively after results are seen.

## 2. Benchmark governance

For each benchmark:

- preregister dataset/corpus;
- pin source versions;
- define target hardware;
- define cold/warm state;
- define metrics;
- define exclusions;
- preserve failed/losing cells;
- bind result to code/model/data revision;
- do not tune on hidden test data;
- state population/region limitations.

A provider marketing benchmark is research input, not Mckani PASS evidence.

## 3. Reference device classes

P00 defines reproducible reference classes:

- low/mid mobile;
- flagship mobile;
- ordinary laptop CPU/iGPU;
- developer workstation;
- self-hosted small server;
- enterprise server profile.

Claims name the class actually tested.

## 4. Rendering benchmark

Measure:

- time to first useful map;
- pan/zoom frame pacing;
- label stability;
- layer update latency;
- memory;
- battery/thermal;
- low-end behavior;
- WebGL/native failures;
- 3D degradation;
- Arabic/RTL;
- accessibility fallback.

## 5. Region pack benchmark

Measure:

- download size;
- install;
- validation;
- update;
- rollback;
- search index build;
- routing graph activation;
- corruption recovery;
- disk pressure.

## 6. Search/geocoding benchmark

Corpora must include:

- Arabic;
- English;
- code switching;
- Arabic and Western numerals;
- transliteration;
- landmarks;
- partial/typo queries;
- duplicate names;
- rural/urban;
- addresses;
- categories;
- viewport/bounds.

Metrics:

- top-k relevance;
- exact address success;
- entity identity precision;
- latency;
- memory/index size;
- stale/duplicate handling.

## 7. Entity resolution benchmark

Positive/negative/hard-negative pairs.

Measure:

- false merge;
- missed merge;
- confidence calibration;
- human-review rate;
- rollback/unmerge.

False merge cost is explicitly weighted for high-impact entities.

## 8. Routing benchmark

Compare candidate engines/configurations for:

- route success;
- legal/restriction behavior where data supports;
- distance/time;
- alternate routes;
- time dependence;
- pedestrian/cycle;
- matrix;
- isochrone;
- map matching;
- offline footprint;
- build/update cost;
- Arabic/localized instruction quality.

## 9. ETA benchmark

Stratify by:

- region;
- trip length;
- time;
- congestion;
- mode;
- weather/event where available;
- pickup/drop-off friction.

Metrics:

- MAE;
- quantile/interval calibration;
- underprediction tail;
- stability;
- compute latency.

No one-number ETA accuracy claim.

## 10. DecisionProvider benchmark

For Laya/GLiClass/OpenJev/other candidates:

- task accuracy/F1/ranking metric;
- Brier/calibration;
- abstention;
- OOD;
- dynamic labels;
- Arabic/English/code-switching;
- adversarial inputs;
- latency;
- RAM;
- disk;
- battery/thermal;
- CPU/GPU/NPU.

Different tasks may select different providers.

## 11. Voice benchmark

From Wispral/Himsat principles:

- WER plus spatial entity accuracy;
- address/place binding;
- command/aside;
- endpointing;
- noisy vehicle/outdoor;
- Bluetooth;
- correction;
- interruption/barge-in;
- latency;
- resource use;
- network lock;
- long-session stability.

## 12. Memory benchmark

Measure:

- exact recall;
- temporal eligibility;
- contradiction handling;
- scope leakage;
- deletion;
- stale memory suppression;
- FTS baseline;
- graph benefit;
- vector/reranker incremental value;
- context precision/recall;
- latency;
- audit/explain.

## 13. World Pulse benchmark

Per feed/layer:

- freshness;
- coverage;
- missingness;
- false events;
- stale detection;
- outage behavior;
- conflation;
- provider disagreement;
- privacy aggregation behavior.

Busy-place predictions need calibration against observed aggregate outcomes.

## 14. Mobility benchmark

### Dispatch

- candidate-generation latency;
- assignment latency;
- hard-constraint violations;
- pickup ETA;
- empty distance;
- completion;
- churn/reassignment;
- workload/fairness constraints.

### Optimization

- problem size;
- solve time;
- objective;
- constraint satisfaction;
- optimality gap when reference known;
- stability under incremental change.

### Delivery

- prep estimate;
- courier wait;
- batch detour;
- on-time rate;
- final handoff/arrival friction.

## 15. Enterprise benchmark

- tenant isolation;
- large spatial joins;
- connector freshness;
- ingestion throughput;
- concurrent analysis;
- API latency;
- agent workflow latency;
- export;
- backup/restore;
- upgrade;
- provider outage;
- data residency/egress tests.

## 16. Security benchmark

Include:

- cross-tenant adversarial tests;
- SSRF;
- prompt/tool injection;
- malformed geometry;
- decompression/oversized inputs;
- provider spoof;
- secret leakage;
- malicious style/document;
- sync conflict;
- replay/idempotency;
- location privacy;
- delete/forget;
- model bundle tamper.

## 17. Accessibility acceptance

Test:

- keyboard;
- screen reader;
- text/list alternatives;
- color independence;
- reduced motion;
- mobile target sizes;
- route instruction semantics;
- voice fallback.

## 18. Economics benchmark

Measure:

- baseline no-paid-provider path;
- storage/bandwidth;
- region-pack serving;
- model pack distribution;
- provider cost per relevant unit;
- enterprise self-host operational footprint.

Cost claims state who pays.

## 19. Claim registry

Every public comparative claim should have:

- claim ID;
- exact wording;
- population/region;
- benchmark;
- revision;
- date;
- limitations;
- expiry/revalidation condition.

Marketing must not outrun evidence.
