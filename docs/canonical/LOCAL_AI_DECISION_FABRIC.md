# Local AI and Decision Fabric

## 1. Objective

Mckani needs fast, calibrated decisions for search, ranking, voice intent, routing preferences, memory promotion, moderation, place relevance, alerts, entity resolution, mobility operations, and agent routing.

A large generative model is not the default answer.

The Decision Fabric uses the Jev/select-over-generate philosophy: when the task is bounded choice, score, boolean, rubric, relevance, or reranking, prefer a model that returns a typed calibrated decision over token generation.

## 2. Escalation ladder

~~~text
Tier 0 — Deterministic
rules | SQL | FTS | graph | geometry | routing | constraints

Tier 1 — Micro decision
small calibrated classifiers / score models

Tier 2 — Semantic judge
NLI | cross-encoder | reranker | evidence-grounded decision model

Tier 3 — Local System-2
small/medium generative model using typed tools

Tier 4 — Multimodal
vision | OCR | speech | image/place grounding

Tier 5 — Optional external
explicit user/company-selected remote provider
~~~

Escalate only when lower tiers are insufficient for the declared task.

## 3. DecisionProvider contract

Every probabilistic decision provider implements a provider-neutral envelope.

Input:

- task_type;
- schema/version;
- options/labels/rubric;
- bounded context;
- evidence refs;
- locale;
- requested calibration mode;
- latency/resource budget;
- privacy/network policy;
- model/provider constraints.

Output:

- chosen option(s) or scores;
- calibrated confidence/probability when supported;
- abstain/OOD state;
- provider/model identity and revision;
- runtime identity;
- context digest;
- latency/resource observations;
- explanation/evidence references when supported;
- limitations.

The result is advisory unless deterministic policy explicitly permits an action based on it.

## 4. Current decision-model research set

Observed on 2026-09-23:

### convaiinnovations/laya

Current Hugging Face metadata observed:

- text-classification;
- Transformers AutoModel;
- 421.3M parameters for the inspected model;
- Apache-2.0 metadata;
- tags include calibrated decisions, routing, scoring, guardrails and moderation.

Planned role: Tier-1 low-latency System-1 challenger for bounded choices/scores.

It is not frozen as the default until MckaniBench proves Arabic/English quality, calibration, latency, memory and device fit.

### AlexWortega/openjev

Current metadata observed:

- text-classification / NLI / cross-encoder / reranker;
- Qwen3.5-4B base;
- English;
- MIT metadata.

Planned role: heavier semantic judge/reranker challenger, not always-on primitive.

### GLiClass

Current project describes efficient zero-shot classification in one forward pass and supports dynamic/hierarchical labels.

Planned role: dynamic-label classifier/reranker challenger where labels are not known at model-build time.

Exact code/model licenses and model artifacts are re-qualified at adoption.

### Bespoke-Nimble-9B

Current Hugging Face metadata observed:

- Qwen3.5-9B LoRA;
- text classification / structured prediction / evidence grounding;
- Apache-2.0 metadata.

Planned role: heavier evidence-grounded decision challenger for benchmark comparison, not a consumer baseline.

### SemIf and Decider

TheHalfMoon/kernux already records SemIf and Mapika/decider as decision-provider research candidates.

Mckani adopts the abstraction, not an unverified upstream identity. Exact repository, revision, license, model/runtime closure, and benchmark behavior must be re-established before dependency/import.

## 5. Model-selection rule

There is no permanent "best model" in architecture.

Selection uses a qualified Model Registry and considers:

- task;
- language;
- device class;
- memory;
- accelerator;
- battery/thermal state;
- latency objective;
- model rights;
- network policy;
- calibration;
- failure history;
- privacy class.

No hidden local-to-cloud fallback.

## 6. Resource governor

The client records:

- RAM and available memory;
- GPU/NPU/accelerator capability where exposed;
- battery/charging;
- thermal policy where exposed;
- disk;
- installed model packs;
- resident workers.

User modes:

~~~text
LITE
BALANCED
PERFORMANCE
CUSTOM / ENTERPRISE POLICY
~~~

Modes select capabilities, not truth semantics.

## 7. Typed intent compiler

Natural language becomes a typed request before spatial execution.

Example:

~~~text
"quiet specialty coffee within 15 minutes,
easy parking and not busy"

-> PlaceSearchIntent {
     category: specialty_coffee,
     route_time_max: 15m,
     quietness_min: ...,
     parking: easy,
     activity_max: ...,
     open_at: expected_arrival
   }
~~~

The LLM/classifier may propose the structure. Validation, capability policy and execution are deterministic.

Ambiguous consequential fields trigger clarification or abstention.

## 8. Spatial recommendation

Recommendation has two separate stages:

1. **Eligibility** — hard deterministic constraints.
2. **Preference ranking** — explicit formula and/or qualified decision model.

A model may not rank an option that violates hard eligibility as valid.

Recommended outputs include:

- score;
- dimensions;
- weights/formula;
- evidence;
- freshness;
- unknown dimensions;
- sensitivity to changed weights.

## 9. Decision uses

Initial bounded candidate tasks:

- query intent;
- route objective classification;
- place relevance;
- review spam/irrelevance candidate;
- review theme classification;
- memory candidate action;
- entity-match semantic score;
- alert relevance;
- layer recommendation;
- command vs aside;
- voice confidence escalation;
- enterprise question routing;
- dispatch candidate ranking after hard feasibility;
- incident classification;
- support/contradiction classification.

No decision provider owns:

- authorization;
- legal truth;
- geometry validation;
- hard fleet feasibility;
- tenant boundaries;
- payment mutation;
- memory deletion;
- release verification.

## 10. Calibration and abstention

Every decision benchmark must test:

- accuracy/task metric;
- calibration error/Brier or task-appropriate equivalent;
- abstention quality;
- OOD behavior;
- class imbalance;
- adversarial phrasing;
- Arabic;
- English;
- Arabic-English code switching;
- ambiguous inputs;
- stale evidence;
- disagreement.

A provider that cannot express uncertainty is unsuitable for authority-adjacent tasks unless wrapped by a stricter deterministic gate.

## 11. Provider disagreement

For selected tasks Mckani may compare two qualified decision providers.

Disagreement does not trigger majority-vote truth.

Policy may:

- fall back to deterministic rule;
- escalate to heavier judge;
- ask the user;
- require enterprise review;
- return unknown.

## 12. Local System-2

Generative models are useful for:

- decomposition;
- explanations;
- multi-step spatial planning;
- natural-language summaries;
- tool orchestration;
- formula suggestions;
- scenario setup;
- report drafting.

They receive bounded ContextBundles and typed tools.

They do not receive ambient access to every local/private dataset.

## 13. Context compiler

~~~text
intent
-> required evidence classes
-> scope authorization
-> exact/entity lookup
-> spatial/temporal filters
-> lexical search
-> graph traversal
-> optional vectors
-> optional reranking
-> contradiction/freshness handling
-> budget
-> ContextBundle
~~~

Exact and lexical retrieval must remain useful without embeddings.

## 14. Vector policy

Vectors are optional derived indexes.

Admit them only when a reproducible benchmark shows incremental value for a defined task.

Missing embeddings must not break core search, memory, or world lookup.

## 15. Mckani Decision Bench

The founding benchmark program includes:

- place intent;
- Arabic/English geospatial query parsing;
- code-switching;
- dynamic labels;
- route preference;
- review moderation;
- entity conflation;
- memory mutation proposals;
- command/aside;
- dispatch ranking on feasible sets;
- OOD/abstention;
- latency/resource use across device tiers.

No model is called the Mckani default until the exact model/runtime artifact passes the relevant cell.
