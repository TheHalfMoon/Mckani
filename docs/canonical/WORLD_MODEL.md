# Canonical World Model

## 1. Objective

Mckani needs one representation that can describe a coffee shop, road segment, hospital, warehouse, parking entrance, delivery zone, weather cell, aircraft, private factory asset, route, event, user annotation, and future scenario without collapsing their different authority or privacy semantics.

The World Model therefore separates stable identity from assertions and observations.

## 2. Core types

~~~text
WorldEntity
├── mckani_id
├── entity_type
├── names/aliases
├── external_ids[]
├── geometry_assertions[]
├── state_assertions[]
├── relations[]
├── rights_refs[]
├── sensitivity
└── lifecycle

WorldObservation
├── observation_id
├── subject
├── observed_at
├── valid_time
├── source
├── payload
├── geometry
├── confidence?
├── quality
├── provenance
├── sensitivity
└── rights_ref

WorldEvent
├── event_id
├── event_type
├── participants[]
├── geometry
├── valid_interval
├── before_refs[]
├── after_refs[]
├── evidence[]
└── provenance

WorldPrediction
├── target
├── horizon
├── produced_at
├── model/rule identity
├── distribution/range
├── confidence/calibration refs
├── features/evidence refs
└── expiry

WorldScenario
├── scenario_id
├── baseline_revision
├── branch
├── hypothetical_changes[]
├── simulation_method
└── outputs[]
~~~

## 3. Identity

Mckani owns Mckani IDs.

External IDs may include:

- Overture GERS;
- OSM identifiers;
- provider place IDs;
- official/national address IDs;
- enterprise asset IDs;
- merchant IDs;
- mobility platform IDs.

Rules:

- distance alone cannot merge entities;
- normalized name alone cannot merge entities;
- external source disappearance does not delete Mckani identity;
- merge/unmerge is auditable;
- identity conflicts remain explicit;
- private enterprise identities are never automatically published to the public world;
- GERS is a valuable open stable reference, not a replacement for private/internal identities.

## 4. Entity resolution

Conflation pipeline:

~~~text
external observation
-> candidate generation
-> deterministic identifier/name/spatial/category evidence
-> optional semantic match score
-> conflict detection
-> policy threshold
-> auto-link only for bounded low-risk cases
   or require review
-> canonical link
-> provenance
~~~

High-impact facility, legal boundary, pickup/drop-off, enterprise asset, or address merges require stronger evidence.

## 5. Geometry assertions

A WorldEntity may have multiple geometry assertions.

Fields:

- geometry;
- SRID/CRS;
- geometry role;
- precision class;
- source;
- observed_at;
- valid interval;
- verification state;
- evidence;
- supersedes;
- rights.

Candidate geometry roles:

- centroid;
- parcel;
- footprint;
- entrance;
- accessible entrance;
- vehicle entrance;
- courier entrance;
- loading dock;
- pickup zone;
- drop-off zone;
- parking;
- service area;
- route;
- lane/curb segment;
- approximate area.

Canonical public longitude/latitude exchange uses WGS84 unless a contract explicitly states otherwise.

Reject invalid coordinates, NaN/Infinity, wrong ranges, and undeclared CRS.

## 6. Precision

Minimum precision classes:

~~~text
VERIFIED_POINT
VERIFIED_ENTRANCE
VERIFIED_FOOTPRINT
VERIFIED_PARCEL
PROVIDER_ATTESTED_POINT
SENSOR_OBSERVED
APPROXIMATE_POINT
APPROXIMATE_AREA
PRIVATE_HIDDEN
UNKNOWN
~~~

UI and API must not present an approximate area as an exact entrance.

## 7. Time

Mckani uses bi-temporal semantics:

- **valid time** — when an assertion/event is true in the world;
- **knowledge time** — when Mckani learned or committed it.

Optional event times include produced_at, received_at, predicted_for, expires_at, and retracted_at.

Queries support:

- current world;
- world as valid at time T;
- what Mckani knew at time T;
- change timeline;
- diff between times;
- prediction available at a past time;
- scenario branch vs baseline.

## 8. Truth state

Every material derived item carries one of:

~~~text
OBSERVED
ATTESTED
INFERRED
PREDICTED
SIMULATED
USER_PRIVATE
ORGANIZATION_PRIVATE
UNKNOWN
~~~

Verification/authority is separate from this origin class.

An observed sensor reading can still be low quality. An inferred result can be high confidence but remains inferred.

## 9. Evidence

EvidenceRef binds:

- source identity;
- source revision/version;
- source location/span/object;
- digest when practical;
- acquisition time;
- transformation lineage;
- parser/model identity;
- access scope;
- taint/trust classification;
- rights/attribution reference.

A summary never replaces its underlying evidence.

## 10. Relations

Typed relation examples:

~~~text
LOCATED_IN
HAS_ENTRANCE
HAS_PARKING
CONNECTED_TO
SERVES
NEAR
PART_OF
SAME_AS_CANDIDATE
CANONICAL_LINK
SUPPORTS
CONTRADICTS
SUPERSEDES
DERIVED_FROM
CAUSED_BY
AFFECTS
ROUTE_USES
PICKUP_AT
DELIVERY_TO
OPERATED_BY
MEMBER_OF
OBSERVED_BY
~~~

Inferred relations record why they exist.

## 11. Rights

DataRightsRef tracks:

- source;
- license/terms identifier;
- attribution requirement;
- redistribution permission;
- derivative/share-alike considerations;
- caching/retention constraints;
- geographic/usage restrictions;
- commercial-use status where known;
- review date.

Rights metadata is part of data lineage, not a legal note disconnected from objects.

## 12. Sensitivity

Initial classes:

- PUBLIC;
- USER_PRIVATE;
- HOUSEHOLD_SHARED;
- TEAM_PRIVATE;
- ORGANIZATION_PRIVATE;
- RESTRICTED_OPERATIONAL;
- SECRET_REFERENCE_ONLY.

Location history and precise private origins require explicit sensitivity treatment.

## 13. World state

Current state is a projection over assertions/events, not a mutable source blob.

State resolution considers:

- authority;
- validity interval;
- source freshness;
- supersession;
- contradictions;
- policy;
- tenant/scope.

When conflict cannot be safely resolved, expose conflict/unknown instead of guessing.

## 14. Scenario branches

Scenarios fork a baseline revision.

~~~text
main-world
  |
  +-- scenario/road-closure
  +-- scenario/new-store
  +-- scenario/warehouse-move
  +-- scenario/event-egress
~~~

A scenario cannot write observed truth. Applying a scenario to operational state requires an explicit separate action/approval path.

## 15. Personal and organizational overlays

The public world and private worlds are layered.

A personal statement such as "I dislike this route" is not public route truth.

An organization statement such as "Gate B is our approved loading entrance" may be authoritative inside that tenant but not globally public.

The World Kernel therefore resolves context by principal and scope rather than maintaining one universal mutable record.

## 16. World diffs

A first-class WorldDiff can describe:

- entity appeared/disappeared;
- geometry changed;
- place status changed;
- route connectivity changed;
- business hours changed;
- rating/reputation changed;
- traffic pattern changed;
- private asset state changed;
- evidence contradiction;
- prediction change.

WorldDiff powers "what changed here?" and supports audit, alerts, and memory.

## 17. World object acceptance contract

No world object enters a canonical store unless:

- schema validates;
- identity/scope is known;
- geometry is valid or explicitly absent;
- source/provenance is known;
- time semantics are declared;
- sensitivity is classified;
- rights reference is present where external data requires it;
- authority/verification state is explicit;
- unsupported fields do not silently expand authority.
