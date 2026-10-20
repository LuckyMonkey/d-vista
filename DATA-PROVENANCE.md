# Data Provenance, Ethics, and Release

## Dataset status

`OBSERVATIONS.csv` is an **empty, header-only data template**. There are no recorded D-VISTA operator outcomes in the repository as of this revision. Do not add example successes to this file. Synthetic training examples belong in [SESSION-LOG-EXAMPLE.md](SESSION-LOG-EXAMPLE.md) with conspicuous labels.

## Capture chain

**Experience → initial recall → timestamped report → coded outcome → aggregate summary.**

At every step, preserve what was actually observed versus what was inferred:

- Experience: private, not directly available after waking.
- Initial report: written/recorded promptly; retain original wording.
- Coding: explicit rule from [DATA-DICTIONARY.md](DATA-DICTIONARY.md).
- Analysis: include missing and adverse reports rather than selecting memorable successes.
- Publication: label conclusions by strength of evidence.

## Public repository rules

- Avoid names, contact details, exact addresses, patient identifiers, medication schedules, health-device screenshots, sexual or traumatic personal material, or other sensitive content.
- Do not publish another person's diary without express consent and a review of identifiability.
- Researchers working with participants must establish adequate consent, withdrawal, and appropriate ethics procedures.
- Store full dream transcripts privately by default; only commit a fully reviewed, intentionally public extract.
- Git retains history; removing a file in a later commit does not erase older copies from forks or previous revisions. Treat public data as effectively published.
- Do not assert direct cross-state download or communication from an ordinary dream report.

## Versioning and quality

Use a protocol version and stable study identifier for each collected night. Predeclare outcomes before collecting data. Maintain the original report and a change log for coding revisions. When using independent raters, separate the raw report, individual scores, and reconciled score.

## Interpreting negative and ambiguous data

No dream recall is a **measurement limitation**, not a no-dream result. Ambiguous lucidity remains uncertain. A negative result for H2 can coexist with a positive result for H1. A protocol that makes sleep worse fails the feasibility objective regardless of recall frequency.

Study specification: [STUDY.md](STUDY.md). Replication methods: [REPLICATION.md](REPLICATION.md).
