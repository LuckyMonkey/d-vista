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

Illustrative. This is the protocol's fictional status display, not output from
any program.

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

The user must be unconscious for the interface to become available, then
conscious of dreaming to obtain access. A dream alone is not a session:
successful boot does not imply interactive authentication.

WARNING: attempts to inspect the service from the waking host terminate the
session.

## Implementation note

This is the part where the documentation tells you what it has been doing.

D-VISTA is a lucid-dreaming practice. You have just installed it: reading the
rule and rehearsing it is the whole installation, and the deployment target was
your own memory. Underneath the system vocabulary are two established
techniques, **dream incubation** (rehearsing a theme before sleep) and **MILD**,
the mnemonic induction of lucid dreams, which trains a prospective memory: *next
time X happens, I will notice I'm dreaming.* The only new part is the choice of
X, and that part is untested.

No program runs in your head. No Wi-Fi signal or GitHub traffic crosses the
sleep boundary. If you dream of this repository being downloaded, that is your
memory reconstructing what you read. Nothing here guarantees a lucid dream. The
plain account is in [docs/implementation-notes.md](docs/implementation-notes.md);
the evidence and its limits are in
[docs/research-and-limitations.md](docs/research-and-limitations.md).

## Why Wi-Fi

The cue is not the router. The cue is **knowing that you have Wi-Fi**.

Dreams are poor at rendering text, interfaces and precise hardware, but good at
supplying assumed background knowledge: it's your house, the exam is today, the
phone works. "There is Wi-Fi here" is a fact a dream can assert without drawing
anything. That makes it portable across dream scenes and cheap to produce. The
router, SSIDs, signal bars and terminal screens are optional scenery. The
network is not the router. The network is the recognition that connectivity is
available. Design rationale: [docs/architecture.md](docs/architecture.md).

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

## Documentation

| Document | Purpose |
| --- | --- |
| [BOOTSTRAP.md](BOOTSTRAP.md) | The installer. Start here. |
| [runbooks/tonight.md](runbooks/tonight.md) | The full 7–10 minute bedtime procedure |
| [PROTOCOL.md](PROTOCOL.md) | Operator walkthrough: ANCHOR → INCUBATE → NOTICE → CHECK → LUCID → ACT → RECORD |
| [SPEC.md](SPEC.md) | Requirement language, state machine, service states, failure modes |
| [docs/boot-sequence.md](docs/boot-sequence.md) | From repository to session: fiction and actual action side by side |
| [docs/implementation-notes.md](docs/implementation-notes.md) | The plain-language truth |
| [docs/d-vista.md](docs/d-vista.md) | Runtime operations: a system that runs only during downtime |
| [docs/architecture.md](docs/architecture.md) | Why an invisible capability makes a good cue |
| [RFC 0001](rfc/0001-reality-phase-nat.md) | Reality Phase-NAT |
| [RFC 0002](rfc/0002-dream-domain-name-system.md) | Dream Domain Name System (dDNS) |
| [RFC 0003](rfc/0003-conceptual-wlan-discovery.md) | Conceptual WLAN Discovery (dWLAN) |
| [RFC 0004](rfc/0004-lucidity-handshake.md) | Lucidity Handshake (LCP) |
| [RFC 0005](rfc/0005-session-persistence.md) | Session Persistence and Recall |
| [RFC 0006](rfc/0006-security-considerations.md) | Security Considerations |
| [runbooks/natural-awakening.md](runbooks/natural-awakening.md) | Optional rehearsal after an unplanned night waking |
| [runbooks/incident-response.md](runbooks/incident-response.md) | Troubleshooting |
| [docs/glossary.md](docs/glossary.md) | Terminology |
| [docs/research-and-limitations.md](docs/research-and-limitations.md) | Research background and limits |
| [examples/sample-session-log.md](examples/sample-session-log.md) | Illustrative session logs |
| [examples/sample-dream-journal.md](examples/sample-dream-journal.md) | Journal template |

## Known limitations

- There is no published research on Wi-Fi as a lucid-dream cue. This is a
  personal experiment built on techniques that do have research behind them.
- Most nights will produce no session. Many will produce no recall. This is
  normal operation, not a fault.
- A dream that contains Wi-Fi is not a lucid dream. Only recognizing that you
  are dreaming counts.
- The dream is permitted to assign an IP address without implementing DHCP. Do
  not treat anything a dream displays, says or computes as external fact.
- Wake-on-LAN is not supported; Wake-on-Lucid may be attempted.

## Troubleshooting excerpt

```text
SYMPTOM   Dreamt about Wi-Fi all night. Was never lucid.
CAUSE     Cue resolved; handshake not attempted.
ACTION    None tonight. Rehearse the question, not the router.

SYMPTOM   Lay awake rehearsing for an hour.
CAUSE     Operator polled reality so aggressively that the host stayed online.
ACTION    Stop rehearsing. Sleep. The protocol resumes tomorrow.

SYMPTOM   Router appeared in dream, on fire, speaking French.
CAUSE     Split-horizon resolution. Expected.
ACTION    Ask whether you are dreaming. You were.
```

Full table: [runbooks/incident-response.md](runbooks/incident-response.md).

## Safety

D-VISTA is designed to run without loss of sleep. It never asks you to set an
alarm to interrupt sleep, stay awake, take anything, change medication, use a
bright screen in bed, or silence a medical device. Keep glucose monitors,
insulin pump alerts and other medical alarms exactly as they are. If the
practice makes sleep worse, increases anxiety, or brings on nightmares, stop.
The threat model is [RFC 0006](rfc/0006-security-considerations.md).

## Project

Experimental. Licensed under the [MIT License](LICENSE). Contributions:
[CONTRIBUTING.md](CONTRIBUTING.md). History: [CHANGELOG.md](CHANGELOG.md).
Build briefs used to write this repository are kept in [meta/](meta/RUNBOOK.md).

**D-VISTA: the service is only operational during downtime.**
