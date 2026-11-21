---
title: REFLECTION± — Light In, Light Out, Compute
description: Optical acquisition, computation, emission and reciprocal feedback.
---
# REFLECTION± — Light in, Light out, compute

**Status: RESEARCH / PROPOSED ARCHITECTURE.** No integrated REFLECTION± implementation is claimed.

REFLECTION± investigates **bidirectional optical–computational systems**:

**LIGHT IN → COMPUTE → LIGHT OUT → ENVIRONMENT / HUMAN RESPONSE → LIGHT IN**

The system acquires optical information, transforms it and emits or modulates light. The output changes what a person or environment sees and may affect subsequent input.

## Distinguish the physical operations

- **Reflection:** light is returned by an optical surface.
- **Transmission:** light passes through a material.
- **Detection:** a sensor measures incident optical energy.
- **Computation:** information is transformed.
- **Emission/modulation:** a display or optical device generates or controls outgoing light.

A passive mirror does not compute. A camera is not a mirror. A display is not a reflective surface. Their integration must be engineered and measured.

## Architecture

1. Optical scene and illumination.
2. Acquisition: CMOS/CCD, event sensors, ToF, photodiodes or spectral sensors.
3. Transport and timestamps: CSI-2, USB, Ethernet, PCIe or device-specific interfaces.
4. Compute: CPU/GPU/DSP/FPGA baseline; photonic processing as a separate experimental track.
5. Output transport and rendering.
6. Optical output: LCD/OLED/microLED, projection, LED/laser or spatial light modulation.
7. Human interpretation, participant-directed action and feedback.

These are logical layers. They do not prescribe one device topology.

## Research findings to carry forward

- Computational optical imaging co-designs physical optics and digital reconstruction. It is a stronger foundation than treating software as an afterthought. See Wang et al., [Computational optical imaging: on the convergence of physical and digital layers](https://hub.hku.hk/bitstream/10722/361862/1/content.pdf?accept=1), *Optica* (2025).
- Event cameras asynchronously report brightness changes rather than conventional fixed-rate frames. Their temporal characteristics are useful for selected fast-motion tasks, but require event-aware algorithms. See [Gallego et al. (2022)](https://doi.org/10.1109/TPAMI.2020.3008413).
- MIPI CSI-2 v4.2 (adopted 15 December 2025) includes protocol support for event-based vision sensor use cases. Device implementation and conformance remain hardware-specific. [MIPI CSI-2](https://www.mipi.org/specifications/csi-2).
- MIPI DSI-2 v2.2 is an established host-to-display interface; it is not universal across panels and projectors. [MIPI DSI-2](https://www.mipi.org/specifications/dsi-2).
- Linux provides established media/display interfaces: [V4L2](https://docs.kernel.org/userspace-api/media/v4l/v4l2.html), [DRM/KMS](https://docs.kernel.org/gpu/drm-kms.html), and [GStreamer clock/latency facilities](https://gstreamer.freedesktop.org/documentation/application-development/advanced/clocks.html).
- IEEE 1588 PTP can synchronise clocks on supported networked systems; it does not automatically synchronise sensor exposure or display photons. [IEEE 1588-2019](https://standards.ieee.org/ieee/1588/6825/).
- Photonic computing is an experimental comparison, not a default architecture. Optical/electrical conversion, nonlinear operations, calibration and system integration must be counted. See [Farmakidis et al. (2024)](https://doi.org/10.1038/s44287-024-00050-9).

## Real-time requirements

Measure the complete path, not only frame rate:

- exposure/readout;
- transport and queueing;
- processing and rendering;
- display submission, scanout and optical response;
- clock offset and inter-stream skew;
- dropped frames/events and recovery.

Report median, p95, p99, maximum observed latency, jitter, throughput and test duration. Motion-to-photon latency is a physical measurement; use a repeatable high-speed-camera method where appropriate. See [Measuring motion-to-photon latency](https://pmc.ncbi.nlm.nih.gov/articles/PMC10616216/).

## Experimental sequence

1. Passive optical assembly and mirror comparison.
2. Display-through-surface luminance, contrast and thermal tests.
3. Optional camera acquisition using non-identifying calibration targets.
4. Local compute-to-display latency baseline.
5. Controlled closed-loop feedback.
6. Event-camera comparison for a defined fast-motion task.
7. Multi-device synchronisation and scaling.
8. Photonic-compute comparison only for a workload with a measured electronic baseline.

All are proposed experiments. Do not infer implementation or validation from this article.

## Ecosystem responsibilities

- **IKAI:** reflective experience, optics, participant authority and integration research.
- **WARENA:** native device interfaces, compute, timing, infrastructure and reproducibility.
- **NAKEBUSEN:** practical beauty/loc-care context and sole commercial interface.
- **GENJE:** movement, choreography, livecoding and embodied creative practice.
- **FELOH Corpus:** shared terminology, evidence, provenance and governance.

No face identification, biometric matching, person scoring, diagnosis, emotion inference, covert recording or hidden profiling. Camera availability is not consent. Preserve a useful non-camera path and participant control.

## Primary research record

See [REFLECTION± — Light In, Light Out, Compute (2026-11-21)](../../docs/REFLECTION-PLUS-MINUS-LIGHT-IN-LIGHT-OUT-COMPUTE-RESEARCH-2026-11-21.md) for the full research dossier, standards map, annotated bibliography, evidence labels, research gaps and experimental programme.
