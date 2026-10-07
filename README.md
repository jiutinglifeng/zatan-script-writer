# zatan-script-writer

杂谈类视频的口播逐字稿写作和视频脚本拆分 skill。适用于经济、产业、社会、历史等话题的横屏中长视频。

一句话定位：**一个普通人顺着一个直觉往下想，边查边改主意，把想明白的过程讲给你听。**

---

## 能做什么

| 活 | 产出 |
|---|---|
| 从大纲写逐字稿 | 按段编号的口播正文，段末附内部标注（事实标签、来源编号、假设说明） |
| 改已有的逐字稿 | 修改后的段落，加五层质检报告 |
| 把定稿逐字稿拆成视频脚本 | 分镜表：口播、画面类型、画面说明、上屏数字、字幕关键词、来源、素材难度和负责人 |

不用于：公众号或图文长文、60 秒以内的短视频文案、语音转写稿校对。

## 怎么触发

在 Claude Code 里说这些话就会用上：写口播稿、写逐字稿、写稿、改稿、出稿、杂谈视频、视频文案、视频脚本、分镜表、拆分镜、口播。

也可以直接输入 `/zatan-script-writer`。

## 目录

```
zatan-script-writer/
├── README.md                    本文件，给人看的说明
├── LICENSE                      本 skill 的 MIT 许可证
├── LICENSE-khazix-skills        原版 khazix-writer 的 MIT 许可声明
├── SKILL.md                     主流程，Claude 每次都会读
└── references/                  细则，Claude 按需读
    ├── spoken-style.md          口播文风：听感规则、口语表达、网络梗边界、比喻、禁用词、改写对照
    ├── fact-discipline.md       事实纪律：四类标签、来源、口径陷阱、数字念法、时效复查、中立
    ├── video-script-format.md   分镜表模板、画面类型、数据图设计规则、素材难度
    ├── self-check.md            五层自检、视频脚本专项检查、质检报告模板
    └── style-samples.md         用户本人的风格样本
```

## 核心规则一览

- **叙事骨架**：一个直觉 → 出现矛盾 → 推一步 → 又出现新矛盾 → 落到一个更大的问题。不写知识点罗列。
- **核心手法**：亲自去查，查完改了主意（「我一开始以为……后来一查发现……」）。必须是真的改口，一期三四处为限。
- **事实分层**：FACT / INFERENCE / HYPOTHESIS / USER VIEW 分开标。数字只从项目的核实表里拿，没核实的写「【待核实】」。
- **写给耳朵听**：逗号之间一口气能念完；口播每段念的关键数字不超过两个，其余放到画面上。
- **语气**：可以玩梗、自嘲，不带粗口；比喻只用用户自己提出的；不替用户下确定结论。
- **用户定稿是标准答案**：自检规则误判用户定稿时，改规则，不改定稿。

## 配合项目文件使用

skill 是通用的，不写死某一期视频的内容。每期专属的材料放在项目里，skill 会在开工前去找：

- 项目说明（CLAUDE.md、PROJECT_PLAN 等）
- 叙事方案或大纲
- 用户观点文件
- 事实核实表和来源总表
- 大白话对照表

没有这些文件也能用，但 Claude 会先问你要，或者把数字留成「【待核实】」。

## 安装到别的项目

仓库地址：https://github.com/jiutinglifeng/zatan-script-writer

把仓库克隆到下面任一位置：

- **只给某个项目用**：那个项目的 `.claude/skills/zatan-script-writer/`
- **所有项目都能用**：`~/.claude/skills/zatan-script-writer/`

```bash
git clone https://github.com/jiutinglifeng/zatan-script-writer.git ~/.claude/skills/zatan-script-writer
```

克隆后重开 Claude Code 会话即可生效。

## 维护

- **补样本。** 有新定稿的段落，或者录音后校对过的转写稿，加进 `references/style-samples.md`，注明出处、日期和能看出的特点。录音转写稿最能代表真实的说话方式，有了要优先补。同时记下实际语速，替换 SKILL.md 里每分钟 225 字的估算。
- **改规则。** 规则和用户定稿冲突时，改规则。改完拿已有的定稿段落再跑一遍自检，确认不会误判。
- **加反例。** 用户明确否决过的写法，可以作为反例放进 `style-samples.md` 或 `spoken-style.md` 的改写对照。

## 来源和版本

改写自卡兹克（Khazix）的公众号写作 skill `khazix-writer`（GitHub：`KKKKhazix/khazix-skills`）。保留了原版的人机分工、禁用词表、扣主线句、分层自检框架；去掉了卡兹克个人人设、公众号格式、粗口和口癖、文化升维和 AI 生成比喻；新增了听感规则、事实纪律、数字念法、视频脚本拆分。

原作品以 MIT 许可证发布，原版权声明和许可声明见 [LICENSE-khazix-skills](LICENSE-khazix-skills)。

本 skill 同样以 MIT 许可证发布，见 [LICENSE](LICENSE)。

| 日期 | 变更 |
|---|---|
| 2026-10-07 | 初版。拿 global-economy-video 项目的 S00 定稿试跑自检，放宽两条规则：开头允许车价、工资这类生活数字；段尾可以用陈述句把观众推向下一段 |
