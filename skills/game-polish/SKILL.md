---
name: game-polish
description: "Run the polish pass on a factory game feature or the whole build: performance, feel, visuals, audio, and final QA hardening. Use after the cut pass and before the release candidate."
---

# Game Polish

Make the shipping game feel finished, in the order players notice. Adapted from the upstream team-polish orchestration and perf-profile workflow: upstream delegates to a four role team; the factory runs one pass with the same coverage, sequenced by player impact, and measured against device budgets instead of engine profiler targets.

## Budgets (set per game in the brief, checked here)

- Cold launch to interactive: under 2 seconds on the oldest supported device class.
- Frame time: stable 60 frames per second in the core loop, no hitch over 100 ms on level transitions.
- Memory: no growth across a long session (checked against the extended session result from game-qa).
- Battery and heat: a 30 minute session should not make a phone warm; if it does, the cause is found, not shrugged at.

## Pass order

1. Correctness of feel: input latency, animation timing, haptic and sound synchronisation, win and lose state clarity. A correct looking game that responds late feels broken.
2. Performance: profile the core loop and the heaviest screen, fix the top three measured costs, remeasure. No optimisation without a before and after number.
3. Visual consistency: spacing, type sizes, contrast, dark mode where the OS expects it, Dynamic Type and VoiceOver labels on every interactive element, and no text under the legibility floor on the smallest supported screen. Run the upstream style UX review checks as a checklist here: spec against build, accessibility, and readiness.
4. Audio: mix levels across effects and music, no clipping, silent mode respected, and audio that stops correctly on backgrounding.
5. Edge hardening: rotation and resize where supported, interruption handling (call, background, low power), first launch with no network, and upgrade with an old save file.
6. Screenshot proof: rerun the snapshot pack and read every screen. Polish that cannot be seen in the pack is claimed, not shown, and gets rechecked.

## Output

- polish-report.md with budget measurements before and after, the fixes in pass order, and the final screenshot pack reference. Open items move to game-launch-checklist as named risks or get cut through game-cut; they do not ride along silently.

## Factory rules that override upstream

- Stack is native Swift and SwiftUI (or SpriteKit only where a spec says so) on iOS. No Godot, Unity, Unreal, web canvas, or browser build steps anywhere in this workflow.
- One game, one job. The brief names the single core loop in one sentence; anything that does not serve it is out of scope until launch.
- Build sessions run on Opus; Fable is polish only. State the model at session start.
- Evidence over labels. A step counts as done only with a receipt: a build that runs, a screenshot pack, a test result, or a filled report in the project folder.
- Owner gates stay owner gates: spending, signatures, attestations, and personal identity calls are never made inside this workflow. Everything else is decided and recorded, not escalated as a question.
- No em dashes or en dashes in any output document, store copy, or in-game text produced here.
