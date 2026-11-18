# IKAI Mirror M1 — Engineering Validation Specification

**Date:** 18 November 2026  
**Status:** RESEARCH / PROPOSED VALIDATION PLAN  
**Authority:** IKAI owns participant-facing requirements; WARENA evaluates enabling infrastructure; FELOH Corpus governs shared evidence and provenance.  
**Implementation status:** Not implemented. No hardware is selected, purchased, installed or qualified by this document.  
**Specification maturity:** Proposed test plan. Numerical thresholds marked provisional require review against actual optical materials, room conditions and test equipment before they become release criteria.

## 1. Purpose and decision

This document translates the IKAI Mirror Technology & Scholarly Research note into an engineering validation plan for a stationary M1 demonstrator.

M1 is intended to answer a narrow question:

> Can a locally operated, computationally augmented mirror preserve a useful physical reflection while presenting optional digital information in a controlled, measurable and participant-directed way?

M1 is not intended to prove the full IKAI platform, diagnose appearance or health, infer emotion, identify people, or deliver a commercial beauty service.

### 1.1 M1 design posture

- Physical reflection is the primary visual reference.
- Digital information is secondary, explicitly distinguishable and dismissible.
- No camera or sensor is required for the basic mirror/display demonstrator.
- Tracking is a separate, opt-in experiment and must not be a hidden dependency.
- Core display and interaction must work offline.
- Local data is minimised; no account or cloud service is required.
- Every component remains replaceable behind documented interfaces.
- GNU/Linux and native interfaces are preferred; Guile/Scheme is the application-orchestration research direction.
- No JavaScript or web-technology application/runtime dependency.

### 1.2 Out of scope

- Emotion recognition, affect inference or sentiment analysis.
- Face identification, identity matching or biometric templates.
- Medical, dermatological or scalp diagnosis.
- Body scoring, attractiveness scoring, ranking or normative appearance judgements.
- Automatic assessment of hair health, texture, colour or condition.
- Mandatory cloud, remote analytics, advertising or third-party telemetry.
- Production deployment, procurement approval, customer records or commercial availability.

## 2. System boundary and proposed test configuration

### 2.1 M1 system boundary

The demonstrator is divided into independently testable subsystems:

1. **Optical assembly:** mirror substrate, coating, frame, mounting and protective measures.
2. **Display assembly:** panel, controller, mounting, thermal management and brightness control.
3. **Illumination:** ambient and task lighting; controlled conditions for visual evaluation.
4. **Compute:** local GNU/Linux host, graphics output and storage.
5. **Application:** a minimal native display compositor/UI with a clearly visible idle state and dismissible overlay.
6. **Optional sensing:** separately enabled RGB camera or depth sensor, only for a defined experiment.
7. **Safety and control:** physical power isolation, display disable, camera disable and microphone mute if audio hardware is later introduced.

### 2.2 Reference arrangement to investigate

A semi-transparent reflective surface with a rear-mounted display is the preferred first optical candidate, not a final material selection. A conventional reference mirror and a direct display-only reference should be available for comparative testing.

The test fixture should allow adjustment of:
- Mirror-to-display spacing.
- Display position and angle.
- Observer distance and viewing angle.
- Front-side and rear-side illumination.
- Display luminance.
- Overlay position, size and opacity.

Do not permanently bond or enclose components before the optical and thermal tests pass.

### 2.3 Modes

| Mode | Function | Sensor requirement |
|---|---|---|
| M1-A Reflect | Conventional physical reflection | None |
| M1-B Display | Reflection plus static, non-personal information | None |
| M1-C Calibrated overlay | Reflection plus geometrically positioned graphics | Calibration target; no human tracking required |
| M1-D Optional tracking | Controlled hand/body interaction experiment | Sensor only if justified and explicitly enabled |

M1-A through M1-C define the minimum demonstrator. M1-D is optional and must not block validation of the basic mirror.

## 3. Requirements and acceptance criteria

The following thresholds are proposed engineering targets, not established facts about any particular mirror material or display. Record the actual test conditions and revise targets before formal qualification.

### 3.1 Optical fidelity — mandatory

**Question:** Does the assembled surface remain useful as a mirror under the intended lighting and viewing conditions?

Tests:
- Measure front-side and rear-side illuminance at documented positions.
- Record mirror reflectance/transmittance data from the supplier where available; independently measure the assembled system where suitable instruments are available.
- Compare the assembled surface against a conventional reference mirror.
- Inspect at normal and representative oblique viewing angles.
- Evaluate image clarity, ghosting, haze, tint, double reflections and visible display leakage.
- Test at low, nominal and high intended room-light conditions.
- Repeat with the display off, idle and at its proposed maximum operating luminance.

Provisional acceptance:
- Participants can complete predefined reflection tasks without relying on the digital display.
- The physical reflection remains the dominant visual reference in M1-A and M1-B.
- No unacceptable ghost image, distortion, tint or glare is observed in the agreed viewing zone.
- Optical performance is documented as a function of lighting and viewing geometry, not described with a single unqualified claim.

**Beauty/loc-care constraint:** no appearance-evaluation claim is allowed until colour and illumination performance are separately validated. A camera image or display overlay must not be treated as a colour-accurate representation by assumption.

### 3.2 Colour and illumination — mandatory for appearance-related experiments

Test:
- Use a recognised colour target and a calibrated measurement workflow.
- Compare target appearance in the reference mirror environment and assembled environment.
- Record light-source model, spectral/colour-rendering data where available, correlated colour temperature, illuminance and camera exposure if a camera is tested.
- Repeat after warm-up and at more than one illumination level.

Provisional target for any camera/display colour-reproduction experiment: mean colour difference ΔE00 ≤ 3 on the selected target under a defined, controlled condition. This is a research target, not a guarantee of human appearance fidelity or a universal beauty-industry standard.

Pass requires a documented measurement method, reference, calibration status, uncertainty and repeatability. If suitable instruments are unavailable, mark colour fidelity **NOT MEASURED**, not passed.

### 3.3 Display readability and thermal behaviour — mandatory

Test:
- Measure display luminance at multiple brightness settings.
- Assess text and graphic readability at agreed distances and angles.
- Measure contrast with the mirror/display assembly in its real optical configuration.
- Run sustained operation at representative content and maximum intended brightness.
- Record panel, controller and enclosure temperatures; observe throttling, image retention and instability.

Provisional targets:
- Information is readable at the declared operating distance and lighting range.
- The lowest usable brightness is preferred; the display must not overwhelm the reflection.
- No component exceeds its manufacturer's rated operating temperature.
- No thermal throttling, display instability or unsafe surface temperature occurs during the defined endurance run.

A panel specification alone is not proof of assembled-system readability.

### 3.4 Overlay geometry — mandatory for M1-C

M1-C initially uses fixed calibration geometry or known physical reference points. It does not require face or body tracking.

Test:
- Define the physical coordinate frame, display coordinate frame and mirror plane.
- Document calibration procedure and calibration target.
- Measure overlay displacement at the centre and edges of the agreed usable area.
- Repeat after power cycling, display repositioning and controlled changes to viewing geometry.
- Record whether the overlay is mirror-reversed, non-reversed or otherwise transformed; do not silently switch conventions.

Provisional target: static overlay registration error no greater than 10 display pixels RMS at the defined calibration plane. Report pixel pitch, physical error in millimetres, measurement distance and uncertainty. This threshold applies only to the static demonstrator; it does not establish 3D body registration.

Pass requires repeatable calibration, a visible calibration status and a safe fallback to an overlay-free reflection.

### 3.5 Optional tracking — conditional, not a baseline dependency

Only test tracking if a defined interaction cannot be evaluated through a simpler input method.

Before enabling it:
- State the interaction purpose and minimum data needed.
- Prefer synthetic targets, calibration objects or consenting adult test participants.
- Keep raw sensor streams local and temporary.
- Provide a physical or clearly accessible sensor-disable control.
- Do not retain face images, identity templates or inferred emotional states.
- Record sensor field of view, lighting, occlusion, distance and failure conditions.

If hand/body tracking is tested, report:
- Position error in millimetres against a stated reference.
- Jitter and latency distributions, including median and 95th percentile.
- Dropout rate and reacquisition time.
- Performance across tested distances, angles, lighting and occlusion.
- False activation and unintended interaction rates.

No universal pass threshold is assigned before the interaction task and sensor are selected. The test protocol must set task-specific limits before data collection. A successful tracking demonstration is not evidence of identity recognition or health/appearance assessment.

### 3.6 Offline operation and data control — mandatory

Test with external network access physically disconnected:
- Boot and operate the mirror.
- Display local information and local test assets.
- Restart the application and host.
- Confirm the absence of cloud/account dependencies.
- Inspect local processes, services, logs, storage and network interfaces.
- Verify no unexpected outbound connection attempts.
- Verify the application remains usable if optional sensors are disconnected.

Pass:
- M1-A, M1-B and M1-C operate without internet access.
- No personal data is required to start the system.
- No data leaves the device in the offline test.
- Local records, if any, have documented purpose, location, format, retention and deletion procedure.
- A participant can clear the session and disable display/sensing without specialist intervention.

### 3.7 Reliability, recovery and serviceability — mandatory

Test:
- Repeated cold boot and warm restart.
- Display disconnect/reconnect.
- Application crash and restart.
- Loss of optional sensor.
- Power interruption and safe recovery.
- Storage-full behaviour if any persistent data is enabled.
- Restore from a documented backup if configuration or records are retained.

Provisional endurance target: 8 hours of continuous operation under a representative test load, followed by inspection for thermal, display and software faults. This is a demonstrator test, not a lifetime or production reliability claim.

Pass requires no unsafe state, no silent corruption and a documented recovery path. Any failure must be logged with conditions and severity.

## 4. Test equipment and evidence requirements

No specific supplier or model is selected. Choose instruments based on availability, calibration and uncertainty.

| Measurement | Suitable instrument / evidence |
|---|---|
| Illuminance | Calibrated lux meter |
| Display luminance | Luminance meter or validated measurement instrument |
| Colour | Calibrated colorimeter/spectrophotometer and colour target |
| Geometry | Rigid calibration target, ruler/calipers, camera or optical measurement method |
| Temperature | Contact probes or calibrated thermal measurement instrument |
| Timing/latency | High-frame-rate recording or timestamped measurement setup |
| Network behaviour | Local packet capture and interface/process inspection |
| Power | Power meter and component telemetry |
| Reliability | Test log, restart counter and fault records |

For every test record:
- Test ID and requirement ID.
- Date, operator and test-article configuration.
- Hardware identifiers and firmware/software versions.
- Instrument model, calibration status and uncertainty.
- Room conditions, illuminance, geometry and operating mode.
- Procedure, raw observations and processed results.
- Pass/fail/not-measured result and rationale.
- Deviations, defects, limitations and evidence location.

Photographs or video may support a record but do not replace measurement data. Do not capture identifiable people unless the test requires it and informed consent, purpose limitation and retention controls are documented.

## 5. Test matrix and stage gates

| Gate | Test scope | Exit condition |
|---|---|---|
| G0 — Requirements freeze | Use cases, viewing zone, room conditions, safety and privacy | Requirements and provisional thresholds reviewed |
| G1 — Optical bench | Mirror samples, display samples, illumination and reflection | Candidate optical arrangement selected on measured evidence |
| G2 — Display integration | Mounting, luminance, readability and thermal behaviour | Stable, readable display without unacceptable reflection compromise |
| G3 — Static interaction | Calibration, overlay geometry, dismiss/disable behaviour | Repeatable M1-C calibration and safe fallback |
| G4 — Local operation | Offline boot, storage, network inspection and recovery | Core modes operate locally and recoverably |
| G5 — Optional sensing | Only if justified; calibration, accuracy, latency and privacy | Task-specific criteria met or sensing excluded |
| G6 — Demonstrator review | Consolidated results, failures, limitations and reproducibility | Explicit decision: proceed, revise, defer or stop |

A gate may fail. A failed gate is a valid research result and must not be hidden by changing the acceptance threshold after seeing the outcome.

## 6. Proposed test cases

| ID | Test | Mode | Priority |
|---|---|---|---|
| OPT-01 | Reflection comparison with reference mirror | M1-A | Mandatory |
| OPT-02 | Reflection under varied front/rear illumination | M1-A/B | Mandatory |
| OPT-03 | Ghosting, haze, tint and viewing-angle inspection | M1-A/B | Mandatory |
| DSP-01 | Display luminance and readability | M1-B | Mandatory |
| DSP-02 | Sustained thermal operation | M1-B | Mandatory |
| COL-01 | Colour target comparison and measurement uncertainty | M1-A/B | Required before appearance claims |
| GEO-01 | Static overlay calibration and displacement | M1-C | Mandatory |
| GEO-02 | Calibration repeatability after restart/repositioning | M1-C | Mandatory |
| OFF-01 | Full operation with network physically disconnected | M1-A/B/C | Mandatory |
| PRI-01 | Process, storage and network data-flow inspection | All | Mandatory |
| REC-01 | Restart, disconnect and recovery tests | All | Mandatory |
| SEN-01 | Sensor disable and disconnected-sensor fallback | M1-D | Conditional |
| SEN-02 | Tracking accuracy, jitter, latency and dropout | M1-D | Conditional |

## 7. Software and interface architecture

The demonstrator should remain small and separable. Do not introduce a large XR framework, scene database or distributed service before a requirement demands it.

Proposed logical interfaces:

| Interface | Responsibility | Contract |
|---|---|---|
| DisplayOutput | Render static UI and overlays | Resolution, refresh, luminance control, failure state |
| OpticalProfile | Record mirror/display/lighting configuration | Material identifiers, geometry, conditions, measurement provenance |
| CalibrationProfile | Store static coordinate mapping | Coordinate frames, transform, residual error, timestamp, version |
| InputAdapter | Buttons, keyboard or other explicit controls | Events only; no hidden sensor activation |
| SensorAdapter | Optional sensor access | Explicit enable/disable, local-only stream, status and error |
| SessionController | Manage modes and session lifecycle | Start, pause, clear, stop and fallback |
| EvidenceLogger | Store test metadata and faults | No personal content by default; exportable plain records |

These are conceptual contracts, not implemented APIs.

### Guile/Scheme integration direction

- Use Guile for application orchestration, state transitions, configuration and test metadata where practical.
- Keep display and device-specific operations behind native interfaces.
- Evaluate native graphics and input bindings against actual host and display requirements.
- Keep hardware adapters replaceable; avoid binding the application domain to one compositor, sensor vendor or XR runtime.
- Use ordinary files for authoritative configuration and evidence. SQLite may be evaluated as a rebuildable local index, not the sole archive.
- Use Guix for reproducible environment definitions after package and driver feasibility are checked.
- Use Shepherd only where a separately managed service is justified.
- No JavaScript, browser engine, web frontend or cloud API is a required part of M1.

## 8. Privacy, safety and participant control

### 8.1 Default data posture

M1 should collect no personal data in its baseline modes. Calibration data should describe the apparatus, not a person. Test records should identify test configurations and observations without identifying participants.

If a later study involves people:
- Obtain informed, specific and revocable consent.
- Explain what is sensed, why, where it is processed and when it is deleted.
- Provide a non-sensing alternative wherever possible.
- Do not repurpose data for identification, scoring, profiling or model training.
- Define retention and deletion before collection.
- Restrict access and document any export.
- Stop collection immediately when consent is withdrawn.

### 8.2 Physical controls

Provide:
- A physical display-off control.
- A physical power isolation method.
- A visible sensor-active indicator for any optional camera/depth sensor.
- A physical or directly accessible sensor-disable control.
- Safe mounting, protected wiring, ventilation and accessible service points.

A software toggle alone is insufficient for a camera-disable claim if the sensor remains powered and capable of capture.

### 8.3 Kenya data protection

Any future processing of identifiable personal data in Kenya requires a separate legal and operational review against the applicable Data Protection Act and regulations, including lawful basis, transparency, purpose limitation, data minimisation, retention, security and data-subject rights. This engineering note is not legal advice or a compliance certification. A data-protection impact assessment may be required depending on the nature and scale of processing and risk.

## 9. Hardware qualification — no bill of materials

No component is approved by this specification. A candidate may only be promoted after documenting:
- Exact manufacturer, model and revision.
- Optical/electrical/mechanical specifications and tolerances.
- Driver and firmware support on the named GNU/Linux host.
- Licence and provenance for relevant software.
- Availability, repairability, replacement and service access.
- Power, thermal, mounting and electrical safety.
- Local operation and data-flow behaviour.
- Test evidence under the intended configuration.

Evaluate the optical assembly before locking the compute platform. The panel, mirror coating, mounting geometry and lighting determine the useful system envelope; choosing a compute board first would be premature.

## 10. Risks and mitigations

| Risk | Consequence | Mitigation |
|---|---|---|
| Excessive reflectance | Display unreadable | Compare samples and measured lighting configurations |
| Excessive transmission | Reflection loses mirror quality | Keep reflection primary; reject unsuitable optical samples |
| Uneven lighting | Misleading colour/appearance | Controlled high-CRI lighting; no unvalidated appearance claims |
| Display heat | Unsafe or unstable enclosure | Open bench tests, temperature monitoring and ventilation |
| Calibration drift | Misplaced overlays | Fixed geometry, visible calibration state and re-test |
| Sensor overreach | Privacy and trust failure | No sensor by default; purpose-specific enablement |
| Cloud/runtime dependency | Offline failure and data exposure | Offline-first test gate and network inspection |
| Framework lock-in | Hard-to-maintain architecture | Native interfaces and replaceable adapters |
| Scope expansion | M1 never validates | Keep tracking and XR outside minimum pass criteria |

## 11. Deliverables and research records

Expected outputs from the validation programme:

1. Requirements and test-condition record.
2. Optical sample comparison report.
3. Display readability and thermal report.
4. Colour/illumination report, or explicit NOT MEASURED statement.
5. Static overlay calibration report.
6. Offline and network inspection report.
7. Reliability and recovery report.
8. Optional sensor report, if that experiment is separately approved.
9. Hardware candidate register with provenance and qualification status.
10. M1 gate review with proceed/revise/defer/stop decision.

Every report must distinguish measured results, supplier claims, estimates, assumptions and untested hypotheses.

## 12. Decision rules

M1 may proceed to a more complete demonstrator only when:
- The optical assembly passes the agreed reflection-use test.
- The display is readable without overpowering the reflection.
- Static overlay calibration is repeatable.
- Core modes work offline.
- Physical disable and safe recovery controls work.
- No unresolved critical safety or privacy issue remains.

If colour measurement is unavailable, do not make appearance-fidelity claims. If tracking is not justified or fails its task-specific test, omit it. If a two-way mirror assembly cannot meet the reflection requirement, revisit the optical approach rather than weakening the requirement without review.

A successful M1 demonstrator does not establish a released IKAI product, clinical validity, commercial readiness, general-purpose tracking accuracy or suitability for all users and environments.

## 13. Related source-of-record documents

- [IKAI Mirror Technology & Scholarly Research (2026-11-18)](IKAI-MIRROR-TECHNOLOGY-AND-SCHOLARLY-RESEARCH-2026-11-18.md)
- [IKAI Mirror Spatial Research (2026-11-14)](IKAI-MIRROR-SPATIAL-RESEARCH-2026-11-14.md)
- [Voice, Smart Glasses & Distributed Reflective Computing (2026-11-18)](IKAI-VOICE-GLASSES-DISTRIBUTED-ARCHITECTURE-2026-11-18.md)
- [WARENA IKAI MIRROR+ Compute Architecture (2026-11-14)](https://github.com/donfelohke/WARENA/blob/main/docs/IKAI-MIRROR-COMPUTE-ARCHITECTURE-2026-11-14.md)
- [FELOH Corpus IKAI Mirror Cross-Project Alignment (2026-11-18)](https://github.com/donfelohke/feloh-corpus/blob/main/docs/IKAI-MIRROR-CROSS-PROJECT-ALIGNMENT-2026-11-18.md)
- [IKAI Privacy Model](privacy-model.md)
- [WARENA Technology Constitution](https://github.com/donfelohke/WARENA/blob/main/docs/TECHNOLOGY-CONSTITUTION-2026-11-17.md)

---

**Maintainer:** IKAI research  
**Author context:** Felix Lwova / Don Feloh  
**Status:** RESEARCH / PROPOSED VALIDATION PLAN  
**No implementation, procurement, deployment or product claim is made.**
