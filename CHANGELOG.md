# Changelog

## v0.1.0 (2026-10-03)

First public release.

- `critic` sub-agent for Claude Code, with its own context.
- `adversarial-review` skill with inline fallback for tools without sub-agents.
- Core checks: unsourced claim, generic messaging, contradicts a learned rule,
  honest classification, missing evidence, audience mismatch.
- Packs: voice, clearance, confidentiality walls, report style, decision memo.
- Config templates: voice, clearance registry, learned rules.
- `critic-changelog.md` with format and one synthetic entry.
- Docs: why adversarial, tuning the critic, optional slop scrub.
- Worked example on synthetic data: weak cold email, review, rewrite, second
  pass.
- Project instructions for Claude.ai and ChatGPT Projects; `AGENTS.md` for
  other agents.
