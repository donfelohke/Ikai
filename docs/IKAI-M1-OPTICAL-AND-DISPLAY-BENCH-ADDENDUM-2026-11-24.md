# IKAI Mirror M1 — Optical and Display Bench Addendum

**Date:** 2026-11-24  
**Status:** RESEARCH / PROPOSED TEST PROTOCOL  
**Relationship:** Supplements the existing [M1 Engineering Validation Specification](IKAI-MIRROR-M1-ENGINEERING-VALIDATION-2026-11-18.md), [Mirror Technology Research](IKAI-MIRROR-TECHNOLOGY-AND-SCHOLARLY-RESEARCH-2026-11-18.md) and [Real-Time Bidirectional I/O Study](IKAI-REALTIME-BIDIRECTIONAL-IO-AND-MIRROR-SYSTEMS-2026-11-22.md).  
**Implementation:** No mirror assembly, optical measurement or display calibration is claimed as completed.

## 1. Research correction: choose standards by scope

The M1 dossier contains useful provisional targets for optical fidelity, colour difference and overlay registration. Those values must remain **provisional** until the material, instruments, viewing geometry and user task are fixed.

Relevant references have different scopes:

- [ISO 3664:2025 — Graphic technology and photography, viewing conditions](https://www.iso.org/standard/83759.html) specifies viewing conditions for images on reflective/transmissive media such as prints and transparencies. The 2025 edition replaced ISO 3664:2009 and removed the former monitor-appraisal conditions. It is useful when defining controlled reference-object viewing, but it is **not a mirror-display acceptance standard** and does not validate human appearance assessment.
- [ASTM D1003-21](https://store.astm.org/standards/d1003) addresses haze and luminous transmittance of transparent plastics. It may be relevant to a plastic optical component or protective sheet when its scope and specimen requirements fit. It must not be represented as a glass-mirror test method.
- [EN 410](https://standards.iteh.ai/catalog/standards/cen/a3922bba-1e6d-4625-a9c0-32d431c2160a/en-410-1-2026) provides methods for luminous/solar characteristics of glazing, including spectral transmittance and reflectance. It is a candidate reference for glazing-related optical data, not automatic qualification of a coated mirror/display stack.
- [CIE 15 Colorimetry](https://cie.co.at/publications/colorimetry-4th-edition) and relevant CIE colour-difference methods provide metrology foundations. A ΔE00 target is meaningful only with a declared illuminant, observer, measurement geometry, instrument, calibration and reference.

Do not write “ISO compliant mirror” or “colour accurate” from a component data sheet, a single colour target or an uncontrolled visual inspection.

## 2. Optical assembly test matrix

Test the actual assembled stack, not just supplier glass data. Keep a conventional mirror and a display-only surface as controls.

| Variable | Minimum recorded conditions | Observation / measurement |
|---|---|---|
| Glass/coating | Manufacturer, product code, thickness, coating side, stated R/T curve | Supplier datasheet and traceable sample identity |
| Display | Panel/controller, pixel pitch, brightness setting, refresh, warm-up | Luminance, contrast, heat and image stability |
| Ambient illumination | Front and rear lux, source type, direction, time of day | Reflection visibility, glare and display leakage |
| Viewing geometry | Observer distance, horizontal/vertical angle, mirror dimensions | Clarity, distortion, ghosting and usable viewing zone |
| Display position | Distance/angle behind mirror, alignment and enclosure | Parallax, double image, brightness uniformity |
| Surface condition | Clean/dry state, scratches, dust, protective film | Repeatability and maintenance sensitivity |
| Power state | Display off, idle, nominal and maximum intended brightness | Reflection quality and thermal change |

Measure at multiple points across the mirror, not just the centre. Record the instrument model, calibration date, uncertainty, method and raw readings. Where the instrument cannot measure a property, mark it NOT MEASURED.

## 3. Reflection and display must be evaluated as separate functions

**Reflection task:** a participant must be able to complete predefined ordinary mirror tasks with the display off and with the intended overlay states. Use a conventional mirror as a reference. The task protocol should avoid subjective beauty ratings.

**Display task:** test text/graphic legibility, contrast, visual obstruction, viewing angle, ambient-light sensitivity, minimum usable brightness and dismissibility. The display must not dominate the reflection.

**Combined task:** evaluate whether the user can alternate attention between reflection and information without confusion, glare or loss of mirror utility. Record task completion and observed failure modes; do not infer health, emotion or personal attributes.

## 4. Colour and illumination protocol

If appearance-related colour work is later justified:

1. Define the exact task (for example, viewing a neutral/colour reference), not a vague goal of “true colour.”
2. Use a traceable colour target and a calibrated spectrophotometer/colorimeter where available.
3. Record illuminant/spectral power distribution, illuminance, viewing geometry, display state and observer adaptation conditions.
4. Record camera model, lens, exposure, white balance, colour pipeline and display calibration separately if camera imagery is involved.
5. Calculate colour differences only under a stated CIE method and measurement setup.
6. Report mean, maximum and distribution across target patches, instrument uncertainty and repeatability.
7. Keep direct human visual reflection assessment separate from camera/display colour reproduction.

The existing ΔE00 ≤ 3 proposal is not a universal mirror or salon standard. Retain it only as a provisional experiment threshold after a metrology review. If no calibrated instrument is available, do not claim a colour pass.

## 5. Camera, latency and privacy gates

The mirror must remain useful in the no-camera mode. Camera evaluation is a separate opt-in experiment.

- Use synthetic charts, printed targets or props before human imagery.
- Define capture purpose, fields retained, processing location and deletion before capture.
- Make camera enable/disable physically observable and easy to revoke.
- Do not infer identity, emotion, health, personality, attractiveness, hair condition or capability.
- Do not store images in routine performance logs.
- Measure capture-to-display latency using a documented method and a common time reference; report p50/p95/p99, maximum, drops and clock-domain uncertainty.
- If the measurement method cannot isolate submit-to-photon delay, state that limitation explicitly.

OpenXR is a later optional spatial interface, not a requirement for M1-A through M1-C. Consult the [Khronos OpenXR Registry](https://registry.khronos.org/OpenXR/) only when a specific headset/runtime integration is under test.

## 6. Local operating conditions

The M1 bench should represent the intended room, not a generic laboratory alone:

- daylight and direct-sunlight variation;
- front/rear room illumination and reflective surroundings;
- local dust, cleaning and maintenance routines;
- actual power draw, heat dissipation and safe power interruption;
- availability and replaceability of the panel, glass, power supply and compute;
- offline operation and recovery after loss of internet access.

Do not size a UPS, solar system or thermal enclosure from national electricity-generation statistics. Measure the actual assembly and use location-specific supply and tariff evidence.

## 7. Decision record

Each test report must include: sample/component identity; setup drawing; geometry; environmental conditions; instrument/calibration; procedure; raw readings; calculations; uncertainty; photographs of the fixture (not participants unless separately authorised); pass/fail/inconclusive; and reviewer.

A negative or inconclusive result is useful. If the optical reflection is compromised, stop the integration and revise material, lighting or display placement before adding tracking or XR.

## 8. References

- [ISO 3664:2025](https://www.iso.org/standard/83759.html) — viewing conditions for reflective/transmissive image media; scope boundary noted above.
- [ASTM D1003-21](https://store.astm.org/standards/d1003) — haze/transmittance of transparent plastics only.
- [EN 410-1:2026](https://standards.iteh.ai/catalog/standards/cen/a3922bba-1e6d-4625-a9c0-32d431c2160a/en-410-1-2026) — glazing optical characteristics; applicability to the selected mirror construction must be reviewed.
- [CIE 15, Colorimetry, 4th Edition](https://cie.co.at/publications/colorimetry-4th-edition).
- [OpenXR Registry](https://registry.khronos.org/OpenXR/) — optional later spatial-runtime research.

**Maturity:** RESEARCH / PROPOSED TESTS. No optical, colour, display, thermal, latency or privacy test has been executed by this addendum.
