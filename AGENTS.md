# Mckani Agent and Contributor Rules

## 1. Authority order

When sources disagree, use this order:

1. live GitHub and repository truth;
2. this AGENTS.md;
3. CONSTITUTION.md;
4. canonical SpecGrain state under .specgrain;
5. accepted architecture decisions and canonical requirements;
6. docs/canonical documents;
7. the active bounded WorkPacket;
8. source/research records;
9. historical summaries, prompts, or chat context.

Repository truth always outranks narrative.

## 2. Language

Repository and technical content is English only: code, comments, commands, specifications, plans, issues, PR bodies, reports, evidence, commit messages, reviewer responses, and prompts.

## 3. No implementation by roadmap prose

A roadmap phase is not implementation authority.

Implementation requires:

- a dependency-eligible bounded SpecGrain leaf;
- explicit scope in and scope out;
- acceptance checks;
- risk and recovery;
- change surface;
- context budget;
- evidence requirements;
- source/provenance closure for introduced dependencies or donor code.

If work is too broad to verify independently, refine it.

## 4. Proof before done

Executor self-report is never completion authority.

Every code-bearing change must be reviewed against the exact diff and exact head. Once the real workspace exists, repository-owned Diffcipline policy defines the minimum commands for R0-R3 risk profiles.

NOT RUN != PASS.

## 5. World truth rules

Permanent semantic distinctions:

~~~text
OBSERVED != INFERRED
INFERRED != PREDICTED
PREDICTED != SIMULATED
CONFIDENCE != AUTHORITY
RENDERED_FEATURE != CANONICAL_WORLD_ENTITY
ROUTE_DISTANCE != STRAIGHT_LINE_DISTANCE
ETA != GUARANTEE
DECISION_PROVIDER_OUTPUT != POLICY_DECISION
LLM_OUTPUT != SPATIAL_FACT
~~~

Do not hide or weaken these distinctions in UI, APIs, storage, or agent prompts.

## 6. Deterministic spatial tools before model guesses

Geometry, containment, intersection, routing, matrix computation, isochrones, distance, temporal filtering, authorization, state mutation, pricing constraints, and other correctness-sensitive operations must use typed deterministic implementations where available.

Models may:

- classify;
- rank;
- infer;
- propose;
- explain;
- summarize;
- decompose intent;
- suggest constraints or weights.

Models do not gain write or policy authority through natural-language output.

## 7. Provider neutrality

No renderer, tile provider, geocoder, router, places provider, traffic feed, model provider, cloud vendor, speech engine, or database vendor becomes Mckani semantic authority.

Every provider integration must declare:

- identity and revision/API version;
- capability;
- code license where applicable;
- data/model/service rights;
- attribution;
- privacy/egress behavior;
- retention/training terms where known;
- freshness;
- region coverage;
- cost owner and budget;
- fallback/degraded behavior;
- replacement path.

No silent provider fallback may widen privacy, cost, or authority.

## 8. Source permission is eligibility, not trust

Founder-stated permission to copy or adapt a source makes that source eligible for exact-path qualification. It does not automatically cover:

- bundled third-party code;
- model weights;
- map data;
- imagery;
- fonts;
- icons;
- datasets;
- API/service usage;
- trademarks;
- user data.

Before copied/adapted source enters Mckani, bind exact source revision, selected paths, permission/license evidence, notices, transitive assets, and security review.

## 9. Local-first and founder-cost boundary

The useful personal core must not require a Mckani-hosted inference account or a founder-funded per-query service.

A required paid dependency is prohibited unless a canonical decision records:

- cost owner;
- budget cap;
- why open/local alternatives are insufficient;
- customer-revenue linkage when applicable;
- fallback;
- exit/migration plan.

Enterprise and managed offerings may charge later. Founder-zero-runtime-burn does not mean user-free-forever.

## 10. Privacy and surveillance

Precise personal location, movement history, home/work inference, voice, private enterprise geometry, and private operational data are sensitive.

Defaults:

- local storage where practical;
- minimum necessary retention;
- no background location unless a product requirement is explicit and permissioned;
- no named-person tracking of non-consenting people;
- no facial recognition product feature;
- no covert surveillance workflow;
- no precise private location in ordinary telemetry;
- no public share URL that leaks precise private state;
- no automatic promotion of private observations into public world truth.

Enterprise workforce location features require explicit organizational authority, purpose limitation, role controls, retention, and jurisdiction review.

## 11. Voice authority

Voice is an input/control surface, not automatic authorization.

Speech must preserve separable provenance for raw/ephemeral audio policy, transcript, normalization, entity binding, semantic class, final typed intent, and authorization.

Push-to-talk is the reliability baseline. Always-listening, wake word, hands-free full duplex, and background capture are separate gated capabilities.

User interruption and cancellation are first-class runtime semantics.

## 12. Memory authority

Memory candidates are not durable memory.

Any persistent personal or enterprise memory must declare:

- scope;
- evidence;
- source;
- sensitivity;
- validity/observation time;
- retention/expiry;
- correction/supersession semantics;
- deletion/export behavior.

Users and authorized organizations must be able to inspect, correct, export, and delete Mckani-owned durable memory within supported policies.

## 13. Mobility authority

Dispatch, ETA, batching, route optimization, pricing, incentives, vehicle assignment, and fleet actions must be typed and auditable.

A probabilistic model may rank feasible assignments but cannot override hard constraints such as:

- vehicle capacity;
- required skills;
- safety restrictions;
- time-window hard bounds;
- tenant/policy isolation;
- driver/courier work limits;
- jurisdiction-specific restrictions.

Compensation, pricing, or incentive changes must not occur as hidden side effects of a routing model.

## 14. Enterprise isolation

Tenant isolation and authorization are R3 trust boundaries.

Cross-tenant retrieval, analytics, caching, embeddings, model context, logs, alerts, or map layers must fail closed.

## 15. Accessibility and non-AI fallback

Every consequential map capability needs a usable textual/list fallback where practical. Core search, saved places, permissions, and critical controls must not depend only on 3D, voice, color, animation, or generative AI.

## 16. Claims

Do not claim:

- production readiness;
- traffic accuracy;
- ETA superiority;
- geocoding accuracy;
- voice accuracy;
- model superiority;
- cost savings;
- privacy guarantees;
- scalability;
- offline coverage;
- enterprise compliance;
- benchmark wins;

until reproducible Mckani evidence exists for the exact claim and target population/hardware/region.
