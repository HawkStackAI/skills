# Setup answers (example, preconfigured)

This file is a completed example of the answers the setup-matt-pocock-skills interview produces, filled in with a common default setup: GitHub Issues in the target repo, the canonical triage labels, and documentation living in the repo. To use it, copy the three files under docs/agents/ in this skill folder into a target repo at the same paths and add the Agent skills block below to that repo's AGENTS.md or CLAUDE.md (edit whichever already exists, never create the other). Replace the account and organisation names with your own.

## Answers

- Issue tracker: GitHub Issues, via the gh CLI, in the target repo under your own GitHub account or organisation. Infer the exact repo from git remote -v inside that repo and confirm with gh repo view before the first issue create in a session. Never file into the upstream mattpocock/skills repo.
- Triage: GitHub labels, using the five canonical roles with label strings equal to their names: needs-triage, needs-info, ready-for-agent, ready-for-human, wontfix. Category labels are bug and enhancement. Wayfinder labels are wayfinder:map and wayfinder:research, wayfinder:prototype, wayfinder:grilling, wayfinder:task.
- Docs: live in the target repo. Domain docs are single-context by default: GLOSSARY.md at the repo root and ADRs (architecture decision records) under docs/adr/. Agent setup docs live at docs/agents/issue-tracker.md, docs/agents/triage-labels.md, and docs/agents/domain.md in the target repo.
- Pull requests as a triage surface: no (the upstream default). Flip only in a repo where external pull requests are treated as feature requests.

## Agent skills block for the target repo

## Agent skills

### Issue tracker

Issues live in GitHub Issues for this repo. See docs/agents/issue-tracker.md.

### Triage labels

The five canonical triage roles, label strings equal to their names. See docs/agents/triage-labels.md.

### Domain docs

Single-context: GLOSSARY.md at the root, ADRs in docs/adr/. See docs/agents/domain.md.

## Files written in this skill folder

- SETUP-ANSWERS.md (this file): the example answers.
- docs/agents/issue-tracker.md: ready to copy into a target repo.
- docs/agents/triage-labels.md: ready to copy into a target repo.
- docs/agents/domain.md: ready to copy into a target repo.
