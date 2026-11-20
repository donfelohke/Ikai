# IKAI Research Knowledge Base

**Status: RESEARCH / DOCUMENTATION BASELINE.** IKAI is reflective-compute research, not a released product. This index does not claim that a working mirror, sensor integration, or evaluation method exists.

## IKAI Mirror research track

- [Mirror M1 Engineering Validation Specification (2026-11-18)](IKAI-MIRROR-M1-ENGINEERING-VALIDATION-2026-11-18.md) — proposed measurable optical, colour/illumination, display/thermal, static-overlay, offline, reliability, privacy and optional-sensing tests; stage gates and evidence requirements. Proposed thresholds are provisional; no implementation or procurement is claimed.

- [Mirror Technology & Scholarly Research (2026-11-18)](IKAI-MIRROR-TECHNOLOGY-AND-SCHOLARLY-RESEARCH-2026-11-18.md) — five engineering approaches, optical trade-offs, hardware stack, essential scholarly reading (smart-mirror, AR mirrors, embodiment/movement, data protection), research modules, proposed M1 prototype, and architectural position (Mirror / Glass / Space).
- [Voice, Smart Glasses & Distributed Reflective Computing (2026-11-18)](IKAI-VOICE-GLASSES-DISTRIBUTED-ARCHITECTURE-2026-11-18.md) — both voice-only and visual AR wearables; hybrid intelligence; first-class display; contracts, hardware qualification, Scheme integration, privacy threat model and staged MVP.

- [Spatial-computing research (2026-11-14; source clarification 2026-11-20)](IKAI-MIRROR-SPATIAL-RESEARCH-2026-11-14.md) — reflective surface, spatial registration, GNU/MAVERIK and DEVA3 source clarification, participant authority and research gates.
- [WARENA spatial/XR/opt-in AI architecture (2026-11-20)](https://github.com/donfelohke/WARENA/blob/main/docs/SPATIAL-COMPUTING-XR-AI-ARCHITECTURE-2026-11-20.md) — infrastructure/runtime source of record; IKAI retains participant-facing and privacy authority.
- [Reflective-computing research alignment (2026-11-18)](REFLECTIVE-COMPUTING-RESEARCH-ALIGNMENT-2026-11.md) — seven-dimension design critique, methodological limits, participant-directed reflection and movement-notation boundaries.

## Current portfolio boundary

- [Portfolio Boundary (2026-10-31)](PORTFOLIO-BOUNDARY-2026-10-31.md) — IKAI's separation from commercial products and the GENJE launch campaign.

## Reading path

1. Read the [research agenda](research-agenda.md) before proposing an experiment.
2. Apply the [privacy model](privacy-model.md) before collecting or processing data.
3. Define the research question, participant control, minimum data, success/failure criteria, and deletion path.
4. Use synthetic data or a local isolated setup where feasible.
5. Record implementation and observations separately from interpretation.
6. Publish limitations and negative results; do not overstate findings.

## Research

- [NVIDIA XR AI Architecture Comparative Study (2026-11-18)](NVIDIA-XR-AI-ARCHITECTURE-COMPARATIVE-STUDY-2026-11-18.md) — industrial architecture reference; no NVIDIA dependency or deployment selected.
 domains

| Domain | Questions to document | Evidence required |
|---|---|---|
| Reflective interfaces | What can a participant inspect and control? | Interaction specification and observed tests |
| Embodied practice | How is movement contextualised without reducing a person to a profile? | Method, context, consent, limitations |
| Local computation | What data stays on-device or local network? | Data-flow inspection and external-traffic tests |
| Sensor experiments | What is collected and why? | Inventory, access model, retention and deletion tests |
| Participant-directed records | Can participants inspect/export/delete their data? | Demonstrated workflows and failure cases |
| Optical mirror systems | How does reflection quality interact with display and sensing? | Optical measurements, lighting control, overlay registration |

## Non-negotiable boundaries

- No face identification, biometric identity matching, covert surveillance, diagnosis, person scoring, or hidden profiling.
- Do not infer health, emotion, personality, identity, or capability from movement/sensor data.
- External processing requires an explicit purpose and reviewed data-flow, retention, and access model.
- Do not describe a prototype as privacy-preserving until relevant data flows and controls have been tested.
- For beauty/loc-care applications, optical reflection remains the primary visual reference; digital content must not compromise natural appearance assessment.

## Experiment evidence record

For each experiment record the question, status/date, source commit, hardware/software, data type and source, consent basis where relevant, processing location, procedure, success/failure criteria, observed results, alternative explanations, limitations, privacy review, reproduction steps, and deletion confirmation.

A demonstration is not validation. A policy is not an implementation audit. Treat hypotheses and interpretation as such, and distinguish them from observations.

## Canonical identity and technology policy — 2026-11-17

- [IKAI Name Note](IKAI-NAME-NOTE.md) — IKAI is a Turkana female name meaning “home.”
- [Identity and Native Technology Boundary](IDENTITY-AND-NATIVE-TECHNOLOGY-BOUNDARY-2026-11-17.md) — JavaScript prohibition, web-technology exclusion and native/local-first research direction.
- [WARENA Technology Constitution](https://github.com/donfelohke/WARENA/blob/main/docs/TECHNOLOGY-CONSTITUTION-2026-11-17.md) — governing infrastructure policy.
