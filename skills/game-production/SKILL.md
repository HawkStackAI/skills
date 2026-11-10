---
name: game-production
description: "Run production for a factory game: epics, stories with acceptance criteria, readiness and done checks, sprint planning and status, milestone reviews, and scope checks. Use from brief approval to launch."
---

# Game Production

Keep a game build moving in stories that can be verified, at the lightest weight that still prevents drift. Adapted from the upstream create-epics, create-stories, story-readiness, story-done, dev-story, sprint-plan, sprint-status, milestone-review, and scope-check workflows. Upstream runs these as separate heavy ceremonies with director gates; the factory runs them as one pass with the same checks, because the builder and the checker are usually the same pipeline here.

## Stories

- One epic per system in the brief (core loop, content, progression, monetization, settings and save, polish and store assets).
- Each story is implementable in one build session and carries: the player visible result, acceptance criteria a test or screenshot can check, the design source (brief section or system spec), and dependencies. A story that cannot state its acceptance criteria is not ready, and the readiness check says which criterion is missing.
- Story readiness gate, applied before a build session starts it: criteria checkable, design source present, dependencies done or explicitly waived with the risk written down.
- Story done gate, applied before it closes: every criterion verified with evidence (test result, screenshot, or play note), no silent deviation from the design source, and any deviation recorded as a design change note for game-design-brief to absorb.

## Planning rhythm

- Sprint plan: pull stories by dependency and risk, hardest unknowns first, slice scope protected (the vertical slice stories outrank content volume until the slice verdict is GO).
- Sprint status: one short snapshot per check in: stories done, in progress, blocked, with the blocker named in plain words and the day count. No burndown theatre for a one pipeline factory; the snapshot is the instrument.
- Milestone review at concept, slice, feature complete, and release candidate: completeness against the brief, quality evidence from game-qa, open risks, and a go or no go recommendation with reasons. The review is a page, not a meeting pack.

## Scope check

At each milestone, diff the current feature list against the brief's features in and features later lists. Every addition since the brief is named, priced in stories, and either formally moved into scope (with something else moved out or the launch date moved) or cut on the spot. Silent scope growth is the failure this workflow exists to catch, and it feeds game-cut at feature complete.

## Output

- Epic and story files in the project production folder, status snapshots, milestone review pages, and scope check notes, all dated and tied to build numbers where relevant.

## Factory rules that override upstream

- Stack is native Swift and SwiftUI (or SpriteKit only where a spec says so) on iOS. No Godot, Unity, Unreal, web canvas, or browser build steps anywhere in this workflow.
- One game, one job. The brief names the single core loop in one sentence; anything that does not serve it is out of scope until launch.
- Build sessions run on Opus; Fable is polish only. State the model at session start.
- Evidence over labels. A step counts as done only with a receipt: a build that runs, a screenshot pack, a test result, or a filled report in the project folder.
- Owner gates stay owner gates: spending, signatures, attestations, and personal identity calls are never made inside this workflow. Everything else is decided and recorded, not escalated as a question.
- No em dashes or en dashes in any output document, store copy, or in-game text produced here.
