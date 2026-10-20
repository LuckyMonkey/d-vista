# RFC 0003 — Conceptual WLAN Discovery

```text
D-VISTA Working Group                                       LuckyMonkey
Document: dDNS-RFC-0003                                     October 2026
Category: Experimental / Informational

                     Conceptual WLAN Discovery:
         Wi-Fi Availability as an Ambient, Low-Fidelity Dream Cue
```

## Status of This Memo

Part of the D-VISTA document series. This memo specifies the dWLAN subsystem.
Experimental. Internal project document number; not an IETF RFC. No radio
frequencies are allocated by this document.

## Abstract

This document defines dWLAN, the cue used by D-VISTA. The cue is not a router, a network
name, an icon or a screen. The cue is the fact that **wireless connectivity is
available**. That fact can be present in a dream with no imagery at all, as
contextual knowledge, which makes it unusually cheap for a dream to produce.

## 1. Scope

This document defines what counts as discovering Wi-Fi in a dream and how
representations of it are treated. It does not define the response
([RFC 0004](RFC-0004-LUCIDITY-HANDSHAKE.md)).

## 2. Terminology

- **Capability**: something the operator can do or has access to, as opposed to
  something they see.
- **Ambient cue**: a cue that is part of the background of a situation rather
  than an object in it.
- **Representation**: any concrete form the dream gives the cue.
- **Fidelity**: the amount of perceptual detail a representation requires.

## 3. The core insight

Wi-Fi is invisible even in waking life. Nobody sees it; people know they have
it. In dreams, knowledge of this kind is abundant and free: the dreamer simply
knows things about the situation without those things being shown. Therefore:

> **Having Wi-Fi is an invisible ambient capability that requires little or no
> dream imagery.**

A cue defined as a capability can occur in nearly any dream setting, at nearly
zero rendering cost, and does not depend on the dream producing stable text or
accurate hardware, which dreams are poor at.

## 4. Discovery methods

The following are all valid discovery. None is preferred, and none is required.

| Method | Example | Fidelity |
| --- | --- | --- |
| Contextual knowledge | You just know there's Wi-Fi here. | None |
| Implied use | Something is streaming, loading, syncing, or a message arrives. | Very low |
| Dialogue | Someone mentions the Wi-Fi, or asks for the password. | Low |
| Symbol | A fan-shaped signal symbol, bars on a phone. | Medium |
| Device | A router, any router, possibly the WRT54GS. | Medium to high |
| Network name | An SSID shown on a screen. | High, often unstable |

Detection MAY be spontaneous contextual knowledge. The operator is not required
to look for anything. The rehearsal aims to make the *noticing* of
connectivity, by whichever row, bring the intention back.

## 5. Role of the reference hardware

The Linksys WRT54GS is the reference implementation of the installation medium.
It is used while awake to give the rehearsal concrete weight. Its appearance in
a dream is a medium-fidelity representation, equivalent to every other row in
section 4. It is not a prerequisite, it is not a transmitter, and its power state
during the night is irrelevant.

An operator who waits for the router to appear has restricted discovery to a
single high-fidelity representation and discarded the main advantage of the cue.

## 6. Operational considerations

- **Rehearse the fact, not the picture.** During waking rehearsal, include at
  least one imagined scenario with no router and no screen, in which the
  operator simply knows Wi-Fi is available
  ([RUNBOOK-TONIGHT.md](RUNBOOK-TONIGHT.md), step 4).
- **Notice it awake.** During the day, the moment you realize you are connected
  (a page loads, a phone joins a network) is an opportunity for a brief, honest
  check. This builds the habit that MILD relies on. Keep it occasional and calm.
- **Do not alter real networks.** Renaming your SSID or enabling a guest network
  to "strengthen the signal" is not part of the protocol and may break the
  household's actual Wi-Fi.

## 7. Failure modes

- **Silent discovery**: the cue is present but so ordinary that it is never
  noticed as anything. Expected early on.
- **Fidelity lock-in**: the operator has trained only on the router image and
  misses ambient occurrences.
- **Over-discovery**: the operator dreams of networks constantly without any
  checks. The cue is reaching the dream; the handler is not. Shift rehearsal
  toward the question.

## 8. Security Considerations

Dreamed networks have no security properties. Do not join them, do not trust
them, and do not report them to your ISP. See
[RFC 0006](RFC-0006-SECURITY-CONSIDERATIONS.md).
