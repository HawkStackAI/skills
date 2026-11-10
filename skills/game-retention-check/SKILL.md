---
name: game-retention-check
description: "Check a factory game for difficulty fairness and retention risks before launch and after updates. Use when judging session design, difficulty walls, content cadence, and whether the Pro offer respects the player."
---

# Game Retention Check

Judge whether players will come back, using design evidence available before launch and real numbers after it. Adapted from the upstream team-live-ops orchestration and the live-ops and analytics agents, stripped of live service machinery the factory does not run: no seasons, no battle passes, no server events, no push campaign tooling. Factory games are offline first, content complete products; retention here means the game earns tomorrow's session honestly.

## Pre launch checks (design evidence)

- Session shape: a satisfying stopping point exists every few minutes, progress is visible, and the next goal is always named by the game itself.
- Difficulty fairness: no wall that a median player cannot pass with practice, verified against playtest fail counts from game-playtest-report. A wall placed to sell skips is a design failure here, and also a store review risk.
- Content depth against promise: the shipped level or puzzle count, at measured median solve times, delivers at least the hours the store page implies. Do the arithmetic and write it down.
- Return hooks that are not manipulation: unfinished sets, personal bests, daily puzzle where the genre supports it, and streaks that forgive a missed day. No expiring currency, no loss framing, no fake opponents.
- Pro respect test: a free player can finish the game; a Pro player gets more game, not relief from pain the design inflicted on purpose.

## Post launch checks (real numbers)

- Read App Store Connect and in game analytics where present: day 1 and day 7 retention where measurable, session count per player, level fail clustering, and the level where the most players last played before going quiet. That level is the first tuning target.
- Compare against the pre launch predictions made in this check. A prediction that missed gets its reason recorded, so the next game's check starts smarter.
- One change at a time, shipped as a tuning update with the expected effect written in advance, then remeasured. Two changes at once teach nothing.

## Output

- retention-check.md with the pre launch verdicts (PASS, CONCERN, or FAIL per check, with evidence) and, after launch, the measured follow up against predictions.

## Factory rules that override upstream

- Stack is native Swift and SwiftUI (or SpriteKit only where a spec says so) on iOS. No Godot, Unity, Unreal, web canvas, or browser build steps anywhere in this workflow.
- One game, one job. The brief names the single core loop in one sentence; anything that does not serve it is out of scope until launch.
- Build sessions run on Opus; Fable is polish only. State the model at session start.
- Evidence over labels. A step counts as done only with a receipt: a build that runs, a screenshot pack, a test result, or a filled report in the project folder.
- Owner gates stay owner gates: spending, signatures, attestations, and personal identity calls are never made inside this workflow. Everything else is decided and recorded, not escalated as a question.
- No em dashes or en dashes in any output document, store copy, or in-game text produced here.
