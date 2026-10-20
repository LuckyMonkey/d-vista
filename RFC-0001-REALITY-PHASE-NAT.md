# RFC 0001 — Reality Phase-NAT

```text
D-VISTA Working Group                                       LuckyMonkey
Document: dDNS-RFC-0001                                     October 2026
Category: Experimental / Informational

            Reality Phase-NAT: Translation of Waking Intent
                   into Dream-Usable Representations
```

## Status of This Memo

Part of the D-VISTA document series. This memo specifies the Phase-NAT subsystem.
This memo describes an experimental practice. It is not an Internet Standard.
"RFC 0001" is an internal project document number and has no relationship to
the IETF RFC series. Distribution of this memo is unlimited; its effectiveness
is not.

## Abstract

An intention formed while awake is stored in a form suited to waking cognition:
a sentence, a plan, a deliberate decision. Dream-state cognition does not
reliably execute sentences. This document describes Phase-NAT, a metaphor for
rewriting a waking intention into a cue that dreaming cognition is likely to
encounter and act on.

## 1. Scope

This document covers the translation step only: how the intention "recognize
that I am dreaming" is bound to a cue. It does not cover recognition itself
([RFC 0004](RFC-0004-LUCIDITY-HANDSHAKE.md)) or the choice of Wi-Fi as the cue
([RFC 0003](RFC-0003-CONCEPTUAL-WLAN-DISCOVERY.md)).

## 2. Terminology

- **Inside address**: the intention as held while awake. Explicit, verbal,
  deliberate.
- **Outside address**: the form in which the intention is available while
  dreaming. Associative, contextual, triggered.
- **Translation table**: the rehearsed association between the two.
- **Phase**: a state of experience: waking, hypnagogic, or dreaming. "Phase" is
  a literary term here. It does not mean a dimension, plane or place.

## 3. Problem statement

A dreaming operator rarely thinks "I should check whether I am dreaming" on
their own initiative. Self-reflection is typically reduced during ordinary
dreams; the dreamer accepts impossible events without question. An intention
that waits to be remembered spontaneously is, in network terms, an inside host
with no outbound route.

## 4. Translation

Phase-NAT establishes the route by binding the intention to an event that the
dream will produce by itself. When that event occurs, the association fires and
the intention is retrieved. The resulting translation table has exactly one
entry:

```text
+--------------------------+------------------------------+
| Outside (dream event)    | Inside (waking intention)    |
+--------------------------+------------------------------+
| "I have Wi-Fi"           | "Check whether I'm dreaming" |
+--------------------------+------------------------------+
```

The table is built while awake, by rehearsal:

1. State the entry aloud or silently.
2. Rehearse it with the physical anchor in hand, so the entry carries sensory
   detail.
3. Rehearse the full sequence in imagination: dream event occurs, intention is
   retrieved, check is made, dream is recognized.

This is the core of MILD. Phase-NAT is a name for it.

## 5. What is not translated

Phase-NAT is a metaphor. **No information is transferred between phases.**
There is no channel between the waking world and the dream other than the
operator's own memory. In particular:

- the anchor does not emit anything that reaches the sleeper;
- real Wi-Fi in the house plays no role and need not exist;
- no external party can place an entry in the operator's table.

The only state that persists across the boundary is the state the operator put
there by rehearsing it.

## 6. Mapping persistence

NAT mappings expire when idle. So do intentions. A single rehearsal may not
survive until a dream occurs. Mitigations:

- rehearse briefly but with attention, as the last deliberate thought before
  sleep;
- re-establish the mapping after a natural night waking
  ([RUNBOOK-NATURAL-AWAKENING.md](RUNBOOK-NATURAL-AWAKENING.md));
- repeat across nights. The table is expected to become more stable with use.

Keepalives MUST NOT be sent by staying awake. A mapping that prevents sleep has
no traffic to translate.

## 7. Operational considerations

Translate one intention only. Operators commonly attempt to add entries ("and
then I'll fly, and also find my grandmother"). Each additional entry dilutes the
rehearsal. Additional actions belong in the session plan
([RFC 0005](RFC-0005-SESSION-PERSISTENCE.md)), not in the translation table.

## 8. Failure modes

- **Mapping expired**: the cue appears in a dream with no associated intention.
  The operator notices Wi-Fi and carries on with the dream.
- **Mapping inverted**: the intention appears without the cue: the operator
  dreams about practicing the technique. This is not a failure, but it is not
  lucidity either unless recognition follows.
- **Port collision**: Wi-Fi is so common in the operator's dreams already that
  it no longer stands out. Consider pairing it with a stronger rehearsal of
  the question.

## 9. Security Considerations

The principal risk of this document is literalism. An operator who believes a
real channel exists between dream and world may misattribute dream content. See
[RFC 0006](RFC-0006-SECURITY-CONSIDERATIONS.md).
