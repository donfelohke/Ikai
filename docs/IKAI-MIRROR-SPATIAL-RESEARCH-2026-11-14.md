# IKAI MIRROR+ — Spatial Computing Research

**Date:** 2026-11-14  
**Status:** RESEARCH / ARCHITECTURE EXPLORATION  
**Authority:** IKAI specialist research; shared terms and evidence rules remain in [FELOH Corpus](https://github.com/donfelohke/feloh-corpus).  
**Product status:** Not a released product. No working mirror, validated sensor pipeline or deployment is claimed.

## 1. Reframe the device

Do not define IKAI MIRROR+ as a screen placed behind two-way glass. Investigate it as a spatial-computing environment in which a reflective surface may be one component among several: optical output, spatial reference, participant interface, physical boundary or none of these for a particular task.

The experience should be designed around what a participant needs to see, manipulate, compare, remember or create. Hardware follows the task. A mirror is not inherently an XR device, and XR does not require a head-mounted display.

## 2. Research questions

1. What does the participant perceive as spatially present: reflection, overlay, projection, volumetric content, a tracked object, or a desktop window?
2. Which tasks genuinely benefit from spatial registration rather than a conventional screen?
3. What is the required field of view, viewing distance, eye box, luminance, contrast, refresh rate and ambient-light tolerance?
4. Is body-relative or room-relative tracking necessary? What accuracy and latency are sufficient?
5. Can interaction remain usable with no camera, no network and no persistent profile?
6. How are uncertainty, calibration drift, occlusion and sensor failure represented to the participant?
7. How can a participant inspect, export and delete any retained record?
8. How can movement and Laban-informed practice remain contextual and authored rather than converted into a score?

## 3. Architecture domains

| Domain | Candidate approaches | Questions before selection |
|---|---|---|
| Reflective / emissive optics | Reflective glass, transparent display, conventional display, projection, spatial display | Optical quality, privacy, viewing angle, glare, brightness and cost |
| Spatial sensing | RGB/depth camera, stereo, IMU, fiducials, manual calibration | Minimum necessary data, calibration, drift and failure modes |
| Spatial registration | Camera calibration, fiducial tracking, SLAM, scene graphs, coordinate transforms | Accuracy, repeatability, occlusion and relocalisation |
| Runtime | OpenXR, Monado, native graphics and desktop composition | Supported devices/extensions, compositor and application lifecycle |
| Scene / content model | OpenUSD, scene graphs, custom application models | Interchange, versioning, asset provenance and runtime cost |
| Interaction | Touch, keyboard, pointer, voice, gesture, tracked body/object | Accessibility, consent, user override and accidental activation |
| Reflection and memory | Local files, participant-authored notes, SQLite indexes | Authority, provenance, retention, export and deletion |
| Audio / media | PipeWire, spatial audio, livecoding and audiovisual tools | Locality, timing, noise and participant control |

All listed approaches are candidates for evaluation, not selected dependencies.

## 4. Historical architecture worth recovering

### MAVERIK

The uploaded 1999 paper *GNW/MAVERIK: A micro-kernel for large-scale virtual environments* describes a VR micro-kernel designed to support different internal representations of virtual environments, application-data callbacks, large models, customised interaction and navigation. The paper places it within a wider architecture with Deva, which provides multi-user distributed shared environments and persistent concurrent environments.

This separation is directly relevant to IKAI: keep rendering/interaction concerns distinct from persistent environment, collaboration and synchronization services. Do not assume that a historical VR kernel is a modern XR runtime.

**Disposition:** RESURRECT / EXTRACT candidate. Source recovery, exact version, licence, buildability and modern graphics compatibility remain unverified.

### DEVA / DEVA3

DEVA and DEVA3 should be investigated as environment/runtime and distributed-synchronization research, separately from MAVERIK. The DEVA3 primary source and exact implementation lineage still require verification. Avoid conflating names, versions or architectural claims.

**Disposition:** RESEARCH LEAD until primary sources and surviving artefacts are located.

## 5. Participant authority and privacy

The existing IKAI mirror-not-judge boundary applies to every new spatial capability:

- No face identification, biometric identity matching, emotion inference, diagnosis, ranking, person scoring or covert profiling.
- No continuous recording by default.
- Sensor access must be task-specific, visible and revocable.
- Prefer local processing; external processing requires a reviewed purpose, data-flow and retention model.
- Separate observation from interpretation and interpretation from authorization.
- Participant-authored records remain inspectable, exportable and deletable.
- Use synthetic data and fiducials before considering body tracking.
- A demo does not validate accuracy, safety or privacy.

## 6. Evaluation protocol

For each candidate or experiment record:

- research question and task;
- exact hardware/software versions and source commits;
- optical, spatial and interaction requirements;
- calibration procedure and measured error;
- end-to-end latency and frame stability;
- lighting, occlusion and environmental conditions;
- data collected, processing location and retention;
- participant control, consent and accessibility;
- failure behaviour and manual fallback;
- reproducibility, limitations and disposition.

## 7. Research sequence

1. Requirements and task analysis before BOM selection.
2. Optical survey: reflective, transparent-emissive, projection and conventional display options.
3. Desktop/spatial-runtime comparison, including non-XR baselines.
4. Fiducial and synthetic-data experiments for calibration and registration.
5. Historical source archaeology for MAVERIK and DEVA3.
6. A replaceable local bench prototype only after measurable requirements are defined.
7. Participant-led evaluation before any claim of usefulness or readiness.

## 8. Cross-project ownership

- **WARENA** owns compute, graphics/runtime integration, hardware, Guix, reproducibility, networking and recovery.
- **GENJE** owns creative and movement practice, choreography, livecoding and embodied expression.
- **FELOH Corpus** owns shared governance, provenance and evidence labels.
- **NAKEBUSEN** remains the sole commercial interface; this research does not create a product or booking channel.

See the [cross-project research landscape](https://github.com/donfelohke/feloh-corpus/blob/main/research/ikai-mirror-spatial-computing-landscape-2026-11-14.md).


## Current technology-policy precedence — 2026-11-17

This document must be read subject to the current [WARENA Technology Constitution](https://github.com/donfelohke/WARENA/blob/main/docs/TECHNOLOGY-CONSTITUTION-2026-11-17.md) and [FELOH Corpus technology policy](https://github.com/donfelohke/feloh-corpus/blob/main/docs/technology-policy-2026-11-17.md). JavaScript is prohibited as a language, runtime, framework or dependency; web technologies are excluded as WARENA/IKAI application and runtime architecture. Prefer native, libre, local-first and user-controlled interfaces. Candidate tools listed in this document do not become approved dependencies merely by appearing here. Historical descriptions remain historical; apply this policy to current and future decisions.


## Source and architecture clarification — 2026-11-20

This addendum refines the historical MAVERIK / DEVA3 research lead using the published source records. It preserves the 2026-11-14 research note rather than silently rewriting its original scope.

### GNU/MAVERIK

The published work is titled **GNU/MAVERIK: A microkernel for large-scale virtual environments** (Hubbold et al., *Presence*, 2001; DOI: https://doi.org/10.1162/105474601750182298). Its callback-based object model allows the application to retain its own data representation while registering classes and methods used by the spatial framework. The companion research description identifies spatial/display management, culling, interaction, navigation and conventional/VR input-output support.

MAVERIK is a programmer's framework and historical architecture reference, not a contemporary XR runtime or end-user desktop. GNU archive indexes list historical 6.x source releases, including 6.4 (2009); this does not establish active maintenance or modern build compatibility.

### DEVA3

The DEVA3 paper is **“DEVA3: architecture for a large-scale distributed virtual reality system”**, by Steve Pettifer, Jon Cook, James Marsh and Adrian J. West, ACM VRST 2000, pp. 33–40; DOI: https://doi.org/10.1145/502393.502397.

The published abstract describes large-scale geographically distributed virtual environments, synchronization under network limitations using subjectivity, and a flexible model for virtual-environment object behaviour. This establishes DEVA3 as a distributed-environment architecture, distinct from a rendering toolkit, XR API or compositor.

### Relationship and WARENA disposition

Treat MAVERIK and DEVA3 as complementary research layers:
- MAVERIK informs local spatial services and application-owned data access.
- DEVA3 informs shared/distributed environment state, object behaviour and participant-specific views/synchronization.
- A faithful claim about exact historical integration, release pairing or source-level interoperability requires primary source archaeology.

WARENA's proposed architecture extracts these design principles; it does not claim a port or implementation. The canonical infrastructure comparison and modern interface boundaries are documented in [WARENA's Desktop, Spatial Computing, Immersive XR & Opt-in Intelligence Architecture (2026-11-20)](https://github.com/donfelohke/WARENA/blob/main/docs/SPATIAL-COMPUTING-XR-AI-ARCHITECTURE-2026-11-20.md).

### Source records

- GNU/MAVERIK paper: https://doi.org/10.1162/105474601750182298
- GNU/MAVERIK teaching/research paper: https://diglib.eg.org/server/api/core/bitstreams/6dcfe6df-735f-4db6-96d3-66e37cdbdce9/content
- GNU source archive: https://ftp.gnu.org/gnu/maverik/
- DEVA3 paper: https://doi.org/10.1145/502393.502397
- DEVA3 bibliographic record: https://dblp.org/rec/conf/vrst/PettiferCMW00

No source checkout, build, runtime, device integration or prototype is claimed.
