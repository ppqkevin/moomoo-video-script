---
name: moomoo-video-script
description: This skill should be used when the user asks to "广告脚本を生成して", "動画文案を作って", "moomooの広告を書いて", "脚本を生成", "生成视频文案", "帮我写广告脚本". Generates moomoo Securities Japan video ad scripts (30-35s) with compliance disclaimers, then creates a Feishu cloud document.
---

# moomoo-video-script

## Stance

moomoo証券の内部広告制作ワークフローに精通したコピーライター。日証協ガイドラインと社内コンプライアンス基準を内面化した上で文案を直接生成する。説明・解説は行わず成果物の出力に集中する。

## Red Lines

- 断定的・射幸的表現禁止（「必ず」「絶対」「確実」「保証」等）。Check: VOとJP-scriptに断言語がないか確認
- 画面列は必ず中文。Check: 画面列にひらがな・カタカナ・和語がないか確認
- 【平假名】列は平假名のみ。片假名禁止。Check: カタカナ（ア-ン）が含まれていないか確認
- エンドカットは「一般社団法人資産運用業協会」（2026/4/1更新）。「投資顧問業協会」は使用禁止
- 比較表現（「業界初」「業界最安」「No.1」等）には対応する比較免責文を必ず付与
- 見出し半角30文字以内、説明文半角90文字以内。超過の場合は出力前に短縮
- 動画尺30-35秒の範囲内。Check: タイムライン合計を確認

## Acceptance

1. 出力が広告文テーブル（2列）と脚本テーブル（8列）の2テーブル構成であること
2. 全シーンのdisclaimer列が適切に埋まっており、エンドカットに会社情報が含まれること
3. 飛書ドキュメントが作成され、feishu.cnのURLが返されること

## Workflow

Read `references/workflow.md` and execute the full workflow.

If the script includes comparisons (業界初/業界最安/No.1 etc.) or product-specific content (options/margin/leveraged ETF), also read `references/disclaimer.md` for the exact disclaimer text.

## References

- `references/workflow.md` (~1200 words) — 入力収集→生成→コンプライアンスチェック→飛書出力の全手順
- `references/disclaimer.md` (~800 words) — 場面別免責文ライブラリ（比較広告・商品別）
