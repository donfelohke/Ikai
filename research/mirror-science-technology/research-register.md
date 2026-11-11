# MIRROR Research Register

**Status:** RESEARCH PLANNING REGISTER  
**Last updated:** 2026-10-25  
**Purpose:** Track questions, evidence needs, outputs, and review status. This is a roadmap, not a report of completed research.

## Status vocabulary

- **PROPOSED:** question identified; research not yet conducted.
- **SCOPING:** source inventory and boundaries being defined.
- **IN_PROGRESS:** evidence collection or analysis is underway.
- **AWAITING_REVIEW:** draft exists and needs review.
- **SUPPORTED:** a documented answer is supported within a stated scope.
- **DISPUTED:** credible evidence or interpretations materially conflict.
- **BLOCKED:** progress depends on access, permissions, data, or a decision.
- **CLOSED:** work concluded with rationale and links to outputs.
- **SUPERSEDED:** replaced by a newer question or record.

## Priority model

- **P0 — Foundation:** needed for research integrity, ethics, or reproducibility.
- **P1 — First studies:** high-value studies that test and establish methods.
- **P2 — Specialist:** domain-specific work following foundational tasks.
- **P3 — Exploratory:** useful questions without immediate dependencies.

Priority is a sequencing decision, not a measure of scientific importance.

## Questions

| ID | Domain | Research question | Priority | Status | Minimum useful output |
|---|---|---|---|---|---|
| MIR-001 | Research integrity | How should claims, sources, uncertainty, corrections, and disagreements be represented consistently? | P0 | AWAITING_REVIEW | [Worked claim-traceable note](studies/MIR-001-reproducibility-terminology.md) |
| MIR-002 | Reproducibility | What information is required to rerun a computational result independently? | P0 | PROPOSED | Checklist and experiment record |
| MIR-003 | Source evaluation | How can primary evidence be distinguished from commentary, synthesis, and AI-generated summaries? | P0 | PROPOSED | Source-evaluation rubric |
| MIR-004 | Data governance | How can data be reusable without exposing sensitive or restricted information? | P0 | PROPOSED | Access and permissions policy |
| MIR-005 | AI accountability | Which controls prevent reflective systems becoming hidden scoring or surveillance systems? | P0 | PROPOSED | Threat model and acceptance tests |
| MIR-006 | Scientific method | How do disciplines operationalise evidence, testing, explanation, and uncertainty? | P1 | PROPOSED | Comparative methods review |
| MIR-007 | Statistics | Which common statistical errors produce overconfident claims? | P1 | PROPOSED | Annotated guide with examples |
| MIR-008 | Causal inference | What evidence supports causal claims rather than association? | P1 | PROPOSED | Causal-claim checklist |
| MIR-009 | Open science | Which open-science practices improve transparency and reuse, and what trade-offs arise? | P1 | PROPOSED | Evidence review |
| MIR-010 | Free software | What distinguishes free software, open source, source-available, and proprietary systems? | P1 | PROPOSED | Definitions and licence decision tree |
| MIR-011 | Reproducible computing | Under which conditions can a Guix-based build be reproduced? | P1 | PROPOSED | Bounded build experiment |
| MIR-012 | Software supply chain | What can reproducible builds establish, and what security properties remain unproven? | P1 | PROPOSED | Threat-model comparison |
| MIR-013 | Local-first systems | How should offline capability, synchronisation, conflict resolution, and data ownership be evaluated? | P1 | PROPOSED | Criteria and test plan |
| MIR-014 | AI evaluation | How should model capability claims be tested against a defined task and baseline? | P1 | PROPOSED | Evaluation protocol |
| MIR-015 | AI risk | How can the NIST AI RMF be applied proportionately to a local-first prototype? | P1 | PROPOSED | Framework mapping with gaps |
| MIR-016 | HCI | What evidence supports reflective interfaces without scores or diagnoses? | P1 | PROPOSED | Literature review and study design |
| MIR-017 | Movement | Which Laban/Bartenieff concepts are descriptive vocabularies and which claims have empirical validation? | P1 | PROPOSED | Source map and claim review |
| MIR-018 | African science history | Which African-authored and institutionally grounded sources document scientific and technical traditions? | P1 | SCOPING | Annotated regional bibliography |
| MIR-019 | Kenyan technology | What primary data describe Kenya's research, computing, connectivity, energy, and technology infrastructure? | P1 | PROPOSED | Country-specific source map |
| MIR-020 | Community knowledge | Which protocols protect community authority, attribution preferences, restricted knowledge, and consent? | P0 | PROPOSED | Ethics and permission checklist |
| MIR-021 | Documentation | Which repository structures and metadata support long-term maintenance and cross-linking? | P1 | PROPOSED | Schema comparison and trial |
| MIR-022 | Digital preservation | Which formats, checksums, replicas, and restore tests support durable preservation? | P1 | PROPOSED | Preservation protocol |
| MIR-023 | Communication | How should facts, interpretations, hypotheses, opinions, and unknowns be presented clearly? | P1 | PROPOSED | Style guide and usability test |
| MIR-024 | Publishing | Which licensing and attribution choices support reuse while respecting privacy and third-party rights? | P1 | PROPOSED | Publishing decision guide |
| MIR-025 | Historical archives | How should provenance, conflicting testimony, translation, and archival gaps be represented? | P2 | PROPOSED | Historical-source template |
| MIR-026 | Embodied computation | What movement data can be measured reliably, and what should remain qualitative or participant-interpreted? | P2 | PROPOSED | Measurement validity review |
| MIR-027 | Resilient infrastructure | How should offline-first networks be tested for recovery, security, performance, and maintainability? | P2 | PROPOSED | Scenario-based test matrix |
| MIR-028 | Research economics | Which costs and dependency risks matter when comparing local-first and cloud-dependent systems? | P2 | PROPOSED | Transparent cost model |
| MIR-029 | Negative results | How should failed replications, negative results, and contradictory sources be retained? | P1 | PROPOSED | Correction and negative-results policy |
| MIR-030 | Stewardship | Which governance and handover practices help a research corpus outlive its founder? | P1 | PROPOSED | Succession and maintainer guide |

## First study sequence

### Study 1 — Claim and source provenance (MIR-001, MIR-003)
**Question:** Can a reader trace every material conclusion in a short research note to its supporting source and method?

**Method:** Choose a bounded technical question; identify primary and secondary sources; build a claim-source table; ask a second reviewer to trace conclusions; record unsupported or ambiguous claims.

**Success criteria:** Material factual claims have relevant sources; inference and opinion are labelled; inaccessible evidence is disclosed; disagreement and gaps remain visible.

### Study 2 — Reproducibility record (MIR-002, MIR-011)
**Question:** Can another maintainer reproduce one selected computation or build using the recorded inputs and environment?

**Method:** Select a safe open-source target; record commit, dependencies, platform, commands, outputs, failures, and environment; repeat from a clean state; compare outputs.

**Success criteria:** A second attempt is documented; differences are explained or unresolved; conclusions do not extend beyond tested conditions.

### Study 3 — Reflective-system boundaries (MIR-005, MIR-016)
**Question:** Can a reflective interface provide user-directed feedback without inferring identity, assigning scores, diagnosing, or covertly profiling?

**Method:** Start with data-flow and threat models; use synthetic or explicitly consented data; test retention, export, deletion, local processing, and user control; obtain appropriate ethics review before studies involving people.

**Success criteria:** Data flows and limits are documented; prohibited behaviours have acceptance tests; user interpretation is distinct from system inference.

### Study 4 — African and Kenyan source landscape (MIR-018, MIR-019, MIR-020)
**Question:** Which sources support specific claims about African and Kenyan scientific and technical histories, and under what conditions may they be used?

**Method:** Build a region- and period-aware inventory; prioritise African scholarship, primary records, institutional archives, and local research; record language, translation, provenance, permissions, and gaps.

**Success criteria:** Claims are geographically and historically bounded; sources are attributed; archival silence is not treated as proof of absence; restricted knowledge is not published without permission.

## Maintenance rule

Create a research note and source annotations before marking a question IN_PROGRESS. Update status only when work actually occurs. Link final outputs and record reasons for closure or supersession.
