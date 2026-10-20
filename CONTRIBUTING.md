# Contributing to dDNS

dDNS accepts contributions in three categories: new cues and dream signs, bug
reports against the protocol, and corrections to the documentation. Patches to
the operator are out of scope.

## Ground rules

1. **Label your evidence.** Every claim belongs to one of three classes:
   - `anecdote`: something that happened to you or someone you know;
   - `research`: a published, checkable source, cited so another person can find
     it;
   - `design`: a reasoned argument with no data behind it yet.

   Most of this repository is `design`. That is acceptable as long as it says so.
2. **No medical claims.** Do not suggest that dDNS treats insomnia, nightmares,
   anxiety or anything else. Do not suggest supplements, drugs, medication
   changes, sleep restriction, or silencing medical alarms. Pull requests that
   do will be closed.
3. **No literal transmission.** Contributions must not describe dreams as
   receiving signals, packets or data from real networks or other people. The
   networking is an analogy. RFC 0001 says so, normatively.
4. **Humor is welcome; accuracy is mandatory.** A joke that makes a false claim
   about sleep science or networking is a bug. A joke that is technically
   correct is a feature.

## Submitting a new cue or dream sign

Open an issue titled `CUE: <short name>` containing:

- **Record:** the semantic fact the cue asserts (for example, "I have signal",
  "the lights are on").
- **Fidelity required:** how much the dream must render for the cue to be
  present. Lower is better; see [RFC 0003](rfc/0003-conceptual-wlan-discovery.md).
- **Waking frequency:** how often the fact is true in waking life. A cue that is
  always true while awake is a good rehearsal trigger and a poor proof; that is
  fine, because no cue is proof. See [RFC 0004](rfc/0004-lucidity-handshake.md).
- **Anchor:** the physical object used to rehearse it, if any.
- **Evidence class:** `anecdote`, `research` or `design`.

## Reporting a bug

Open an issue titled `BUG: <status code or symptom>`. Use the codes in
[runbooks/incident-response.md](runbooks/incident-response.md) where one fits.
Include:

- what you did before sleep (briefly);
- what you recalled, using the 0–4 score from
  [runbooks/tonight.md](runbooks/tonight.md);
- whether the Wi-Fi cue appeared, and separately whether you recognized you were
  dreaming;
- anything that made sleep worse.

Do not include identifying details about other people who appeared in your
dreams. Their consent was not obtained at layer 7.

## Documentation changes

- Keep the RFC voice: dry, precise, one joke per section at most.
- Keep relative links working. From the repository root, this lists any broken
  internal link:

  ```sh
  grep -rhoE '\]\([^)#]+' --include='*.md' . | sort -u
  ```

  then check each target exists relative to the file that links it.
- No emoji, badges, screenshots or invented statistics.
- Markdown only. Do not add a package manager, build step or runtime.
