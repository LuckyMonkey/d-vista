# dDNS Specification

```text
Document:  dDNS-SPEC
Version:   0.1.0
Status:    Experimental / Informational
Scope:     Operator behavior before, during and after one sleep period
```

## 1. Requirements language

The key words **MUST**, **MUST NOT**, **SHOULD**, **SHOULD NOT** and **MAY** in
this document are used as follows:

- **MUST / MUST NOT**: required for the protocol to be what it claims to be, or
  required for safety. Violating one means you are no longer running dDNS.
- **SHOULD / SHOULD NOT**: recommended. Deviate when you have a reason.
- **MAY**: optional. Neither helps nor hurts conformance.

These words are a documentation convention borrowed from network standards. They
describe how this protocol is defined. They do **not** describe scientific
certainty about how sleep or dreaming works. Nothing in this specification is
guaranteed to produce a lucid dream.

## 2. Entities

- **Operator**: the person sleeping.
- **Anchor**: a physical object used during waking rehearsal. Reference
  implementation: Linksys WRT54GS.
- **Cue**: the semantic record "I have Wi-Fi".
- **Handler**: the rehearsed response "Am I dreaming?" followed by a genuine
  check of the current state.
- **Resolver**: the operator's mind, in whichever state it is currently running.

## 3. Requirements

### 3.1 Anchor

1. The anchor MUST be used only while the operator is awake.
2. The anchor MUST NOT be modified, reflashed, reconfigured or connected to any
   network for the purposes of this protocol. Powering it is MAY.
3. The anchor MUST be stored somewhere safe and dry during sleep, and MUST NOT be
   placed in the bed.
4. Success MUST NOT depend on the anchor appearing in a dream.

### 3.2 Cue

1. The cue MUST be the semantic fact of having Wi-Fi, not any particular image
   of it.
2. Representations such as an SSID, a signal icon, a router, a password prompt
   or a phone MAY occur and MUST be treated as equivalent to the bare fact.
3. The cue MUST NOT be treated as evidence of dreaming. It is a trigger for a
   check.

### 3.3 Handler

1. On resolution of the cue, the operator SHOULD ask "Am I dreaming?" and SHOULD
   examine the situation: continuity of events, stability of the environment,
   memory of how they arrived.
2. While awake, the handler MUST return the honest answer, "No, I'm awake." Reality
   checks are for increasing orientation, not undermining it.
3. The operator SHOULD rehearse the handler mindfully rather than mechanically.

### 3.4 Sleep

1. The operator MUST NOT set an alarm for the sole purpose of interrupting sleep
   under this version of the protocol.
2. The operator MUST NOT stay awake deliberately, restrict sleep, or use any
   substance or medication change to improve results.
3. The operator MUST NOT silence, disable or move out of hearing range any
   medical alarm, including glucose and insulin alerts.
4. The operator SHOULD stop rehearsing as soon as rehearsal begins to delay sleep.
5. The operator MAY use a natural, unplanned awakening for a brief rehearsal, per
   [runbooks/natural-awakening.md](runbooks/natural-awakening.md).

### 3.5 Recording

1. On waking, the operator SHOULD record the dream before other activity.
2. The record MUST distinguish "the cue appeared" from "I recognized I was
   dreaming."
3. Content generated inside a dream MUST NOT be treated as external fact.

## 4. State machine

```text
            anchor + rehearsal            actual sleep
  +-------+ -----------------> +-------------+ --------------> +----------+
  | AWAKE |                    | SLEEP_ONSET |  (unobserved)    | DREAMING |<-----+
  +-------+                    +-------------+                  +----------+      |
      ^                                                   Wi-Fi     |             |
      |                                                  noticed    v    no       |
      |                                                       +----------+ recog. |
      |                                                       | CHECKING |--------+
      |                                                       +----------+
      |                                                 recognized  |
      |                                                 as dreaming v
      |          wrote note       +--------+    woke       +-------+
      +---------------------------| LOGGED |<--- RECALL <--| LUCID |
                                  +--------+               +-------+
```

| State | Trigger | Next |
| --- | --- | --- |
| `AWAKE` | physical anchor + rehearsal | `SLEEP_ONSET` |
| `SLEEP_ONSET` | actual sleep | `DREAMING` (unobserved) |
| `DREAMING` | Wi-Fi concept noticed | `CHECKING` |
| `CHECKING` | recognized as dreaming | `LUCID` |
| `CHECKING` | no recognition | `DREAMING` |
| `LUCID` | woke | `RECALL` |
| `RECALL` | wrote note | `LOGGED` |

Additional transitions, not shown in the main table:

| State | Trigger | Next |
| --- | --- | --- |
| `DREAMING` | woke | `RECALL` |
| `SLEEP_ONSET` | still awake after a reasonable time | `AWAKE`; stop rehearsing |
| `LUCID` | lucidity lost, dream continues | `DREAMING` |
| `RECALL` | nothing remembered | `LOGGED` with score 0 |
| `LOGGED` | next night | `AWAKE` |

### 4.1 Runtime guarantees

There is no runtime guarantee that the transition `DREAMING -> CHECKING` occurs.
On most nights it will not. There is likewise no guarantee that `CHECKING`
leads to `LUCID`, or that any of it is remembered. The transition
`SLEEP_ONSET -> DREAMING` is unobserved by design: the operator cannot watch
themselves fall asleep, and SHOULD NOT try.

## 5. Failure modes

| Code | Description | Detail |
| --- | --- | --- |
| `F1 CUE_ABSENT` | No Wi-Fi in any recalled dream. | Normal. Incubation is probabilistic. |
| `F2 CUE_NO_HANDLER` | Wi-Fi appeared; no question was asked. | The most likely failure. Rehearse the question. |
| `F3 FALSE_NEGATIVE` | Question asked in the dream; concluded "awake". | Check the situation, not one object. |
| `F4 SESSION_DROP` | Lucid briefly, then woke. | Excitement. Observe before acting. |
| `F5 RECALL_LOSS` | Lucid, but details lost by morning. | Record sooner, in fewer words. |
| `F6 SLEEP_DEGRADED` | Rehearsal delayed sleep or caused waking. | Stop. Sleep takes precedence over protocol. |
| `F7 MISATTRIBUTION` | Dream content treated as real information. | See [RFC 0006](rfc/0006-security-considerations.md). |

Operational responses are in
[runbooks/incident-response.md](runbooks/incident-response.md).

## 6. Conformance

An operator is conformant with dDNS 0.1.0 if they rehearse the cue and handler
with an anchor while awake, sleep normally, and record the outcome honestly.
Achieving lucidity is not a conformance requirement. A night with a score of
zero, logged accurately, is a fully conformant run.
