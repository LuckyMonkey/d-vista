# Sample Dream Journal

Copy the template below into a notebook, a text file, or a voice memo script.
Keep it short; the point is to capture the night before it expires.

## Template

```text
Date:
Bedtime routine:        full / 60-second / skipped
Natural awakening rehearsal:  Y / N   (approx. time: )
Sleep quality (self-report, 1-5):

Narrative (keywords first, sentences optional):


Wi-Fi cue appeared:             Y / N
  form (knowledge / dialogue / device / screen / other):
Explicit dream recognition:     Y / N
Task attempted:                 Y / N
Score (0-4):

Uncertainties:

Anything that made sleep worse:
```

Scoring, from [RUNBOOK-TONIGHT.md](RUNBOOK-TONIGHT.md):

| Score | Meaning |
| --- | --- |
| `0` | Nothing recalled |
| `1` | Dream recalled |
| `2` | Wi-Fi concept appeared |
| `3` | Wi-Fi led to recognition of dreaming |
| `4` | Lucid, and the intended action was attempted |

## Example entries

> **Illustrative.** These example entries are synthetic and not actual participant observations, written to show how to fill in
> the template. They are not results.

### Entry A: no lucidity

```text
Date:                     night 1 (example)
Bedtime routine:          full
Natural awakening rehearsal:  N
Sleep quality:            4

Narrative:
  grocery store, but it was also my parents' kitchen. looking for cereal.
  a cousin was there. long hallway. lost my shoes.
  later: helping someone set up a printer. it would not connect.

Wi-Fi cue appeared:       Y (sort of)
  form: printer "would not connect". no explicit Wi-Fi.
Explicit dream recognition:  N
Task attempted:           N
Score:                    1, arguably 2

Uncertainties:
  not sure "printer won't connect" counts as Wi-Fi. scoring 1 to be safe.
  did not think of the question at all.

Anything that made sleep worse:  no
```

Reading this entry: the dream produced something adjacent to connectivity, but
the intention never came back. Per
[incident-response.md](RUNBOOK-INCIDENT-RESPONSE.md#connection_refused-warn),
the next step is more rehearsal of the question, not more rehearsal of the
router. This is a normal, conformant night.

### Entry B: Wi-Fi without recognition

```text
Date:                     night 3 (example)
Bedtime routine:          60-second
Natural awakening rehearsal:  Y (~3 am)
Sleep quality:            3

Narrative:
  hotel. asked front desk for the Wi-Fi password. they gave me a very long one.
  I wrote it on my arm. it kept changing.

Wi-Fi cue appeared:       Y
  form: dialogue + text
Explicit dream recognition:  N
Task attempted:           N
Score:                    2

Uncertainties:
  the changing password is a textbook dream sign and I didn't notice.
  maybe I asked "am I dreaming" at some point? can't confirm. not counting it.

Anything that made sleep worse:  took a while to fall back asleep after 3 am.
                                 shorten the night rehearsal.
```

The cue arrived, and even an unstable-text anomaly was present, but no check
happened. That's `TOO_MANY_REDIRECTS` territory: incubation is working, and the
handshake isn't completing yet.
