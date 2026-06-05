---
title: Reinforce LLM Reasoning through Multi-Agent Reflection
title_zh: 通过多智能体反思强化LLM推理
authors: "Yurun Yuan, Tengyang Xie"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=6k3oFS3Lbl"
tags: ["query:agent-papers"]
score: 9.0
evidence: 多智能体反思结合强化学习进行迭代答案改进
tldr: 现有验证-改进范式受限于反馈空间和缺乏协调训练，导致性能次优。本文提出DPSDP算法，将多轮细化过程建模为马尔可夫决策过程，通过直接偏好学习训练演员-评论家LLM系统，在多智能体反思中迭代改进答案。实验表明该方法在推理任务上取得显著提升，为智能体递归自我改进提供了有效框架。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-6k3ofs3lbl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1458, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6k3ofs3lbl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1478, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6k3ofs3lbl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1780, \"height\": 699, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6k3ofs3lbl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 66, \"height\": 70, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6k3ofs3lbl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 117, \"height\": 66, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-6k3ofs3lbl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1617, \"height\": 1572, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6k3ofs3lbl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 875, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6k3ofs3lbl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 880, \"height\": 443, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6k3ofs3lbl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1305, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6k3ofs3lbl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1610, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6k3ofs3lbl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 739, \"height\": 404, \"label\": \"Table\"}]"
motivation: 现有验证-改进方法在LLM推理中反馈空间受限且缺乏协调训练，性能不佳。
method: 将多轮细化建模为MDP，提出DPSDP算法，用直接偏好学习训练演员-评论家系统迭代改进。
result: 在推理任务上性能显著提升，展示了多智能体递归自我改进的有效性。
conclusion: 多智能体反思与强化学习结合可有效实现LLM递归自我改进。
---

## Abstract
Leveraging more test-time computation has proven to be an effective way to boost the reasoning capabilities of large language models (LLMs). Among various methods, the verify-and-improve paradigm stands out for enabling dynamic solution exploration and feedback incorporation. However, existing approaches often suffer from restricted feedback spaces and lack of coordinated training of different parties, leading to suboptimal performance. To address this, we model this multi-turn refinement process as a Markov Decision Process and introduce DPSDP (**D**irect **P**olicy **S**earch by **D**ynamic **P**rogramming), a reinforcement learning algorithm that trains an actor-critic LLM system to iteratively refine answers via direct preference learning on self-generated data. Theoretically, DPSDP can match the performance of any policy within the training distribution. Empirically, we instantiate DPSDP with various base models and show improvements on both in- and out-of-distribution benchmarks. For example, on benchmark MATH 500, majority voting over five refinement steps increases first-turn accuracy from 58.2% to 63.2% with Ministral-based models. An ablation study further confirms the benefits of multi-agent collaboration and out-of-distribution generalization.

---

## 论文详细总结（自动生成）

# 论文《Reinforce LLM Reasoning through Multi-Agent Reflection》详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题背景**：大型语言模型（LLM）在推理任务中可通过增加测试时计算来提升性能，其中“验证-改进”范式（verify-and-improve）允许动态探索解空间并整合反馈，优于链式思维或自一致性等方法。
- **现有局限**：（1）反馈空间受限（如仅编译器信息或固定工具输出）；（2）缺乏对LLM智能体与反馈提供者的联合训练，导致子优交互。
- **本文目标**：提出多智能体反射框架，将多轮细化过程建模为马尔可夫决策过程（MDP），并设计强化学习算法DPSDP（Direct Policy Search by Dynamic Programming），通过直接偏好学习联合训练演员（actor）和评论家（critic），实现迭代答案改进。

## 2. 论文提出的方法论

### 核心思想
- **建模**：将多轮对话（演员生成答案、评论家提供反馈、演员根据反馈细化）形式化为一个固定步长（H=2L+1）的马尔可夫决策过程（MDP）。状态为当前问题与最近一次答案（缩减上下文），动作为LLM输出，奖励为答案正确性。
- **算法灵感**：基于经典策略搜索动态规划（PSDP），但直接优化KL正则化目标以避免离散动作空间限制。

### 关键技术细节
1. **KL正则化策略优化**：
   - 对每个时间步 \( h \)，目标为：
     \[
     \hat{\pi}_h = \arg\max_{\pi} \mathbb{E}_{s_h\sim d_{\pi_{\text{ref}}}^h, a_h\sim\pi} \left[ Q^{\hat{\pi}_{h+1}}(s_h, a_h) - \beta D_{KL}[\pi(\cdot|s_h) \| \pi_{\text{ref}}(\cdot|s_h)] \right]
     \]
   - 闭式解：\(\hat{\pi}(a|s) \propto \pi_{\text{ref}}(a|s) \exp(Q(s,a)/\beta)\)。

2. **数据收集与偏好学习**：
   - 从参考策略 \(\pi_{\text{ref}}\) 采样完整轨迹 \((x, a_0, a_1, a_2)\)（仅一个细化步）。
   - 在每个状态 \(s_h\) 生成 \(n\) 个候选响应，利用Q值估计（见下）选择正负对，构建DPO数据集。
   - 将原始交叉熵损失简化为DPO损失：
     \[
     L_{\text{DPO}} = -\mathbb{E}_{(s_h, a_h^+, a_h^-)} \left[ \log \sigma\left(\beta \log\frac{\pi(a_h^+|s_h)}{\pi_{\text{ref}}(a_h^+|s_h)} - \beta \log\frac{\pi(a_h^-|s_h)}{\pi_{\text{ref}}(a_h^-|s_h)}\right) \right]
     \]

3. **Q值估计**：
   - 对演员的细化答案 \(a_2\)：用其即时正确性作为Q值。
   - 对评论家的反馈 \(a_1\)：使用 \(\pi_{\text{ref}}\) 生成一个细化答案，取其正确性作为Q值。
   - 对演员的首次答案 \(a_0\)：直接用其正确性（因与最终Q值高度相关）。

4. **实践简化**：
   - **上下文缩减**：状态仅包含问题、最近一次答案和对应反馈（忽略历史），使模型不受训练时视野限制。
   - **训练时仅用一步细化**（H=3），但测试时可推广到任意多轮。
   - **统一训练**：将各时间步的DPO数据合并，一次性优化演员（用 \(D_0 \cup D_2\)）和评论家（用 \(D_1\)）。

5. **预训练阶段**：先用更强模型（如Mistral-Large）生成反馈和细化答案，对基座模型进行有监督微调（SFT），使它们具备基本的反馈和细化能力，再应用DPSDP。

### 算法流程（文字说明）
1. 初始化：使用参考策略 \(\pi_{\text{ref}}\)，预训练后的演员和评论家。
2. 对于每个训练问题 \(x\)：
   - 从 \(\pi_{\text{ref}}\) 采样轨迹 \((x, a_0, a_1, a_2)\)。
   - 对于每个时间步 \(h=0,1,2\)，采样 \(n\) 个候选动作，估计其Q值，选择正负对存入数据集 \(D_h\)。
3. 合并数据集，用DPO损失分别训练演员（\(D_0 \cup D_2\)）和评论家（\(D_1\)）。
4. 输出最终策略 \(\hat{\pi} = (\hat{\pi}_a, \hat{\pi}_c)\)。

## 3. 实验设计

### 使用数据集
- **训练集**：OpenMathInstruct-2（从MATH和GSM8K增强或采样）。
- **测试基准**：
  - 同分布（ID）：MATH 500、GSM8K
  - 分布外（OOD）：MMLU-Pro Math、Olympiad Bench

### 评估指标
- **pass1@turn1**：首次答案准确率。
- **maj1@turn5**：5次答案（1次初始+4次细化）多数投票准确率。
- **pass1@turn5**：5次答案中至少一次正确的准确率。

### 对比方法
- **基准方法**：
  - **STaR**：仅用最终正确轨迹的SFT。
  - **STaR-DPO**：与STaR相同数据收集，但加入错误轨迹进行DPO训练。
  - **Oracle-RISE**：使用真实反馈的Oracle模型（仅Ministral-8B）。
- **消融变体**：
  - 非生成式评论家（仅二元反馈）
  - 单智能体（演员与评论家为同一模型）
  - 非马尔可夫设置（保留完整历史）
  - 无“重启”数据收集（直接采样完整轨迹而非从各状态重新采样）
  - 无SFT预训练

### 基础模型
- Ministral-8B-Instruct-2410
- Llama-3.1-8B-Instruct
- Qwen2.5-3B

## 4. 资源与算力

- **硬件**：4 × H100 80GB GPU。
- **训练**：
  - SFT阶段：学习率1e-6（Llama）或5e-6（Ministral、Qwen），梯度累积64步，训练1 epoch。
  - DPO阶段：学习率2e-7或4e-7，KL系数β=0.1~1.0，梯度累积64步，训练1~3 epochs。
- **推理**：vLLM离线引擎，温度T=0（除自一致性用0.5），数据采集用T=1.0。
- **论文未报告总GPU小时数或完整训练时长**，但给出了典型配置。

## 5. 实验数量与充分性

- **主要实验**：在3种基座模型上评估ID + OOD共4个基准，报告3个指标，形成12个主要结果表（Table 1）。
- **消融实验**：至少包括6组系统消融：
  - 单智能体 vs 多智能体
  - 马尔可夫 vs 非马尔可夫
  - 重启 vs 非重启数据收集
  - 有无SFT预训练
  - 生成式 vs 非生成式评论家
  - 统一训练 vs 逐步训练
  - 多轮细化动态分析（图3、表4）
- **充分性**：实验设计全面，覆盖了关键设计选择，对比基线公平（所有基线使用相同SFT起点）。结果统计了多次重复（如不明确但多数投票已降低随机性）。论文未提供置信区间或显著性检验，但多模型、多基准的复现增强了可信度。

## 6. 主要结论与发现

1. **DPSDP有效提升推理性能**：例如Ministral模型在MATH 500上maj1@turn5从57.2%提升至63.2%（相对SFT），且OOD基准（如Olympiad Bench）也有提升。
2. **多智能体优于单智能体**：在困难基准（MATH 500、Olympiad）上多智能体显著更强；简单任务（GSM8K）上单智能体略优。
3. **马尔可夫状态设计优于非马尔可夫**：仅用最近答案的设定减少了分布漂移，性能更好。
4. **重启数据收集优于无重启**：从中间状态重新采样可促进探索。
5. **SFT预训练必不可少**：无SFT时DPSDP几乎无提升（仅+1.2%）。
6. **生成式评论家优于非生成式**：生成式评论家在困难任务上优势明显，非生成式在简单任务上略优（可能因避免过度思考）。
7. **DPSDP可推广到更多细化轮次**：正确率随轮次增加而提升，且错误修正比例始终高于引入新错误的比例。

## 7. 优点

- **理论保证**：提供了性能界（Theorem 1），在单策略可集中性和有界分布内泛化误差下，DPSDP可匹配任何策略。
- **实用简化**：通过上下文缩减、单步训练、统一DPO训练，降低了实现复杂度并支持测试时无限细化。
- **泛化能力强**：在OOD基准上仍有效，说明模型学到了迭代改进能力而非记忆。
- **多智能体协同**：联合训练演员和评论家，利用灵活的自然语言反馈，而非固定信号。
- **消融实验系统**：清晰揭示了关键设计（马尔可夫、重启、生成式反馈、预训练）的价值。

## 8. 不足与局限

- **依赖离线数据**：使用参考策略 \(\pi_{\text{ref}}\) 生成数据，未探索在线/迭代DPO（作者也指出这是未来方向）。
- **未覆盖所有任务域**：实验限于数学推理，未评估代码、常识推理等场景。
- **非马尔可夫设置性能下降**：全历史上下文虽更丰富但引入分布漂移，可能需更复杂的状态设计。
- **超参数敏感性**：β值选择对性能有影响，实验仅在0.1~1.0之间调参，未系统研究。
- **计算资源未完整报告**：缺乏总GPU小时数，不利于复现对比。
- **单智能体在简单任务上的优势**暗示混合生成目标可能带来提升，但论文未深入。
- **非生成式评论家虽简单但性能受限**，且文中未讨论其值函数训练细节（如奖励归一化）。

（完）
