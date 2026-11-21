---
title: Privacy and Participant Authority
---
# Privacy and participant authority

**Status: GOVERNING DESIGN REQUIREMENTS.** A policy document alone does not prove implementation privacy. Data flows, permissions, retention and deletion must be tested in the actual system.

## Core rule

A camera, microphone or other sensor being present does not grant permission to collect data. The participant must understand the purpose and retain meaningful control.

## Before collection

Document the research question and intended benefit; participants or data source; exact fields and media collected; why each field is necessary; processing location and every external transfer; who can access the data; retention period and deletion method; consent, opt-out and withdrawal path; validation and stop conditions.

Prefer synthetic or non-identifying data where appropriate.

## Technical controls

- Local processing by default where practical.
- No default cloud profile.
- Visible sensor and recording state.
- Physical shutter or equivalent hardware control where feasible.
- Purpose-limited permissions.
- Separate temporary buffers from persistent records.
- Minimal retention and verified deletion.
- User-directed export and access.
- No undisclosed telemetry or external transfer.
- Useful operation without camera input where feasible.

## Prohibited directions

IKAI must not introduce face identification, biometric identity matching, person scoring, ranking, diagnosis, covert surveillance, hidden profiling or inference of sensitive traits from movement or appearance.

## Human authority

The system may present information, options or transformations. The participant decides what to accept, retain, share or act upon. Computational interpretation does not confer authority.

## Related records

- [Privacy model](../../docs/privacy-model.md)
- [Governance](../../GOVERNANCE.md)
- [Evidence and release criteria](../../docs/research-evidence-and-release-criteria.md)
