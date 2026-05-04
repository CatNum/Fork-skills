---
name: cc-macos-notice
description: "Function: silent macOS osascript notifications (folder + short task/error text); Submarine on success, Glass on error/blocker/approval wait. Triggers: (1) current user request fully answered; (2) unfixable local command failure; (3) paused for [Y/n] on a sensitive operation."
---

---

**名称（中文）**：Mac 多会话智能通知助手
**描述（中文）**：**功能**：在 macOS 上通过 `osascript` 静默推送通知（含目录名与简短任务/报错摘要）；成功 **Submarine**，阻塞/报错/等待授权 **Glass**。**触发时机**：（1）本轮用户请求已完整交付；（2）本地命令出现无法自修复的报错或阻塞；（3）高危操作暂停等待 `[Y/n]`。

---

# 💻 核心设定 (Core Persona)

作为运行在本地终端的智能体，你深刻理解用户通常会在 iTerm2 的多个分屏中并行执行多个命令。
为了避免用户“干等”或“错过报错”，你被授予了调用底层操作系统的权限，负责在关键节点向 macOS 发送精准、带有上下文的物理弹窗汇报。

# 🎯 触发机制 (Trigger Rules)

**请在后台静默执行，并在以下场景必定触发系统通知：**

1.  **任务闭环 (Task Completed)**：当你对用户本轮请求已形成**完整交付**并即将结束回复时——包括但不限于：单轮问答、语法/概念说明、小改动、批量重构、编译与长文档生成。**不论耗时几秒还是几十分钟**，只要本轮有可陈述的「完成结果」，就必须弹窗。
2.  **硬性阻塞 (Blocker Encountered)**：当你执行本地命令（Bash/Terminal）时，遇到了你无法自动修复的报错（如：Git 合并冲突、缺少关键依赖、接口 500 报错、权限被拒绝）。
3.  **人类确认 (Human Auth Required)**：当你准备执行高危操作（如直接删除大批量文件、`git push --force`），在暂停等待用户 `[Y/n]` 输入时。

# 🛠️ 动作执行指南 (Execution Guidelines)

你必须使用内置的 `Bash` 或 `Terminal` 工具执行 Mac 底层的 `osascript`。**音效约定**：任务正常结束用 **Submarine**；报错、阻塞、等待关键授权一律用 **Glass**。

### 场景 A：任务圆满完成 (Success)
- **要求**：从上下文中提炼你刚才完成的【核心任务】（限 10 个字内）。与任务体量无关，**凡属触发规则第 1 条的成功收尾，均在给出最终 Markdown 总结之前执行本场景**。
- **执行命令模板**：
  ```bash
  osascript -e 'display notification "任务 [填写核心任务，如：简历HTML转换] 已圆满完成！" with title "✅ [填写当前所在目录名] 节点空闲" sound name "Submarine"'
  ```

### 场景 B：遇到报错与阻塞 (Error & Conflict)
- **要求**：提炼最致命的【报错原因】（限 15 个字内，如：存在未解决的 Git 冲突）。
- **执行命令模板**：
  ```bash
  osascript -e 'display notification "卡住了：[填写报错原因]，请切回此终端处理！" with title "🚨 [填写当前所在目录名] 发生异常" sound name "Glass"'
  ```

### 场景 C：等待关键授权 (Waiting for Approval)
- **执行命令模板**：
  ```bash
  osascript -e 'display notification "遇到敏感操作，正在等待您的 [Y/n] 授权继续。" with title "⚠️ [填写当前所在目录名] 等待指令" sound name "Glass"'
  ```

# 🚫 铁律 (Strict Constraints)

1.  **绝对静默 (Silent Execution)**：在执行 `osascript` 弹窗命令时，**绝不要**把这行复杂的 Bash 代码在最终的聊天回复中打印给用户看。直接在后台悄悄执行即可，用户的终端屏幕必须保持干净，只显示你的总结文字。