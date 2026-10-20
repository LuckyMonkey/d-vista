# Changelog

All notable changes to this protocol are recorded here. Versions follow
semantic versioning, applied to documentation and, by extension, to the
operator.

## Unreleased

### Added — evidence and sleep-onset capture

- [N1 Capture runbook](RUNBOOK-N1-CAPTURE.md): optional Dalí/Edison-inspired hypnagogic recording procedure; safe natural-awakening default and separate N1 reporting.
- [RFC 0007](RFC-0007-SLEEP-ONSET-CAPTURE.md): sleep-onset capture interface independent of the REM-oriented lucid-dream handshake.
- [Evidence register](EVIDENCE.md): externally checked primary literature for MILD, N1 creativity, Dormio, TLR, and explicit distinction between supported findings and untested Wi-Fi hypotheses.
- README research tracks and bootstrap link to the optional module.

### Earlier unreleased changes

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
- [BOOT-SEQUENCE.md](BOOT-SEQUENCE.md): protocol analogy and actual action side
  by side; Deferred Semantic Reconstruction (an invented project term).
- [IMPLEMENTATION.md](IMPLEMENTATION.md): the plain
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
- Runbooks: [tonight](RUNBOOK-TONIGHT.md),
  [natural awakening](RUNBOOK-NATURAL-AWAKENING.md),
  [incident response](RUNBOOK-INCIDENT-RESPONSE.md).
- [D-VISTA runtime operations](OPERATIONS.md): the downtime-only runtime,
  system status table and operations vocabulary.
- Recall scoring scale 0–4.
- Illustrative session log and dream journal template.

### Not included

- Alarm-based wake-back-to-bed. Deferred; version 0.1.0 uses only awakenings
  that happen on their own.
- Any form of audio, light or device cueing during sleep.
- Field results. The first test has not been run.
