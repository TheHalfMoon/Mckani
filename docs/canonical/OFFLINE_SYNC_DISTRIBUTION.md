# Offline, Sync, Distribution, and Updates

## 1. Objective

"App + internet" should be simple for ordinary users while still allowing useful degraded/offline behavior.

Offline capability is regional and capability-specific, not a blanket claim.

## 2. Install profile

Base application should avoid bundling every world dataset/model.

Candidate install:

- application runtime;
- minimal style/assets;
- lightweight local state;
- no mandatory large LLM;
- no mandatory planet database.

Additional packs download on demand.

## 3. Pack classes

- RegionPack;
- VoicePack;
- DecisionPack;
- LocalLLMPack;
- Vision/OCRPack;
- Terrain/3DPack;
- EnterprisePolicyPack.

Every pack has:

- manifest version;
- compatible app/core version;
- source/revision;
- rights/attribution;
- file digests;
- size;
- capabilities;
- hardware requirements;
- install/update/rollback metadata.

## 4. Region pack lifecycle

~~~text
discover
-> rights/compatibility check
-> space/battery/network policy
-> download to staging
-> digest verification
-> structural validation
-> atomic publish
-> index build/verify
-> active
~~~

Interrupted install never replaces a known-good active pack.

## 5. Delta/update

Where formats/sources permit:

- version manifests;
- conditional fetch;
- delta download;
- staged rebuild;
- atomic switch;
- old-version retention for bounded rollback.

Never patch a routing/search database in place without recovery semantics.

## 6. Offline matrix

Each feature declares:

- ONLINE_REQUIRED;
- OFFLINE_IF_PACKED;
- OFFLINE_DEGRADED;
- LOCAL_ONLY.

Examples:

- map tiles: offline if region cached/packed;
- local search: offline if index present;
- routing: offline if graph present;
- traffic: online/live feed required, historical fallback only if explicitly modeled;
- cloud imagery: online unless licensed cache;
- local voice: offline if speech pack present;
- personal memory: local;
- enterprise shared state: degraded/local queue depending workflow.

## 7. Sync objects

Not every local object needs cloud sync.

Candidate synced objects:

- saved places/lists;
- explicit personal preferences;
- user-created layers;
- alerts;
- scenario definitions;
- selected memory categories;
- collaboration state.

Provider cache and open world packs can be re-fetched and need not be treated as personal sync truth.

## 8. Conflict classes

Objects declare merge semantics:

- last-write-safe;
- set/CRDT-like;
- append-only;
- compare-and-swap;
- manual conflict;
- non-mergeable.

Do not use generic last-write-wins for memories, decisions, payments, assignments, or policy.

## 9. Deletion

Deletion/forget supports:

- local canonical state;
- sync replicas;
- derived indexes;
- caches where user data is represented;
- exports/backups according to declared retention;
- audit references that may retain tombstone evidence without retaining deleted content where policy allows.

## 10. Encryption

Before sensitive cross-device sync, define:

- key ownership;
- recovery;
- device enrollment;
- server visibility;
- rotation;
- revoked devices;
- backup;
- sharing semantics.

Do not advertise end-to-end encryption until exact implementation and threat evidence exist.

## 11. Model updates

Model update is a supply-chain event.

Require:

- exact model/runtime;
- digest;
- rights;
- benchmark cell;
- device compatibility;
- rollback;
- no silent quality/privacy regression.

## 12. App updates

Release/update infrastructure is R3.

Requirements:

- signed/reputable package channels;
- checksum/provenance;
- rollback/recovery strategy;
- migration compatibility;
- unsupported-newer-data fail-safe;
- no updater shell execution from untrusted provider metadata.

## 13. Bandwidth/storage governor

The user can control:

- cellular downloads;
- background updates;
- max cache;
- region retention;
- model packs;
- offline regions.

Mckani surfaces storage impact before large downloads.

## 14. Enterprise distribution

Enterprises may:

- mirror packs/models internally;
- pin versions;
- block external updates;
- qualify update windows;
- enforce provider/model allowlists.

The same manifest/digest model supports controlled enterprise distribution.
