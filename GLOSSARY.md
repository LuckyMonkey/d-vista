# Glossary

Each entry gives the real meaning of the term, then its meaning inside D-VISTA.
Where the two diverge, the D-VISTA meaning is an analogy.

### Anchor

A physical object handled during waking rehearsal to make an intention
concrete. In dDNS, the Linksys WRT54GS. Used only while awake.

### ARP (Address Resolution Protocol)

Maps an IP address to a hardware address on a local network. In dDNS:
associating a familiar concept with whatever the dream has bound it to tonight.
A dream may answer "who has the kitchen?" with a gymnasium. No gratuitous ARP
should be trusted.

### Cue

A recognizable event that triggers a rehearsed response. In dDNS, the
semantic fact "I have Wi-Fi."

### dDNS (Dream Domain Name System)

This protocol. A framework for resolving one waking intention in dream-state
cognition. Not real DNS. Sends no queries.

### Deferred Semantic Reconstruction (DSR)

An invented project term, not a research finding. Dreams draw on recent waking
experience; DSR names the case where pieces of a document you read and rehearsed
reappear in a dream, usually altered. A dream of downloading this repository is
DSR, not a download. See [boot-sequence.md](BOOT-SEQUENCE.md).

### DHCP (Dynamic Host Configuration Protocol)

Hands out IP addresses on a network. In dDNS: the dream's habit of assigning
you a role, location or backstory without any negotiation. The dream is
permitted to assign an IP address without implementing DHCP.

### DNS (Domain Name System)

The distributed system that translates names into addresses. In dDNS: the
general process by which a concept ("home", "Wi-Fi") is resolved into an
experience. The name-to-meaning mapping can change between states.

### Downtime

In ordinary operations, time a system is unavailable. In D-VISTA, sleep, which
is the only time the system runs. Scheduled downtime is bedtime; insomnia is
unplanned uptime.

### Dream sign

Something that recurs in your dreams or is characteristic of them, which can
serve as a cue to recognize dreaming. dDNS installs an artificial one.

### D-VISTA

Dream Virtual Interface for State Transition and Awareness. The project, and
the runtime that hosts dDNS, Phase-NAT, dWLAN and LCP: the operator's sleeping
mind, described as a service that is unavailable while the host is awake. See
[d-vista.md](OPERATIONS.md).

### dWLAN

Dream WLAN. The subsystem that covers awareness that Wi-Fi is available, with or
without any imagery. Specified in [RFC 0003](RFC-0003-CONCEPTUAL-WLAN-DISCOVERY.md).

### ERR_HOST_ACTIVE

The error the service returns when started while the operator is awake. Not a
fault: D-VISTA cannot run on the machine where its source is being read.

### False awakening

Dreaming that you have woken up. Common around lucid dreams. Treat the first
minutes after waking as a good moment to ask the question once, calmly, and then
accept the answer.

### Firewall

Filters traffic between networks by rule. In dDNS: the boundary that keeps
dream content from being treated as waking fact. See
[RFC 0006](RFC-0006-SECURITY-CONSIDERATIONS.md). Default policy: drop.

### Handshake

A protocol exchange that establishes a session. In dDNS: notice cue, recall
intention, check state, recognize dreaming. Defined in
[RFC 0004](RFC-0004-LUCIDITY-HANDSHAKE.md).

### Host

The operator's waking self. The host is online when awake and in downtime when
asleep. Host downtime is the service's operating window.

### Hypnagogia

The transitional state while falling asleep, often with brief imagery or
fragments of thought. In dDNS, the `SLEEP_ONSET` state. Observe it if it happens;
do not try to hold onto it.

### Installation medium

Whatever carries the rule into memory: this documentation, and the physical
anchor used while reading it. Reference implementation: the WRT54GS.

### Interactive session

The service state corresponding to lucidity: dreaming and knowing it. A dream
without that recognition is `RUNTIME_AVAILABLE`, not a session.

### LCP (Lucidity Control Protocol)

The rehearsed sequence: notice the cue, recall the rule, check the situation,
recognize the dream. Specified in [RFC 0004](RFC-0004-LUCIDITY-HANDSHAKE.md).

### Lucidity

Being aware, during a dream, that you are dreaming. The only success condition
in dDNS. Control over the dream is optional and not required.

### MILD (Mnemonic Induction of Lucid Dreams)

A technique developed by Stephen LaBerge: rehearse the intention to recognize
that you are dreaming next time a particular thing happens, and visualize doing
so. dDNS is MILD with a networking-themed cue.

### NAT (Network Address Translation)

Rewrites addresses as traffic passes between networks. In dDNS, Phase-NAT:
the metaphorical translation of a waking intention into something usable in a
dream. See [RFC 0001](RFC-0001-REALITY-PHASE-NAT.md).

### NXDOMAIN

The DNS response for a name that does not exist. In dDNS: the dream cannot
produce a concept you were looking for, such as the planned action or the
intention itself. It is not a sign of an outside signal; it is retrieval
failure.

### Phase-NAT

The metaphorical translation of a waking intention into a reminder that works
in dreams. No information crosses between states except through the operator's
own memory. See [RFC 0001](RFC-0001-REALITY-PHASE-NAT.md).

### Prospective memory

Remembering to do something in the future when the right moment comes, such
as remembering to buy milk when you pass the shop. MILD relies on it.

### Reality check

A deliberate test of whether you are awake or dreaming. In dDNS, a check of
the whole situation (continuity, stability, how you got here), always answered
honestly.

### Runtime

In software, the environment a program executes in. In D-VISTA, dream-state
cognition: available only during host downtime, and best-effort.

### Semantic trigger

A cue defined by meaning rather than appearance: "I have Wi-Fi" rather than
"I see a router." It can be present in a dream that draws nothing at all.

### Split-horizon DNS

Serving different DNS answers to different clients, usually inside and outside
a network. In dDNS: the same symbol resolving differently awake and asleep.
Expected behavior.

### SSID (Service Set Identifier)

The broadcast name of a wireless network. In dDNS: one optional way the dream
might represent "I have Wi-Fi". Never required.

### TTL (Time To Live)

How long a cached answer remains valid. In dDNS: how long an intention stays
available after rehearsal, and, on waking, how long dream memories last before
expiring. The second TTL is short. Write things down.

### WBTB (Wake Back To Bed)

Waking during the night, staying up briefly, then returning to sleep, often
combined with MILD. Usually done with an alarm. D-VISTA 0.1.0 does not use alarms;
it only uses awakenings that happen on their own. See
[RUNBOOK-NATURAL-AWAKENING.md](RUNBOOK-NATURAL-AWAKENING.md).

### Wi-Fi

Wireless local area networking based on the IEEE 802.11 standards. In dDNS:
the cue, as a fact rather than an image. You can have Wi-Fi without seeing
anything.

### WRT54GS

A Linksys wireless router from the 802.11g era, recognizable by its two
antennas, blue and black case, and front indicator lights. In dDNS: the
reference anchor. It transmits nothing into your sleep.
