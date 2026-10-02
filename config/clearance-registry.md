# Clearance registry

**Default for anyone not listed: `Not Cleared`.**

Every status needs a source: who gave it, when, and where that is recorded (an
email thread, a signed form, a call note). A row without a source is read as
`Not Cleared`.

## Statuses

| Status | Meaning | Rule |
|---|---|---|
| `Cleared` | Explicitly cleared for public reference | Free to cite |
| `Pending` | Asked, not yet answered | Do not publish |
| `Not Cleared` | Default. Not asked, or asked and declined | Do not publish |
| `Sensitive` | Cleared with specific conditions | Use only as the conditions allow |
| `Anonymised` | Cleared only if not named or identifiable | Use without the name |

## Clients

| Name | Status | Conditions | Date set | Source |
|---|---|---|---|---|
| (example) Juno Freight | Not Cleared | Not asked | 2026-10-03 | Default |
| (example) Larch Atelier | Anonymised | No name, no city, no headcount | 2026-09-20 | Signed release form, file `raw/clearance/larch-release.md` |
| (example) Pinecrest Tools | Cleared | None | 2026-09-12 | Reply from their founder, saved at `raw/clearance/pinecrest.md` |

## Prospects

| Name | Status | Notes | Source |
|---|---|---|---|
| (any prospect) | Not Cleared | Default | Default |

## Changing a status

Only the human owner changes a status, and only with a source. Write the date.
Never upgrade a status because a draft needs it.
