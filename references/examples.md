# Calibration examples

These examples show how the skill should shape ordinary human-facing output from the start. They are not primarily rewrite examples.

## Example 1: ordinary technical status report

### Internal understanding

The model has established that seven runtime traces were requested, five have been captured, and two failed because the fixed build did not launch in one environment.

### Avoid

> 5/7 traces done. 2 fail due env/build launch issue. Retry after env fix.

### Prefer

> 7本の実行記録のうち、5本は取得できました。残り2本は、固定したビルドが対象環境で起動しなかったため取得できていません。現時点では、環境側の問題なのかビルド側の問題なのかまでは確定していません。

Why:

- Write the report for a human without waiting for a rewrite request.
- Preserve the unresolved cause instead of collapsing it into a confident diagnosis.
- Restore omitted particles and logical relationships.

## Example 2: answer to a user question

### User question

> この設定ならCloudflareだけで十分ですか？

### Avoid

> 基本OK。Origin bypassだけ注意。

### Prefer

> Cloudflare側の保護だけで十分とは限りません。Cloudflareを経由せずにオリジンサーバーへ直接アクセスできる状態が残っていると、AccessやWAFを回避されるためです。オリジン側でも、Cloudflare経由の通信だけを許可する構成にする必要があります。

Why:

- Explain the condition that makes the conclusion true or false.
- Do not compress the answer into shorthand that assumes shared context.

## Example 3: unknown actor

### Established fact

> 本番設定が更新されたため、旧設定では接続できない。

### Avoid

> 管理者が本番設定を更新したため、旧設定では接続できません。

### Prefer

> 本番設定が更新されたため、旧設定のままでは接続できません。

Why: the available information does not identify who updated the settings.

## Example 4: preserve uncertainty

### Established fact

> The failure may be caused by DNS caching, but we have not confirmed it.

### Avoid

> 原因はDNSキャッシュです。

### Prefer

> DNSキャッシュが原因である可能性があります。ただし、現時点では確認できていません。

## Example 5: technical term in normal conversation

### Avoid

> transitive depsは契約外です。

### Prefer

> `transitive dependency`（間接的な依存関係）は、元の実装では必要でも、今回の再構築で必ず守るべき契約には含めません。

Also add `transitive dependency` to `GLOSSARY.md` if the working environment supports persistent files.

## Example 6: project-specific abbreviation with unknown expansion

### Available context

The project repeatedly uses `RC`, but its formal expansion is not established.

### Avoid

> RC（Reconstruction Contract）の境界を確認しました。

### Prefer

> `RC` の境界を確認しました。ここではプロジェクト内の正式な略語として使われていますが、正式名称は現在の情報だけでは確認できません。

In `GLOSSARY.md`, mark the term as `未確認` rather than guessing the full form.

## Example 7: completion report

### Avoid

> Done. Tests green. No issues.

### Prefer

> 変更は完了し、実行したテストはすべて通過しました。今回確認した範囲では、新たな問題は見つかっていません。

Why: `問題なし` can overstate certainty if only a limited test scope was checked.

## Example 8: do not over-structure

### Avoid

- 結論: 成功
- 理由: テスト通過
- 状態: 完了
- 詳細: なし

### Prefer

> テストはすべて通過しており、今回の変更については検証が完了しています。

Use a list only when the items are genuinely parallel or need independent scanning.

## Example 9: preserve a precise technical distinction

### Avoid

> 間接的な依存関係を全部、不要な依存関係と呼びます。

### Prefer

> `transitive dependency` は「間接的な依存関係」と説明できます。ただし、「不要な依存関係」とは意味が異なるため、そのようには言い換えません。

## Example 10: user explicitly asks for a short answer

### User request

> 3行で説明して。

### Prefer

Keep the answer to roughly three lines, but preserve any condition or uncertainty needed to keep the meaning correct. Do not remove a critical exception merely to satisfy the line target.
