# Build: Token Architecture

## Layer Budget

| Layer | File | Content | Target |
|---|---|---|---|
| 0: Metadata | SKILL.md frontmatter | name + description | ≤100 words |
| 1: Router | SKILL.md body | Stance, red lines, workflow routing | ≤600 words |
| 2: Workflow | references/workflow.md | Step-by-step generation + Feishu export | ≤1800 words |
| 3: Reference | references/disclaimer.md | 免責文ライブラリ（場面別） | On-demand only |

## Decisions

1. **Sub-commands不要** — 単一ワークフロー（入力→生成→出力）のみ
2. **免責ライブラリはLayer 3** — 毎回全量ロードは不要。生成時に参照が必要な場合のみ読み込む
3. **フォーマット定義はworkflow.mdに内包** — テーブル構造はシンプルなので別ファイル化しない

## Token Declarations (SKILL.md内のポインタ)

- `references/workflow.md` (~1200 words) — メイン生成ワークフロー（常時ロード）
- `references/disclaimer.md` (~800 words) — 免責文ライブラリ（比較表現・商品訴求時にロード）
