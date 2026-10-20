# RFC 0005 — Session Persistence and Recall

```text
dDNS Working Group                                          LuckyMonkey
Document: dDNS-RFC-0005                                     October 2026
Category: Experimental / Informational

                   Session Persistence and Recall:
           Maintaining a Lucid Session and Logging It on Waking
```

## Status of This Memo

Experimental. Internal project document number; not an IETF RFC. Sessions are
not resumable.

## Abstract

Lucid sessions established under [RFC 0004](0004-lucidity-handshake.md) are
often short, and their contents are often lost on waking. This document
describes how to keep a session stable long enough to do one planned action, and
how to write it to persistent storage afterward.

## 1. Scope

This document covers behavior from session establishment (`LUCID`) to the
written log (`LOGGED`). It does not cover sleep onset or cue discovery.

## 2. Terminology

- **Session**: a period of lucidity.
- **Session drop**: lucidity ends, either by waking or by sliding back into an
  ordinary dream.
- **Payload**: the single planned action.
- **Flush**: writing the dream down.

## 3. Session stabilization

New lucid dreamers frequently wake up within seconds of becoming lucid,
commonly attributed to excitement. The protocol therefore specifies a short
idle period before any payload:

1. **Acknowledge.** Think, calmly, "This is a dream."
2. **Observe.** Look at the scene for a few moments. Notice detail, texture,
   light. Touch something if you can.
3. **Stay calm.** If the scene starts to fade, slow down rather than speed up.
   Keep attention on what's in front of you.

There is no guarantee these steps keep a session open. They are the commonly
recommended approach, and they are harmless.

## 4. Payload

One planned action, chosen in advance and rehearsed once before sleep. Keep it
simple. The reference payload is:

```text
# DREAMED EXAMPLE. Not a real command execution.
# Typed on any keyboard the dream provides, or spoken aloud.
$ ssh fridge
```

This is an imagined action inside a dream. Nothing connects to anything; no
packet leaves the bedroom, and no host named fridge, real or otherwise, receives
a login attempt. Whatever the dreamed terminal prints is dream content. If no
keyboard is available, say the command aloud, or look for any door labeled
"fridge" and open it. If the payload cannot be produced (`NXDOMAIN`), the session
is still a success. Look around instead.

Operators MAY substitute any other single action: looking at their hands,
asking a dream character a question, walking through a door. Operators SHOULD
NOT plan several actions; one completed action is worth more than three
forgotten ones.

## 5. Session termination

Sessions end by themselves. There is no requirement to end one deliberately and
no reason to try to stay in one longer than it lasts. Wake-on-LAN is not
supported; Wake-on-Lucid may be attempted, by simply deciding to wake up, but is
never required.

If a lucid dream becomes unpleasant, the operator MAY do any of the following:
remind themselves it's a dream and cannot hurt them, turn away from the
unpleasant element, or try to wake up gently by focusing on the body in bed.
See [runbooks/incident-response.md](../runbooks/incident-response.md).

## 6. Recall (flush to disk)

On waking, from any state:

1. **Keep still for a moment.** Don't move or reach for anything yet. Replay
   what you remember.
2. **Write or record immediately.** Paper or a voice memo. Keep screens dim;
   prefer paper if possible.
3. **Write fragments, not prose.** Keywords first; full sentences later if you
   like.
4. **Separate the two facts.** "Wi-Fi appeared: yes/no." "I knew I was dreaming:
   yes/no."
5. **Score it** using the 0–4 scale in
   [runbooks/tonight.md](../runbooks/tonight.md).
6. **Go back to sleep** if it is still night. Recall MUST NOT turn into staying
   up.

The template is [examples/sample-dream-journal.md](../examples/sample-dream-journal.md).

## 7. Operational considerations

- Do not sacrifice sleep for recall. If writing would fully wake you at 3 a.m.,
  record three keywords and sleep.
- Recall improves with practice. Even nights with no lucidity are worth
  logging, because recording dreams tends to improve dream recall over time.

## 8. Failure modes

- **Drop on excitement**: woke immediately after recognition. Still score 3.
- **Silent downgrade**: lucidity faded into ordinary dreaming. Record when it
  faded if you can.
- **Write-back corruption**: the dream gets more coherent as you write it.
  Note uncertainty explicitly.

## 9. Security Considerations

Output from a dreamed terminal is not output from a terminal. See
[RFC 0006](0006-security-considerations.md).
