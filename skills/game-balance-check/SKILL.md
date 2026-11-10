---
name: game-balance-check
description: "Audit a factory game's numbers for balance outliers, broken progressions, degenerate strategies, and economy imbalance. Use before the slice verdict, before launch, and after any tuning change."
---

# Game Balance Check

Find the numbers that break the game before players do. Adapted directly from the upstream balance-check workflow: its method (read the data, model the progression, hunt outliers and degenerate strategies) transfers unchanged; only the data formats change, from engine data files to Swift constants, JSON content files, and property lists in the factory codebase.

## Workflow

1. Name the balance domain for this pass: progression, scoring, economy (in game currency, hints, lives), difficulty, or a named system. One domain per pass keeps findings actionable.
2. Read the actual data: the shipped constants and content files, not the brief. Where brief and data disagree, the data is the finding.
3. Model the progression on paper: cost and reward per level band, time to each unlock, resource sources and sinks per session. Show the table; a curve that cannot be tabled cannot be judged.
4. Hunt the standard failures:
   - Outliers: any value more than roughly double or under half its neighbours in the same series, with no written reason.
   - Degenerate strategy: a single move, purchase, or grind that beats intended play. If the boring strategy wins, players will use only it.
   - Dead content: levels, items, or modes no rational player would choose at their price or difficulty.
   - Sink failure: currency earned faster than it can be spent, or a faucet that makes the Pro unlock pointless.
   - Wall failure: a difficulty step that a median player cannot pass without paying or grinding, in a game whose brief promises fairness.
5. Classify each finding: BLOCKER (breaks the loop or the store promise), TUNE (wrong number, right system), or WATCH (needs playtest data, named in the playtest plan).
6. Propose the smallest numeric change per finding, with the expected effect stated in advance, so the next check can confirm or refute it.

## Output

- balance-report.md with the progression table, findings by class, and the proposed changes with expected effects. No finding ships without the data value it rests on.

## Factory rules that override upstream

- Stack is native Swift and SwiftUI (or SpriteKit only where a spec says so) on iOS. No Godot, Unity, Unreal, web canvas, or browser build steps anywhere in this workflow.
- One game, one job. The brief names the single core loop in one sentence; anything that does not serve it is out of scope until launch.
- Build sessions run on Opus; Fable is polish only. State the model at session start.
- Evidence over labels. A step counts as done only with a receipt: a build that runs, a screenshot pack, a test result, or a filled report in the project folder.
- Owner gates stay owner gates: spending, signatures, attestations, and personal identity calls are never made inside this workflow. Everything else is decided and recorded, not escalated as a question.
- No em dashes or en dashes in any output document, store copy, or in-game text produced here.
