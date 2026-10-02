# Pack: clearance

Stops the critic from shipping anything that names a client, customer or
partner who has not said yes to being named. Reads
`config/clearance-registry.md`.

## C1. Named party without clearance

1. Find every reference to a client, customer, partner or prospect in the
   draft: names, logos described in text, unmistakable descriptions ("the
   largest freight firm in the region"), quotes attributed to them.
2. Look each one up in the registry.
3. Apply the status:

| Status | Meaning | What the critic does |
|---|---|---|
| `Cleared` | They said yes to public reference | Pass |
| `Pending` | Asked, no answer yet | **HARD FAIL** |
| `Not Cleared` | Default. Not asked, or asked and declined | **HARD FAIL** |
| `Sensitive` | Cleared with conditions | Pass only if every condition in the registry row is met; otherwise **HARD FAIL** |
| `Anonymised` | Cleared only without the name | Pass if unnamed and not identifiable; **HARD FAIL** if named or identifiable |

- **Anyone missing from the registry is `Not Cleared`.** No exceptions.
- A registry row with no source (who cleared it, when, where it is recorded) is
  treated as `Not Cleared`, and the critic adds a finding against the registry.

## C2. Identifiable without being named

An anonymised mention that still identifies the party (exact headcount, city
plus industry plus size, a unique event). **HARD FAIL** under `Anonymised`,
`Pending` and `Not Cleared`.

## Verdict rule

A clearance failure the drafter can fix by removing the name is `rewrite`. A
draft whose whole point needs the name (a case study, a testimonial) is
`escalate`: only the owner can go and ask for clearance.
