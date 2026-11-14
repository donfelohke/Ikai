# IKAI MIRROR+ · WARENA COMPUTE

**Consolidated foundational research and architecture dossier**

| Field | Value |
|-------|-------|
| **Date** | 14 November 2026 |
| **Status** | RESEARCH · ARCHITECTURE PROPOSAL |
| **Scope** | Immersive mirrors, XR desktops, beauty, movement, choreography, wellness, spatial computing, optical systems, foundational software |
| **Implementation** | **Not authorised** by this document |

---

## 1. Executive proposition

**IKAI MIRROR+** is a persistent, spatially aware and embodied computing environment capable of expressing itself through interchangeable optical and digital interfaces.

It is not merely a smart mirror, a screen behind two-way glass, a fitness product or an XR headset. It is a platform relating physical environments, digital entities, human participants, movement, time and multiple forms of representation.

The platform must support:

- Reflective and conventional display mirrors
- Transparent and semi-transparent displays
- Aerial and mid-air image systems
- Spatial and immersive desktop environments
- Beauty and personal-care applications
- Dance, movement and choreography
- Wellness and guided physical activity
- Multiple participants and viewpoints
- Local, persistent and distributed computing

**Objective:** one reusable platform rather than several disconnected smart-mirror products.

### Governing engineering doctrine

1. Reuse before rebuild.
2. Recover before replace.
3. Extend before fork.
4. Fork before reimplement.
5. Reimplement only when existing approaches demonstrably fail.

Age or dormancy alone does not disqualify software. Evaluate source availability, licence, architecture, dependencies, buildability, compatibility, performance, interoperability and revival cost.

### Disposition vocabulary

| Term | Meaning |
|------|---------|
| **ADOPT** | Use substantially as designed |
| **ADAPT** | Modify or integrate |
| **REVIVE** | Recover abandoned/dormant work |
| **EXTRACT** | Reuse a subsystem or concept |
| **REPLACE** | Only after demonstrated failure |

---

## 2. Project relationships

| Project | Responsibility |
|---------|----------------|
| **WARENA COMPUTE** | Infrastructure, OS environment, hardware integration, reproducible software |
| **IKAI** | Reflective computing, spatial representation, embodied interaction, mirror applications |
| **GENJE** | Movement, choreography, rhythm, creative expression, embodied performance |
| **NAKEBUSEN** | Beauty, loc care, personal presentation, consultation and care services |
| **FELOH Corpus** | Research governance, source documentation, decisions |

**Commercial boundary:** ONLY NAKEBUSEN transacts for beauty services. IKAI and GENJE remain research/creative technology. WARENA enables technical capability.

**Brand formula:** *NAKEBUSEN grounds. GENJE embodies. IKAI reflects. WARENA enables.*

---

## 3. Three application families

### 3.1 NAKEBUSEN Beauty Mirror

Beauty and personal-care mirror for consultation, visualisation, care education and longitudinal records.

**Priority opportunity:** practical loc-care support and client–loctician visual communication — not generic virtual makeup.

Capabilities (research candidates):

- Loc and hairstyle consultation; sectioning and retie guidance
- Hair segmentation / geometry estimation; styling previews
- Loc progress documentation; before/after comparisons
- Care instructions; reference annotation; authorised history

**Rule:** distinguish actual camera observations from simulated styling previews. A virtual style is a proposal, not a guaranteed physical result.

### 3.2 GENJE Movement and Choreography Mirror

Creative movement instrument for observing, recording, revisiting and transforming movement.

Capabilities (research candidates):

- Pose estimation; joint/skeleton visualisation; movement trails
- Phrase capture; delayed self-reflection; multi-temporal playback
- Choreographic annotation; rhythm synchronisation; spatial notation
- Search/compare phrases; abstract and non-photorealistic representations
- Collaborative choreography

**Rule:** do not enforce a single correct dance form. Support the dancer’s vocabulary and agency. Promising interaction: reenact a remembered pose to retrieve a recorded choreography moment.

### 3.3 IKAI Wellness Mirror

Personal movement and body-awareness environment.

Capabilities (research candidates):

- Guided stretch/mobility; yoga/balance; exercise demonstration
- Breathing/relaxation; accessible visual and audio guidance
- Optional instructor-led sessions; user-controlled history

**Rule:** no medical diagnosis, no replacement of professional supervision, no clinical validity claims from camera pose alone.

---

## 4. Shared platform, separate domain logic

| Capability | Beauty | Movement / choreography | Wellness |
|------------|--------|-------------------------|----------|
| Primary view | Face, hair, upper body | Full body and room | Full body / exercise area |
| Sensing | RGB close-up | RGB-D, wide-angle, optional IMU | RGB or RGB-D |
| Spatial model | Face/head/hair geometry | Joints, trajectories, room coords | Pose, balance, range |
| Feedback | Previews, annotations | Traces, timelines, overlays | Visual + audio guidance |
| Persistence | Client-authorised care records | Phrases and choreography | User-controlled routines |
| Main concern | Fidelity + privacy | Creative agency + tracking | Safety + accessibility |

Shared infrastructure may include calibration, coordinate transforms, tracking, rendering, local persistence, session management, audio, permissions and lifecycle. **Do not** force one generic fitness UI.

---

## 5. Conceptual model (six distinctions)

1. **Observation** — what a sensor measures
2. **Estimate** — inference from observations
3. **Entity** — persistent computational identity
4. **World state** — maintained entities and relationships
5. **Subjective view** — participant-specific representation
6. **Presentation** — device-specific rendering and interaction

Preserve provenance, confidence, time, coordinate frames, permissions, and the distinction between measured, inferred and manually supplied information.

---

## 6. Seven logical architecture layers

Architectural responsibilities — not seven new repositories.

1. **Computational foundation** — GNU/Linux, drivers, Guix, storage, network, security, GPU/display
2. **Runtime and distribution** — lifecycle, IPC, discovery, sync, local-first
3. **Semantic world model** — identity, relations, hierarchy, behaviour history, provenance
4. **Spatial model** — frames, geometry, anchors, transforms, calibration, tracking
5. **Perception and actuation** — cameras, IMU, audio, touch/gesture, outputs (kept separate)
6. **Subjective computing** — viewpoint, context, attention, permissions, local authority
7. **Embodiment and presentation** — reflective, transparent, aerial, desktop, HMD, mobile

The semantic model must not depend on any single display technology.

---

## 7. Optical and display tracks

| Track | Content | Role |
|-------|---------|------|
| **A** | Conventional reflective mirror + camera/display | **Practical computational baseline** |
| **B** | AIRR, MiTAI, LeAIRR, p-AIRR, MMAP/DCRA | Distinctive optical research |
| **C** | Integral imaging / light-field / multiview | Longer-term research |

**MiTAI** (Mirror-Transcending Aerial Imaging): optical systems that move imagery between mirrored and real space (Sano et al., JSID 2023, DOI [10.1002/jsid.1221](https://doi.org/10.1002/jsid.1221); interactive implementation research e.g. SUI 2023).

**Do not** make aerial or light-field imaging a prerequisite for validating IKAI software architecture.

IEC references for aerial display measurement (research index): IEC 62629-52-1:2024; IEC TR 62629-51-1:2020.

---

## 8. Historical software (recovery candidates)

| Project | Relevance |
|---------|-----------|
| **DEVA / DEVA3** | Distributed virtual environments; environment hierarchy; subjective views |
| **MAVERIK** | Modular rendering kernel; application-owned data |
| **Croquet** | Replicated collaborative environments |
| Open Wonderland, OpenSimulator, X3D/VRML, OpenSceneGraph, VulkanSceneGraph, ARToolKitX | Context / recovery candidates |

**Lesson:** rendering must not own persistent entity identity or the full semantic world model.

Code is **not** reusable until source, licence, dependencies and buildability are audited.

---

## 9. XR desktop and related software

Candidates for **evaluation** (not interchangeable):

- [Stardust XR](https://stardustxr.org/) — spatial display server / 2D+3D environment on Linux
- WayVR — XR overlay / desktop integration research
- Monado — open-source OpenXR runtime
- DisplayXR — OpenXR for spatial displays
- Xpra — persistent remote X11 sessions
- MagicMirror² — conventional modular smart-mirror software

OpenXR spatial-container directions (Khronos ecosystem, 2026) are interoperability interfaces, not the whole IKAI architecture.

### Desktop policy (aligned with WARENA)

| Track | Disposition |
|-------|-------------|
| **Default research desktop** | X11 (Xorg first; XLibre experiment) |
| **Alt** | Wayland · dwl-guile / RDE |
| **Config home** | Guix + RDE |

A spatial mirror may **extend** ordinary desktop applications; it need not replace them.

---

## 10. Perception and spatial software shortlist

| Need | Candidate |
|------|-----------|
| Image processing / calibration | OpenCV |
| Body/hand landmarks | MediaPipe |
| SLAM | ORB-SLAM3, RTAB-Map, OpenVINS |
| Camera/IMU calibration | Kalibr |
| Transforms / middleware | ROS 2 TF2, DDS |
| Assets | OpenUSD, glTF |
| XR interface | OpenXR |
| Graphics | Vulkan, OpenGL |

Select by **application need** (beauty may prioritise close-up fidelity; choreography prioritises temporal analysis and room calibration).

---

## 11. WARENA COMPUTE foundation

**Preferred stack direction (research):**

- GNU/Linux · GNU Guix · GNU Guile · GOOPS
- Native C/C++ for vision, SLAM, geometry, GPU, drivers
- SQLite or replaceable local persistence
- Vulkan/OpenGL · OpenXR where appropriate

**Guile/GOOPS for:** entities, relations, coordination, policy, events, high-level interaction.  
**Native for:** CV, SLAM, rendering, high-throughput paths.  
**FFI:** narrow and deliberate.

**Distribution requirements:** offline operation, local-first ownership, explicit network permissions, multi-device, reproducible configuration, backup/recovery, human-controlled permissions.

---

## 12. Hardware architecture

Modular, not a sealed appliance.

Shared: reflective surface, display/optical source, camera, compute, storage, network, audio, physical controls.

Profiles differ for beauty (colour-consistent lighting, close-up RGB), movement (full-length, wide-angle, optional depth/IMU, clearance), wellness (accessibility, audio, safety boundaries).

Compute: existing x86-64 GNU/Linux first; external/distributed compute during early optical experiments preferred. EliteBook-class hardware remains **unconfirmed** as the target. GPU selection only after measured requirements.

---

## 13. Privacy, consent, safety, agency

Foundational — not a later feature.

- Local processing by default; no mandatory cloud
- Explicit recording controls; clear sensor indicators
- User-controlled retention and deletion
- Per-application permissions; no automatic cross-app transfer of intimate records
- No covert recording; no biometric ID without separate justified consent
- No unsupported medical/psychological claims; no compulsory body scoring
- Option to hide reflection or use abstract representations
- Accessible alternatives to gesture-only UI
- Usable without creating a persistent personal record

---

## 14. Source register (research index)

**Not** a claim that every item has been full-text reviewed or build-verified.

### Optical

- MiTAI, Sano et al., 2023 — DOI [10.1002/jsid.1221](https://doi.org/10.1002/jsid.1221)
- Interactive MiTAI / SUI 2023 — DOI [10.1145/3607822.3614536](https://doi.org/10.1145/3607822.3614536)
- Related AIRR / LeAIRR / freeform / polarisation literature (see prior research notes; verify each DOI before citation in publications)

### Movement

- CHI 2023 mixed-reality mirror dance improvisation literature
- Embodied retrieval / pose-to-archive research directions (e.g. DanXeReflect-class work)
- Dance visual analytics and interactive learning system reviews

### Standards

- IEC aerial display measurement family
- OGC GeoPose 1.0; ARML 2.0
- OpenXR, glTF registries

### Software hubs

Stardust XR, Monado, MagicMirror², OpenCV, MediaPipe, ORB-SLAM3, RTAB-Map, OpenVINS, Kalibr, ROS 2 geometry2, OpenUSD, Guile, Guix.

### Patent search (outstanding)

Google Patents, Patentscope, J-PlatPat, EPO, Kenya KIPI — aerial imaging, AIRR/MiTAI, beauty visualisation, mirror feedback. **No FTO conclusion.**

---

## 15. Development programme (phased)

| Phase | Focus |
|-------|--------|
| **0** | Requirements, privacy model, geometry baseline |
| **1** | Conventional mirror foundation (camera, UI, local runtime, persistence, beauty/movement prototypes) |
| **2** | Embodied interaction (tracking, spatial model, trails, controlled record/playback) |
| **3** | Temporal/persistent computing (phrases, entities, offline, multi-session) |
| **4** | Optical experiments (AIRR breadboard, luminance, sharpness, viewing angle, MiTAI transitions) |
| **5** | XR desktop integration (spatial windows, OpenXR where useful) |
| **6** | Advanced spatial embodiments (multiview, multi-observer, collaborative) |

No arbitrary performance targets before baseline measurements.

---

## 16. Evaluation criteria (summary)

Optical · Perception · Interaction · Software (reproducibility, offline, permissions) · Human factors (privacy, comfort, body-image, accessibility, agency).

---

## 17. Open research questions

1. Can DEVA environment/subjective-view concepts adapt to local-first spatial computing?
2. Which MAVERIK parts remain architecturally valuable?
3. Guile/GOOPS for semantic coordination vs native perception/render — workable FFI?
4. Multi-participant subjective views of shared entities?
5. Disconnected local authority reconciliation without naïve last-write-wins?
6. Movement as persistent temporal-spatial entity vs video-only?
7. Isolation of beauty vs body-movement records across apps?
8. Optical architecture trade-offs (brightness, size, maintainability, cost)?
9. What is common across reflective, aerial and HMD embodiments?
10. Usefulness when tracking fails, cameras off, or network absent?

---

## 18. Architectural decision table

| Area | Direction | Status |
|------|-----------|--------|
| Identity | IKAI MIRROR+ / WARENA COMPUTE | Research |
| Domains | Beauty · Movement · Wellness | Research |
| OS foundation | GNU/Linux + Guix | Preferred |
| Semantic runtime | Guile/GOOPS | Candidate |
| Heavy processing | Native C/C++ | Preferred separation |
| Conventional mirror | Initial embodiment | Proposed baseline |
| AIRR / MiTAI | Optical research | Experimental |
| Light field | Future track | Experimental |
| Persistence | Local-first, replaceable | Requirement |
| Privacy | Consent, least privilege | Foundational |
| Hardware | Modular | Requirement |
| Historical software | Audit → recover → reuse | Research |
| Production implementation | — | **Not approved** |

---

## 19. Final synthesis

The most valuable contribution may not be a new optical gadget or a new pose algorithm, but integration of:

- Persistent spatial computing
- Subjective and shared world models
- Embodied interaction and temporal movement memory
- Interchangeable optical embodiments
- Local-first infrastructure
- Human-controlled perception and representation

**Recommended strategy:** establish shared computational foundation → validate conventional mirror applications → investigate AIRR/MiTAI as optical research → recover proven historical technologies before commissioning new implementations.

**Outstanding evidence work:** DEVA/MAVERIK/Croquet audits; competitor capability comparison; licence/build verification; patent-family research; hardware/optical test plans; separation of validated findings from vendor claims.

---

## Status line

**Research and architecture consolidation only.** No hardware purchase, production implementation, deployment or commercial release is authorised by this document.
