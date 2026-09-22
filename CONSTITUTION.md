# Mckani Constitution

These principles constrain product and architecture. Changing one requires an explicit architecture/governance decision rather than an incidental implementation diff.

## Principle I — The world model is canonical; the map is a projection

Mckani does not define truth by what a renderer happens to display.

The canonical system models identity, geometry assertions, time, state, relationships, observations, evidence, confidence, provenance, permissions, rights, and actions. MapLibre, Cesium, lists, dashboards, AR, and agent responses are projections.

## Principle II — Space and time are inseparable

Real-world state changes.

Every material assertion must support enough temporal semantics to answer:

- what is believed true now;
- when it was valid in the world;
- when Mckani observed or learned it;
- what it superseded or contradicted;
- how fresh it is;
- whether it has expired.

Latest-write-wins must not erase historical meaning.

## Principle III — Evidence travels with claims

A material world claim must retain source identity and transformation lineage.

Scores, model confidence, popularity, search rank, provider rank, and visual prominence are evidence signals, not authority.

## Principle IV — Observed, inferred, predicted, and simulated are different states

Mckani must never silently present a prediction as observation or a scenario as reality.

Derived layers, forecasts, AI summaries, and simulations remain explicitly typed.

## Principle V — Deterministic computation owns correctness-sensitive spatial work

Models do not calculate authoritative geometry, permissions, hard routing constraints, ledger integrity, tenant isolation, or state transitions by free-form reasoning.

Models use typed tools.

## Principle VI — AI escalates only as far as necessary

The preferred path is:

~~~text
deterministic rules and indexes
-> small calibrated local decision provider
-> semantic judge or reranker
-> local generative model
-> optional remote provider
~~~

A more expensive or less private model is not used merely because it exists.

## Principle VII — Local-first is a product property

The individual product must retain a useful path with local state, local memory, local decision capability where hardware permits, and open/provider-neutral world data.

Cloud connectivity may enrich the world. It does not silently become ownership of the user's private world.

## Principle VIII — Memory is governed, not ambient

Mckani may learn from explicit use, but durable memory is scoped, inspectable, correctable, exportable, and deletable.

Location history is not automatically memory.

## Principle IX — Voice is interruptible and accountable

Voice must preserve user authority. Command, context, aside, correction, cancellation, and approval are distinct concepts.

A voice assistant that cannot be interrupted is not an acceptable control plane.

## Principle X — Providers are adapters

Mckani owns stable semantic contracts around renderers, basemaps, geocoding, routing, traffic, places, imagery, weather, models, speech, notifications, and external actions.

No commercial provider is required for core correctness.

## Principle XI — Personal, mobility, builder, and enterprise surfaces share primitives

Mckani does not build four unrelated products.

Identity, world state, evidence, memory, decision contracts, capability policy, provider contracts, and event semantics are shared. Surface-specific behavior is layered above them.

## Principle XII — Mobility optimizes systems under explicit constraints

Routing and dispatch optimize declared objectives subject to safety, capacity, time, policy, fairness, privacy, and worker constraints.

Short-term marketplace gain does not silently authorize a longer-term policy change.

## Principle XIII — Privacy and safety are architectural

Sensitive location cannot be made safe by a privacy policy added after storage design.

Data minimization, locality, coarse aggregation, retention, tenant isolation, egress policy, audit, and user control are part of the system model.

Mckani is not designed as a named-person surveillance or facial-recognition platform.

## Principle XIV — Open world data needs explicit rights

Source-code permission and data rights are separate.

Every imported map database, derived dataset, model weight, imagery product, font, style, icon set, and service response remains governed by its own license/terms and attribution obligations.

## Principle XV — Complexity must be progressive

Individuals should not need to understand GIS, models, providers, or routing engines to use Mckani.

Enterprise experts and developers may access depth, but ordinary users receive intent-driven experiences.

## Principle XVI — Evidence before completion

SpecGrain defines bounded work. Diffcipline defines the proof-before-done floor.

No agent, maintainer, benchmark, or CI label can substitute for exact evidence against the exact revision.
