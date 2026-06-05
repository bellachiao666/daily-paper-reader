---
title: Adaptive Context Length Optimization with Low-Frequency Truncation for Multi-Agent Reinforcement Learning
title_zh: 基于低频截断的自适应上下文长度优化用于多智能体强化学习
authors: "Wenchang Duan, Yaoliang Yu, Jiwan He, Yi Shi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=4BsrGHtvW5"
tags: ["query:agent-papers"]
score: 5.0
evidence: 为多智能体强化学习自适应优化上下文长度，提升探索和收敛
tldr: 多智能体强化学习中固定大上下文长度导致探索效率低和信息冗余。论文提出自适应上下文长度优化框架，通过中心智能体利用时序梯度分析动态调整上下文长度。实验表明该方法在长期依赖任务上加速收敛并提升最终性能，为MARL中的记忆管理提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-4bsrghtvw5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1432, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4bsrghtvw5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1320, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4bsrghtvw5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1422, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4bsrghtvw5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 544, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4bsrghtvw5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 566, \"height\": 880, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 895, \"height\": 728, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 816, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1433, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1160, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1283, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1338, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1082, \"height\": 734, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1332, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1453, \"height\": 588, \"label\": \"Table\"}]"
motivation: 固定大上下文长度限制探索效率并引入冗余信息。
method: 设计中心智能体通过时序梯度分析动态调整上下文长度。
result: 在多个MARL基准任务上，自适应上下文长度方法显著提升性能。
conclusion: 动态上下文优化是提升MARL探索效率的有效手段。
---

## Abstract
Recently, deep multi-agent reinforcement learning (MARL) has demonstrated promising performance for solving challenging tasks, such as long-term dependencies and non-Markovian environments. Its success is partly attributed to conditioning policies on large fixed context length. However, such large fixed context lengths may lead to limited exploration efficiency and redundant information. In this paper, we propose a novel MARL framework to obtain adaptive and effective contextual information. Specifically, we design a central agent that dynamically optimizes context length via temporal gradient analysis, enhancing exploration to facilitate convergence to global optima in MARL. Furthermore, to enhance the adaptive optimization capability of the context length, we present an efficient input representation for the central agent, which effectively filters redundant information. By leveraging a Fourier-based low-frequency truncation method, we extract global temporal trends across decentralized agents, providing an effective and efficient representation of the MARL environment. Extensive experiments demonstrate that the proposed method achieves state-of-the-art (SOTA) performance on long-term dependency tasks, including PettingZoo, MiniGrid, Google Research Football (GRF), and  StarCraft Multi-Agent Challenge v2 (SMACv2).

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：在多智能体强化学习（MARL）中，为处理长期依赖和非马尔可夫环境，通常采用固定且较大的上下文长度。然而，这导致两个关键挑战：计算量增加（探索效率低）和输入表示高维化（信息冗余）。现有方法（如优化上下文长度、并行计算）只能获得静态长度，难以适应动态环境，且表示挑战在MARL领域未得到解决。
- **动机**：本文旨在**系统性解决 MARL 中上下文长度增长带来的双重挑战**，实现自适应、高效的上下文信息利用，以提升决策质量和探索效率。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：引入一个**中心智能体（central agent）**，负责动态优化分散智能体（decentralized agents）使用的上下文长度，并通过**傅里叶低频截断**获取全局时间趋势，作为中心智能体的高效输入表示。
- **关键技术细节**：
  - **傅里叶低频截断（Low-Frequency Truncation, LFT）**：
    - 对历史状态序列进行**离散傅里叶变换（DFT）**，将时域数据转换到频域。
    - 采用**Littlewood–Paley理论**中的**二进划分单位分解（Dyadic Partition of Unity）**，构造低通窗口函数和带通窗口函数，截取低于某个阈值（由可调参数 \( m \) 控制）的低频成分，滤除高频噪声和冗余信息。该分解在离散频域上近似满足单位分解（误差随序列长度增大而减小为 \( O(1/t) \)）。
  - **中心智能体自适应上下文长度优化**：
    - **状态**：来自 LFT 模块的低频表示 \( s_t^c \)。
    - **动作空间**：选择不同的低频截断水平 \( m_i \)，对应不同的上下文长度（如 2^m 序列），每个动作对应一个保留的低频频段。
    - **奖励设计**：使用**多头注意力机制**，以中心智能体的价值函数和策略分布作为 Query，各分散智能体的价值函数和策略分布作为 Key，计算注意力权重 \( \omega_t^i \)，加权聚合分散智能体的即时奖励得到中心智能体奖励 \( r_t^c = \sum_i \omega_t^i r_t^i \)。
    - **训练**：通过优势估计（GAE）和策略梯度更新中心智能体参数。
  - **时空解耦学习结构**：
    - 中心智能体独立训练，只处理时序信息；分散智能体利用当前状态和优化后的上下文联合训练其策略和价值函数。这种解耦避免了联合优化带来的巨大参数搜索空间。
- **理论证明**：文中给出**定理1**，证明在动态环境中，自适应上下文长度相对于任何固定长度的长期累积互信息损失下界为 \( \Omega(T) - O(T^\alpha) = \Omega(T) \)（当 \( T \) 足够大时），表明自适应策略的长期优势。

## 3. 实验设计
- **数据集/场景**：
  - PettingZoo Sample Spread（4智能体覆盖3个地标）
  - MiniGrid Soccer Game（15×15格子，3队各3智能体，4个球）
  - Google Research Football (GRF)：Academy 3 vs 1 with Keeper，Academy Counterattack-Hard
  - StarCraft Multi-Agent Challenge v2 (SMACv2)：3s5z_vs_3s6z，5m_vs_6m，corridor
- **Baseline 方法**：
  - 序列处理方法：Transformer、Token Statistics Transformer (ToST)、AMAGO、Mamba
  - 不同固定长度方法（如8,16,32,64步）
  - 不同MARL骨干：MAPPO、QMIX、QPLEX（在SMACv2上）
- **对比与评估**：在主要环境中，对比了与序列处理方法的性能曲线和最终收敛结果；在GRF中对比了固定长度方法；在SMACv2上比较了不同骨干下的性能。所有结果在5个随机种子上平均。

## 4. 资源与算力
- 文中明确指出：**所有实验使用单张 NVIDIA A100 GPU**，最长单次训练大约一个月。
- 未提及具体训练时长分布、并行配置或更多硬件细节。

## 5. 实验数量与充分性
- **实验组数**：涵盖4个主要环境（Sample Spread, MiniGrid, GRF的2个子任务）+ SMACv2的3个子任务 = 共7个主要任务场景，每个场景有与多种baseline的对比。
- **消融实验**：在GRF的2个场景上进行了消融（去除自适应长度ACL、去除低频截断LFT），验证各组件贡献。
- **案例研究**：在MiniGrid上展示自适应长度如何根据奖励调整，直观说明优势。
- **去中心化设置实验**：在SMACv2上测试无跨智能体历史信息共享的情况，确认性能提升源于方法本身而非信息泄露。
- **充分性评价**：实验设计较为全面，覆盖了不同复杂度、不同任务类型（连续控制、离散网格、足球、星际争霸）。报告了均值和标准差，对比了多种前沿方法，消融实验关键。但仍存在一些可改进之处（如未对所有环境进行消融、未提供统计假设检验等）。总体来说**实验较为充分、公平**。

## 6. 主要结论与发现
- **ACL-LFT 在全部长期依赖任务上**均达到SOTA性能，显著优于Transformer、ToST、AMAGO等序列处理方法。
- **自适应上下文长度**在动态环境中远优于任何固定长度方法，验证了定理1的长期优势。
- **低频截断**有效滤除噪声和冗余，为中心智能体提供稳定的全局趋势表示。
- **消融实验**表明：自适应长度（ACL）贡献最大，低频截断（LFT）也显著提升性能，二者互补。
- **去中心化设置**仍能保持优势，证明方法不依赖跨智能体历史信息共享。

## 7. 优点
- **方法创新性**：首次在MARL中系统解决上下文长度增长的双重挑战（计算和表示）。
- **理论贡献**：给出自适应长度优于固定长度的理论下界（定理1），提供严谨数学证明。
- **低频截断机制**：利用成熟信号处理理论和Littlewood–Paley分解，巧妙实现高效冗余过滤。
- **解耦学习结构**：中心智能体与分散智能体分开训练，降低参数搜索复杂度，加速收敛。
- **实验广泛**：在多种典型长期依赖任务、多个baseline、多个骨干算法上验证，结果可复现。

## 8. 不足与局限
- **计算资源**：单次训练需一个月（最长），计算开销较大，未讨论更高效实现或资源要求更低的变体。
- **环境假设**：定理证明中假设环境动力学可用扩散过程近似，且后验高斯，现实中可能不成立；参数 \( \alpha \) 为非确定性，依赖具体环境，削弱了定理的普遍适用性。
- **实验覆盖**：未在真实大规模智能体（如20+）或更具挑战性的非平稳场景（如对抗性环境）下测试；消融实验仅在两个GRF子任务上进行，未在所有环境上重复。
- **统计显著性**：仅报告均值和标准差，未进行假设检验（如t检验）来证明性能差异显著。
- **超参数敏感性**：中心智能体的动作空间（截断水平）和窗口参数的选择未讨论其敏感性或自适应选择方法。
- **潜在偏差**：所有环境均基于公开模拟器，但实验结果对其他未测试的MARL环境（如物流、交通）的推广性仍存在风险。

（完）
