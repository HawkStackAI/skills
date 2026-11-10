---
name: game-prototype
description: "Build a throwaway playable prototype of a game concept in native Swift to test whether the core loop is fun. Use after the brief, before any production build commitment."
---

# Game Prototype

Test one question: is the core loop fun in the hand, in under five minutes of play? Adapted from the upstream prototype workflow; the upstream route builds a browser game in a single HTML folder, which is dropped here. The factory prototype is a native Swift build, because feel on the target device is the thing being tested and a browser stand in cannot answer for touch, haptics, or frame timing.

## Rules

- Throwaway by declaration. Prototype code lives in a prototypes/ target or branch, is never merged into the production target, and is written for speed: hard coded content is fine, architecture is not a goal.
- One question per prototype. The brief for the prototype is three lines: the loop being tested, the one variable that decides pass or fail (for example solve time, fail rate, or one more round rate in a timed session), and the kill threshold written before the build starts.
- Timebox: one build session. If the loop is not playable inside the timebox, that is the result; record it and stop.
- No art pass, no store assets, no Pro unlock, no analytics SDK. Sound and haptics only where they are part of the feel being tested.

## Workflow

1. Write the three line prototype brief and the kill threshold.
2. Build the smallest playable version: one level set or one endless loop, start to win or lose, restart in one tap.
3. Run it through the scripted check: cold launch with no crash, the core loop completed once end to end by the test pack, screenshots of the start, mid loop, and end states.
4. Play it as a person would for the timed session and record the deciding variable honestly. Scripted checks prove it runs; they never prove it is fun, and the report says so in those words: Not yet played by a person, until a person has played it.
5. Verdict: FUN (advance to vertical slice or production), FLAT (one named change worth one retest), or DEAD (kill threshold met, concept returns to game-brainstorm or dies). Record the verdict and the numbers in the prototype folder.

## Output

- Playable prototype build, screenshot set, and a verdict note with the deciding variable and its measured value.

## Factory rules that override upstream

- Stack is native Swift and SwiftUI (or SpriteKit only where a spec says so) on iOS. No Godot, Unity, Unreal, web canvas, or browser build steps anywhere in this workflow.
- One game, one job. The brief names the single core loop in one sentence; anything that does not serve it is out of scope until launch.
- Build sessions run on Opus; Fable is polish only. State the model at session start.
- Evidence over labels. A step counts as done only with a receipt: a build that runs, a screenshot pack, a test result, or a filled report in the project folder.
- Owner gates stay owner gates: spending, signatures, attestations, and personal identity calls are never made inside this workflow. Everything else is decided and recorded, not escalated as a question.
- No em dashes or en dashes in any output document, store copy, or in-game text produced here.
