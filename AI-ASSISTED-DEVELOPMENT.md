# AI Assistance, Research Integrity and Participant Privacy

**Status:** Proposed research policy  
**Canonical policy:** [FELOH Corpus — AI-Assisted Development and Source Integrity](https://github.com/donfelohke/feloh-corpus/blob/main/AI-ASSISTED-DEVELOPMENT.md)

IKAI applies the canonical policy to reflective-compute research, interface experiments, embodied interaction, sensor studies and local computation.

## Rules

- Do not upload identifiable participant data, movement recordings, sensor traces, private logs, sensitive reflections or consent materials to external AI services unless a documented lawful basis, informed consent and approved data-processing arrangement explicitly permit it.
- Prefer synthetic, aggregate or properly de-identified data where sufficient; document residual re-identification risk.
- AI output must not be used to diagnose, score, rank, identify or covertly profile people. Preserve IKAI's boundary: a mirror, not a judge.
- Distinguish participant testimony, measured observation, interpretation, hypothesis and model-generated summary.
- Never treat an LLM's interpretation as a validated research finding or a participant's own statement.
- Record material AI assistance, model/tool where known, authorised input class, human review and limitations.
- Do not use leaked or restricted implementation code as an AI rewrite input or represent such a rewrite as independent work.
- Keep data local where practical; document any external processing, retention, access and deletion assumptions before proposing it.

## Licensing status

This document does not change the repository software licence. IKAI has a root **GNU General Public License, Version 3** (`LICENSE` on the default branch).

That root GPL-3.0 grant covers original software and documentation released under it. It does **not** automatically establish rights over third-party datasets, participant-derived material, firmware, recordings, sensor traces, vendor implementations or other separately restricted content. Those items require individual rights, consent and provenance assessment before use, redistribution or relicensing.

## Research-code provenance and clean-room integrity

For sensor pipelines, firmware, interaction models, interfaces and research prototypes, distinguish public documentation, lawful observations, participant-derived data, third-party implementation and original code. Do not use confidential vendor source, restricted datasets or participant material as AI rewrite inputs. Do not turn restricted research artefacts into paraphrased specifications and then call the implementation independent.

Record the permitted evidence set, data authority/consent, source versions, specification authorship and reviewer. If the provenance of a model, library, dataset or generated code is unclear, isolate it from experiments and releases pending review. Preserve the distinction between participant testimony, measured observations, interpretation and model-generated output.

For IKAI, **code laundering** includes disguising the origin, licence or access restrictions of copied research code, firmware, datasets, sensor pipelines or vendor implementations through AI rewriting or paraphrased specifications. A clean-room claim requires an independent, documented evidence path.
