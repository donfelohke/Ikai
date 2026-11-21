# Claim Status and Evidence Labels

This vocabulary is a practical editorial convention, not a universal scientific ranking system. Apply labels to individual claims and include the reason for the label.

| Label | Meaning | Minimum documentation |
|---|---|---|
| `VERIFIED` | The claim has been checked against directly inspectable evidence appropriate to its scope. | Evidence, verification method, date, and limits. |
| `ESTABLISHED` | A strong body of relevant evidence or authoritative technical material supports the claim. | Key sources, scope, and material limitations or dissent. |
| `SUPPORTED` | Available evidence supports the claim but is incomplete or context-limited. | Sources and what remains uncertain. |
| `INTERPRETATION` | An analytical reading or synthesis of evidence. | Underlying evidence and plausible alternatives. |
| `HYPOTHESIS` | A proposition awaiting adequate testing. | Rationale and a possible way to test or falsify it. |
| `OPINION` | An attributed value judgment, preference, or personal assessment. | Author/attribution and distinction from factual claims. |
| `DISPUTED` | Credible sources or methods materially conflict. | Competing positions and evidence on each side. |
| `UNKNOWN` | Evidence is absent, inaccessible, insufficient, or not yet evaluated. | What is missing and the next verification step. |
| `SUPERSEDED` | A newer record replaces this claim or interpretation. | Link to the replacement and reason for change. |

## Rules

1. Never label a claim VERIFIED merely because it appears in a published source.
2. Distinguish source existence from the truth of the source's statements.
3. Use the narrowest defensible wording; do not generalise beyond the evidence.
4. Record negative findings and failed replications, not only successful outcomes.
5. Keep a dated revision trail when claim status changes.
6. Where evidence depends on a community's oral history, cultural practice, or situated knowledge, document provenance and permissions respectfully; do not force it into an inappropriate laboratory-only model.
7. Do not manufacture numeric confidence scores. If confidence is assessed, explain the method and limitations.
8. Model-generated summaries are discovery aids, not primary evidence. Verify important claims against the underlying source.

## Example

> **Claim:** The documented test passed on the named configuration.  
> **Status:** VERIFIED (limited scope).  
> **Evidence:** Test command, environment, version/commit, output, and date.  
> **Limit:** This does not establish correctness on untested hardware or configurations.
