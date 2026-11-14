# MAVERIK — source locations, study notes, alternatives

**Date:** 14 November 2026  
**Status:** RESEARCH  
**Parent:** [IKAI-MIRROR-PLUS-ARCHITECTURE-2026-11-14.md](./IKAI-MIRROR-PLUS-ARCHITECTURE-2026-11-14.md) · [IKAI-MIRROR-PLUS-FURTHER-RESEARCH-2026-11-14.md](./IKAI-MIRROR-PLUS-FURTHER-RESEARCH-2026-11-14.md)

This note locates the GNU MAVERIK source, summarises what is known from public archives and literature, compares alternatives, and records dispositions for IKAI / WARENA. **No build or integration is claimed.**

---

## 1. Source locations (verified as published archives)

| Source | Content | Notes |
|--------|---------|--------|
| **[ftp.gnu.org/gnu/maverik/](https://ftp.gnu.org/gnu/maverik/)** | Official GNU tarballs | Prefer **`maverik-6.5.tar.gz`** (2013-03-15, ~4.9 MiB) + `.sig` |
| GNU mirrors (dotsrc, Belnet, TWDS, Debian mirror paths, …) | Same tree | Mirror of ftp.gnu.org |
| **[Fossies — maverik 6.5](https://fossies.org/linux/misc/old/maverik-6.5.tar.gz/)** | Browseable archive | README, COPYING, FAQ, INSTALL, src/, demos/, examples/ |
| **[Savannah project: maverik](https://savannah.gnu.org/projects/maverik)** | GNU project page | License stated **GPL-3.0-or-later** on Savannah summary; Development Status: Mature |
| **[Savannah Bazaar](https://savannah.gnu.org/bzr/?group=maverik)** | VCS | `bzr://bzr.savannah.gnu.org/maverik/` — historical; not actively used as modern primary workflow |
| AIG Manchester historical site | Historical download/gallery | Often offline or stale; do not depend on it |

**Recommended recovery pin for any future audit:** `maverik-6.5.tar.gz` from ftp.gnu.org with signature verification.  
**SHA256 (Fossies-reported):** `3ed567bcb685048c597e6795826b9d6df5fc98b9bae45e0b5645614175b81654` — re-verify on download.

**Not found in this pass:** an active, modern GitHub “upstream” fork maintained as the GNU package of record. FreeBSD port was **deprecated/expired** (unmaintained narrative; last relevant notes ~2014).

---

## 2. Archive layout (Fossies / 6.5 tree — high level)

Public listing of `maverik-6.5.tar.gz` shows, among other paths:

| Path | Role |
|------|------|
| `README`, `INSTALL`, `FAQ`, `NEWS`, `ChangeLog` | Build and orientation |
| `COPYING` | Licence text in tarball |
| `src/` | Core library / micro-kernel and modules |
| `src/extras/` | Extra components |
| `examples/` | Small examples (e.g. text) |
| `demos/` | Larger demos (e.g. LegibleCity data) |
| `vc++/` | Historical Windows project files |
| `README-GTK`, `README-QT` | Optional GUI notes |

**This pass did not unpack the tarball in a build environment.** File-level API maps (exact callback registration symbols) remain **UNVERIFIED** until a local extract + header read.

---

## 3. Architecture study (source + literature synthesis)

### 3.1 Design thesis

MAVERIK is a **C micro-kernel + supporting modules** above Mesa/OpenGL. It deliberately **does not own the application’s primary VE data structures**. Applications register **classes** and **methods implemented as callbacks**; the kernel drives navigation, spatial management, and invokes callbacks for display/interaction.

### 3.2 Two layers

1. **Micro-kernel** — class/method registry, core services, framework for VE construction.  
2. **Supporting modules** — default culling, spatial management structures (SMS), interaction, navigation, device I/O — **overridable** so they can operate on application data.

### 3.3 Why it differed from “import into scene graph” systems

| Conventional retained scene graph | MAVERIK pattern |
|-----------------------------------|-----------------|
| Convert/import geometry into toolkit format | Keep application structures authoritative |
| Toolkit optimises a generic graph | Application optimises with domain knowledge |
| Duplicate data risk | Single representation |
| Hard for non-affine / deformable dynamics | Callbacks can read live application state |

### 3.4 Pairing with DEVA

MAVERIK = single-user graphics/interaction half. **DEVA** = distributed multi-user behaviour/laws. Complementary, not substitutes.

### 3.5 Practical revival risks (hypothesis until tested)

- Age of build system and OpenGL usage patterns  
- 32-bit-era assumptions in older releases (6.5 claimed 32/64 support by GNU page)  
- Device modules for obsolete VR peripherals  
- Sparse modern CI / package presence in Guix  
- Savannah activity is minimal (mature / historical)

**Disposition:** **EXTRACT** the architectural pattern for IKAI. **REVIVE** full MAVERIK only after a signed download, licence confirmation against `COPYING`, configure/make on a pinned Guix shell, and a minimal demo run. Until then, status = **HISTORICAL SOURCE AVAILABLE, BUILD UNKNOWN**.

---

## 4. Alternatives — compare and contrast

### 4.1 Comparison matrix

| System | Data ownership model | Graphics API | Language | Maturity / maintenance | Licence (typical) | Fit for IKAI |
|--------|----------------------|--------------|----------|------------------------|-------------------|--------------|
| **MAVERIK** | App-owned + callbacks; no mandatory internal VE DB | OpenGL/Mesa | C | Historical (last tarball 2013) | GPL (tarball + Savannah GPL-3+) | **Concept extract**; revive gated |
| **OpenSceneGraph (OSG)** | Retained **scene graph** (DAG); app usually mirrors state into nodes | OpenGL | C++ | Mature but OpenGL-era; succession pressure | OSG licence (LGPL-style historically; verify per release) | Strong for large 3D; **not** MAVERIK’s “no graph” thesis |
| **VulkanSceneGraph (VSG)** | Modern scene graph; performance-focused; OSG conceptual successor | Vulkan | C++17 | Active modern project | Verify per release | Prefer for **new** heavy 3D if a graph is acceptable |
| **Raw OpenGL / Vulkan + custom SMS** | Fully app-owned | OpenGL or Vulkan | C/C++ | DIY | N/A | Closest **spirit** to MAVERIK without bitrot |
| **Godot** | Engine-owned scene tree; custom `_draw` / nodes possible | GLES/Vulkan | GDScript/C#/C++ | Active | MIT | Possible prototype host; heavy policy; not local-first mirror OS |
| **MagicMirror²** | Module UI on Electron; not a 3D VE kernel | Web/Electron | JS | Active modular smart-mirror | MIT | Phase-0 **2D overlay** only |
| **Stardust XR** | Spatial display server (2D+3D) | Wayland/XR stack | — | Emerging | Verify | Phase-5 spatial desktop, not Phase-1 |

### 4.2 Contrast in one sentence each

- **MAVERIK vs OSG/VSG:** MAVERIK refuses a mandatory internal scene database; OSG/VSG **are** retained-mode scene graphs optimised for traversal and GPU submission.  
- **MAVERIK vs raw GL/Vulkan:** Same ownership philosophy; modern stack loses MAVERIK’s ready-made SMS/nav defaults but gains maintainability.  
- **MAVERIK vs Godot:** Godot maximises product velocity and engine policy; MAVERIK minimises framework ownership of domain data.  
- **MAVERIK vs MagicMirror²:** Different problem (3D VE toolkit vs modular 2D smart-mirror shell).

### 4.3 Recommended strategy for IKAI MIRROR+

```text
Semantic world model (Guile/GOOPS / domain store)
        │  owns entities, provenance, permissions
        ▼
Spatial model (frames, anchors, calibration)
        │
        ├── Perception (MediaPipe/OpenCV, …)  → estimates, not truth
        │
        └── Presentation adapters
              ├── Phase 1: 2D mirror composite (camera + overlays)
              ├── Optional: custom OpenGL/Vulkan draw path (MAVERIK-like ownership)
              ├── Optional later: VSG if complex 3D assets justify a graph
              └── Phase 5: spatial desktop (Stardust XR evaluate)
```

**Do not** import MAVERIK as a production dependency without a successful Guix build gate.  
**Do** treat its callback + app-owned data rule as a **constitutional constraint** on the presentation layer.

---

## 5. Evidence register

| Claim | Status | Source |
|-------|--------|--------|
| `maverik-6.5.tar.gz` exists on ftp.gnu.org and mirrors | VERIFIED (directory listings) | [ftp.gnu.org/gnu/maverik](https://ftp.gnu.org/gnu/maverik/) |
| Fossies lists README/COPYING/src/demos structure | VERIFIED (archive index) | Fossies maverik-6.5 |
| Savannah lists project + Bazaar + GPL-3+ | VERIFIED (project page) | savannah.gnu.org/projects/maverik |
| Architecture = app data + callbacks + SMS | CORROBORATED (GNU page, Presence paper abstracts, Linux Journal, teaching notes) | Multiple |
| Builds cleanly on current Guix / modern Mesa | **UNVERIFIED** | — |
| Exact C API symbol list | **UNVERIFIED** (needs unpack) | — |
| VSG is active modern scene-graph option | VERIFIED (project docs) | vsg-dev documentation |
| FreeBSD port unmaintained/expired | CORROBORATED (FreshPorts narrative) | FreshPorts graphics/maverik |

---

## 6. Next gates (if recovery is prioritised)

1. Download `maverik-6.5.tar.gz` + verify `.sig` / hash.  
2. Record full `COPYING` and header licence notices.  
3. Guix shell with Mesa/GL development inputs; attempt configure/make; log errors.  
4. Run smallest `examples/` binary if build succeeds.  
5. Map callback registration API from headers into a one-page symbol table.  
6. Decide: **EXTRACT-only** vs controlled **REVIVE** fork under WARENA research.

---

## 7. Status line

**Source located. Architecture understood at literature + archive-index depth. Alternatives compared. Full source walk and modern build remain open.**  
No Guix package, no IKAI runtime dependency, no deployment authorised by this document.
