# TalkSpec — Muse Edition

**A profile of [TalkSpec](https://github.com/aartem1/talkspec) for Meta's Muse, derived by audit, not by taste.**

Upstream TalkSpec is a universal communication spec for AI assistants. Muse already implements part of it as product behaviour: its answers are measured far shorter than its rivals', rarely use lists or tables, and almost never end with a question. Repeating those rules at full weight is harmless but wasteful, and two upstream rules actively fight the product — Muse is a personal agent with a memory, and its chat voice is a friend's natural voice. This edition keeps the parts of TalkSpec that Muse does not supply, scopes the parts that collide, and records the evidence for every decision in [AUDIT.md](AUDIT.md).

## What changed, in one list

- **Kept verbatim:** the grammatical core (actor + verb sentences, nominalization recovery, noun-chain and compressed-label bans, the per-sentence information test, evaluation-needs-a-fact), all English-only rules, the entire Russian section, the evidence and continuity rules, list grouping, and most scenario guidance. The audit found no Muse default that produces any of these, and no public data at all on Muse's Russian style.
- **Scoped (5 core rules, 1 scenario):** the no-profile assumption becomes "use the given profile, assume nothing beyond it"; "end when complete" governs answers, while task work keeps its next action and required questions; the idiom rule binds informational and generated text, not personal chat; the emoji ban binds informational and generated text, with chat reactions exempt; the ask-only rule governs task input, not conversation; work-duration estimates are never stated unmeasured.
- **Removed:** nothing silently. Rules that duplicate Muse's defaults stay in the text as anchors, marked as covered in the audit, because an agent's instructions get summarized and rebuilt and the fleet surfaces do not inherit chat behaviour in any documented way.

## Structure

- `spec/rules.json` — the adapted core. Same eight rule ids as upstream; each rule carries an `adaptation` field stating what changed and why, or that it is upstream verbatim.
- `spec/languages/` — `en.md` and `ru.md`, identical to upstream.
- `spec/scenarios/` — upstream scenario guidance; `execution.md` carries the estimate-domain split.
- `skills/talkspec-muse/` — the installable skill form of this edition.
- `adapters/muse/` — how the edition is applied on Muse.
- `AUDIT.md` — the evidence and the full rule-by-rule classification.

## Derivation and tracking

This edition tracks the latest upstream TalkSpec (v0.2.2 at derivation). It is a profile, not a fork: when upstream changes, re-run the audit in AUDIT.md and re-derive. The canonical spec remains upstream; this repository owns only the Muse-specific delta.

## Scope of application

This edition is written for one surface: an agent running on Muse for a user who also runs full TalkSpec elsewhere. Other hosts (Claude Code, Codex, Cursor, Grok) keep upstream TalkSpec — their defaults differ, and this audit says nothing about them.

## License

MIT, inherited from upstream TalkSpec; attribution to the upstream project applies.
