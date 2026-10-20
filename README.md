# dDNS — Dream Domain Name System

**Reality Phase-NAT / Conceptual WLAN Discovery**

```text
Document class:   Experimental / Informational
Version:          0.1.0
Runtime:          one human brain, unmodified
Reference anchor: Linksys WRT54GS
Dependencies:     none
```

> **dDNS requires the operator to be offline before establishing a connection.**
>
> The protocol runs on [D-VISTA](docs/d-vista.md), a runtime that is unavailable
> during normal operating hours and boots only when the operator falls asleep.
> Sleep is not downtime. Sleep is the production environment.

## Abstract

dDNS is an experimental protocol for resolving a single waking intention inside
dream-state cognition. The operator binds a physical anchor (the reference
implementation is a Linksys WRT54GS) to one semantic record: **"I have Wi-Fi."**
When that record later resolves inside a dream, the operator's resolver is
expected to return a second record: **"Am I dreaming?"** A correct answer to the
second query constitutes a lucid session.

The protocol does not require the anchor to appear in the dream. It does not
require a screen, a signal-strength icon, an SSID, a password prompt, or an IP
address. It requires only that, somewhere in the dream, the operator *knows* that
wireless connectivity is available, and that this knowledge prompts a genuine
check of the current state.

Consciousness discovery is best-effort. No delivery guarantees are provided.

## What this is, plainly

This repository uses networking **as an analogy**. It does not connect dreams to
networks, and no physical network traffic crosses the sleep boundary. The router
transmits nothing into your sleep. It is a memory aid, held in the hand before
bed.

Underneath the RFC formatting, dDNS is a structured application of two
established lucid-dreaming techniques: **dream incubation** (deliberately
rehearsing a theme before sleep) and **MILD**, the mnemonic induction of lucid
dreams, which trains a prospective memory of the form *"next time X happens, I
will notice that I am dreaming."* The only novel part is the choice of X. That
part is untested. See [research and limitations](docs/research-and-limitations.md).

## Architecture

```text
[WRT54GS / physical anchor]
              |
       waking rehearsal
              v
     [Wi-Fi awareness]
              |
      prospective memory
              v
     [reality-state check]
              |
    recognition of dreaming
              v
       [lucid session]
              |
     wake / recall / log
```

The network is not the router. The network is the recognition that connectivity
is available.

Wi-Fi was selected as the cue because it is invisible. Dreams are poor at
rendering text, interfaces and precise hardware, but good at supplying assumed
background knowledge: you are at school, it is your house, the phone works.
"There is Wi-Fi here" is the kind of fact a dream can assert without drawing
anything. The design rationale is in [docs/architecture.md](docs/architecture.md).

## Quick Start (60 seconds)

The entire protocol compresses to one rule:

> **When I notice I have Wi-Fi, I check whether I am dreaming.**

1. Pick up the router. Look at it for a few seconds: two antennas, the blue and
   black case, the row of indicator lights. It means "wireless is available."
2. Ask, honestly: *"Am I dreaming?"* Look around, check that the room is
   stable, recall how you got here. Answer: *"No, I'm awake."*
3. Imagine being somewhere strange, knowing there's Wi-Fi, asking the same
   question, and this time realizing: *"This is a dream."*
4. Put the router somewhere safe. Lie down. Repeat the rule once or twice and
   let sleep happen normally.
5. On waking, write down what you remember before you check your phone.

The full 7–10 minute version is [runbooks/tonight.md](runbooks/tonight.md).

## Reference hardware

The **Linksys WRT54GS** is the reference implementation of the installation
medium. It was chosen for its distinctive silhouette, its period-correct
indicator panel, and the fact that a generation of administrators met wireless
networking through its web interface at `192.168.1.1`.

| Property | Requirement |
| --- | --- |
| Power | Optional. An unpowered unit is fully conformant. |
| Firmware | Unchanged. Do not flash, downgrade or reconfigure. |
| Radio | Irrelevant. Do not enable legacy or open Wi-Fi for this. |
| Location at night | Somewhere safe and dry. Not in the bed. |
| Ownership | Optional. Any object you associate with wireless works. |

An operator without a WRT54GS may substitute any equivalent anchor: a different
router, a printed photo, a sticker of the Wi-Fi symbol. The anchor exists to make
the waking rehearsal concrete. It does not need to show up at night.

## Protocol modules

| Document | Purpose |
| --- | --- |
| [PROTOCOL.md](PROTOCOL.md) | Operator walkthrough: ANCHOR → INCUBATE → NOTICE → CHECK → LUCID → ACT → RECORD |
| [SPEC.md](SPEC.md) | Requirement language, state machine, failure modes |
| [RFC 0001](rfc/0001-reality-phase-nat.md) | Reality Phase-NAT: translating a waking intention into a dream-usable cue |
| [RFC 0002](rfc/0002-dream-domain-name-system.md) | Dream Domain Name System: state-dependent symbol resolution |
| [RFC 0003](rfc/0003-conceptual-wlan-discovery.md) | Conceptual WLAN Discovery: Wi-Fi as an ambient capability |
| [RFC 0004](rfc/0004-lucidity-handshake.md) | Lucidity Handshake: the actual algorithm |
| [RFC 0005](rfc/0005-session-persistence.md) | Session Persistence and Recall |
| [RFC 0006](rfc/0006-security-considerations.md) | Security Considerations |
| [runbooks/tonight.md](runbooks/tonight.md) | The bedtime procedure |
| [runbooks/natural-awakening.md](runbooks/natural-awakening.md) | Optional rehearsal after an unplanned night waking |
| [runbooks/incident-response.md](runbooks/incident-response.md) | Troubleshooting |
| [docs/d-vista.md](docs/d-vista.md) | D-VISTA runtime: the system that only operates during downtime |
| [docs/glossary.md](docs/glossary.md) | Terminology |
| [examples/](examples/sample-session-log.md) | [Sample session log](examples/sample-session-log.md) and [journal template](examples/sample-dream-journal.md) |

## Known limitations

- There is no published research on Wi-Fi as a lucid-dream cue. This is a
  personal experiment built on techniques that do have research behind them.
- Most nights will produce no lucid session. Many will produce no recall. This is
  normal operation, not a fault.
- A dream that contains Wi-Fi is not a lucid dream. Only recognizing that you are
  dreaming counts.
- The dream is permitted to assign an IP address without implementing DHCP. Do
  not treat anything a dream displays, says or computes as external fact.
- Wake-on-LAN is not supported; Wake-on-Lucid may be attempted.

## Troubleshooting excerpt

```text
SYMPTOM   Dreamt about Wi-Fi all night. Was never lucid.
CAUSE     Cue resolved; handshake not attempted.
ACTION    None tonight. Rehearse the question, not the router.

SYMPTOM   Lay awake rehearsing for an hour.
CAUSE     Operator is polling reality so aggressively that they remain awake.
ACTION    Stop rehearsing. Sleep. The protocol resumes tomorrow.

SYMPTOM   Router appeared in dream, on fire, speaking French.
CAUSE     Split-horizon resolution. Expected.
ACTION    Ask whether you are dreaming. You were.
```

The full table is in [runbooks/incident-response.md](runbooks/incident-response.md).

## Safety

dDNS is designed to run without loss of sleep. It never asks you to set an alarm
to interrupt sleep, stay awake, take anything, change medication, use a bright
screen in bed, or silence a medical device. Keep glucose monitors, insulin pump
alerts and any other medical alarms exactly as they are. If the practice makes
sleep worse, increases anxiety, or brings on nightmares, stop. The threat model
is in [RFC 0006](rfc/0006-security-considerations.md).

## Status

Experimental. The first field test is tonight. Read
[runbooks/tonight.md](runbooks/tonight.md), pick up the Linksys, and go to sleep.

Licensed under the [MIT License](LICENSE). Contributions:
[CONTRIBUTING.md](CONTRIBUTING.md). History: [CHANGELOG.md](CHANGELOG.md).
