# RFC 0004 — Lucidity Handshake

```text
D-VISTA Working Group                                       LuckyMonkey
Document: dDNS-RFC-0004                                     October 2026
Category: Experimental / Informational

                   Lucidity Handshake (LCP):
          Cue, Recall, Check and Recognition in Dream-State Cognition
```

## Status of This Memo

Part of the D-VISTA document series. This memo specifies LCP, the Lucidity Control Protocol.
Experimental. Internal project document number; not an IETF RFC. Session
establishment is best-effort.

## Abstract

This document defines LCP, the algorithm at the center of D-VISTA: the four-step
sequence that turns noticing Wi-Fi in a dream into recognizing the dream. Only
the final step counts as success.

## 1. Scope

This document specifies the handshake and its failure cases. Cue discovery is
in [RFC 0003](0003-conceptual-wlan-discovery.md); what to do once lucid is in
[RFC 0005](0005-session-persistence.md).

## 2. Terminology

- **Initiator**: the cue (Wi-Fi noticed).
- **Responder**: the operator's own self-reflection.
- **Session**: a period of lucidity.
- **Loopback**: a query the operator directs at their own state.

## 3. The handshake

```text
 Dream                          Operator
   |                               |
   |--- 1. CUE: "I have Wi-Fi" --->|
   |                               |  2. RECALL: "I meant to check."
   |                               |
   |<-- 3. CHECK: loopback query --|  "Am I dreaming?"
   |       examine situation       |   - how did I get here?
   |                               |   - does this place make sense?
   |                               |   - does text/detail hold steady?
   |                               |
   |--- 4. RECOGNIZE ------------->|  "This is a dream."
   |                               |
   |====== session established ====|
```

### 3.1 CUE

Wi-Fi is noticed, in any representation, including pure knowledge.

### 3.2 RECALL

The cue retrieves the bedtime intention. This is the prospective-memory step,
and it is where most attempts fail. Rehearsal targets this step.

### 3.3 CHECK

The operator asks "Am I dreaming?" and actually looks. A useful check examines
the situation as a whole:

- **Continuity**: Can I remember how I got here and what I was doing ten minutes
  ago?
- **Plausibility**: Is anything here impossible or out of place?
- **Stability**: If I look away and back, does text or detail stay the same?
- **Context**: I went to bed tonight intending to do this. Is this bed?

The check SHOULD be honest in both directions. While awake, it returns "No, I'm
awake," and that answer is correct. While dreaming, the same honest check is
more likely to turn up something that doesn't fit.

### 3.4 RECOGNIZE

The operator becomes aware that they are dreaming. **This, and only this, is
success.** Steps 1–3 without step 4 are an unestablished session.

## 4. Why the cue is not proof

Wi-Fi is available in most waking environments. If the cue alone were treated
as evidence of dreaming, the operator would be wrong most of the day. The cue
is a trigger to perform a check. The check, not the cue, carries the
information.

This also keeps waking checks safe: because the answer while awake is honestly
"awake," the practice reinforces orientation instead of eroding it.

## 5. Failure modes

| Failure | Description | Mitigation |
| --- | --- | --- |
| No initiation | Wi-Fi was in the dream; the intention never came back. | Rehearse the link between Wi-Fi and the question, with imagined scenarios. |
| Cached response | The question was asked; "awake" was returned without looking. | Rehearse checking the situation, not just saying the words. |
| Rationalized anomaly | Something was off; the dream explained it away. | During rehearsal, practice saying "that doesn't fit, so this is a dream." |
| Incorporated cue | The dream turned the intention into plot: you dream of explaining dDNS to someone. | None needed; it shows incubation working. Continue. |
| Stale cache | The router or the docs appeared; the rule did not. | Rehearse the question more than the anchor. See `STALE_CACHE` in [incident response](../runbooks/incident-response.md#stale_cache-warn). |
| Brief session | Recognition happened; you woke seconds later. | Counts as success. See [RFC 0005](0005-session-persistence.md). |

The incorporated-cue case deserves emphasis. An ordinary, non-lucid dream full
of routers, networks and Wi-Fi is a common early outcome. It is evidence that the
cue is reaching dream content. It is not lucidity, and the journal SHOULD record
it as score 2, not 3.

## 6. Operational considerations

- The handshake can only be rehearsed while awake. Rehearse it as a story that
  ends in recognition, several times, with attention.
- Daytime practice: when you notice you're connected, do one honest check,
  occasionally. Do not do this so often that it becomes background noise or a
  source of unease. Avoid polling reality so aggressively that the operator
  remains awake.

## 7. Security Considerations

A handshake that concludes "dreaming" while the operator is in fact awake is a
serious fault. The check exists to increase orientation. If waking checks begin
to produce doubt rather than confirmation, stop the protocol. See
[RFC 0006](0006-security-considerations.md).
