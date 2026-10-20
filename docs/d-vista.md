# D-VISTA Runtime Operations

```text
D-VISTA SYSTEM STATUS
-------------------------------------
Operator awake:        OFFLINE
Operator asleep:       BOOTING
REM detected:          ONLINE
Lucidity established:  SESSION UP
Operator awakened:     CONNECTION LOST
-------------------------------------
```

D-VISTA is the runtime environment that hosts dDNS. It has one unusual
operational property:

> **D-VISTA requires the operator to be offline before establishing a
> connection.**

During normal operating hours the system is unavailable. When the operator
loses consciousness, the system boots. Sleep is not downtime. Sleep is the
production environment.

## 1. Installation

```text
D-VISTA INSTALLATION COMPLETE

Runtime:              Biological
Installation target:  Prospective memory
Execution state:      DORMANT
Required downtime:    Sleep
Network interface:    Conceptual WLAN
Reference hardware:   Linksys WRT54GS

NOTICE:
The software cannot be executed from this terminal.
The operator must enter downtime to continue.
```

There is no installer. Installation is the waking rehearsal in
[runbooks/tonight.md](../runbooks/tonight.md). The banner above is illustrative;
no command prints it.

## 2. Operational vocabulary

Ordinary operations terms, inverted for a system whose production window is the
night. The left column is the joke; the right column is what it means in
practice.

| Term | D-VISTA meaning | In plain terms |
| --- | --- | --- |
| Scheduled downtime | Bedtime | Go to bed at your usual time. |
| Cold boot | Falling asleep | Unobserved by design. Do not try to watch it. |
| Uptime | Time spent dreaming | Most dreaming happens in REM sleep, more of it later in the night. |
| Unplanned uptime | Insomnia | The protocol's worst outage. Stop rehearsing and rest. |
| User authentication | Reality check | An honest look at the situation. Awake, it returns "awake". |
| Session established | Lucidity | Knowing you are dreaming. Control is not required. |
| Kernel panic | Nightmare | Look away, remind yourself it is a dream, or wake gently. |
| Session timeout | Waking up | Log immediately. The cache expires in minutes. |
| System restore | Falling back asleep | Do it. Recall must not turn into staying up. |
| Monitoring | Dream journal | The only monitoring that does not take the system down. |

## 3. Observability

Warning: attempting to observe system operation may terminate the session.

This is accurate. Checking whether you are falling asleep tends to keep you
awake, and excitement during a lucid dream tends to wake you up. D-VISTA is
therefore monitored only after the fact, through the journal. There are no live
dashboards, and none should be built. A device that watches the operator sleep
is out of scope for version 0.1.0 ([research-and-limitations.md](research-and-limitations.md),
section 4).

## 4. Service level

- **Availability:** nightly, during downtime only.
- **Guarantee:** none. Consciousness discovery is best-effort.
- **Maintenance window:** the day. Rehearsal happens here.
- **Escalation:** stop the protocol and sleep normally
  ([runbooks/incident-response.md](../runbooks/incident-response.md)).

D-VISTA: making downtime productive since 2026. Downtime remains the priority;
productivity is optional.
