# IKAI — Voice, Smart Glasses & Distributed Reflective Computing

**Date:** 18 November 2026  
**Status:** RESEARCH / ARCHITECTURE SPECIFICATION  
**Product status:** Not released. No wearable, voice pipeline, spatial display or assistant deployment is claimed.

## 1. Locked research decisions

| Dimension | Decision |
|---|---|
| Wearable scope | Both voice-only wearables and visual AR glasses |
| Intelligence placement | Hybrid: local control and sensitive processing by default; optional remote inference |
| Display philosophy | Central / first-class interaction surface |
| System identity | Distributed reflective-computing platform, not a single appliance |
| Interaction ethic | A mirror, not a judge; participant controls pace, interpretation, memory and exit |

IKAI is a Turkana female name meaning **home**. This informs the research interest in continuity, belonging and participant control; it is not a claim that a device can define identity.

## 2. Distributed topology

```text
Voice wearable ───┐
                  ├── Companion device ── IKAI Core (Guile/Scheme)
AR glasses ───────┘        │                    │
                           │                    ├── WARENA workstation
                           │                    │   Guix/RDE · Shepherd
                           │                    │   SQLite · media services
                           │                    └── optional remote gateway
                           └── pairing, status, fallback UI
```

- **Wearable:** capture only during explicit sessions; expose mute/capture state and device capabilities.
- **Companion:** pairing, transport, status, fallback controls and device-specific adapters.
- **IKAI Core:** session lifecycle, permission checks, event routing and participant-owned context.
- **WARENA workstation:** local persistence, media processing, reproducible environment and optional local inference.
- **Remote gateway:** optional, disabled by default; every transfer has a declared purpose, payload class, destination and retention rule.

The companion is a bridge, not the authority for consent. WARENA provides infrastructure but does not own participant records or interpretation.

## 3. Logical component contracts

These are proposed interfaces, not implemented APIs.

| Contract | Responsibility | Required semantics |
|---|---|---|
| `Device` | Pairing and capabilities | identity, transport, firmware, battery, connect/disconnect |
| `Media` | Audio/video lifecycle | source, format, start/stop, mute state |
| `Conversation` | Turn-taking | session, intent, interrupt, cancel, close |
| `Inference` | Model routing | task, data class, execution location, model/version, consent, timeout |
| `Spatial` | Pose/anchors/display | coordinate frame, timestamp, quality, anchor lifetime |
| `Permission` | Authorisation | principal, purpose, resource, scope, expiry, revocation |
| `Memory` | Participant records | owner, source, retention, export/delete |
| `Display` | Visual composition | surface, placement, opacity, priority, dismissal, fallback |

Every contract requires explicit failure and cancellation paths. Disconnect, permission expiry or service failure must stop capture and cancel pending work.

## 4. Hardware qualification matrix

Candidates only; not procurement advice or compatibility certification. Confirm exact model, revision, firmware and regional availability before selection.

| Candidate | Role | Qualification questions |
|---|---|---|
| Audio-first Bluetooth/open-ear frames | Voice-only MVP | Mic quality, physical mute, profiles, latency, battery, vendor-cloud dependence |
| Ray-Ban Meta family | Commercial reference case | Developer access, capture indicators, data routing, platform lock-in, repairability |
| XREAL Air 2 Ultra | Visual display / spatial research | SDK, OpenXR path, tracking limits, tethering, Linux/Android support |
| Android XR reference devices | XR runtime comparator | OpenXR support, permission controls, developer access, data flows |
| Android companion phone | Pairing and fallback | API access, USB/Bluetooth reliability, offline behaviour |
| x86-64 WARENA workstation | Local compute | CPU/GPU, RAM, thermals, drivers, Guix packaging and recovery |

Qualification gates: exact SKU and firmware; documented developer API; capture and privacy controls; mic/display/latency/thermal/battery measurements; offline and reconnect tests; synthetic data first. Record PASS / FAIL / NOT TESTED. Marketing claims are not compatibility evidence.

## 5. Research software stack

| Layer | Candidate | Purpose |
|---|---|---|
| System | GNU Guix + RDE | Reproducible workstation environment |
| Policy/orchestration | GNU Guile / Scheme | Session state, permissions and routing |
| Supervision | Shepherd | Service lifecycle and recovery |
| Persistence | SQLite | Local metadata and participant-authored records |
| IPC | Unix sockets; D-Bus selectively | Local typed component communication |
| Audio | PipeWire | Audio graph, routing and mute state |
| Media | GStreamer | Audio/video pipelines and codecs |
| Native UI | GNUstep / Objective-C first | Companion/workstation UI research |
| XR | OpenXR | Native spatial runtime abstraction |
| Graphics | Native graphics APIs | Display composition |
| Speech/vision | Local model and native CV candidates | Optional, purpose-bound processing |
| Remote inference | Explicit gateway adapter | Optional remote model execution |

JavaScript is prohibited as runtime, application language, framework or architectural dependency. WebXR is not the selected route. OpenXR and all listed frameworks remain candidates until source, licence, package, hardware and performance qualification is recorded.

### Upstream discovery register

- Guile: https://git.savannah.gnu.org/cgit/guile.git
- Guix: https://git.savannah.gnu.org/cgit/guix.git
- Shepherd: https://git.savannah.gnu.org/cgit/shepherd.git
- PipeWire: https://gitlab.freedesktop.org/pipewire/pipewire
- GStreamer: https://gitlab.freedesktop.org/gstreamer/gstreamer
- OpenXR SDK: https://github.com/KhronosGroup/OpenXR-SDK
- OpenXR headers and loader: https://github.com/KhronosGroup/OpenXR-SDK (generated SDK headers and loader); authoritative API specification and header sources: https://github.com/KhronosGroup/OpenXR-Docs; registry: https://registry.khronos.org/OpenXR/
- SQLite: https://github.com/sqlite/sqlite
- GNUstep: https://github.com/gnustep

These are discovery entry points, not endorsements or pinned dependencies. Inspect licence, maintenance, release/tag, dependencies, platform support, security advisories and Guix build status before adoption.

## 6. Guile/Scheme integration

Proposed module boundaries:

- `(ikai core session)` — lifecycle, state, cancellation and recovery.
- `(ikai device registry)` — pairing and capability negotiation.
- `(ikai permissions)` — purpose-bound grants, expiry and revocation.
- `(ikai media audio)` / `(ikai media video)` — PipeWire/GStreamer adapters.
- `(ikai inference router)` — local/remote selection under policy.
- `(ikai spatial scene)` — coordinate frames, anchors and display intent.
- `(ikai memory store)` — SQLite records, export and deletion.
- `(ikai transport)` — versioned IPC and wearable bridge.
- `(ikai audit)` — policy/lifecycle events without raw media by default.

Guile governs policy; native libraries own performance-sensitive media, graphics and drivers. Use maintained C interfaces and scoped bindings. Do not block the Scheme event loop on media or inference. Supervise long-running workers and bound queues. Begin with Unix sockets and deterministic mock devices; add D-Bus only where desktop integration warrants it.

## 7. Privacy and security threat model

**Assets:** speech, camera frames, spatial/pose data, transcripts, notes, device credentials, prompts, memory records and remote-service credentials.

**Threats:** accidental activation; capture of bystanders; lost devices; compromised vendor apps/firmware/cloud accounts; over-privileged local services; prompt injection from environmental content; unauthorised remote inference; linkability across time/location; capture continuing after disconnect.

**Controls:**
1. Microphone, camera and spatial capture default off; explicit session start.
2. Visible capture status and physical mute/disable controls where supported.
3. Permission grants bound to principal, purpose, resource, scope and expiry.
4. Local-first processing; remote processing requires explicit disclosure and authorisation.
5. No raw audio/video retention by default.
6. Participant inspection, correction, export and deletion; revocation stops future processing.
7. Least privilege, authenticated IPC, separated credentials and bounded device access.
8. No face identification, speaker identity matching, emotion/health/personality inference or capability scoring.
9. Environmental text/audio and model outputs are untrusted data, never privileged instructions.
10. Disconnect, timeout, crash or expiry stops capture and cancels pending tasks.
11. Audit permission changes and remote transfers without logging content.
12. Pin/update dependencies, document rollback and preserve reproducible build evidence.

A policy is not proof of privacy. Verify device telemetry, radio interfaces, storage, deletion and network egress for each qualified device.

## 8. MVP boundary

**Included:** Guile local session manager; companion with explicit start/stop; one documented voice-only wearable path; push-to-talk, interruption and cancellation; local speech evaluation with text fallback; optional local inference adapter; participant-authored notes; export/delete; synthetic device fixtures.

**Excluded:** custom/full AR glasses; continuous surveillance; face/biometric identification; emotion inference; unrestricted agents; long-term spatial memory; automatic personal profiling; automated choreography interpretation; mandatory remote inference/cloud memory; clinical or validated cognitive outcomes.

**Acceptance:** no capture before activation; tested mute/stop/disconnect; offline core interaction within measured model limits; every saved record accepted by participant; tested export/deletion; network trace with no unexplained egress; recorded build inputs, hardware, tests and limitations.

## 9. Staged implementation

| Stage | Work | Exit gate |
|---|---|---|
| 0 | Contracts, schemas, threat model, synthetic fixtures | Reviewed misuse/failure cases |
| 1 | Guile core, Shepherd, SQLite, Unix IPC | Deterministic lifecycle/restart tests |
| 2 | Voice wearable and companion | Offline, mute, disconnect and latency tests |
| 3 | Local speech/inference | Licence, resource and data-flow review |
| 4 | Visual display and one qualified AR device | Legibility, accessibility, thermal and spatial tests |
| 5 | Optional hybrid routing | Consent, retention and egress audit |
| 6 | GENJE participant-authored movement reflection | Separate method/consent review |
| 7 | Small usability study | Ethics, accessibility, deletion and safety gates |

Do not advance a stage on the strength of a demo alone.

## 10. Market framing

The earlier exploratory **US$6–38B annual global opportunity by 2030** is a scenario range for the convergence of smart glasses, voice interfaces, spatial computing and personal AI. It is not a measured IKAI market, forecast, valuation, SAM or SOM. Do not use it in investor or public marketing material until category definitions, source dates, geography, pricing, adoption assumptions and overlap/double counting are independently reconstructed.

## 11. Relationship to Mirror, Glass, GENJE and WARENA

- **IKAI Mirror:** stationary reflective environment and display/sensing research.
- **IKAI Glass:** voice and visual wearable interaction.
- **IKAI Space:** shared spatial and interaction model.
- **GENJE:** authored movement, choreography, livecoding and performance context; no automated interpretation of performers.
- **WARENA:** systems infrastructure, reproducible environments, local services and device integration.

Share permission, session and record contracts without forcing identical hardware or interaction patterns.

## 12. Open questions

- Which voice wearable exposes reliable audio interfaces without mandatory vendor cloud processing?
- Which AR glasses offer documented native/OpenXR development and workable Linux/Android paths?
- What is the minimum companion role?
- Which local speech models handle Kenyan English, Kiswahili and code-switching within target hardware limits?
- What spatial data is necessary for a user-directed task?
- How should optical fidelity and display legibility be measured?
- Which dependencies build reproducibly in Guix today?

## Evidence record

For every paper, standard, upstream project and device, record author/maintainer, date, URL, exact version, review depth, licence, claim supported and limitation. Distinguish metadata/abstract review from full-text and method review. This is a research specification, not a completed source audit or hardware test.
