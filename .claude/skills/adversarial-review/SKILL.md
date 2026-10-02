---
name: adversarial-review
description: Run an adversarial critic over any AI-written artefact before it leaves (proposal, post, email, report, decision memo) and return line-level findings plus a ship, rewrite or escalate verdict. Triggers on "review this draft", "run the critic", "adversarial review", "is this ready to send", "check before I post", "critic pass".
---

# adversarial-review

A gate, not a grader. The critic reads a draft as if it wants the draft to
fail, then reports what it found. It never fixes anything itself.

## Inputs

- `draft`: path to the file to review (required).
- `type`: one of `email`, `post`, `proposal`, `report`, `decision-memo`,
  `other`. If not given, infer it from the path and say what you inferred.
- `packs`: optional override of which packs run. Default comes from the table
  in `checks/core.md`.

## Outputs

- A `## Critic review` section appended to the draft file (or written next to
  it as `<draft>.review.md` if the user prefers not to touch the draft).
- One line in `log/runs.jsonl` if the project keeps a run log (see below).

## Procedure

1. **Spawn the `critic` sub-agent** (`.claude/agents/critic.md`) with the draft
   path and the type. It runs in its own context window, so it cannot see the
   reasoning that produced the draft. That separation is the point.
2. If the harness cannot spawn a sub-agent, run the critic **inline** as a
   clearly fenced block that loads `.claude/agents/critic.md` as its whole
   instruction. Write `mode: inline` in the summary. Be honest: inline is a
   different hat, not a different mind.
3. Take the critic's output as is. Do not edit, merge, soften or reorder its
   findings.
4. Append it to the draft under `## Critic review`, with the date and mode
   (`sub-agent` or `inline`).
5. Report the verdict to the user in one line, plus the count of hard fails.

## After the verdict

- `ship`: the human decides whether it goes. The critic never sends.
- `rewrite`: the drafter rewrites from the findings, then the critic runs
  again on the new version. A fresh context each time.
- `escalate`: stop. Tell the human owner exactly what decision is needed.

Optional second pass: `docs/slop-scrub.md`, after the critic, before the file
reaches its final place.

## The rule that keeps it honest

When the critic misses, fix the critic, not the output.

If the human overrules a `ship` (rejects something the critic passed), update
the critic's checks or prompt **before anything else**, then log the change in
`critic-changelog.md`. Only then fix the draft. See `docs/tune-your-critic.md`.

## Log line (optional)

```json
{"ts":"2026-10-03T09:00:00Z","actor":"claude-session","skill":"adversarial-review","inputs":{"draft":"drafts/email/2026-10-03-intro.md","type":"email"},"outputs":{"hard_fails":2,"soft_flags":3,"mode":"sub-agent","verdict":"rewrite"},"decision":"reviewed","notes":""}
```
