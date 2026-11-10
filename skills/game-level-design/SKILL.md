---
name: game-level-design
description: "Design levels, puzzles, boards, and encounter pacing for a native Swift iOS game. Use when producing a level set, a puzzle generation spec, or a difficulty ordered content pack."
---

# Game Level Design

Produce levels and puzzle content that teach, test, and then twist the core loop, in that order. Adapted from the upstream team-level orchestration and the level-designer agent: upstream coordinates a six role team across narrative, world, and art for explorable areas; the factory version is a single disciplined pass for levels, puzzles, and boards in 2D Swift games, where the level itself is the content.

## Design rules

- Every level has one job, written on it: teach a mechanic, practice it, combine it, test mastery, or rest. A level with no job, or three jobs, gets redesigned.
- New information one piece at a time. A player should never meet a new mechanic and a new hazard in the same level.
- Difficulty is a curve, not a vibe. Each level records its difficulty drivers numerically where the game allows (target count, move or time limit, board density, distractor count, par score), and the set is ordered by those drivers, then adjusted by playtest data.
- Generated puzzles need a solvability proof, not hope: the generator or a solver pass must verify every shipped puzzle is solvable inside its limits, and record the proof in the content validation step of the build.
- Fairness first: no level whose solution depends on information the player cannot see, a reflex window under the accessibility floor, or a purchase.

## Workflow

1. Map the set: level count, the job of each level, and where each mechanic is introduced, practiced, and tested. Write it as a table before designing any single level.
2. Design in waves of 10 to 20 levels. For each wave, record difficulty drivers per level and check the curve for spikes (a driver jumping more than the set's usual step) and flats (five or more levels with no new pressure).
3. For generated content, write the generation spec instead: parameter ranges per difficulty band, the solver check, the rejection rules, and the seed handling so a reported puzzle can be reproduced exactly.
4. Validate: solver or scripted pass over the whole set, plus a human style review of the first, middle, and hardest levels against the brief.
5. Ship the set with its table. Playtest findings come back through game-playtest-report and change the table first, then the levels.

## Output

- The level set or generation spec, the set table with jobs and difficulty drivers, and the validation result (solvable count out of total, spikes found and fixed).

## Factory rules that override upstream

- Stack is native Swift and SwiftUI (or SpriteKit only where a spec says so) on iOS. No Godot, Unity, Unreal, web canvas, or browser build steps anywhere in this workflow.
- One game, one job. The brief names the single core loop in one sentence; anything that does not serve it is out of scope until launch.
- Build sessions run on Opus; Fable is polish only. State the model at session start.
- Evidence over labels. A step counts as done only with a receipt: a build that runs, a screenshot pack, a test result, or a filled report in the project folder.
- Owner gates stay owner gates: spending, signatures, attestations, and personal identity calls are never made inside this workflow. Everything else is decided and recorded, not escalated as a question.
- No em dashes or en dashes in any output document, store copy, or in-game text produced here.
