# D-VISTA — Post-Build Refactor Runbook

**For:** Claude Code / Codex  
**Stage:** SECOND PASS ONLY — run after the original `ddns` implementation completes.  
**Working directory:** the existing local dDNS repository.  
**Target identity:** **D-VISTA** — *Dream Virtual Interface for State Transition and Awareness*.  
**Subsystem retained:** **dDNS** — *Dream Domain Name System*.  
**Primary change:** make the Markdown documentation itself the fictional installation medium of a waking-memory-based lucid-dream protocol.

> **Core premise:** D-VISTA is a piece of software that cannot run on the machine where its source code is hosted. Reading the documentation is the installation process. The operator's prospective memory is its deployment target. Sleep is the production environment. The system is only operational during scheduled downtime.

## 0. Immediate execution instructions for the coding agent

1. **Do not start this refactor until the prior dDNS-writing agent has finished and its file writes have settled.** Never run concurrent destructive edits against the same checkout.
2. Inspect the checkout, current branch, existing documents, and `git status --short`. Read the *actual files produced by the first agent*, especially `README.md`, `PROTOCOL.md`, `SPEC.md`, `runbooks/tonight.md`, `docs/architecture.md`, and all RFCs.
3. Make the changes described below **in the existing repository**. Preserve all sound technical and dream-induction material. Do not replace the original output wholesale with a shorter new project.
4. If the tree already includes user changes, preserve them and make focused, reviewable edits. Never `git reset --hard`, clean untracked work, discard changes, force-push, or overwrite a remote.
5. **Do the work, not a plan.** Create and edit complete Markdown files, test links and prose consistency, then report changes and any remaining decisions.
6. Don't rename the GitHub repository or change git remotes. The *display name* changes to D-VISTA now; GitHub `LuckyMonkey/ddns` may remain the URL until the owner chooses to rename it.

No runtime dependencies. No React, Node, TypeScript, Python, package managers, CI setup, containers, telemetry, browser app, or invented hardware drivers. Markdown-only is ideal; an optional tiny dependency-free shell link checker is acceptable if the original agent already provided one.

## 1. The breakthrough in one paragraph

The first iteration was a collection of imaginary networking RFCs explaining lucid dreaming. The second iteration should feel like **software that has been installed into the reader by virtue of reading its documentation**. It is a deliberately self-referential instruction set. Readers clone a repo expecting software; there is no binary; the documentation trains a concrete prospective-memory response. They go to sleep. If they dream that wireless connectivity is available, the learned response may be recalled and turn the dream lucid. Dream content may resemble a reboot or the documentation being fetched from GitHub, but that is *dream-generated reconstruction*, not an actual network transfer. The project is both a deadpan fiction of software deployment and a usable, unguaranteed cognitive exercise.

Preserve both layers simultaneously:

- **In-universe:** The README installs a dormant module. The operator is a host. The dream environment resolves a cached runtime image. The repository appears to be retrieved during downtime. Lucidity grants an interactive session.
- **Out-of-universe:** The reader voluntarily rehearses a mnemonic cue and intention using dream incubation and MILD-inspired practice. Neither GitHub nor the physical router can transmit software into dreams. Genuine lucidity means noticing *that one is dreaming*, not merely imagining Wi-Fi.

**Do not make the reveal contemptuous.** It should land as: *Oh, the install instructions actually did something to my memory.*

## 2. Rename architecture; preserve dDNS

Make this distinction consistent in all updated files:

| Name | Role | Literal status |
| --- | --- | --- |
| **D-VISTA** | Umbrella product / cognitive runtime / documentation installation | Fictional software framing |
| **dDNS** | Symbolic name resolution and assumed context inside dreams | Metaphor, not physical DNS |
| **Phase-NAT** | Translate an intention rehearsed while awake into a dream-usable reminder | Metaphor, not a cross-reality tunnel |
| **dWLAN** | Awareness that Wi-Fi is available, regardless of imagery | Targeted semantic dream sign |
| **LCP** | Lucidity Control Protocol: notice cue → remember intention → recognize dreaming | Rehearsed mental sequence |
| **WRT54GS** | Waking installation medium / tangible mnemonic anchor | Real optional Linksys device |
| **Session log** | Operator's recollection after waking | Subjective, fallible record |

Keep existing paths and relative links working. Preserve existing `rfc/0001` through `0006` names; modify their introductory framing and headings if necessary. Avoid mass moves that would destroy working cross-links. The original `ddns` name is now explicitly a **component** of D-VISTA, not a deprecated name to erase.

The header should generally read:

```text
D-VISTA
Dream Virtual Interface for State Transition and Awareness

Subsystems: dDNS | Phase-NAT | dWLAN | LCP
Reference hardware: Linksys WRT54GS
Host requirements: one sleeping operator
Runtime dependencies: none
```

The README's first screen should make the new brand unmistakable while inviting readers to keep going.

## 3. Treat documentation as an installable artifact

The user experience should proceed through five **cognitive phases** and one **post-session log**:

```text
$ git clone <repo>             # optional, normal waking-life Git operation
$ cat README.md               # waking: the installation medium is read

       SOURCE / GITHUB                OPERATOR
    +--------------------+        +-------------------------+
    | Markdown / text    |------->| READ / ENCODE INTENTION |
    | no executable     |        | WRT54GS = physical key   |
    +--------------------+        +-----------+-------------+
                                            |
                                       sleep onset
                                            v
                                 +-------------------------+
                                 | DREAM ENVIRONMENT       |
                                 | cached concept: Wi-Fi   |
                                 +-----------+-------------+
                                             |
                                     notice Wi-Fi?
                                       /          \
                                     no            yes
                                     |              |
                              normal dream    'am I dreaming?'
                                                    |
                                              recognize dream?
                                              /             \
                                             no             yes
                                             |               |
                                        normal dream      LUCID
                                                              |
                                                           waking
                                                              v
                                                        RECALL / LOG
```

**Exact core recognition:** `Whenever I notice I have Wi-Fi, I remember to check whether I'm dreaming.`

The physical router is NOT the required dream object. The Wi-Fi concept is invisible, portable between dream scenes, and low-fidelity. The dream only needs to assert *connectivity exists*. SSIDs, a phone screen, routers, DHCP leases and terminal screens remain optional scenery.

### Two kinds of download, never confuse them

- **Literal GitHub clone:** Real files may be copied to a real device while awake.
- **Dream-state "pull":** The dream may reconstruct the *feeling, appearance, or semantic knowledge* that D-VISTA was fetched. No physical packets cross the sleep boundary; no HTTP traffic is promised or required.

Name the phenomenon **Deferred Semantic Reconstruction (DSR)**, explicitly an **invented in-project term**, not a neuroscience finding. DSR means the operator's memory may reconstruct elements of a previously read document during dreaming. If an agent uses DSR, define it clearly and never pretend it is peer-reviewed terminology.

Do **not** imply reading text forces a dream, installs hidden subconscious code, or creates an external connection. The actual mechanism being attempted is explicit, voluntary prospective-memory training.

## 4. The central architectural joke: operational during downtime

This is a design constraint, not a throwaway joke. Integrate it into README, protocol state descriptions, session handling and troubleshooting.

> **The host must enter downtime before the service can become available.**

Maintain consistent distinctions:

| Condition | Host/operator | D-VISTA service | Commentary |
| --- | --- | --- | --- |
| `AWAKE` | Online | `INSTALLED / DORMANT` | Source can be read, service cannot run |
| `SLEEP_ONSET` | Entering scheduled downtime | `BOOT_PENDING` | No guaranteed dream |
| `DREAMING` | Asleep | `RUNTIME_AVAILABLE` | Session can still be nonlucid |
| `LUCID` | Asleep and aware of dreaming | `INTERACTIVE_SESSION` | Desired outcome, not guaranteed |
| `AWAKE_AGAIN` | Online | `DISCONNECTED` | Record what is recalled |

Do not insist that all dreams are REM dreams or that the system can actually measure sleep stage. REM may be mentioned as a common dream-rich period; there are dreams in other stages too.

Good dry lines (select a few, don't dump them all in one section):

- `The service is only operational during scheduled downtime.`
- `The host must be offline before the operator can connect.`
- `No binaries are shipped. The installation media is this document.`
- `All GitHub downloads occur before execution. Runtime downloads are reconstructed from memory.`
- `No physical network traffic crosses the sleep boundary.`
- `WARNING: Attempts to inspect the service from the waking host terminate the session.`
- `CONNECTION_RESET_BY_PEER — Operator woke.`
- `NO_CARRIER — Wireless concept failed to appear in recalled dream.`
- `Successful boot does not imply interactive authentication.`
- `The user must be unconscious for the interface to become available, then conscious of dreaming to obtain access.`

**Precise punchline:** Normal computing associates uptime with availability; D-VISTA makes the host's downtime its operating window. Don't accidentally define *the same machine's uptime* as both sleep and wake without disambiguation.

## 5. The reader should be inside the program before noticing

Construct a deliberate reading progression in the new landing page:

1. **First paragraph:** A plausible, slightly eerie technical product abstract. Avoid immediate wink-wink explanation, but never claim paranormal capabilities.
2. **Installation:** The ordinary-looking GitHub user reads a minimal 60–90 second "bootstrap" instruction from Markdown. The instruction is real and actionable as a mnemonic practice.
3. **System readiness:** Documentation reports `INSTALLED / DORMANT`. No actual process exists; this is in-universe output.
4. **Downtime condition:** The README explains that attempting to execute while awake produces `ERR_HOST_ACTIVE`.
5. **Operation:** The actual Wi-Fi recognition practice is explained in a linked runbook.
6. **Interpretation:** A conspicuous, readable implementation note explains the cognitive mechanism and limits, without deflating the literary atmosphere.
7. **Postmortem:** The reader discovers that their own recall is the log sink.

The reader's realization should be: **"I read the source, and the source was an instruction to my memory."** This is the self-referential design. Avoid suggesting an automatic or involuntary mental takeover.

## 6. Refactor files and paths

Modify existing files, retaining detailed research, links and useful content:

### `README.md` — full identity refactor

- Change top heading to `# D-VISTA` and full acronym underneath.
- Introduce downtime paradox in opening ~120 words.
- Keep a prominent ~60-second practical quick start with physical anchor, Wi-Fi awareness, reality questioning and sleep intention.
- Rename project-level sections to match D-VISTA; list `dDNS` as a subsystem.
- Include a terminal-style **mock status** display. Label it as *illustrative* or put it clearly in the context of the fictional protocol, not as an actual shell output.
- Link to `BOOTSTRAP.md`, `runbooks/tonight.md`, the RFCs, and `docs/implementation-notes.md`.
- State explicitly that no literal cross-sleep transmission or guaranteed lucidity occurs.
- Preserve license, previous useful information and existing internal links.

### `BOOTSTRAP.md` — NEW, the most important new file

This is the in-universe installer and out-of-universe experiment. Keep it short enough for a sleepy person (roughly 350–650 words), centered on a **90-second mnemonic seed** followed by optional deep rehearsal elsewhere.

Write the steps in terse imperative voice:

1. Observe the Linksys WRT54GS if one is available; otherwise recall the image of a familiar access point. No powered network required.
2. State the single rule: *When I notice Wi-Fi, I check whether I'm dreaming.*
3. Perform one **honest waking-state check** (where am I, how did I arrive here, what happened before this?). While awake conclude accurately that one is awake.
4. Close eyes and imagine **three different settings**, with one that has **no visible router, phone, or computer**. In each, know that Wi-Fi is available, then rehearse realizing that it is a dream.
5. Let go of the visualization and fall asleep normally. A good night of sleep matters more than forcing lucidity.
6. If Wi-Fi becomes apparent in a dream, recall the rule, check state, and become lucid *only if the operator recognizes the dream*.
7. Upon awakening, write down what was actually recalled.

The text should end on a dry, memorable footer:

```text
INSTALLATION COMPLETE.
SERVICE STATUS: DORMANT.
NEXT REQUIRED ACTION: ENTER SCHEDULED DOWNTIME.
```

Do not include night-time reconfiguration, SSIDs, hidden browser scripts, bedtime light exposure, altered medications or medical alarms. The experiment must work without actual router configuration.

### `docs/boot-sequence.md` — NEW, narrative architecture

Explain the GitHub-to-memory-to-dream conceit using the two-column distinction **Documented Fiction / Actual Cognitive Action**. Include a small stage-by-stage diagram and how in-dream “git pull” is a dream-generated reconstruction. Define Deferred Semantic Reconstruction as fictional nomenclature. Distinguish source retrieval from in-dream representation. Include `ERR_HOST_ACTIVE` and `CONNECTION_RESET_BY_PEER` as in-universe errors.

### `docs/implementation-notes.md` — NEW, out-of-universe truth

Keep this easy to find and plainspoken. Clarify no executable program is installed in the brain, real DNS is not perspective-only, no Wi-Fi packets or actual GitHub traffic occur during sleep, and neither router nor Markdown guarantees lucidity. The actual method is cue rehearsal, prospective memory, incubation and a dream-state check. Explain basic sleep hygiene and logging with conservative science. No invented research, citations, success rates, physical planes or reality breaches.

### `PROTOCOL.md` and `SPEC.md`

Wrap existing dDNS detail in D-VISTA system-wide flow. Introduce states `INSTALLED`, `DORMANT`, `BOOT_PENDING`, `RUNTIME_AVAILABLE`, `INTERACTIVE_SESSION`, `DISCONNECTED` where helpful. Don't force a breaking rewrite of original state-machine names—add a clear mapping table rather than leaving contradictions. Mark protocol language as fictional convention rather than claims of actual implementation.

### `docs/architecture.md`

Add architecture view of human memory as deployment target; “ambient connectivity” as a semantic dream sign, and downtime as the service operating window. Explicitly distinguish what a dream *assumes* from what external reality *contains*.

### `docs/glossary.md`

Add and alphabetize `D-VISTA`, `Deferred Semantic Reconstruction (DSR)`, `downtime`, `ERR_HOST_ACTIVE`, `host`, `installation medium`, `interactive session`, `runtime`, and `semantic trigger`. Retain originals including dDNS and Phase-NAT.

### Existing RFC files under `rfc/`

Keep all six. Make restrained edits so terminology reflects D-VISTA's role as umbrella project. dDNS RFC remains a subsystem specification. Extend failure modes where logical, not every RFC with duplicated jokes. No generic find-and-replace of `dDNS` to `D-VISTA`—it would destroy the design.

### `runbooks/tonight.md`

Retain the full original real-world lucid-dream procedure. Add an introductory "Deployment" section that links to the **short** bootstrap. Clear that reading documentation is waking preparation only, and that lucidity is not guaranteed. Keep the cue universal: awareness of having Wi-Fi. Maintain medical alarm and sleep safeguards.

### `runbooks/incident-response.md`

Add failure cases: `ERR_HOST_ACTIVE` (reader expects dream execution while awake); `INSTALL_SUCCEEDED_NO_SESSION` (read docs but no dream recall/lucidity); `STALE_CACHE` (dream contains router but no Wi-Fi intention); `CONNECTION_RESET_BY_PEER` (awakening). Every error maps to a plausible sleep/memory phenomenon and one practical nonintrusive suggestion.

### `examples/sample-session-log.md`

Make illustrative events clearly fictional. Include *one non-success scenario* as well as success; don't conflate a lucid dream with actual communication to GitHub or the real Fridge server.

### `CONTRIBUTING.md` and `CHANGELOG.md`

Update displayed product identity, explain dDNS retention, document this as an identity/experience refactor (e.g. `Unreleased` section). Do not fabricate published version history. Preserve actual credits/license.

### `AGENTS.md` / `CLAUDE.md` only if already present

Update agent pointers and project-wide identity if such files are part of the repository. Avoid attaching contradictory instructions. Do not create new instructions files gratuitously.

## 7. Exact comedic posture

The project should read like a 2006 Linksys appliance manual crossed with a straight-faced software RFC. Self-referential, slightly ominous, but welcoming and completely comprehensible.

**Do:**

- use a few measured system messages in terminal-style blocks;
- let ordinary technical precision carry the absurdity;
- imply the joke by describing real psychological instructions as install/configure/boot/log;
- make the text itself the thing a person rehearses before sleep;
- retain enough actionable instructions that someone could meaningfully try it tonight;
- have the reveal land after a credible technical introduction.

**Don't:**

- become an ARG claiming to compromise minds or secretly install code;
- assert paranormal physics, real cross-reality network traffic, telepathy, or objective information retrieved from sleeping GitHub;
- bury truthful implementation notes so deeply they are inaccessible;
- insert jokes in every sentence or three pages of pseudoscientific filler;
- require technical equipment, paid tools or apps for the sleep practice;
- turn it into an interactive SPA or real router firmware project;
- turn the repository into Windows Vista fan fiction: the name is an allusion, not licensed OS branding.

### Canonical sample prose (adapt, don't copy everything verbatim)

> D-VISTA is a documentation-distributed runtime intended for execution during operator downtime. It is installed by reading the specification and suspended while the host remains awake. Upon entering a dream, the host MAY instantiate a cached representation of the protocol without retaining any file system. A successful session requires recognition of the dream state. Network connectivity is simulated by the host's own contextual assumptions. No RF interface is opened.

> **Operator note:** D-VISTA may appear to have been pulled from GitHub during a dream. This is an expected form of reconstructed dream content, not evidence of a network connection. The source was read before the operator went offline.

> **WARNING:** Attempting to inspect the live system by waking the host will disconnect the current session.

## 8. Validation / definition of done

Run or perform all of the following, report concrete results:

- [ ] `git status --short` inspected; original in-progress build was complete before refactor began.
- [ ] `README.md` is branded **D-VISTA**. dDNS stays the named symbolic resolver subsystem.
- [ ] `BOOTSTRAP.md`, `docs/boot-sequence.md`, and `docs/implementation-notes.md` exist and contain finished, non-placeholder content.
- [ ] A reader who sees only the README and BOOTSTRAP can do a **90-second preparatory practice** without external tools.
- [ ] The practical trigger is *noticing Wi-Fi availability*; a visible router/SSID/screen is optional.
- [ ] The text's self-reference is clear: reading the repository is the fictional installation step, and remembering its intention during a dream is the hoped-for activation.
- [ ] The "GitHub pulled while sleeping" motif is framed as dream-generated reconstruction; never a physical remote fetch.
- [ ] Sleep = host downtime / D-VISTA operating window. Dreaming does not automatically equal lucidity.
- [ ] A separate implementation note cleanly distinguishes the story from a real cognitive mechanism.
- [ ] Existing RFCs, research caveats, warnings and links are intact; no duplicate or broken state-machine definitions.
- [ ] `git diff --check` passes.
- [ ] All local relative Markdown links resolve, including anchors if checker supports them.
- [ ] No fake journal evidence, imagined scientific findings, unverified clinical claims, or promised success rates.
- [ ] No router firmware changes, sleeping Wi-Fi emissions, forced awakenings, sleep deprivation, disabling medical alarms or altered medication schedules required.
- [ ] No new software runtime dependencies.
- [ ] No automatic remote rename, push, commit, or publish without permission.

## 9. Agent hand-off command

Paste this into **Claude Code or Codex after the first agent finishes**:

> Read `REFACTOR-RUNBOOK.md` completely. This is a second-pass refactor of the dDNS repository already produced by a prior agent. Inspect the working tree and preserve its content. Implement the D-VISTA identity and documentation-as-installer design, keeping dDNS as a subsystem. Create and finish the three new Markdown documents, refactor the specified existing ones, keep all links valid, and validate the definition of done. The documentation must be an actual lucid-dream mnemonic practice concealed inside dead-serious system documentation, with explicit reality/safety limits. Don't stop at planning. Don't touch the remote or overwrite unrelated work. Report the touched files and tests run.

## 10. Final repository experience

A developer visits GitHub, reads what seems to be a niche network protocol and notices the installation command. The command is to read a short set of instructions and shut down the host for the night. They recognize, several lines later, that **their own memory** was the install destination. They might dream of a network, and might remember the deliberately practiced cue. If lucidity follows, they have a D-VISTA session. If not, the protocol remains best effort.

The documentation should have a memorable, completely sober final line:

> **D-VISTA: the service is only operational during downtime.**
