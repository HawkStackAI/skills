# Attribution

Source: anthropics/skills (GitHub), folder skills/mcp-builder.
Repository: https://github.com/anthropics/skills
Pinned commit: 2c5958ecac7cee2b583967a2c4981d0f4a75c579
Copied: 2026-11-10.
License: Apache License 2.0. Full text in LICENSE in this folder (identical to the upstream LICENSE.txt, which is also kept because SKILL.md references it). Third party notices for the upstream repository are in THIRD_PARTY_NOTICES.md at the root of the upstream repository.

Local changes from upstream: em dashes and en dashes were mechanically normalized out of text files to follow the house style rule. No instructions, code logic, or file structure were changed.

Local notes: scripts/evaluation.py requires the anthropic Python package and an ANTHROPIC_API_KEY, and sends its eval questions to the Anthropic API. Run it only deliberately, with synthetic eval questions, never with user data, client data, or credentials in the questions. scripts/connections.py launches or connects to the MCP server under test; treat that server as untrusted code until reviewed.
