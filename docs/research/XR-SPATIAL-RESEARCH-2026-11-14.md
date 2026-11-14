# XR & spatial computing research · IKAI MIRROR+

**Date:** 14 November 2026  
**Status:** RESEARCH · T3 / Phase 5 track  
**Does not change:** T0 MVP priority, local-first doctrine, NAKEBUSEN commercial boundary

---

## 1. Role of XR in the architecture

XR is **one embodiment class** of the same semantic platform — not a replacement for the physical mirror.

| Embodiment | Tier | Status |
|------------|------|--------|
| Ordinary display / laptop | T0 | **Default now** |
| Two-way glass panel | T1 | Next after software proof |
| Aerial optics (AIRR / MiTAI) | Lab | Track B |
| **XR HMD / spatial desktop / spatial display** | **T3** | **This document** |

Same pipeline still holds: capture → estimate → entity → policy → present → persist. XR only changes the **present** stage and optional input (hands, controllers, head pose).

---

## 2. OpenXR spatial containers (2026)

**Finding (SECONDARY / standards):** Khronos published multi-vendor extensions for **spatial containers** — system-managed volumes analogous to 2D windows, with bounded vs immersive modes.

| Extension | Role |
|-----------|------|
| `XR_EXT_spatial_container` | Create/manage spatial containers |
| `XR_EXT_spatial_container_self_rendering` | App renders into containers via composition layers |

Reported timeline context: extensions associated with OpenXR **1.1.63** registry work (Sept 2026 class reporting); public announcement and samples around Oct 2026; **runtime implementations expected to roll out through 2026** — not assumed present on every device today.

**IKAI implication:** Domain apps (consult overlays, phrase panels, wellness guides) should eventually be **portable panels** that can appear on a mirror surface *or* in a spatial container — shared semantic API, dual presenters.

**Limit:** A ratified extension ≠ working Monado/vendor support on our hardware until tested.

---

## 3. Linux open runtime path

| Component | Evidence | WARENA angle |
|-----------|----------|--------------|
| **Monado** | OpenXR runtime; Guix package exists (`monado`, e.g. 25.1.0 listed in Guix package browser) | Primary **candidate** runtime for Guix stations |
| **WebXR on Linux** | Chromium work via OpenXR/Monado continuing in 2026 | Optional browser-based experiments |
| **Spatial container in Monado** | Reporting indicates mainline support **not** assumed complete when extensions landed | Track upstream; do not depend for MVP |

---

## 4. Spatial desktop / compositor candidates

| Project | Model | Notes |
|---------|-------|-------|
| **Stardust XR** | Linux XR display server; 2D windows + 3D objects in shared space | Open-source spatial desktop direction; packaging varies by distro |
| **Godot + OpenXR** | Engine + composition layers (quad/cylinder/equirect) | Strong for GENJE / prototype visuals; not Guile-native |
| **DisplayXR-class runtimes** | OpenXR for spatial *displays* (not only HMDs) | Relevant if light-field / 3D monitor path returns |
| **WindowMirror-class research** | Multi-window desktop into XR | Productivity pattern; evaluate licence before use |

**Guile-first policy:** XR presenters may be native/Godot/Rust; **semantic ownership stays** in Guile/local store where possible (same as CV boundary).

---

## 5. Hybrid mirror + XR patterns (research inspiration)

| Pattern | Idea | Privacy note |
|---------|------|--------------|
| **Headset-driven external mirror** | Passthrough / MR content mirrored to a room display so observers participate without wearing HMD (e.g. MIRAGE-class installations) | Capture and cast policies must be explicit |
| **Seated spatial workspace** | Panels in arm-reach arc; hands-first | Aligns with salon stool / studio chair use |
| **XR window managers** | Automated layout of spatial zones | Optional; avoid mandatory cloud LLM layout for IKAI |

These validate **shared reflection without forcing every participant into an HMD** — complementary to IKAI’s physical mirror thesis.

---

## 6. XR stack proposal (T3 only)

```text
IKAI domain apps (Guile semantic core)
        │
   present adapters
   ├── mirror_presenter (T0/T1)
   └── xr_presenter (OpenXR)
            │
        Monado (candidate) ── hardware
            │
   optional: Stardust XR / Godot clients for spatial chrome
```

| Layer | Candidate |
|-------|-----------|
| API | OpenXR 1.x + watch spatial container support |
| Runtime | Monado on Guix |
| Engine (optional) | Godot 4.x OpenXR |
| Spatial OS experiment | Stardust XR |
| Web path | WebXR via Chromium+OpenXR when needed |

**Hardware BoM (T3):** HMD or spatial display — **not** purchased under this research note; evaluate used/dev kits only after T1 software gates.

---

## 7. What XR must not break

- Local-first storage and consent  
- Observation vs estimate vs recommendation labels  
- NAKEBUSEN-only commercial path  
- Ability to run full consult MVP with **zero** XR hardware  

---

## 8. Research gates before any XR “support” claim

1. Monado installs and `hello_xr`-class test on a named Guix or interim host.  
2. One IKAI panel type rendered both on 2D display and in OpenXR quad layer.  
3. Documented privacy behaviour for passthrough/camera.  
4. Explicit **non-support** list (devices never tested).

---

## 9. Status line

**XR is a first-class research track (T3), second-class product dependency.**  
Standards momentum (spatial containers) is real; shipping runtimes and Guix-daily-driver maturity remain to be evidenced on WARENA hardware.
