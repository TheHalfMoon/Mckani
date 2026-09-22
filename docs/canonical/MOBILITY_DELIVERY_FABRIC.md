# Mobility and Delivery Fabric

## 1. Product objective

Make Mckani a serious foundation for:

- ride-hailing;
- food delivery;
- grocery;
- pharmacy;
- parcel/courier;
- last mile;
- trucking;
- field service;
- employee/school transport;
- fleet operations;
- future autonomous/robotic delivery adapters.

A route API alone is insufficient.

Mckani Mobility owns contracts across routing, ETA, matching, dispatch, batching, marketplace state, pickup/drop-off intelligence, driver/courier UX, fleet optimization, and evidence.

## 2. Core domain

~~~text
MobilityActor
Vehicle
DriverCourier
RiderCustomer
Merchant
Order
Shipment
Visit
Stop
Pickup
Dropoff
ServiceArea
Shift
DispatchCandidate
Assignment
RoutePlan
JourneyTimeline
ETAEstimate
ProofOfPickup
ProofOfDelivery
Fleet
MarketplaceCell
~~~

Every entity is tenant-scoped where applicable.

## 3. Journey timeline

Delivery ETA is not drive time.

Candidate stages:

~~~text
order received
-> merchant acceptance
-> preparation
-> dispatch latency
-> courier to pickup
-> parking/entrance
-> pickup wait/handoff
-> linehaul to destination
-> parking/gate/building access
-> final handoff
~~~

Each stage may have an estimate, uncertainty and observed outcome.

This enables root-cause analysis instead of one opaque ETA.

## 4. ETA architecture

~~~text
network route time
+ live/historical traffic correction
+ temporal/local correction
+ merchant preparation model
+ pickup friction
+ drop-off/building friction
+ vehicle mode
+ operational state
-> calibrated arrival interval
~~~

Return ranges/confidence where qualified rather than false precision.

Separate:

- route duration estimate;
- pickup ETA;
- ready ETA;
- drop-off ETA;
- complete-order ETA.

## 5. Dispatch

Dispatch is an online decision problem.

Pipeline:

~~~text
new/changed demand
-> hard candidate feasibility
-> travel/ETA matrix
-> operational constraints
-> candidate scoring/optimization
-> marketplace-balance signals
-> policy
-> dispatch proposal
-> assignment
-> continuous re-evaluation
~~~

Nearest-driver is not the universal objective.

## 6. Hard feasibility

Examples:

- tenant;
- service area;
- vehicle capacity;
- vehicle type/restrictions;
- required skill/certification;
- cold-chain/hazard policy;
- shift/work constraints;
- pickup/delivery time windows;
- order compatibility;
- access restriction;
- battery/fuel reserve policy;
- jurisdiction restrictions.

A model cannot override hard infeasibility.

## 7. Dispatch objective

A configurable objective may consider:

- pickup ETA;
- delivery ETA;
- idle time;
- merchant ready probability;
- customer SLA risk;
- route overlap;
- future supply balance;
- workload balance;
- operating cost;
- empty distance;
- vehicle utilization;
- declared fairness/worker constraints.

Weights/policy are versioned and auditable.

## 8. Routing and optimization

Candidate foundation:

- Valhalla or another qualified local/open router for network paths, matrices, time-dependent cost, isochrones and map matching;
- VROOM for VRP/VRPTW/pickup-delivery/multi-depot heterogeneous fleet optimization where fit;
- OR-Tools as a reference/optional solver for richer constraint formulations;
- custom rolling/online dispatch logic for high-frequency marketplace assignment.

Do not force batch VRP tooling to solve a real-time marketplace problem it was not designed for.

## 9. Rolling re-optimization

When orders, traffic, closures, cancellations, vehicle status, or merchant readiness change:

- preserve completed/committed work;
- compute safe insertion/reassignment candidates;
- bound churn;
- respect customer promises;
- respect driver/courier constraints;
- explain material route/assignment changes.

## 10. Batching

Batch only compatible work.

Optimization:

~~~text
maximize useful completed work and utilization
subject to:
  freshness/perishability
  SLA
  detour bounds
  capacity
  preparation timing
  access
  worker limits
  customer experience
~~~

Batching is not "maximum orders per driver".

## 11. Pickup/drop-off and curb intelligence

Entity arrival model may include:

- public entrance;
- vehicle entrance;
- courier entrance;
- loading dock;
- curb side;
- legal stop zone;
- pickup point;
- drop-off point;
- parking;
- mall/campus internal handoff;
- gate/building instructions.

Successful verified journeys can produce candidate arrival knowledge with freshness and corroboration.

Do not expose private customer instructions as public world data.

## 12. Marketplace cells

H3-derived cells support aggregate marketplace features:

- demand now/forecast;
- available supply;
- busy supply;
- average pickup delay;
- delivery delay;
- traffic;
- merchant density;
- acceptance/cancellation aggregate;
- weather/event context.

H3 is an aggregation feature, not exact pickup geometry.

## 13. Driver/courier voice

Voice tasks include:

- accept/decline where product policy permits;
- next stop;
- reroute explanation;
- parking/entrance query;
- report closure;
- structured customer update;
- pause new offers;
- incident/help workflow.

Driving mode applies stricter interaction/safety rules.

## 14. Merchant intelligence

Merchant/private metrics:

- preparation accuracy;
- courier wait;
- pickup friction;
- peak delay;
- cancellation/exception reasons;
- handoff reliability;
- delivery-zone performance;
- demand forecast.

A merchant's private operational data remains tenant/workspace governed.

## 15. Customer experience

Expose status truthfully:

- assigned/unassigned;
- preparing;
- courier en route;
- pickup wait;
- traffic delay;
- access delay;
- estimated interval;
- evidence/freshness appropriate to the surface.

Do not expose sensitive driver history or internal scores.

## 16. Vehicle profiles

Candidate modes:

- bicycle;
- motorcycle;
- car;
- van;
- truck;
- refrigerated;
- EV;
- accessible vehicle;
- specialized field-service vehicle.

Profiles may include:

- capacity dimensions;
- height/weight/axle restrictions;
- energy/battery;
- charging;
- skills;
- start/end/shift;
- service territory;
- safety constraints.

## 17. Fleet optimization

Support:

- multi-depot;
- heterogeneous fleet;
- time windows;
- capacities;
- breaks;
- pickup and delivery precedence;
- service durations;
- skills;
- priorities;
- open routes;
- route-duration limits;
- fairness/workload policies.

Solver input and result are versioned for reproducibility.

## 18. Pricing and incentives

Pricing/incentive capability is optional and separately governed.

Rules:

- route/dispatch models cannot silently mutate pay/fare;
- policy version is explicit;
- jurisdiction/legal review is external gate;
- user/driver-facing disclosures follow product/jurisdiction requirements;
- simulations are not automatically applied;
- experimentation has safety/ethics/rollback constraints.

## 19. Anti-abuse and data integrity

Plan defenses for:

- impossible GPS jumps;
- stale device state;
- duplicate orders/events;
- replayed proof;
- bot/fake demand;
- provider spoofing;
- map/data poisoning.

Detection must avoid turning the platform into invasive worker surveillance.

## 20. Proof of pickup/delivery

Proof is policy-specific and may include:

- explicit app confirmation;
- scan;
- geofence plausibility;
- photo with retention controls;
- recipient code/signature where permitted.

Proof data is sensitive and retention-bounded.

## 21. Real-time service architecture

Consumer-local-first does not mean a multi-party marketplace has no shared backend.

Mobility control plane needs shared durable state for:

- orders;
- supply;
- assignments;
- trips;
- driver/courier presence;
- merchant state;
- dispatch;
- pricing policy;
- events.

Planning default is a modular server architecture with Postgres/PostGIS and durable event/outbox semantics, evolving to dedicated streaming/services only when measured scale requires it.

Edge/client still owns:

- rendering;
- local cache;
- navigation assistance;
- voice;
- selected privacy-sensitive memory;
- offline/degraded behavior.

## 22. Builder API

High-level:

~~~text
orders.create(...)
dispatch(order)
track(journey)
~~~

Lower-level:

~~~text
route.matrix(...)
eta.predict(...)
dispatch.candidates(...)
optimization.solve(...)
marketplace.cells(...)
arrival.resolve(...)
~~~

High-level APIs compose lower-level typed contracts rather than hiding provider-specific blobs.

## 23. Mobility benchmarks

Measure:

- route success/quality;
- ETA MAE/quantile calibration by trip length/region/time;
- dispatch latency;
- assignment acceptance/completion;
- pickup wait;
- merchant wait;
- on-time delivery;
- empty distance;
- batch detour;
- solver time/optimality gap where knowable;
- reroute stability;
- offline/degraded behavior;
- battery/network use;
- fairness/constraint violation rate;
- incident recovery.

No benchmark metric overrides safety/privacy/hard constraints.
