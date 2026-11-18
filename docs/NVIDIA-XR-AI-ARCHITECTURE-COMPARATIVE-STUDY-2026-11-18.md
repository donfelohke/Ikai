# IKAI — NVIDIA XR AI Architecture Comparative Study

**Date:** 18 November 2026  
**Status:** RESEARCH / INDUSTRIAL ARCHITECTURE COMPARISON  
**Authority:** IKAI owns reflective interaction and participant semantics; WARENA owns platform and service integration.  
**Maturity:** Comparative study only. No NVIDIA component, GPU, model, runtime or service is selected or deployed.

## 1. Purpose

Evaluate NVIDIA's public XR AI stack as an industrial reference for IKAI's voice, smart-glasses and spatial-computing research. The purpose is to identify reusable architectural ideas and their limits, not to make NVIDIA XR AI the IKAI foundation.

Official project description: XR AI connects interactive clients—including XR glasses and headsets, phones and browser clients—to a shared media hub, agent workers, AI services and tools. Optional CloudXR integration supports remote-rendered AR/XR. The project is public beta; APIs and behaviour may change.

## 2. Architecture observed in upstream documentation

NVIDIA documents four cooperating planes:

| Plane | NVIDIA responsibility | IKAI research interpretation |
|---|---|---|
| Media | DeviceIOHub, transport connector, participant-tagged media/data and optional capture | Device adapters and media transport separated from reflective policy |
| Application | Agent workers, participant state, tasks, model/tool orchestration, cancellation and concurrency | IKAI session and workflow services; Scheme owns policy |
| Service | Typed model clients, inference endpoints, tools and capability services | Replaceable local/remote inference and bounded native tools |
| Control | Orchestrator and launcher for startup ordering, readiness, process lifetime and shutdown | Shepherd-supervised services and explicit lifecycle contracts |

These are responsibility boundaries, not necessarily separate machines. Services may run on one host while model endpoints are local or remote.

### Main components and ownership

| Component | Upstream responsibility | Architectural lesson |
|---|---|---|
| XR client | Capture, presentation and user interaction | Client does not own agent execution or service orchestration |
| Transport connector | Transport sessions and conversion to hub events | Keep transport-specific code behind an adapter |
| DeviceIOHub | Media fan-out, participant identity, return routing and shared-media access | Preserve participant-scoped routing and isolation |
| Optional session capture | Timestamped media/events and workflow projections | Recording must be a separate, explicit capability |
| Agent SDK | Hub IPC, typed events, model protocols, voice composition and tools | Keep worker-facing contracts small and typed |
| Agent worker | Application state, tasks, prompts, model/tool loops, concurrency and cleanup | Application owns its state and cancellation |
| Model services | Inference and model-specific serving | Separate model serving from application policy |
| Tools/capability services | Bounded application capabilities | Tools should have narrow, declared authority |
| Orchestrator/launcher | Process declarations, startup order, readiness and shutdown | Make lifecycle and failure behaviour explicit |

### Runtime paths

A representative voice interaction is composed from audio input, voice activity detection, speech recognition, an application worker, language or vision-language inference, tools and speech synthesis. This is a composable path, not a mandatory fixed pipeline.

The upstream design keeps video pixels in shared memory and uses lightweight frame notifications; a worker requests a frame when the application needs one. Typed model factories isolate LLM, VLM, STT, TTS and embedding provider details. Tool selection, retries, task lifetime and participant context remain application-worker responsibilities.

The upstream documentation also describes participant-scoped return routing and process readiness separately from client readiness. These distinctions are useful for IKAI's failure and session contracts.

## 3. Relevant upstream packages and services

The current documentation identifies these principal package boundaries:

- `xr-ai-hub` — hub IPC.
- `xr-ai-models` — typed model protocols, profiles and clients.
- `xr-ai-runtime` — agent registration and participant-scoped event fan-out.
- `xr-ai-tools` — tool primitives and relay-managed tools.
- `xr-ai-voice` — voice agent and media composition.
- `xr-ai-web-events` — selected application-event views for browser clients.

NVIDIA XR AI uses a process-oriented architecture and documents MessagePack over ZeroMQ IPC between agent workers and the hub. Transport integrations and model-specific protocols are kept behind these interfaces.

Optional CloudXR integration is a remote-rendering path. It is not the same thing as OpenXR, which is an application/runtime interoperability API. IKAI should keep spatial API, runtime, renderer and remote-rendering decisions separate.

## 4. What IKAI should study or adapt

1. **Explicit planes of responsibility.** Keep media, participant experience, inference and process control independently replaceable.
2. **Participant-scoped routing.** Prevent cross-session data or response leakage.
3. **Typed model adapters.** Keep model-provider protocols out of core reflective-computing policy.
4. **Application-owned cancellation.** A user stop, disconnect or permission expiry must cancel work throughout the pipeline.
5. **Process readiness and health.** Distinguish service startup from device/session readiness.
6. **Media/data separation.** Avoid placing raw media in ordinary application events or model tool results.
7. **On-demand visual capture.** Prefer explicit still-frame requests to continuous video transfer when a task permits.
8. **Optional service composition.** Deterministic local tools should work without a model call.
9. **Replaceable transports and models.** Keep vendor-specific adapters at the boundary.

These are design observations. They do not establish that an IKAI implementation exists.

## 5. What IKAI should not inherit by default

| Upstream characteristic | IKAI decision |
|---|---|
| NVIDIA GPU-oriented deployment and model ecosystem | Treat as an optional acceleration/provider path, not a system requirement |
| Python-centric agent SDK and samples | Use as a comparative implementation; IKAI policy and orchestration remain Guile/Scheme-led |
| Browser and web clients | Do not adopt browser/JavaScript runtime architecture under WARENA policy |
| LiveKit transport integration | Evaluate only if a concrete interoperability need justifies it; not a mandatory transport |
| CloudXR remote rendering | Optional external capability; not the default spatial architecture |
| Optional raw session capture | Do not enable by default; participant-controlled capture and retention gates remain mandatory |
| Public-beta APIs | Pin exact commits/releases and re-audit before any future integration |

The Apache-2.0 project licence does not automatically relicense third-party dependencies or models. Review the repository's third-party notices, model terms, data flows and GPU/driver requirements independently.

## 6. IKAI / WARENA mapping

| NVIDIA concept | IKAI / WARENA candidate |
|---|---|
| XR client | Voice wearable, visual glasses, phone, mirror or workstation adapter |
| Transport connector | Native device/transport adapter with explicit capability contract |
| DeviceIOHub | A minimal IKAI media/event broker, if needed after the single-host MVP |
| Agent worker | Bounded IKAI application service |
| Agent SDK | Versioned Scheme records and IPC contracts |
| Typed model clients | Scheme-facing inference adapter with native service workers |
| Tool/capability service | Least-privilege local service with explicit permission checks |
| Orchestrator/launcher | Guix-defined services supervised by Shepherd |
| Session capture | Separate opt-in recording service with retention and deletion controls |
| CloudXR | Optional remote-rendering integration research, distinct from OpenXR |

For the initial IKAI MVP, do not recreate the full NVIDIA topology. A single-host Guile core, SQLite store, one voice path, a small number of supervised native workers and deterministic test fixtures are sufficient to validate the core contracts. Introduce a media broker or distributed workers only when measured requirements justify them.

## 7. Privacy and safety review

The NVIDIA architecture's participant routing and media separation are useful engineering patterns, but they do not by themselves establish privacy, consent or safe inference.

IKAI requirements remain:

- Capture off until a participant starts an explicit session.
- Visible capture and mute state, with accessible stop controls.
- No raw audio/video retention by default.
- Participant-scoped media, events, model requests and return output.
- No face identification, speaker identity matching, emotion/health/personality inference or capability scoring.
- Environmental media and model outputs are untrusted data, not privileged instructions.
- Remote inference requires a declared purpose, destination, payload class, consent and retention statement.
- Disconnect, permission expiry, cancellation or service failure stops capture and pending work.
- Inspection, correction, export and deletion are testable, not merely policy text.

Session recording is a separate feature requiring its own explicit activation, scope, storage, retention and deletion review.

## 8. Qualification gates before any integration

- Pin the upstream release/commit and inspect its migration notes.
- Record licence and third-party component/model terms.
- Map network ports, TLS, credentials, media paths and external egress.
- Identify required NVIDIA GPU, driver, CUDA/NIM and CloudXR components per sample.
- Test participant isolation, disconnect, cancellation and readiness behaviour.
- Measure audio/video latency, frame transfer, CPU/GPU and memory costs.
- Verify local-only operation and behaviour when remote services are unavailable.
- Compare a native Guile/Scheme orchestration prototype against the external worker model.
- Record replacement paths for transport, inference provider and renderer.

A successful upstream demo is not IKAI compatibility evidence. A build is not a device qualification. A qualified device is not a deployment.

## 9. Research conclusion

NVIDIA XR AI is a valuable industrial reference for multimodal agent composition, participant-scoped media routing, typed model interfaces and process lifecycle management. Its strongest contribution to IKAI is architectural separation, not a ready-made foundation.

**Recommended disposition:** REFERENCE / COMPARATIVE STUDY. Borrow the responsibility boundaries and testable invariants; preserve IKAI's Guile/Scheme-led, local-first, human-governed architecture and WARENA's vendor-independent infrastructure policy.

## 10. Primary sources

1. [NVIDIA XR AI — project overview](https://nvidia.github.io/xr-ai/)
2. [NVIDIA XR AI — architecture](https://nvidia.github.io/xr-ai/main/overview/architecture.html)
3. [NVIDIA XR AI — Agent SDK](https://nvidia.github.io/xr-ai/main/components/agent-sdk.html)
4. [NVIDIA XR AI — source repository](https://github.com/NVIDIA/xr-ai)
5. [NVIDIA XR AI — release migration notes](https://nvidia.github.io/xr-ai/main/reference/migrations.html)
6. [NVIDIA XR AI — releases](https://github.com/NVIDIA/xr-ai/releases)

**Source limitations:** this is an architecture-document review, not a full source-code audit, reproducible build, security assessment or hardware test. The upstream project is public beta and its API, package names and deployment instructions may change.
