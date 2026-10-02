# Pack: voice

Checks the draft against how you actually write. The lists live in
`config/voice.md` so you can fill them without touching the check.

## V1. Banned phrase

Any phrase in the `banned_phrases` list of `config/voice.md`.

- **Hard fail** on any hit, on any channel, in any table cell.
- Fix: rewrite the whole sentence. Swapping one word usually leaves a generic
  sentence behind.

## V2. Punctuation and style rules

Each rule in the `style_rules` list of `config/voice.md`. The shipped example
is an em-dash rule (the long dash, Unicode U+2014): it is banned in body
prose, and the fix is a full stop, comma, colon or ellipsis. Replace it with
your own rules.

- Severity is set per rule in the config.

## V3. AI tells

Patterns that mark text as machine-written even when no single phrase is
banned. Default list in `config/voice.md`, section `ai_tells`. Examples:

- "Here's the thing:" or "Here's what most people miss:" openers;
- "It's not X. It's Y." used twice or more in one piece;
- rule-of-three lists used as filler;
- stacked adjectives;
- a closing "What do you think?";
- "In my experience..." with no scene attached;
- bullet lists where a sentence would land harder.

Soft flag each. **Hard fail** if 4 or more appear in one short artefact
(under 300 words).

## V4. Voice drift

Sentences that read like an encyclopedia summary, a corporate deck or a generic
ghost-writer rather than the author. Compare against the `voice_samples` in
`config/voice.md` if present.

Soft flag each. If more than a third of the draft drifts, verdict `rewrite`.
