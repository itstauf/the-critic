## Critic review (second pass)

date: 2026-10-03 · mode: sub-agent (fresh context) · draft: `examples/03-rewrite.md` · type: email

Sources checked: `examples/sources/juno-job-ad.md` supports the quote on line 5 and the description of the handover. No client, partner or prospect is named other than the recipient, so the clearance pack has nothing to block. About 100 words, under the 150 in `config/learned-rules.md`.

- [line 6 | unsourced claim] "Handovers like that are where I usually start." : soft flag. "usually" is a soft claim about her own practice with no source; one such claim is under the hard-fail threshold : fine to keep if true; cut "usually" if she has only done this once
- [line 11 | audience mismatch] "If it is useful, I can send the one-page checklist we use to map a single handover." : soft flag. The checklist must exist before this is sent : confirm the file exists and is ready to attach

```
hard_fails: 0
soft_flags: 2
packs_run: core, voice, clearance
missing_inputs: none
verdict: ship
reason: no hard fail; the quote is sourced, the ask is one a single reader can accept, nothing banned remains
```

The critic does not send it. Mira reads the two soft flags, confirms the checklist exists, and sends it herself.
