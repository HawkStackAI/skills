# Attribution

Source: anthropics/skills (GitHub), folder skills/skill-creator.
Repository: https://github.com/anthropics/skills
Pinned commit: 2c5958ecac7cee2b583967a2c4981d0f4a75c579
Copied: 2026-11-10.
License: Apache License 2.0. Full text in LICENSE in this folder (identical to the upstream LICENSE.txt, which is also kept because SKILL.md references it). Third party notices for the upstream repository are in THIRD_PARTY_NOTICES.md at the root of the upstream repository.

Local changes from upstream: em dashes and en dashes were mechanically normalized out of text files to follow the house style rule. No instructions, code logic, or file structure were changed.

Local notes: the eval and description optimization scripts assume a Claude Code `claude` CLI on PATH; where that CLI is not available, the authoring workflow, quick_validate.py, and package_skill.py still work with plain Python. Do not run run_eval.py or run_loop.py until they are adapted to your environment; they spawn `claude -p` subprocesses and write command files into a project .claude/commands folder.
