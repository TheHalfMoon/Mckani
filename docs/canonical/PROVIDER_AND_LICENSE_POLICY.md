# Provider, Source, Rights, and Cost Policy

## 1. Principle

Mckani separates:

- source-code rights;
- dependency license;
- model code license;
- model weight license;
- dataset license;
- map-data license;
- imagery rights;
- fonts/icons/styles;
- API/service terms;
- user-data permissions;
- trademarks/branding.

Permission in one category is never silently generalized to another.

## 2. Founder-authorized sources

The founder has stated permission to copy/adapt/use source from several named mapping/Jev sources and from repositories under the founder's GitHub control.

This is recorded as **founder-asserted permission** until an exact adoption binds:

- source identity;
- exact revision;
- selected paths;
- permission scope/evidence;
- embedded third-party closure.

Permission makes source eligible. It does not make the source secure, correct, maintained, or compatible.

## 3. Adoption modes

Each source is one of:

- DEPEND — consume a pinned package/library.
- COPY_SELECTIVE — copy exact qualified files/components.
- ADAPT_SELECTIVE — implement bounded adaptation with provenance.
- REFERENCE — learn behavior/architecture only.
- PROVIDER — external service/data adapter.
- DATA — ingest/transform dataset under explicit rights.
- EXPERIMENT — benchmark only.
- REJECT — do not adopt.

Whole-repository copy is never the default.

## 4. Provider registry

Every provider record includes:

~~~text
provider_id
capability_family
implementation/API version
regions
data classes
required credentials
network endpoints
privacy classification
retention/training terms
rights/attribution
cache/storage rules
cost owner
budget/quota
freshness
health/SLA
fallback
exit/migration
~~~

## 5. Cost classes

- ZERO_LOCAL — no per-use service charge.
- PUBLIC_BEST_EFFORT — free public endpoint, no production SLA assumed.
- USER_BYOK — user supplies key/contract.
- CUSTOMER_FUNDED — enterprise/startup pays provider.
- MCKANI_MANAGED — future paid Mckani service.
- UNKNOWN — cannot be production-required.

Core correctness must not depend on UNKNOWN or founder-funded per-query spend.

## 6. Open baseline strategy

Prefer open/local foundations where quality is adequate:

- MapLibre;
- OpenFreeMap/self-host patterns;
- Overture;
- OSM;
- H3;
- DuckDB/SQLite/PostGIS;
- qualified open routing/optimization;
- GTFS;
- local speech/models.

Optional providers enrich traffic, places, imagery and other live data.

## 7. Public free endpoint rule

A free public endpoint is not automatically production infrastructure.

Before production reliance, record:

- acceptable-use policy;
- quotas;
- commercial-use status;
- privacy;
- SLA/no-SLA;
- failover;
- caching;
- load responsibility.

Example: public Nominatim has explicit low-volume constraints and is not treated as default commercial autocomplete.

## 8. Attribution

Attribution is a product requirement.

Rendering/UI must support provider/data attribution without hiding it in source code or a legal file.

Region packs preserve their attribution manifest.

## 9. Derived databases

Before distributing a database derived from share-alike/open-map sources, close:

- source obligations;
- database-right implications;
- attribution;
- notice;
- redistribution;
- combination/conflation effects.

Do not infer legal status from code license.

## 10. Models

Model Registry must treat:

- runtime code;
- weights;
- tokenizer;
- adapters/LoRA;
- conversion outputs;
- training data claims;

as separate provenance surfaces.

A permissive runtime does not make a model weight permissive.

## 11. Commercial APIs

Mapbox, Google Maps Platform, HERE, TomTom, Radar, Foursquare, commercial imagery/terrain, or other services may be excellent providers.

They remain adapters.

Do not:

- make one required for repository tests;
- embed founder production keys;
- assume redistribution;
- assume response caching;
- assume training rights;
- assume derived-data ownership;
- claim zero-cost when provider billing applies.

## 12. Mapbox-specific boundary

Founder-stated permission to use source material does not identify a particular covered proprietary source artifact.

Until exact source/revision/scope evidence is present:

- treat current Mapbox products/APIs as product/provider references;
- do not copy proprietary source;
- do not backport incompatible proprietary Mapbox GL code into MapLibre.

## 13. God's Eye View boundary

Selective adaptation only after path-level provenance.

Acceptable conceptual areas:

- layer lifecycle;
- camera/scene behavior;
- shareable views;
- live-object visualization;
- voice-to-scene patterns.

Reject by default:

- named-person tracking;
- facial recognition;
- covert surveillance;
- unverified third-party data/assets;
- military/spy framing.

## 14. Project license

**Planning recommendation:** Apache-2.0 for Mckani-authored open-source core code.

**Status:** not founder-ratified by this planning PR.

P00 must ratify or replace the project-license decision before the first production code or donor-code import whose licensing depends on the project license.

No LICENSE file is created by this planning PR to avoid fabricating founder authority.

## 15. License compatibility

Before adoption:

- inspect exact LICENSE/NOTICE;
- inspect package/submodule/component licenses;
- preserve notices;
- verify patent terms where material;
- detect copyleft/network-copyleft implications;
- inspect generated/vendor assets;
- inspect model/data terms;
- record conclusion in SOURCE_LEDGER.

"GitHub says MIT" is not enough when selected files have different terms.

## 16. Secrets

Provider secrets:

- never committed;
- least privilege;
- environment/OS/enterprise secret store;
- rotation;
- separate dev/prod;
- browser-exposed keys only where provider intentionally supports restricted public keys;
- origin/app restrictions where available.

## 17. Provider degradation

Every provider integration must define what still works when it fails.

Core UI must not reinterpret unavailable as empty/zero.

## 18. Exit strategy

For any strategically important provider, keep:

- stable internal schema;
- export;
- data/provider ID mappings;
- replacement adapter tests;
- no provider-specific IDs leaking as canonical Mckani IDs.

Provider portability is part of architecture, not a later migration project.
