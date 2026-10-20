# Runbook: Incident Response

```text
Runbook:    D-VISTA-RB-INCIDENT-RESPONSE
Audience:   operator, the morning after
Hours:      the helpdesk is staffed by you
```

Find the code that matches what happened. Each entry gives the symptom, the
probable cause in plain language, and what to do. None of the fixes involve
losing sleep.

## Severity levels

| Level | Meaning |
| --- | --- |
| `INFO` | Normal behavior. No action needed. |
| `WARN` | Adjust rehearsal. |
| `CRIT` | Stop the protocol. Sleep normally. |

## Status codes

### `ERR_HOST_ACTIVE` (INFO)

- **Symptom.** You finished reading the docs, waited, and nothing happened.
- **Cause.** The host is awake. D-VISTA cannot run on the machine where its
source is being read. The installation succeeded; execution requires sleep.
- **Action.** Go to bed at your usual time. Do not stay up to "test" it.

### `INSTALL_SUCCEEDED_NO_SESSION` (INFO)

- **Symptom.** You did the bootstrap and slept, and got no lucid dream, or no
recall at all.
- **Cause.** The expected outcome on most nights. Rehearsal raises the odds; it
does not guarantee anything.
- **Action.** Log the night honestly, even as a 0. Repeat on nights you feel like
it. A few nights of practice is a fairer test than one.

### `NO_SIGNAL` (INFO)

- **Symptom.** No dreams recalled at all.
- **Cause.** Normal. Many nights have no recall, especially at first.
- **Action.** Keep paper by the bed. Lie still for a moment on waking before
moving. Recall tends to improve with regular journaling.

### `NO_CARRIER` (INFO)

- **Symptom.** You recalled dreams, but the wireless concept never appeared in
them.
- **Cause.** Incubation is partial. The dream didn't produce the cue.
- **Action.** Emphasize scenario C (no router, just knowing there's Wi-Fi)
during rehearsal, so the cue doesn't depend on the dream drawing anything.

### `NXDOMAIN` (INFO)

- **Symptom.** You were lucid and couldn't produce the thing you planned (no
keyboard, no door).
- **Cause.** The dream didn't produce the concept. Retrieval failure, not a
signal of anything.
- **Action.** You were lucid, which is the success condition. Look around
instead.

### `STALE_CACHE` (WARN)

- **Symptom.** The router, a network or the docs appeared in the dream, but the
rule didn't come with them. You saw the WRT54GS and thought nothing of it.
- **Cause.** The dream reconstructed the scenery from memory and dropped the
instruction (see [Deferred Semantic Reconstruction](BOOT-SEQUENCE.md#3-deferred-semantic-reconstruction-dsr)).
The anchor was rehearsed more strongly than the rule.
- **Action.** Spend less time on the router and more on the question. The
router is only the installation medium.

### `CONNECTION_REFUSED` (WARN)

- **Symptom.** Wi-Fi was in the dream. You noticed it. You didn't ask anything.
- **Cause.** Cue reached the dream; the intention didn't come with it. The most
common early result.
- **Action.** Shift rehearsal time from the router to the question. In the
imagined scenarios, linger on the moment of asking.

### `TIMEOUT` (WARN)

- **Symptom.** You asked "Am I dreaming?" in the dream and decided you were awake.
- **Cause.** Cached response. The question was asked without really looking.
- **Action.** Rehearse checking the situation: how did I get here, what was I
doing before, does this place make sense. In waking practice, actually look
before answering.

### `TOO_MANY_REDIRECTS` (INFO)

- **Symptom.** The dream was entirely about Wi-Fi, routers, passwords, networks,
or explaining this project to someone, but you were never lucid.
- **Cause.** Incubation working, handshake not completing. The dream turned the
intention into plot.
- **Action.** Log as score 2. Good sign. Continue unchanged for a few nights.

### `CONNECTION_RESET_BY_PEER` (INFO)

- **Symptom.** The operator woke. Often right after becoming lucid.
- **Cause.** Waking ends every session. Waking right after recognition is
commonly attributed to excitement.
- **Action.** Log immediately. If you were lucid, score 3 even if it lasted
seconds. Next time, spend the first moments just observing calmly before doing
anything.

### `PACKET_LOSS` (INFO)

- **Symptom.** You were lucid, or think you were, but remember almost nothing.
- **Cause.** Dream memory fades fast.
- **Action.** Write keywords first thing, before moving or checking your phone. If
you're unsure whether you were lucid, record it as uncertain and score
conservatively.

### `DUPLICATE_SESSION` (INFO)

- **Symptom.** You "woke up," wrote your dream down, then actually woke up.
- **Cause.** False awakening. Common around dream-focused practice.
- **Action.** None needed. On waking, one calm check ("Am I awake? Yes, the room
is stable") is fine. Then accept the answer and get on with the day.

### `HOST_UNREACHABLE` (WARN)

- **Symptom.** You forgot to do the routine, or were too tired.
- **Cause.** Being a person.
- **Action.** None. The 60-second version is fine. Skipping a night is fine.

### `BROADCAST_STORM` (WARN)

- **Symptom.** You lay awake rehearsing, or kept thinking about the experiment
instead of sleeping.
- **Cause.** Over-rehearsal. Polling reality so aggressively that the operator
remains awake.
- **Action.** Shorten the routine. Say the intention once, then think about
something else entirely. If it continues, take a few nights off.

### `HOSTILE_PEER` (CRIT if recurring)

- **Symptom.** Nightmares, unpleasant lucid dreams, or frightening sleep
paralysis.
- **Cause.** Dream-focused practice can make some people more aware of difficult
dreams.
- **Action.** In a lucid dream, look away, remind yourself it's a dream, or wake
up gently. If it happens more than once, or is upsetting, stop the protocol. If
it continues after stopping, talk to a doctor.

### `SPLIT_BRAIN` (CRIT)

- **Symptom.** While awake, reality checks make you uneasy, or you're less sure
than usual what's real or what you dreamt.
- **Cause.** Reality checks are supposed to confirm wakefulness. If they're doing
the opposite, the protocol is harming orientation.
- **Action.** Stop immediately. Do not do reality checks. Sleep normally. Talk to
a doctor if it doesn't clear up quickly.

### `LINK_DEGRADED` (CRIT)

- **Symptom.** You're sleeping worse: longer to fall asleep, more waking, tired
during the day.
- **Cause.** The protocol is costing sleep.
- **Action.** Stop. Sleep takes precedence. Resume only if and when you want to,
in its shortest form.

### `MEDICAL_ALARM` (not an incident)

- **Symptom.** A glucose monitor, insulin pump or other medical alarm woke you
during a dream, possibly a lucid one.
- **Cause.** The alarm worked.
- **Action.** Respond to the alarm exactly as you normally would. Never silence or
move medical alarms for this protocol.

## Escalation

There is no escalation path beyond stopping. If something persists after you
stop, the right next step is a doctor, not a configuration change.
