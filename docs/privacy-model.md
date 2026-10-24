# IKAI Privacy Model

## Default position

Prefer local processing, data minimisation, short retention, transparent operation, and participant control. Do not collect data merely because a sensor can produce it.

## Required record for each prototype

- **Purpose:** the specific question or interaction the data supports.
- **Data inventory:** raw inputs, derived features, outputs, logs, and metadata.
- **Processing location:** device, local network, or external service.
- **Access:** who or what can read each data type.
- **Persistence:** whether data is stored, where, for how long, and in what form.
- **Export:** how a participant can inspect or obtain their data.
- **Deletion:** how raw and derived data are deleted, including caches and backups where applicable.
- **Consent and withdrawal:** what is explained before collection and how a participant can stop.
- **Failure behaviour:** what happens if storage, sensors, network, or deletion fails.
- **Verification:** tests or inspections that support each privacy claim.

## Data minimisation

Use synthetic or aggregate data when possible. Avoid identifying attributes and do not infer identity, health status, emotion, personality, or capability from movement or sensor data.

## External services

Any proposal to transmit data outside the local device or network requires an explicit purpose, documented data-flow diagram, retention terms, access model, and review before implementation.

## Acceptance criteria

A prototype should not be described as privacy-preserving until the relevant data flows, access boundaries, retention, and deletion behaviour have been tested. A policy document alone is not an implementation audit.
