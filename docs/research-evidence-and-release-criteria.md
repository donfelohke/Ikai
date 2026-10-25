# IKAI Research Evidence and Release Criteria

**Status:** Research governance proposal  
**Principle:** Mirror, not judge.

## Purpose
IKAI explores reflective interfaces and local-first computation. Public communication must distinguish the research question, design concept, implemented prototype and tested capability.

## Non-negotiable boundaries
- No face identification or biometric identity matching.
- No diagnosis or clinical-assessment claims.
- No person scoring, ranking, hidden profiling or covert surveillance.
- No unannounced cloud profile or undisclosed external processing.
- Collect the minimum data needed for a stated purpose.
- Prefer local processing, short retention, transparent data flows and participant control.
- Do not infer identity, intent, health, character or worth from movement or interaction data.

## Research record
For each experiment, record the research question, intended benefit, hypothesis (labelled as such), sources, system boundary, data collected, processing location, retention, consent and participant control where relevant, implementation status and version, method and environment, tests and observations, limitations and failure cases, unresolved questions, and publication/retention decision.

## Status vocabulary
- PROPOSED — design idea only.
- RESEARCH — question or method under investigation.
- PROTOTYPE — implementation exists but is not a general product.
- LIVE — publicly available and verified for the stated use.
- SUPERSEDED, HISTORICAL, ABANDONED or UNKNOWN — preserve an honest record.

## Release gate
Before describing a feature publicly, verify its implementation in source, define the supported environment, run relevant tests, document limitations and ensure the privacy model matches actual data flows. A passing unit test does not establish human benefit, clinical validity or broad safety.

## Public communication
Use “explores”, “researches” and “prototype” where appropriate. Do not claim validated outcomes, production readiness or participant benefit without evidence. A local-first design does not guarantee privacy if logs, backups, dependencies or external services remain unassessed.

## Review checklist
- [ ] Research question and status are explicit.
- [ ] Data flow and retention are documented.
- [ ] Participant consent and control are addressed where relevant.
- [ ] Claims match implementation and test evidence.
- [ ] Limitations and failure modes are visible.
- [ ] No prohibited identification, diagnosis, scoring or covert profiling is introduced.
- [ ] Changes are reviewed through a branch and pull request.
