# MIRROR Research Update Plan — 2026-10-25

**Status:** RESEARCH / REVIEW PLAN  
**Scope:** Follow-up to MIRROR research baseline in PR #5  
**Evidence boundary:** This document records a repository review and planned verification. It does not claim an independent scientific review, completed experiment, or comprehensive literature search.

## Repository review findings

The current MIRROR baseline contains a charter, six-domain taxonomy, starter bibliography, 30-question register, claim-status vocabulary, source protocol, reproducibility protocol, ethics guidance, templates, and study MIR-001.

The repository correctly identifies MIR-001 as `AWAITING_REVIEW` and explicitly states that no MIRROR software or scientific result was executed or independently reproduced. Preserve that status until review evidence is recorded.

### Findings to carry forward

1. **Scope is appropriately bounded.** MIR-001 is a terminology/source review, not a systematic review or computational experiment.
2. **Claim separation is useful.** The study distinguishes source-backed definitions from editorial recommendations and rejects the claim that reproducing a computation proves the scientific conclusion.
3. **Bibliography gaps are explicit.** Laban/Bartenieff and reflective-HCI entries are discovery tasks, not completed references. Do not replace these placeholders with guessed citations.
4. **Evidence labels need operational discipline.** Apply labels to individual claims and record the exact source passage, verification date, and reviewer. A repository status label is not a scientific quality score.
5. **The next high-value work is verification, not expansion for its own sake.** Check the exact claims in MIR-001, then run one bounded and safe reproducibility exercise.
6. **No implementation claims are warranted.** A proposed protocol, README, or Git commit does not prove a working reflective-compute system or tested privacy controls.

## Ordered action plan

### P0 — Independent source review of MIR-001

- [ ] A reviewer other than the original author checks claims C1–C4 against the cited NASEM and FAIR source passages.
- [ ] Record exact chapter/section/page or paragraph anchors for each claim.
- [ ] Check whether paraphrases preserve the source's qualifications and disciplinary terminology.
- [ ] Record any disagreement, corrections, inaccessible material, or changes required.
- [ ] Do not mark the study reviewed until a reviewer identity/role, date, and review record are present.

**Acceptance criterion:** Each material factual claim has a traceable source location and a recorded review outcome; unresolved items remain explicitly unresolved.

### P0 — Validate repository documentation

- [ ] Check every relative Markdown link in the research directory.
- [ ] Verify bibliography metadata against publisher, DOI, official institution, or primary-source pages.
- [ ] Check that cited versions and dates match the actual source.
- [ ] Confirm templates do not imply consent, legal compliance, or research approval automatically.
- [ ] Record commands, outputs, environment, and date for any automated checks.

**Acceptance criterion:** Link and metadata checks are documented with reproducible steps and results; failures are reported, not silently omitted.

### P1 — Bounded computational reproducibility experiment

- [ ] Select a small, safe, openly licensed build or computation with stable source inputs.
- [ ] State the question, expected output, comparison rule, platform, and exclusions before execution.
- [ ] Record repository URL, exact commit, dependency inputs, tool versions, environment, commands, logs, and output hashes where appropriate.
- [ ] Run once from the documented environment and repeat from a clean state or second environment where feasible.
- [ ] Explain mismatches and limitations; do not equate matching outputs with correctness or security.
- [ ] Publish only artefacts whose licences and data-handling conditions permit redistribution.

**Acceptance criterion:** Another maintainer can follow the record and report whether the declared comparison criterion was met. If the experiment cannot be run, document the blocker and leave the result unknown.

### P1 — Source discovery for reflective HCI and movement research

- [ ] Find primary and scholarly sources for reflective design, participatory design, user agency, and privacy-preserving interaction.
- [ ] Find primary texts and credible scholarly histories for Laban Movement Analysis and Bartenieff Fundamentals.
- [ ] Separate historical description, practitioner vocabulary, empirical measurement, and clinical claims.
- [ ] Annotate source limitations, licensing, context, and relevance to a specific research question.

**Acceptance criterion:** Add only sources whose bibliographic details and relevant passages have been checked. Until then, keep the source-discovery gaps visible.

### P1 — Contributor usability trial

- [ ] Ask a contributor unfamiliar with the project to complete the source-annotation and research-note templates.
- [ ] Record where instructions are ambiguous, what fields cannot be completed, and what extra verbal guidance was needed.
- [ ] Revise templates based on observed difficulties; identify the trial as informal unless a suitable study design is used.

**Acceptance criterion:** A documented walkthrough exists. Do not describe one informal walkthrough as validated usability research.

## Evidence and status rules

Use the following distinctions in all updates:

- **Repository fact:** directly visible in a file, commit, check, or pull-request record.
- **Source-verified claim:** checked against the cited source at a recorded location.
- **Interpretation/recommendation:** reasoned proposal, not a source quotation or experimental result.
- **Experiment attempted:** a documented execution took place.
- **Experiment reproduced:** the declared output criterion was met under recorded conditions.
- **Unknown / blocked:** evidence is missing, inaccessible, contradictory, or not yet collected.

Do not change MIR-001 from `AWAITING_REVIEW` to a completed status solely because this plan was added.

## Change log

| Date | Change | Basis |
|---|---|---|
| 2026-10-25 | Added ordered review and validation plan | Review of the MIRROR research files and MIR-001 draft in the PR branch |

## Related records

- [MIRROR research index](README.md)
- [Research register](research-register.md)
- [MIR-001 study](studies/MIR-001-reproducibility-terminology.md)
- [Annotated bibliography](bibliography.md)
