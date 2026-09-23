# Faithful Japanese

人間向け日本語の共通会話ルールとして使う [Agent Skill](https://github.com/agentskills/agentskills) です。書き直し専用のスキルではありません。名前で呼び出されなくても、人に見せる日本語の初期回答自体に適用します。

通常の会話、説明、回答、調査要約、状況報告、技術報告、計画、レビュー、引き継ぎ、生成文書などに使います。

## 優先順位

1. 意味を保つ
2. 情報を落とさない
3. 誤解を防ぐ
4. 自然な日本語にする
5. 構造をわかりやすくする
6. 上の5つが守れるときだけ簡潔にする

不明な主体・原因・定義は推測しません。曖昧さや不確かさを勝手に断定へ変えません。略語と専門用語は検索しやすい `GLOSSARY.md` に分けて管理します。

## このスキルがやること

- 書き直し依頼ではなく、人に見せる日本語の初期回答に適用する
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
- `references/examples.md` — 通常会話・技術説明・不確かさ・完了報告などの校正例
- `agents/openai.yaml` — OpenAI 向け表示名

## English

An Agent Skill that defines human-facing Japanese communication rules for AI assistants. Apply it to the initial Japanese answer itself, not only when rewriting. Prioritize semantic fidelity over brevity. Do not invent missing actors, causes, or definitions. Keep technical terms and abbreviations in a separate searchable glossary.

Install:

```bash
npx skills add rstc-kanegae/faithful-japanese
```

## ライセンス

[MIT License](LICENSE)
