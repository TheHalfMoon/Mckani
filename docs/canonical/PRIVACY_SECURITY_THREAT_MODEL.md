# Privacy and Security Threat Model

## 1. Security objective

Protect private location, movement, enterprise worlds, credentials, provider secrets, agent authority, and canonical world integrity while still supporting useful spatial intelligence.

Privacy is a data-flow property, not a settings-page promise.

## 2. High-value assets

- precise current location;
- location history;
- home/work/private-place associations;
- saved places/trips;
- voice/audio;
- private photos/documents;
- personal memory;
- organization geometry;
- fleet/customer/order state;
- enterprise assets/sensors;
- authentication/session material;
- provider/API secrets;
- world/evidence ledger;
- model/context bundles;
- decision/dispatch policies;
- backups/exports.

## 3. Trust zones

~~~text
Device local trusted core
Device UI/renderers
Local models
External map/data providers
External AI providers
Mckani/self-hosted control plane
Enterprise connectors
Untrusted files/web/documents
Other users/collaborators
Agents/plugins/MCP clients
~~~

Connectivity does not grant trust.

## 4. Threats and controls

### Precise location leakage

Threats:

- ordinary telemetry;
- tile/provider requests;
- route/geocoder queries;
- share links;
- logs;
- crash reports;
- analytics.

Controls:

- minimize;
- local processing;
- coarse aggregation;
- strip identity;
- sensitive logging policy;
- provider egress policy;
- private opaque share tokens;
- no precise location in URLs when avoidable;
- retention limits.

### Location-history overcollection

Controls:

- accountless/local baseline;
- no default forever GPS ledger;
- memory candidate policy;
- category controls;
- expiry;
- user inspection/export/delete.

### Public/private world conflation

Controls:

- scope-aware WorldEntity overlays;
- explicit publication workflow;
- no automatic public promotion;
- provenance/sensitivity on every assertion.

### Named-person surveillance

Mckani does not provide a default product capability for:

- searching/tracking arbitrary named individuals;
- facial recognition;
- covert background surveillance.

Legitimate enterprise fleet/workforce contexts require explicit role, purpose, consent/legal authority as applicable, retention and audit.

### Prompt/tool injection

Untrusted map metadata, reviews, files, web pages, documents and connector payloads may contain instructions.

Controls:

- treat as data;
- taint;
- bounded parsers;
- context compiler;
- capability policy independent of content;
- no content-derived privilege;
- output validation.

### Malicious maps/styles/3D assets

Threats:

- XSS/script payload;
- oversized geometry;
- decompression bombs;
- hostile shaders/assets;
- remote URL fetches.

Controls:

- strict schemas;
- CSP/web isolation;
- size/complexity limits;
- allowlisted fetch policy;
- safe parsers;
- worker/sandbox boundaries where justified;
- no arbitrary executable style expressions beyond renderer contract.

### SSRF

Provider/import URL fetching:

- scheme allowlist;
- DNS/IP protections;
- private-network policy;
- redirect limits;
- size/time limits;
- credential isolation.

### Provider credential leakage

- OS secure storage/enterprise secret store;
- no key in logs/share URLs;
- scoped keys;
- rotation;
- provider-domain allowlist;
- separate client/server credentials.

### Supply chain

- pinned dependencies for release;
- lockfiles;
- SBOM;
- checksum/signature where available;
- license/notice;
- dependency review;
- no unverified donor script execution;
- reproducible release evidence where practical.

### Model supply chain

Every executable model bundle records:

- source;
- revision;
- digest;
- license;
- runtime;
- conversion lineage;
- resource manifest.

Model file is untrusted binary/data input to its runtime.

### World-data poisoning

Threat:

- false place;
- malicious edit;
- fake closure;
- fake busy signal;
- review spam;
- sensor spoofing.

Controls:

- source identity;
- corroboration;
- trust/quality;
- anomaly detection;
- rate limits;
- reversible assertions;
- conflicts;
- human/provider review for material corrections.

### GPS/location spoofing

Use plausibility and cross-signal checks where legitimate.

Do not turn anti-abuse into invasive hidden surveillance.

### Mobility replay/duplication

- idempotency keys;
- event identities;
- assignment versions;
- proof anti-replay;
- durable state machine;
- reconciliation.

### Route manipulation

Route inputs/providers are untrusted.

Hard safety/legal constraints are validated independently where data supports them. Unknown road restriction or stale data is surfaced rather than assumed safe.

### Tenant escape

Controls:

- tenant key in every server authority path;
- database policy/tests;
- tenant-specific object namespaces;
- cache/index scoping;
- context-bundle authorization before retrieval;
- adversarial cross-tenant tests;
- export isolation.

### Sync conflict and rollback

- version/digest compare;
- immutable versions for critical objects;
- explicit conflict;
- reconciliation state;
- no silent overwrite of newer private state;
- delete propagation.

### Alerts/workflows side effects

- idempotency;
- effect authorization;
- bounded retries;
- duplicate suppression;
- delivery state;
- approval for high-impact actions.

## 5. Privacy-safe aggregation

H3/coarse spatial analytics can still re-identify people when counts are low.

Controls:

- minimum cohort;
- time-bucket policy;
- suppression;
- noise/privacy mechanism where justified;
- no high-dimensional drill-down that reconstructs an individual;
- audit for export.

## 6. Voice privacy

Defaults:

- explicit active listening indicator;
- push-to-talk baseline;
- no passive recording;
- local STT where qualified;
- audio retention independent from transcript/memory;
- external STT is explicit provider egress;
- driving interaction safety.

## 7. Children/minors and sensitive places

The product must not create hidden sensitive-person profiles from repeated presence at schools, clinics, places of worship, shelters, political venues, or other sensitive sites.

Any future feature involving protected/sensitive inferences requires separate policy/legal/privacy authorization and should prefer not creating the inference.

## 8. Enterprise employee data

Organization ownership of devices/fleet does not automatically justify unlimited worker monitoring.

Enterprise plans must define:

- operational purpose;
- collection scope;
- visible policy;
- retention;
- role access;
- jurisdiction;
- off-shift boundaries where applicable.

## 9. Network Lock

Support a policy mode in which selected data classes cannot leave the device/customer network.

A provider/router/model marked network-required is unavailable rather than silently bypassing Network Lock.

## 10. Security risk levels

R3 examples:

- authorization;
- tenant isolation;
- encryption/key handling;
- precise-location sharing;
- background location;
- sync conflict;
- public publication;
- provider secrets;
- release/update integrity;
- destructive memory/delete;
- dispatch/payment policy;
- enterprise connectors with write effects.

R3 requires independent review and adversarial/failure evidence.

## 11. Security acceptance

No security/privacy claim is accepted from design prose alone.

Evidence includes:

- threat tests;
- negative tests;
- logs/telemetry inspection;
- network egress capture;
- failure injection;
- cross-tenant tests;
- restore/delete proof;
- dependency/SBOM review;
- exact-head independent review.
