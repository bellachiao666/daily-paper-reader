---
title: Revisiting Cooperative Off-Policy Multi-Agent Reinforcement Learning
title_zh: 重访协作式离策略多智能体强化学习
authors: "Yueheng Li, Guangming Xie, Zongqing Lu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=JPkJAyutW0"
tags: ["query:agent-papers"]
score: 4.0
evidence: 协作式多智能体强化学习方法
tldr: 本文针对协作式离策略多智能体强化学习中的Q目标估计错误问题，提出了一套包括退火多步引导在内的方法，有效缓解了因动作空间指数增长带来的可扩展性挑战，实验表明该方法在多个基准任务上提升了性能，为大规模多智能体协作提供了更稳定的训练框架。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 851, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 830, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 835, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 840, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1548, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1644, \"height\": 748, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1731, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1744, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 823, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1714, \"height\": 731, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1729, \"height\": 785, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1712, \"height\": 972, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1727, \"height\": 359, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jpkjayutw0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1247, \"height\": 878, \"label\": \"Table\"}]"
motivation: 现有离策略多智能体方法因联合动作空间过大导致Q目标估计错误，限制了可扩展性。
method: 提出退火多步引导等技术，修正Q目标估计，提升训练稳定性。
result: 在多个标准MARL任务上验证了方法的有效性，降低了估计误差，提高了协作性能。
conclusion: 该工作为大规模协作多智能体系统提供了实用的训练改进方案。
---

## Abstract
Cooperative Multi-Agent Reinforcement Learning (MARL) has become a critical tool for addressing complex real-world problems. 
However, off-policy MARL methods, which rely on joint Q-functions, face significant scalability challenges due to the exponentially growing joint action space.
In this work, we highlight a critical yet often overlooked issue: erroneous Q-target estimation, primarily caused by extrapolation error.
Our analysis reveals that this error becomes increasingly severe as the number of agents grows, leading to unique challenges in MARL due to its expansive joint action space and the decentralized execution paradigm.
To address these challenges, we propose a suite of techniques tailored for off-policy MARL, including annealed multi-step bootstrapping, averaged Q-targets, and restricted action representation. Experimental results demonstrate that these methods effectively mitigate erroneous estimations, yielding substantial performance improvements in challenging benchmarks such as SMAC, SMACv2, and Google Research Football.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：协作式多智能体强化学习（MARL）中，离策略（off-policy）方法因依赖联合 Q 函数，面临严重的可扩展性挑战。特别是随着智能体数量增加，联合动作空间呈指数增长，导致 Q 目标估计中出现严重的**外推误差（extrapolation error）**，进而引起**Q 目标估计误差（TEE）**，使性能显著下降。
- **研究动机**：已有工作多关注目标近似误差（TAE），而忽视了 TEE 的影响。作者通过误差分解和实验（图2）证明，TEE 在 MARL 中远大于 TAE，且随智能体数量增加而恶化，是制约离策略方法性能的关键瓶颈。
- **整体意义**：揭示 TEE 的本质并设计针对性缓解技术，为大规模离策略 MARL 提供更稳定、高效的训练框架，具有理论价值和实际意义。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：通过降低对 Q(s', a') 的依赖、减少目标估计方差、限制联合动作空间的影响，从三个不同角度缓解 TEE。
- **关键技术细节**：
  - **退火多步引导（Annealed Multi-Step Bootstrapping）**：采用 Peng's Q(λ)（PQL）算子，用多步回报替代单步 TD 目标，降低对未训练 Q 值的依赖。通过 λ 退火策略（从 1 衰减到 λ*），在训练初期利用大 λ 减少误差，后期减小 λ 避免策略偏差。
  - **平均 Q 目标（Averaged TD Target）**：对多个独立 Q 函数（或个体效用）取平均，利用方差降低性质（方差与 1/M 成正比）提升目标精度。对于值分解方法，只平均个体效用网络，不平均混合网络。
  - **受限动作表示（Restricted Action Representation, RAR）**：对直接使用联合 Q 函数的方法（如 MADDPG），用映射函数 g(a) 将高维联合动作压缩至低维离散空间；对 QPLEX，通过 Sigmoid 限制权重 λ_i 在 [0,1] 内，避免异常值积累。
- **公式/算法流程**：误差分解公式 (4)；PQL 算子定义 (5)；误差传播上界 (7)；平均 Q 目标损失函数 (9)；λ 退火公式 (13)；算法伪代码见 Algorithm 1（AEQMIX）。

## 3. 实验设计：数据集/场景、Benchmark、对比方法

- **场景与 Benchmark**：
  - SMAC（StarCraft Multi-Agent Challenge）：含 Easy、Hard、Super Hard 地图。
  - SMACv2：更具随机性和部分可观测性，含多种族（zerg/protoss/terran）5v5、10v10、20v20、10v11、20v23 等 15 个地图。
  - Google Research Football (GRF)：含 5 个场景（如 3_vs_1_with_keeper、counterattack_easy/hard 等）。
- **对比方法**：
  - 基线算法：QMIX、VDN、QPLEX、FACMAC、MADDPG。
  - 改进版本：AEQMIX、AEVDN、AEQPLEX-RAR、AEFACMAC、AEMADDPG-RAR。并对比了不同 λ、不同集成大小 M、不同网络隐藏尺寸的消融。

## 4. 资源与算力

- **文中未明确说明**使用的 GPU 型号、数量、训练时长等算力信息。仅提及使用了并行 runner（batch size 8/4/32）、buffer size 等超参数。未提及具体硬件配置和总训练时间。

## 5. 实验数量与充分性

- **实验数量**：
  - SMAC：4 张地图（1 Easy, 1 Hard, 2 Super Hard）。
  - SMACv2：15 张地图（5 个种族 × 3 种规模 × 额外数量不对称场景）。
  - GRF：5 个场景。
  - 消融实验：调整 λ、集成大小 M、网络隐藏尺寸；对比不同悲观程度的目标（类似 REDQ）；对比不同数量混合网络；验证 RAR 对 QPLEX 和 MADDPG 的影响。
  - 还给出了 TEE 和方差随 λ、M 变化的定量分析（图9）。
- **充分性与公平性**：
  - 实验覆盖了多种不同类型的方法（值分解、策略梯度）和挑战性基准，验证了方法的通用性。
  - 控制变量设计（如仅改变网络尺寸而非参数数量来排除容量影响）表明性能提升源于更准确的目标估计。
  - 对比基线和消融均采用相同代码库（pymarl2，FACMAC 官方代码），超参数一致，**公平客观**。
  - 但 SMACv2 的 15 张地图中有部分未展示完整的学习曲线（仅展示部分代表性图），全文图5-8、11-13 共显示约20+条曲线，总体充足。

## 6. 论文的主要结论与发现

- **主要发现**：TEE（目标估计误差）是离策略 MARL 性能下降的核心原因，主要由外推误差驱动；随智能体数量增加而恶化。
- **关键理论**：单调性（∂Q/∂Qi ≥ 0）是错误传播一致性（EPC）的充要条件，单调值分解能使联合 Q 函数的误差控制有效传递至个体效用，从而通过在线交互自纠正。
- **方法有效性**：退火多步引导、平均 Q 目标、受限动作表示三者结合能显著提升多种离策略方法的性能，在 SMACv2 等高难度任务中，改进版 AEQMIX 相比 QMIX 性能大幅提升（如图6）。
- **意外发现**：简单地增加网络参数量（如扩大隐藏层）反而恶化性能，说明问题不在于表达能力而在于目标估计精度。

## 7. 优点：方法或实验设计上的亮点

- **理论分析深入**：从误差分解（TAE/TEE/OD）出发，明确指出 TEE 是关键，并通过实验量化其严重性。
- **方法通用且轻量**：提出的三项技术可轻松嵌入现有离策略方法（值分解、策略梯度），无需改变训练范式。
- **实验严谨**：
  - 通过比例统计（图2左）直观展示外推比例随智能体数增长。
  - 消融实验分别验证了 λ 退火、集成大小、网络容量、悲观目标等的影响，剥离了混杂因素。
  - 在多个差异显著的环境（SMAC、SMACv2、GRF）验证，增强结论鲁棒性。
- **理论保证**：给出 TEE 传播上界（命题4.1），并从统计角度解释平均目标降低方差（公式8）。

## 8. 不足与局限

- **实验覆盖**：未在连续动作空间场景（如 Multi-Agent Particle Environment 的 continuous 版本）或超大规模（>20 个智能体）环境中的非对称任务进行验证；GRF 仅测试 5 个场景，且主要展示 QMIX 的改进，对 VDN、QPLEX 的 GRF 结果未展示。
- **假设依赖**：平均 Q 目标有效降低方差依赖于各 Q 函数误差独立同分布的假设，实际可能因共享训练数据不严格满足；退火 λ 策略基于启发式，缺乏理论最优性保证。
- **RAR 技术局限**：对 MADDPG 的 RAR 需要额外学习映射网络，且可能限制联合策略的表达能力，在需要精细协调的任务中可能损失性能。
- **未讨论离线/离线-在线混合设置**：尽管外推误差概念与离线 RL 相关，论文仅针对在线 RL，未探讨所提方法在离线场景下的适用性。
- **算力资源未报告**：不利于复现和公平比较成本。

（完）
