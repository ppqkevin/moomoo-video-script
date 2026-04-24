# Build: Resource Plan

| Resource | Type | Used In | Justification |
|---|---|---|---|
| references/workflow.md | Reference (Layer 2) | 全実行 | Step-by-step生成手順。毎回必要 |
| references/disclaimer.md | Reference (Layer 3) | 比較表現・商品訴求時 | 60種の免責文。全量常時ロードは重いためon-demand |

## Audit

- **scripts/不要**: 文字数カウント等はLLMが直接実行可能。外部スクリプト不要
- **assets/不要**: テンプレート画像等なし
- **既存skill活用**: 飛書ドキュメント作成は `lark-doc` skillに委譲。独自実装しない
