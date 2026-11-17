# IKAI — Reflective Computing Research Alignment

**Date:** 2026-11-18  
**Status:** RESEARCH / DESIGN-CRITIQUE FRAMEWORK  
**Product status:** IKAI remains research / work in progress; this is not a released feature specification.

## 1. Research source and limits

Md Haseen Akhtar, *Reflective Computing: Seven Dimensions from the Gaps in 134 Interactive Systems, 1996–2026*, arXiv:2610.35696v1, submitted 26 October 2026.

- [arXiv abstract and metadata](https://arxiv.org/abs/2610.35696)
- [Full paper PDF](https://arxiv.org/pdf/2610.35696)
- Treat this as a research preprint; peer-review/publication status is not established here.
- The paper analyses a purposive exemplar corpus of 134 ACM-published interactive systems. Its counts are not a census of all HCI systems.
- The reported codebook, sampling, dimension definitions and statistical methods require critical appraisal; no independent replication is claimed.

The abstract reports two phases of analysis and inter-coder reliability statistics. Reliability is not construct validity or ethical validity. A reported association is not causal evidence. A design framework can be useful as critique, but turning it into a scorecard can recreate the ranking and behavioural optimisation it seeks to avoid.

## 2. Seven dimensions as a design-critique lens

| Dimension | IKAI design question |
|---|---|
| Tempo agency | Does the participant choose when to begin, pause, continue and stop? |
| Invitational form | Does the interface invite reflection without pressure, streaks or coercion? |
| Interpretive openness | Can the participant decide what an experience means, including choosing no interpretation? |
| Reflective depth | Does it support inquiry and reconsideration rather than merely summarising activity? |
| Temporal span | Can a participant connect their own records across time without creating a compulsory profile? |
| Protected idleness | Is silence, inactivity or non-use allowed without penalty or prompt escalation? |
| Ethical non-extraction | Are collection, inference, retention and external processing minimised, visible and participant-controlled? |

This table is IKAI's proposed interpretation of the paper, not a validated implementation or a formal adaptation endorsed by the author.

## 3. Laban-related movement research

Movement may be a participant-authored subject of reflection, but the underlying systems must remain distinct:
- Labanotation / Kinetography Laban are movement notation traditions.
- Motif notation selectively represents essential movement ideas.
- Laban Movement Analysis is a framework for observing and describing movement.
- Bartenieff Fundamentals is a related movement practice.

See the [Ohio State University Department of Dance resource overview](https://dance.osu.edu/research/dnb/resources) and the [FELOH Corpus research brief](https://github.com/donfelohke/feloh-corpus/blob/main/docs/research/labanotation-and-reflective-computing-2026-11.md).

IKAI must not assume that movement notation reveals inner state. A person may use a score, journal or annotation to reflect on their own practice; the system must not convert that record into diagnosis, identity label, emotion estimate, personality inference or capability score.

## 4. Proposed research prototype boundary

A first exploratory study could use only participant-authored text and manually entered movement annotations, with synthetic examples during interface development. Sensor capture is not a prerequisite.

1. Participant creates a record or chooses not to.
2. Participant controls pace and can pause or leave.
3. The interface presents the participant's own chosen notes and temporal comparisons.
4. The participant supplies, revises or rejects any interpretation.
5. Export and deletion are available and tested.
6. No model-generated judgement about the participant is produced.

## 5. Non-negotiable safeguards

- No face identification or biometric identity matching.
- No diagnosis or clinical claims.
- No person scoring, ranking, hidden profiling or covert surveillance.
- No inference of health, emotion, personality, identity, intention or capability from movement or sensor data.
- No default cloud profile; document external processing before proposing it.
- Minimise data; prefer local processing; define retention, export, correction and deletion before collection.
- Do not call a design privacy-preserving until data flows and controls have been tested.
- Obtain appropriate consent and permissions before participant research or recording.

## 6. Evaluation questions

- Can participants control tempo, pause, exit and decide not to reflect?
- Do they understand what is stored, where it is processed and how to delete it?
- Does the interface preserve interpretive openness?
- Does it support reflection without prescribing a meaning?
- Does temporal comparison remain participant-directed rather than turning into a score?
- Can the same purpose be served with less data or no sensor data?

## 7. Design implications — hypotheses, not features

1. **Reflection is not a model output.** The system may help a person revisit records; it must not claim to know what the person has learned, felt or become.
2. **User-paced interaction must be real.** Pause, silence, exit, delayed review and non-use should be valid states, not merely UI decorations.
3. **Interpretation remains user-owned.** Any future optional prompts must be labelled, contestable and never presented as diagnosis or authoritative reading.
4. **Temporal comparison is not a performance metric.** A timeline can show the person's own records without calculating progress, ranking or normative deviation.
5. **Ethical non-extraction requires an auditable data path.** Specify what is collected, processed, retained, exported and deleted; local-first remains a design goal until verified.
6. **No sensor requirement.** Begin with manually authored text or annotations and synthetic data. Do not introduce cameras, microphones, biometrics or motion capture merely because they are available.

## 8. Movement records and reflective interfaces

Ethnographic literature on Labanotation shows that notation can be useful when interpreted alongside practitioner knowledge, direct contextual inquiry, audio and video. It also shows the danger of treating an outsider's first transcription as definitive: the Lahu case required a dancer's corrections to phrase boundaries, rhythm, mistakes and stylistic detail.

If IKAI ever supports movement-related reflection, the participant must own the record and its meaning. The system must not infer emotion, intention, health, identity or capability from the score, video, sound or movement. The person must be able to leave the record uninterpreted, revise it, export it or delete it.

## References

- Md Haseen Akhtar, *Reflective Computing*, arXiv:2610.35696v1: https://arxiv.org/abs/2610.35696
- Latipher Amma Osei (2020), *Documenting Ghanaian dances through Labanotation*: https://www.uew.edu.gh/theatre-arts/staff/laosei/publications/29001/detail
- Kate Grim-Feinberg and Monica FA Wong Santos, *Movement Notation and the Analysis of Embodied Knowledge*: https://jashm.press.uillinois.edu/22.2/grim-feinberg.html
- Ohio State University Department of Dance, resources: https://dance.osu.edu/research/dnb/resources
- International Council of Kinetography Laban, textbook bibliography: https://ickl.org/resources/textbooks/

**Status:** Research critique and hypotheses only. No IKAI feature, user study, sensor processing, clinical use or deployment is claimed.
