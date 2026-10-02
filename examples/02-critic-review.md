## Critic review

date: 2026-10-03 · mode: sub-agent · draft: `examples/01-draft.md` · type: email

- [line 1 | banned phrase] "Unlock the potential of AI at Juno Freight" : HARD FAIL. "unlock potential" is on the banned list : rewrite the subject around one thing that is true only of Juno Freight
- [line 1 | generic messaging] "Unlock the potential of AI at Juno Freight" : HARD FAIL. Swap in any company name and the subject still works : anchor it in something specific to Juno, with a source
- [line 5 | banned phrase] "In today's fast-paced logistics world, AI is a game-changer." : HARD FAIL. Two banned phrases in one sentence : cut the sentence; it says nothing the reader does not already believe
- [line 6 | banned phrase] "At Halden & Co we help companies leverage AI to transform their operations seamlessly." : HARD FAIL. "leverage" as a verb and "seamlessly" are banned : say what you actually do, in one concrete sentence
- [line 6 | generic messaging] "At Halden & Co we help companies leverage AI to transform their operations seamlessly." : HARD FAIL. Any consultancy could send this line unchanged : name the one problem you start with
- [line 7 | clearance] "We recently helped Larch Atelier cut onboarding time by 40% with our AI agent rollout." : HARD FAIL. Larch Atelier is `Anonymised` in the registry and is named here : remove the name, and check the description is not identifiable
- [line 7 | unsourced claim] "cut onboarding time by 40%" : HARD FAIL. No source for the figure in the project files : cite the project note that measured it, or remove the number
- [line 7 | honest classification] "with our AI agent rollout" : HARD FAIL. The learned rule says never lead with tooling; this credits the tool for an onboarding result without evidence that the tool caused it : describe what changed for the people, or drop the claim
- [line 8 | unsourced claim] "Most freight companies are losing millions to manual dispatch." : HARD FAIL. A money claim about an industry with no source : remove it, or cite a named public source
- [line 8 | honest classification] "Most freight companies are losing millions to manual dispatch." : HARD FAIL. A guess written as a fact about the reader's own industry. Tomas will know if it is wrong : delete it
- [line 9 | ai tell] "Our proven framework covers strategy, tooling, and change management." : soft flag. Rule-of-three filler, and "proven" with no proof : name one thing the method does that others do not, or cut the line
- [line 10 | banned phrase] "I'd love to set up a 60-minute deep dive with your leadership team to explore synergies." : HARD FAIL. "deep dive" and "synergies" are banned : rewrite the ask
- [line 10 | audience mismatch] "I'd love to set up a 60-minute deep dive with your leadership team to explore synergies." : HARD FAIL. A head of operations cannot commit his leadership team's hour to a stranger's first email. The ask is not actionable : make the ask something he can say yes to alone, in under a minute
- [line 12 | ai tell] "What do you think?" : soft flag. Generic closer that invites no specific reply : end on the ask, or end on nothing
- [line 14 | audience mismatch] "Mira" : soft flag. A first name only, on a cold email, gives the reader no way to place the sender : full name and firm

```
hard_fails: 12
soft_flags: 3
packs_run: core, voice, clearance
missing_inputs: none
verdict: rewrite
reason: every hard fail can be fixed by the drafter from the draft and its sources; if the Larch result is the only proof point worth sending, the owner should decide whether to ask Larch for named clearance, which would make it escalate
```
