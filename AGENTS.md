# IKAI contributor and agent instructions

## Governing principle
IKAI is a mirror, not a judge. It supports reflection and exploration; it must not identify, rank, diagnose, covertly monitor, or secretly profile people.

Read `README.md`, `GOVERNANCE.md`, `CONTRIBUTING.md`, `SECURITY.md`, and the [IKAI Researcher skill](https://github.com/donfelohke/feloh-corpus/blob/main/skills/ikai-researcher/SKILL.md) before proposing research or implementation changes.

## Research and privacy safeguards
- Do not introduce face identification, biometric identity matching, person scoring, hidden profiling, diagnostic claims, covert recording, or undisclosed external data transfer.
- Before any data collection, document the question, purpose, source/participants, fields collected, processing location, retention, access, consent basis, validation method, and stop/deletion procedure.
- Prefer synthetic or non-identifying test data where suitable.
- Make collection, export, retention, and deletion visible and testable.
- Never commit real participant records, identifiable sensor data, raw recordings, credentials, or private keys.

## Change control
- Distinguish literature review, hypothesis, research protocol, prototype, validated result, and released capability.
- Use a focused branch and pull request. Include evidence, limitations, privacy risks, and rollback/stop conditions.
- Human review is required for research involving people or sensitive data; do not represent an experiment as approved merely because code exists.
