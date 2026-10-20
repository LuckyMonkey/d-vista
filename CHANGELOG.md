# Changelog

All notable changes to this protocol are recorded here. Versions follow
semantic versioning, applied to documentation and, by extension, to the
operator.

## Unreleased

Identity and experience refactor. No change to the practice itself.

### Changed

- Project renamed for display to **D-VISTA** (Dream Virtual Interface for State
  Transition and Awareness). dDNS is retained as a subsystem, alongside
  Phase-NAT, dWLAN and LCP.
- README rewritten so the documentation is the installation medium:
  installation, illustrative status, then the implementation note.
- SPEC: service states mapped onto the existing state machine.
- Incident response: `ERR_HOST_ACTIVE`, `INSTALL_SUCCEEDED_NO_SESSION`,
  `STALE_CACHE`; `NO_CARRIER` now means the cue was absent, and `NO_SIGNAL`
  means no recall.
- Agent build briefs moved to `meta/`.

### Added

- [BOOTSTRAP.md](BOOTSTRAP.md): the 90-second installer.
- [docs/boot-sequence.md](docs/boot-sequence.md): fiction and actual action side
  by side; Deferred Semantic Reconstruction (an invented project term).
- [docs/implementation-notes.md](docs/implementation-notes.md): the plain
  account.

## 0.1.0 — 2026-10-20

Initial experimental specification.

### Added

- Core cue: the semantic record "I have Wi-Fi", bound to the response
  "Am I dreaming?"
- Reference anchor: Linksys WRT54GS, powered or unpowered, unmodified.
- [PROTOCOL.md](PROTOCOL.md) operator walkthrough and [SPEC.md](SPEC.md) state
  machine.
- RFC series 0001–0006: Reality Phase-NAT, Dream Domain Name System, Conceptual
  WLAN Discovery, Lucidity Handshake, Session Persistence, Security
  Considerations.
- Runbooks: [tonight](runbooks/tonight.md),
  [natural awakening](runbooks/natural-awakening.md),
  [incident response](runbooks/incident-response.md).
- [D-VISTA runtime operations](docs/d-vista.md): the downtime-only runtime,
  system status table and operations vocabulary.
- Recall scoring scale 0–4.
- Illustrative session log and dream journal template.

### Not included

- Alarm-based wake-back-to-bed. Deferred; version 0.1.0 uses only awakenings
  that happen on their own.
- Any form of audio, light or device cueing during sleep.
- Field results. The first test has not been run.
