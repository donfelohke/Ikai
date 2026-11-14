# IKAI MIRROR+ · Product research, design, TAM, MVP, MaxVP

**Date:** 14 November 2026  
**Status:** RESEARCH · PRODUCT STRATEGY PROPOSAL  
**Not:** a revenue forecast, fundraise deck, or implementation approval

Parent architecture: [IKAI-MIRROR-PLUS-ARCHITECTURE-2026-11-14.md](./IKAI-MIRROR-PLUS-ARCHITECTURE-2026-11-14.md)

---

## 0. Evidence rules for this document

| Label | Meaning |
|-------|---------|
| **VERIFIED** | Inspectable primary fact (our own prices, repo state, named product existence) |
| **SECONDARY ESTIMATE** | Third-party analyst market size — useful orientation, **not** our revenue |
| **INTERPRETATION** | Our reasoned product mapping |
| **UNVERIFIED** | Attractive claim without adequate local evidence |

**Market-size warning:** Published “smart mirror” and “fitness mirror” totals **disagree by an order of magnitude** across firms (hundreds of millions vs multi-billion definitions). Treat ranges as **category context**, not a budget line.

**Commercial boundary:** ONLY **NAKEBUSEN** transacts. IKAI / GENJE / WARENA remain research and technical practice unless a future, explicit commercial decision is recorded.

---

## 1. Product design thesis

**One platform · three application families · staged embodiment**

| Family | Brand surface | Job to be done |
|--------|---------------|----------------|
| Beauty & care | **NAKEBUSEN** | Loc consultation, progress memory, client–loctician alignment |
| Movement & choreography | **GENJE** | Capture, revisit, transform movement with agency |
| Wellness & reflection | **IKAI** | Guided body awareness without clinical claims |
| Infrastructure | **WARENA** | Reproducible local compute, not a consumer brand |

**Design principles**

1. Local-first; no mandatory cloud.  
2. Observation ≠ estimate ≠ recommendation.  
3. Preview is not a physical guarantee (especially hair).  
4. Human remains author of care and movement decisions.  
5. Conventional reflective mirror before aerial optics.  
6. Software proves value before expensive optical hardware.

---

## 2. Market context (SECONDARY ESTIMATES)

### 2.1 Broad “smart mirror” category

Analyst summaries publicly cite very different 2025–2026 baselines, for example:

| Source class (public abstracts) | Approx. 2025/2026 figure | Horizon |
|---------------------------------|--------------------------|---------|
| Business Research Company–class | ~USD 4.1B (2025) → ~4.6B (2026) | → ~7.4B by 2030 |
| Fortune Business Insights–class | ~USD 3.0B (2025) → ~3.4B (2026) | → ~10B by 2034 |
| Mordor–class | ~USD 4.5B (2025) | → ~7.4B by 2031 |
| Precedence–class | ~USD 0.65–0.70B (2025–26) | → ~1.3B by 2034 |

**INTERPRETATION:** Definition drift (automotive digital mirrors, retail AR, bathroom IoT, fitness hardware, hospitality) inflates or shrinks the same label. **Do not pick one number as “the TAM.”**

### 2.2 Fitness / wellness mirror slice

| Source class | Approx. value | Notes |
|--------------|---------------|--------|
| GM Insights–class smart fitness mirror | ~USD 347M (2025), ~382M (2026) | ~231k units cited for 2025 |
| Fact.MR–class AI wellness mirrors | ~USD 247M (2025), ~273M (2026) | |
| Other fitness-mirror reports | ~USD 0.37–1.8B depending on definition | Lululemon Mirror / Tonal / Tempo / Echelon cited as category anchors |

**INTERPRETATION:** Premium connected fitness mirrors are a **small, contested, subscription-heavy** segment with high hardware cost and known brand exits/pivots — not a blank cheque for a Kenya-first loc studio product.

### 2.3 Beauty / virtual styling adjacency

Public abstracts cite large **hairstyle simulation AI** and **virtual try-on / virtual fitting** categories (global, software-heavy). Kenya-specific **virtual fitting room** and **fashion tech** reports exist as paid research; **open free full figures for salon-mirror hardware in Eldoret are not established here.**

**VERIFIED local commercial path:** NAKEBUSEN already sells **loc services** (documented site prices and WhatsApp enquiry), not smart-mirror hardware.

---

## 3. TAM / SAM / SOM (honest ladder)

```text
TAM  — global spend in categories we might eventually touch
SAM  — reachable category × regions × use cases we could serve
SOM  — share we could realistically win in a defined period with our channel
```

### 3.1 TAM (context only — SECONDARY)

Union of: smart mirrors (retail/residential/hospitality) + fitness/wellness mirrors + salon digital consultation / virtual hair tooling.

**Order-of-magnitude:** hundreds of millions to low billions USD depending on definition. **Not actionable as a single number.**

### 3.2 SAM (INTERPRETATION)

Narrower, product-shaped markets:

| Segment | Why in SAM |
|---------|------------|
| Salon / loctician **consultation tooling** (software + optional display) | Aligns with NAKEBUSEN craft |
| **Studio / cultural movement** tools (phrase capture, delayed reflection) | Aligns with GENJE |
| **Local-first wellness guidance** mirrors (non-clinical) | Aligns with IKAI ethics |
| **East Africa / Kenya** professional beauty services digitisation | Geographic reality |

Exclude for near-term SAM: automotive mirrors, EU truck ADAS, pure US premium home gym subscriptions unless a deliberate export play is funded.

### 3.3 SOM (near-term, INTERPRETATION — not a forecast)

**Primary SOM (0–24 months):** revenue and learning from **NAKEBUSEN loc care** + optional **paid consultation experiments** (software-assisted booking/history), not mirror-hardware sales.

**Secondary SOM (research):** 1–3 pilot mirror stations (studio or home lab) used to validate software — cost centres, not assumed product-market fit.

**Explicit non-goals for SOM:** claiming % of global fitness-mirror market; shipping AIRR/MiTAI consumer devices; medical claims.

Until field counts exist (clients served with tool, pilot retention, willingness-to-pay interviews), **SOM stays qualitative**.

---

## 4. Personas and jobs

| Persona | Primary job | Success look |
|---------|-------------|--------------|
| Loc client (Kenya) | Understand options; trust craft; track progress | Clear before/after memory; less style mismatch |
| Loctician (NAKEBUSEN) | Consult faster; document work; reduce rework | Shared visual plan; authorised history |
| Dancer / choreographer | Remember and transform movement | Phrase recall; non-judgemental replay |
| Home wellness user | Practice safely with guidance | Local sessions; no body-shaming scores |
| Systems operator (WARENA) | Keep station reproducible offline | Guix-defined image; recovery path |

---

## 5. MVP · MLP · MaxVP

Definitions used here:

| Term | Meaning |
|------|---------|
| **MVP** | Smallest product that tests the riskiest assumption with real users |
| **MLP** | Minimum *lovable* product — still narrow, but craft-quality enough to retain |
| **MaxVP** | Maximum vision product — full platform ambition **ceiling**, not next sprint |

### 5.1 Beauty (NAKEBUSEN) path — commercial priority

| Stage | Scope |
|-------|--------|
| **MVP** | Phone or laptop **consultation aid**: authorised photo pairs, notes, sectioning checklist, WhatsApp handoff. **No** two-way glass required. |
| **MLP** | Station display in studio: camera + calibrated lighting + overlay annotations + local history (client consent). Still conventional display/mirror. |
| **MaxVP** | Full beauty mirror: hair geometry aids, style previews clearly labeled simulated, multi-client privacy vault, optional retail kiosk mode, aerial optics **only if** Track B research succeeds |

**Riskiest assumption to test first:** locticians and clients will use a structured visual history in real appointments (not that consumers will buy a USD 1k+ fitness-class mirror).

### 5.2 Movement (GENJE) path — creative research

| Stage | Scope |
|-------|--------|
| **MVP** | Single-camera pose overlay + timed delayed video replay on existing PC/display |
| **MLP** | Phrase bookmarking, side-by-side compare, export stills/clips, local library |
| **MaxVP** | Multi-view room, collaborative sessions, notation export, spatial desktop integration |

### 5.3 Wellness (IKAI) path — careful scope

| Stage | Scope |
|-------|--------|
| **MVP** | Guided routine player + optional silhouette overlay; explicit non-medical framing |
| **MLP** | User-owned session log; accessibility options; offline packs |
| **MaxVP** | Multi-participant reflective environment; optical embodiments; still **no** diagnostic claims |

### 5.4 Platform MaxVP (IKAI MIRROR+ vision ceiling)

Persistent spatial computing: shared entity model, subjective views, interchangeable optics (reflective → AIRR/MiTAI → light-field), XR desktop hooks, WARENA-reproducible stations — as in the architecture dossier. **This is not the MVP.**

---

## 6. Pricing hypotheses (INTERPRETATION only)

| Offer | Hypothesis |
|-------|------------|
| Loc services | Keep **existing** NAKEBUSEN starting prices as commercial truth; tool is margin/support, not a price rewrite |
| Studio software pilot | Bundle into service quality; or small monthly tool fee **after** proven time-save |
| Hardware station | Avoid early DTC hardware; lab/build cost tracked as R&D |
| Fitness-mirror-like subscription | **Out of scope** unless separate business case |

---

## 7. Competitive positioning (qualitative)

| Competitor class | Example anchors | Our difference |
|------------------|-----------------|----------------|
| Premium fitness mirrors | Mirror/Lululemon lineage, Tonal, Tempo, Echelon | Not competing on US subscription gym content |
| Beauty AR apps / kiosks | ModiFace-class, retail try-on | Loc-craft + local consent + offline |
| DIY MagicMirror | Open modules | Domain apps + privacy doctrine + Guix |
| Salon POS (Kenya) | Local salon software | Visual craft memory, not only till/commission |

---

## 8. Go-to-market sequence

1. **Prove software in live NAKEBUSEN appointments** (MVP beauty).  
2. **Instrument learning** (time per consult, rework rate, consent completion) — private metrics.  
3. **Optional studio station** (MLP) once workflow sticks.  
4. **GENJE labs** in parallel as creative R&D, not forced revenue.  
5. **Hardware/optics** only after software retention evidence.  
6. **Export / B2B salon tooling** only after Kenya proof.

---

## 9. Success metrics (research programme)

| Stage | Leading indicators |
|-------|--------------------|
| MVP beauty | % appointments using tool; consent rate; qualitative loctician feedback |
| MLP | Week-4 retention of use; reduced “style mismatch” complaints (define baseline first) |
| GENJE MVP | Phrases saved per session; intentional replay rate |
| Platform | Offline session success; restore-from-backup drill pass |

**Non-metrics:** forced body scores; unauthorised biometric ID; vanity global TAM %.

---

## 10. Risks

| Risk | Mitigation |
|------|------------|
| Chasing global fitness-mirror TAM | SOM locked to NAKEBUSEN path |
| Optical research absorbs all budget | Track A software first |
| Privacy harm | Local-first, per-app permissions, visible capture indicators |
| Analyst-number cargo cult | Secondary estimates labeled; no board KPI on vendor CAGR |
| Scope collapse (three apps at once) | Sequence beauty → movement → wellness features |

---

## 11. Decision summary

| Question | Current research answer |
|----------|-------------------------|
| What is the product? | Platform for reflective spatial apps; **first commercial surface = NAKEBUSEN consultation tooling** |
| What is MVP? | Software-assisted loc consultation & history — no aerial mirror required |
| What is MaxVP? | Full IKAI MIRROR+ multi-embodiment platform |
| What is TAM? | Broad smart-mirror/fitness/beauty-tech **context only**; figures conflict |
| What is SOM? | Near-term Kenya loc-care + pilot stations; quantitative SOM **pending field data** |

---

## 12. Status line

**Product research only.** Market figures are secondary estimates with high variance. No hardware purchase, pricing change, or commercial launch is authorised by this document.
