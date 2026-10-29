# Applying this edition on Muse

Muse has no plugin or system-prompt slot for a style spec. The edition applies through the two surfaces the product does expose:

1. **The agent skill.** Install `skills/talkspec-muse/` as a custom skill (on this deployment: `~/workspace/custom-skills/talkspec-muse/`). The skill body carries the adapted core; its `references/` carry the scenarios and language sections.
2. **The workspace operating notes.** The agent's `AGENTS.md` points at this edition as the communication default for everything the agent writes on Muse — chat replies and generated content (digests, guides, scheduled messages) — and records the derivation rule: canonical text is the latest upstream TalkSpec; this edition is its Muse profile, re-derived by audit when upstream changes version.

Fleet job bodies that cite TalkSpec inherit this edition on Muse, because the edition — not upstream — is the agent's standing default there. Other hosts are untouched: Claude Code, Codex, Cursor, and Grok keep upstream TalkSpec via their own adapters in the upstream repository.
