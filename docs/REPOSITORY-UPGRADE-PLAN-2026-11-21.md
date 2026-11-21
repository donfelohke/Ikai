# Repository upgrade plan — 2026-11-21

**Role:** IKAI is the Portal for reflective-computing research, knowledge and future validation. **Status:** RESEARCH / WORK IN PROGRESS.

## Portal preservation rule

**The existing IKAI repository and Portal structure are accepted as-is. Do not reorganise, flatten, rename or replace its current wiki/docs/assets/site hierarchy.** Improvements strengthen navigation, content quality and validation in place.

IKAI is a Turkana female name meaning “home.” Its guiding principle is a mirror, not a judge.

## Research architecture

IKAI investigates reflective environments integrating reflective optics, sensing, displays, local computation and human-directed interaction. The mirror is an initial embodiment, not the research boundary. NAKEBUSEN provides grounded beauty/loc-care context; WARENA provides technical capability; GENJE contributes embodied creative practice. FELOH Corpus governs shared canon and evidence.

## Upgrade workstreams

1. Validate Portal navigation, cross-links, accessible headings, mobile reading and metadata without changing repository structure.
2. Connect claims to sources, dates, methods, confidence, limitations and related experiments.
3. Separate optical feasibility, sensing, display, compute, IO, thermal/power, ergonomics and interaction into testable subsystems.
4. Map realtime bidirectional IO paths, latency, synchronization, failure modes, permissions and human override before proposing an integrated device.
5. Preserve participant agency: no face identification, biometric identity matching, person scoring, diagnosis, covert recording or hidden profiling.
6. Prefer local processing, native interfaces and open protocols; no mandatory cloud, analytics, tracking or web runtime.
7. Distinguish literature review, hypothesis, concept, prototype, validation and release.
8. Survey existing standards, scholarship, open-source projects and hardware before inventing components; credit creators.

## Release gates

No product, clinical, performance or deployment claim without direct evidence. No participant data collection without documented purpose, consent, retention, export and deletion controls. Static Portal publication is not evidence of an implemented reflective-computing system.

## Immediate sequence

1. **Enable GitHub Pages with GitHub Actions as the publishing source.** The workflow exists. On 2026-11-21, run [#105](https://github.com/donfelohke/Ikai/actions/runs/44887636726) completed the repository validation and Jekyll build jobs successfully, but the deploy job failed with HTTP 404: “Ensure GitHub Pages has been enabled.” Repository metadata currently reports `has_pages: false`. Enable Pages in repository Settings → Pages → Build and deployment → Source: GitHub Actions, then rerun the `main` workflow and verify the published URL. Do not describe the Portal as live until deployment succeeds and the page is checked.
2. Reconcile open research PRs against the current master dossier.
3. Audit broken links and navigation in the current Portal hierarchy.
4. Prioritise an M1 mirror validation protocol and bidirectional IO test matrix.
5. Record results, including negative results and unknowns, in existing docs/wiki locations.