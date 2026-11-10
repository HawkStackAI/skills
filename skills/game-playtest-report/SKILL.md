---
name: game-playtest-report
description: "Structure, run, and report a playtest for a factory game. Use for prototype tests, slice tests, difficulty checks, and pre launch fresh eyes sessions."
---

# Game Playtest Report

Turn watching someone play into decisions. Adapted from the upstream playtest-report workflow, with its two modes kept (blank session template, and structuring raw notes) and its measures pointed at mobile puzzle and casual games.

## Before the session

- State the focus in one sentence: the loop, a level band, the difficulty ramp, the first minute, or the Pro offer moment. A session with no focus produces opinions, not findings.
- Recruit honestly: a tester who has never seen the game for first minute and comprehension questions; a genre player for difficulty questions. Note which kind each tester is; mixing them silently corrupts the findings.
- Prepare the build and the observation sheet. Tasks are given as goals (finish level 5), never as instructions (tap the blue tile), or the session tests the instructions instead of the game.

## During

Record per tester: time to first meaningful action, where they hesitated and for how long, every misread of the interface, level by level pass and fail, where they stopped and why, and the exact words they use to describe the game afterward. Observer does not help, hint, or explain; a rescued tester is a failed data point and is recorded as one.

## The report

- Session facts: build, date, tester count and kinds, focus.
- Findings ranked by severity times frequency, each with the observation behind it (counts and times, not adjectives). One tester hitting a wall is a note; every tester hitting it is a blocker.
- Comprehension verdict: can a fresh player state the goal and the core action after minute one, in their own words.
- Difficulty verdict per band tested: too easy, right, or wall, with fail counts.
- Decisions: each finding mapped to fix now, tune (with the number to change), watch next session, or accepted with a reason. Findings without decisions are returned to the report author, not filed.

## Output

- playtest-report.md in the project folder, filed by date and build, feeding game-level-design, game-balance-check, and the cut and polish passes.

## Factory rules that override upstream

- Stack is native Swift and SwiftUI (or SpriteKit only where a spec says so) on iOS. No Godot, Unity, Unreal, web canvas, or browser build steps anywhere in this workflow.
- One game, one job. The brief names the single core loop in one sentence; anything that does not serve it is out of scope until launch.
- Build sessions run on Opus; Fable is polish only. State the model at session start.
- Evidence over labels. A step counts as done only with a receipt: a build that runs, a screenshot pack, a test result, or a filled report in the project folder.
- Owner gates stay owner gates: spending, signatures, attestations, and personal identity calls are never made inside this workflow. Everything else is decided and recorded, not escalated as a question.
- No em dashes or en dashes in any output document, store copy, or in-game text produced here.
