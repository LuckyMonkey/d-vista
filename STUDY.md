# D-VISTA Study Protocol — DV-001

Status: **Prospective, single-operator, exploratory study**. Revision: 2026-10-20.

## Research question

Can a prospective-memory cue built around the **awareness that Wi-Fi is available** be incorporated into dreams and, when noticed, prompt recognition that the operator is dreaming?

The Linksys WRT54GS is an optional waking mnemonic anchor. It is not an active transmitter into sleep. The project measures dream content and lucidity; external downloads, DNS lookups, and network packets are not predicted outcomes.

## Hypotheses established before data collection

- **H1 — Incorporation:** the proportion of recalled dreams containing wireless-connectivity awareness is greater on trained nights than baseline nights.
- **H2 — Cue-to-awareness:** on at least some nights, Wi-Fi awareness occurs **before** explicit recognition of dreaming and is reported as a trigger.
- **H3 — Task retention:** among lucid dreams, the operator attempts the precommitted dream task more frequently on trained than baseline nights. Because sessions may be rare, treat this as exploratory.
- **H4 — Acceptability:** average self-reported sleep quality is not materially worse on trained nights. A decline triggers protocol review or discontinuation.

A null result **does not prove impossibility**; it limits evidence under the tested conditions. An apparently successful dream does not establish any waking-world Wi-Fi connection.

## Design

A low-burden, repeated-measures N-of-1 design. No sleep restriction.

1. **Baseline (7 ordinary nights):** record dream recall and sleep quality without adding the Wi-Fi routine. If already practicing regularly, label the baseline *exposed* and do not represent it as a clean control.
2. **Training (14 nights):** before normal bedtime, follow [RUNBOOK-TONIGHT.md](RUNBOOK-TONIGHT.md) for approximately 3–8 minutes. Stop sooner if it makes sleep harder.
3. **Follow-up (7 ordinary nights):** do not perform the formal rehearsal; continue brief morning logs. Residual learning can persist, so this is not a return to a truly unexposed baseline.
4. **Optional replication:** repeat additional cycles on a calendar agreed in advance. Do not select nights post hoc based on remembered success.

Record all scheduled nights, **including zero recall, incomplete records, and interruptions**. A small number of nights cannot provide convincing efficacy estimates; the first cycle establishes feasibility and baseline variation, not proof.

## Primary outcomes and denominators

**P1 — Lucid nights:** nights with explicit in-dream recognition / all **logged** nights with acceptable recall confidence. Present also the count per **all scheduled nights** to reveal missingness.

**P2 — Wi-Fi-cue nights:** nights where Wi-Fi awareness appears / nights with ≥1 recalled dream. Report **no recalled dream** separately, not as evidence that the cue was absent.

**P3 — Triggered lucidity:** nights with a report that Wi-Fi awareness directly preceded dream recognition / all lucid nights with recalled trigger sequence. Attribution is subjective and should be coded with confidence.

**P4 — Sleep cost:** change in sleep-quality rating and reported difficulty falling asleep relative to baseline; report descriptive distributions and harms, not only successes.

Dream counts can supplement night counts but must be stored separately. Multiple dreams in a single night are **not independent trials**.

## Evidence codes

| Code | Minimum observation | Not sufficient |
| --- | --- | --- |
| E0 | No remembered dream, or unknown | An assumption that no dreams happened |
| E1 | One or more nonlucid dream reports | Retrospective interpretation after waking |
| E2 | Wireless cue appeared in a dream | Seeing a router without noticing connectivity is recorded separately |
| E3 | Explicit awareness *during the dream* that this is a dream | Saying “I am dreaming” as a dream plot line, without clear recognition |
| E4 | Lucid, and planned action actually attempted | A completed objective inferred without recall |
| ELAB | REM verified via polysomnography plus time-stamped volitional eye or muscle signal | Consumer sleep-stage estimate alone |

Codes E0–E4 are **subjective self-reports**, not EEG verification.

## Confounding and biases

- **Dream recall selection:** better recall may increase both cue reports and lucidity reports.
- **Expectancy and demand:** knowing the protocol can increase reported successes without causing the target transition.
- **Practice carryover:** rehearsal cannot be fully erased during follow-up.
- **Sleep timing, stress, substances, illness, medication, and overnight glucose disruptions** influence sleep and recall.
- **Retrospective reclassification:** record immediately, retain original version, and do not edit an E2 into an E3 later.

## Analysis plan

Use descriptive counts, rates, and a timeline first. For baseline/training comparison, report absolute percentage-point differences alongside numerators and denominators. With few events, confidence intervals will be broad. Do **not** infer efficacy from one compelling report.

Analyse the two outcomes separately: **whether Wi-Fi was remembered** and **whether lucidity occurred**. A training effect on cue incorporation without lucidity is a meaningful negative result for LCP.

Keep [N1 Capture](RUNBOOK-N1-CAPTURE.md) as a distinct daytime protocol with a different endpoint; exclude it from overnight lucid-night numerators.

## Stopping, boundaries, and consent

The operator can stop any day. Never interrupt essential sleep, silence glucose or other medical alarms, adjust insulin or psychoactive medication, use drugs for induction, or force night awakenings. Stop if nightmares, derealization, insomnia, fatigue, or anxious reality-checking increase. Sleep and daily functioning take precedence.

No other person's personal dream narratives should be published without their informed permission; consent can be withdrawn for future releases but not guaranteed to erase existing forks.

## Planned artifacts

- [DATA-DICTIONARY.md](DATA-DICTIONARY.md) — field-by-field log definitions.
- [OBSERVATIONS.csv](OBSERVATIONS.csv) — **header-only** local data entry template (no fabricated outcomes).
- [MEASUREMENT.md](MEASUREMENT.md) — coding, uncertainty, and interpretation.
- [REPLICATION.md](REPLICATION.md) — replication and independent validation.
- [EVIDENCE.md](EVIDENCE.md) — study claims and evidence levels.

Study status: **no D-VISTA outcome data are claimed by this document**.
