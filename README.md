<br/>
<br/>
<br/>
<p align="center"><a href="./README.md">English</a> | <a href="./README.zh-CN.md">简体中文</a></p>

> **Note:** This repository is a fork of Anthropic's Agent Skills examples. For information about the Agent Skills standard, see [agentskills.io](http://agentskills.io).

# Skills

## Key Points

- **Repository purpose**: This repo collects Agent Skills that package instructions, scripts, references, and assets into reusable task capabilities.
- **Fork additions**: This fork adds workflow, documentation, Markdown, skill-maintenance, interview-practice, and interview-review skills on top of the original example and document skills.
- **Current entry point**: Each skill is self-contained under `skills/<skill-name>/SKILL.md`, with optional `references/`, `scripts/`, `assets/`, or `project-docs/` resources.
- **Plugin grouping**: The local Claude plugin marketplace currently exposes `document-skills`, `example-skills`, and `claude-api` plugin groups.

## One, About Skills

Skills are folders of instructions, scripts, and resources that Claude loads dynamically to improve performance on specialized tasks. Skills teach Claude how to complete specific tasks in a repeatable way, whether that is creating documents with your company's brand guidelines, analyzing data using an organization's specific workflows, or automating personal tasks.

For more information, check out:

- [What are skills?](https://support.claude.com/en/articles/12512176-what-are-skills)
- [Using skills in Claude](https://support.claude.com/en/articles/12512180-using-skills-in-claude)
- [How to create custom skills](https://support.claude.com/en/articles/12512198-creating-custom-skills)
- [Equipping agents for the real world with Agent Skills](https://anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills)

## Two, About This Repository

This repository contains skills that demonstrate what is possible with Claude's skills system. These skills range from creative applications, such as art and design, to technical tasks, such as web app testing and MCP server generation, to enterprise workflows, such as internal communications and brand guidance.

Each skill is self-contained in its own folder with a `SKILL.md` file containing the instructions and metadata that Claude uses. Browse these skills to get inspiration for your own skills or to understand different patterns and approaches.

Many skills in this repo are open source under Apache 2.0. The document creation and editing skills that power [Claude's document capabilities](https://www.anthropic.com/news/create-files) are included under [`skills/docx`](./skills/docx), [`skills/pdf`](./skills/pdf), [`skills/pptx`](./skills/pptx), and [`skills/xlsx`](./skills/xlsx). These are source-available, not open source, but they are useful references for more complex skills used in production AI applications.

### 2.1 Disclaimer

**These skills are provided for demonstration and educational purposes only.** While some of these capabilities may be available in Claude, the implementations and behaviors you receive from Claude may differ from what is shown in these skills. Always test skills thoroughly in your own environment before relying on them for critical tasks.

## Three, Fork-Specific Skills

### 3.1 Custom Added

| No. | Skill | Summary | Path |
| --- | --- | --- | --- |
| 1 | `ai-native-standard-flow` | Executes an AI Native collaboration workflow for zero-code development, including standards, required artifacts, compliance checks, and AI-driven progress. | [`skills/ai-native-standard-flow`](./skills/ai-native-standard-flow) |
| 2 | `design-changelog-maintainer` | Maintains per-project `design.md`, `changelog.md`, and `resume-interview.md` across multi-project repositories with explicit scope configuration. | [`skills/design-changelog-maintainer`](./skills/design-changelog-maintainer) |
| 3 | `md-formatting` | Normalizes Markdown documents into a consistent structure with a dedicated key-points section for easier reading and extraction. | [`skills/md-formatting`](./skills/md-formatting) |
| 4 | `interview-transcript-review` | Turns real mock-interview transcripts into post-interview review documents with scoring, interviewer intent, answer-direction analysis, shortcoming cards, and Markdown/HTML output. | [`skills/interview-transcript-review`](./skills/interview-transcript-review) |
| 5 | `project-mock-interview` | Runs strict Chinese, one-question-at-a-time P7 backend project mock interviews based on a single user-provided project and its materials. | [`skills/project-mock-interview`](./skills/project-mock-interview) |
| 6 | `skill-update-assistant` | Audits proposed updates to existing skills against structural and iteration standards, then guides sync and changelog follow-up. | [`skills/skill-update-assistant`](./skills/skill-update-assistant) |
| 7 | `transcript-refine` | Refines long video or live-course transcripts into structured first-study materials, with reading-oriented and spoken-script output modes. | [`skills/transcript-refine`](./skills/transcript-refine) |

### 3.2 Customized

| No. | Skill | Summary | Path |
| --- | --- | --- | --- |
| 1 | `skill-creator` | Customized for Chinese adaptation and skill-authoring workflows, including bilingual header guidance in `SKILL.md`. | [`skills/skill-creator`](./skills/skill-creator) |

## Four, Current Skill Inventory

### 4.1 Document Skills

| Skill | Summary | Path |
| --- | --- | --- |
| `docx` | Creates, reads, edits, comments on, redlines, and validates Word `.docx` files. | [`skills/docx`](./skills/docx) |
| `pdf` | Reads, creates, inspects, splits, combines, fills, encrypts, OCRs, and validates PDF files. | [`skills/pdf`](./skills/pdf) |
| `pptx` | Creates, reads, edits, combines, validates, and exports PowerPoint `.pptx` decks. | [`skills/pptx`](./skills/pptx) |
| `xlsx` | Creates, reads, edits, cleans, recalculates, and converts spreadsheet files. | [`skills/xlsx`](./skills/xlsx) |

### 4.2 Example And Technical Skills

| Skill | Summary | Path |
| --- | --- | --- |
| `algorithmic-art` | Creates original p5.js generative art with seeded randomness and interactive parameters. | [`skills/algorithmic-art`](./skills/algorithmic-art) |
| `brand-guidelines` | Applies Anthropic brand colors and typography to visual artifacts. | [`skills/brand-guidelines`](./skills/brand-guidelines) |
| `canvas-design` | Creates static visual art in PNG and PDF outputs using bundled design guidance and fonts. | [`skills/canvas-design`](./skills/canvas-design) |
| `doc-coauthoring` | Guides structured co-authoring of documentation, proposals, specs, and decision docs. | [`skills/doc-coauthoring`](./skills/doc-coauthoring) |
| `frontend-design` | Builds distinctive production-grade frontend interfaces, pages, components, and artifacts. | [`skills/frontend-design`](./skills/frontend-design) |
| `interview-transcript-review` | Turns real mock-interview transcripts into Markdown or HTML review reports with scoring, interviewer intent, answer improvement notes, and shortcoming cards. | [`skills/interview-transcript-review`](./skills/interview-transcript-review) |
| `internal-comms` | Writes internal communications such as status reports, leadership updates, newsletters, FAQs, and incident updates. | [`skills/internal-comms`](./skills/internal-comms) |
| `mcp-builder` | Guides creation of high-quality MCP servers in Python or Node/TypeScript. | [`skills/mcp-builder`](./skills/mcp-builder) |
| `slack-gif-creator` | Creates animated GIFs optimized for Slack constraints and validation. | [`skills/slack-gif-creator`](./skills/slack-gif-creator) |
| `theme-factory` | Applies preset or generated themes to slides, docs, reports, HTML pages, and similar artifacts. | [`skills/theme-factory`](./skills/theme-factory) |
| `web-artifacts-builder` | Builds complex Claude.ai HTML artifacts with React, Tailwind CSS, and shadcn/ui. | [`skills/web-artifacts-builder`](./skills/web-artifacts-builder) |
| `webapp-testing` | Uses Playwright helpers to interact with and test local web applications. | [`skills/webapp-testing`](./skills/webapp-testing) |

### 4.3 API And Template Skills

| Skill | Summary | Path |
| --- | --- | --- |
| `claude-api` | Provides Claude API, Anthropic SDK, and Agent SDK guidance across supported languages. | [`skills/claude-api`](./skills/claude-api) |
| `template-skill` | Provides the baseline template for creating a new skill. | [`skills/template`](./skills/template) |

## Five, Repository Layout

- [`skills`](./skills): Skill examples for Creative & Design, Development & Technical, Enterprise & Communication, fork-specific workflows, and Document Skills.
- [`spec`](./spec): The Agent Skills specification.
- [`template`](./template): The skill template.
- [`.claude-plugin/marketplace.json`](./.claude-plugin/marketplace.json): Local Claude Code plugin marketplace definition.

## Six, Try In Claude Code, Claude.ai, And The API

### 6.1 Claude Code

You can register this repository as a Claude Code plugin marketplace by running the following command in Claude Code:

```text
/plugin marketplace add anthropics/skills
```

Then, to install a specific set of skills:

1. Select `Browse and install plugins`.
2. Select `anthropic-agent-skills`.
3. Select `document-skills`, `example-skills`, or `claude-api`.
4. Select `Install now`.

Alternatively, directly install a plugin via:

```text
/plugin install document-skills@anthropic-agent-skills
/plugin install example-skills@anthropic-agent-skills
/plugin install claude-api@anthropic-agent-skills
```

After installing a plugin, you can use a skill by mentioning it. For instance, if you install the `document-skills` plugin from the marketplace, you can ask Claude Code to do something like: "Use the PDF skill to extract the form fields from `path/to/some-file.pdf`."

### 6.2 Local OpenSkills Usage

This fork is also organized for local OpenSkills usage. From the repository root, read a skill with:

```bash
npx openskills read <skill-name>
```

For multiple skills:

```bash
npx openskills read skill-one,skill-two
```

### 6.3 Claude.ai

The original example skills are available to paid plans in Claude.ai.

To use any skill from this repository or upload custom skills, follow the instructions in [Using skills in Claude](https://support.claude.com/en/articles/12512180-using-skills-in-claude#h_a4222fa77b).

### 6.4 Claude API

You can use Anthropic's pre-built skills, and upload custom skills, via the Claude API. See the [Skills API Quickstart](https://docs.claude.com/en/api/skills-guide#creating-a-skill) for more.

## Seven, Creating A Basic Skill

Skills are simple to create: a folder with a `SKILL.md` file containing YAML frontmatter and instructions. You can use the `template-skill` in this repository as a starting point:

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

The frontmatter requires two fields:

- `name`: A unique identifier for your skill, using lowercase letters and hyphens for spaces.
- `description`: A complete description of what the skill does and when to use it.

The Markdown content below the frontmatter contains the instructions, examples, and guidelines that Claude will follow. For more details, see [How to create custom skills](https://support.claude.com/en/articles/12512198-creating-custom-skills).

## Eight, Partner Skills

Skills are a useful way to teach Claude how to get better at using specific software. As strong example skills from partners appear, they may be highlighted here:

- **Notion**: [Notion Skills for Claude](https://www.notion.so/notiondevs/Notion-Skills-for-Claude-28da4445d27180c7af1df7d8615723d0)
