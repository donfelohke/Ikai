# Research Note MIR-001 — Reproducibility, Replicability, and Evidence Boundaries

- **Status:** AWAITING_REVIEW
- **Research domain:** Research integrity / reproducible computing
- **Created:** 2026-10-25
- **Review status:** NOT INDEPENDENTLY REVIEWED
- **Question:** How should MIRROR distinguish computational reproducibility from replication when documenting research claims?

## Executive finding

For this note, MIRROR adopts the terminology used by the National Academies of Sciences, Engineering, and Medicine (NASEM, 2019): computational reproducibility concerns obtaining consistent results from the same input data, computational steps, methods, code, and analysis conditions; replicability concerns consistent results across studies aimed at the same scientific question where each study obtains its own data. NASEM explicitly notes that terminology differs across disciplines, so a research note must state its definition rather than assume a universal usage. [Source S1, Chapter 3, pp. 42–46](https://www.nationalacademies.org/read/25303/chapter/6).

This is a terminology and documentation finding, not an experiment. No MIRROR software, package build, or scientific result was executed or independently reproduced in this study.

## Scope

**Included:** terminology, source traceability, and implications for MIRROR research records.

**Excluded:** a systematic review of every disciplinary definition; a claim about the frequency of irreproducible results; testing a specific Guix build; assessment of any AI model; and any claim that one reproducibility vocabulary is universally adopted.

## Method

1. Located the National Academies' 2019 consensus report and opened its chapter on understanding reproducibility and replicability.
2. Checked the report's explicit definitions and discussion of cross-disciplinary terminology.
3. Compared those definitions with the FAIR principles' emphasis on provenance and reusable research objects.
4. Derived documentation recommendations, clearly separating the source's statements from MIRROR's editorial choices.

This was a bounded source review, not a systematic literature review. Search strategy was limited; no formal inclusion protocol, dual screening, or exhaustive source search was performed.

## Claim register

| ID | Claim | Status | Evidence | Limitation |
|---|---|---|---|---|
| C1 | NASEM's 2019 report defines computational reproducibility using the same input data, computational steps, methods, code, and conditions of analysis. | VERIFIED against source text | S1, Chapter 3, conclusion 3-1, pp. 45–46 | This is the report's chosen definition, not a universal definition across all disciplines. |
| C2 | In the NASEM report, replicability involves consistent results across studies aimed at the same question, with each study obtaining its own data. | VERIFIED against source text | S1, Chapter 3, conclusion 3-1, pp. 45–46 | Consistency must be interpreted with measurement uncertainty and the design of the field in view. |
| C3 | Different disciplines have used the terms reproducibility and replicability inconsistently, sometimes in opposing ways. | VERIFIED against source text | S1, Chapter 3, pp. 42–45 | The report's account does not exhaust every later or current disciplinary convention. |
| C4 | Research data and analysis workflows benefit from clear metadata, provenance, and reuse information. | ESTABLISHED as a documented principle | S2, FAIR Guiding Principles (2016) | FAIR is a guiding principles paper, not proof that a particular MIRROR record is FAIR or reusable. |
| C5 | MIRROR research notes should name the definition of reproducibility they use and record exact inputs, environment, methods, outputs, and limitations. | INTERPRETATION / DESIGN RECOMMENDATION | Derived from S1 and S2 | Proposed editorial requirement; it has not yet been usability-tested or independently evaluated. |
| C6 | A successful computational reproduction proves the original scientific conclusion is true. | NOT SUPPORTED; reject as overclaim | S1 distinguishes checking computations from replication across new data and contexts | Reproducing an analysis can confirm consistency of the computation without validating the assumptions, data quality, causal interpretation, or generalisability. |

## Sources

### S1 — Primary source for the definitions used here

National Academies of Sciences, Engineering, and Medicine. (2019). *Reproducibility and Replicability in Science*. Washington, DC: The National Academies Press. https://doi.org/10.17226/25303

Relevant chapter: “3 Understanding Reproducibility and Replicability,” especially the discussion of inconsistent terminology and conclusion 3-1, pp. 42–46.  
Direct chapter: https://www.nationalacademies.org/read/25303/chapter/6

**Source type:** Consensus study report.  
**What was checked:** Online chapter text and the stated definitions.  
**What was not checked:** Every reference cited by the report or the full literature underlying its conclusions.

### S2 — Research-data stewardship principles

Wilkinson, M. D. et al. (2016). “The FAIR Guiding Principles for scientific data management and stewardship.” *Scientific Data*, 3, 160018. https://doi.org/10.1038/sdata.2016.18  
Open full text: https://pmc.ncbi.nlm.nih.gov/articles/PMC4792175/

**Source type:** Peer-reviewed principles paper.  
**Relevance:** Findability, accessibility, interoperability, reusability, metadata, provenance, and licence information.  
**Limit:** The principles do not prescribe a single implementation and do not override privacy or access restrictions.

## Implications for MIRROR

Every computational research record should distinguish at least four different assertions:

1. **Artifacts are available:** source code, data, methods, and environment details are sufficiently described or accessible for checking.
2. **A reproduction was attempted:** someone executed the specified process.
3. **The reproduction matched:** the observed outputs matched a declared comparison criterion under recorded conditions.
4. **The scientific conclusion is supported:** a separate judgement considers measurement quality, assumptions, study design, uncertainty, alternative explanations, and whether new-data replication or generalisation is relevant.

These are different claims and must not be collapsed into one badge such as “verified.”

## Recommended record fields

- Definition of reproducibility or replication used, with source.
- Research question and claim under test.
- Input dataset identifiers and integrity checks.
- Source repository and exact commit.
- Runtime environment, dependency versions, commands, and configuration.
- Expected result and comparison rule.
- Actual result, logs, and differences.
- New-data replication status, if applicable.
- Known limitations and unresolved uncertainty.
- Reviewer and date.

## Counterevidence and limitations

- NASEM itself documents conflicting terminology; another field or venue may use the terms differently.
- Data and code availability are prerequisites for some forms of computational checking, but availability alone is not a completed reproduction.
- A reproduced computation can faithfully repeat an error, flawed assumption, biased sample, or inappropriate statistical analysis.
- Replication results may differ for legitimate reasons such as measurement uncertainty, population differences, context, or methodological variation. A mismatch should be investigated rather than automatically treated as misconduct or proof that the original study was false.
- The FAIR principles are not an ethics approval or a guarantee that a data object is safe to share.

## Conclusion

**Supported within this note's scope:** MIRROR should state the disciplinary definition it adopts, preserve research provenance, and separate artifact availability, an attempted reproduction, a matching result, and support for a scientific conclusion.

**Not established:** that the proposed MIRROR documentation process has been independently reviewed, that a real computation has been reproduced, or that the entire bibliography is exhaustive.

## Next actions

- [ ] Independent reviewer checks C1–C4 against the cited source passages.
- [ ] Test whether a new contributor can complete the reproducibility record without extra verbal instructions.
- [ ] Apply this schema to one bounded software/build experiment.
- [ ] Record revisions and reviewer response before changing status from AWAITING_REVIEW.
