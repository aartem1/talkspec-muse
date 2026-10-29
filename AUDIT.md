# Audit — how this edition was derived

Date: 2026-10-29. Method: every TalkSpec v0.2.2 rule was checked against two independent evidence sets before anything was changed. A rule was removed or scoped only where the evidence showed Muse already produces the behaviour or actively pushes against the rule. Everything else was carried verbatim.

## Evidence

**Local.** The operating instructions of a running Muse agent (its writing-style, brevity, and formatting sections) plus the product documentation shipped with it. Caveat: the audited copy is one user's configured instance, so "Muse default" here means the default as deployed, not a laboratory stock install. Result: 23 distinct built-in writing defaults; ~55 TalkSpec rules classified.

**External.**
- AirOps research as published in a chart shared on X (Simon Taylor, quote-posted by Alexandr Wang, 2026-10-29; data window Oct 23–27, 2026). AirOps publishes no methodology, prompt set, or caveats; the numbers are vendor data read off a chart. Muse vs ChatGPT / Gemini / Google AI Mode: citations per answer 25.1 / 6.9 / 6.2 / 7.3; average answer length 777 / 5,192 / 4,010 / 3,023 characters; answers using a list or table 11.4% / 95.5% / 98.8% / 98.6%; answers asking a question back 0.2% / 73.6% / 39.5% / 91.5%.
- Artificial Analysis, AA-PersonalityBench (Oct 2026): 900 questions, no system prompt, API surface. Muse Spark 1.3 leads Friendliness and co-leads Warmth and Informativeness; it is not in the top three for Direct or for Answer First (led by Grok and GPT models). Caveat: measures the model API, not the Muse app.
- Profound (Oct 2026, small exploratory sample): in the shopping flow, Muse by default does not name the sources it visits, and may ask follow-up questions to narrow a request. This conflicts with the AirOps citation count and is unreconciled in public sources; the difference is likely surface and definition.
- Meta's own materials state task orientation and report-back behaviour; the only explicit Meta-side style claim is Wang's "anti-slop-text" post. No public data exists on Muse's style in Russian or any non-English language, and none comparing chat with scheduled/background output style.

## Covered by Muse — kept as anchors, not re-argued

Conversational surface behaviour: brevity of the final response with complete (non-fragmented) sentences; repetition and stock-phrase cutting; bans on generic praise and canned openings; prose by default with no forced headings or bullets in casual chat; plainspoken error reporting; citation mechanics in chat; truthful completion claims; labelled estimates. These duplicate TalkSpec statements remain in the text where upstream put them, because the edition must stay self-contained where an agent's instructions are summarized, compacted, or rebuilt — and because fleet outputs (digests, guides, scheduled messages) do not inherit the chat surface's behaviour in any documented way.

## Not covered — carried verbatim (the core of this edition)

- Lead with the answer, as an explicit rule (see the answer rule's adaptation note).
- The priority ladder in scope.
- Every grammatical rule: named actor + finite verb; deverbal nouns rewritten as verbs; noun chains over three, and any chain ending in an objectless abstract noun; the compressed-label ban; the per-sentence information test; no announcements; an evaluation counts only with a concrete consequence; one idea per paragraph joined by real relations; one exact term per thing; antithesis and three-item lists only as content; read-aloud splitting.
- All English-only rules: nominalization recovery, passive discipline, plain over Latinate verbs, the copula rule, qualifier leeches, AI promotional lexis as a density warning.
- The entire Russian section, unchanged: канцелярит, support constructions, -ние dosing, participle stacking, denominal prepositions (Golub), genitive chains at 2–3 links, the register quarantine (Chukovsky), paired clichés, «являющийся», the subject/object genitive clash (Rozental §204), the «является» copula, stamp-density testing, information-final word order. No evidence about Muse's Russian exists; there was no basis to cut anything.
- Structure rules with no product equivalent: list grouping (~5 visible per group), visual-marker discipline.
- Evidence rules in full, including fact/inference/estimate separation and the fact-behind-the-evaluation rule.
- Continuity rules: finish the current item first; restate position, not finished content; the four-part failure report.
- Scenario rules with no product equivalent: correct a false premise before answering; no manufactured precision or confidence percentages; a provisional recommendation over a questionnaire, with its reversal condition; a complete explanation on request, not a teaser; the stop-and-diagnose rule after repeated failures.

## In tension — scoped, not deleted

Five changes, each recorded in the `adaptation` field of `spec/rules.json` (and one in `spec/scenarios/execution.md`):

1. **scope** — the no-profile assumption is replaced: Muse is a personal agent; use the given profile, assume nothing beyond it.
2. **answer** — "end when complete" is scoped to answers; task work keeps its next action and its required questions.
3. **language** — the idiom rule is scoped to informational and generated text; personal chat keeps natural idiom.
4. **structure** — the emoji ban becomes the marker principle (user's ruling, 2026-10-29): fitting, logical, sparse emoji and visualization that improve structure are welcome; decoration and excess are the defect. Chat reactions are exempt.
5. **questions** — the ask-only rule is scoped to task input; conversation with a user who is sharing is not intake.
6. **execution scenario** — estimates split by domain: content estimates in concrete units with their changing condition; the agent's own work durations are never stated unmeasured.

## Maintenance rule

This edition tracks the latest upstream TalkSpec. When upstream changes version, re-run this audit before re-deriving: a rule carried verbatim may have become covered, and a scoped rule may need its scope revisited. When Meta publishes measured style data for a new surface or language, the same applies in reverse.
