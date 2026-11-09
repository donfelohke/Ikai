# IKAI — Reflective Computing Research Alignment

**Date:** 2026-11-09  
**Status:** RESEARCH / DESIGN-CRITIQUE FRAMEWORK  
**Product status:** IKAI remains research / work in progress; this is not a released feature specification.

## 1. Research source

Md Haseen Akhtar, *Reflective Computing: Seven Dimensions from the Gaps in 134 Interactive Systems, 1996–2026*, arXiv:2610.35696v1, submitted 26 October 2026.

- [arXiv abstract and metadata](https://arxiv.org/abs/2610.35696)
- [Full paper PDF](https://arxiv.org/pdf/2610.35696)
- **Accessed:** 2026-11-09
- **Review:** Full 54-page PDF inspected. The paper is treated as a research preprint; peer-review/publication status is not established here.
- **Methodological caution:** The paper analyses a purposive exemplar corpus of 134 ACM-published interactive systems. Its reported counts are not a census of all HCI systems. The results and codebook require critical review; no independent replication is claimed.

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

IKAI should not assume that movement notation reveals inner state. A person may use a score, journal or annotation to reflect on their own practice; the system must not convert that record into a diagnosis, identity label, emotion estimate, personality inference or capability score.

## 4. Proposed research prototype boundary

A first exploratory study could use only participant-authored text and manually entered movement annotations, with synthetic examples during interface development. Sensor capture is not a prerequisite.

Candidate interaction:
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
- Obtain appropriate consent and permissions before any participant research or recording.

## 6. Evaluation questions

- Can participants control tempo, pause, exit and decide not to reflect?
- Do they understand what is stored, where it is processed and how to delete it?
- Does the interface preserve interpretive openness?
- Does it support reflection without prescribing a meaning?
- Does temporal comparison remain participant-directed rather than turning into a score?
- Can the same purpose be served with less data or no sensor data?

**Status boundary:** This document records research alignment and candidate questions. It does not claim an implemented prototype, completed participant study, validated outcome, sensor integration or deployment.
