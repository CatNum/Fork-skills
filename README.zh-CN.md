<br/>
<br/>
<br/>
<p align="center"><a href="./README.md">English</a> | <a href="./README.zh-CN.md">简体中文</a></p>

> **说明：** 本仓库是 Anthropic Agent Skills 示例仓库的 fork。关于 Agent Skills 标准，请参阅 [agentskills.io](http://agentskills.io)。

# Skills（技能）

## 重点

- **仓库定位**：本仓库收集 Agent Skills，将说明、脚本、参考资料和资源封装成可复用的任务能力。
- **Fork 增量**：本 fork 在原始示例与文档技能基础上，新增了协作流程、文档维护、Markdown 格式化、skill 更新、项目模拟面试和面试复盘等技能。
- **当前入口**：每个 skill 都位于 `skills/<skill-name>/SKILL.md`，并可按需携带 `references/`、`scripts/`、`assets/` 或 `project-docs/` 等资源目录。
- **插件分组**：本地 Claude 插件市场当前暴露 `document-skills`、`example-skills` 和 `claude-api` 三组插件。

## 一、Skills 简介

Skill 是由说明、脚本和资源组成的目录，Claude 会按需动态加载它们，以提升其在特定任务上的表现。Skill 可以教会 Claude 以可重复的方式完成某类任务，例如根据公司品牌规范创建文档、按照组织特定工作流分析数据，或自动化个人任务。

更多信息请参阅：

- [什么是 skills？](https://support.claude.com/en/articles/12512176-what-are-skills)
- [在 Claude 中使用 skills](https://support.claude.com/en/articles/12512180-using-skills-in-claude)
- [如何创建自定义 skills](https://support.claude.com/en/articles/12512198-creating-custom-skills)
- [用 Agent Skills 让智能体更好地适应真实世界](https://anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills)

## 二、关于本仓库

本仓库包含一组 skill，用于展示 Claude skills 系统可以实现哪些能力。这些 skill 覆盖了从创意类应用（艺术、设计）到技术类任务（网页应用测试、MCP 服务器生成），再到企业工作流（内部沟通、品牌规范等）的多个方向。

每个 skill 都是一个独立目录，其中包含一个 `SKILL.md` 文件，文件内含 Claude 使用的说明和元数据。你可以浏览这些 skill，从中获得创建自己 skill 的灵感，或了解不同的实现模式与设计思路。

本仓库中的许多 skill 采用 Apache 2.0 开源许可证。此外，我们还提供了支撑 [Claude 文档创建能力](https://www.anthropic.com/news/create-files) 的文档创建与编辑 skill 源码，位于 [`skills/docx`](./skills/docx)、[`skills/pdf`](./skills/pdf)、[`skills/pptx`](./skills/pptx) 和 [`skills/xlsx`](./skills/xlsx) 子目录中。这些内容属于“可获取源码（source-available）”而非开源，但仍可作为生产级 AI 应用中复杂 skill 的参考示例。

### 2.1 免责声明

**这些 skill 仅用于演示和教学目的。** 尽管其中一些能力可能也可在 Claude 中使用，但你在 Claude 中实际获得的实现方式和行为，可能与这些 skill 中展示的内容不同。这些 skill 旨在帮助你理解模式与可能性。在你自己的环境中依赖这些 skill 执行关键任务前，请务必进行充分测试。

## 三、本 Fork 的 Skills

### 3.1 自研新增

| 序号 | Skill | 简介 | 路径 |
|----| --- | --- | --- |
| 1  | `md-formatting` | 将 Markdown 文档规范化为统一结构，并增加“重点”区块，便于阅读和信息提取。 | [`skills/md-formatting`](./skills/md-formatting) |
| 2  | `interview-transcript-review` | 将真实模拟面试转写稿整理为面试后复盘文档，包含评分、面试官考点、回答方向分析、短板卡片以及 Markdown/HTML 输出。 | [`skills/interview-transcript-review`](./skills/interview-transcript-review) |
| 3  | `skill-update-assistant` | 对已有 skill 的变更方案做结构与迭代标准审核，并辅助完成同步和变更记录。 | [`skills/skill-update-assistant`](./skills/skill-update-assistant) |
| 4  | `transcript-refine` | 将长视频或直播课程转写稿整理为首次学习材料，支持阅读优化版和视频口播稿版。 | [`skills/transcript-refine`](./skills/transcript-refine) |

### 3.2 定制更新

| 序号 | Skill | 简介 | 路径 |
| --- | --- | --- | --- |
| 1 | `skill-creator` | 面向中文适配和 skill 创作流程做过定制，补充了 `SKILL.md` 的双语表头说明。 | [`skills/skill-creator`](./skills/skill-creator) |

## 四、当前 Skill 清单

### 4.1 文档类 Skills

| Skill | 简介 | 路径 |
| --- | --- | --- |
| `docx` | 创建、读取、编辑、批注、修订和校验 Word `.docx` 文件。 | [`skills/docx`](./skills/docx) |
| `pdf` | 读取、创建、检查、拆分、合并、填写、加密、OCR 和校验 PDF 文件。 | [`skills/pdf`](./skills/pdf) |
| `pptx` | 创建、读取、编辑、合并、校验和导出 PowerPoint `.pptx` 演示文稿。 | [`skills/pptx`](./skills/pptx) |
| `xlsx` | 创建、读取、编辑、清洗、重算和转换电子表格文件。 | [`skills/xlsx`](./skills/xlsx) |

### 4.2 示例与技术类 Skills

| Skill | 简介 | 路径 |
| --- | --- | --- |
| `algorithmic-art` | 使用 p5.js、种子随机数和交互参数创建原创生成艺术。 | [`skills/algorithmic-art`](./skills/algorithmic-art) |
| `brand-guidelines` | 将 Anthropic 官方品牌颜色和字体应用到视觉产物中。 | [`skills/brand-guidelines`](./skills/brand-guidelines) |
| `canvas-design` | 使用内置设计指南和字体，创建 PNG 与 PDF 静态视觉设计。 | [`skills/canvas-design`](./skills/canvas-design) |
| `doc-coauthoring` | 引导用户共同撰写文档、提案、技术规格和决策文档。 | [`skills/doc-coauthoring`](./skills/doc-coauthoring) |
| `frontend-design` | 构建具有设计质量的前端界面、页面、组件和 artifact。 | [`skills/frontend-design`](./skills/frontend-design) |
| `interview-transcript-review` | 将真实模拟面试转写稿生成 Markdown 或 HTML 复盘报告，包含评分、面试官考点、回答优化和短板卡片。 | [`skills/interview-transcript-review`](./skills/interview-transcript-review) |
| `internal-comms` | 撰写状态报告、领导层更新、公司新闻、FAQ 和事故更新等内部沟通内容。 | [`skills/internal-comms`](./skills/internal-comms) |
| `mcp-builder` | 指导使用 Python 或 Node/TypeScript 创建高质量 MCP 服务器。 | [`skills/mcp-builder`](./skills/mcp-builder) |
| `slack-gif-creator` | 创建符合 Slack 约束并经过校验的动画 GIF。 | [`skills/slack-gif-creator`](./skills/slack-gif-creator) |
| `theme-factory` | 为幻灯片、文档、报告、HTML 页面等产物应用预设或生成主题。 | [`skills/theme-factory`](./skills/theme-factory) |
| `web-artifacts-builder` | 使用 React、Tailwind CSS 和 shadcn/ui 构建复杂 Claude.ai HTML artifacts。 | [`skills/web-artifacts-builder`](./skills/web-artifacts-builder) |
| `webapp-testing` | 使用 Playwright 辅助工具与本地 Web 应用交互并进行测试。 | [`skills/webapp-testing`](./skills/webapp-testing) |

### 4.3 API 与模板类 Skills

| Skill | 简介 | 路径 |
| --- | --- | --- |
| `claude-api` | 提供 Claude API、Anthropic SDK 和 Agent SDK 在多语言中的使用指导。 | [`skills/claude-api`](./skills/claude-api) |
| `template-skill` | 提供创建新 skill 的基础模板。 | [`skills/template`](./skills/template) |

## 五、仓库结构

- [`skills`](./skills)：Creative & Design、Development & Technical、Enterprise & Communication、Fork 自研流程以及 Document Skills 的 skill 集合。
- [`spec`](./spec)：Agent Skills 规范。
- [`template`](./template)：skill 模板。
- [`.claude-plugin/marketplace.json`](./.claude-plugin/marketplace.json)：本地 Claude Code 插件市场定义。

## 六、在 Claude Code、Claude.ai 和 API 中试用

### 6.1 Claude Code

你可以在 Claude Code 中运行以下命令，将本仓库注册为 Claude Code 插件市场：

```text
/plugin marketplace add anthropics/skills
```

随后，安装某一组 skill：

1. 选择 `Browse and install plugins`。
2. 选择 `anthropic-agent-skills`。
3. 选择 `document-skills`、`example-skills` 或 `claude-api`。
4. 选择 `Install now`。

也可以直接通过命令安装插件：

```text
/plugin install document-skills@anthropic-agent-skills
/plugin install example-skills@anthropic-agent-skills
/plugin install claude-api@anthropic-agent-skills
```

安装插件后，你只需在对话中提到对应 skill 即可使用。例如，如果你从 marketplace 安装了 `document-skills` 插件，可以让 Claude Code 执行类似这样的任务：

“使用 PDF skill 从 `path/to/some-file.pdf` 中提取表单字段。”

### 6.2 本地 OpenSkills 用法

本 fork 也按本地 OpenSkills 使用方式组织。在仓库根目录读取某个 skill：

```bash
npx openskills read <skill-name>
```

读取多个 skill：

```bash
npx openskills read skill-one,skill-two
```

### 6.3 Claude.ai

原始示例 skill 已经面向 Claude.ai 的付费方案提供。

如果你想使用本仓库中的任意 skill，或上传自定义 skill，请参阅 [在 Claude 中使用 skills](https://support.claude.com/en/articles/12512180-using-skills-in-claude#h_a4222fa77b) 中的说明。

### 6.4 Claude API

你可以通过 Claude API 使用 Anthropic 预构建的 skill，也可以上传自定义 skill。详见 [Skills API Quickstart](https://docs.claude.com/en/api/skills-guide#creating-a-skill)。

## 七、创建一个基础 Skill

Skill 的创建非常简单：只需要一个目录，里面放一个包含 YAML frontmatter 和说明内容的 `SKILL.md` 文件即可。你可以使用本仓库中的 `template-skill` 作为起点：

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

frontmatter 需要两个字段：

- `name`：skill 的唯一标识符，使用小写字母，空格用连字符表示。
- `description`：对 skill 功能及适用场景的完整描述。

下方的 Markdown 正文中可以写入说明、示例和规则，Claude 在 skill 激活时会遵循这些内容。更多细节请参阅 [如何创建自定义 skills](https://support.claude.com/en/articles/12512198-creating-custom-skills)。

## 八、合作伙伴 Skills

Skill 是让 Claude 更擅长使用特定软件的一种方式。当我们看到合作伙伴提供了出色的示例 skill 时，也可能会在这里展示：

- **Notion**：[Notion Skills for Claude](https://www.notion.so/notiondevs/Notion-Skills-for-Claude-28da4445d27180c7af1df7d8615723d0)
