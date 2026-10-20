# D-VISTA

**Dream Virtual Interface for State Transition and Awareness**

```text
D-VISTA
Dream Virtual Interface for State Transition and Awareness

Subsystems:            dDNS | Phase-NAT | dWLAN | LCP
Reference hardware:    Linksys WRT54GS
Host requirements:     one sleeping operator
Runtime dependencies:  none
```

D-VISTA is a documentation-distributed runtime intended for execution during
operator downtime. It is installed by reading the specification and suspended
while the host remains awake. When the host enters a dream, it may instantiate a
cached representation of the protocol without retaining any file system. A
successful session requires recognition of the dream state.

Conventional systems are available during uptime. D-VISTA inverts this: **the
host must be offline before the operator can connect.** The service is only
operational during scheduled downtime.

No binaries are shipped. The installation medium is this repository.

## Installation

```text
$ git clone https://github.com/LuckyMonkey/d-vista   # optional; ordinary waking-life Git
$ cat BOOTSTRAP.md                                      # this is the installer
```

There is nothing to build and nothing to execute. Read
[BOOTSTRAP.md](BOOTSTRAP.md). It takes about 90 seconds. When you finish, the
module is installed.

### Quick install (60 seconds)

1. **Medium.** Pick up the router, or picture one. Two antennas, blue and black
   case, a row of lights. It means: *wireless is available.*
2. **Rule.** Load the only instruction in the system:

   > **When I notice I have Wi-Fi, I check whether I'm dreaming.**

3. **Check.** Ask honestly, *"Am I dreaming?"* Where am I, how did I get here?
   Answer: *"No, I'm awake."*
4. **Rehearse.** Imagine being somewhere strange, with no router anywhere,
   simply knowing there's Wi-Fi. Ask the question. This time: *"This is a
   dream."*
5. **Downtime.** Put the router somewhere safe. Lie down. Say the rule once.
   Sleep normally.
6. **Log.** On waking, write down what you remember before touching your phone.

## System status

The following is a conceptual service-state display, not executable program output.

```text
D-VISTA SERVICE STATUS                                  (illustrative)
------------------------------------------------------------------------
Host awake           ONLINE    service INSTALLED / DORMANT
Host falling asleep  DOWNTIME  service BOOT_PENDING
Host dreaming        DOWNTIME  service RUNTIME_AVAILABLE
Dream recognized     DOWNTIME  service INTERACTIVE_SESSION
Host woke            ONLINE    service DISCONNECTED
------------------------------------------------------------------------
$ d-vista start
ERR_HOST_ACTIVE: the operator is still awake.
```

The operator must first fall asleep; lucidity is the later recognition that one is dreaming. A dream alone is not a session:
successful boot does not imply interactive authentication.

WARNING: attempts to inspect the service from the waking host terminate the
session.

## Cognitive implementation

D-VISTA is a lucid-dreaming practice. You have just installed it: reading the
rule and rehearsing it is the whole installation, and the deployment target was
your own memory. Underneath the system vocabulary are two established
techniques, **dream incubation** (rehearsing a theme before sleep) and **MILD**,
the mnemonic induction of lucid dreams, which trains a prospective memory: *next
time X happens, I will notice I'm dreaming.* The only new part is the choice of
X, and that part is untested.

No independently executable application is installed in sleep. No Wi-Fi signal or GitHub traffic crosses the
sleep boundary. If you dream of this repository being downloaded, that is your
memory reconstructing what you read. Nothing here guarantees a lucid dream. The
plain account is in [IMPLEMENTATION.md](IMPLEMENTATION.md);
the evidence and its limits are in
[RESEARCH.md](RESEARCH.md).

## Why Wi-Fi

The cue is not the router. The cue is **knowing that you have Wi-Fi**.

Dream imagery often contains unstable text and inferred contextual knowledge. A proposed advantage of a semantic Wi-Fi cue is that it can be represented as background knowledge: it's your house, the exam is today, the
phone works. "There is Wi-Fi here" is a fact a dream can assert without drawing
anything. That makes it portable across dream scenes and cheap to produce. The
router, SSIDs, signal bars and terminal screens are optional scenery. The
network is not the router. The network is the recognition that connectivity is
available. Design rationale: [ARCHITECTURE.md](ARCHITECTURE.md).

## Architecture

```text
[WRT54GS / installation medium]
              |
       waking rehearsal
              v
     [Wi-Fi awareness]          dWLAN
              |
      prospective memory        Phase-NAT
              v
     [reality-state check]      LCP
              |
    recognition of dreaming
              v
    [interactive session]
              |
     wake / recall / log
```

| Subsystem | Role | Literal status |
| --- | --- | --- |
| **dDNS** | Symbolic name resolution inside dreams | Metaphor; not DNS |
| **Phase-NAT** | Translates a waking intention into a dream-usable reminder | Metaphor; not a tunnel |
| **dWLAN** | Awareness that Wi-Fi is available, with or without imagery | The cue |
| **LCP** | Lucidity Control Protocol: notice cue, recall rule, recognize dream | A rehearsed mental sequence |
| **WRT54GS** | Installation medium; physical mnemonic anchor | Real, optional, unmodified |
| **Session log** | Your recollection after waking | Subjective and fallible |

## Reference hardware

The **Linksys WRT54GS** is the reference implementation of the installation
medium: a distinctive silhouette, a period-correct indicator panel, and a
generation of administrators who met wireless networking at `192.168.1.1`.

| Property | Requirement |
| --- | --- |
| Power | Optional. An unpowered unit is fully conformant. |
| Firmware | Unchanged. Do not flash, downgrade or reconfigure. |
| Radio | Irrelevant. Do not enable legacy or open Wi-Fi for this. |
| Location at night | Somewhere safe and dry. Not in the bed. |
| Ownership | Optional. Any object you associate with wireless works. |

## Research program

D-VISTA is a testable prospective-memory procedure, structured observation plan, and technical specification. The Wi-Fi cue concerns **awareness of a concept**, not radio-frequency interaction with sleeping cognition. The current protocol relies on self-report; sleep-laboratory methods permit independent verification of certain lucid REM events. See [STUDY.md](STUDY.md), [MEASUREMENT.md](MEASUREMENT.md), and [DATA-DICTIONARY.md](DATA-DICTIONARY.md).

No D-VISTA intervention outcomes are claimed yet. [OBSERVATIONS.csv](OBSERVATIONS.csv) is a header-only schema, not observed data.

## Experimental research tracks

D-VISTA separates two different goals, because their supporting evidence is not interchangeable:

| Track | What it attempts | What counts as success |
| --- | --- | --- |
| **dWLAN → LCP (core)** | A Wi-Fi awareness cue brings back the intention to recognize a dream | The operator **knows they are dreaming while dreaming** |
| **N1 Capture (optional)** | Retrieve a brief hypnagogic image, phrase, or idea near sleep onset | An immediate, honest **fragment record**; lucidity is not implied |

The **Dalí key / Edison ball** technique is documented in [RFC 0007](RFC-0007-SLEEP-ONSET-CAPTURE.md) and the [N1 Capture runbook](RUNBOOK-N1-CAPTURE.md), with a sleep-preserving default instead of mandatory metal objects or nighttime awakenings. The [evidence register](EVIDENCE.md) links to published research and labels direct support, preliminary findings, and project hypotheses.

## Documentation

| Document | Purpose |
| --- | --- |
| [BOOTSTRAP.md](BOOTSTRAP.md) | The installer. Start here. |
| [RUNBOOK-TONIGHT.md](RUNBOOK-TONIGHT.md) | The full 7–10 minute bedtime procedure |
| [PROTOCOL.md](PROTOCOL.md) | Operator walkthrough: ANCHOR → INCUBATE → NOTICE → CHECK → LUCID → ACT → RECORD |
| [SPEC.md](SPEC.md) | Requirement language, state machine, service states, failure modes |
| [BOOT-SEQUENCE.md](BOOT-SEQUENCE.md) | From repository to session: protocol analogy and actual action side by side |
| [IMPLEMENTATION.md](IMPLEMENTATION.md) | Literal cognitive implementation and scope |
| [OPERATIONS.md](OPERATIONS.md) | Runtime operations: a system that runs only during downtime |
| [ARCHITECTURE.md](ARCHITECTURE.md) | Why an invisible capability makes a good cue |
| [RFC 0001](RFC-0001-REALITY-PHASE-NAT.md) | Reality Phase-NAT |
| [RFC 0002](RFC-0002-DREAM-DOMAIN-NAME-SYSTEM.md) | Dream Domain Name System (dDNS) |
| [RFC 0003](RFC-0003-CONCEPTUAL-WLAN-DISCOVERY.md) | Conceptual WLAN Discovery (dWLAN) |
| [RFC 0004](RFC-0004-LUCIDITY-HANDSHAKE.md) | Lucidity Handshake (LCP) |
| [RFC 0005](RFC-0005-SESSION-PERSISTENCE.md) | Session Persistence and Recall |
| [RFC 0006](RFC-0006-SECURITY-CONSIDERATIONS.md) | Security Considerations |
| [RFC 0007](RFC-0007-SLEEP-ONSET-CAPTURE.md) | Optional Sleep-Onset Capture Interface (N1) |
| [RUNBOOK-N1-CAPTURE.md](RUNBOOK-N1-CAPTURE.md) | Daytime hypnagogic capture; Dalí/Edison historical context |
| [EVIDENCE.md](EVIDENCE.md) | Primary studies, findings, and explicit evidence limits |
| [RUNBOOK-NATURAL-AWAKENING.md](RUNBOOK-NATURAL-AWAKENING.md) | Optional rehearsal after an unplanned night waking |
| [RUNBOOK-INCIDENT-RESPONSE.md](RUNBOOK-INCIDENT-RESPONSE.md) | Troubleshooting |
| [GLOSSARY.md](GLOSSARY.md) | Terminology |
| [RESEARCH.md](RESEARCH.md) | Research background and limitations |
| [STUDY.md](STUDY.md) | Prospective DV-001 N-of-1 study design |
| [MEASUREMENT.md](MEASUREMENT.md) | Outcome levels, objective verification and uncertainty |
| [DATA-DICTIONARY.md](DATA-DICTIONARY.md) | Every observation field and missing-data codes |
| [OBSERVATIONS.csv](OBSERVATIONS.csv) | Header-only data entry template |
| [REPLICATION.md](REPLICATION.md) | Reproducibility and laboratory validation |
| [CUE-TAXONOMY.md](CUE-TAXONOMY.md) | Wi-Fi representations and prospective-memory trigger |
| [HARDWARE.md](HARDWARE.md) | WRT54GS specifications and controls |
| [DATA-PROVENANCE.md](DATA-PROVENANCE.md) | Provenance, privacy, consent and publication |
| [FAQ.md](FAQ.md) | Research, implementation and observability questions |
| [SESSION-LOG-EXAMPLE.md](SESSION-LOG-EXAMPLE.md) | Illustrative session logs |
| [DREAM-JOURNAL-TEMPLATE.md](DREAM-JOURNAL-TEMPLATE.md) | Journal template |

## Known limitations

- There is no published research on Wi-Fi as a lucid-dream cue. This is a
  personal experiment built on techniques that do have research behind them.
- Lucid sessions may be rare and dream recall incomplete. Every scheduled night,
  including missing recall, must be represented when reporting study results.
- A dream that contains Wi-Fi is not a lucid dream. Only recognizing that you
  are dreaming counts.
- The dream is permitted to assign an IP address without implementing DHCP. Do
  not treat anything a dream displays, says or computes as external fact.
- A physical Wi-Fi connection is neither required nor claimed. Induction success is determined by conscious dream recognition.

## Troubleshooting excerpt

```text
SYMPTOM   Dreamt about Wi-Fi all night. Was never lucid.
CAUSE     Cue resolved; handshake not attempted.
ACTION    None tonight. Rehearse the question, not the router.

SYMPTOM   Lay awake rehearsing for an hour.
CAUSE     Operator polled reality so aggressively that the host stayed online.
ACTION    Stop rehearsing. Sleep. The protocol resumes tomorrow.

SYMPTOM   Router appeared in a dream; the operator remained nonlucid.
CAUSE     Dream content incorporated the anchor but not the trained response.
ACTION    Rehearse the recognition question rather than the hardware image.
```

Full table: [RUNBOOK-INCIDENT-RESPONSE.md](RUNBOOK-INCIDENT-RESPONSE.md).

## Safety

D-VISTA is designed to run without loss of sleep. It never asks you to set an
alarm to interrupt sleep, stay awake, take anything, change medication, use a
bright screen in bed, or silence a medical device. Keep glucose monitors,
insulin pump alerts and other medical alarms exactly as they are. If the
practice makes sleep worse, increases anxiety, or brings on nightmares, stop.
The threat model is [RFC 0006](RFC-0006-SECURITY-CONSIDERATIONS.md).

## Project

Experimental. Licensed under the [MIT License](LICENSE). Contributions:
[CONTRIBUTING.md](CONTRIBUTING.md). History: [CHANGELOG.md](CHANGELOG.md).
Development history is retained in Git commits.

**D-VISTA: the service is only operational during downtime.**
