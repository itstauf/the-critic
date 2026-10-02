# Core checks

These run on every artefact, whatever its type. Each has a name (use it as the
`category` in findings) and a severity.

## Which packs run

| Artefact type | Core | voice | clearance | confidentiality-walls | report-style | decision-memo |
|---|---|---|---|---|---|---|
| email | yes | yes | yes | if walls configured | no | no |
| post | yes | yes | yes | if walls configured | no | no |
| proposal | yes | yes | yes | if walls configured | optional | no |
| report | yes | yes | yes | if walls configured | yes | no |
| decision-memo | yes | yes | if it leaves the team | if walls configured | no | yes |
| other | yes | yes | if it names anyone outside | if walls configured | no | no |

Change this table to fit your work. It is a config, not a law.

## 1. Unsourced claim

Any number, statistic, quote, name, result or claim about a customer, market or
method that has no source the critic can open. A source is a file in the
project (raw notes, a transcript, a dataset) or a named public citation.

- Assume a claim was invented until a source proves it was not.
- **Hard fail** on any unsourced number, quote, or named result.
- **Hard fail** if there are 3 or more unsourced softer claims ("most teams
  struggle with...") in one artefact. Under 3: soft flag each.

## 2. Generic messaging

A line, or a whole draft, that any competitor could have sent unchanged. Test:
swap your name for a rival's. If nothing breaks, it is generic.

- **Hard fail** for outreach, posts and proposals.
- Soft flag for internal documents.
- The fix is always a specific anchor: a scene, a number with a source, a named
  method, something only you saw.

## 3. Contradicts a learned rule

The draft breaks a rule the system already learned and wrote down (by default
`config/learned-rules.md`, or wherever your project keeps confirmed rules).

- **Hard fail.** If the rule now looks wrong, the answer is to challenge the
  rule in its own file, not to ship past it. Use `escalate`.

## 4. Honest classification

The draft calls something by a stronger name than it has earned:

- a guess presented as a fact;
- a draft presented as a decision;
- a projection presented as a result;
- a single case presented as a pattern;
- a tool fix offered for a problem the draft itself diagnoses as people or
  process.

**Hard fail.** Fix: relabel it ("our estimate", "proposed", "in one case") or
add the evidence.

## 5. Missing evidence for numbers, quotes and names

Narrower than check 1 and stricter. Every number, every quotation mark and every
proper noun of a person or company is checked against a source on its own.

- **Hard fail** on any quote with no speaker and source.
- **Hard fail** on any named person or company with no reason to be there.
- A number with a source but no date: soft flag.

## 6. Audience mismatch

The draft is written for someone other than its reader: jargon the reader does
not use, a length the channel does not allow, an ask the reader cannot say yes
to, a tone that fits a different relationship.

- Soft flag each. **Hard fail** if the main ask is one the reader cannot act on.

## Severity summary

| # | Check | Severity |
|---|---|---|
| 1 | Unsourced claim | Hard fail on numbers, quotes, named results; hard fail at 3+ softer claims |
| 2 | Generic messaging | Hard fail on external outreach, posts, proposals |
| 3 | Contradicts a learned rule | Hard fail |
| 4 | Honest classification | Hard fail |
| 5 | Missing evidence | Hard fail on unsourced quote or unexplained name |
| 6 | Audience mismatch | Soft flag; hard fail if the ask is not actionable |

Add your own checks below this line. Give each a name, a test, and a severity.
Log every addition in `critic-changelog.md`.
