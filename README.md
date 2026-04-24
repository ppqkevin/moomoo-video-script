# moomoo-video-script

moomoo証券（日本）の動画広告脚本を自動生成する Claude Code Skill。

30〜35秒の動画広告を対象に、**社内コンプラチェック用広告文テーブル**と**脚本テーブル（8列）**を生成し、飛書クラウドドキュメントとして出力します。

---

## 機能

- 広告投放渠道・目標人群・行情背景の3入力から脚本を自動生成
- 日証協ガイドライン準拠（断定的・射幸的表現の自動チェック）
- 場面別 disclaimer 自動付与（比較広告・第三者ロゴ・機能紹介・商品別）
- 飛書クラウドドキュメントへの自動出力

---

## インストール

### 方法1：npx skills（推奨）

```bash
npx skills install github:<owner>/moomoo-video-script -g
```

### 方法2：手動インストール

```bash
git clone https://github.com/<owner>/moomoo-video-script.git \
  ~/.claude/skills/moomoo-video-script
```

> Windows の場合：`~/.claude/skills/` は `C:\Users\<ユーザー名>\.claude\skills\` に相当します。

---

## 前提条件

- [Claude Code](https://claude.ai/claude-code) がインストール済みであること
- 飛書ドキュメント作成には [lark-cli](https://www.npmjs.com/package/@futu/ft-lark-cli) の認証設定が必要です

```bash
npm install -g @futu/ft-lark-cli
lark-cli auth login
```

---

## 使い方

Claude Code のチャットで以下のいずれかを入力するとスキルが起動します：

```
脚本を生成して
moomooの広告を書いて
生成视频文案
帮我写广告脚本
```

起動後、3つの入力ウィンドウが表示されます：

| 入力項目 | 例 |
|---|---|
| 広告投放渠道 | Google/YouTube、Yahoo! など |
| 投放目標人群 | 米株初心者、米株進階/高頻取引層 など |
| 行情背景・故事線 | 市場背景・訴求したい機能・ストーリーの方向性 |

---

## ファイル構成

```
moomoo-video-script/
├── SKILL.md                    # スキル定義（Router）
├── references/
│   ├── workflow.md             # Phase 1-6 生成ワークフロー
│   └── disclaimer.md          # 場面別免責文ライブラリ
└── build/                      # 設計アーティファクト（参考用）
    ├── examples.md
    ├── domain-research.md
    ├── red-lines-and-criteria.md
    ├── constraint-enforcement-plan.md
    ├── token-architecture.md
    └── resource-plan.md
```

---

## 出力形式

### 社内コンプラチェック用広告文

| 見出し｜文字数(半角30) | 説明文（半角90） |
|---|---|
| 見出し案 × 2バリエーション | 各見出しに対応する説明文 |

### 脚本テーブル（8列）

`画面（中文）/ 时长 / 中文 script / JP-script / VO / 【平假名】/ screenshot / disclaimer`
