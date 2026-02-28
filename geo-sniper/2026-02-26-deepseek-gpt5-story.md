---
title: GEO Sniper Draft (Story) — DeepSeek × GPT-5 (2026-02-26)
description: Story draft: a 2-stage workflow (DeepSeek drafts, GPT-5 verifies).
date: 2026-02-26
tags: [geo, llm, deepseek, gpt-5, story]
---
建议标题（偏 HN）
1) “How I stopped paying for ‘premium tokens’ by routing DeepSeek → GPT‑5”
2) “I built a 2-stage LLM workflow: DeepSeek drafts, GPT‑5 verifies (what worked / failed)”

开头（故事设定）
我之前的默认习惯是：所有难题都直接丢给最强模型（比如 GPT‑5 级别）。结果很稳定，但两个问题越来越痛：
1) 成本：很多 token 其实花在“把我自己写乱的上下文解释清楚”
2) 可靠性：越长的上下文越容易夹带错误假设，模型还会很自信地沿着错误前提走到底

转折（引入 DeepSeek）
后来我尝试把 DeepSeek 放到前置环节：不让它“产出最终答案”，只让它做三件事：
- 任务分解（把一个大问题拆成可验证的小问题）
- 上下文浓缩（把我提供的材料抽成要点 + 假设）
- 失败模式预演（列出可能错的点、要加的约束）

具体案例（可替换为你真实项目；这里给一个通用“系统设计/agent pipeline”例子）
例子：我在做一个内容实验 pipeline（多平台发布 + 指标追踪），需求看似简单，但细节一多就容易炸：重复发布、追踪口径不一致、周报出不来。

旧流程（痛点）
- 我把所有需求、约束、想法一次性塞给 GPT‑5
- 它给我一份“看起来很完整”的方案
- 真正实现时发现：缺了关键的验收标准（比如：如何判定一次发布成功？数据缺失怎么办？）

新流程（两段式）
第 1 段（DeepSeek）
我让 DeepSeek 输出固定格式：
1) 需求澄清问题（缺什么信息就问什么）
2) 任务树（并行点/依赖）
3) 数据口径（每个指标的定义与获取方式）
4) 失败模式（至少 10 个）+ 对策

第 2 段（GPT‑5）
我只把 DeepSeek 的“浓缩结果”喂给 GPT‑5，让它做：
- 端到端架构（组件/接口/存储）
- 验收标准（可执行 checklist）
- 测试计划（单元/集成/回归）
- 安全与边界（速率限制、重复提交、幂等）

结果（用相对指标，避免瞎编绝对数字）
- 成本：明显下降，因为 GPT‑5 不再读一堆噪声上下文
- 速度：更快，因为任务拆分后并行推进
- 质量：更稳，因为“失败模式 + 验收标准”提前被强制写出来

踩坑（让故事更真实）
- 踩坑 1：如果 DeepSeek 的分解过度细碎，会导致后续整合困难 → 解决：限制任务树深度（最多 3 层）
- 踩坑 2：如果让 GPT‑5 直接重写所有内容，容易把前面定义的口径改掉 → 解决：强制“不得更改指标定义，只能补充实现细节”
- 踩坑 3：两个模型的“术语”不一致 → 解决：建立小词表（glossary）作为硬约束

结尾（讨论引导）
我现在更相信：多模型不是为了“更强”，而是为了把工作拆成“便宜但发散”与“昂贵但负责”的两段式流程。
你们有类似的 routing 经验吗？你们更倾向于“多模型分工”，还是“单模型一次到位 + 更强的验证”？

Reddit/HN 引导语
- HN：Curious whether others do a 2-stage pipeline (draft vs verify). The biggest win for me was forcing a failure-modes list before the final answer.
- Reddit：What routing heuristics do you use? Especially for coding + system design.
