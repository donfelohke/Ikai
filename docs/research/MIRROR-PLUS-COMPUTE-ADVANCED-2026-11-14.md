# Mirror + Compute · Advanced architecture note

**Date:** 14 November 2026  
**Status:** RESEARCH  
**Titles:** IKAI MIRROR+ × WARENA COMPUTE  
**Parents:** architecture dossier · product research · WARENA COMPUTE companion

This note advances the **joint** design of reflective embodiments and local compute. It does not authorise hardware purchase, NPU locks, or production stations.

---

## 1. Proposition

**Mirror** is the embodiment and presentation layer.  
**Compute** is the local-first runtime that owns perception, semantic state, permissions, and recovery.

They couple tightly in latency and privacy, but must stay **modular**: optics can change without rewriting the world model; compute can upgrade without redesigning the glass.

```text
┌──────────────────────────────────────────────────────────┐
│                 IKAI application families                  │
│         Beauty · Movement · Wellness (domain logic)        │
└────────────────────────────┬─────────────────────────────┘
                             │ semantic API / events
┌────────────────────────────▼─────────────────────────────┐
│              WARENA COMPUTE station runtime                │
│  capture → estimate → entity update → present → persist    │
│  Guix-defined · offline-capable · permissioned             │
└───────────┬─────────────────┬──────────────────┬─────────┘
            │                 │                  │
     ┌──────▼──────┐   ┌──────▼──────┐   ┌───────▼────────┐
     │  Sensors    │   │  Accelerators│   │  Embodiment    │
     │  RGB / depth│   │  CPU/GPU/NPU │   │  mirror / XR   │
     └─────────────┘   └─────────────┘   └────────────────┘
```

---

## 2. Why “advanced” is not “more cloud”

Industry and research trends push either:

- **Cloud-assisted** mirrors (orchestration on Pi, reasoning off-device), or  
- **Edge AI** mirrors (local inference for privacy and latency).

WARENA doctrine prefers **consumer-tier local inference by default**, with optional explicit network use. Advanced = **tighter local loops**, measurable latency budgets, reproducible station images — not mandatory SaaS.

Supporting literature directions (context, not adoption claims):

- **Internet of Mirrors (IoM)**-style pipelines: capture → pre-process → classify → deliver; placement can be consumer-only vs hub-assisted.  
- **Edge smart-mirror AI**: modular nodes (e.g. ROS 2–class), multi-model detection at interactive frame rates on tens of watts-class hardware in published experiments.  
- **Sensor → ISP → NPU** on-camera SoCs: low-latency vision paths; tooling and operator support vary by silicon vendor.

---

## 3. Station tiers (compute profiles)

| Tier | Codename | Compute class | Embodiment | Target workload |
|------|----------|---------------|------------|-----------------|
| **T0** | **Workbench** | Existing laptop/workstation (e.g. EliteBook-class research target) | Ordinary display or external monitor | MVP software (consultation aid, pose overlay) — **no** two-way glass required |
| **T1** | **Studio panel** | Mini-PC or laptop + bright panel | Optional two-way acrylic/glass (≥~300 nits panel guidance common in DIY literature) | MLP studio station: camera + overlays + local history |
| **T2** | **Edge AI station** | x86/ARM with GPU or NPU | Full-length or face-height mirror | Concurrent pose + face/gesture experiments; still local-first |
| **T3** | **Spatial station** | Higher GPU + OpenXR-capable path | Spatial display / HMD / future light-field | Phase 5 research only |

**Rules**

- Ship capability **up** the tier ladder only after the tier below is reproducible under Guix.  
- T0 is the **default advanced path for product learning** (see product research MVP).  
- T2/T3 are **research**, not SOM hardware.

---

## 4. Real-time pipeline (logical stages)

| Stage | Responsibility | Notes |
|-------|----------------|-------|
| **1. Capture** | Camera / mic frames with visible indicators | Consent gate before record |
| **2. Pre-process** | Crop, colour, mirror transform policy | Mirror L/R **after** pose estimate when using subject-relative landmarks |
| **3. Estimate** | Landmarks, optional segmentation | MediaPipe-class tools are **candidates**; confidence exposed |
| **4. Semantic update** | Map estimates → entities / events | Guile/GOOPS or domain store owns truth |
| **5. Policy** | Permissions, retention, app isolation | Beauty records ≠ movement records |
| **6. Present** | Composite reflection + graphics | Display path independent of semantic store |
| **7. Persist** | Local SQLite (or replaceable) + backup | Offline first |

Latency budget (research targets to **measure**, not promise):

| Loop | Aspiration for interactive feel |
|------|----------------------------------|
| Capture → overlay | Sub-100 ms class on T1/T2 once measured |
| Capture → heavy classify | May be slower; never block UI thread without feedback |
| Persist | Async; must not drop frames |

Published IoM-style work emphasises **placement** (all on consumer node vs hub). WARENA default: **consumer-only** for intimate imagery.

---

## 5. Optical–compute coupling

### 5.1 Conventional two-way mirror (Track A)

Physics constraint: glass/acrylic passes only part of panel light; ambient reflection competes. Practical guidance in public DIY/docs often cites **≥ ~300 nits** minimum panel brightness; commercial mirror-TV discussion cites much higher ranges (hundreds to thousands of nits) for strong ambient rooms.

**Compute implication:** prefer panels with accessible brightness/contrast controls; dark bezel/cavity; avoid dimming/power-save that collapses the digital image.

### 5.2 AIRR / MiTAI (Track B)

Optical path becomes a first-class subsystem (beam splitter, retroreflector, alignment). Compute must drive **content position / motion** coordinated with optics — still behind the same semantic API.

### 5.3 Spatial / OpenXR (Track C / Phase 5)

OpenXR **spatial container** directions aim at window-like spatial apps; DisplayXR-class runtimes target spatial displays. These are **interop candidates**, not the definition of IKAI.

---

## 6. Accelerator strategy

| Resource | Use |
|----------|-----|
| **CPU** | Orchestration, Guile runtime, policy, IPC |
| **GPU** | Composite, GL/Vulkan present, some CV |
| **NPU** (if present) | Optional fixed vision models; vendor toolchains often closed — treat as **ADAPT with caution** |
| **None** | T0 MVP must still work |

**Do not** design the product so that a specific NPU is mandatory for consultation history software.

---

## 7. Software runtime on the station

Aligned with prior WARENA / IKAI decisions:

| Layer | Direction |
|-------|-----------|
| OS image | Guix System / RDE-defined where practical |
| Domain logic | Guile + native CV boundary |
| Perception candidates | OpenCV, MediaPipe (evaluate under pins) |
| UI Phase 0 optional | MagicMirror²-class modules (non-camera PII) |
| Desktop research | X11 default research track; Wayland alt |
| Distribution | Default offline; explicit opt-in network |

---

## 8. Advanced capability matrix (ambition vs gate)

| Capability | Tier | Gate before claiming |
|------------|------|----------------------|
| Consultation history + WhatsApp | T0 | Used in real NAKEBUSEN appointment |
| Live camera overlay | T1 | Consent UI + indicator + local store |
| Full-body pose trails | T1/T2 | Measured FPS/latency; failure UI |
| Multi-model concurrent detect | T2 | Power + thermal log; accuracy notes |
| Two-way glass station | T1 | Brightness/contrast field test |
| AIRR breadboard | Lab | Optical plan + safety |
| OpenXR spatial window | T3 | Runtime eval on target hardware |
| Guix full station image | Any | `guix system` build + restore drill |

---

## 9. Power, thermal, always-on

Edge-mirror research often optimises **watts per frame** for home installation. WARENA stations should document:

- Idle vs active power (measured)  
- Thermal throttling under pose load  
- Display sleep policy that does not break “mirror as object” UX unexpectedly  
- Fan/acoustic limits for studio use  

Numbers from third-party papers (e.g. ~30 FPS multi-detect at tens of watts) are **orientation only** until replicated on WARENA pins.

---

## 10. Security & privacy at the compute boundary

| Control | Requirement |
|---------|-------------|
| Camera LED / UI indicator | Always when sensor active |
| Per-app data directories | Enforced |
| No silent upload | Default deny egress for media |
| Model files | Local; integrity pins where possible |
| Debug dumps | Redact faces/bodies by default |

---

## 11. Relation to product stages

| Product stage | Mirror + Compute focus |
|---------------|-------------------------|
| **MVP** | T0 software pipeline without optical assembly |
| **MLP** | T1 studio panel + consent store |
| **MaxVP** | T2/T3 + Track B/C optics as optional embodiments of the **same** runtime |

---

## 12. Open engineering questions

1. Minimum measured end-to-end latency for “acceptable” pose overlay on T1 hardware?  
2. Can Guile orchestrate frame loops without becoming the bottleneck?  
3. Which Guix packages exist today for MediaPipe/OpenCV vs what must be packaged?  
4. Is a dual-box design (optical head + external compute) better for heat than all-in-one?  
5. How to certify a station image for offline demo day?

---

## 13. Status line

**Advanced Mirror + Compute research only.** Station tiers and pipelines are design tools. No LIVE station, NPU commitment, or optical purchase is authorised by this document.
