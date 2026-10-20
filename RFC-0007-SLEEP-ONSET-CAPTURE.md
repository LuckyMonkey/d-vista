# RFC 0007 — Sleep-Onset Capture Interface (N1)

~~~text
D-VISTA Working Group                                  LuckyMonkey
Document: D-VISTA-RFC-0007                             October 2026
Category: Experimental / Informational

                   Sleep-Onset Capture Interface
          Hypnagogic Recall Without Lucidity Claims
~~~

## Status of This Memo

Experimental D-VISTA extension. Not an IETF RFC. Does not alter the normative LCP handshake specified in [RFC 0004](RFC-0004-LUCIDITY-HANDSHAKE.md).

## Abstract

This memo defines a separate, optional capture channel for ideas and imagery recalled on waking near sleep onset. Historical inspiration: Dalí's key and Edison's dropping ball(s). Related evidence concerns **N1 sleep and creative insight**, not reliably inducing lucidity.

## 1. Interface contract

- **Input:** a waking question or theme, optionally the dWLAN semantic cue “I have Wi-Fi.”
- **Attempt:** a short, safe resting period.
- **Trigger:** natural waking, or an optional low-risk prop demonstration during supported daytime rest.
- **Output:** a *first recollection* recorded immediately after waking.
- **Validation:** the operator distinguishes recalled imagery from interpretation; no unmeasured sleep stage is reported as confirmed N1.
- **Failure:** no recalled content, degraded sleep, distress, injury risk. Stop rather than retrying compulsively.

## 2. N1 and REM are not interchangeable

| Interface | Sleep phase targeted | Primary endpoint |
| --- | --- | --- |
| **N1 Capture (this RFC)** | Hypnagogic sleep onset; N1 not confirmed without instrumentation | Reported imagery or associations |
| **LCP (RFC 0004)** | Dreaming; often REM in studied cases | Recognizing “I am dreaming” while the dream continues |

An N1 fragment does **not** satisfy LCP session authentication.

## 3. Procedure

Follow [RUNBOOK-N1-CAPTURE.md](RUNBOOK-N1-CAPTURE.md). Use natural awakening and journaling as the default. The historical object-drop trick is not a requirement. Nighttime alarms and deliberate sleep deprivation remain unsupported under D-VISTA 0.1.

## 4. Evidence boundaries

Lacaux et al. (2021) reported higher rates of identifying a hidden rule after brief N1 sleep than after remaining awake in a specific laboratory task. The study does not establish that dropping a ball improves lucid dreaming, does not imply insight is always correct, and does not validate the project-specific Wi-Fi cue.

MIT's Dormio system (Horowitz et al., 2020; 2023) studies targeted *dream content* near sleep onset. That is a separate result from lucid-dream induction. See the [evidence register](EVIDENCE.md).

## 5. Security and safety considerations

Never impair sleep, disable medical alarms, or use hazardous falling objects. Reality orientation is preserved: the sleeping experience is subjective, and any dream-generated answer requires waking verification. If experimentation worsens sleep, terminate the protocol. See [RFC 0006](RFC-0006-SECURITY-CONSIDERATIONS.md).

## 6. Implementation status

**Specified for human-only manual testing.** No electronic detector, sensor, app, or automatic audio cue is shipped or claimed. D-VISTA remains a documentation-first project.
