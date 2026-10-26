# IKAI Research Knowledge Base

**Status: RESEARCH / DOCUMENTATION BASELINE.** IKAI is reflective-compute research, not a released product. This index does not claim that a working mirror, sensor integration, or evaluation method exists.

## Reading path

1. Read the [research agenda](research-agenda.md) before proposing an experiment.
2. Apply the [privacy model](privacy-model.md) before collecting or processing data.
3. Define the research question, participant control, minimum data, success/failure criteria, and deletion path.
4. Use synthetic data or a local isolated setup where feasible.
5. Record implementation and observations separately from interpretation.
6. Publish limitations and negative results; do not overstate findings.

## Research domains

| Domain | Questions to document | Evidence required |
|---|---|---|
| Reflective interfaces | What can a participant inspect and control? | Interaction specification and observed tests |
| Embodied practice | How is movement contextualised without reducing a person to a profile? | Method, context, consent, limitations |
| Local computation | What data stays on-device or local network? | Data-flow inspection and external-traffic tests |
| Sensor experiments | What is collected and why? | Inventory, access model, retention and deletion tests |
| Participant-directed records | Can participants inspect/export/delete their data? | Demonstrated workflows and failure cases |

## Non-negotiable boundaries

- No face identification, biometric identity matching, covert surveillance, diagnosis, person scoring, or hidden profiling.
- Do not infer health, emotion, personality, identity, or capability from movement/sensor data.
- External processing requires an explicit purpose and reviewed data-flow, retention, and access model.
- Do not describe a prototype as privacy-preserving until relevant data flows and controls have been tested.

## Experiment evidence record

For each experiment record the question, status/date, source commit, hardware/software, data type and source, consent basis where relevant, processing location, procedure, success/failure criteria, observed results, alternative explanations, limitations, privacy review, reproduction steps, and deletion confirmation.

A demonstration is not validation. A policy is not an implementation audit. Treat hypotheses and interpretation as such, and distinguish them from observations.
