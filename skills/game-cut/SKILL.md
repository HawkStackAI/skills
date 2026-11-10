---
name: game-cut
description: "Run the cut pass at feature complete: propose what to cut, protect the core loop, and set the polish list and the finish date. Use when a game must converge to a launchable scope."
---

# Game Cut

Finish the game by removing things, on purpose, before launch pressure removes them at random. Adapted closely from the upstream cut workflow, which is one of the strongest in the repo: read what exists, propose cuts with reasons, let the decider pick each one, then set dates. Here the decider is the factory pipeline acting under the maintainer's delegated authority for scope calls; cuts are recorded with reasons and are reversible from source control until submission.

## Workflow

1. Read what exists: the brief and its two feature lists, the built feature set, open stories, QA findings, playtest findings, and the balance and retention reports. The cut list is built from evidence, not from taste.
2. Propose each cut with: what it is, what it costs to finish (stories, QA surface, store risk), what the player loses, and the recommendation (cut, defer to first update, or keep and finish). Candidates that always get reviewed: any feature used by a minority of sessions, any content band with repeated playtest failure, any system the brief marked later that crept in, and anything whose only argument is that it is already partly built.
3. Protect in the same pass: name what is never cut (core loop integrity, save reliability, purchase and restore, accessibility floor, the levels or content the store screenshots promise). A cut that touches the protected list needs a written override reason.
4. Decide each item in the document: CUT, DEFER, or KEEP, with one line of reasoning. No item stays undecided; an undecided cut list is how games miss dates.
5. Set the finish line: feature freeze date, release candidate date, and submission target, counted back from the remaining KEEP stories at measured velocity. If the dates do not fit, the answer is more cuts, not more hope.
6. Produce the polish list in the same document: everything that stays but is not yet at shipping quality, ranked, which becomes the input to game-polish.

## Output

- cut-list.md with per item decisions and reasons, the protected list, the three dates, and the ranked polish list.

## Factory rules that override upstream

- Stack is native Swift and SwiftUI (or SpriteKit only where a spec says so) on iOS. No Godot, Unity, Unreal, web canvas, or browser build steps anywhere in this workflow.
- One game, one job. The brief names the single core loop in one sentence; anything that does not serve it is out of scope until launch.
- Build sessions run on Opus; Fable is polish only. State the model at session start.
- Evidence over labels. A step counts as done only with a receipt: a build that runs, a screenshot pack, a test result, or a filled report in the project folder.
- Owner gates stay owner gates: spending, signatures, attestations, and personal identity calls are never made inside this workflow. Everything else is decided and recorded, not escalated as a question.
- No em dashes or en dashes in any output document, store copy, or in-game text produced here.
