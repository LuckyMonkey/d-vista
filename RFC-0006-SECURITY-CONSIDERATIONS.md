# RFC 0006 — Security Considerations

```text
D-VISTA Working Group                                       LuckyMonkey
Document: dDNS-RFC-0006                                     October 2026
Category: Experimental / Informational

                 Security Considerations for D-VISTA
               and the Dream Domain Name System (dDNS)
```

## Status of This Memo

Part of the D-VISTA document series. This memo specifies the security model for all D-VISTA subsystems.
Experimental. Internal project document number; not an IETF RFC. This memo
is normative for every other document in the series. Where it conflicts with
them, it wins.

## Abstract

D-VISTA has no network attack surface, because it has no network. Its risks are to
sleep, to mood, and to the operator's sense of what is real. This document lists
those risks and the controls that address them.

## 1. Scope

All D-VISTA and dDNS documents, runbooks and examples, and any operator running them.

## 2. Assets

In priority order:

1. The operator's sleep.
2. The operator's safety, including medical devices and alarms.
3. The operator's orientation: a reliable sense of being awake when awake.
4. The operator's wellbeing at bedtime.
5. Lucidity. A distant fifth.

## 3. Threat model

### 3.1 T1: Overselling the metaphor

**Threat.** The operator, or a reader, takes the networking language literally
and believes that dreams connect to networks, that the router transmits into
sleep, or that dream content can carry real information.

**Controls.** Every document states that networking is an analogy. No physical
network traffic crosses the sleep boundary. Contributions that claim otherwise
are rejected ([CONTRIBUTING.md](CONTRIBUTING.md)).

### 3.2 T2: Disrupted sleep

**Threat.** Rehearsal delays sleep, an operator wakes repeatedly to check
progress, or sets alarms to create awakenings.

**Controls.** Rehearsal is brief and ends when the operator lies down to sleep.
Version 0.1.0 uses no alarms to interrupt sleep. Natural awakenings may be used
briefly. If sleep worsens, the protocol stops (section 4).

### 3.3 T3: Distressing dreams

**Threat.** Focusing on dreams may increase nightmares, unpleasant lucid
dreams, or frightening sleep paralysis in some people.

**Controls.** No technique in dDNS attempts to induce sleep paralysis or to stay
conscious while the body falls asleep. Inside a lucid dream, the operator may
look away, remind themselves it's a dream, or wake up gently. Distress is a stop
condition.

### 3.4 T4: Impaired reality testing

**Threat.** Frequent reality checks, done anxiously, could make the operator
doubt whether they are awake.

**Controls.** Waking checks MUST return the honest answer "awake." The checks
are meant to make orientation sharper. Anyone with a history of
dissociation, derealization, psychosis or similar experiences should not run this
protocol without talking to their clinician first.

### 3.5 T5: Medical alarms

**Threat.** In pursuit of undisturbed REM sleep, the operator silences,
disables or moves away a glucose monitor, insulin pump alert or other medical
alarm.

**Controls.** Forbidden, without exception. Silence only nonessential
disturbances. A medical alarm that wakes you mid-lucid-dream has done its job.

### 3.6 T6: Dream output treated as external fact

**Threat.** The operator treats something produced in a dream (a password,
a server's response, a message from a person, a prediction) as true information
about the world.

**Controls.** All dream content is untrusted and unauthenticated. The dream is
authoritative for nothing. The dreamed `ssh fridge` in
[RFC 0005](RFC-0005-SESSION-PERSISTENCE.md) connects to nothing and its output
means nothing outside the dream. Do not type anything a dream told you into a
real terminal.

### 3.7 T7: Performance pressure

**Threat.** The experiment turns bedtime into a test the operator is failing.

**Controls.** A night with score 0, logged honestly, is a conformant run
([SPEC.md](SPEC.md), section 6). There is no streak to maintain.

## 4. Stop conditions

Stop the protocol and sleep normally if any of the following occur:

- falling asleep takes noticeably longer, or night waking increases;
- bedtime becomes a source of anxiety;
- nightmares or frightening sleep paralysis become more frequent;
- after waking, it is harder than usual to tell dream from memory;
- anything else makes you feel worse.

If symptoms persist after stopping, consult a doctor.

## 5. Out of scope

- Network security of the anchor. It is not reconfigured and does not need to be
  on. Do not enable legacy encryption or open networks for this project.
- Attacks by dream characters. They have no credentials.

## 6. Residual risk

With all controls in place, the main residual risk is that nothing happens and
the operator gets a normal night's sleep. This risk is accepted.
