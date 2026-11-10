---
name: game-design-brief
description: "Write the one page design brief and per system specs for a native Swift iOS game. Use after a concept is picked, and for any later design change that alters rules, numbers, or screens."
---

# Game Design Brief

Write the smallest design record that a build session can execute without guessing. Adapted from the upstream design-system, quick-design, and design-review workflows, compressed: upstream writes a full game design document per system with eight sections; the factory writes one page for the game and short specs only for systems that carry numbers or rules.

## The one page brief

Write design/game-brief.md with exactly these sections:

1. In the player's words: the concept as the player would describe it, kept verbatim from the pick.
2. Core loop: one sentence, plus the first minute described step by step (what the player sees, taps, and wins in minute one).
3. Challenge: where difficulty comes from, and what losing or stalling feels like.
4. Sessions: target session length, what brings a player back tomorrow, and the natural stopping points.
5. Features in, features later: two lists. Later is a real list; anything not on either list is out.
6. Numbers that matter: every tuning value the game depends on (board size, move limits, scoring, timers, prices) in one table with starting values and the reason for each.
7. Screens: the full screen list, one line each. If a screen is not listed, it is not built.
8. Pro unlock: what it contains and the exact moment it is offered.

## System specs (only where needed)

For a system with formulas, generation rules, or edge cases (puzzle generation, scoring, difficulty ramp, economy), add a spec under design/systems/ with: overview, detailed rules, edge cases and what happens in each, dependencies on other systems, and acceptance criteria a test can check. Systems without numbers get one paragraph in the brief and no spec.

## Quick changes

A tuning change or minor mechanic change does not reopen the brief. Write a quick design note instead: the change, the reason, the numbers before and after, and which acceptance criteria move. File it with the story it belongs to.

## Review before build

Run a self review of the brief and specs and record it in the same files:

- Completeness: every screen listed, every number tabled, every edge case in a spec answered.
- Consistency: no two sections disagree on a rule, a number, or a name. Cross check systems against each other the way upstream review-all-gdds checks across documents; here the scope is one game, so the check is fast and total.
- Implementability: a build session could start today without asking a design question. Any sentence it would have to guess at gets rewritten now.
- Apple risk: no mechanic that reads as gambling with real money, no placeholder content, no dead end screen.

## Output

- design/game-brief.md, plus system specs where the rule above requires them.
- Verdict line in the brief: READY TO BUILD, or NOT READY with the blocking gaps listed.

## Factory rules that override upstream

- Stack is native Swift and SwiftUI (or SpriteKit only where a spec says so) on iOS. No Godot, Unity, Unreal, web canvas, or browser build steps anywhere in this workflow.
- One game, one job. The brief names the single core loop in one sentence; anything that does not serve it is out of scope until launch.
- Build sessions run on Opus; Fable is polish only. State the model at session start.
- Evidence over labels. A step counts as done only with a receipt: a build that runs, a screenshot pack, a test result, or a filled report in the project folder.
- Owner gates stay owner gates: spending, signatures, attestations, and personal identity calls are never made inside this workflow. Everything else is decided and recorded, not escalated as a question.
- No em dashes or en dashes in any output document, store copy, or in-game text produced here.
