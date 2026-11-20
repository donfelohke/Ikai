# IKAI Mirror — Mirror Technology & Scholarly Research

**Date:** 18 November 2026  
**Status:** RESEARCH  
**Authority:** IKAI specialist research; shared terms and evidence rules remain in FELOH Corpus.  
**Product status:** Not a released product. No working mirror, validated sensor pipeline or deployment is claimed.

**Related:** [IKAI MIRROR+ Spatial Computing Research (2026-11-14)](IKAI-MIRROR-SPATIAL-RESEARCH-2026-11-14.md) · [Reflective Computing Research Alignment](REFLECTIVE-COMPUTING-RESEARCH-ALIGNMENT-2026-11.md)

## Central research proposition

IKAI Mirror is a computationally augmented reflective environment in which the physical reflection remains meaningful while digital information, spatial intelligence and human interaction become available.

This connects three domains:

- **Mirror technology** — optics, displays, illumination and sensing.
- **Reflective computing** — interfaces for self-observation, personal context and interaction.
- **Embodied computing** — appearance, movement, gesture, choreography and spatial awareness.

The mirror is investigated beyond the conventional smart-mirror concept. A mirror can be an optical instrument, a display surface, a sensing and perception system, an augmented-reality interface, an instrument for embodied interaction, and a reflective environment for personal computing.

## 1. Five engineering approaches

These are not interchangeable. They produce different optical properties, interaction possibilities and implementation costs.

### A. Two-way mirror display (preferred first prototype)

- Semi-transparent reflective glass.
- LCD/OLED display mounted behind it.
- Computer renders information through the glass.
- Camera and sensors can be integrated into the frame.

Best for IKAI Mirror's initial physical implementation.

### B. Digital or virtual mirror

- Camera captures the user.
- Display reproduces a live image.
- Computer vision overlays graphics.
- Supports image processing, virtual try-on and visual analysis.

Best for experimentation with visual transformations. It is **not** an optical mirror: image latency, camera quality and colour reproduction matter.

### C. Augmented-reality mirror

- Real reflection remains visible.
- Digital objects are registered to the body or surrounding space.
- Requires calibrated geometry and tracking.
- Can support gesture and viewpoint-dependent rendering.

Best for loc-care guidance and embodied spatial interfaces.

### D. Transparent display mirror

- Transparent OLED or similar display technology.
- Digital imagery and the background can be seen together.
- Potentially more integrated than a separate mirror and monitor.

Investigate optical contrast, transparency, cost and repairability.

### E. Mixed-reality reflected environment

- Physical mirror combined with a spatially tracked XR headset.
- Physical and reflected spaces are computationally connected.
- Virtual objects can appear in the reflection and be manipulated through it.

Most ambitious direction for IKAI's XR research.

### Critical optical distinction

A two-way mirror is not automatically a transparent display. It is a partially reflective, partially transmissive optical surface. The visual balance depends on reflectance/transmittance characteristics, illumination on both sides, and the brightness of the display behind it.

Trade-off:

- More reflection improves conventional mirror appearance.
- More transmission improves visibility of the underlying display.
- Higher display brightness improves readability but increases power and thermal requirements.

For a beauty and loc-care mirror, the optical reflection must remain the primary visual reference. Digital content should not compromise the ability to assess natural hair texture, colour and appearance.

## 2. Physical system architecture (research recommendation)

### Hardware stack

| Layer | Components |
|-------|------------|
| Optical | Two-way mirror glass · Protective frame |
| Display | LCD / OLED · Backlight · Display controller |
| Sensing | RGB camera · Optional depth camera · Microphone · Lighting sensors |
| Compute | GNU/Linux · CPU · GPU · Storage · Guile |
| Software | Reflection · Vision · Spatial UI · Voice · Context · Privacy |

### Component recommendations (research, not procurement)

| Component | Research recommendation |
|-----------|-------------------------|
| Reflective glass | Semi-transparent mirror glass |
| Display | High-brightness LCD initially |
| Camera | RGB camera with manual exposure control |
| Depth sensing | Optional, for body and hand tracking |
| Lighting | High-CRI adjustable LED illumination |
| Microphone | Physical mute capability |
| Speakers | Local audio output |
| Compute | x86-64 GNU/Linux workstation |
| GPU | Hardware-accelerated graphics |
| Storage | Local encrypted storage |
| Operating system | Guix-based GNU/Linux |

Lighting is critical. Beauty-related computer vision can be misleading under changing illumination. A controlled, high-colour-rendering light source is necessary to distinguish genuine appearance from lighting artefacts.

## 3. Scholarly works — essential reading

### A. Foundational smart-mirror research

1. **Reflecting Health: Smart Mirrors for Personalized Medicine** (2018)  
   Miotto et al., *npj Digital Medicine*. DOI: 10.1038/s41746-018-0068-7  
   Architecture, embedded computing, sensing, healthcare applications landscape.

2. **The SHAPES Smart Mirror Approach for Independent Living, Healthy and Active Ageing** (2021)  
   Modular architecture, system integration, multimodal interaction.  
   PMC: https://pmc.ncbi.nlm.nih.gov/articles/PMC8659491/

3. **A Smart Mirror for Emotion Monitoring in Home Environments** (2021)  
   Bianco et al., *Sensors*. DOI: 10.3390/s21227453  
   Face/voice processing and interaction. Emotion-recognition claims must be examined critically; facial expressions are not reliable evidence of internal emotional states.

### B. Augmented reality mirror engineering

4. **Interacting with Augmented Reality Mirrors** (2016)  
   Portalés et al. DOI: 10.4018/978-1-5225-0435-1.ch009  
   Review of AR mirror configurations, interaction techniques, applications and limitations.

5. **Exploring Non-Reversing Magic Mirrors for Screen-Based Augmented Reality Systems** (2017)  
   Bork et al., IEEE VR. DOI: 10.1109/VR.2017.7892332  
   Should a computational mirror reproduce the conventional reversed reflection or show a non-reversing view? Relevant for anatomy, grooming and spatial interaction.

6. **Optical-Reflection Type 3D Augmented Reality Mirrors** (2019)  
   Lee, Park & Billinghurst. DOI: 10.1145/3359996.3364782

7. **Improving User Experience in Augmented Reality Mirrors with 3D Displays** (2020)  
   Lee et al. DOI: 10.1007/978-3-030-64556-4_50  
   Visual depth mismatch between real reflection and digital overlays.

### C. Embodiment, movement and reflective computing (especially relevant to IKAI + GENJE)

8. **Here and Now: Creating Improvisational Dance Movements with a Mixed Reality Mirror** (2023)  
   CHI 2023, Velloso et al. DOI: 10.1145/3544548.3580666  
   Movement traces, delayed body presence, spatial/temporal relationships, reflected-body interaction, improvisational choreography. Involved 13 dancers and choreographers. High priority for IKAI.

9. **Reflected Reality: Augmented Reality through the Mirror** (2023)  
   Zhou, Syiem, Li, Goncalves & Velloso. *IMWUT* 7(4). DOI: 10.1145/3631431  
   PDF: https://qiushi-zhou.github.io/PDF/IMWUT-2023-RR.pdf  
   First-person interaction via XR headset; second-person interaction using the reflected body as avatar; egocentric and allocentric spatial references; manipulation of virtual objects across the mirror boundary. Strong foundation for advanced IKAI mirror architecture.

10. **Is That Me? — Embodiment and Body Perception with an Augmented Reality Mirror** (2018)  
    IEEE ISMAR. DOI: 10.1109/ISMAR-Adjunct.2018.00057  
    Ownership and agency over an augmented mirrored body.

### D. Newer mirror-interface research

11. **Augminded: Ambient Mirror Display Notifications** (2025)  
    Götzelmann, Karg & Müller. *Multimodal Technologies and Interaction*. DOI: 10.3390/mti9090093  
    Subtle, context-sensitive information presentation without a wearable headset.

12. **Smart Mirrors and Data Protection Regulation** (2025)  
    Colonna & Riva. DOI: 10.1007/978-3-031-84158-3_12  
    Consent, transparency, biometric data and data protection by design.

## 4. Mirror × Body × Identity

Three different representations of the human subject can coexist:

- **Physical self** — optical reflection.
- **Computational self** — tracked body and measurements.
- **Represented self** — digital avatar and transformation.

IKAI can investigate how these representations interact without collapsing them into a single scored or classified identity.

Example questions:

- What does a person perceive when their reflected body is delayed?
- What happens when their digital representation moves independently?
- Can a person explore alternative movement patterns through a reflected avatar?
- Can digital overlays communicate information without replacing the natural reflection?
- How can personal identity remain distinct from computational classification?

This is where reflective computing becomes more interesting than conventional smart-mirror engineering.

## 5. Proposed research modules

| Module | Research domain | Example application |
|--------|-----------------|---------------------|
| M1 | Optical systems | Reflection and display engineering |
| M2 | Computer vision | Hair, face, body and object perception (with strict non-diagnostic boundary) |
| M3 | Spatial interaction | Gesture, gaze and reflected space |
| M4 | Embodied computing | Movement, posture and choreography |
| M5 | Reflective interfaces | Personal observation and journaling |
| M6 | Privacy and ethics | Consent, sensing and data ownership |

### Application directions (research, not products)

**IKAI Beauty Mirror**  
Loc length and distribution documentation; hair and scalp visualisation (with clinical limitations); styling previews; colour-consistent appearance assessment; client-controlled visual records.

**IKAI Movement Mirror**  
Movement traces; body-joint visualisation; delayed movement playback; choreographic annotation; spatial movement analysis.

**IKAI Reflective Mirror**  
Voice journaling; personal notes; optional contextual prompts; personal information display; local-first reflective computing.

## 6. Proposed prototype: IKAI Mirror M1

Recommendation: begin with a stationary full-length mirror rather than a headset.

**Initial specifications (research demonstrator):**

- Full-length reflective surface.
- Rear-mounted high-brightness display.
- RGB camera.
- Adjustable high-CRI lighting.
- Optional depth sensor.
- Microphone with hardware mute.
- x86-64 GNU/Linux compute.
- Guile/Scheme application orchestration.
- Local storage and local processing.
- No mandatory cloud services.

**First demonstrator must prove four things:**

1. Optical reflection remains usable.
2. Digital overlays are correctly registered.
3. Body and hand tracking work reliably (where used).
4. The system remains functional without internet access.

Do **not** begin with emotion recognition, biometric profiling or medical diagnosis. They are unnecessary to prove the fundamental architecture and conflict with IKAI boundaries.

## 7. Research sequence (checklist)

1. Optical mirror and display technologies — Foundations
2. Augmented mirror interaction and calibration — Foundations
3. Reflected Reality (2023) and embodied interaction — Theory
4. Dance, movement and visualisation research — Theory
5. Computer vision and depth-sensing feasibility — Engineering
6. GNU/Linux and Guile integration — Engineering
7. Privacy, consent and data governance — Governance
8. IKAI Mirror M1 prototype specification — Design

## 8. Architectural position

Three complementary systems (conceptual):

- **IKAI Mirror** — stationary, physical reflective computing.
- **IKAI Glass** — mobile, wearable reflective and contextual computing.
- **IKAI Space** — immersive, spatially extended computing.

They should share one underlying spatial, identity, event and permission architecture.

The scholarly literature establishes that mirror-based interfaces can support more than notifications: they can enable body-centric interaction, spatial extension, movement creation and alternative perspectives on embodied experience.

The particularly important combination is the 2023 *Reflected Reality* work and the 2023 CHI dance-mirror study. Together they offer a strong research bridge between XR engineering and the embodied, reflective direction of IKAI.

**Research principle:**

> The mirror should not merely show a person information. It should give a person new ways to observe, understand, create and interact with their own world.

## 9. Non-negotiable boundaries (reaffirmed)

- No face identification or biometric identity matching.
- No diagnosis or clinical claims.
- No person scoring, ranking or hidden profiling.
- No covert surveillance.
- No default cloud profile; document external processing before proposing it.
- Minimum data for a stated purpose · prefer local processing · short retention · participant control.
- Optical reflection remains primary for appearance assessment; digital content must not compromise natural visual evaluation.

## 10. Cross-project ownership

- **WARENA** — compute, graphics/runtime, hardware, Guix, reproducibility.
- **GENJE** — creative and movement practice, choreography, embodied expression.
- **FELOH Corpus** — shared governance, provenance and evidence labels.
- **NAKEBUSEN** — sole commercial interface; this research does not create a product or booking channel.

---
**Maintainer:** IKAI research · **Author context:** Felix Lwova / Don Feloh · **Status:** RESEARCH · **Date:** 18 November 2026


## Glass Terminal alignment — IKAI reflective interaction — 2026-11-20

Glass Terminal is a cross-project interface research direction, not a new IKAI product or a mandate to turn the mirror into a dashboard. IKAI contributes the reflective-experience layer: participant-directed reflection, optical display research, consent, context, privacy and memory semantics.

### IKAI's role

- Investigate the two-way mirror as a physical optical boundary, not merely a visual metaphor.
- Study display placement, illumination balance, luminance, viewing angles, ambient light, legibility and thermal/power constraints.
- Keep reflected-body presence distinct from identity recognition or automated interpretation.
- Let the participant decide what is displayed, recorded, retained, replayed or shared.
- Keep any sensing optional, purpose-limited, visible and revocable; provide a useful non-camera path.
- Do not add face identification, diagnosis, beauty scoring, emotion inference, hidden profiling or covert surveillance.

### Interface relationship

The Glass Terminal visual language may inform a future IKAI interface through restrained translucency, clear hierarchy, reflective surfaces and contextual information. Browser CSS blur is not a physical mirror, optical validation or an IKAI implementation. Native rendering and physical optical behavior require separate engineering evaluation.

The public Glass Terminal page is a static research presentation, not an IKAI runtime or commercial feature:
https://donfelohke.github.io/research/glass-terminal/

### Research status

This alignment adds no implemented mirror display, spatial tracking, sensing pipeline, personal-memory service or released product claim. The M1 two-way-mirror engineering track remains subject to its own optical validation and participant-safety gates.
