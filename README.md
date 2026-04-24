# moomoo-video-script

moomoo证券（日本）视频广告脚本自动生成 Claude Code Skill。

针对30〜35秒视频广告，自动生成**合规审查用广告文案表格**和**脚本表格（8列）**，并输出为飞书云文档。

---

## 功能

- 根据广告投放渠道、目标人群、行情背景3个输入自动生成脚本
- 符合日本证券业协会（日証協）合规要求（自动检查断言性/射幸性表现）
- 按场景自动附加免责声明（比较广告、第三方Logo、功能介绍、商品别）
- 自动输出为飞书云文档

---

## 安装

### 方式1：npx skills（推荐）

```bash
npx skills install github:ppqkevin/moomoo-video-script -g
```

### 方式2：手动安装

```bash
# Mac / Linux
git clone https://github.com/ppqkevin/moomoo-video-script.git \
  ~/.claude/skills/moomoo-video-script

# Windows
git clone https://github.com/ppqkevin/moomoo-video-script.git ^
  %USERPROFILE%\.claude\skills\moomoo-video-script
```

---

## 前置条件

- 已安装 [Claude Code](https://claude.ai/claude-code)
- 生成飞书文档需要配置 [lark-cli](https://www.npmjs.com/package/@futu/ft-lark-cli) 认证

```bash
npm install -g @futu/ft-lark-cli
lark-cli auth login
```

---

## 使用方法

在 Claude Code 对话框中输入以下任意触发词即可启动：

```
生成视频文案
帮我写广告脚本
脚本を生成
moomooの広告を書いて
```

启动后会弹出3个输入窗口：

| 输入项 | 示例 |
|---|---|
| 广告投放渠道 | Google/YouTube、Yahoo! 等 |
| 投放目标人群 | 米股初心者、米股进阶/高频交易层 等 |
| 行情背景及故事线 | 市场背景、主打功能、故事方向 |

---

## 文件结构

```
moomoo-video-script/
├── SKILL.md                    # Skill 定义（Router）
├── references/
│   ├── workflow.md             # Phase 1-6 生成工作流
│   └── disclaimer.md          # 场景别免责声明库
└── build/                      # 设计文档（参考用）
    ├── examples.md
    ├── domain-research.md
    ├── red-lines-and-criteria.md
    ├── constraint-enforcement-plan.md
    ├── token-architecture.md
    └── resource-plan.md
```

---

## 输出格式

### 合规审查用广告文案

| 见出し｜文字数(半角30) | 説明文（半角90） |
|---|---|
| 2个标题方案 | 每个标题对应的说明文 |

### 脚本表格（8列）

`画面（中文）/ 时长 / 中文 script / JP-script / VO / 【平假名】/ screenshot / disclaimer`
