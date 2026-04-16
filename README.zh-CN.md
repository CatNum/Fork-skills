> **说明：** 本仓库包含 Anthropic 为 Claude 编写的 skills 实现。关于 Agent Skills 标准，请参阅 [agentskills.io](http://agentskills.io)。

# Skills（技能）

Skill 是由说明、脚本和资源组成的目录，Claude 会按需动态加载它们，以提升其在特定任务上的表现。Skill 可以教会 Claude 以可重复的方式完成某类任务，无论是根据你公司的品牌规范创建文档、按照你们组织特定的工作流分析数据，还是自动化个人任务。

更多信息请参阅：
- [什么是 skills？](https://support.claude.com/en/articles/12512176-what-are-skills)
- [在 Claude 中使用 skills](https://support.claude.com/en/articles/12512180-using-skills-in-claude)
- [如何创建自定义 skills](https://support.claude.com/en/articles/12512198-creating-custom-skills)
- [用 Agent Skills 让智能体更好地适应真实世界](https://anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills)

# 关于本仓库

本仓库包含一组 skill，用于展示 Claude skills 系统可以实现哪些能力。这些 skill 覆盖了从创意类应用（艺术、音乐、设计）到技术类任务（网页应用测试、MCP 服务器生成），再到企业工作流（沟通、品牌等）的多个方向。

每个 skill 都是一个独立目录，其中包含一个 `SKILL.md` 文件，文件内含 Claude 使用的说明和元数据。你可以浏览这些 skill，从中获得创建自己 skill 的灵感，或了解不同的实现模式与设计思路。

本仓库中的许多 skill 采用开源许可证（Apache 2.0）。此外，我们还提供了支撑 [Claude 文档创建能力](https://www.anthropic.com/news/create-files) 的文档创建与编辑 skill 源码，位于 [`skills/docx`](./skills/docx)、[`skills/pdf`](./skills/pdf)、[`skills/pptx`](./skills/pptx) 和 [`skills/xlsx`](./skills/xlsx) 子目录中。这些内容属于“可获取源码（source-available）”而非开源，但我们仍希望将其分享给开发者，作为在生产级 AI 应用中实际使用的复杂 skill 参考示例。

## 免责声明

**这些 skill 仅用于演示和教学目的。** 尽管其中一些能力可能也可在 Claude 中使用，但你在 Claude 中实际获得的实现方式和行为，可能与这些 skill 中展示的内容不同。这些 skill 旨在帮助你理解模式与可能性。在你自己的环境中依赖这些 skill 执行关键任务前，请务必进行充分测试。

## 本 Fork 的 Skills

### 自研新增

| 序号 | Skill | 简介 | 路径 |
| --- | --- | --- | --- |
| 1 | `ai-native-standard-flow` | 面向零代码开发的 AI Native 标准协作流程，覆盖流程定义、必备产物以及 AI 驱动的进度推进。 | [`skills/ai-native-standard-flow`](./skills/ai-native-standard-flow) |
| 2 | `design-changelog-maintainer` | 按项目作用域维护 `design.md`、`changelog.md` 与 `resume-interview.md` 的设计与变更日志技能。 | [`skills/design-changelog-maintainer`](./skills/design-changelog-maintainer) |
| 3 | `md-formatting` | 将 Markdown 文档规范化为统一结构，并增加“重点”区块，便于阅读和信息提取。 | [`skills/md-formatting`](./skills/md-formatting) |
| 4 | `skill-update-assistant` | 在修改 skill 时先做结构与迭代质量审核，再辅助收尾同步与变更记录。 | [`skills/skill-update-assistant`](./skills/skill-update-assistant) |
| 5 | `transcript-refine` | 将课程/视频转写稿整理为结构化学习材料，并补充了更严格的引用与输出规则。 | [`skills/transcript-refine`](./skills/transcript-refine) |

### 定制更新

| 序号 | Skill | 简介 | 路径 |
| --- | --- | --- | --- |
| 1 | `skill-creator` | 做过中文适配，补充了 `SKILL.md` 的双语表头说明。 | [`skills/skill-creator`](./skills/skill-creator) |

# Skill 集合
- [./skills](./skills)：Creative & Design、Development & Technical、Enterprise & Communication 以及 Document Skills 的示例 skill
- [./spec](./spec)：Agent Skills 规范
- [./template](./template)：skill 模板

# 在 Claude Code、Claude.ai 和 API 中试用

## Claude Code

你可以在 Claude Code 中运行以下命令，将本仓库注册为 Claude Code 插件市场：

```bash
/plugin marketplace add anthropics/skills
```

随后，安装某一组 skill：
1. 选择 `Browse and install plugins`
2. 选择 `anthropic-agent-skills`
3. 选择 `document-skills` 或 `example-skills`
4. 选择 `Install now`

也可以直接通过命令安装任一插件：

```bash
/plugin install document-skills@anthropic-agent-skills
/plugin install example-skills@anthropic-agent-skills
```

安装插件后，你只需在对话中提到对应 skill 即可使用。例如，如果你从 marketplace 安装了 `document-skills` 插件，可以让 Claude Code 执行类似这样的任务：

“使用 PDF skill 从 `path/to/some-file.pdf` 中提取表单字段。”

## Claude.ai

这些示例 skill 已经面向 Claude.ai 的付费方案提供。

如果你想使用本仓库中的任意 skill，或上传自定义 skill，请参阅 [在 Claude 中使用 skills](https://support.claude.com/en/articles/12512180-using-skills-in-claude#h_a4222fa77b) 中的说明。

## Claude API

你可以通过 Claude API 使用 Anthropic 预构建的 skill，也可以上传自定义 skill。详见 [Skills API Quickstart](https://docs.claude.com/en/api/skills-guide#creating-a-skill)。

# 创建一个基础 skill

Skill 的创建非常简单——只需要一个目录，里面放一个包含 YAML frontmatter 和说明内容的 `SKILL.md` 文件即可。你可以使用本仓库中的 **template-skill** 作为起点：

```markdown
---
name: my-skill-name
description: A clear description of what this skill does and when to use it
---

# My Skill Name

[Add your instructions here that Claude will follow when this skill is active]

## Examples
- Example usage 1
- Example usage 2

## Guidelines
- Guideline 1
- Guideline 2
```

frontmatter 只要求两个字段：
- `name`：skill 的唯一标识符（小写，空格用连字符表示）
- `description`：对 skill 功能及适用场景的完整描述

下方的 Markdown 正文中可以写入说明、示例和规则，Claude 在 skill 激活时会遵循这些内容。更多细节请参阅 [如何创建自定义 skills](https://support.claude.com/en/articles/12512198-creating-custom-skills)。

# 合作伙伴 skills

Skill 是让 Claude 更擅长使用特定软件的一种非常好的方式。当我们看到合作伙伴提供了非常出色的示例 skill 时，也可能会在这里进行展示：

- **Notion** - [Notion Skills for Claude](https://www.notion.so/notiondevs/Notion-Skills-for-Claude-28da4445d27180c7af1df7d8615723d0)
