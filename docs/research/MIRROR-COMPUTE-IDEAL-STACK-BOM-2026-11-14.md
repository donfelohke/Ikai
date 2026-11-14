# Mirror + Compute · Ideal stack & Bill of Materials (today)

**Date:** 14 November 2026  
**Status:** RESEARCH · PROCUREMENT GUIDANCE (not a purchase order)  
**Parents:** Mirror+Compute advanced · product research · WARENA station tiers

**Rules**

- Prices are **indicative global ranges** in USD; Kenya landed cost (import, VAT, shipping) is **higher and must be quoted locally**.  
- Prefer **reuse existing hardware** (T0) before buying.  
- Guix/RDE pins remain **RESEARCH** until build evidence on a named host.  
- ONLY **NAKEBUSEN** transacts commercially; this BoM is R&D / studio tooling.

---

## 1. Ideal stack (logical) — one diagram

```text
APPLICATIONS
  NAKEBUSEN consult · GENJE movement · IKAI wellness
        │
RUNTIME
  Domain logic (Guile / local services)
  Perception adapters (OpenCV / MediaPipe candidates)
  Local store (SQLite) + backup (restic candidate)
        │
OS / CONFIG
  GNU Guix + RDE (target) · interim: existing Linux for T0 spikes
  X11 research default · Wayland/dwl-guile alternate
        │
HARDWARE TIER
  T0 workbench → T1 studio panel → T2 edge AI → T3 spatial (later)
```

---

## 2. Software stack — ideal *today*

### 2.1 Production-minded path (aligned with WARENA research)

| Layer | Ideal choice | Role | Maturity label |
|-------|--------------|------|----------------|
| Package/OS | **GNU Guix** (+ **RDE** features) | Declarative system + home | RESEARCH until host evidence |
| Init | **GNU Shepherd** | Services | with Guix System |
| Language | **GNU Guile 3.x** | Domain + policy | core direction |
| Native CV | **OpenCV** (Guix package where available) | Capture, geometry | evaluate pins |
| Pose/landmarks | **MediaPipe** or lighter alternatives | Estimates only | candidate; packaging effort |
| Local DB | **SQLite** | History, consent flags | default |
| Backup | **restic** | Station restore | candidate |
| Optional HUD | **MagicMirror²** | Non-camera info modules | Phase 0 experiments only |
| Desktop WM | **X11 baseline** (i3 / EXWM / research Guile-WM) | Daily driver research | not locked |
| Wayland alt | **dwl-guile** + home-service | Scheme compositor | RESEARCH |
| Browser | **ungoogled-chromium** or policy-approved browser | Docs, WhatsApp Web if needed | optional |
| Editor | **Emacs** | Development | WARENA practice |

**Do not require:** cloud LLM, proprietary fitness subscription, mandatory NPU SDK, Face-ID scoring.

### 2.2 Interim spike path (fast learning, T0)

If Guix image is not yet bootstrapped on the machine in hand:

| Layer | Acceptable interim |
|-------|-------------------|
| OS | Existing Debian/Devuan/Arch **or** current Guix host |
| Language | Python + OpenCV **or** Guile bindings as available |
| UI | Simple local web UI or GTK for consult MVP |
| Contact | WhatsApp deep link (existing NAKEBUSEN path) |

Interim spikes must still obey **consent, local storage, no silent upload**. Promote proven pieces into Guix manifests later.

### 2.3 Explicitly deferred

| Item | Why |
|------|-----|
| AIRR / MiTAI optics | Track B research |
| OpenXR spatial runtime | T3 |
| GNU Hurd | Parallel research, not station default |
| Full MagicMirror as product shell | Security/model mismatch for camera PII |

---

## 3. Hardware — ideal *today* by tier

### T0 — Workbench (ideal **now** for MVP)

**Goal:** Ship consultation/movement software learning with **zero new optics**.

| Item | Spec guidance | Qty | Notes |
|------|---------------|-----|-------|
| Computer | **Existing** research laptop (e.g. HP EliteBook-class / Ryzen or Intel modern U-series, ≥16 GB RAM, ≥512 GB SSD) | 1 | Prefer what is already owned |
| Webcam | USB 1080p, fixed-focus or autofocus; UVC | 1 | Mount stable; cover when off |
| Optional second display | Any HDMI/USB-C monitor | 0–1 | Client-facing preview |
| Lighting | Soft LED panel or ring, high CRI if beauty work | 1 | Consistency > luxury brand |
| Storage offline | External SSD for Guix images / backups | 1 | Label `warena-backup` |
| Network | Existing LAN/Wi-Fi; ability to **air-gap** demos | — | Default deny media egress |

**BoM cost if buying only webcam + light + SSD:** often on the order of **USD 50–200** equivalent before local import — verify local quotes.

### T1 — Studio panel (ideal **next** for MLP)

**Goal:** Face- or torso-height station; optional two-way mirror; still local-first.

| Item | Spec guidance | Qty | Notes |
|------|---------------|-----|-------|
| Compute | Fanless or quiet **mini-PC**: Intel N100/N150-class **or** Ryzen equivalent; **≥16 GB RAM**; **≥512 GB NVMe** | 1 | Prefer Linux-friendly firmware |
| *Alt compute* | Raspberry **Pi 5 (8 GB)** | 1 | Good for MagicMirror-class HUD; **weaker** for heavy pose; MM² docs target Pi 2–5 with full desktop OS |
| Display | IPS **≥21–27"**, **≥300 nits**, accessible brightness controls; HDMI | 1 | Brighter is better behind two-way glass |
| Two-way panel | Optical acrylic or glass **two-way** (e.g. ~50/50 class) sized to display | 0–1 | Optional; skip until software sticks |
| Frame / cavity | Light-sealed dark enclosure, vented for compute | 1 | DIY wood/aluminium |
| Camera | USB 1080p **or** Pi Cam if Pi-based | 1 | Visible LED / UI indicator |
| Mic (optional) | USB mic | 0–1 | Voice later |
| Cabling | HDMI, USB, power; strain relief | set | |
| Mount | VESA or wall bracket rated for weight | 1 | Safety first |
| UPS (optional) | Small line-interactive | 0–1 | Studio power stability |

**Indicative hardware band (no glass):** mini-PC class often **USD ~200–500** online list; Pi 5 kit lower; **display + frame** highly variable. **With two-way glass/acrylic:** add substantial material cost — quote Kenya suppliers.

### T2 — Edge AI station (research, not SOM)

| Item | Spec guidance | Qty |
|------|---------------|-----|
| Compute | Mini-PC or NUC-class with **strong iGPU** and/or **NPU** (e.g. Core Ultra class) **or** Jetson-class if CUDA path justified | 1 |
| RAM | **32 GB** preferred | 1 |
| Storage | **1 TB** NVMe | 1 |
| Camera | Global-shutter or higher-quality UVC; optional depth later | 1 |
| Display | Same as T1 or dual | 1 |
| Thermals | Measure under sustained pose load | — |

**NPU is optional.** Do not block product on vendor SDK availability.

### T3 — Spatial (out of BoM for today)

OpenXR-capable HMD or spatial display — **catalogue only**, no BoM line items until Phase 5 gate.

---

## 4. Consolidated BoM tables

### 4.1 T0 — buy list (if nothing on hand)

| # | Part | Priority | Indicative |
|---|------|----------|------------|
| 1 | USB 1080p webcam | P0 | Low |
| 2 | Soft key light / ring | P0 | Low |
| 3 | 1 TB USB SSD (images + backup) | P1 | Low–mid |
| 4 | Tripod / clamp for camera | P1 | Low |
| 5 | Privacy webcam cover | P0 | Trivial |

### 4.2 T1 — buy list (studio station)

| # | Part | Priority | Indicative |
|---|------|----------|------------|
| 1 | Mini-PC ≥16 GB / 512 GB **or** Pi 5 8 GB + NVMe hat if used | P0 | Mid |
| 2 | Bright IPS monitor ≥21" | P0 | Mid |
| 3 | USB camera | P0 | Low |
| 4 | Enclosure / frame materials | P1 | Variable |
| 5 | Two-way acrylic/glass | P2 | Defer |
| 6 | VESA mount | P1 | Low |
| 7 | Quality HDMI + power | P0 | Low |

### 4.3 Consumables / ops

| Item | Purpose |
|------|---------|
| Labels, asset tags | Station identity |
| Consent paper/digital template | Legal/ethics process |
| Cleaning cloth (non-abrasive) | Glass/panel |
| Spare USB cables | Field |

---

## 5. Kenya / Eldoret practical notes

| Topic | Guidance |
|-------|----------|
| Sourcing | Prefer Nairobi/Eldoret available mini-PCs and monitors; verify warranty |
| Power | Voltage stability; surge protection |
| Import | Factor duty on acrylic optics and specialised glass |
| Internet | Design demos that work **offline**; WhatsApp only for human booking |
| Repair | Prefer standard HDMI/USB parts over locked appliance firmware |

---

## 6. Stack ↔ product stage mapping

| Stage | Stack profile | BoM |
|-------|---------------|-----|
| **MVP beauty** | T0 + interim or Guix dev shell | Webcam + light (+ existing PC) |
| **MLP studio** | T1 Guix-leaning station | Mini-PC + bright panel + camera |
| **GENJE pilot** | T0/T1 same | Same camera path |
| **MaxVP** | T2/T3 + Track B optics | Separate gated BoM |

---

## 7. Acceptance before calling a station “ideal”

| Check | Pass criterion |
|-------|----------------|
| Boot | Documented image or known OS boots |
| Camera | Preview + cover behaviour |
| Consent | Explicit gate before record |
| Offline | Core loop without WAN |
| Backup | One successful restore drill |
| Latency | Overlay usable (measured, not assumed) |
| Brand boundary | No fake medical/fitness claims on UI |

---

## 8. Status line

**Ideal stack and BoM are research recommendations for 14 Nov 2026.**  
They are **not** a purchase order, inventory, or LIVE deployment record. Update prices and SKUs only after local quotes and Guix pin evidence.
