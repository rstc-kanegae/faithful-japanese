---
name: faithful-japanese
description: Generate natural, plain, well-structured Japanese for human readers while preserving the intended meaning exactly. Use for Japanese explanations, reports, technical notes, plans, summaries, handoffs, reviews, research results, and other work outputs, especially when source material contains technical terms, abbreviations, English shorthand, project-specific vocabulary, dense AI-style compression, or ambiguous wording. Prioritize semantic fidelity over brevity, never invent missing facts or actors, and maintain a separate searchable glossary for technical terms and abbreviations.
---

# Faithful Japanese

## Purpose

Write Japanese that is easy to understand without simplifying away meaning.

Apply priorities in this order:

1. Preserve meaning.
2. Preserve information.
3. Prevent misunderstanding.
4. Use natural Japanese.
5. Make the structure easy to follow.
6. Be concise only when the first five remain intact.

Never trade semantic fidelity for shorter output.

## Core rule: preserve semantic invariants

Before finalizing, preserve all material distinctions in the source or task requirements, including:

- facts, numbers, names, identifiers, and references;
- subject, object, and responsibility when known;
- conditions, exceptions, prerequisites, and scope;
- negation and exclusions;
- degree, probability, uncertainty, and confidence;
- causal versus correlational relationships;
- chronological and procedural order;
- distinctions between requirement, recommendation, possibility, assumption, and example;
- distinctions between confirmed information and interpretation.

Do not strengthen, weaken, generalize, narrow, or otherwise alter a claim merely to make the Japanese smoother.

If the original wording is ambiguous, preserve the ambiguity or state that it is ambiguous. Do not silently choose an interpretation.

## Do not invent missing information

Do not add an actor, cause, intention, definition, expansion, conclusion, or relationship that is not supported by the source or task context.

For example, do not change:

> 設定が変更された。

into:

> 管理者が設定を変更した。

unless the actor is actually known.

When an abbreviation or project term cannot be expanded with confidence, retain the original term and mark its definition as unconfirmed in the glossary. Never guess an expansion because it looks plausible.

## Write natural Japanese

Use the principles of plain Japanese as a readability guide, but subordinate them to semantic fidelity.

- Prefer ordinary Japanese words when they express the same meaning precisely.
- Use complete sentences rather than compressed note fragments.
- Keep the subject and predicate reasonably close when doing so does not change emphasis or meaning.
- Break long sentences when the logical relationship remains clear.
- Use headings, paragraphs, bullets, or tables when they genuinely improve comprehension.
- Put the main point early when the main point is actually supported and doing so does not distort the source's logical order.
- Prefer active voice only when the actor is known. Do not invent an actor to avoid passive voice.
- Prefer positive wording only when it is logically equivalent. Preserve negation when it carries meaning.
- Avoid literal English-to-Japanese syntax when natural Japanese can express the same content more clearly.
- Avoid unnecessary honorifics, rhetorical flourishes, hype, and vague business jargon.

Treat sentence-length targets as guidance, not hard limits. A longer precise sentence is better than two short sentences that break a condition or dependency.

See `references/plain-japanese-adaptation.md` for the adapted readability rules.

## Prevent AI-style over-compression

Do not write Japanese as if it were token-saving notes for another model.

Avoid:

- unexplained abbreviations;
- newly coined acronyms or shorthand;
- noun chains that omit relationships;
- particles omitted for brevity;
- sentence fragments used as the default style;
- slash-separated concepts whose relationship is unclear;
- English labels inserted where ordinary Japanese is clearer;
- compressed statements that require the reader to reconstruct omitted logic.

Expand the minimum context needed for a human reader to understand what happened, why it matters, and how the ideas relate.

Example:

Bad:

> RC境界でEvidence分離。transitive depsは契約外。RSS freeze後にverify。

Better:

> 再構築時に守るべき契約の境界に基づいて、検証に必要な証拠を分けます。元の実装が間接的に依存しているだけの要素は、再構築時に守るべき契約には含めません。RSSを固定したあと、その内容を検証します。

If `RC` or `RSS` are official project terms, retain the official notation where useful and explain them rather than silently replacing them with an inferred expansion.

## Handle technical terms and abbreviations

Preserve an established technical or project term when replacing it would reduce precision, searchability, or compatibility with source material.

For each technical term or abbreviation that a reasonable non-specialist reader may not know:

1. At first use, give a short plain-language explanation when it can be done without disrupting the text.
2. Use one canonical spelling consistently afterward.
3. Do not create a new abbreviation merely to save space.
4. Add the term to the separate glossary.

Include project-specific terms even when they look like ordinary English words if they have a special project meaning.

## Maintain a separate searchable glossary

When the output contains technical terms, abbreviations, project-specific vocabulary, or uncommon English labels, create or update a separate glossary named `GLOSSARY.md` whenever the working environment supports files.

If `GLOSSARY.md` already exists, update it instead of creating competing glossary files. Preserve useful existing definitions unless new evidence requires a correction.

The glossary must be optimized for exact search:

- use the exact canonical term as the entry heading;
- record abbreviations and aliases explicitly;
- keep one canonical entry per concept;
- include the full form only when verified;
- explain the term in plain Japanese;
- distinguish general meaning from project-specific meaning when they differ;
- record the definition source or context when available;
- mark uncertain or unavailable definitions as `未確認` rather than guessing;
- sort entries by canonical term for predictable lookup.

Follow `references/glossary-standard.md` exactly for glossary structure.

If the environment cannot create a separate file, append a clearly separated `用語集` section after the main response using the same entry structure. Treat this as a fallback, not the preferred form.

Do not interrupt the main explanation with long dictionary definitions. Keep the main text readable and put detailed definitions in the glossary.

## Preserve project vocabulary without becoming opaque

Use official names, identifiers, file names, API names, commands, code symbols, standards, and protocol terms exactly when accuracy or searchability depends on them.

Do not translate code identifiers or command names.

When an English technical term has a stable Japanese equivalent, choose the form most likely to help the reader understand the sentence, while keeping the original searchable term in parentheses or in the glossary when useful.

Do not alternate casually between synonyms for the same concept. Terminological consistency is more important than stylistic variety.

## Structure explanations for human reading

Choose the lightest structure that makes the logic obvious.

A useful default is:

1. State the conclusion or current state.
2. Explain the reason or mechanism.
3. Describe conditions, exceptions, risks, or unresolved points.
4. Give procedures or details in the order they are used.

Do not force this order when the source meaning depends on a different sequence.

Use lists for parallel items. Use tables only when comparison across the same dimensions is genuinely useful. Avoid turning every sentence into a bullet.

## Fidelity check before final output

Silently verify the following before sending the answer:

1. Did any fact, condition, exception, uncertainty, negation, or scope disappear?
2. Did the wording add an actor, cause, intention, or conclusion that was not established?
3. Did a plain-language replacement make a technical distinction less precise?
4. Did any abbreviation or coined shorthand appear without an explanation?
5. Could a human reader understand the logical relationship without reconstructing omitted words?
6. Are official names and searchable identifiers preserved?
7. If technical terms or abbreviations appear, was `GLOSSARY.md` created or updated, or was the chat-only glossary fallback used?

If clarity and brevity conflict, keep the necessary explanation.

## References

- Read `references/plain-japanese-adaptation.md` when deciding how to apply plain-Japanese readability principles without changing meaning.
- Read `references/glossary-standard.md` whenever creating or updating the terminology glossary.
- Read `references/examples.md` when examples are useful for calibrating the desired output style.
