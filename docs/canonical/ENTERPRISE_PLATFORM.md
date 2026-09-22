# Enterprise Platform

## 1. Objective

Mckani Enterprise turns the World Kernel into a governed private spatial operating environment.

The enterprise product must support non-GIS users without weakening the controls required by GIS, security, data, operations, legal and platform teams.

## 2. Organization model

~~~text
Organization
├── identities
├── tenants/business units
├── workspaces
├── teams
├── roles/policies
├── data catalog
├── private world
├── connectors
├── agents
├── workflows
├── alerts
├── dashboards
├── decisions
└── audit/evidence
~~~

## 3. Private World

Enterprise WorldEntity may represent:

- facility;
- warehouse;
- store;
- campus;
- asset;
- sensor;
- vehicle;
- service territory;
- customer/site;
- internal road;
- utility;
- project;
- work order;
- private POI;
- field observation.

Private entity IDs and geometry stay organization-scoped unless explicitly published.

## 4. Digital twin

A digital twin is a governed projection of world/private state, not a magical real-time copy.

Every twin declares:

- entity coverage;
- data sources;
- refresh;
- missingness;
- authority;
- latency;
- simulated vs observed fields;
- retention;
- rights;
- owners.

## 5. Connectors

Connector families:

- Postgres/PostGIS;
- object storage;
- files/GeoJSON/GeoParquet/CSV;
- warehouses;
- IoT/event systems;
- CRM/ERP;
- fleet/order systems;
- approved external APIs;
- document repositories.

Connector output is untrusted input until validated.

Connector authentication never grants world-write authority beyond its scoped policy.

## 6. Data catalog

Every dataset/layer records:

- owner;
- schema/version;
- source;
- refresh;
- region;
- sensitivity;
- rights;
- retention;
- quality/missingness;
- lineage;
- permitted uses;
- serving/index status.

## 7. Authorization

Plan for both RBAC and resource/attribute-aware policy.

Capability grants bind:

- principal;
- organization/tenant;
- action;
- resource;
- data class;
- runtime;
- constraints;
- expiry where applicable.

Unknown policy fails closed.

## 8. Enterprise identity

Later qualified adapters may include:

- OIDC;
- SAML;
- SCIM;
- MFA/device policy;
- service identities.

No identity vendor becomes semantic authority.

## 9. Tenant isolation

R3 boundary.

Isolation applies to:

- database rows/schemas as designed;
- object storage;
- caches;
- search indexes;
- vector indexes;
- model context;
- prompt/context bundles;
- observability;
- exports;
- alerts;
- backups;
- analytics.

Cross-tenant "aggregate" data is not permitted merely because identities were removed. Re-identification risk is assessed.

## 10. Spatial analytics

Support:

- proximity;
- catchment;
- service/accessibility gaps;
- site selection;
- route/travel burden;
- spatial joins;
- density;
- H3 aggregation;
- territory design;
- flow;
- change detection;
- private/public layer comparison;
- scenario analysis.

Each analytical artifact retains input versions and definitions.

## 11. Natural-language enterprise analysis

Question:

"Which stores are likely to miss service targets this week and why?"

Pipeline:

~~~text
intent
-> authorize datasets
-> compile typed plan
-> deterministic/analytical tools
-> optional model decision/synthesis
-> evidence-linked result
-> map/table/chart
~~~

The model never gets ambient warehouse access.

## 12. Enterprise agents

Agents operate through the Spatial Capability Kernel.

Examples:

- SiteSelectionAgent;
- FleetOpsAgent;
- FieldServiceAgent;
- RetailExpansionAgent;
- FacilityRiskAgent;
- LogisticsAgent.

Agent identity, tools, data scope, budgets, approvals and audit are explicit.

## 13. Workflows

Workflow steps may:

- query;
- analyze;
- wait for condition;
- request approval;
- create derived layer;
- notify;
- call external approved tool;
- create work item;
- propose operational action.

Side effects have idempotency and reconciliation semantics.

## 14. Collaboration

Spatial collaboration:

- comments;
- mentions;
- annotations;
- assignments;
- review;
- voting where appropriate;
- approvals;
- shared views;
- versioned layers;
- decisions.

Collaboration state is not embedded irreversibly into map style JSON.

## 15. Decision record

Material enterprise decision:

~~~text
DecisionRecord
├── question
├── owner
├── date
├── alternatives
├── data snapshot refs
├── assumptions
├── formulas/models
├── evidence
├── approvals
├── decision
└── later outcome links
~~~

This enables "why did we decide this?" years later.

## 16. Warehouse-native option

Mckani may push appropriate analytics to the customer's warehouse rather than copying all data.

Rules:

- execution plan is explicit;
- permissions remain customer-controlled;
- only necessary result/context leaves the system;
- SQL/tool plan is reviewable where practical;
- no provider-specific warehouse becomes mandatory.

## 17. Deployment

Supported targets to qualify:

- self-hosted single node for smaller teams;
- Kubernetes/container platform for larger deployments only when justified;
- private cloud;
- BYOC;
- air-gapped/restricted-network subsets where data/model packs permit;
- future managed Mckani.

Personal app architecture does not require enterprise orchestration.

## 18. Data residency and egress

Organization policy can constrain:

- regions;
- external AI;
- map providers;
- geocoders;
- routing providers;
- telemetry;
- crash reports;
- connectors;
- model downloads;
- exports.

No silent external-provider fallback.

## 19. Observability

Observe:

- request health;
- provider health;
- freshness;
- connector lag;
- index builds;
- route/dispatch latency;
- job failures;
- model runtime health;
- quota/cost;
- policy denies;
- sync conflicts.

Avoid logging sensitive geometry/payloads by default.

## 20. Reliability

Required production design includes:

- idempotency;
- transactional outbox;
- bounded retries/backoff;
- dead-letter/review;
- reconciliation;
- backups;
- restore drills;
- schema migration;
- rollback;
- disaster recovery targets defined by deployment tier;
- provider circuit breaking;
- graceful degradation.

## 21. Admin safety

Administrative capabilities are separate from ordinary MCP/agent tools.

Sensitive actions such as:

- tenant export/delete;
- policy change;
- provider secret change;
- connector write authorization;
- model egress policy;
- public layer publication;

require explicit administrative authority and audit.

## 22. Enterprise release gates

Before an enterprise-readiness claim:

- tenant isolation tests;
- authn/authz threat tests;
- backup/restore proof;
- upgrade/rollback proof;
- data egress tests;
- source/SBOM audit;
- supported-platform deployment proof;
- observability proof;
- load/soak evidence;
- incident runbooks;
- privacy/security review;
- no unresolved R3 findings.
