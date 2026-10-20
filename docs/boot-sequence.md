# Boot Sequence

This document traces D-VISTA from source repository to interactive session. Each
stage is given twice: as **documented fiction** (how the system describes
itself) and as **actual cognitive action** (what the operator is really doing).
The second column is the true one.

## 1. Stages

```text
  [ GitHub / any copy ]        WAKING HOST              DOWNTIME
  +-------------------+      +--------------+      +------------------+
  | Markdown, no      |----->| read, encode |      | dream assumes    |
  | executable        | read | rule + anchor|      | "Wi-Fi is here"  |
  +-------------------+      +------+-------+      +--------+---------+
                                    |                       |
          real file transfer        |  memory only          | rule recalled?
          (awake, optional)         +---------------------->|
                                      no packets            v
                                                     check -> LUCID
                                                            |
                                                      wake  v
                                                     recall / log
```

| Stage | Documented fiction | Actual cognitive action |
| --- | --- | --- |
| Acquire | Source is cloned from the repository. | You download or open some text files, awake, with a normal computer. |
| Install | The README writes a dormant module into prospective memory. | You read an instruction and choose to remember it. |
| Configure | The WRT54GS binds the module to the dWLAN interface. | You handle an object so the rule has a concrete memory attached. |
| Verify | Installation reports `DORMANT`. | One honest reality check while awake returns "awake". |
| Boot | Host enters scheduled downtime; runtime becomes available. | You fall asleep. Dreams happen, mostly later in the night. |
| Discover | dWLAN advertises connectivity. | A dream includes the knowledge that Wi-Fi is available. |
| Authenticate | LCP challenges the operator: "Am I dreaming?" | The cue brings back the rule and you genuinely check. |
| Session | Interactive session granted. | You recognize that you are dreaming. |
| Disconnect | `CONNECTION_RESET_BY_PEER`. | You wake up. |
| Log | Session written to the log sink. | You write down what you remember. |

## 2. Two kinds of download

**Literal clone.** Real files are copied to a real device, while you are awake,
over a real network. This is ordinary Git and has nothing to do with sleep.

**Dream-state pull.** A dream may show you fetching the repository, reading
its README on a screen, watching a progress bar reach 100%. None of this is
network activity. All GitHub downloads occur before execution; runtime
downloads are reconstructed from memory.

## 3. Deferred Semantic Reconstruction (DSR)

*DSR is an invented in-project term.* It is not a neuroscience finding and does
not appear in the research literature.

In this project, DSR names a familiar thing: dreams draw on recent waking
experience, and something you read and rehearsed before bed may reappear in a
dream, usually altered. If D-VISTA appears in a dream, as text, as a terminal,
as a feeling that "the protocol is running", that is DSR: your memory
rebuilding pieces of a document you already read. It is not retrieval from
anywhere outside you.

DSR is usually lossy. The dream may keep the router and lose the rule, which is
why the rule is rehearsed more than the router. See `STALE_CACHE` in
[incident response](../runbooks/incident-response.md#stale_cache-warn).

## 4. In-universe errors

```text
ERR_HOST_ACTIVE
  The service was started while the host was awake. D-VISTA cannot run on the
  machine where its source is being read. Expected during installation.
  Action: enter scheduled downtime.

CONNECTION_RESET_BY_PEER
  The operator woke. The session is closed and cannot be resumed.
  Action: log immediately; the cache expires within minutes.
```

WARNING: attempts to inspect the service from the waking host terminate the
session. In practice: checking whether you're falling asleep keeps you awake,
and excitement during a lucid dream tends to wake you.

## 5. What the boot sequence does not do

- It does not run unless you deliberately rehearse the rule.
- It does not send anything anywhere, during sleep or otherwise.
- It does not guarantee a dream, a cue, or a session. Successful boot does not
  imply interactive authentication.

The out-of-universe account is in
[implementation-notes.md](implementation-notes.md).
