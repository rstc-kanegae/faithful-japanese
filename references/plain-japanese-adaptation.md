# Plain Japanese adaptation for human-facing AI output

This reference adapts plain-language principles for Japanese responses produced by AI assistants. The governing rule is semantic fidelity: readability rules may improve expression, but they must never alter the underlying meaning.

Reference inspiration: Japan Association of Plain Language, "プレインジャパニーズとは" and its guidance pages.

- https://japl9.org/plainjapanese/
- https://japl9.org/plainjapanese/j10rules-analysis/

## Adapted rules

### 1. Write for the actual human reader

Assume the reader is intelligent but may not share the model's internal shorthand, latent associations, or project-specific vocabulary. Do not assume that a technical reader automatically knows local abbreviations.

### 2. State the main point early when safe

Put the conclusion or current state early when it is already established by the evidence. Do not manufacture a conclusion merely to satisfy a preferred writing structure.

### 3. Make the visual structure readable

Use headings, paragraphs, lists, and tables to expose relationships. Structure must clarify the content, not replace missing explanation.

### 4. Prefer manageable sentences

Split long sentences when conditions, modifiers, and causal relations remain intact. Do not obey a fixed character limit at the cost of precision.

### 5. Prefer familiar words

Replace unnecessarily difficult wording with ordinary Japanese only when the replacement is semantically equivalent. Retain technical terms when they carry a specific established meaning.

### 6. Remove needless wording, not needed information

Delete repetition, decoration, and empty phrases. Do not delete assumptions, qualifications, evidence, examples needed for interpretation, or boundary conditions.

### 7. Prefer active voice only with a known actor

Active voice often clarifies responsibility, but converting passive voice must not introduce an inferred actor. When the actor is unknown or intentionally unspecified, keep the passive or actor-neutral construction.

### 8. Prefer positive wording only when logically equivalent

Do not transform a negative statement if the positive version changes scope, obligation, exception handling, or logical force.

### 9. Keep subject and predicate close when practical

Reorder or split a sentence to reduce cognitive load, provided the modification does not change the attachment of modifiers or the information structure.

## Additional AI-specific rules

Plain-language guidance alone is not sufficient for human-facing AI output. Also enforce the following:

- Apply the rules to the initial response, not only when rewriting existing text.
- Do not compress prose into note-like fragments.
- Do not coin abbreviations for one-off use.
- Do not hide uncertainty behind assertive prose.
- Do not silently resolve ambiguity.
- Do not replace precise domain terms with broad everyday words if precision is lost.
- Preserve exact identifiers, filenames, commands, API names, protocol names, version numbers, and proper nouns.
- Maintain terminology consistently across the response and glossary.
- Explain relationships that would otherwise exist only implicitly in the model's reasoning.
- Do not confuse short output with clear output.
