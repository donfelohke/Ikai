---
title: Camera-Screen Bidirectional ReflectiveIO
---
# Camera-screen bidirectional ReflectiveIO

**Status: RESEARCH / PROPOSED ARCHITECTURE.** This article describes a research direction, not a working integrated system.

## The proposition

IKAI investigates an expanded path: **Physical scene → Camera → Capture pipeline → Processing → Display pipeline → Reflective surface → Human perception**. The human response closes the loop: the person interprets the output and decides whether to act.

## Distinguish the channels

- **Optical reflection:** light returned by the reflective surface.
- **Camera input:** sampled image data from a sensor.
- **Touch input:** explicit interaction through a touch surface or frame.
- **Compute:** processing, state transitions and application logic.
- **Display output:** pixels emitted by a display and transmitted through the optical assembly.
- **Human feedback:** perception, interpretation and intentional action.

A camera is not the same thing as a mirror. A display is not the same thing as reflection. Their alignment and timing must be measured.

## Real-time concerns

The research must account for frame rate and exposure, sensor-to-host transport, buffer ownership and copies, processing time and queue depth, timestamp quality and clock domains, camera synchronisation, display refresh, end-to-end latency and jitter, thermal throttling and device recovery.

For multiple streams, aggregate bandwidth is only one constraint. Synchronisation, memory traffic, buffer lifecycle, scheduling and processing cost can dominate.

## Linux research candidates

- **V4L2** for video capture devices.
- **Media Controller** for complex media pipelines where supported.
- **GStreamer** for multimedia pipeline composition and experimentation.
- **DRM/KMS** for display and modesetting.
- **ALSA** for audio I/O where needed.
- **USB, PCIe and MIPI CSI-2** as hardware transport/interface candidates.

These are candidates, not a final bill of materials or selected architecture. Guile/Scheme may coordinate services and application logic while performance-sensitive capture, image processing and rendering use appropriate native libraries.

## Benchmark design

Measure capture timestamp to host availability; host availability to processing completion; processing completion to display submission; display submission to visible presentation; input event to visible response; inter-stream timestamp deviation; dropped frames, queue growth and recovery time.

Report distributions (median, p95, p99), not just a single average. State hardware, driver, resolution, pixel format, frame rate, exposure, workload and test duration.

## Privacy boundary

Camera availability is not consent. Capture must be visible, purpose-limited, revocable and disabled by default where the use case does not require it. A useful non-camera path must remain available. No face identification, biometric matching, hidden profiling or covert recording is permitted.

## Open questions

Which camera/display topology is best? Is hardware synchronisation needed? Which buffer-sharing mechanisms are supported by the selected devices? What latency is necessary for each application? What is the minimum useful number of simultaneous streams? These questions require comparative tests before a new ABI or runtime is justified.
