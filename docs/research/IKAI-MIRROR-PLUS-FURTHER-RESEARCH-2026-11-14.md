# IKAI MIRROR+ · Further research notes

**Date:** 14 November 2026  
**Status:** RESEARCH  
**Parent:** [IKAI-MIRROR-PLUS-ARCHITECTURE-2026-11-14.md](./IKAI-MIRROR-PLUS-ARCHITECTURE-2026-11-14.md)

This note deepens recovery candidates, conventional smart-mirror software, and pose-estimation limits. It does **not** authorise implementation or deployment.

---

## 1. DEVA / DEVA3 — EXTRACT concepts first

**Origin:** Advanced Interfaces Group, University of Manchester (Pettifer, Cook, Marsh, West and colleagues).

**Architectural ideas of lasting value (from published descriptions):**

- Communicating **entities** as the unit of VE state (objects, environment properties, abstract controllers).
- Logical **client/server** with a definitive locus of control and **client-side mirrors** of entities.
- Use of **subjectivity** to manage synchronisation under network limits (participant views need not equal global authoritative state).
- Flexible description of object **behaviours** and environment **laws**.

**Relation to MAVERIK:** complementary — MAVERIK focuses on modular single-user rendering and application-owned data; DEVA on distribution, behaviour and multi-user scale. Papers treat them as paired, not competing, designs.

**Disposition for IKAI:** **EXTRACT** the conceptual model (entity vs subjective view vs presentation). **Do not** treat DEVA source as ready-to-run until a full recovery audit (source location, licence, dependencies, build on modern GNU/Linux) is completed. Current status of runnable tarballs remains **UNVERIFIED** in this pass.

**Primary literature entry:** DEVA3 architecture paper, VRST 2000 (ACM DOI family `10.1145/502390.502397`).

---

## 2. MAVERIK — GNU project historical micro-kernel

**What it is:** Manchester Virtual Environment Interface Kernel — VR micro-kernel over Mesa/OpenGL, designed so applications retain their own data structures rather than forcing one internal scene graph.

**Published strengths:**

- Application-owned data + callback-driven rendering
- Multiple display and 3D input device support in its era
- Explicit design to integrate with DEVA for multi-user cases

**GNU presence:** Documented as a GNU project (historical download paths via AIG / ftp.gnu.org). Maintainer notes and test coverage on modern hardware are **not** established here.

**Disposition:** **EXTRACT** the “renderer does not own the semantic model” rule (already adopted in the parent dossier). **REVIVE** only after licence tree, build dependency and OpenGL path audit. Age alone is not disqualification; unbuildable bitrot is.

**Reference:** [gnu.org/software/maverik](https://www.gnu.org/software/maverik/).

---

## 3. Croquet family — split open-source vs commercial kernel

| Line | Notes | Disposition |
|------|-------|-------------|
| **Classic Croquet Project** | Squeak Smalltalk collaborative VE SDK; MIT-licensed project history | EXTRACT replicated-computation *ideas*; runtime is not Guile-native |
| **Croquet Microverse** | Browser multiplayer 3D worlds; Apache-2.0 sources on GitHub (`croquet/microverse`); Three.js backend | ADAPT study for collaboration patterns; not a mirror OS |
| **Croquet OS / Reflectors** | Synchronisation infrastructure; commercial reflector network; kernel historically not fully open | **Do not** depend on proprietary reflector for local-first IKAI |

**Lesson for IKAI:** replicated computation and shared object protocols are valuable *concepts*. A local-first mirror must not require a vendor reflector for single-user reflection, beauty consultation or choreography capture.

---

## 4. MagicMirror² — conventional modular baseline (not spatial IKAI)

**What it is:** Open-source modular smart-mirror platform (Electron wrapper, plugin modules). Designed for a display behind two-way glass showing calendar/weather/modules — **not** spatial world models, pose choreography or aerial optics.

**Useful precedents:**

- Module isolation (default vs third-party modules)
- Config redaction toward the browser; recent **secrets** via environment variables (server-side protection only)
- Large community of display-behind-glass builds

**Limits relative to IKAI MIRROR+:**

- No native spatial entity model or subjective multi-view architecture
- Trust boundary: third-party modules can be high risk; secrets only safe server-side
- Not a substitute for GENJE movement or NAKEBUSEN loc-care domain logic

**Disposition:** **ADOPT as Phase-0 UI experiment optional** for simple non-camera overlays; **do not** treat as the IKAI application architecture. Prefer WARENA-controlled local apps for camera-bearing beauty/movement workflows.

**References:** [docs.magicmirror.builders](https://docs.magicmirror.builders/).

---

## 5. MediaPipe Pose — candidate perception, known limits

**Capability:** On-device pose landmarker; **33** body landmarks; image / video / live stream modes; optional segmentation mask; normalised image coordinates and approximate **world** coordinates (metres, origin near hips).

**Implications for mirror apps:**

| Topic | Research finding |
|-------|------------------|
| Finger detail | Not in the 33-point body set — insufficient alone for fine hand choreography |
| World depth `z` | Inferred from monocular input; independent measurements report large angle errors if world landmarks are trusted naïvely for 3D rigs |
| Image vs world | Prefer image-plane landmarks for overlay on mirror video; treat world landmarks as weak estimates |
| Mirroring | Subject-relative left/right; decide mirror transform **after** estimation |
| Failure modes | Cropped body, upside-down poses, small subject, motion blur, person-detector misses |
| Visibility | Version-dependent; older builds may omit visibility fields |

**Disposition:** **ADOPT as Phase-1/2 experiment** for full-body overlay and wellness guidance prototypes, with explicit uncertainty UI. **Not** clinical measurement. Combine with application rules: confidence thresholds, no silent scoring, user-controlled recording.

**Reference:** [MediaPipe Pose Landmarker](https://ai.google.dev/edge/mediapipe/solutions/vision/pose_landmarker).

---

## 6. Stardust XR — spatial desktop candidate (evaluate later)

Linux spatial display server aiming at 2D Wayland apps and 3D objects in one environment. Relevant to **Phase 5** XR desktop integration, not Phase 1 conventional mirror.

**Disposition:** **EVALUATE** after conventional mirror software path works under Guix. Packaging is distro-specific (Fedora/Arch paths documented upstream); Guix availability **UNVERIFIED** here.

**Reference:** [stardustxr.org](https://stardustxr.org/).

---

## 7. Updated disposition summary

| Component | Disposition | Gate before use |
|-----------|-------------|-----------------|
| DEVA concepts | EXTRACT | None for concepts; source audit for code |
| MAVERIK | EXTRACT / possible REVIVE | Licence + modern build |
| Croquet Microverse | Study only | No proprietary reflector dependency |
| MagicMirror² | Optional Phase-0 overlay | Module trust review; no camera PII modules without audit |
| MediaPipe Pose | Phase-1/2 experiment | On-device only; uncertainty UI; no clinical claims |
| Stardust XR | Phase-5 evaluate | Guix packaging / session test |
| AIRR / MiTAI optics | Track B experimental | Optical lab plan; patent search outstanding |

---

## 8. Recommended next evidence tasks

1. Locate DEVA/MAVERIK source archives; record licence files and last known build OS.
2. Pin a Guix revision and attempt **OpenCV + MediaPipe** (or documented alternatives) in a pure offline shell — record pass/fail.
3. Draft Phase-1 conventional mirror lab checklist (camera placement, lighting, two-way glass optional, no aerial optics).
4. Start patent-family search log (empty template OK) under Corpus governance rules.
5. Reconcile this note with open IKAI PRs #5 / #14 before merge.

---

## Status line

**Further research only.** Concepts extracted; no recovery build, no pose pipeline deployment, no optical hardware work authorised by this note.
