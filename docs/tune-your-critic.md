# Tune your critic

The critic is the part of the system you should change most often. A gate that
never changes is either perfect or ignored.

## The rule

When the critic misses, fix the critic, not the output.

If you reject something the critic passed, the critic was wrong. Before you
touch the draft:

1. Find the line it should have caught. Quote it.
2. Decide why it missed:
   - **No check covered it.** Add a check to `checks/core.md` or the right
     pack. Give it a name, a test you can apply by reading, and a severity.
   - **A check existed but was too narrow.** Widen the wording. Add the case
     as an example under the check.
   - **The config was empty or stale.** Fill `config/voice.md`,
     `config/clearance-registry.md` or `config/learned-rules.md`.
3. Make the change.
4. Re-run the critic on the same draft. It should now fail it. If it does not,
   your change is not specific enough. Go again.
5. Log the entry in `critic-changelog.md`.
6. Now fix the draft.

The order matters. If you fix the draft first, you feel done, and the critic
never learns.

## When the critic over-flags

It will. A check written too broadly fails good drafts. Signs:

- You keep shipping past the same finding on purpose.
- Findings quote lines that are fine, with reasons that are technically true
  and practically silly.

Treat that as a miss too. Narrow the check, add a "not a hit" example, and log
it. Loosening a check is as legitimate as tightening one, as long as it is
written down.

## Adding a pack

A pack is a markdown file in `checks/packs/` with:

- a short note on which artefacts it applies to;
- numbered checks, each with a name, a test, and a severity;
- a verdict rule if the pack needs one (for example, "missing stance is always
  escalate").

Add a row for it in the "Which packs run" table in `checks/core.md`.

## Keep it readable

If a check needs a paragraph to explain, split it. The critic is a model; it
follows short, testable rules better than nuanced essays. So do the humans who
have to trust it.
