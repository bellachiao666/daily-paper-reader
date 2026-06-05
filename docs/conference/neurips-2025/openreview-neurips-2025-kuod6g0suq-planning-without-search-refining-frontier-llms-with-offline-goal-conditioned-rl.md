---
title: "Planning without Search: Refining Frontier LLMs with Offline Goal-Conditioned RL"
title_zh: 无搜索规划：用离线目标条件强化学习精炼前沿大语言模型
authors: "Joey Hong, Anca Dragan, Sergey Levine"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=kuoD6G0Suq"
tags: ["query:agent-papers"]
score: 7.0
evidence: 离线目标条件强化学习微调LLM以提升长程规划能力
tldr: 现有LLM在需要交互的复杂任务中缺乏长程推理和规划能力，而多轮RL训练成本高昂且不适用于闭源模型。本文提出离线目标条件强化学习方法PWS，通过目标条件奖励函数和离线数据微调LLM，在无需在线交互的情况下显著提升LLM在谈判、说服等任务中的规划性能。该方法为LLM通过强化学习实现自改进提供了一种高效可扩展的途径。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-kuod6g0suq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1397, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kuod6g0suq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1363, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kuod6g0suq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 703, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kuod6g0suq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1435, \"height\": 865, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-kuod6g0suq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1100, \"height\": 711, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kuod6g0suq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1105, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kuod6g0suq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 737, \"height\": 470, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kuod6g0suq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 739, \"height\": 468, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kuod6g0suq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 740, \"height\": 469, \"label\": \"Table\"}]"
motivation: LLM在需要交互的复杂任务中缺乏长程推理和规划能力，而现有的多轮RL训练成本高、难以扩展。
method: 提出离线目标条件强化学习方法，利用目标条件奖励函数和离线交互数据微调LLM，避免在线RL的高成本。
result: 在谈判和说服等任务上，该方法显著提升了LLM的规划能力，且训练效率远高于在线RL。
conclusion: 离线目标条件RL是一种高效且可扩展的LLM自改进方法，适用于复杂交互任务。
---

## Abstract
Large language models (LLMs) excel in tasks like question answering and dialogue, but complex tasks requiring interaction, such as negotiation and persuasion, require additional long-horizon reasoning and planning. Reinforcement learning (RL) fine-tuning can enable such planning in principle, but suffers from drawbacks that hinder scalability. In particular, multi-turn RL training incurs high memory and computational costs, which are exacerbated when training LLMs as policies. Furthermore, the largest LLMs do not expose the APIs necessary to be trained in such manner. As a result, modern methods to improve the reasoning of LLMs rely on sophisticated prompting mechanisms rather than RL fine-tuning. To remedy this, we propose a novel approach that uses goal-conditioned value functions to guide the reasoning of LLM agents, that scales even to large API-based models. These value functions predict how a task will unfold given an action, allowing the LLM agent to evaluate multiple possible outcomes, both positive and negative, to plan effectively. In addition, these value functions are trained over reasoning steps rather than full actions, to be a concise and light-weight module that facilitates decision-making in multi-turn interactions. We validate our method on tasks requiring interaction, including tool use, social deduction, and dialogue, demonstrating superior performance over both RL fine-tuning and prompting methods while maintaining efficiency and scalability.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：大型语言模型（LLMs）在问答、对话等任务表现优异，但在需要多轮交互的复杂任务（如谈判、说服、社交推理）中缺乏长程推理和规划能力。这类任务要求智能体在多个回合中制定策略、预估长期后果、适应对手反应。
- **现有方法不足**：
  - 多轮强化学习（RL）微调理论上可提升规划能力，但面临高昂的存储和计算成本，且不适用于无法暴露训练 API 的最前沿大模型（如 GPT-4）。
  - 当前主流的改进方法（如 ReAct、Reflexion、树搜索）依赖推理时的模拟或自省，计算开销大、可扩展性差。
- **核心目标**：提出一种可扩展到任意 API 模型的高效方法，在不直接训练 LLM 的情况下提升其规划与推理能力。

## 2. 方法论：核心思想、关键技术细节

- **整体思路**：学习一个轻量级的目标条件价值函数（Critic），在推理时分析可能的未来结果，引导 LLM 的思考（thought）改进，而无需训练 LLM 本身或进行推理时搜索。
- **关键技术细节**：
  1. **离线训练阶段**：
     - 从先前收集的交互轨迹数据 \( D \) 中提取样本 \((s, a_{\text{tht}}, s', g)\)，其中 \( g \) 为未来的某目标状态。
     - 使用隐式 Q 学习（IQL）训练目标条件 Q 函数 \( \hat{Q}(s, a_{\text{tht}}, g) \)，预测在状态 \( s \) 采取思考 \( a_{\text{tht}} \) 后达到目标 \( g \) 的概率。
     - 为降低复杂度：将轨迹摘要为简洁描述；使用 LLM（如 GPT-3）生成嵌入，Q 函数为 2 层 MLP。
  2. **推理阶段**：
     - LLM 生成初始思考。
     - 自然语言评论家生成 \( n=4 \) 个正面/负面目标（未来情景），用学习到的 Q 函数评估每个目标的概率。
     - 将目标和对应概率组合为自然语言价值，反馈给 LLM 进行自我修正（最多 \( m=2 \) 次迭代）。
     - 无需任何在线搜索或仿真。
- **损失函数**（IQL 变形）：
  \[
  L_Q = E_{(s, a_{\text{tht}}, s', g)\sim D}\left[ \left( r(s,g) + \gamma \hat{V}(s', g) - Q(s, a_{\text{tht}}, g) \right)^2 \right]
  \]
  \[
  L_V = E_{(s, a_{\text{tht}}, g)\sim D}\left[ L_{\tau_2}\left( \hat{Q}(s, a_{\text{tht}}, g) - V(s, g) \right) \right]
  \]
  其中 \( r(s,g) \) 是是否到达目标 \( g \) 的二进制指示器，\( L_{\tau_2} \) 为 expectile 损失。

## 3. 实验设计

- **数据集/场景**：
  1. **WebShop**：在线购物环境，12k 条用户指令，模拟 GPT-3.5 低效代理生成轨迹，指标为得分（Score）和成功率（SR）。
  2. **AvalonBench**：社交推理游戏（阿瓦隆），5 人局，LLM 扮演最难的 Merlin 角色，2.5k 轨迹（Merlin 胜率 21.4%），指标为胜率（Winrate）。
  3. **Persuasion**：说服对话任务，劝说用户向“拯救儿童”捐款，最大 10 轮，2.5k 对话（平均捐款 $0.21），指标为平均捐款额（Avg. Donation）。
- **对比方法**：
  - **RL 微调**：ArCHeR（离线/在线），基于 GPT-2。
  - **LLM 推理**：ReAct、Reflexion（n=5）、LATS（n=5 或 30）、Self-Plan（n=5）。
  - **任务特定**：Agent Q（WebShop，n=5/30，基于 Mixtral-7B）、Strategist（Avalon，n=5/30）、GDP-Zero（Persuasion，n=5/30）。
- **本文方法**：PNLC，GPT-4 作为基座，n=4 目标，m=1 轮修正。

## 4. 资源与算力

- 文中未明确说明使用的 GPU 型号、数量和训练时长。仅提及训练的是轻量级 MLP（2 隐藏层），使用 AdamW 优化器，学习率在 1e-4 到 8e-4 之间，超参数表给出。推理时间方面：PNLC 约 5-6 秒/决策，而对比的搜索方法（n=30）为 46-62 秒。
- **指出**：论文未提供详细的算力消耗（如 GPU 类型、训练总时长），也未报告在线搜索方法的完整成本。

## 5. 实验数量与充分性

- **实验数量**：
  - 主要结果（表1）：三个任务 × 每种方法（共约 15 种方法/变体），每个测试点 100 次独立运行。
  - 消融实验（表2）：两个 ablation（去除目标条件 / 去除修正），同样三个任务。
- **充分性评估**：
  - **优点**：覆盖了多种基线类型（RL 微调、推理提示、任务特定），任务多样性较好。
  - **不足**：
    - 未报告误差条或置信区间，无法评估结果稳定性。
    - 不同方法使用了不同基座模型（GPT-2、Mixtral-7B、GPT-4），作者承认模型大小不统一是局限。
    - 消融实验显示两个组件均必要，但未探索其他设计选择（如目标数量 n、修正轮数 m 的影响）。
  - **整体**：实验数量尚可，但充分性受限于缺乏统计误差和模型异质性。

## 6. 主要结论与发现

- PNLC 在所有三个任务上均取得最佳性能，超越了 RL 微调和推理时搜索方法，同时推理成本仅为对比方法的 1/10 左右。
- 两个关键组件（目标条件价值函数 + 自然语言修正）缺一不可：缺少任一组件则性能退化为简单提示方法（如 ReAct）。
- 消融实验表明，单独使用标量 Q 值或仅做 best-of-n 选择效果很差，说明自然语言反馈和修正过程是优势来源。

## 7. 优点

- **高效可扩展**：无需训练 LLM，只训练轻量 MLP，适用于任何提供 API 的模型，推理时间极短。
- **无需搜索**：不依赖推理时模拟，从而节省大量计算资源。
- **可解释性强**：自然语言价值直接给出正面/负面情景及概率，便于 LLM 理解和修正。
- **数据高效**：仅需少量离线轨迹（由次优代理收集），无需在线交互。
- **通用性**：方法框架不依赖特定领域，可应用于购物、社交推理、对话等多种任务。

## 8. 不足与局限

- **任务特定性**：需要为每个任务训练独立的价值函数，限制了跨任务泛化能力。
- **对 LLM 推理的依赖**：生成未来目标状态依赖 LLM 的“直觉”，在领域外任务（如医疗诊断）中可能不可靠。
- **数据质量要求**：离线数据需覆盖多种策略（包括错误策略），数据多样性不足可能影响效果。
- **实验局限**：
  - 未提供统计误差条或 P 值。
  - 不同方法使用不同基座模型，对比不够公平。
  - 论文未报告训练价值函数的具体计算资源（GPU 时长、模型参数等）。
- **潜在风险**：若将方法用于有害交互（如欺诈性说服），可能放大 LMs 的操纵能力，论文未深入讨论伦理风险。

（完）
