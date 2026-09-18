# 怎样开会 (how-to-run-meetings)

> 从《怎样开会》（任仲然著，党建读物出版社，"机关工作实务丛书"第一本）提炼的 Agent 技能库——不是书的摘要，而是一套可执行的会议方法论工具箱。

## 这是什么

一个 OpenClaw / Claude Code / Copilot CLI / Amp 兼容的 skill 目录，把全书十五讲的会议方法论拆解为：

- **命名框架与原则**——保留作者原话表述
- **可执行的操作步骤**——每讲的方法都写成"何时用 / 怎么做"
- **反面模式**——作者反复警示的错误做法及原因
- **实例拆解**——书中经典案例的压缩重述
- **决策速查表**——把作者的判断逻辑浓缩成一眼可查的规则

双用途设计：

1. **给 AI 用**——筹备会议、主持会议、写讲话稿、做会议纪要、抓会议精神落实等任务，按本 skill 的方法论干活
2. **给自己用**——按讲次或主题快速检索书中观点与方法

## 安装

**方式一 · Agent Skills 标准（推荐）**

```bash
npx skills add yxdwind/how-to-run-meetings -g
```

**方式二 · 安装脚本（自动探测 Claude Code / OpenClaw / Codex / Cursor / Cline 等已装目录）**

```powershell
# Windows PowerShell
irm https://raw.githubusercontent.com/yxdwind/how-to-run-meetings/main/install.ps1 | iex
```

```bash
# macOS / Linux
curl -fsSL https://raw.githubusercontent.com/yxdwind/how-to-run-meetings/main/install.sh | bash
```

**方式三 · 手动**

```bash
git clone https://github.com/yxdwind/how-to-run-meetings.git
# 把仓库目录（含 SKILL.md）复制到你的 AI 技能目录，
# 如 ~/.agents/skills/how-to-run-meetings 或 ~/.claude/skills/how-to-run-meetings
```

更新已装的 skill：`npx skills update how-to-run-meetings`，或重跑安装脚本（加 -Force/--force 覆盖）。

## 使用案例

一句话调用示例（完整实战见 [examples/](examples/) 目录）：

| 你说 | AI 会做什么 |
|------|------------|
| "两周后开跨部门部署会，任务清单附后，帮我筹备" | 议程筐→议题把关→规模控制→通知与会前检查清单（[案例1](examples/example-1-deployment-meeting-prep.md)） |
| "明天主持方案评审会，两个团队对立+有大佬跑题" | 虎头熊腰豹尾+控场速查卡+两个变成（[案例2](examples/example-2-chairing-discussion.md)） |
| "开决策会拍'是否自建数据平台'，正反都有硬理由" | 议题成熟度检查+一个制度三个规矩+交换比较反复（[案例3](examples/example-3-decision-meeting.md)） |
| "开两场座谈会听真话，别让满意代表垄断" | 三个怎样+示弱求真话+三类人都请+反馈闭环（[案例4](examples/example-4-symposium-design.md)） |
| "公司要来我这开现场会，怎么防盆景秀" | 只看新典型+以面验点+交叉抽查+材料红线（[案例5](examples/example-5-onsite-meeting.md)） |
| "大会昨天开完，6 项任务怎么抓落地" | 两个90%+事项项目化+刚性时限+视频调度会（[案例6](examples/example-6-implementation.md)） |

## 目录结构

```
how-to-run-meetings/
├── SKILL.md              # 核心框架 + 讲次索引 + 主题索引（入口文件）
├── chapters/             # 十五讲逐章拆解（按需加载）
│   ├── ch01-why-meetings.md              # 第一讲 为什么开会
│   ├── ch02-meeting-preparation.md       # 第二讲 会议的筹备
│   ├── ch03-chairing-meetings.md         # 第三讲 如何主持会议
│   ├── ch04-speech-drafting.md           # 第四讲 讲话稿的写法
│   ├── ch05-meeting-speeches.md          # 第五讲 如何做会议讲话
│   ├── ch06-learn-not-blindly-follow.md  # 第六讲 可借鉴不可盲从
│   ├── ch07-decision-meetings.md         # 第七讲 决策会
│   ├── ch08-summary-deployment-meetings.md # 第八讲 总结部署会
│   ├── ch09-problem-solving-meetings.md  # 第九讲 解决问题的会
│   ├── ch10-study-meetings.md            # 第十讲 学习会
│   ├── ch11-symposiums.md                # 第十一讲 座谈会
│   ├── ch12-onsite-meetings.md           # 第十二讲 现场会
│   ├── ch13-video-phone-meetings.md      # 第十三讲 视频会和手机会
│   ├── ch14-meeting-publicity.md         # 第十四讲 会议的宣传
│   └── ch15-implementing-meeting-spirit.md # 第十五讲 会议精神的落实
├── examples/             # 六个完整实战案例（筹备/主持/决策/座谈/现场/落实）
├── glossary.md           # 全书术语表
├── patterns.md           # 方法与模式全集
├── cheatsheet.md         # 决策速查表（最实用的一层）
├── overview.html         # 可视化总览页
└── README.md
```

## 用法

**Agent 里**（OpenClaw / Claude Code 等，将本目录放入技能目录后）：

- 直接说"用怎样开会这个 skill 筹备一场工作部署会"→ 加载核心框架
- 问具体主题，如"主持座谈会有什么技巧"→ 自动定位到对应讲次细读
- 问"ch03"→ 加载第三讲（如何主持会议）

**人读**：从 [SKILL.md](SKILL.md) 的索引进入，按需点开各讲。

## 生成方式

由 OpenClaw book-to-skill 流水线生成：196 页扫描版 PDF → OCR 全文提取（AutoClaw OCR）→ 结构分析 → 逐章提炼 → 安全扫描。提炼遵循"提取结构，不抄原文"原则，框架命名保留作者原话。

## 机关工作实务四部曲

- how-to-run-meetings（本仓库）—— 《怎样开会》（任仲然）
- [how-to-research](https://github.com/yxdwind/how-to-research) —— 《怎样调研》（任仲然）
- [how-to-write](https://github.com/yxdwind/how-to-write) —— 《怎样写作》（任仲然）
- [smart-notes](https://github.com/yxdwind/smart-notes) —— 《卡片笔记写作法》（申克·阿伦斯）

## 版权说明

本书版权归原作者及出版社（党建读物出版社）所有。本仓库仅包含对书中方法论的提炼与转述（合理使用），不包含原文文本。
