# Critic changelog

When the critic misses, fix the critic, not the output.

Every time the human owner overrules the critic, the critic changes first and
the change is logged here. Then, and only then, the draft gets fixed. Over
time this file is the record of how your critic learned your standards.

## Entry format

```
## YYYY-MM-DD: short name of the miss

- artefact: path to the draft
- critic verdict: ship | rewrite | escalate
- owner verdict: what the owner decided, in their words if possible
- the miss: what the critic should have caught, quoted from the draft
- why it missed: no check covered it | a check existed but was too narrow | config was empty | other
- change made (before anything else): file, and the exact text added or changed
- re-test: critic re-run on the same draft, with its new verdict
- then: what happened to the draft
```

Two rules for entries:

1. The "change made" line is written before the draft is touched. If you fix
   the draft first, the miss is forgotten by the next run.
2. If the owner overruled a `rewrite` (shipped something the critic failed),
   that is also an entry. Either the check was wrong and should loosen, or the
   owner took a risk on purpose and the entry says so.

---

## 2026-09-18: a single case passed off as a pattern (synthetic example)

- artefact: `drafts/post/2026-09-18-handover-checklists.md`
- critic verdict: ship (0 hard fails, 2 soft flags)
- owner verdict: rejected. "This says teams that map handovers onboard faster.
  We saw that once, at one client. It reads like a finding."
- the miss: line 4, "Teams that map their handovers first onboard new staff
  faster." The claim had a source (one project note), so check 1 passed it.
  Nothing checked whether one source could carry a general claim.
- why it missed: a check existed but was too narrow. Core check 4 (honest
  classification) covered guess vs fact and draft vs decision, but not one case
  vs pattern.
- change made (before anything else): `checks/core.md`, check 4, added the
  bullet "a single case presented as a pattern".
- re-test: critic re-run on the same draft. New finding:
  `- [line 4 | honest classification] "Teams that map their handovers first onboard new staff faster." : HARD FAIL. One source, written as a general rule : say "In one project, ..." or add the other cases`
  New verdict: rewrite.
- then: the drafter rewrote line 4 as "In one project, mapping the handovers
  first cut a new starter's first week in half." The source note was checked
  for the half. The critic passed it. The owner shipped it.
