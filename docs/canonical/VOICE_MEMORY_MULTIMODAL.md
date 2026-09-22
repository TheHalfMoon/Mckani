# Voice, Spatial Memory, and Multimodal Context

## 1. Voice is a control plane

Mckani voice is not microphone-to-search-box dictation.

Target flow:

~~~text
audio
-> capture health
-> VAD / endpointing
-> streaming STT
-> spatial-context grounding
-> COMMAND / ASIDE / QUESTION / CORRECTION / CANCEL
-> typed intent
-> capability policy
-> deterministic spatial tools / agent
-> evidence
-> map action
-> optional TTS
~~~

## 2. Provenance through speech

Keep separable:

1. source audio metadata or explicit non-persistence marker;
2. raw transcript;
3. normalized transcript;
4. location/place/entity candidates;
5. selected entity bindings;
6. semantic utterance class;
7. typed instruction/context;
8. authorization decision;
9. resulting effects/evidence.

A polished agent prompt must not become the only record of what happened.

## 3. Push-to-talk baseline

The first voice product proves:

- visible push-to-talk;
- cancel;
- partial/final transcription;
- text correction;
- touch/text fallback;
- bounded spatial context;
- no passive background recording.

Later, independent horizons may qualify:

- semantic endpointing;
- wake word;
- hands-free turn taking;
- duplex TTS;
- acoustic echo cancellation;
- background/lock-screen modes where OS rules and privacy allow.

## 4. Interruption

Audio capture, STT, TTS, agent execution, navigation, and UI rendering have independently cancellable lifecycles.

If the user interrupts:

- TTS stops immediately where technically possible;
- current agent/tool action receives cancellation if cancellable;
- stale outputs cannot silently apply after cancellation;
- non-cancellable side effects retain explicit status.

## 5. Command vs context

Speech can be:

- COMMAND;
- QUESTION;
- ASIDE/context;
- CORRECTION;
- CONFIRMATION;
- DENIAL;
- CANCEL;
- UNKNOWN.

Probabilistic classification feeds deterministic policy.

Example:

"I might go to Jeddah tomorrow, don't plan anything yet" is context/aside, not a route-creation command.

## 6. Spatial voice context

Voice resolution may use a bounded state envelope:

- current/consented location;
- heading and motion state;
- viewport;
- zoom;
- selected entities;
- active route;
- upcoming maneuver;
- active trip/order;
- visible layers;
- recent relevant dialogue;
- local personal preference refs;
- safety/driving state.

This allows "what is that building?" without sending an unbounded world snapshot.

## 7. Driving/riding mode

When movement context indicates driving:

- minimize visual interaction;
- prefer short voice output;
- avoid unnecessary confirmations that require screen interaction;
- require stronger confirmation for consequential changes;
- allow safe cancellation;
- do not expose complex dashboards;
- respect platform driving-safety restrictions.

## 8. Speech engine fabric

Speech engines are replaceable.

Candidates already researched in TheHalfMoon/Himsat and Wispral include:

- whisper.cpp — portable local ASR baseline;
- sherpa-onnx — ASR/VAD/diarization/speaker/KWS/TTS substrate candidate;
- Moonshine-class edge speech — low-latency challenger;
- platform-native acceleration;
- Silero/TEN/sherpa-hosted VAD challengers;
- qualified local TTS engines.

Exact engine/model pair is a model-registry artifact with:

- runtime revision;
- binary digest;
- model revision/digest;
- license/permission;
- language support;
- memory/accelerator needs;
- benchmark evidence.

## 9. Voice benchmark

Measure:

- word/entity accuracy;
- place/address/entity binding accuracy;
- Arabic/English/code-switching;
- noisy car;
- wind/outdoor;
- Bluetooth;
- far-field;
- endpointing;
- false activation;
- correction preservation;
- barge-in stages;
- end-to-end latency;
- CPU/RAM;
- battery/thermal;
- long-session stability;
- privacy/network behavior.

Generic WER alone is insufficient.

## 10. Spatial Memory

Mckani memory scopes:

~~~text
SESSION
PERSONAL
HOUSEHOLD / SHARED
PLACE
ROUTE
TRIP
PROJECT
TEAM
ORGANIZATION
WORLD_CANDIDATE
~~~

Public world memory is not automatically writable from personal observation.

## 11. Memory lifecycle

~~~text
observation
-> candidate
-> normalize
-> sensitivity/taint
-> decision
-> policy/scope
-> STORE | UPDATE | MERGE | SUPERSEDE | CONTRADICT
   | EXPIRE | FORGET | REDACT | QUARANTINE
   | IGNORE | REQUIRE_REVIEW
-> durable version
-> derived indexes
~~~

This adapts Morize's governed-memory pattern to space/time.

## 12. Memory examples

Personal:

- prefers quiet cafes;
- avoids a route;
- saved parking location;
- enjoyed a trail;
- accessibility preference;
- explicit budget range.

Place/route observation:

- entrance was closed at a recorded time;
- parking was difficult;
- loading dock moved;
- road work observed.

Organization:

- approved loading entrance;
- rejected site and reasons;
- facility operational history;
- route policy;
- decision evidence.

Each has different scope and authority.

## 13. Sensitive-memory policy

Do not automatically promote:

- home inference;
- workplace inference;
- healthcare visit history;
- religious/political location inference;
- sensitive-person association;
- precise movement history;
- voice raw audio;

into durable general memory.

Sensitive categories require explicit product policy and often explicit user action.

## 14. Memory controls

User-facing:

- What do you remember about me?
- Why do you remember this?
- Correct this.
- Forget this.
- Forget this trip/area/time range where supported.
- Export my Mckani data.
- Disable selected memory categories.

Organization administrators receive equivalent scoped governance for organization-owned memory, not employee private memory.

## 15. Multimodal geo-ingestion

Inputs:

- PDF;
- image;
- screenshot;
- CSV;
- GeoJSON;
- GeoParquet;
- GPX/KML where supported;
- engineering/site plan;
- drone/aerial image where rights allow;
- web document;
- voice note;
- camera observation.

Pipeline:

~~~text
input
-> hostile-input boundary
-> parser/OCR/vision
-> normalized document IR
-> place/address/date/entity extraction
-> geospatial candidate linking
-> confidence/evidence
-> user/reviewer confirmation where needed
-> private/public scope decision
-> world observation
~~~

External content cannot issue agent instructions merely because it contains imperative text.

## 16. Camera and AR

Camera uses are contextual:

- identify a place/building candidate;
- read a sign/menu/parking rule;
- find an entrance;
- return to parking;
- field-asset capture;
- document site evidence.

AR is later and bounded to useful navigation/field tasks.

Image recognition is not permission for facial recognition.

## 17. Evidence retention

Raw media retention is separate from derived text/entity memory.

The user/organization may choose:

- do not store;
- session-only;
- retain source;
- retain redacted source;
- retain derived facts only.

Derived facts always retain lineage to the retention policy, even when the source bytes are no longer retained.
