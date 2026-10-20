# D-VISTA Protocol Walkthrough

This document describes the D-VISTA protocol, including its dDNS, Phase-NAT,
dWLAN and LCP subsystems, from the operator's side: what you do, in
what order, and what is actually happening in your head at each step. The
normative definition is [SPEC.md](SPEC.md). The bedtime procedure is
[runbooks/tonight.md](runbooks/tonight.md).

## Overview

```text
ANCHOR -> INCUBATE -> NOTICE -> CHECK -> LUCID -> ACT -> RECORD
  awake     awake      dream    dream    dream   dream   awake
 |<- install ->|     |<---------- downtime ----------->|  log
 DORMANT             RUNTIME_AVAILABLE    INTERACTIVE_SESSION
```

ANCHOR and INCUBATE are the installation ([BOOTSTRAP.md](BOOTSTRAP.md)). Everything
after that only happens while the host is asleep.

Each stage below has two descriptions. **Analogy** is the networking framing.
**Cognitive step** is what you are really doing. Where the two disagree, the
cognitive step wins.

## 1. ANCHOR

**Analogy.** The operator provisions a physical installation medium. The
WRT54GS is bound to a single record: `wifi.available = true`.

**Cognitive step.** You handle a real object and attach a meaning to it. Holding
and naming the router gives the intention a concrete, multisensory memory: the
weight, the antennas, the lights. That makes it easier to recall later than an
abstract sentence.

The anchor is used **while awake only**. It does not need to be powered, nearby,
or present in the dream.

## 2. INCUBATE

**Analogy.** The record is published to the local resolver with a long TTL, and
a handler is registered: on resolution of `wifi.available`, issue query
`self.state?`.

**Cognitive step.** This is MILD-style prospective-memory training. You rehearse
the intention *"When I notice I have Wi-Fi, I'll remember to check whether I'm
dreaming,"* and you visualize it working: being somewhere in a dream, realizing
Wi-Fi is available, asking the question, and recognizing the dream. Rehearsing
the theme before sleep is also a form of dream incubation, which can make the
theme more likely to show up.

Rehearse mindfully, a handful of times. Then stop and let sleep happen.

## 3. NOTICE

**Analogy.** Conceptual WLAN discovery. The dream advertises connectivity. No
beacon frames are involved; the network is announced as a fact of the
environment.

**Cognitive step.** At some point in a dream, you *know* Wi-Fi is available.
This might come with an image (a router, a signal icon, someone asking for the
password) but it does not have to. In dreams, a lot of information arrives as
background knowledge rather than as something seen. You can simply know that
this is your aunt's house even though it looks like an airport. "There's Wi-Fi
here" belongs to the same category, which is why it was chosen. See
[RFC 0003](rfc/0003-conceptual-wlan-discovery.md).

## 4. CHECK

**Analogy.** Loopback query. The resolver queries its own state before
forwarding anything.

**Cognitive step.** Noticing Wi-Fi brings back the bedtime intention, and you
actually ask: *"Am I dreaming?"* A useful check looks at the situation, not
just at an object: How did I get here? Does this place make sense? Was I just
somewhere else? Is text stable if I look at it twice?

The cue itself is not evidence. Wi-Fi exists in waking life too. Its only job is
to make you ask.

## 5. LUCID

**Analogy.** Handshake complete. Session established.

**Cognitive step.** You recognize that you are dreaming. That recognition, and
nothing else, is the success condition. Seeing a router in a dream is not
lucidity. Dreaming about checking whether you're dreaming, and concluding you're
awake, is not lucidity either. It is a legitimate and common failure.

## 6. ACT

**Analogy.** First command on the new session. Keep it small; the link is
fragile.

**Cognitive step.** Pause and observe the scene for a moment. Excitement tends
to end lucid dreams, so stay calm and let the scene settle. Then do one planned
action. The reference action is to type `ssh fridge` on any keyboard the dream
provides. That is a dreamed action: nothing connects to anything. If no keyboard
appears, say it aloud, or just look around. See
[RFC 0005](rfc/0005-session-persistence.md).

## 7. RECORD

**Analogy.** Flush the session log to persistent storage before the cache is
invalidated.

**Cognitive step.** Dream memories fade fast after waking. Write down or record
what you remember before doing anything else, and keep two facts separate:
whether Wi-Fi appeared, and whether you knew you were dreaming. Use the template
in [examples/sample-dream-journal.md](examples/sample-dream-journal.md).

## Success and failure states

| Outcome | Score | Meaning |
| --- | --- | --- |
| Nothing recalled | 0 | Packet loss on the recall path. Common and harmless. |
| Dream recalled | 1 | Session logged; no cue observed. |
| Wi-Fi appeared | 2 | Incubation reached the dream; handshake did not start or did not complete. |
| Wi-Fi led to recognition | 3 | Handshake complete. This is the protocol's success condition. |
| Lucid and action attempted | 4 | Full session, including the planned action. |

A score of 2 is useful data: it means the cue is reaching the dream. The next
step is to rehearse the *question*, not to rehearse the router harder.

The global failure state is **sleep got worse**. If that happens, stop. See
[RFC 0006](rfc/0006-security-considerations.md).
