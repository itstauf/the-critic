# Voice config

Fill this in. The `voice` pack reads it. Everything here is an example; delete
what does not apply to you and add your own.

## banned_phrases

One per line. The critic matches case-insensitively.

```
game-changer
leverage (as a verb)
synergy
unlock value
unlock potential
in today's fast-paced world
revolutionize
deep dive
thought leader
best practices
at scale (as filler)
seamless
robust
delve
```

## style_rules

| Rule | Severity | Fix |
|---|---|---|
| No em-dash (U+2014) in body prose | hard fail | Full stop, comma, colon or ellipsis |
| No contractions in client reports outside quotations | soft flag | Expand it |
| No exclamation marks in outreach | soft flag | Remove it |

## ai_tells

```
"Here's the thing:"
"Here's what most people miss:"
"Imagine if..." as an opener
"It's not X. It's Y." more than once
rule-of-three filler
stacked adjectives
closing "What do you think?"
"In my experience..." with no scene
```

## voice_samples

Paste two or three short passages you wrote and are happy with. The critic uses
them as the reference for voice drift.

```
(paste here)
```
