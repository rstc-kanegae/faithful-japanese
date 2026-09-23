# Faithful Japanese

意味を変えずに、人が読める自然な日本語を書くための [Agent Skill](https://github.com/agentskills/agentskills) です。

技術用語、略語、英語の省略、プロジェクト固有の語彙、AI特有の圧縮表現を含む説明・報告・技術メモ・計画・要約・引き継ぎ・レビュー・調査結果などに使います。

## 優先順位

1. 意味を保つ
2. 情報を落とさない
3. 誤解を防ぐ
4. 自然な日本語にする
5. 構造をわかりやすくする
6. 上の5つが守れるときだけ簡潔にする

不明な主体・原因・定義は推測しません。曖昧さや不確かさを勝手に断定へ変えません。略語と専門用語は検索しやすい `GLOSSARY.md` に分けて管理します。

## このスキルがやること

- 意味と情報を先に守り、そのうえで自然な日本語にする
- 不明な行為者・原因・定義を補わない
- 曖昧さや不確かさを勝手に断定へ変えない
- 技術用語と略語は検索しやすい用語集に残す
- トークン節約のためのメモ体・省略体を避ける

## インストール

Agent Skills 形式です。次のいずれかで導入できます。

```bash
npx skills add rstc-kanegae/faithful-japanese
```

```bash
git clone https://github.com/rstc-kanegae/faithful-japanese.git
```

手動で置く場合の例:

| 環境 | 配置先 |
| --- | --- |
| Claude Code | `~/.claude/skills/faithful-japanese/` |
| Cursor | `~/.cursor/skills/faithful-japanese/` または `.cursor/skills/faithful-japanese/` |
| Codex | `~/.codex/skills/faithful-japanese/` |
| プロジェクト共通 | `.agents/skills/faithful-japanese/` |

このリポジトリのルートに `SKILL.md` があるため、リポジトリそのものをスキルフォルダとして使えます。

## 構成

```
SKILL.md
agents/openai.yaml
references/
  examples.md
  glossary-standard.md
  plain-japanese-adaptation.md
```

- `SKILL.md` — スキル本体（メタデータと指示）
- `references/plain-japanese-adaptation.md` — プレインジャパニーズの適用方針
- `references/glossary-standard.md` — 用語集の書き方
- `references/examples.md` — 出力スタイルの校正例
- `agents/openai.yaml` — OpenAI 向け表示名

## English

An Agent Skill for writing natural, readable Japanese without changing the intended meaning. Prioritize semantic fidelity over brevity. Do not invent missing actors, causes, or definitions. Keep technical terms and abbreviations in a separate searchable glossary.

Install:

```bash
npx skills add rstc-kanegae/faithful-japanese
```

## ライセンス

[MIT License](LICENSE)
