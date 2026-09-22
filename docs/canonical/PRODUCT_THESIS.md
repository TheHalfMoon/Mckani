# Product Thesis

## Category

Mckani is a **Spatial Operating System**.

It combines consumer mapping, local AI, spatial memory, live-world intelligence, mobility infrastructure, developer primitives, and enterprise GIS/operations around one canonical World Kernel.

The category is deliberately broader than "AI maps" because the long-term product is not only a map that answers questions. It is an interface through which people, organizations, applications, and AI agents understand and act on the physical world.

## North star

> See anything. Ask anything. Understand anywhere. Navigate intelligently. Remember what matters. Simulate safely. Act through governed tools.

Internal positioning:

> The intelligence layer between software and the physical world.

## User groups

### Individuals

Jobs:

- discover places and experiences;
- navigate by car, transit, walking, cycling, and multimodal trips;
- know traffic, weather, events, parking, crowd/activity and arrival context;
- ask natural-language spatial questions;
- use voice safely while moving;
- remember personal places, trips, preferences, and explicit observations;
- compare areas/routes/places with explainable criteria;
- coordinate with friends or family;
- receive alerts when spatial conditions become true;
- understand past change and future predictions;
- inspect privacy and memory.

Experience goal: a simple map first. Intelligence appears when useful.

### Mobility and delivery companies

Jobs:

- geocode and resolve pickup/drop-off;
- route and reroute;
- predict ETA with calibrated uncertainty;
- match supply and demand;
- dispatch drivers/couriers;
- batch compatible deliveries;
- optimize fleets and routes;
- model merchant preparation and handoff time;
- learn entrances, curbs, parking, loading docks and building access;
- provide driver/courier voice interaction;
- operate real-time control rooms;
- inspect reasons for late or failed journeys;
- integrate their own traffic, fleet, pricing, order, sensor and policy data.

Experience goal: one mobility fabric instead of unrelated mapping, optimization, tracking, ETA, dispatch, and geofencing vendors.

### Builders and startups

Jobs:

- embed map/search/routing/places/pulse;
- use typed spatial APIs instead of prompting an LLM for geometry;
- build agents through MCP/tool contracts;
- create custom layers, formulas, alerts and workflows;
- run open/local infrastructure where possible;
- bring their own providers;
- preserve provider exit paths.

Experience goal: easy defaults with composable lower-level primitives.

### Enterprises

Jobs:

- map internal facilities, assets, operations, customers, service territories and sensors;
- join private data with public world context;
- build digital twins;
- ask natural-language spatial questions while preserving governance;
- perform site selection, catchment, accessibility, supply/demand and operational analysis;
- create alerts and workflows;
- collaborate on spatial decisions;
- preserve decision/evidence history;
- deploy in customer-owned environments.

Experience goal: Spatial Intelligence OS rather than a larger GIS dashboard.

## Signature product primitives

### Ask Anywhere

Natural language is compiled into typed spatial intent and constraints.

Example:

~~~text
Find quiet specialty coffee within 15 minutes,
open when I arrive,
easy parking,
not currently busy,
good for two hours of work.
~~~

The result is a map/list of candidates with evidence and explicit constraints, not an unsupported paragraph.

### Ask This

The user selects a place, building, road, polygon, route, live object, event, or private enterprise entity and asks about that object.

Spatial context resolves pronouns such as "this", "here", "that building", and "the road on the right" from visible/selected state rather than free-form guessing.

### World Pulse

A unified time-varying layer for traffic, transit, incidents, events, weather, parking, place activity, fleet/sensor state, and predictions.

### Spatial Memory

Personal or organizational memory attached to the physical world with temporal provenance.

Examples:

- this entrance worked last time;
- avoid this road for me;
- this merchant normally runs ten minutes late on Friday evenings;
- our team rejected this site last year for these recorded reasons.

### World Formula

Users and organizations can define transparent scoring formulas.

~~~text
AreaScore =
  commute * 0.40
+ affordability * 0.30
+ walkability * 0.20
+ services * 0.10
~~~

AI may propose weights or dimensions, but the formula remains inspectable and editable.

### Query-to-Layer

A question can produce a reusable derived layer whose definition, sources, timestamp, confidence, and limitations are inspectable.

### Scenario Branches

"What if" changes are isolated from observed truth.

A scenario may close a road, add a store, change a fleet, add housing, adjust demand, or model an event without mutating the canonical observed world.

### World Triggers

~~~text
WHEN spatial/temporal/data condition becomes true
IF policy allows
THEN notify or propose an action
~~~

### Evidence Lens

Any material result can reveal:

- source;
- freshness;
- observed/inferred/predicted/simulated state;
- confidence when applicable;
- formula or rule;
- provider;
- limitations;
- rights/attribution where relevant.

## Competitive direction

Mckani does not win by recreating every proprietary dataset on day one.

It is designed around a different compound advantage:

~~~text
World Identity Graph
+ Temporal World Model
+ Local Spatial Memory
+ World Pulse
+ Decision Fabric
+ Voice/Multimodal Context
+ Governed Spatial Agents
+ Mobility Fabric
+ Personal World
+ Enterprise Private World
+ Builder Ecosystem
~~~

Each component reinforces the others.

## Explicit non-goals

Mckani is not:

- a single-vendor wrapper;
- a chat sidebar over a map;
- a vector database presented as world truth;
- a general-purpose named-person tracking platform;
- a facial-recognition product;
- a military/spy product derived from God's Eye View semantics;
- a requirement that users run Docker or an LLM server;
- a requirement that startups use a Mckani-hosted paid API;
- a promise that open data alone can reproduce proprietary live traffic or global live busyness on launch;
- a reason to copy donor architecture without exact qualification.

## Product success

Long-term product success is measured separately for each surface.

Personal:
- usefulness and task completion;
- route/search quality;
- privacy trust;
- repeat voluntary use;
- memory benefit without creepiness;
- accessibility;
- battery and performance.

Mobility:
- calibrated ETA;
- on-time rate;
- assignment/route efficiency;
- courier/driver wait;
- pickup/drop-off success;
- operational reliability;
- cost with declared constraints.

Builder:
- time to first useful spatial operation;
- provider portability;
- local/self-host success;
- SDK/API reliability;
- integration depth.

Enterprise:
- decision cycle time;
- data lineage and reproducibility;
- governed adoption beyond GIS specialists;
- deployment/control fit;
- tenant isolation and audit;
- operational outcomes supported by evidence.

No metric permits weakening privacy, safety, rights, or truth semantics.
