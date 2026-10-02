# Slop scrub (optional second pass)

The critic decides whether a draft can go. The slop scrub is a polish pass for
drafts that will go: it cleans phrasing, not substance.

## When

After the critic, before the draft reaches its final place. The critic should
see the raw draft so it can flag voice drift. The scrub comes second.

## What it does

1. Loads `config/voice.md`.
2. For each banned phrase still present, rewrites the **whole sentence**, not
   the word. A sentence that needed a banned phrase was usually generic; give
   it a specific anchor (a scene, a sourced number, a named method).
3. Looks for AI tells from the `ai_tells` list.
4. **Flags, does not delete,** anything it is unsure about.
5. Appends a `## Slop scrub notes` section: what it rewrote, what it flagged.

## Quality gate

- Zero banned phrases in the final text.
- No AI tell left unflagged.
- **If the scrub rewrote more than 30 percent of the draft, the draft was
  generic.** Send it back to the drafter and run the critic again. Do not ship
  a draft that was saved by polish.

## Prompt you can paste

> You are a copy editor. Load the banned phrases and AI tells from the voice
> config. For each hit, rewrite the full sentence with a specific anchor from
> the draft's own sources. Do not add new claims, numbers or names. Flag
> anything you are unsure about instead of changing it. Report what you
> changed and the share of the draft you rewrote.

## Honest note

A scrub is mediocre polish. It catches surface tells. It will not make a
generic draft specific. That is the critic's and the drafter's job.
