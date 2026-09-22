# World Pulse and Data Fabric

## 1. Objective

A modern map must answer not only "what is here?" but:

- what is happening now;
- what changed;
- what is abnormal;
- what is likely next;
- how fresh is the evidence;
- what does it mean for the user's current goal.

World Pulse is the normalized time-varying state layer above provider-specific feeds.

## 2. Normalized pulse types

### TrafficState

- road/edge reference;
- observed speed;
- free-flow/typical speed where known;
- congestion/jam level;
- incidents/closures;
- observed_at;
- source;
- confidence/quality;
- predicted intervals where available;
- rights/retention.

### PlacePulse

- open/closed/unknown;
- current activity estimate;
- typical activity;
- trend;
- queue/wait estimate where supported;
- predicted activity;
- confidence;
- evidence;
- freshness.

### ParkingPulse

- facility/area;
- availability estimate;
- entrance;
- price;
- restrictions;
- EV/accessibility attributes;
- observed/predicted time;
- confidence.

### TransitPulse

- trip updates;
- delays/cancellations;
- service alerts;
- vehicle positions;
- feed freshness.

### WeatherPulse

- current conditions;
- precipitation/radar reference;
- wind;
- visibility;
- heat;
- dust/air quality where sourced;
- hazard alerts;
- forecast horizon.

### Event/Incident

- type;
- geometry;
- time;
- expected/observed impact;
- evidence;
- severity;
- affected network/world entities.

## 3. Provider Fabric

Provider families:

- basemap/tiles;
- open world entities;
- geocoding/search;
- routing;
- traffic;
- places/reputation;
- parking;
- transit;
- weather/radar;
- imagery/terrain;
- EV charging;
- events;
- municipal/open-data feeds;
- enterprise sensors;
- user/community telemetry.

Each family has a stable Mckani contract.

## 4. Open baseline

Planning baseline:

### OpenFreeMap

Role:

- open vector basemap/tile infrastructure;
- styles;
- self-hosting reference;
- full-planet/regional tile source candidate.

Not:

- geocoder;
- router;
- live traffic;
- satellite provider;
- place-reputation service.

### Overture Maps

Role:

- open world entities;
- addresses/buildings/divisions/places/transportation;
- structured schemas;
- GERS stable reference identities;
- GeoParquet/source data for regional packs and server analytics.

Mckani still owns conflation and private identities.

### OpenStreetMap

Critical road/place/community source with ODbL and attribution obligations.

Data rights are separate from code rights.

## 5. Regional distribution

Avoid making the personal product dependent on founder-funded dynamic backend compute.

Preferred patterns where fit:

- static/object-hosted artifacts;
- range-readable archives;
- regional downloads;
- CDN/community mirrors;
- delta updates;
- local cache;
- user/company self-hosting;
- BYO provider.

A RegionPack has a manifest, checksums, source releases, rights, attribution, compatible schema version, and rollback metadata.

## 6. Search data

Baseline search should combine structured and lexical evidence before semantic search.

Possible local data:

- Overture places/addresses;
- OSM-derived aliases;
- country/region dictionaries;
- official address sources when authorized;
- local user aliases;
- organization private places.

Public Nominatim is not an unlimited autocomplete SLA.

## 7. Traffic strategy

There is no assumed free global live-traffic feed with proprietary-provider quality.

Launch architecture:

1. traffic-independent routing baseline;
2. qualified provider adapter(s) where user/company accepts terms/cost;
3. public/municipal incident feeds where available;
4. enterprise/fleet observations;
5. privacy-safe Mckani network signals as scale develops.

Traffic absence must be explicit, never replaced with fabricated live state.

## 8. Place activity and busy-now

Busy-now is a data-network problem, not a UI feature.

Candidate signal fusion:

~~~text
opening hours
+ historical visit patterns
+ anonymous opt-in arrival/departure aggregates
+ dwell distribution
+ nearby traffic/transit
+ parking pressure
+ events
+ weather
+ merchant signals
+ user reports
+ licensed provider signals
-> PlacePulse
~~~

The system must publish confidence and suppress low-evidence estimates.

## 9. Privacy-safe World Pulse Network

Long-term opt-in first-party network:

~~~text
raw device observation
-> on-device validation/reduction
-> coarse H3/time bucket
-> privacy/quality filter
-> aggregation threshold
-> differential-privacy or equivalent qualified protection where applicable
-> aggregate pulse
~~~

Principles:

- do not upload full raw location history as the default;
- require sufficient cohort before publishing;
- defend against low-count re-identification;
- rate-limit and detect poisoning/anomaly patterns;
- allow full opt-out;
- do not make participation a hidden condition of core map use.

Exact privacy mechanism is benchmark/security gated.

## 10. Ratings and reputation

Store source-specific reputation separately.

Example:

~~~text
Mckani verified reviews
Provider A rating
Provider B rating
Personal fit prediction
~~~

Do not average incompatible scales blindly.

A derived reputation score may consider:

- recency;
- sample size;
- verified visit;
- source reliability;
- abuse/spam risk;
- dimension relevance.

The formula/version remains inspectable.

## 11. Review dimensions

Category-specific dimensions can include:

- quality;
- service;
- value;
- quietness;
- work-friendliness;
- parking;
- accessibility;
- family fit;
- wait;
- cleanliness.

Dimensions need minimum-count safeguards.

AI theme summaries are derived analytics, not the review record.

## 12. Verified visit

A verified-visit signal should reveal only what is needed to establish review eligibility.

Design goal:

- local plausibility check;
- bounded cryptographic/attestation approach only if justified;
- no publication of the user's location history;
- anti-replay/abuse;
- retention minimization.

A verified visit increases evidence weight but does not guarantee review truth.

## 13. Parking and arrival

Destination understanding includes:

- correct entrance;
- vehicle/courier entrance;
- drop-off/pickup;
- parking facilities;
- walk from parking;
- restrictions;
- accessibility;
- EV;
- historical arrival friction.

A route should be able to terminate at the best arrival point, not only the entity centroid.

## 14. Weather and hazards

Weather/radar providers remain adapters.

Weather can affect:

- route recommendation;
- walking/cycling;
- delivery ETA;
- outdoor place fit;
- event impact;
- fleet risk.

Weather forecasts are PREDICTED and carry source/horizon.

## 15. Transit

GTFS Schedule and GTFS Realtime are preferred open interchange standards where feeds exist.

Transit freshness is explicit.

No update means unknown realtime status, not "on time".

## 16. Imagery

Satellite/aerial/photogrammetry is provider- and rights-sensitive.

Separate:

- renderer support;
- imagery access;
- caching;
- redistribution;
- training/use;
- capture date;
- resolution;
- attribution.

Open/public earth-observation imagery may support analysis but does not automatically replace consumer high-resolution imagery.

## 17. Freshness

Every live/derived layer defines:

- expected update interval;
- stale threshold;
- expiry;
- fallback;
- visible freshness label.

Example states:

~~~text
LIVE — 42 seconds ago
RECENT — 12 minutes ago
STALE — 3 hours ago
HISTORICAL
PREDICTED — next 30 minutes
UNKNOWN
~~~

## 18. Provider health

ProviderHealth records:

- reachability;
- last success/failure;
- latency;
- quota/cost state where available;
- schema/version compatibility;
- freshness;
- regional coverage.

Provider health affects routing but never silently widens privacy/cost policy.

## 19. Cost policy

Core personal correctness must not require a founder API key.

Optional commercial feeds are:

- user-funded;
- company-funded;
- future managed-plan funded;
- BYOK/BYO contract.

The Provider Registry records cost owner and hard budget/limit behavior.

## 20. Data observability

Track without logging sensitive payloads unnecessarily:

- freshness;
- missingness;
- duplicate rate;
- conflation conflict;
- update failures;
- source coverage;
- stale cells/regions;
- provider error classes;
- ingestion lag;
- rights manifest version.

Data quality problems are visible operational state.
