# D-VISTA Runtime Operations

```text
D-VISTA SERVICE STATUS                         (illustrative)
-------------------------------------------------------------
Host awake:            ONLINE     service INSTALLED / DORMANT
Host falling asleep:   DOWNTIME   service BOOT_PENDING
Host dreaming:         DOWNTIME   service RUNTIME_AVAILABLE
Dream recognized:      DOWNTIME   service INTERACTIVE_SESSION
Host woke:             ONLINE     service DISCONNECTED
-------------------------------------------------------------
```

D-VISTA (Dream Virtual Interface for State Transition and Awareness) is the
runtime that hosts dDNS and its sibling subsystems. It has one unusual
operational property:

> **The host must enter downtime before the service can become available.**

Two machines' worth of vocabulary meet here, so this document is careful about
whose uptime it means:

- **Host** = the operator's waking self. Host uptime is being awake.
- **Service** = D-VISTA. Service availability is dreaming.

Host downtime is the service's operating window. Sleep is not downtime for the
service. Sleep is the production environment.

## 1. Installation

```text
D-VISTA INSTALLATION COMPLETE                  (illustrative)

Runtime:              Biological
Installation target:  Prospective memory
Execution state:      DORMANT
Required downtime:    Sleep
Network interface:    Conceptual WLAN (dWLAN)
Reference hardware:   Linksys WRT54GS

NOTICE:
The software cannot be executed from this terminal.
The operator must enter downtime to continue.
```

There is no installer program. Installation is reading
[BOOTSTRAP.md](BOOTSTRAP.md) and doing what it says. No command prints the
banner above.

## 2. Operational vocabulary

| Term | D-VISTA meaning | In plain terms |
| --- | --- | --- |
| Scheduled host downtime | Bedtime | Go to bed at your usual time. |
| Cold boot | Falling asleep | Unobserved by design. Do not try to watch it. |
| Service uptime | Time spent dreaming | Dreams occur throughout sleep; REM periods, longer later in the night, are especially dream-rich. |
| Unplanned host uptime | Insomnia | The worst outage. Stop rehearsing and rest. |
| Authentication | Reality check | An honest look at the situation. Awake, it returns "awake". |
| Interactive session | Lucidity | Knowing you are dreaming. Control is not required. |
| Kernel panic | Nightmare | Look away, remind yourself it is a dream, or wake gently. |
| Session timeout | Waking up | Log immediately. The cache expires in minutes. |
| System restore | Falling back asleep | Do it. Recall must not turn into staying up. |
| Monitoring | Dream journal | The only monitoring that does not take the service down. |

## 3. Observability

WARNING: attempts to inspect the service from the waking host terminate the
session.

This is accurate. Checking whether you are falling asleep tends to keep you
awake, and excitement during a lucid dream tends to wake you. D-VISTA's present implementation is monitored after waking through structured dream reports. Independent sleep-laboratory instrumentation could provide stronger objective evidence of sleep and volitional responses, but no such instruments are included in this release. Consumer devices do not verify lucidity. See [REPLICATION.md](REPLICATION.md).

Detailed monitoring is outside the current protocol ([RESEARCH.md](RESEARCH.md),
section 4).

## 4. Service level

- **Availability:** nightly, during host downtime only.
- **Guarantee:** none. Consciousness discovery is best-effort.
- **Maintenance window:** the day. Rehearsal happens here.
- **Escalation:** stop the protocol and sleep normally
  ([RUNBOOK-INCIDENT-RESPONSE.md](RUNBOOK-INCIDENT-RESPONSE.md)).

D-VISTA's operating window is normal sleep. Preserving restorative sleep is a design requirement.
