# Architecture

This document explains the design choices behind dDNS, in particular why the cue
is the *fact of having Wi-Fi* rather than any object or image. These are design
arguments. None of them has been tested, and none of them shows that Wi-Fi is a
better cue than the alternatives. They explain why it is a reasonable one to
try.

## 1. Data path

```text
  WAKING PLANE                     |   DREAM PLANE (no physical link)
                                   |
  +-------------+                  |
  | WRT54GS     |  handle, name    |
  | (anchor)    |--------+         |
  +-------------+        |         |
                         v         |
                +-----------------+|
                | intention:      ||
                | "When I notice  ||
                |  I have Wi-Fi,  ||
                |  I check."      ||
                +--------+--------+|
                         |  memory, not transmission
  - - - - - - - - - - - -|- - - - -+- - - - - - - - - - - - - - - - -
                         v
                         |   +---------------------------+
                         +-->| dream asserts: Wi-Fi here |  (any form,
                             +-------------+-------------+   or no form)
                                           |
                                           v
                             +---------------------------+
                             | "Am I dreaming?"          |
                             | check the situation       |
                             +------+-------------+------+
                                    |             |
                               recognized     not recognized
                                    v             v
                                 LUCID        dream continues
```

The only thing that crosses the dashed line is memory: an intention that was
rehearsed while awake and is still available while asleep. No physical network
traffic crosses the sleep boundary.

## 2. Why an invisible capability

### 2.1 Dreams contain assumed knowledge

A great deal of dream content is not seen; it is known. The dreamer knows whose
house this is, knows the exam is today, knows the car is theirs, often without
any of it being rendered convincingly. Having Wi-Fi is the same kind of fact. A
dream can assert it without drawing it. This makes it a candidate for a cue that
does not depend on the dream generating any particular image.

### 2.2 Low rendering requirements

Dreams are known to be unreliable at stable text and detailed interfaces. A cue
that depends on reading an SSID or seeing a specific signal icon depends on
exactly the kind of detail dreams handle poorly. "There's Wi-Fi" requires no
detail at all. If the dream does draw something (a router, a phone showing
bars), that is a bonus, not a requirement.

### 2.3 Broad context coverage

Wi-Fi plausibly exists in houses, schools, offices, shops, trains, airports and
hotels, and a dream can make it available in a forest without objection. A cue
that fits almost any setting gets more opportunities to appear than one tied to
a specific place or object.

### 2.4 Prospective memory fit

MILD works by forming an intention to notice something in the future and
respond to it. Prospective memory research generally finds that intentions are
easier to act on when the cue is distinctive and the link to the action is well
rehearsed. "Wi-Fi" is a short, concrete concept, and pairing it with a physical
object gives the rehearsal something to hold onto.

### 2.5 The counter-argument

The same features cut the other way. Wi-Fi is so ordinary in waking life that it
may not feel noteworthy when it appears in a dream, which is the classic way a
cue gets missed. That is why the protocol trains the question, not the
recognition of Wi-Fi itself, and why [RFC 0004](../rfc/0004-lucidity-handshake.md)
treats "Wi-Fi appeared, no question asked" as the expected first failure.

## 3. Perspective-dependent resolution

In real DNS, the answer to a query can depend on who is asking. Split-horizon
DNS returns internal addresses to clients inside a network and public addresses
to clients outside it. Resolvers cache answers for a time-to-live and may serve
stale data until it expires. None of this makes DNS subjective; it is
deterministic given the resolver and its configuration.

dDNS borrows the shape of this, not the substance. The same symbol resolves
differently depending on the state of the resolver:

| Query | Waking resolver | Dreaming resolver |
| --- | --- | --- |
| `wifi.available` | Yes, from the router in the hall. | Yes, from nowhere in particular. |
| `location.current` | Bedroom, stable. | "My school," shaped like a ferry. |
| `self.state` | Awake (verified). | Awake (cached, stale). |

The last row is the whole point. A dreaming resolver tends to return the cached
answer "awake" without checking. The handler exists to force a fresh lookup.
Split-horizon resolution is expected; different states may resolve the same
symbol differently.

## 4. Components that are deliberately absent

- **No device in the bedroom.** There is no audio, light or haptic cueing during
  sleep. Some research setups do this under controlled conditions; dDNS 0.1.0
  does not.
- **No alarms.** No wake-back-to-bed schedule. See
  [research-and-limitations.md](research-and-limitations.md).
- **No software.** The runtime is the operator. The repository is the
  documentation.
