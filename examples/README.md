# Example: a cold email, before and after the critic

Everything here is synthetic. Halden & Co, Juno Freight, Larch Atelier and
every person named are made up.

The setup: Mira Okafor runs Halden & Co, a small operations consultancy. She
asks her AI to draft a first-touch email to Tomas Reyes, Head of Operations at
Juno Freight. The project has a filled `config/voice.md`, the example
`config/clearance-registry.md` (Larch Atelier is `Anonymised`, Juno Freight is
`Not Cleared`) and the example `config/learned-rules.md`.

| File | What it is |
|---|---|
| `01-draft.md` | The first draft, exactly as the drafter produced it. Line numbers in the review refer to this file. |
| `02-critic-review.md` | The critic's full output, run as a sub-agent in its own context. |
| `03-rewrite.md` | The drafter's rewrite, made from the findings only. |
| `04-second-pass.md` | A fresh critic run on the rewrite. Verdict: ship. |
| `sources/juno-job-ad.md` | The source the rewrite cites. |

What to notice:

- The critic quotes the exact line every time, so the drafter cannot argue
  about what was meant.
- It never rewrites the email itself.
- The second pass still raises a soft flag. `ship` does not mean perfect. It
  means no hard fail.
