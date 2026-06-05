---
title: "Multi-Agent Design: Optimizing Agents with Better Prompts and Topologies"
title_zh: 多智能体设计：通过更好的提示和拓扑优化智能体
authors: "Han Zhou, Xingchen Wan, Ruoxi Sun, Hamid Palangi, Shariq Iqbal, Ivan Vulić, Anna Korhonen, Sercan O Arik"
date: 2025-01-23
pdf: "https://openreview.net/pdf?id=uCKvHweh1g"
tags: ["query:agent-papers"]
score: 6.0
evidence: 优化多智能体系统的提示和拓扑以求解复杂任务
tldr: 多智能体系统的提示和拓扑设计十分复杂。本文提出MASS框架，通过自动化搜索来优化提示和拓扑结构。实验表明，联合优化提示和拓扑能显著提升多智能体系统的性能。该工作为多智能体系统的高效设计提供了新方法。
source: ICML-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 842, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 841, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1672, \"height\": 724, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 841, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 838, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1786, \"height\": 670, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1673, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1130, \"height\": 746, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1870, \"height\": 2155, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-uckvhweh1g/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 929, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uckvhweh1g/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1773, \"height\": 469, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uckvhweh1g/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1757, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uckvhweh1g/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1754, \"height\": 472, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uckvhweh1g/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1758, \"height\": 477, \"label\": \"Table\"}]"
motivation: 多智能体系统的提示和拓扑设计复杂且耗时。
method: 提出多智能体系统搜索（MASS）框架，自动优化提示和拓扑。
result: 在多种任务上，优化后的MAS性能显著提升。
conclusion: 提示和拓扑的联合优化是构建有效MAS的关键。
---

## Abstract
Large language models, employed as multiple agents that interact and collaborate with each other, have excelled at solving complex tasks. The agents are programmed with prompts that declare their functionality, along with the topologies that orchestrate interactions across agents. Designing prompts and topologies for multi-agent systems (MAS) is inherently complex. To automate the entire design process, we first conduct an in-depth analysis of the design space aiming to understand the factors behind building effective MAS. We reveal that prompts together with topologies play critical roles in enabling more effective MAS design. Based on the insights, we propose Multi-Agent System Search (MASS), a MAS optimization framework that efficiently exploits the complex MAS design space by interleaving its optimization stages, from local to global, from prompts to topologies, over three stages: 1) block-level (local) prompt optimization; 2) workflow topology optimization; 3) workflow-level (global) prompt optimization, where each stage is conditioned on the iteratively optimized prompts/topologies from former stages. We show that MASS-optimized multi-agent systems outperform a spectrum of existing alternatives by a substantial margin. Based on the MASS-found systems, we finally propose design principles behind building effective multi-agent systems.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- 大型语言模型（LLM）作为多智能体系统（MAS）在复杂任务中表现出色，但设计MAS的提示（prompts）和拓扑（topologies）非常复杂且耗时。
- 现有自动化方法（如DSPy、ADAS、AFlow）要么只优化提示，要么只优化拓扑，缺乏对两者联合优化效果的理解。
- 本文首先深入分析设计空间，揭示**提示**和**拓扑**是影响MAS性能的关键因素，进而提出多智能体系统搜索（MASS）框架，以自动化方式联合优化提示和拓扑，从而构建更有效的MAS。

## 2. 方法论：核心思想、关键技术细节、算法流程

- **核心思想**：通过分阶段、由局部到全局、由提示到拓扑的交替优化，降低组合搜索复杂度，挖掘设计空间中最有影响力的组件。
- **关键技术细节**：
  - 搜索空间包括五种构建块（Aggregate、Reflect、Debate、Summarize、Tool-use），每个块有可优化的提示（指令和样例）。
  - 采用**块级提示优化**（Stage 1）：先优化单智能体预测器，再优化每个构建块的最小规模版本，并存储增量影响 \( I_{a_i} = E(a_i^*)/E(a_0^*) \)。
  - **工作流拓扑优化**（Stage 2）：基于增量影响计算选择概率 \( p_a = \text{Softmax}(I_a, t) \)，通过概率采样和拒绝采样（受预算B约束）生成候选拓扑，并用验证集评估选择最佳。
  - **工作流级提示优化**（Stage 3）：在最佳拓扑上再次运行提示优化器，调整提示以适应智能体间的协作。
- **算法流程**（文字说明）：
  1. 对初始智能体 \( a_0 \) 进行提示优化得到 \( a_0^* \)。
  2. 对每个构建块 \( a_i \)（除 \( a_0 \)）进行提示优化得到 \( a_i^* \)，计算 \( I_{a_i} \)。
  3. 根据 \( I_{a_i} \) 得到选择概率，采样并评估拓扑，保留最佳 \( W_c^* \)。
  4. 对 \( W_c^* \) 进行工作流级提示优化，输出最终MAS设计 \( W^* \)。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：涵盖推理（MATH、DROP）、多跳长文本理解（HotpotQA、MuSiQue、2WikiMultiHopQA）、代码生成（MBPP、HumanEval、LiveCodeBench test output prediction）共8个任务。
- **基准模型**：Gemini 1.5 Pro、Gemini 1.5 Flash，并在Claude 3.5 Sonnet上验证主要结论。
- **对比方法**：
  - 传统基线：CoT、Self-Consistency (SC@9)、Self-Refine、Multi-Agent Debate。
  - 自动化方法：ADAS（LLM元智能体迭代生成新智能体）、AFlow（基于MCTS搜索工作流，但元提示不兼容，仅用Claude优化+Gemini执行提供参考）。
- 所有方法限制最大智能体数量为10。

## 4. 资源与算力

- 论文未明确说明使用的GPU型号、数量或训练时长。
- 实验中主要调用Gemini 1.5 API（闭源），因此可能不涉及本地GPU训练；提示优化使用MIPROv2（也基于API）。
- 需要指出：本文未提供任何关于算力的具体信息。

## 5. 实验数量与充分性

- **实验数量**：包含完整主实验（Gemini Pro/Flash共8个任务，各3次运行）、消融实验（每阶段贡献、有无修剪、有无提示优化）、成本效益分析（token效率曲线）、Claude验证实验（6个任务）、以及详细的优化轨迹分析。
- **充分性与公平性**：
  - 基线实现遵守原始设置（如ADAS 30轮搜索、AFlow 20轮），并限制智能体数量相同。
  - 消融实验系统考察了每个阶段的增益，并额外排除提示优化或搜索空间修剪验证其必要性。
  - 多模型验证（Gemini Plus Claude）增强了结论可靠性。
  - 不足：AFlow因元提示不兼容无法在同一LLM下完全公平比较（其标记为*）。

## 6. 主要结论与发现

- **MASS显著优于所有基线**：Gemini Pro平均78.8%，Flash平均74.3%，比次优方法（Multi-Agent Debate/ADAS）提高8-10个百分点。
- **提示优化比单纯增加智能体数量更有效**：图2显示通过更好的提示可获得更优的token效率。
- **并非所有拓扑都有益**：图3表明只有少量拓扑（如Debate）能带来增益，因此搜索空间剪枝至关重要。
- **三阶段优化均贡献显著**：块级提示优化+6%，拓扑优化+3%，工作流级提示优化进一步+2%（图5）。
- **设计原则**：1）先优化单个智能体再组合；2）组成有影响的拓扑；3）通过联合优化建模智能体间依赖。

## 7. 优点

- **深入分析**：首次系统量化提示与拓扑对MAS性能的影响，并揭示设计空间的不均匀性。
- **方法创新**：提出分阶段交替优化策略，有效克服联合搜索的组合爆炸问题，且各阶段可并行化。
- **搜索空间剪枝**：基于增量影响概率采样，自动聚焦于有效拓扑，提高搜索效率。
- **实验充分**：跨两类LLM（Gemini、Claude）、多种任务（推理、长上下文、代码）验证，消融完整，成本效益可视化。
- **可扩展性**：框架模块化，可集成其他提示优化器或拓扑结构。

## 8. 不足与局限

- **搜索空间覆盖有限**：仅探索了Aggregate、Reflect、Debate等基本拓扑，可能遗漏更复杂的连接（如稀疏通信、动态激活）。
- **提示优化依赖特定技术**：使用MIPROv2，其性能受限于候选质量和采样策略，可能不是最优选择。
- **计算成本未量化**：虽声称“管理预算”，但未给出具体GPU/API调用数或时间，实际应用中的成本难以评估。
- **跨模型泛化不稳定**：在Claude 3.5 Sonnet上，某些基线出现严重性能下降（如Debate仅45%），MASS虽恢复但增幅小于Gemini，提示模板迁移性问题。
- **可复现性不足**：匿名投稿且未提供代码/配置，仅部分模板在附录中给出；需依赖商业API（Gemini、Claude）。
- **实验结果方差未充分讨论**：部分标准偏差较大（如Gemini Flash MATH 2.45），但未深入分析原因。

（完）
