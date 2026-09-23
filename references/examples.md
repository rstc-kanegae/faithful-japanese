# Calibration examples

These examples demonstrate the target balance: preserve technical meaning, restore omitted relationships, and write natural Japanese.

## Example 1: compressed technical notes

### Avoid

> RC境界でEvidence分離。transitive depsは契約外。RSS freeze後にverify。

### Prefer

> 再構築時に守るべき契約の境界に基づいて、検証に必要な証拠を分けます。元の実装が間接的に依存しているだけの要素は、再構築時に守るべき契約には含めません。RSSを固定したあと、その内容を検証します。

Notes:

- Restore particles and logical relationships.
- Do not invent the formal expansions of `RC` or `RSS` if they are not established.
- Put those abbreviations in `GLOSSARY.md`.

## Example 2: unknown actor

### Source

> 本番設定が更新されたため、旧設定では接続できない。

### Avoid

> 管理者が本番設定を更新したため、旧設定では接続できません。

### Prefer

> 本番設定が更新されたため、旧設定のままでは接続できません。

Reason: the source does not identify who updated the settings.

## Example 3: preserve uncertainty

### Source

> The failure may be caused by DNS caching, but we have not confirmed it.

### Avoid

> 原因はDNSキャッシュです。

### Prefer

> DNSキャッシュが原因である可能性があります。ただし、現時点では確認できていません。

## Example 4: preserve a precise technical term

### Avoid

> 間接的な依存関係を全部、不要な依存関係と呼び換える。

### Prefer

> `transitive dependency` は「間接的な依存関係」と説明します。ただし、「不要な依存関係」とは意味が異なるため、そのようには言い換えません。

## Example 5: do not over-structure

### Avoid

- 結論: 成功
- 理由: テスト通過
- 状態: 完了
- 詳細: なし

### Prefer

> テストはすべて通過しており、今回の変更については検証が完了しています。

Use a list only when the items are genuinely parallel or need independent scanning.
