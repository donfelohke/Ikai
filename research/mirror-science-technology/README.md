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

## Epistemic rules

- Cite the source that supports each material factual claim.
- Prefer primary sources for original evidence and official documentation for implementation details.
- Record publication/version dates, access dates where useful, methods, limitations, and conflicts of interest.
- Do not treat a citation, publication, majority view, or model output as automatic proof.
- Mark missing, inaccessible, contradictory, or unverified evidence explicitly.
- Do not infer causation from correlation without an appropriate design and supporting evidence.
- Preserve dissenting interpretations when they are material and evidence-based.

## Claim status vocabulary

Use the schema in [claim-status.md](claim-status.md). Status labels describe the claim and its current support, not the personal worth or general credibility of its author.

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

Use the project vocabulary: `LIVE`, `PROTOTYPE`, `RESEARCH`, `CONCEPT`, `HISTORICAL`, `SUPERSEDED`, and `UNKNOWN`. State what was actually implemented, observed, tested, and independently reviewed.

## First milestones

- [ ] Approve the research charter and claim-status vocabulary.
- [ ] Build an annotated bibliography with source quality notes.
- [ ] Add one worked research note with explicit claim/source links.
- [ ] Define a reproducibility checklist for computational research.
- [ ] Review privacy, licensing, cultural permissions, and publication risks before releasing datasets.
- [ ] Link implementation claims to commits, tests, and reproducible demonstrations.

## Contributing

Use [research-note-template.md](templates/research-note-template.md) for new investigations and [source-annotation-template.md](templates/source-annotation-template.md) for source records. Keep unsupported claims labelled as unresolved rather than filling gaps with assumptions.
