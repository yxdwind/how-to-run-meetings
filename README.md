# 怎样开会 (how-to-run-meetings)

![Release](https://img.shields.io/github/v/release/yxdwind/how-to-run-meetings) ![License](https://img.shields.io/github/license/yxdwind/how-to-run-meetings) ![Agent Skills](https://img.shields.io/badge/Agent-Skills-blue)

> 从《怎样开会》（任仲然著，党建读物出版社，"机关工作实务丛书"第一本）提炼的 Agent 技能库——不是书的摘要，而是一套"方法论 + 工序 + 模板自检 + 评测"的可执行办会系统。

## 这是什么

一个符合 Agent Skills 标准、跨工具兼容的 skill 目录（Claude Code / OpenClaw / Codex / Cursor / Cline / CodeBuddy / ZCode 等；安装脚本自动探测，其余工具手动复制 SKILL.md 目录即可）。四层结构：

**方法论层**（全书十五讲拆解）

- **命名框架与原则**——保留作者原话表述
- **可执行的操作步骤**——每讲的方法都写成"何时用 / 怎么做"
- **反面模式**——作者反复警示的错误做法及原因
- **实例拆解**——书中经典案例的压缩重述
- **决策速查表**——把作者的判断逻辑浓缩成一眼可查的规则

**工序层**（强制办会工序）

- 办会任务五步走：**接会问诊 → 会前筹备 → 会中执行 → 会后收口 → 落实验收**（落地原书"不开无筹备之会""民主与集中缺一不可""研究怎样开会，必须研究怎样落实"）
- 红线：议题先过"权限+必要性"两把尺、议程定后不轻改、该定的必须有权威说法、决议必须带落实载体——禁止无依据补记与编造

**模板与自检层**

- **6 张操作模板**——议程筐、通知、主持提纲卡、决策会程序、会议纪要、落实台账，会前会后直接填用
- **5 张交付前自检筛**——通用筛 12 项（必要性筹备/民主集中/决议落实）+ 筹备、主持、临场讲话、纪要与落实四张专项筛，逐项过筛再交付

**评测层**（基准评测，防退化）

- 任务简报 + 硬指标/盲评评分表 + 跑分全记录；改 skill 后跑回归（首轮已跑，见 [evals/runs.log.md](evals/runs.log.md)）

双用途设计：

1. **给 AI 用**——筹备会议、主持会议、临场讲话、写会议纪要、抓会议精神落实等任务，按本 skill 的工序和方法论干活
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

更新已装的 skill：`npx skills update how-to-run-meetings`，或重跑安装脚本（加 -Force/--force 覆盖）。固定版本下载见 [Releases](https://github.com/yxdwind/how-to-run-meetings/releases)。

## 使用案例

一句话调用示例（完整实战见 [examples/](examples/) 目录）：

| 你说 | AI 会做什么 |
|------|------------|
| "两周后开跨部门部署会，任务清单附后，帮我筹备" | 议程筐→议题把关→规模控制→通知与会前检查清单（[案例1](examples/example-1-deployment-meeting-prep.md)） |
| "明天主持方案评审会，两个团队对立+有大佬跑题" | 虎头熊腰豹尾+控场速查卡+两个变成（[案例2](examples/example-2-chairing-discussion.md)） |
| "开决策会拍'是否自建数据平台'，正反都有硬理由" | 议题四种可能+一个制度三个规矩+头脑风暴（[案例3](examples/example-3-decision-meeting.md)） |
| "开两场座谈会听真话，别让满意代表垄断" | 三个怎样+示弱求真话+三类人都请+反馈闭环（[案例4](examples/example-4-symposium-design.md)） |
| "公司要来我这开现场会，怎么防盆景秀" | 只看新典型+以面验点+交叉抽查+材料红线（[案例5](examples/example-5-onsite-meeting.md)） |
| "大会昨天开完，6 项任务怎么抓落地" | 两个90%+事项项目化+刚性时限+视频调度会（[案例6](examples/example-6-implementation.md)） |

## 目录结构

```
how-to-run-meetings/
├── SKILL.md              # 核心框架 + 办会工序入口 + 讲次索引 + 主题索引（入口文件）
├── workflow.md           # 办会工序：五步走（问诊→筹备→执行→收口→落实）执行细则与红线
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
├── templates/            # 操作模板（会前会后直接填用）
│   ├── agenda.md              # 议程筐：主题+议程程序+议题把关+会前检查
│   ├── notice.md              # 会议通知：写清起止时间的字段纪律
│   ├── host-card.md           # 主持提纲卡：虎头熊腰豹尾+插曲处置预案
│   ├── decision-procedure.md  # 决策会程序：议题成熟度+三个规矩+决策记录
│   ├── minutes.md             # 会议纪要：决议三要素+口径规则
│   └── implementation-ledger.md # 落实台账：事项+项目+刚性时限+督查节奏
├── rubrics/              # 交付前自检筛（交付前逐项过筛）
│   ├── general.md                 # 通用筛 12 项：必要性筹备/民主集中/决议落实
│   ├── preparation.md             # 筹备筛 11 项
│   ├── chairing.md                # 主持筛 9 项
│   ├── speech.md                  # 临场讲话筛 10 项（成文深度起草归 how-to-write）
│   └── minutes-implementation.md  # 纪要与落实筛 13 项
├── evals/                # 基准评测（改 skill 后跑回归）
│   ├── README.md                # 评测方法与判定规则
│   ├── scoring.md               # 评分表：硬指标 60 + 软评 40 + 双轨分解
│   ├── briefs/                  # 任务简报（3 个场景）
│   │   └── runs.log.md              # 跑分记录（两轮 3 简报）
├── examples/             # 六个完整实战案例（筹备/主持/决策/座谈/现场/落实）
├── glossary.md           # 全书术语表
├── patterns.md           # 方法与模式全集
├── cheatsheet.md         # 决策速查表（当…就…判断规则+阈值+危险信号）
├── overview.html         # 可视化总览页
├── install.sh            # macOS / Linux 安装脚本（自动探测技能目录）
├── install.ps1           # Windows PowerShell 安装脚本
└── README.md
```

## 用法

**Agent 里**（OpenClaw / Claude Code 等，将本目录放入技能目录后）：

- 直接说"用怎样开会这个 skill 筹备一场工作部署会"→ 走五步工序：先问清类型目标参会人 → 给筹备方案 → 末尾附自检报告
- 问具体主题，如"主持座谈会有什么技巧"→ 自动定位到对应讲次细读
- 问"ch03"→ 加载第三讲（如何主持会议）

**人读**：从 [SKILL.md](SKILL.md) 的索引进入，按需点开各讲。

## 生成方式

由 OpenClaw book-to-skill 流水线生成：196 页扫描版 PDF → OCR 全文提取（AutoClaw OCR）→ 结构分析 → 逐章提炼 → 安全扫描。提炼遵循"提取结构，不抄原文"原则，框架命名保留作者原话。

## 生成方式

方法论层由 OpenClaw book-to-skill 流水线生成：196 页扫描版 PDF → OCR 全文提取（AutoClaw OCR）→ 结构分析 → 逐章提炼 → 安全扫描。提炼遵循"提取结构，不抄原文"原则，框架命名保留作者原话。

工序、模板、自检筛、评测为 v1.1 质量工程阶段增设（架构对齐 how-to-write）：三层设计对应办会质量的三类瓶颈——只给规则不给工序则流程失控（该筹备的不筹备、该落实的不落实），只给工序不给模板则产出各写各的，只交付不自检则夹带私货、含糊时限、一开了之无法拦截。

## 质量与评测

仓库内置了一套基准评测（[evals/](evals/)）：同一任务简报分别用"带本 skill"与"不带"两种方式生成，按硬指标打分（溯源、议程程序、时限刚性），改 skill 后跑回归。已跑三轮回归（3 简报全覆盖），带 skill 卷 95.4/89.4/95.4 分对基线 33.4/52.4/50.4 分全部判「有效」；基线卷在首轮触发"素材外编造"一票否决，盲评流程的匿名化缺陷与整改见 [runs.log.md](evals/runs.log.md) 完整性注记与 [AUDIT_V1.1.md](AUDIT_V1.1.md)。诚实口径：单样本只作流程验证，"装了平均好多少"的量化结论待简报库扩充后再下。

**版权与忠实度**：三线审计（通用体检 + 原书忠实度 + 发布就绪）完成，15 章对原书覆盖度 75%–90%，与原书最长公共子串 47 字（带引号对话引语，单句级），无段落级抄录；详见 [AUDIT_REPORT.md](AUDIT_REPORT.md)（含修复执行记录）。

## 相关技能

**机关工作实务丛书**（任仲然）三部曲：

- how-to-run-meetings（本仓库） —— 《怎样开会》
- [how-to-research](https://github.com/yxdwind/how-to-research) —— 《怎样调研》
- [how-to-write](https://github.com/yxdwind/how-to-write) —— 《怎样写作》

延伸阅读：

- [smart-notes](https://github.com/yxdwind/smart-notes) —— 《卡片笔记写作法》（申克·阿伦斯）提炼的卡片笔记方法论技能

## 许可证与版权

本仓库的代码与文档以 [MIT License](LICENSE) 发布。

《怎样开会》一书版权归原作者及出版社（党建读物出版社）所有。本仓库仅包含对书中方法论的提炼与转述（合理使用），不包含原文文本；案例与数字为压缩转述，未逐字核对原书，引用请以原著为准。
