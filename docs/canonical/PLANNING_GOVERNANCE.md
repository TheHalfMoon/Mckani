# Planning and Delivery Governance

## 1. Purpose

Mckani uses SpecGrain to control decomposition/readiness and Diffcipline to control the proof-before-done floor.

~~~text
Product intent
-> canonical architecture
-> SpecGrain refine/bound/order
-> WorkPacket
-> human or coding agent
-> exact implementation revision
-> Diffcipline exact-diff proof
-> semantic/security/source review as required
-> canonical merge
-> post-merge evidence
~~~

No agent self-report or narrative handoff establishes completion.

## 2. Authority order

1. live GitHub/repository truth;
2. AGENTS.md;
3. CONSTITUTION.md;
4. .specgrain canonical state;
5. accepted architecture/requirements;
6. docs/canonical;
7. active WorkPacket;
8. docs/research/source evidence;
9. historical summaries.

## 3. SpecGrain

Mckani pins TheHalfMoon/SpecGrain to an exact commit.

Lifecycle available in the pinned current source:

~~~text
DRAFT -> SHAPED -> REFINING -> GRAIN
~~~

A leaf becomes a Grain only when readiness proves:

- bounded outcome;
- scope in/out;
- acceptance;
- dependencies;
- risk/recovery;
- context budget;
- change surface;
- evidence;
- minimality;
- safety status.

Program-phase DRAFTs are not implementation authority.

## 4. Rolling-wave planning

Later phases remain coarse enough to absorb evidence.

The next dependency-eligible phase is recursively refined.

Only the current bounded leaf becomes a Grain.

Do not create hundreds of brittle detailed Grains for features whose architecture/provider evidence may change before execution.

## 5. WorkPacket

A WorkPacket binds:

- exact Spec revision;
- exact repository baseline;
- exact context source revisions;
- context budget;
- allowed change surface;
- acceptance checks;
- evidence expectations;
- risk/recovery.

Context selection prefers the smallest exact authority needed.

## 6. Diffcipline

Mckani adopts Diffcipline v1 proof semantics:

- PASS / 0 — configured hard requirements observed and satisfied;
- REVIEW / 1 — no hard failure, judgment/evidence remains;
- FAIL / 2 — hard requirement/verification failed;
- 64 — usage/execution error, no proof verdict.

Binding rule:

~~~text
NOT RUN != PASS
~~~

The founding planning PR does not fabricate .diffcipline.toml commands before a real implementation workspace exists. P00 activates repository-owned policy together with the actual workspace commands.

## 7. Risk profiles

### R0 — documentation/non-behavior

Minimum:

- exact diff inspection;
- structural/link checks;
- no unrelated changes;
- source claims checked where changed.

### R1 — bounded stateless behavior

Examples:

- pure geometry helper;
- presentation;
- non-persistent utility.

Minimum:

- formatting;
- static analysis;
- focused tests;
- impacted integration tests.

### R2 — persistent/provider/data behavior

Examples:

- database schema;
- provider adapter;
- routing/search behavior;
- model/runtime dependency;
- voice pipeline;
- cache;
- SDK/API;
- connector;
- mobility solver;
- new dependency.

Minimum:

- R1;
- full relevant workspace tests;
- failure-path tests;
- dependency/source/license review;
- compatibility/persistence tests;
- platform evidence where relevant.

### R3 — trust/recovery/high-consequence

Examples:

- authorization;
- tenant isolation;
- secrets;
- precise-location sharing;
- background location;
- sync;
- encryption;
- public/private publication;
- memory forget/redact;
- dispatch/payment/pricing authority;
- release/update;
- destructive migration.

Minimum:

- R2;
- adversarial/security tests;
- rollback/recovery rehearsal;
- fault injection where relevant;
- cross-platform/tenant checks;
- independent semantic/security review;
- exact-head qualification.

## 8. Method routing

### Controlled

Use for:

- canonical world storage;
- identity/conflation semantics;
- authorization;
- privacy;
- source rights;
- migrations;
- sync;
- enterprise tenancy;
- release/update;
- deletion;
- provider secrets.

### DMADV-lite

Use for new product capabilities:

- World Kernel;
- Decision Fabric;
- voice-native spatial interaction;
- Spatial Memory;
- World Pulse;
- mobility dispatch;
- query-to-layer;
- scenarios.

### Experiment

Use where the decision is uncertain:

- Laya vs GLiClass vs OpenJev/other judge;
- routing engine;
- speech engine;
- local LLM;
- vector value;
- traffic provider;
- busy-place model;
- ETA model;
- optimizer settings;
- rendering performance alternatives.

Experiment output is evidence plus decision, not silent production code.

### DMAIC-lite

Use for reproduced defects/performance/reliability failures.

### Quick

Only for low-risk already-understood documentation or isolated maintenance.

## 9. Donor and dependency policy

Before adding runtime dependency or copied source answer:

1. what problem does it solve;
2. why existing/native code is insufficient;
3. exact source revision;
4. selected paths/package;
5. transitive closure;
6. license/notice/data/model rights;
7. network/telemetry/credentials;
8. unsafe/FFI/process behavior;
9. founder/customer cost;
10. security;
11. removal/replacement path;
12. benchmark if competing candidates exist.

Founder permission makes a donor eligible, not trusted.

## 10. Source-code review

For code-bearing PRs:

- exact diff review;
- Diffcipline;
- semantic review;
- source/license review if dependency/donor changes;
- threat review for R3;
- review every excluded/binary/generated file by an appropriate mechanism.

Alibaba Open Code Review may be used as an additional review-only tool when available, but it never replaces SpecGrain, Diffcipline, source qualification, security review, or required human judgment.

## 11. Architecture change control

A material change requires explicit planning/ADR revision before implementation if it changes:

- World Model semantics;
- public API compatibility;
- identity/conflation;
- time/truth semantics;
- privacy/authorization;
- project license;
- source-rights policy;
- founder-cost boundary;
- mandatory cloud/provider;
- canonical storage;
- deployment support;
- sync/encryption;
- surveillance boundary;
- mobility compensation/pricing authority;
- release/update trust;
- benchmark claim protocol.

## 12. Phase exit

A phase closes only when:

- required child Grains accepted;
- dependency-required work closed;
- exact evidence exists;
- docs match implementation;
- applicable Diffcipline proof PASS;
- material review findings resolved;
- migration/recovery proof exists where required;
- residual risks recorded;
- canonical merge and post-merge checks succeed where configured.

## 13. Release gate

A release additionally requires:

- source/license audit;
- SBOM;
- supported-platform evidence;
- installer/package checks;
- model/data manifests;
- upgrade/migration proof;
- backup/restore proof for persistent profiles;
- security closure;
- privacy/egress inspection;
- benchmark evidence for public claims;
- checksums/provenance for release assets;
- compatibility statement;
- provider/cost ledger;
- documentation bound to released behavior.

## 14. Completion language

Allowed:

- "implemented on commit X";
- "focused checks passed";
- "Diffcipline PASS on exact head X";
- "benchmark cell passed target Y".

Not allowed without proof:

- "production ready";
- "best";
- "fully secure";
- "zero cost";
- "accurate everywhere";
- "works offline everywhere";
- "enterprise compliant".
