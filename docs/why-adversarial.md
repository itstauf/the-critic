# Why an adversarial critic

## The fear

When I show a room what my AI setup does, the first worry is rarely "will it be
clever enough". It is "will it confidently send rubbish with my name on it".
That fear is right. A model that drafts well will also invent a number, name a
client who never agreed to it, and sound sure about both.

So nothing leaves my system without a second reader whose one instruction is
not to be nice.

## Why not ask the drafter to check its own work

Ask a writer "is this good?" straight after they wrote it and they will mostly
say yes. They know what they meant, so they read what they meant. A model is
the same. Self-grading in the same conversation inherits every assumption that
produced the draft.

The fix is a different reader with a different job:

- **A different prompt.** The critic is told to find reasons the artefact will
  fail. It is not asked whether the draft is good.
- **A different context.** In Claude Code the critic runs as a sub-agent with
  its own context window. It sees the draft file and the rule files. It does
  not see the drafting conversation, the half-sourced notes, or the reasoning
  that talked the drafter into a claim.

This pattern comes from Suchintan (Skyvern) in YC Root Access, video 03,
"context is all you need": a separate agent with a different prompt catches
more than the same agent asked to grade itself.

## Being honest about the limits

- **Same model, often.** The critic and the drafter may be the same underlying
  model. The separation is in prompt and context, not in a different brain.
  That still catches a lot, because most errors live in the context, not in the
  weights. It will not catch blind spots the model shares with itself.
- **Single-context tools.** In a chat tool with no sub-agents (a Claude.ai or
  ChatGPT Project, for example) the critic runs inline. That is a different
  hat, not a different mind. It is weaker. It is still far better than no gate,
  and the review says `mode: inline` so you know which one you got.
- **Rules in, rules out.** The critic can only enforce the checks and configs
  you wrote. An empty clearance registry means everything is `Not Cleared`,
  which is safe, but an empty banned-phrase list means nothing gets caught.

## Why it reports and never fixes

The critic never edits the draft. If it did, you would get a third version
nobody reviewed, written by the one reader whose job was to doubt. Keeping the
roles apart keeps each honest: the drafter writes, the critic reports, the
human decides.

## Why verdicts are only three

`ship`, `rewrite`, `escalate`. More grades invite argument about the grade.
Three verdicts force a decision about the next action: send it, fix it, or ask
the person who owns the risk.
