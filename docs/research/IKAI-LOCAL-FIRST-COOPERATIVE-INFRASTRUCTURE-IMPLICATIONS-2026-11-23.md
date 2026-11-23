# IKAI — Local-First Cooperative Infrastructure Implications

**Date:** 2026-11-23 · **Status:** RESEARCH / DESIGN IMPLICATIONS  
**Owner:** IKAI · MIRROR · **Guiding principle:** A mirror, not a judge.  
**Name:** IKAI is a Turkana female name meaning “home.”

## 1. Research question

What should IKAI require from cooperative digital infrastructure if reflective environments are to remain participant-controlled, useful offline and interoperable without transferring unnecessary personal data to remote services?

This is IKAI's bounded contribution to WARENA's networking research. It does not define a community ISP, select a federation platform or approve sensing.

## 2. Local-first as a participant guarantee

IKAI's essential reflective functions should be designed so that:
- core local functions work without a remote account or continuous internet;
- capture and sensing are visible, intentional and revocable;
- local processing is preferred when it meets the task;
- network transfer is purpose-bound, inspectable and minimised;
- participants understand what is stored, where, who controls it and how to export/delete it;
- loss of internet does not silently erase local work or disable basic interaction.

A locally hosted server is not automatically private. A cooperative operator remains an administrator with responsibilities and potential access. Define device, household, site and cooperative trust boundaries.

## 3. Infrastructure implications

### Community Wi-Fi and mesh

A community network may connect IKAI installations, local archives or shared services. It should not be required for the core mirror loop of acquisition, local computation, rendering and participant feedback. A network partition should degrade optional collaboration gracefully rather than disable local operation.

### Bluetooth and peripherals

Bluetooth may serve short-range peripherals, provisioning or device I/O. Document exact profile, pairing, device role, range, power and security. Pairing is not proof that application data is appropriately protected.

### GNUnet and peer services

GNUnet documents peer transport, encrypted messaging, a distributed hash table and GNS naming. These are possible building blocks, but IKAI has not selected GNUnet. Establish a requirement before adding identity, metadata, lifecycle and recovery costs.

### Tor and remote access

Tor may provide a privacy-oriented route to a remote service. It does not make a camera, sensor, endpoint or stored dataset safe. Do not route raw sensor streams through an anonymity network as a substitute for minimisation or consent.

### Federation and shared services

ActivityPub, Matrix, XMPP and other federated systems differ in identity and metadata models. ActivityPub is an HTTP-based Web protocol. A JavaScript-free client does not make it independent of web architecture. IKAI inherits WARENA's current exclusion of web technologies as application/runtime architecture; no federated application is selected here.

### Databases and persistence

SQLite may suit a self-contained local installation where single-node persistence fits. MariaDB or PostgreSQL may suit a separately operated multi-user service. Choose only after concurrency, backup/restore, migration, access control, encryption, lifecycle and recovery tests. No database is selected for IKAI by this record.

## 4. Participant data and governance requirements

For every networked feature, document:

1. Purpose: what participant benefit requires the feature?
2. Data: which image, video, depth, motion, voice, text or interaction data is needed?
3. Location: device, household server, cooperative node or remote host?
4. Authority: who operates the hardware and administers the service?
5. Visibility: how does the participant know capture or transfer is active?
6. Access: who can read, copy, export or modify records?
7. Retention: what is retained, for how long and why?
8. Deletion: can the participant delete local and request deletion of remote copies?
9. Failure: what happens on network loss, compromise or operator departure?
10. Recovery: can participants restore their work without surrendering control?

Do not infer identity, health, emotion, personality or capability from sensor/movement data. No face identification, biometric identity matching, person scoring, covert recording or hidden profiling. Future sensing remains opt-in, consent-based and separately reviewed.

## 5. Threat-model additions

| Threat | Design response |
|---|---|
| Cooperative administrator overreach | Least privilege, transparent administration, participant export and access logs |
| Lost/stolen device | Data minimisation, encryption where appropriate, revocable credentials and recovery |
| Network partition | Local core functions and queued optional sync with conflict handling |
| Malicious federated peer | Input validation, rate limits, content isolation and moderation |
| Compromised shared server | Data minimisation, separated participant records, backups and incident response |
| Identity correlation | Limit persistent identifiers and cross-service linking |
| Unclear deletion | Define local deletion, remote requests, backups and retention separately |

## 6. Validation questions

- Which functions are essential offline, and which are genuinely collaborative?
- Can a local device operate without a cooperative account?
- Can participants inspect and export their own records in open formats?
- What data must never leave the installation?
- How are keys, backups and operator privileges controlled?
- How are sync conflicts resolved without silent overwrite?
- Can a participant leave a cooperative service without losing local records?
- What is the recovery path if a host or operator disappears?

## 7. Ecosystem relationship

WARENA owns infrastructure and systems engineering. IKAI owns reflective-computing research and participant-facing requirements. GENJE owns embodied creative practice. FELOH Corpus owns shared governance, terminology, evidence and provenance. NAKEBUSEN remains the sole commercial interface; IKAI is not a product or booking feature.

## 8. Sources and related records

- WARENA, [Cooperative Networking, Federation and Self-Hosted Services](https://github.com/donfelohke/WARENA/blob/main/docs/research/cooperative-networking-and-self-hosted-services-2026-11-23.md)
- GNUnet architecture: https://www.gnunet.org/en/architecture.html
- W3C ActivityPub: https://www.w3.org/TR/activitypub/
- Tor relay types: https://community.torproject.org/relay/types-of-relays/
- LibreMesh: https://libremesh.org/getting-started.html

**Evidence limitation:** Design-requirements note only. No participant study, threat-model exercise, integration, device test or deployment has been conducted.
