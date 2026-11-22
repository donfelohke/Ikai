# IKAI — Mirror Systems, Cameras, Displays and Real-Time Bidirectional I/O

**Date:** 22 November 2026  
**Owner:** IKAI / MIRROR  
**Status:** RESEARCH / PROPOSED VALIDATION PROTOCOL  
**System shorthand:** **LIGHT IN → COMPUTE → LIGHT OUT**  
**Principle:** A mirror, not a judge.

## 1. Research question

How can a reflective environment combine mirror optics, optical/electronic sensing, local computation, display output and human-directed feedback while preserving participant agency, privacy, low latency and inspectable operation?

This is a systems research question, not a claim that an integrated mirror exists.

## 2. Optical construction and M1 candidate

The initial M1 study prioritises a **two-way / partially reflective mirror** as the leading candidate because it may support a reflective surface and a display path behind the glass. This is a candidate for comparative validation, not a final component selection, procurement decision or proven optical stack.

Compare against other mirror and reflective constructions. Measure or document:

- visible-light transmission and reflectance across the relevant spectrum;
- colour cast, haze, distortion, ghosting and surface quality;
- viewing angle, ambient-light dependence and reflected-scene brightness;
- display luminance and contrast through the optical stack;
- camera/sensor visibility, occlusion and placement constraints;
- thickness, weight, edge treatment, mounting, safety and serviceability.

Do not assume a vendor's nominal reflectance/transmission ratio predicts assembled performance. Test the actual glass, display and lighting geometry together.

## 3. Separate the subsystems

| Subsystem | Inputs / outputs | Evidence required |
|---|---|---|
| Reflective optics | Ambient scene ↔ reflective/transmissive surface | Measured transmission, reflection, colour and viewing-angle behaviour |
| Camera / optical acquisition | Scene light → frames | Field of view, exposure, frame timing, privacy state and image quality |
| Other sensors | Physical signal → timestamped samples | Sensor type, calibration, range, sample rate and failure behaviour |
| Local compute | Frames/events → derived output | Hardware, software, latency, load, memory and thermal observations |
| Display | Pixels → visible output through mirror | Luminance, contrast, colour, refresh, geometry and power |
| Human controls | Intent/authorisation → permitted action | Clear state, explicit consent, override and observable result |

Camera capture is not equivalent to reflection. A mirror can function optically without a camera; a camera must not be treated as implicit permission to identify or profile a person.

## 4. Real-time bidirectional I/O

Model the system as multiple independently measurable paths:

1. **Optical input → capture:** scene photons to camera/sensor samples.
2. **Capture → compute:** timestamped frames/events to local processing.
3. **Compute → display:** rendered frames or bounded updates to the display pipeline.
4. **Human/control input → compute:** explicit user commands, consent and overrides.
5. **Display/environment feedback → next observation:** visible output changes the environment and subsequent observation.

For every path, define payload, format, clock domain, timestamp origin, sample/frame rate, throughput, buffering, queue policy, back-pressure, latency, jitter, loss/drop behaviour, synchronisation and recovery. Do not combine average latency with worst-case latency or infer end-to-end timing from one subsystem.

### Proposed measurement matrix

| Test | Measure | Record |
|---|---|---|
| Capture cadence | Frame interval and dropped frames | Median, p95/p99, maximum and drop count |
| Capture-to-display | End-to-end glass-to-glass latency | Timestamp method, sample count and distribution |
| Clock alignment | Drift and synchronisation error | Clock sources, offset and drift over time |
| Bidirectional control | Command-to-visible-state and feedback delay | Command ID, acknowledgement and observed state |
| Sustained load | Throughput, queue depth and thermal state | Duration, hardware and workload |
| Failure/recovery | Device loss, stalled stream, overload and restart | Safe state, user notification and recovery time |

No benchmark values are asserted until an experiment is actually run.

## 5. Reuse and interoperability

Survey and qualify existing native interfaces before inventing a new stack. Candidate areas include Linux V4L2 capture, DRM/KMS display, PipeWire media routing, GStreamer pipelines and OpenXR for spatial interfaces. These are research candidates, not approved dependencies or evidence of compatibility with a chosen mirror assembly. Preserve upstream attribution, licence, version and test results.

## 6. Agency, privacy and safety

- Capture is off by default unless a narrowly scoped, explicit experiment authorises it.
- Presence is not identity, consent or permission.
- No face identification, biometric identity matching, person scoring/ranking, diagnosis, covert recording or hidden profiling.
- Keep processing local by default; document any external transfer before it exists.
- Make capture, retention, export, deletion, physical disable and human override testable.
- Separate observation, inference, proposal, authorisation, execution, verification and record.

## 7. Maturity gates

Literature review → hypothesis → optical bench test → subsystem prototype → integrated prototype → independent validation → release are separate gates. A diagram, source repository, paper design or document is not a prototype. Negative results and unknowns are first-class records.

## 8. Ownership

IKAI owns the reflective environment, optical research and participant-facing interaction. WARENA owns enabling compute, device interfaces, timing, local infrastructure and reproducible system validation. GENJE owns authored movement and creative interpretation. FELOH Corpus owns shared canon and evidence standards. NAKEBUSEN remains the only commercial transaction interface.

**Related:** [IKAI M1 validation](IKAI-MIRROR-M1-ENGINEERING-VALIDATION-2026-11-18.md) · [REFLECTION± research](REFLECTION-PLUS-MINUS-LIGHT-IN-LIGHT-OUT-COMPUTE-RESEARCH-2026-11-21.md) · [WARENA real-time I/O architecture](https://github.com/donfelohke/WARENA/blob/main/docs/REALTIME-BIDIRECTIONAL-IO-AND-DISPLAY-PIPELINES-2026-11-22.md)
