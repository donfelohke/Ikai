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
