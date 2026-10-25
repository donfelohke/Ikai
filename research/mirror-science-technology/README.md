# MIRROR — Science & Technology

**Status:** RESEARCH / INITIAL DOCUMENTATION BASELINE  
**Stewardship:** IKAI — Reflexive Compute  
**Principle:** A mirror, not a judge.

MIRROR is a proposed research and documentation framework for observing, investigating, testing, and reflecting on scientific and technological systems. It is not a claim that a working MIRROR platform exists.

## Purpose

- Make claims traceable to sources and methods.
- Separate observation, interpretation, hypothesis, opinion, and unknowns.
- Encourage reproducibility and independent review where feasible.
- Document the social, cultural, environmental, and governance consequences of technology.
- Preserve human agency, privacy, and the ability to inspect, correct, export, or delete personal records.

## Research domains

1. Foundations of science: epistemology, scientific method, measurement, statistics, uncertainty, reproducibility.
2. Free software and computing: GNU/Linux, programming languages, compilers, operating systems, databases, distributed systems.
3. Infrastructure and hardware: networking, embedded systems, edge computing, energy, resilience, repairability.
4. AI and reflective computing: model evaluation, local inference, agentic systems, provenance, human-computer interaction.
5. Embodied knowledge: movement, Laban-related practice, creative computation, skill transmission, situated observation.
6. African knowledge and technology: African histories of science, indigenous knowledge systems, language, archives, and technological self-determination.

These are research categories, not completed literature reviews or claims of comprehensive coverage.

## Research documents

- [Annotated master bibliography](bibliography.md) — curated starter sources, use notes, limitations, and known gaps.
- [Research register](research-register.md) — 30 proposed questions with priority, status, and minimum useful outputs.
- [Review and validation plan](review-plan-2026-10-25.md) — ordered source-review, documentation-validation, reproducibility, and contributor-usability actions; planned work is not marked complete.
- [Study MIR-001: Reproducibility and replicability](studies/MIR-001-reproducibility-terminology.md) — first claim-traceable study, awaiting independent review.
- [Claim status vocabulary](claim-status.md) — editorial labels and evidence rules.
- [Source protocol](source-protocol.md) — source evaluation, citation, and research integrity.
- [Computational reproducibility protocol](reproducibility-protocol.md) — provenance, repeatability, and bounded claims.
- [Research ethics and community knowledge](ethics-and-community-knowledge.md) — proposed safeguards for people, communities, and sensitive knowledge.
- [Research-note template](templates/research-note-template.md) — reusable investigation record.
- [Source-annotation template](templates/source-annotation-template.md) — reusable source record.

## Epistemic rules

- Cite the source that supports each material factual claim.
- Prefer primary sources for original evidence and official documentation for implementation details.
- Record publication/version dates, access dates where useful, methods, limitations, and conflicts of interest.
- Do not treat a citation, publication, majority view, or model output as automatic proof.
- Mark missing, inaccessible, contradictory, or unverified evidence explicitly.
- Do not infer causation from correlation without an appropriate design and supporting evidence.
- Preserve dissenting interpretations when they are material and evidence-based.

## Research lifecycle

1. State a question and why it matters.
2. Define scope, terms, exclusions, and ethical constraints.
3. Inventory and evaluate sources.
4. Record claims with source-level provenance.
5. Describe methods and reproduce analyses where feasible.
6. Document findings, alternatives, limitations, and unresolved questions.
7. Review changes and publish with a version history.
8. Correct or supersede records transparently.

## Boundaries

MIRROR must not become a mechanism for covert surveillance, identity inference, face identification, diagnosis, person scoring, ranking, or hidden profiling. Any collection of data about people requires a defined purpose, data minimisation, appropriate consent or other valid basis, retention limits, security, and meaningful participant control.

## Relationship to IKAI and WARENA

IKAI is the reflective-compute research domain. WARENA supports inspectable, maintainable, reproducible computing systems. MIRROR documentation can specify research methods and evidence requirements; it does not imply that any implementation exists or has passed evaluation.

## Maturity labels

Use the project vocabulary: LIVE, PROTOTYPE, RESEARCH, CONCEPT, HISTORICAL, SUPERSEDED, and UNKNOWN. State what was actually implemented, observed, tested, and independently reviewed.

## Initial milestones

- [x] Create the initial research charter and domain taxonomy.
- [x] Add a starter bibliography with source notes and explicit gaps.
- [x] Establish a 30-question research register and first-study sequence.
- [x] Define claim labels, source protocol, reproducibility protocol, and ethics safeguards.
- [ ] Verify each source and claim in the context of the first selected research question.
- [ ] Complete a worked research note with claim-to-source links and reviewer feedback.
- [ ] Run and document one bounded computational reproducibility experiment.
- [ ] Review privacy, licensing, cultural permissions, and publication risks before releasing datasets.
- [ ] Link implementation claims to commits, tests, and reproducible demonstrations.

Checked items mean the documentation files were created on this branch; they do not mean the research itself is complete or independently validated.

## Contributing

Use the research-note template for new investigations and the source-annotation template for source records. Keep unsupported claims labelled as unresolved rather than filling gaps with assumptions.
