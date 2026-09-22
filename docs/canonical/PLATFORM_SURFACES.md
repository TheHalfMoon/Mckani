# Product Surfaces

## 1. One core, four surfaces

Mckani must resist the common failure mode of building a consumer app, then attaching a developer API, then attaching an enterprise dashboard, then separately building delivery infrastructure.

The product surfaces share World Kernel, provider contracts, evidence, memory, capability policy, and event semantics.

## 2. Personal

### Default experience

The first screen is a map, not an admin dashboard.

Primary controls:

- Ask Anywhere;
- Go;
- Explore;
- Pulse;
- Saved;
- Memory;
- optional voice button.

Complexity is progressive.

### Core personal journeys

- find a place by natural constraints;
- compare options;
- route with explicit objectives;
- decide when to leave;
- see traffic/weather/transit/events/parking/activity;
- remember a place or preference;
- ask what changed in an area;
- share a place/route/area without leaking unrelated private context;
- plan a group meetup;
- create a spatial alert;
- inspect a destination entrance/parking/arrival context;
- ask through voice while moving;
- use list/text fallback when map interaction is inaccessible.

### Personal fit vs public reputation

Keep separate:

- public rating/reputation;
- source-specific ratings;
- verified-visit evidence;
- personal predicted fit.

Never rewrite "4.2 public rating" into "4.8 for you" without distinguishing the semantics.

## 3. Mobility

Surfaces:

- rider/customer;
- driver/courier;
- merchant;
- dispatcher/operations;
- fleet manager;
- developer/admin.

The driver/courier surface prioritizes:

- glanceable navigation;
- voice;
- interruption;
- next action;
- pickup/drop-off truth;
- parking/entrance;
- safety;
- offline degradation;
- low interaction burden.

The operations surface prioritizes:

- supply/demand;
- SLA risk;
- live trips/orders;
- exception queues;
- dispatch reasons;
- fleet health;
- route/ETA confidence;
- incident impact;
- merchant delays;
- evidence and replay.

## 4. Builder

Builder exposes composable contracts.

Candidate SDK families:

~~~text
world
geo
places
routes
pulse
memory
decision
agents
voice
mobility
layers
alerts
scenarios
~~~

Developer ergonomics:

- simple high-level APIs;
- low-level deterministic primitives;
- provider-neutral objects;
- test/fake providers;
- local development path;
- structured machine-readable errors;
- idempotency for effects;
- explicit rate/cost metadata for provider-backed calls;
- replay/evidence hooks.

MCP is a tool/context protocol surface, not an authorization bypass.

## 5. Enterprise

Enterprise Studio:

~~~text
Workspace
├── Map
├── Data Catalog
├── Layers
├── World Entities
├── Analysis
├── Formulas
├── Agents
├── Workflows
├── Alerts
├── Scenarios
├── Dashboards
├── Decisions
├── Evidence
└── Administration
~~~

Enterprise features include:

- private layers/data;
- data connectors;
- digital twins;
- spatial analytics;
- collaboration;
- approvals;
- audit;
- organization memory;
- role/policy controls;
- optional warehouse execution;
- self-host/BYOC;
- SSO/provisioning after qualification.

## 6. Shared interaction contract

A query should produce structured outcomes, not only prose.

Example result envelope:

~~~text
SpatialResult
├── intent
├── constraints
├── entities[]
├── geometries[]
├── routes[]
├── derived_layers[]
├── scores[]
├── explanations[]
├── evidence[]
├── freshness
├── limitations[]
└── suggested_actions[]
~~~

The same result can render as map, list, voice response, enterprise table, or agent tool response.

## 7. Map/list parity

The map and list are views of one result contract.

They share:

- eligibility;
- filtering;
- ranking intent;
- pagination/window semantics;
- evidence;
- rights;
- freshness.

Map clustering is presentation only and cannot alter semantic ranking.

## 8. Progressive disclosure

Individuals should not see:

- provider IDs;
- SRIDs;
- model names;
- warehouse adapters;
- evidence digests;
- routing graph settings;

unless they explicitly inspect advanced details.

Developers/analysts can.

## 9. Localization

Arabic and English are first-class from the founding implementation.

Requirements:

- RTL-safe map controls and panels;
- bidi-safe addresses;
- Arabic/Western numerals;
- transliteration aliases;
- Arabic-English code switching in search/voice benchmarks;
- locale-aware turn instructions;
- no assumption that one transliteration is canonical.

Additional languages are data/benchmark additions, not architecture changes.

## 10. Accessibility

Consequential capabilities have non-map and non-voice paths.

Requirements include:

- keyboard navigation;
- screen-reader text alternatives;
- high-contrast/reduced-motion behavior;
- large-target mobile interaction;
- textual route instructions;
- accessible layer/list representation;
- no meaning conveyed only by color.

## 11. Account model

Personal core should support accountless first use.

Accounts become necessary only for capabilities that inherently require identity/synchronization, such as:

- cross-device sync;
- collaboration;
- paid managed services;
- enterprise membership;
- marketplace publication;
- shared group state beyond anonymous/local modes.

Sign-in is not the first product wall.
