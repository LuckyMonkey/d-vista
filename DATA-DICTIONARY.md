# Data Dictionary — D-VISTA DV-001

One record **per night** in [OBSERVATIONS.csv](OBSERVATIONS.csv). Preserve blank fields when the operator is unsure. Do not turn missing entries into zeros or retrospectively fill in “success.”

## Schema

| Column | Type | Allowed values / coding instructions |
| --- | --- | --- |
| `study_id` | string | `DV-001` for first protocol. |
| `session_date` | ISO date | Local calendar date at **bedtime** (`YYYY-MM-DD`); one unique row per study and bedtime date. |
| `phase` | category | `baseline`, `training`, `followup`, `other`. |
| `protocol_version` | string | e.g. `0.2.0`; use actual version or `unknown`. |
| `rehearsal_completed` | boolean/unknown | `yes`, `no`, `partial`, `unknown`. |
| `rehearsal_minutes` | nonnegative number/blank | Estimate, not a stopwatch requirement. |
| `anchor_used` | category | `wrt54gs`, `other`, `imagined`, `none`, `unknown`. |
| `sleep_hours_estimate` | numeric/blank | Approximate duration; leave blank if unknown. |
| `sleep_quality_1_5` | integer/blank | 1 very poor, 2 poor, 3 fair, 4 good, 5 excellent. |
| `sleep_disruption` | category | `none`, `minor`, `major`, `unknown`; safety takes priority. |
| `dreams_recalled` | integer/blank | 0 if **no recall**; blank when not assessed; do not equate with total dreams experienced. |
| `wifi_cue` | category | `yes`, `no`, `uncertain`, `not_assessable`; “no” only with adequate dream recall. |
| `wifi_representation` | category | `implicit`, `dialogue`, `symbol`, `device`, `ssid`, `mixed`, `none`, `unknown`. |
| `reality_check_in_dream` | category | `yes`, `no`, `uncertain`, `not_assessable`. |
| `lucidity` | category | `yes`, `no`, `uncertain`, `not_assessable`. Explicit awareness that one is dreaming must occur **during** the experience. |
| `trigger_sequence` | category | `wifi_before_lucidity`, `other_trigger`, `undetermined`, `not_applicable`. |
| `planned_action_attempted` | category | `yes`, `no`, `uncertain`, `not_applicable`. |
| `confidence_1_5` | integer/blank | Confidence in the dream report, not confidence the mechanism is real. |
| `outcome_code` | category | `E0`–`E4`; highest well-supported subjective outcome for the night. |
| `recorded_within_minutes` | nonnegative number/blank | Estimated delay after final waking. |
| `adverse_effect` | category | `none`, `sleep_loss`, `nightmare`, `anxiety`, `disorientation`, `other`, `unknown`. |
| `notes_file` | relative filename / blank | Optional detailed report, e.g. `my-private-journal.md`; do not commit sensitive journals by default. |

## Missing-data conventions

- **Blank:** not recorded or unknown, no imputation.
- **No:** observed or confidently recalled negative in a relevant context.
- **Not assessable:** the question could not have been answered (e.g., Wi-Fi absence on a night with no dream recall).
- **Uncertain:** memory is ambiguous. Do not promote to yes on the basis of later reflection.
- **Zero dreams recalled:** means zero *remembered* dreams. It does not establish that dreaming did not happen.
- **E3:** record only if the operator specifically remembers recognizing “this is a dream” **during sleep**; confirm whether the recognition preceded or followed the Wi-Fi cue.
- **E4:** actual attempted action following E3, independent of apparent success of the action.

## Data integrity

1. Date and timestamp reports promptly after waking; use local time zone in detailed notes.
2. Preserve the original report verbatim. Add interpretation under a separate heading.
3. Use consistent definitions across baseline, training, and follow-up.
4. Log adverse outcomes, failed nights, and unremarkable nights.
5. Do not store medication doses, identifiable clinical details, exact location, or personal secrets in a public repository.
6. Use anonymized aggregate summaries for public sharing, with explicit permission.
7. No results exist in the template at publication. For an illustrative record, see [SESSION-LOG-EXAMPLE.md](SESSION-LOG-EXAMPLE.md); examples are not data.

See [MEASUREMENT.md](MEASUREMENT.md) for outcome coding and [STUDY.md](STUDY.md) for denominators.
