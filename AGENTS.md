# AGENTS

<skills_system priority="1">

## Available Skills

<!-- SKILLS_TABLE_START -->
<usage>
When users ask you to perform tasks, check if any of the available skills below can help complete the task more effectively. Skills provide specialized capabilities and domain knowledge.

How to use skills:
- Invoke: `npx openskills read <skill-name>` (run in your shell)
  - For multiple: `npx openskills read skill-one,skill-two`
- The skill content will load with detailed instructions on how to complete the task
- Base directory provided in output for resolving bundled resources (references/, scripts/, assets/)

Usage notes:
- Only use skills listed in <available_skills> below
- Do not invoke a skill that is already loaded in your context
- Each skill invocation is stateless
</usage>

<available_skills>

<skill>
<name>cc-mac-notice</name>
<description>"Function: silent macOS osascript notifications (folder + short task/error text); Submarine on success, Glass on error/blocker/approval wait. Triggers: (1) current user request fully answered; (2) unfixable local command failure; (3) paused for [Y/n] on a sensitive operation."</description>
<location>global</location>
</skill>

<skill>
<name>claude-api</name>
<description>"Build apps with the Claude API or Anthropic SDK. TRIGGER when: code imports `anthropic`/`@anthropic-ai/sdk`/`claude_agent_sdk`, or user asks to use Claude API, Anthropic SDKs, or Agent SDK. DO NOT TRIGGER when: code imports `openai`/other AI SDK, general programming, or ML/data-science tasks."</description>
<location>global</location>
</skill>

<skill>
<name>md-formatting</name>
<description>Format and normalize Markdown (.md) documents for consistent readability and scannable key points. Use when the user creates a new Markdown file or updates an existing one, and wants the result structured for later reading and quick extraction of重点.</description>
<location>global</location>
</skill>

<skill>
<name>skill-creator</name>
<description>Create new skills, modify and improve existing skills, and measure skill performance. Use when users want to create a skill from scratch, edit, or optimize an existing skill, run evals to test a skill, benchmark skill performance with variance analysis, or optimize a skill's description for better triggering accuracy.</description>
<location>global</location>
</skill>

<skill>
<name>skill-update-assistant</name>
<description>>-</description>
<location>global</location>
</skill>

</available_skills>
<!-- SKILLS_TABLE_END -->

</skills_system>
