---
title: "ReMA: Learning to Meta-Think for LLMs with Multi-agent Reinforcement Learning"
title_zh: ReMA：通过多智能体强化学习让大语言模型学习元思维
authors: "Ziyu Wan, Yunxiang LI, Xiaoyu Wen, Yan Song, Hanjing Wang, Linyi Yang, Mark Schmidt, Jun Wang, Weinan Zhang, Shuyue Hu, Ying Wen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ur295YVtmt"
tags: ["query:agent-papers"]
score: 7.0
evidence: 多智能体强化学习激发LLM元思维行为
tldr: 当前单智能体方法难以有效习得元思维能力——即监控、评估和控制自身推理过程。本文提出ReMA框架，将推理过程解耦为高层元思维智能体和低层基础智能体，利用多智能体强化学习训练两者协作。元思维智能体生成策略性监督信号，基础智能体执行推理。实验表明，ReMA在数学推理等任务上显著提升了LLM的表现，为智能体通过强化学习实现递归自改进提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ur295yvtmt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ur295yvtmt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1429, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ur295yvtmt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1390, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ur295yvtmt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1434, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ur295yvtmt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ur295yvtmt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1255, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ur295yvtmt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1440, \"height\": 736, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ur295yvtmt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1399, \"height\": 1176, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ur295yvtmt/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1438, \"height\": 694, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ur295yvtmt/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 706, \"height\": 969, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ur295yvtmt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1320, \"height\": 1062, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ur295yvtmt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1326, \"height\": 406, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ur295yvtmt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1433, \"height\": 420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ur295yvtmt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1142, \"height\": 1029, \"label\": \"Table\"}]"
motivation: 单智能体方法缺乏有效机制让LLM获得元思维能力，限制了推理的自适应改进。
method: 将推理解耦为高层元思维和低层执行智能体，用多智能体强化学习联合训练。
result: 在数学推理等任务上，ReMA使LLM的推理准确率和适应性显著提升。
conclusion: 多智能体强化学习是激发LLM元思维和自改进能力的有效框架。
---

## Abstract
Recent research on Reasoning of Large Language Models (LLMs) has sought to further enhance their performance by integrating meta-thinking—enabling models to monitor, evaluate, and control their reasoning processes for more adaptive and effective problem-solving.
However, current single-agent work lacks a specialized design for acquiring meta-thinking, resulting in low efficacy.
To address this challenge, we introduce Reinforced Meta-thinking Agents (ReMA), a novel framework that leverages Multi-Agent Reinforcement Learning (MARL) to elicit meta-thinking behaviors, encouraging LLMs to think about thinking.
ReMA decouples the reasoning process into two hierarchical agents: a high-level meta-thinking agent responsible for generating strategic oversight and plans, and a low-level reasoning agent for detailed executions.
Through iterative reinforcement learning with aligned objectives, these agents explore and learn collaboration, leading to improved generalization and robustness.
Empirical results from single-turn experiments demonstrate that ReMA outperforms single-agent RL baselines on complex reasoning tasks, including competitive-level mathematical benchmarks and LLM-as-a-Judge benchmarks.
Additionally, we further extend ReMA to multi-turn interaction settings, leveraging turn-level ratio and parameter sharing to improve efficiency.
Comprehensive ablation studies further illustrate the evolving dynamics of each distinct agent, providing valuable insights into how the meta-thinking reasoning process enhances the reasoning capabilities of LLMs.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：当前大语言模型（LLM）在复杂推理任务中表现出色，但单智能体方法难以有效习得**元思维（meta-thinking）**能力——即让模型监控、评估和控制自身推理过程，以实现更自适应和高效的推理。
- **背景问题**：现有的单智能体RL方法（如R1-like）或基于构造的监督微调方法，要么缺乏灵活探索元思维模式的能力，要么需要在单一前向过程中同时学习元思维与推理，导致探索效率低、易收敛到局部最优，且泛化能力不足。

## 2. 论文提出的方法论

- **核心思想**：提出**ReMA（Reinforced Meta-thinking Agents）**框架，将推理过程解耦为两个层级智能体：  
  - **高层元思维智能体（High-level Meta-thinking Agent）**：负责生成策略性监督和计划（如分解问题、验证步骤等）。  
  - **低层推理智能体（Low-level Reasoning Agent）**：根据高层指令执行详细的推理步骤。  
- **关键技术细节**：
  - 使用**多智能体强化学习（MARL）**训练两个智能体，奖励函数基于最终答案的正确性及格式合规性，并针对高层智能体增加一致性奖励或格式惩罚。
  - 单轮场景（T=1）：高层生成完整元思维轨迹，低层执行并输出答案。
  - 多轮场景（T>1）：通过**参数共享**（两个智能体共用同一模型参数，仅通过角色提示区分）和**轮次级别比率（Turn-level Ratio）** 稳定训练，避免长序列不稳定。
  - 采用的RL算法：**GRPO（Group Relative Policy Optimization）** 和 **REINFORCE++**。
- **算法流程（文字描述）**：
  1. 初始化两个策略π_high和π_low。
  2. 对于每个样本，首先由高层智能体生成元思维指令m，然后低层智能体基于(x, m)生成回答y。
  3. 根据最终答案正确性计算奖励R(y, y*)，分别更新两个智能体的策略。
  4. 在单轮训练中采用交替冻结策略：固定一个智能体，更新另一个；多轮训练中利用参数共享同时更新。

## 3. 实验设计

- **数据集与场景**：
  - **数学推理**：训练集为MATH（7.5k样本），测试集包括分布内（MATH500）和分布外（GSM8K、AIME24、AMC23、Gaokao2023En、Minerva Math、Olympiad Bench）共7个benchmark。
  - **LLM-as-a-Judge**：训练集来自RewardBench（5k样本），测试集为RewardBench970和JudgeBench（分布外）。
- **对比方法**：
  - 基础CoT（VRP）
  - VRP RL（在VRP上应用RL）
  - MRP RL（在单智能体元思维推理过程上应用RL）
  - ReMA（本文方法，MAMRP + RL）
  - 额外的推理时基线：Self-Refine、Multi-Agent Debate（MAD）
- **模型**：Llama-3-8B-Instruct、Llama-3.1-8B-Instruct、Qwen2.5-7B-Instruct（数学推理）；Llama3.1-8B-Instruct和Qwen2.5-7B-Instruct（Judge任务）。

## 4. 资源与算力

- 论文明确提到：
  - 单轮实验使用 **8×NVIDIA A100 GPU**，训练基于OpenRLHF框架，使用bf16、ZeRO-2、Flash-Attention。
  - 多轮实验使用 **32×NVIDIA A800 GPU**，最长训练耗时约40小时（由于大规模验证）。
  - 消融实验使用 **8×NVIDIA A800 GPU**，训练约30小时。
- 细节：未提供精确的GPU小时数，但给出了硬件配置和大致时间，已足够评估计算成本。

## 5. 实验数量与充分性

- **实验数量**：覆盖数学推理的7个数据集 + 2个Judge数据集，共做了约50+组对比实验（包括不同模型、不同方法、不同设置）。
- **消融实验**：
  - 单轮设置下对比三种RL训练方案（RL from Base、RL from SFT、RL under Meta-thinking）。
  - 多轮设置下对比Turn-Ratio vs. Token-Ratio、参数共享 vs. 分离参数。
  - 分析不同奖励函数设计（正确率、格式、一致性）对行为的影响。
- **充分性评估**：实验设计较全面，包括分布内和分布外测试，多模型验证，与多种基线对比，且提供了消融分析。结果使用Pass@1（贪婪解码）报告，部分消融实验包含3个随机种子和置信区间。总体上实验客观、公平，验证了方法的有效性。

## 6. 论文的主要结论与发现

- **ReMA在多数benchmark上超越了所有单智能体RL基线**，尤其是在分布外数据集上，如AMC23（+20%）、AIME24（+13.33%）、RewardBench970（+14.23%）。
- **元思维能够提升低层推理的泛化能力**：相比直接从基础模型RL或从SFT开始RL，基于元思维的RL在难题（如AIME24）上表现出更好的学习动态。
- **多智能体架构显著提升探索效率和结构化学习**：将元思维与推理解耦，使各智能体能专注于自身角色，避免单一模型需要同时掌握两种技能。
- **参数共享与轮次级别比率稳定了多轮训练**：避免了对长序列的不稳定更新，提升了样本效率。
- **较小模型（1B）难以维持有效的元思维**，会退化到简单动作，而较大模型（8B）能根据难度自适应选择策略。

## 7. 优点

- **方法创新**：首次正式定义并利用多智能体强化学习优化元思维推理过程（MAMRP），将高层的策略监督与低层的执行分离，设计巧妙。
- **实验严谨**：覆盖多种模型、多领域任务、分布内与分布外测试，消融实验深入，包括奖励设计和交互动态分析。
- **实用性强**：支持单轮和多轮设置，参数共享策略降低了训练资源需求，易于扩展。
- **可解释性提升**：通过分析不同奖励下智能体的行为反转（如低层智能体主动验证高层输出），揭示了元思维学习中的涌现现象。

## 8. 不足与局限

- **实验覆盖有限**：仅测试了数学推理和LLM-as-a-Judge两个领域，未涉及更多需要多轮交互的复杂任务（如代码生成、多步决策）。
- **对超参数敏感**：多轮训练中，最大响应长度和最大轮次数需要细致调参，否则模型容易陷入“回声陷阱”（大量重复或空响应）。
- **训练稳定性挑战**：多轮MARL仍面临长期信用分配和状态漂移问题，论文指出需要更完善的RL基础设施（如异步rollout、预填充-解码分离）。
- **未探索全收敛分析**：论文提供了迭代训练的收敛性简要分析（基于TRPO和块坐标上升），但未给出严格的理论保证。
- **奖励设计依赖人工规则**：格式奖励等需要手动设定，可能限制方法的通用性。

（完）
