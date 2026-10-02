# Pack: confidentiality walls

For people who run two or more contexts that must never leak into each other:
two client tracks, two businesses, a day job and a side practice, two clients
in the same industry.

## Configure your walls

Write them here. The shipped example uses two generic tracks.

| Track | What belongs to it | Never appears in |
|---|---|---|
| Track A | Clients, data, quotes and numbers from Track A work | Any Track B artefact |
| Track B | Clients, data, quotes and numbers from Track B work | Any Track A artefact |

Tell the critic which track the draft belongs to (by folder, front matter, or
in the request). If it cannot tell, that is itself a finding (`escalate`).

## W1. Wall leak

Any name, number, quote, project detail or recognisable situation from the
other side of a wall.

- **HARD FAIL.** Verdict `rewrite` if the line can be removed, `escalate` if
  the draft depends on it.

## W2. Unanonymised crossing

Learning is allowed to cross a wall only after it is stripped of everything
that identifies its origin, and only through a shared, general layer (your
method notes, not your client folders). A pattern that crosses with its origin
still visible ("as we saw with the Track A logistics client...") is a leak.

- **HARD FAIL.**

## W3. Ambiguous origin

A claim whose source the critic can only find on the other side of the wall.
Even if the wording is generic, the evidence is not usable here.

- **HARD FAIL** under check 1 (unsourced) for this track.
