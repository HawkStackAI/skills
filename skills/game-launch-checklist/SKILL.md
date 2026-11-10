---
name: game-launch-checklist
description: "Judge launch readiness for a factory game and run the release checklist through submission. Use at release candidate and on submission day."
---

# Game Launch Checklist

One go or no go judgement for a factory game, assembled from evidence produced by the other game skills, plus the store and submission work that is specific to Apple. Adapted from the upstream launch-checklist, release-checklist, and gate-check workflows: upstream checks across departments including community, infrastructure, and legal teams; the factory version keeps every check that maps to a real factory risk and drops department sign offs for departments that do not exist here.

## Gate verdict

Use the upstream gate vocabulary for the whole judgement and for each section: PASS, CONCERNS, NOT ASSESSED, or FAIL. NOT ASSESSED is a blocking answer at submission time; a section nobody checked is not a passed section. Any FAIL blocks submission until fixed or formally cut.

## Sections

1. Build: release candidate archived from a clean checkout, version and build numbers correct, no debug flags, no test purchase products, crash free in the extended session check.
2. Quality: game-qa report filed, evidence grades ADEQUATE on every critical path, no open blocker or loop breaking bugs, regression suite green.
3. Game truth: balance check and retention check filed, protected list from game-cut intact, the game the store page describes is the game in the build (features, level counts, Pro contents all verified against the build, not the brief).
4. Store: the ASO gate pass is complete (keyword research, metadata built to character limits, extra language localizations, first three screenshots selling the one job from real verified screens), pricing and Pro unlock configured, age rating answered, privacy labels match actual data behaviour, and the listing complete audit has read every App Store Connect section live before anyone calls it ready.
5. Review readiness: review notes give the reviewer a working demo path, the purchase and restore path is walkable, no placeholder content or dead ends anywhere, per the self beta test gate standard.
6. Rollback and day one: the previous build is retained, a day one patch scope can be assembled in one session if a blocker escapes (adapted from the upstream day-one-patch workflow), and the monitoring routine for the first week is named: crash reports, reviews, and ratings checked daily, with review mining feeding the next metadata update.

## Output

- launch-checklist.md with a verdict per section, the evidence link behind each, open CONCERNS with owners and dates, and the final GO or NO GO line signed by the run that produced it.

## Factory rules that override upstream

- Stack is native Swift and SwiftUI (or SpriteKit only where a spec says so) on iOS. No Godot, Unity, Unreal, web canvas, or browser build steps anywhere in this workflow.
- One game, one job. The brief names the single core loop in one sentence; anything that does not serve it is out of scope until launch.
- Build sessions run on Opus; Fable is polish only. State the model at session start.
- Evidence over labels. A step counts as done only with a receipt: a build that runs, a screenshot pack, a test result, or a filled report in the project folder.
- Owner gates stay owner gates: spending, signatures, attestations, and personal identity calls are never made inside this workflow. Everything else is decided and recorded, not escalated as a question.
- No em dashes or en dashes in any output document, store copy, or in-game text produced here.
