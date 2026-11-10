---
name: game-vertical-slice
description: "Build and judge the vertical slice for a factory game: one complete, polished pass through the whole game before full production. Use after a prototype passes, before committing to full content production."
---

# Game Vertical Slice

Prove the whole game once, end to end, at shipping quality, before paying for all of it. Adapted from the upstream vertical-slice workflow with its validation question discipline kept and its engine pipeline assumptions replaced by the Swift build pipeline.

## Scope of a slice

- One complete run of the core loop with real content: for a puzzle game, a small set of finished levels including one hard one; for a match game, full board, scoring, fail state, and progression step.
- Every screen on the brief's screen list, present and reachable, even if some hold only the slice content.
- The real save, settings, and sound paths. The real Pro unlock screen, with purchase wired in sandbox.
- Final art direction on the slice content. The slice is what the screenshots and the App Store preview will be judged against later, so it cannot be grey box.

## Workflow

1. State the validation questions in writing first. Standard set: does the full loop hold together, does the difficulty ramp read correctly on real levels, does the build hold frame budget on the oldest supported device class, does the Pro offer land at a moment of proven value.
2. Build the slice as production code in the real target. Unlike the prototype, this code ships if the verdict is go.
3. Run the self beta test pack on the slice: unit tests, XCUITest walk of every screen plus one full loop, snapshot screenshots of every screen.
4. Review the screenshots one by one against the brief. Any screen that reads as placeholder fails the slice.
5. Answer each validation question with evidence, not adjectives. Verdict: GO (commit to full production), FIX (named gaps, one repair pass, recheck), or NO GO (return to brief or kill the concept, with the failed question named).

## Output

- Slice build, screenshot pack, and slice-report.md answering each validation question with its evidence and the verdict.

## Factory rules that override upstream

- Stack is native Swift and SwiftUI (or SpriteKit only where a spec says so) on iOS. No Godot, Unity, Unreal, web canvas, or browser build steps anywhere in this workflow.
- One game, one job. The brief names the single core loop in one sentence; anything that does not serve it is out of scope until launch.
- Build sessions run on Opus; Fable is polish only. State the model at session start.
- Evidence over labels. A step counts as done only with a receipt: a build that runs, a screenshot pack, a test result, or a filled report in the project folder.
- Owner gates stay owner gates: spending, signatures, attestations, and personal identity calls are never made inside this workflow. Everything else is decided and recorded, not escalated as a question.
- No em dashes or en dashes in any output document, store copy, or in-game text produced here.
