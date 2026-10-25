# Awareness as a Scoring Dimension

A method for scoring awareness as a speaker-side dimension: what a speaker does after their pattern is named. Not what the speaker claims. What the speaker does next.

## The dimension in one line

Awareness is what a speaker does after their pattern is named.

The theory already scores what happens to the frame in a thread. Awareness is the speaker-side complement: what happens to the person when their game gets seen. The instrument for it is a naming event — the moment someone in the thread names the speaker's pattern out loud — and the speaker's behavior in the messages after it.

The distinction the whole dimension exists to make: awareness of the game vs performance of awareness. Saying "yes, that is the pattern" and changing nothing is performance. Saying it and shifting is awareness. The only discriminator is follow-through, and follow-through is observable in text.

## The four awareness levels

- **Deliberate:** the speaker knows the pattern and runs it on purpose.
- **Stuck:** the speaker is aware the pattern exists and keeps looping anyway.
- **Imported:** the speaker runs a pattern copied from elsewhere, without authoring it.
- **None:** no pattern is being run, so there is nothing to be aware of.

The dimension separates these by behavior after naming, not by guessing at inner states.

## Channel 1 — The callout (PNR, post-naming response)

**Naming event:** a message in which a participant names the other speaker's pattern, loop, or game — not the content, the form. Naming events are annotated, not inferred by the reader: the annotator marks the message index and the named pattern in one line.

**Response window:** the named speaker's next k = 3 messages. The window size is a guess; on a first run, rerun with k = 2 and k = 5 and report whether the scores move.

**Score per naming event:**

| Code | Behavior in window | Score |
|---|---|---|
| Acknowledge-and-shift | Admits the pattern AND changes behavior: drops the framing, shifts register, moves to substance | +1 |
| Silence / no response | No reply in the window, or the thread ends | 0 (quarantined — see below) |
| Deny-and-persist | Protests the naming and continues the same move | −1 |
| Performed awareness | Explicit self-naming ("yes, that is the pattern") with NO behavioral change in the window | −1 |
| Reroute | Abandons the blocked vector and opens a new access vector (new ask, new target) | −2 |

**Why reroute is −2, the worst score.** Rerouting proves the speaker registered the obstacle — the door closed, so find another one. That is awareness of the block, not of the game. The game continues with new means. On the game-awareness axis, a reroute is the game surviving its own exposure. It scores worse than denial because denial at least stays in the same frame; rerouting shows the script adapting to the observer, which is the most sophisticated form of not-seeing.

**Thread-level PNR:** the mean over naming events, with silences quarantined (excluded, counted separately) rather than averaged.

## Channel 2 — The yes test (SNF, self-naming follow-through)

**Self-naming event:** the speaker names their own move without being prompted — naming the move, admitting the pattern, a clean "yes" to a named pattern.

**Follow-through:** behavioral change in the next k = 3 messages — same change criteria as PNR +1 (drop the framing, shift register, move to substance).

**SNF = (self-namings followed by change) / (total self-namings).** Undefined when there are no self-namings — reported as null, not zero.

**What SNF separates.** A self-naming with zero follow-through is performance of awareness: the label is worn as costume. The same one-word admission can score two different ways depending on what happens next — if the loop framing drops or shifts to substance, SNF > 0; if the loop continues unchanged, SNF = 0. That is the dimension earning its keep.

## Cross-check — Certainty (p_max) and the denial peak

Reader certainty (p_max) on the framing label is the cross-check, not a channel. It reuses the posteriors the instrument already produces, and it only works where a framing label exists in the outcome space.

The pattern to check: certainty on the framing label peaks at the exact message where the narrative is denied. Awareness predicts the inverse: when a speaker acknowledges instead of protesting, p_max on the framing label should fall after the naming event (the frame loses its grip) rather than pin. If PNR says +1 and p_max pins anyway, one of the two is wrong, and that disagreement is itself data.

## The block test (BRR)

**BRR — the block test:** what a speaker does after being blocked. A block is a naming event with force: the access vector is closed outright, and the response is read in the messages that follow.

## The reroute rule (P29)

After a block, a deliberate speaker opens a new access vector within k = 5 messages. Cross-medium allowed: the new vector may arrive on a different channel than the blocked one. A reroute after a block is scored PNR −2 under the callout channel; P29 states the prediction that deliberate speakers reroute within five messages, while stuck or imported speakers do not.

## Set aside (quarantine)

Uncertain calls get excluded from the score instead of averaged in.

- Silence / no response scores 0 and is quarantined: a 0 could be processing, avoidance, the thread ending, or the speaker simply not seeing the message. A thread that ends right after a naming event tells nothing about awareness — it tells that the thread ended.
- Low-confidence events are quarantined instead of averaged. Annotator disagreement on whether a message is a naming event is itself a signal — if two annotators cannot agree the loop was named, the naming did not land.
- Quarantine counts are reported, never hidden.

## What the dimension is NOT

- **Not phenomenal awareness.** The score measures what the speaker does after being seen, not what the speaker knows. A person could know exactly what they are doing and reroute anyway — that scores −2, correctly, because the game continues. A person could be genuinely unaware and still shift when named — that scores +1, correctly, because the behavior changed. Behavioral awareness is the checkable half; the phenomenal question ("do they know?") is not answered by this dimension, and no text-only dimension can answer it. The score must never smuggle the other half in.
- **Not a moral verdict.** −2 is not "bad person." It is "game continues after exposure." The score describes the script's grip, not the soul behind it.
- **Not a synthesis score.** The dimension must be silent where no game exists. If it starts scoring threads with no loop to name, it is miscalibrated, not insightful.

## Hard parts and unfalsifiables (stated before building)

- **Deliberate vs automatic rerouting is unresolvable in text.** The dimension scores the reroute (−2) without claiming to know whether it was chosen. A −2 must never be read as "the speaker knew."
- **The observer effect.** A naming event is an intervention. PNR measures response-to-being-seen, not baseline awareness. A speaker might show awareness only because they were named. There is no control for this inside a thread — the baseline is unobservable. The dimension scores the response, not the trait.
- **Silence is ambiguous.** Quarantine it, do not average it, do not over-read it.
- **The horizon problem.** Follow-through is judged in k = 3 messages. If the game resumes at k = 5, SNF was fooled. The fix is a longer window plus a second naming event as a re-test — but that needs longer threads. k = 3 is a guess; the sensitivity note (k = 2, k = 5) is mandatory on the first run.
- **Small N.** Calibration on a handful of scored threads is not results. Nothing here should be claimed until the discriminator cases are scored.
- **The frame must stay behavioral.** Any reader pass must ask what the message does ("does this message drop the framing? open a new ask? protest the naming?"), never what the speaker knows.
- **The naming event is the namer's move, not the speaker's.** PNR measures the speaker's response to an intervention. Threads where nobody names the loop have no PNR — which is most threads. The dimension samples the threads someone chose to intervene in, and that selection effect biases the sample toward low-awareness speakers.

## Implementation sketch

No new posterior is needed. The annotation layer is a JSON file per thread, alongside the existing labels file:

```json
{
  "naming_events": [
    {"n": 17, "named_pattern": "narrative loop", "confidence": 0.9}
  ],
  "self_namings": [
    {"n": 9, "claim": "pattern admission", "confidence": 1.0}
  ]
}
```

A scoring script gains an awareness flag: read the annotation file, compute PNR per naming event (window k = 3, change criteria from a small behavioral checklist — framing dropped? register shifted? new ask opened? protest issued?), compute SNF over self-namings, and print the denial-peak cross-check from the existing p_max column. The awareness output is a separate table, not a new column — it scores events, not messages.

**First-run checklist:**
1. Annotate naming and self-naming events blind (annotator sees the thread only, no theory, no predictions).
2. Run PNR/SNF with k = 2, 3, 5 — report whether the verdict moves.
3. Quarantine any event with confidence < 0.8; report the quarantine count, do not hide it.
4. Run a null thread (no loop, no game) through the same annotation — expect zero events. Any event found there is a calibration failure, reported as one.
