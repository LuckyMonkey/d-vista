# Sample Session Log

> **Illustrative example.** This log is fabricated to show the format. It does
> not describe a real night or a real result. No field data exists yet.

Lines are tagged by I/O class:

- `[real]`: something that physically happened in the bedroom.
- `[dream]`: something experienced in the dream. Imagined I/O. Not a fact
  about the world.
- `[note]`: written on waking.

```text
dDNS session log  v0.1.0
operator:   example
anchor:     WRT54GS, unpowered
date:       (example)

22:41 [real]  STATE AWAKE
22:41 [real]  anchor handled. two antennas, five lights, none lit (unpowered).
              "This means I have Wi-Fi."
22:43 [real]  response rehearsed x5. each check returned: awake.
22:46 [real]  scenarios A, B, C rehearsed. C: a field. no devices. knew there was Wi-Fi.
22:48 [real]  lay down. intention set twice. stopped rehearsing.
22:48 [real]  STATE SLEEP_ONSET
      [ -- ]  transition to DREAMING not observed (by design)

~04:30 [dream] STATE DREAMING
       [dream] location: "my old school", resolved to an airport terminal.
               split-horizon. no complaint filed.
       [dream] someone at a gate says the Wi-Fi is free here.
       [dream] cue: wifi.available = true. no router seen.
       [dream] STATE CHECKING
       [dream] "Am I dreaming?"
       [dream] continuity: cannot recall arriving. plausibility: school is an
               airport. stability: departure board text changes on second look.
       [dream] STATE LUCID
       [dream] stood still. looked at the carpet. carpet stable. calmed down.
       [dream] payload: found a laptop at the gate. typed:
                   $ ssh fridge
               dreamed response: "Welcome to fridge. Your milk expires in 3 hours."
               (imagined output. no connection made. no host contacted.
                fridge did not log a login, because none occurred.)
       [dream] board flickered. scene faded.

~04:34 [real]  STATE RECALL
       [real]  woke. lay still. replayed.
04:36  [note]  "airport = school. free wifi. asked. board text moved. lucid.
               laptop. ssh fridge. milk."
04:36  [note]  Wi-Fi appeared: Y. knew I was dreaming: Y. action attempted: Y.
04:36  [note]  score: 4
04:36  [note]  uncertain: how long lucid. maybe 20 s, maybe less.
04:37  [real]  STATE LOGGED. returned to sleep.

07:10 [real]  woke for the day. one calm check: room stable. awake. accepted.
07:12 [real]  verified: fridge has no record of an ssh login at 04:3x.
              expected. dream I/O does not reach real hosts.
```

## Notes on the example

- The cue arrived as **dialogue** ("the Wi-Fi is free here"), not as a router or
  an icon. This is the low-fidelity discovery described in
  [RFC 0003](../rfc/0003-conceptual-wlan-discovery.md).
- The check examined the **situation** (continuity, plausibility, text
  stability), as specified in
  [RFC 0004](../rfc/0004-lucidity-handshake.md).
- The dreamed terminal output is clearly separated from real I/O. The milk
  warning is not actionable.
- The 07:12 check is optional, and included only to make the point. There is no
  need to audit real servers after a dream.
- A realistic first week is likely to look more like the second entry in
  [sample-dream-journal.md](sample-dream-journal.md).
