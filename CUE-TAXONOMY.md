# dWLAN Cue Taxonomy

D-VISTA's discovery target is a **semantic capability**, not a specified object.

## Primary definition

**Wi-Fi awareness:** while experiencing a dream, the operator understands that wireless connectivity is available in the situation, independently of whether an access point is visible.

The reference anchor is the Linksys WRT54GS, used during waking rehearsal. A dream does not need to depict this device.

## Cue classes

| Code | Cue class | Example | Observation confidence considerations |
| --- | --- | --- | --- |
| C0 | None recalled | No wireless context in a recalled dream | Not applicable if the dream was not remembered |
| C1 | Implicit connectivity | The operator *knows* there is Wi-Fi without a screen or device | Strong if recalled explicitly, weak if inferred only after waking |
| C2 | Functional implication | Streaming or syncing, with explicit recognition that wireless access is involved | A streaming screen alone is not necessarily recognized Wi-Fi |
| C3 | Spoken reference | Someone says “the Wi-Fi works” or asks for the wireless password | Dialogue appears, but intention may not be retrieved |
| C4 | Iconic sign | A signal-bars symbol or a wireless menu | Could remain mere scenery if connectivity was not noticed |
| C5 | Access point | WRT54GS or another wireless device, with explicit connectivity awareness | The appearance of a router alone is an **anchor encounter**, not cue recognition |
| C6 | Textual identifier | SSID, terminal network status, DHCP information | Text fidelity and causal interpretation are uncertain |
| CX | Ambiguous | Fragment mentions networking without enough detail | Score “uncertain”; do not increase positive counts |

Multiple representations in a dream may be recorded under `mixed` in [DATA-DICTIONARY.md](DATA-DICTIONARY.md).

## Two separate triggers

**Waking anchor:** touching or observing a WRT54GS reinforces the intended association.

**Dream cue:** noticing that connectivity is available should retrieve the question *“Am I dreaming?”*

This separation permits generalization to dream locations without any electronics. The environment may assert facts without constructing perceptual details; whether that provides an actual advantage over other cues is **untested**.

## Detection versus lucidity

Sequence to record:

1. Representation or semantic awareness of Wi-Fi.
2. Retrieval of the bedtime intention.
3. Attention directed to the present situation.
4. Recognition of dreaming while the dream continues.

An operator may remember steps 1 and 4 but not whether 2 caused 4. The sequence is then **undetermined**. Do not retrospectively infer causation merely because two events were present.

## Failure signatures

- **Anchor lock-in:** router appears, no connectivity association.
- **Silent incorporation:** connectivity implicit but not consciously noticed.
- **Handler loss:** Wi-Fi noticed without remembering the rule.
- **False positive:** operator assumes Wi-Fi proves dreaming while demonstrably awake; the cue must prompt assessment, not dictate an answer.
- **Retrospective contamination:** an association appears only while reviewing dream notes after waking.

The best future comparison is with another similarly low-fidelity, ambient capability. This would test whether Wi-Fi is uniquely effective or whether rehearsal of **any** memorable prospective cue provides a similar benefit.

Related: [ARCHITECTURE.md](ARCHITECTURE.md), [RFC-0003-CONCEPTUAL-WLAN-DISCOVERY.md](RFC-0003-CONCEPTUAL-WLAN-DISCOVERY.md), [MEASUREMENT.md](MEASUREMENT.md).
