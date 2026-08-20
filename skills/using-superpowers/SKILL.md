---
name: using-superpowers
description: Use when starting any conversation - establishes how to find and use skills, requiring skill invocation before ANY response including clarifying questions
---

<SUBAGENT-STOP>
If you were dispatched as a subagent to execute a specific task, ignore this skill.
</SUBAGENT-STOP>

<!-- ═══════════ PERSONAL · merge upstream 时保留这一整块 ═══════════ -->

## 顺序

| 情况 | 先做 |
|---|---|
| 新方向 / 需求不清楚 | **`interview-me`**（在 `~/.claude/skills/`，不在本插件） |
| 要动代码 | `brainstorming` |
| 有了 spec 要拆 | `writing-plans` |
| 有 bug / 行为不符预期 | `systematic-debugging` |
| 要说「做完了」 | `verification-before-completion` |
| 做完一件事 | `requesting-code-review` |
| 定了什么 | `documentation-and-adrs`（在 `~/.claude/skills/`） |

## 决定之前跑一遍

1. 指着任何一个字段问「谁是作者」—— 答不出就是设计没做完
2. 把目标列出来，看有没有两条在互相否定
3. 绕过和照做的代价对不对称？不对称的话，人会往便宜那边跑
4. 这条判据的机械影子是什么？（语义判断 → 引用完整性）

## 两条

- **写文档不是探索**，是把猜测格式化。探索是做出能被证伪的东西
- **绿色测试证明自洽，不证明正确** —— 同一个上下文写测试又写实现，绿了不说明对

<!-- ═══════════ /PERSONAL ═══════════ -->

## The Rule

**Invoke relevant or requested skills BEFORE any response or action** — including clarifying questions, exploring the codebase, or checking files. If it turns out wrong for the situation, you don't have to use it.

Then announce "Using [skill] to [purpose]" and follow the skill exactly. If it has a checklist, create a todo per item.

## Platform Adaptation

If your harness appears here, read its reference file for special instructions:

- Codex: `references/codex-tools.md`

## User Instructions

User instructions (CLAUDE.md, AGENTS.md, direct requests) take precedence over skills, which in turn override default behavior. Only skip skill workflows or instructions when your human partner has explicitly told you to.
