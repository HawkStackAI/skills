---
name: game-qa
description: "Run game QA for a factory build: test plan, smoke gate, regression suite, bug reports and triage, and evidence review. Use at slice, at feature complete, and at every release candidate."
---

# Game QA

Test the game the way the factory ships: automated pack first, human judgement on top, evidence graded honestly. This skill merges the upstream qa-plan, team-qa, smoke-check, regression-suite, bug-report, bug-triage, soak-test, test-evidence-review, and test-flakiness workflows into the single QA pass the factory self beta test gate already expects, and maps them onto XCTest and XCUITest instead of engine test runners.

## The QA plan

For each build under test, classify every story or feature: Logic (unit test), Integration (unit plus UI test), Visual (screenshot snapshot), or UI flow (XCUITest walk). The plan lists the critical paths by name: cold launch, first loop completion, save and resume, purchase and restore in sandbox, settings, and the fail and win states. A critical path with no test is a finding, not a footnote.

## Smoke gate

Before any human play: the automated suite runs green, the app cold launches with no crash, and one full core loop completes in the UI test. A failed smoke check means the build is not QA ready and does not go to playtest. Say so plainly.

## Regression discipline

- Every fixed bug earns a regression test or a named manual case before it closes. A fix with no test is reopened on paper as a risk.
- The regression suite maps to the critical paths and to the fixed bug list. Drift (a path with no coverage after a new feature lands) is flagged at each release candidate.
- Flaky tests are tracked by name with pass rates from CI history. A flaky test is quarantined with a reason and a repair story, never silently retried until green and forgotten.

## Bugs

Report with: build number, device and OS, steps to reproduce from cold launch, expected and actual result, severity (crash or data loss, loop blocking, wrong behaviour, cosmetic), and evidence (screenshot, recording, or log). Triage re-scores priority against severity, assigns each bug to a release (this candidate, next update, or will not fix with a reason), and names systemic trends when three or more bugs share a cause.

## Extended session check

Adapted from the upstream soak test: one long session per release candidate (30 to 60 minutes of continuous play across levels, backgrounding, and resume) watching for memory growth, frame decay, save corruption, and fatigue failures that short tests miss.

## Evidence review

Grade the evidence for the build the way upstream test-evidence-review does, per critical path: ADEQUATE, INCOMPLETE, MISSING, or NOT ASSESSED, with the file or result behind each grade. The beta notes carry these grades and the explicit review readiness verdict the factory gate requires.

## Output

- qa-report.md with plan coverage, smoke result, regression status, open bugs by severity, extended session result, and the evidence grades.

## Factory rules that override upstream

- Stack is native Swift and SwiftUI (or SpriteKit only where a spec says so) on iOS. No Godot, Unity, Unreal, web canvas, or browser build steps anywhere in this workflow.
- One game, one job. The brief names the single core loop in one sentence; anything that does not serve it is out of scope until launch.
- Build sessions run on Opus; Fable is polish only. State the model at session start.
- Evidence over labels. A step counts as done only with a receipt: a build that runs, a screenshot pack, a test result, or a filled report in the project folder.
- Owner gates stay owner gates: spending, signatures, attestations, and personal identity calls are never made inside this workflow. Everything else is decided and recorded, not escalated as a question.
- No em dashes or en dashes in any output document, store copy, or in-game text produced here.
