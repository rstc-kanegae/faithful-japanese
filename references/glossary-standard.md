# Searchable glossary standard

Use this format for `GLOSSARY.md`.

## Purpose

The glossary exists to maintain shared vocabulary between the AI and human readers. It is not limited to rewritten documents. Update it whenever normal conversation, technical explanation, project work, reports, or generated documents introduce technical terms, abbreviations, or project-specific vocabulary.

## File rules

- File name: `GLOSSARY.md`
- Maintain one glossary per working project or deliverable set unless the user specifies otherwise.
- Update the existing file rather than creating versioned duplicates such as `GLOSSARY_2.md`.
- Save UTF-8 text.
- Sort entries by canonical term. Use case-insensitive alphabetical order for Latin terms, then a stable Japanese order for Japanese-only terms.
- Use one canonical entry per concept. Put spelling variants and aliases inside the entry.

## Entry format

Use the exact canonical term as a level-2 heading so exact search finds it immediately.

```markdown
# 用語集

## RSS
- 正式名称: Reconstructible Software Specification
- 種別: 略語 / プロジェクト用語
- 日本語での説明: 再構築に必要な仕様や証拠を固定した情報集合。
- このプロジェクトでの意味: 再構築側へ渡す契約情報の固定版を指す。
- 別名・表記ゆれ: RSS freeze
- 定義元: [文書名、URL、ファイル名、会話上の定義など]
- 状態: 確認済み
```

The example above is a formatting example only. Do not reuse its definition unless the project itself establishes that meaning.

## Required fields

Every entry must include:

- `種別`
- `日本語での説明`
- `状態`

Include these when applicable:

- `正式名称`
- `このプロジェクトでの意味`
- `別名・表記ゆれ`
- `定義元`

## Definition status

Use one of these values:

- `確認済み`: the definition is supported by source material or established context.
- `文脈上の定義`: the meaning is project-specific and established by the current project context.
- `未確認`: the term appears, but its exact expansion or definition cannot be established safely.

For `未確認`, do not fill gaps with a plausible guess. Example:

```markdown
## RC
- 種別: 略語
- 日本語での説明: この文脈で使われている略語。正確な正式名称は確認できていない。
- 定義元: 出力中の用例のみ
- 状態: 未確認
```

## What to include

Include:

- acronyms and initialisms;
- project-specific abbreviations;
- domain terms that a reasonable non-specialist may not know;
- uncommon English labels used as nouns in Japanese text;
- project-specific meanings of otherwise ordinary words;
- protocol, architecture, experiment, model, component, or process names when understanding them requires context.

Normally omit:

- ordinary Japanese words;
- universally obvious punctuation or formatting terms;
- common measurement units unless their interpretation is project-specific;
- code symbols already self-evident from a code listing, unless the prose relies on them as concepts.

## Searchability rules

- Preserve exact capitalization: `API`, `RSS`, `OAuth`, not normalized variants that hide the original form.
- Record alternate capitalization or spelling under `別名・表記ゆれ`.
- Do not embed multiple unrelated terms in one heading.
- Do not use poetic or explanatory headings such as `再構築について`; use the literal term instead.
- If two terms are synonyms, choose one canonical entry and list the other as an alias unless the project explicitly distinguishes them.
