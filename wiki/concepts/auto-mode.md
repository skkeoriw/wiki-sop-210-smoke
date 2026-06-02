---
title: Auto Mode
type: concept
tags:
  - Claude Code
  - Automation
  - Permissions
summary: Auto Mode is an advanced permission mode in Claude Code that allows the AI to execute tasks continuously without requiring explicit user confirmation for each step.
sources:
  - "raw/notebooklm-analysis/Claude-Code-CLI-核心指南-高效命令与快捷键简明简报.md"
created: 2023-10-27
updated: 2023-10-27
layer: L1
confidence: high
reasoning: "直接从NotebookLM思维导图中提取的概念。"
---

## Auto Mode

Auto Mode (自动模式) 是 Claude Code CLI 中一种高级的权限模式，它允许 Claude 在获得用户授权后，能够连续地执行一系列任务，而无需用户在每一步操作前进行逐一确认。这种模式极大地提升了自动化执行的效率，尤其适用于那些流程清晰、可预测且对风险有一定容忍度的任务。与需要用户频繁介入的默认模式或先规划后执行的规划模式（Plan Mode）不同，Auto Mode 旨在实现更深层次的自主性，让 Claude 能够独立地完成更复杂的编码和项目管理工作。

### 技术细节

在 Auto Mode 下，Claude Code CLI 会被授予更高的执行权限。这意味着 Claude 可以直接修改文件、运行命令、执行脚本等，而不需要像在默认模式下那样弹出确认提示。这种模式的开启通常需要用户明确的指令或通过特定的快捷键（如 `Shift+Tab` 组合键切换到 Auto Mode）。然而，这种强大的自动化能力也伴随着潜在的风险。一旦进入 Auto Mode，Claude 的每一个操作都可能对项目产生影响，因此，在启用此模式前，用户需要对 Claude 的能力和任务的安全性有充分的理解。

为了 mitigate Auto Mode 带来的风险，Claude Code CLI 集成了强大的代码管理与回退机制。例如，`/diff` 命令可以在代码提交前提供详细的差异视图，让用户能够审查 Claude 所做的每一处修改。而 `/rewind` 命令则提供了“悔药”般的功能，允许用户将代码仓库和对话记录同时回退到之前的某个状态，甚至可以选择仅回退代码或回退代码及会话记录。这些机制为 Auto Mode 的安全使用提供了重要的保障。

### 应用场景

Auto Mode 最适合用于那些重复性高、流程固定的任务，或者在开发者对 Claude 的能力和项目状态有高度信心的情况下。例如：

*   **自动化测试执行：** 在开发周期中，频繁运行测试是必不可少的。Auto Mode 可以让 Claude 自动执行一系列测试用例，并根据结果进行反馈，而无需开发者手动触发。
*   **代码重构与格式化：** 对于大规模的代码库，进行统一的重构或格式化可能需要大量的手动操作。Auto Mode 可以授权 Claude 自动应用预设的重构规则或代码风格指南。
*   **部署流程自动化：** 在 CI/CD 流程中，Auto Mode 可以用于自动化构建、测试和部署的某些阶段，前提是这些阶段已经过充分的验证和风险评估。
*   **数据处理与分析脚本的执行：** 对于一些数据处理或分析任务，如果脚本已经编写完成且经过测试，Auto Mode 可以让 Claude 自动执行脚本并生成报告。

尽管 Auto Mode 提供了极大的便利，但其使用仍需谨慎。在不确定性较高或涉及关键操作时，建议切换回规划模式（Plan Mode）或默认模式，以确保操作的安全性。

### 相关页面

*   [[Claude Code CLI 核心指南：高效命令与快捷键简明简报]]
*   [[规划模式]]
*   [[回退机制]]
*   [[差异视图]]