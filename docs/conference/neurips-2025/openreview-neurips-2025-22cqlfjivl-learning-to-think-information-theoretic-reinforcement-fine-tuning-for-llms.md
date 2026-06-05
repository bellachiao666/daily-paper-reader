---
title: "Learning to Think: Information-Theoretic Reinforcement Fine-Tuning for LLMs"
title_zh: 学会思考：面向LLM的信息论强化微调
authors: "Jingyao Wang, Wenwen Qiang, Zeen Song, Changwen Zheng, Hui Xiong"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=22CqLfjiVl"
tags: ["query:agent-papers"]
score: 7.0
evidence: 强化微调提升LLM推理效率
tldr: 大型语言模型推理能力提升但常生成冗长推理链。L2T提出信息论强化微调框架，通过量化每轮信息增益作为密集过程奖励，无需额外标注即可引导模型在保持准确性的同时缩短推理长度。实验表明在多个推理数据集上达到了更优的推理效率。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 535, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 896, \"height\": 312, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1449, \"height\": 979, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1456, \"height\": 913, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 741, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1431, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1437, \"height\": 843, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1385, \"height\": 2161, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-22cqlfjivl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1453, \"height\": 465, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-22cqlfjivl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1454, \"height\": 628, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-22cqlfjivl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 672, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-22cqlfjivl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 714, \"height\": 229, \"label\": \"Table\"}]"
motivation: 现有方法忽视推理效果与效率的平衡，导致不必要的长推理链。
method: 提出基于信息论的过程奖励，将查询-响应交互建模为分层会话，量化每轮参数信息增益进行强化微调。
result: 在多个推理基准上，模型用更少token达到相等或更好的推理准确率。
conclusion: 信息论过程奖励为LLM推理效率优化提供了新方向。
---

## Abstract
Large language models (LLMs) excel at complex tasks thanks to advances in their reasoning abilities. However, existing methods overlook the trade-off between reasoning effectiveness and efficiency, often encouraging unnecessarily long reasoning chains and wasting tokens. To address this, we propose Learning to Think (L2T), an information-theoretic reinforcement fine-tuning framework for LLMs to make the models achieve optimal reasoning with fewer tokens. Specifically, L2T treats each query-response interaction as a hierarchical session of multiple episodes and proposes a universal dense process reward, i.e., quantifies the episode-wise information gain in parameters, requiring no extra annotations or task-specific evaluators. We propose a method to quickly estimate this reward based on PAC-Bayes bounds and the Fisher information matrix. Theoretical analyses show that it significantly reduces computational complexity with high estimation accuracy. By immediately rewarding each episode's contribution and penalizing excessive updates, L2T optimizes the model via reinforcement learning to maximize the use of each episode and achieve effective updates. Empirical results on various reasoning benchmarks and base models demonstrate the advantage of L2T across different tasks, boosting both reasoning effectiveness and efficiency.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：大型语言模型（LLMs）虽然推理能力不断提升，但现有方法（尤其是基于结果奖励的强化学习微调）忽略了推理效果与效率之间的平衡，倾向于生成不必要的长推理链（CoT），浪费大量token，在限定token预算下可能导致性能下降。
- **背景与动机**：实验表明，现有方法往往使用超过正确回答所需最小token数两倍以上的资源；且不同难度的问题对推理长度的需求不同（简单题过长推理反而降低准确率）。现有方法依赖最终结果奖励（sparse outcome reward），缺乏对中间步骤的反馈，无法自适应调整推理深度。此外，基于过程奖励的方法（如ReST-MCTS、MRT）需要任务特定的标注或评估器，泛化性差。
- **整体含义**：提出一种通用的、基于信息论的密集过程奖励，无需额外标注，通过强化学习优化LLM，在保证推理效果的同时极大提升token效率，实现“用最少token做最有效的推理”。

## 2. 论文提出的方法论

### 核心思想
- 将每个查询-回答交互建模为**分层会话（hierarchical session）**，由多个**episode（推理片段）**组成，每个episode对应一段连续推理步骤。
- 设计**信息论密集过程奖励**，包括两部分：**拟合信息增益**（量化当前episode对答案正确率的信息贡献）和**参数压缩惩罚**（抑制冗余信息吸收），无需外部标注或任务特定评估器。
- 通过强化学习（基于GRPO）优化LLM，最大化每个episode的累积奖励，使模型自适应地分配推理深度。

### 关键技术细节
1. **问题重述**：将推理过程分解为K个episode，每个episode结束后计算过程奖励，并结合最终结果奖励。
2. **奖励定义（定义4.1）**：
   - 拟合信息增益：用πθ在生成当前episode前后正确概率之差近似。
   - 压缩惩罚：基于参数互信息增量，通过PAC-Bayes界和Fisher信息矩阵近似。
3. **高效近似（定理4.2）**：利用低秩参数代理（SVD）和高斯假设，将互信息增量近似为参数变化与Fisher矩阵的二次型，复杂度从Θ(d²)降至Θ(r²)，r ≪ d。
4. **优化目标**：最大化结果奖励与过程奖励之和，并受token预算约束。
5. **实现**：在GRPO基础上，对每个rollout按episode分配奖励，再按token概率惊喜度分给每个token，计算组级优势并用于策略梯度更新。

## 3. 实验设计

### 数据集/场景
- **数学推理**：AIME 2024/2025、AMC 2023、MATH500、MinervaMATH、Omni-MATH（4个难度层级）。
- **代码生成**：HumanEval（0-shot和5-shot）。
- 训练数据：DeepScaleR-1.5B-Preview使用919道AIME题（1989-2023）；DeepSeek-R1-Distill-Qwen-1.5B使用NuminaMath随机4000道题。

### Benchmark对比方法
- **基模型**：DeepScaleR-1.5B-Preview、DeepSeek-R1-Distill-Qwen-1.5B、DeepSeek-R1-Distill-Qwen-7B、Qwen2-7B-Instruct。
- **对比方法**：
  - 结果奖励RL（GRPO）
  - 长度惩罚
  - 过程奖励模型：ReST-MCTS、MRT（复现）
  - 消融配置（替换信息增益、移除压缩惩罚、随机层采样）

### 评价指标
- Pass@1准确率、token预算（归一化相对倍数）、准确率与token预算曲线。

## 4. 资源与算力

- **GPU**：A100 GPU集群。
- **超参数**：学习率1e-6，权重衰减0.01，batch size 256，最大prompt长度4096 token，最大补全长度16384 token，训练1~10 epoch。
- **推理设置**：greedy解码（temperature=0），最大生成长度16384。
- **其他**：使用vLLM加速，BF16混合精度，Fisher矩阵阻尼系数1×10⁻⁵。
- **未明确说明**：具体GPU数量、总训练时长。

## 5. 实验数量与充分性

- **主实验**：覆盖5个数学推理数据集 + 代码生成任务；在3种基模型（1.5B、7B）上重复。
- **效率分析**：绘制准确率与token预算曲线，展示L2T在相同预算下更高准确率、更低token消耗。
- **消融实验**：
  - 组件消融（3种变体）
  - 参数灵敏度（α和β网格搜索）
  - 结合MCTS的扩展实验
  - 作为reranking信号（推理时）的评估
- **充分性**：实验设计较为全面，从多任务、多模型、多角度验证了有效性；但未在超大模型（>70B）上验证，且未涉及更多近期推理基准（如web设计等）。结果客观公平，对比方法均为公开基线。

## 6. 论文的主要结论与发现

- L2T在所有测试的数学推理和代码生成基准上，以**更少的token预算**实现了**相等或更好的准确率**。
- 相比结果奖励RL（GRPO），平均提分约3.7%，token效率提升近2倍；相比过程奖励基线（ReST-MCTS、MRT），准确率提升约2%，token效率提升约20-30%。
- 自适应推理深度：简单问题用短链，困难问题用长链，避免过度推理。
- 各组件（拟合信息增益、压缩惩罚、低秩近似）缺一不可，消融实验验证其重要性。
- 参数α=0.8、β=0.6为最优设置。

## 7. 优点

- **设计创新性**：将信息论与强化学习结合，提出通用密集过程奖励，无需外部标注，可跨任务迁移。
- **理论支撑**：提供PAC-Bayes和Fisher近似的复杂度与误差分析（定理D.2、D.3），保证计算可行性与近似精度。
- **实验全面性**：覆盖多种难度、多种基模型、多种对比方法，并做了充分的消融和扩展实验。
- **效率显著**：在保持甚至提升准确率的同时，大幅减少token使用，具有实际部署价值。
- **通用性**：奖励基于模型内部信号，不受输入格式、任务类型限制，可应用于数学、代码等不同推理场景。

## 8. 不足与局限

- **模型规模有限**：未在72B及以上超大模型上验证（受限于资源）。
- **任务覆盖面**：主要集中于数学推理和代码生成，未测试如web导航、对话规划等其他推理任务。
- **超参数敏感性**：α和β需调参（网格搜索），对实际使用有一定成本。
- **近似误差**：低秩SVD和Fisher近似有一定信息损失，可能影响极低token预算下的稳定性。
- **训练数据规模**：部分基模型微调数据量较小（如919道AIME题），未探究更大数据量下的表现。
- **未公开代码/模型**：论文仅提供伪代码，未提及开源计划（但附有项目页面链接）。

（完）
