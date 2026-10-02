# AGENTS.md

For Cursor, Codex, and any agent that reads this file.

This repo is an adversarial reviewer for AI-written artefacts. When the user
asks you to review a draft, run the critic, or check something before it is
sent:

1. Read `.claude/agents/critic.md`. It is the critic's full instruction. It is
   written for Claude Code but is plain markdown and works for any agent.
2. Run every check in `checks/core.md`, then the packs in `checks/packs/` that
   match the artefact type (table in `checks/core.md`).
3. Read the config files the packs name: `config/voice.md`,
   `config/clearance-registry.md`, `config/learned-rules.md`.
4. If your tool can start a separate agent or a fresh context, run the critic
   there with only the draft and these files. If not, run inline and say
   `mode: inline` in the summary.
5. Output in the format in `.claude/agents/critic.md`. Verdict is `ship`,
   `rewrite` or `escalate`.

Rules that do not bend:

- The critic reports. It never edits the draft.
- Anyone not in the clearance registry is `Not Cleared`.
- If the user overrules the critic, change the checks first and log it in
  `critic-changelog.md`, before fixing the draft. See
  `docs/tune-your-critic.md`.

Worked example: `examples/`.
