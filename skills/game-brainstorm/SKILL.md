---
name: game-brainstorm
description: "Find and choose a native iOS game concept for the app factory. Use when a new game slot opens, a concept feels weak, or ideas need ranking against factory economics before any brief is written."
---

# Game Brainstorm

Turn no idea, or a rough one, into one chosen concept that the design brief can carry. Adapted from the upstream brainstorm workflow, cut down to the lean tier only: the upstream full tier (director gates, pillars documents, multi agent review rounds) is dropped because heavy process before code is the opposite of factory economics.

## Inputs

- The game slot: puzzle, match, word, board, idle, or simulation, plus any theme hint.
- Shelf reality: the top competing titles in that slot on the App Store and what job they sell.
- Factory screen, applied before creativity gets a vote: the concept must be buildable in Swift by one build pipeline, understandable in under 10 seconds, session length 1 to 5 minutes, no server, no multiplayer, no licensed content, and a Pro unlock that is honest (more content, more modes, or deeper tools, never pay to win the core loop).

## Workflow

1. Propose 2 or 3 one line concepts. Verb first, mashup of mechanic and theme is fine. Each line states the core loop and the win moment.
2. Score each concept in the open on five lines: clarity (can a stranger repeat it back), novelty on the shelf (what is different from the top 5), build cost (small, medium, large, with the reason), content depth (can level or puzzle generation carry 100 plus sessions), and monetization fit (where the Pro unlock honestly sits).
3. Kill weak concepts in the same pass and say why in one line each. A concept that needs a server, a license, or a second mechanic to be fun is killed here, not later.
4. Pick one winner. Record the pick, the killed alternatives, and the scores in the project folder as concept-pick.md.
5. Hand off to game-design-brief. Do not write a game design document here.

## Output

- concept-pick.md with the winning one liner, its scores, and the killed list.
- Verdict line: PICKED, or NO PICK (all concepts failed the screen, with the failing test named). NO PICK is a valid result; forcing a weak concept into the pipeline is not.


## Factory rules that override upstream

- Stack is native Swift and SwiftUI (or SpriteKit only where a spec says so) on iOS. No Godot, Unity, Unreal, web canvas, or browser build steps anywhere in this workflow.
- One game, one job. The brief names the single core loop in one sentence; anything that does not serve it is out of scope until launch.
- Build sessions run on Opus; Fable is polish only. State the model at session start.
- Evidence over labels. A step counts as done only with a receipt: a build that runs, a screenshot pack, a test result, or a filled report in the project folder.
- Owner gates stay owner gates: spending, signatures, attestations, and personal identity calls are never made inside this workflow. Everything else is decided and recorded, not escalated as a question.
- No em dashes or en dashes in any output document, store copy, or in-game text produced here.
