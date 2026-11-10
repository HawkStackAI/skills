# HawkStack Skills

A curated best-of library of Agent Skills: the instruction folders that teach AI coding agents how to do specific jobs well. Every skill in this repo was screened from a named public upstream, deduplicated against the rest of the set, and kept only where it was the strongest version of its job. Sixty skills, organized in six sets.

Maintained by HawkStack AI.

## Install

Each skill is a self-contained folder under `skills/` with a `SKILL.md` at its root.

- Copy any single skill folder into your agent's skills directory (for example `~/.claude/skills/` for Claude Code, or your project's skills folder) and it is ready to use.
- Or clone this whole repo and copy the sets you want:

```bash
git clone https://github.com/HawkStackAI/skills.git
cp -r skills/tdd ~/.claude/skills/
```

- Tooling that discovers skills in the `skills/*/SKILL.md` layout (such as the `skills` CLI used by the upstream projects) can read this repo directly.

## The sets

### Engineering core, 26 skills (from mattpocock/skills, MIT)

tdd, diagnosing-bugs, code-review, grill-with-docs, grilling, domain-modeling, setup-matt-pocock-skills, to-spec, to-tickets, implement, implement-spec, wayfinder, triage, improve-codebase-architecture, codebase-design, prototype, research, pr, retro, ask-matt, grill-me, handoff, teach, to-questionnaire, wait-what, writing-for-agents.

The setup skill ships with SETUP-ANSWERS.md rewritten as a generic example template, so no maintainer-specific answers ship as defaults. Run the setup interview in your own repos and fill in your own.

### Engineering extensions, 13 skills (from addyosmani/agent-skills, MIT)

api-and-interface-design, code-simplification, constraint-driven-development, context-engineering, deprecation-and-migration, doubt-driven-development, frontend-ui-engineering, git-workflow-and-versioning, idea-refine, observability-and-instrumentation, performance-optimization, shipping-and-launch, source-driven-development. Bundled reference checklists are included inside each skill folder, as installed.

### Creation and communication, 6 skills (from anthropics/skills, Apache 2.0)

skill-creator, mcp-builder, frontend-design, internal-comms, canvas-design, algorithmic-art. Local notes that were specific to one machine were rewritten as general notes.

### Security audit, 1 skill (from cloudflare/security-audit-skill, MIT)

security-audit: a multi-phase security audit workflow with independently verified, machine-readable findings.

### Design, 1 skill (from Nutlope/hallmark, MIT)

hallmark: an anti-AI-slop design skill that deals a theme, builds the page around the visitor's job, and lints the result in a real browser.

### Game studio for native iOS, 13 skills (adapted from Donchitos/Claude-Code-Game-Studios, MIT)

game-brainstorm, game-design-brief, game-prototype, game-vertical-slice, game-level-design, game-balance-check, game-playtest-report, game-qa, game-polish, game-cut, game-retention-check, game-launch-checklist, game-production. These are our own adaptations: the upstream studio workflow rewritten for native Swift iOS games, with engine-specific material (Godot, Unity, Unreal, web) dropped and app factory gates (self beta test pack, App Store Optimization pass, listing audit) added.

## How this library was assembled

This is a best-of set, not a mirror. The maintainers screened the public skill repos named above, read every candidate skill in full, and kept one winner per job: where two upstreams covered the same work, the stronger or better-fitting version survived and the other was left out. Every folder keeps its upstream LICENSE and an ATTRIBUTION.md recording the source repo, the pinned commit it was taken from, and what was changed locally. Local changes are small and recorded in those files: house style normalization (em dashes and en dashes removed from copied text), bundled checklists made self-contained, setup answers generalized into a template, and machine-specific notes rewritten as general ones.

## Licenses

The top-level LICENSE in this repo (MIT) covers HawkStack's own original material and adaptations only. It does not relicense anyone else's work. Each skill folder carries its own LICENSE and ATTRIBUTION.md, and those govern that folder: MIT for the mattpocock/skills, addyosmani/agent-skills, Nutlope/hallmark, cloudflare/security-audit-skill, and Game Studios derived material; Apache License 2.0 for the anthropics/skills material. Third-party font licenses inside canvas-design are the SIL Open Font License texts shipped in that folder.

## One honest gap in this snapshot

Two upstream binary asset sets are not in this repo yet: the canvas-design font files (54 TTF files, SIL Open Font License, from anthropics/skills) and the Hallmark theme pictures (50 JPG files, from Nutlope/hallmark). Both are unchanged upstream assets, and the publishing path used for this first release carries text files only. Fetch those two sets from the upstream repos if you want the complete folders; they will be added here when the publishing path supports binary files. Everything else in the sixty skills is complete as installed, including all scripts, references, and checklists.
