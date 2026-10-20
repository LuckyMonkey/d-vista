# RFC 0002 — Dream Domain Name System

```text
D-VISTA Working Group                                       LuckyMonkey
Document: dDNS-RFC-0002                                     October 2026
Category: Experimental / Informational

                     Dream Domain Name System (dDNS):
               State-Dependent Resolution of Named Concepts
```

## Status of This Memo

Part of the D-VISTA document series. This memo specifies the dDNS subsystem, the symbolic resolver at the core of D-VISTA.
Experimental. Internal project document number; not an IETF RFC. This memo
defines no wire format, no port, no record types registered anywhere, and no
queries that leave the operator's head.

## Abstract

In waking life, a name such as "my kitchen" resolves to a stable place. In
dreams, the same name may resolve to a place that looks nothing like it, and the
dreamer accepts the answer without complaint. This document models that
behavior as a name system with state-dependent resolution, and describes how a
single deliberately published record ("I have Wi-Fi") can be used to trigger a
fresh lookup of the operator's own state.

## 1. Scope

This document describes a vocabulary for talking about how concepts behave in
dreams. It is an analogy. It does not claim that memory works like DNS, or that
DNS works like memory.

## 2. Terminology

- **Name**: a concept the operator can think of: a place, person, object, fact.
- **Resolution**: the experience the concept produces in the current state.
- **Resolver**: the operator's mind, running in waking or dreaming mode.
- **Cache**: assumptions the resolver holds without checking.
- **Zone**: the set of names available in one state.

## 3. Resolution model

### 3.1 Dynamic resolution

A dreaming resolver may bind the same name to different representations within
one dream. The house may be "home" while looking like a hotel; a colleague may
be "your brother". This is normal dream behavior and is not an error.

### 3.2 Split-horizon behavior

Real DNS can return different answers to the same query depending on where the
client sits. Waking and dreaming resolvers behave analogously:

```text
query: location.current
  waking view   -> bedroom (verified by stable perception)
  dreaming view -> "the office" (asserted, unverified)

query: self.state
  waking view   -> awake (verified)
  dreaming view -> awake (served from cache)
```

Split-horizon resolution is expected; different states may resolve the same
symbol differently.

### 3.3 Cached assumptions

The dreaming resolver relies heavily on cache. In particular, the record
`self.state = awake` is held with an effectively infinite TTL and served without
revalidation. Most dreams never query it at all. The objective of the protocol
is to force one revalidation.

## 4. The published record

The operator publishes one record before sleep, through rehearsal:

```text
wifi.available   IN  CONCEPT  "true"
                 ; on resolve: query self.state with no cache
```

When `wifi.available` resolves in a dream, by any route and in any
representation, the attached instruction triggers a fresh, non-cached query of
`self.state`. The answer from a fresh query in a dream should, if the operator
genuinely checks, be "dreaming". That answer is lucidity.

The record syntax above is decorative. Nothing parses it.

## 5. Cache invalidation on waking

On waking, the dream zone is invalidated. Records resolved during the dream
begin to expire immediately and are generally gone within minutes unless written
down. Operators SHOULD flush the session to a journal before performing any
other lookup, including looking at a phone.

## 6. Response codes

| Code | dDNS meaning |
| --- | --- |
| `NOERROR` | The concept appeared. |
| `NXDOMAIN` | The concept could not be produced: the planned action, the intention, the cue. This is retrieval failure and is not a sign of any outside signal. |
| `SERVFAIL` | The dream changed or collapsed while the concept was being formed. |
| `REFUSED` | The operator had the cue and dismissed it as unremarkable. |

## 7. Operational considerations

- Do not publish many records. One cue with one handler is the design.
- Do not attempt to resolve external facts in a dream (lottery numbers, other
  people's thoughts, the contents of real servers). The dreaming resolver will
  answer confidently. It is authoritative for nothing.

## 8. Failure modes

The most common failure is a cache hit on `self.state`: the operator notices Wi-Fi,
asks the question in a perfunctory way, and the cached "awake" is returned. The
handshake in [RFC 0004](RFC-0004-LUCIDITY-HANDSHAKE.md) requires examining the
situation precisely to defeat this.

## 9. Security Considerations

Records resolved in a dream are untrusted. See
[RFC 0006](RFC-0006-SECURITY-CONSIDERATIONS.md).
