---
title: Agent-Centric Actor-Critic for Asynchronous Multi-Agent Reinforcement Learning
title_zh: 面向异步多智能体强化学习的以智能体为中心的Actor-Critic算法
authors: "Whiyoung Jung, Sunghoon Hong, Deunsol Yoon, Kanghoon Lee, Woohyung Lim"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=323GZNnGqe"
tags: ["query:agent-papers"]
score: 5.0
evidence: 多智能体RL，使用宏动作支持长程规划
tldr: 该论文提出ACAC算法，以智能体为中心的编码器独立处理轨迹，注意力聚合模块形成集中式评论家，处理宏动作异步性。支持长程规划，在稀疏奖励环境中改善协调。虽无递归自改进，但对多智能体长程推理有贡献。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 771, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 786, \"height\": 325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 1198, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 865, \"height\": 720, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 737, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 846, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1785, \"height\": 1161, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 863, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 861, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1482, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1751, \"height\": 1144, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1744, \"height\": 1735, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1783, \"height\": 1157, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1781, \"height\": 796, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1784, \"height\": 797, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-323gznngqe/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 1290, \"label\": \"Table\"}]"
motivation: 宏动作引入异步，现有CTDE方法使用填充导致假相关。
method: ACAC使用智能体中心编码器独立处理轨迹，注意力机制聚合历史到集中式评论家。
result: 在需要长程规划的多智能体任务中，ACAC优于基线方法。
conclusion: 有效管理异步性，提升多智能体长程协调性能。
---

## Abstract
Multi-Agent Reinforcement Learning (MARL) struggles with coordination in sparse reward environments. Macro-actions —sequences of actions executed as single decisions— facilitate long-term planning but introduce asynchrony, complicating Centralized Training with Decentralized Execution (CTDE). Existing CTDE methods use padding to handle asynchrony, risking misaligned asynchronous experiences and spurious correlations. We propose the Agent-Centric Actor-Critic (ACAC) algorithm to manage asynchrony without padding. ACAC uses agent-centric encoders for independent trajectory processing, with an attention-based aggregation module integrating these histories into a centralized critic for improved temporal abstractions. The proposed structure is trained via a PPO-based algorithm with a modified Generalized Advantage Estimation for asynchronous environments. Experiments show ACAC accelerates convergence and enhances performance over baselines in complex MARL tasks.

---

## 论文详细总结（自动生成）

### 论文中文详细总结

#### 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：多智能体强化学习（MARL）在稀疏奖励环境中面临协调困难，智能体难以从稀疏反馈中推断个体动作对集体性能的影响，需要大量探索。
- **现有方案的局限性**：
  - 宏动作（macro-action）——将一系列微观动作打包为高层决策——有助于长期规划，但导致智能体动作选择时刻变得异步（不同智能体完成宏动作的时间不同）。
  - 集中式训练分散式执行（CTDE）框架在同步场景中有效，但直接应用于异步环境时，现有方法（如 Xiao et al., 2020a,b）采用**填充（padding）** 缺失观测信息的方式，即用智能体最近一次观测填补缺失时刻。这会导致**误导性信息抽象**和**虚假相关性**，降低学习效率。
- **研究动机**：提出一种无需填充的异步MARL方法，以更准确地处理异构轨迹，加速学习并提升最终性能。

#### 2. 方法论：核心思想、关键技术细节
- **核心思想**：利用**以智能体为中心的历史编码器**分别处理每个智能体的轨迹，再通过**注意力聚合模块**将这些独立历史整合到集中式评论家中，从而避免填充带来的冗余和不准确。
- **关键技术细节**：
  1. **Agent-Centric Encoder（智能体中心编码器）**：
     - 每个智能体拥有独立的历史编码器（GRU + MLP），输入包括当前宏观测 `z_i^t` 和对应时间步 `p_i^t`（通过正弦位置编码嵌入），以捕获时间间隔信息。
     - 仅在智能体获得新宏观测时更新隐状态；未获得新观测的智能体使用最新的隐状态，无需填充。
  2. **Centralized Critic（集中式评论家）**：
     - 收集所有智能体当前隐状态 `h_i^t`，通过**自注意力（Self-Attention）** 模块进行交互聚合，再经过平均池化和MLP输出全局价值估计 `V_ψ(˜h_t)`。
     - 该设计消除了传统填充方法中重复使用旧观测造成的假相关。
  3. **Actor（分散式执行器）**：
     - 每个智能体的策略 `π^i_θi` 基于其自身的隐状态 `h_i^t` 选择宏动作。
  4. **训练算法**：
     - 基于PPO（Proximal Policy Optimization）的Actor-Critic框架，采用裁剪替代目标 `L(θ_i) = E[min(ρ·A, clip(ρ)·A)]`，其中 `ρ` 为重要性采样比。
     - 集中式评论家通过回归目标值函数 `L(ψ) = E[(ˆR_t - V_ψ(˜h_t))^2]` 训练，并使用PopArt进行值归一化。
  5. **改进的GAE（广义优势估计）**：
     - 针对异步环境，提出**宏级λ-折扣（Macro-level λ-discounting）**：λ的幂指数基于宏决策步数（macro-timestep）而非微观时间步，从而避免长宏动作未来奖励被过度折扣。
     - 公式：`A^λ_macro_{l(0)} = Σ_{k=0}^{∞} λ^k γ^{l(k)-l(0)} δ_{l(k)}`，其中 `δ_{l(k)}` 为多步TD误差。
- **算法流程**（文字说明）：
  - 收集轨迹：每个智能体执行宏动作直至终止；每当任一智能体获得新宏观测时，记录该时刻的所有智能体隐状态、动作和奖励。
  - 计算TD误差 `δ` 和GAE优势 `A`（使用宏级折扣）。
  - 使用PPO更新每个Actor网络，使用MSE损失更新集中式Critic。
  - 重复直至收敛。

#### 3. 实验设计
- **数据集/场景**：
  - **BoxPushing**（3种地图尺寸：6×6、8×8、10×10）：两个智能体合作推动大箱子到目标区域，奖励稀疏。
  - **Overcooked**（3种地图A/B/C，7×7网格）：三个智能体共同准备沙拉并交付，包含切菜、装盘等宏动作。
  - **Overcooked-Rand**（随机化初始位置）：增加不确定性，测试泛化能力。
  - **Overcooked-Large**（11×11网格，6个智能体）：更具挑战性的大规模场景。
- **Benchmark比较方法**：
  - **Mac-NIACC**（独立Actor+单个集中式Critic，使用填充）。
  - **Mac-IAICC**（独立Actor+为每个智能体分配独立Critic，使用填充）。
  - **ACAC-Vanilla**（与ACAC架构相同但未使用PPO损失函数）。
  - **Micro-action baselines**：标注 `micro`（即不使用宏动作的标准同步MARL），如MAPPO-micro、ACAC-micro等。
- **评估指标**：无折扣回报（undiscounted return），每个实验5个随机种子，报告均值和标准误。

#### 4. 资源与算力
- 明确说明在附录G：
  - GPU型号：**NVIDIA A10**。
  - CPU：**AMD EPYC 7453 28-Core Processor**。
  - 运行时长：
    - Overcooked环境：约**24–150小时**。
    - BoxPushing环境：约**30分钟–2小时**。
  - 未提及使用的GPU数量（推测为单卡或少量）。

#### 5. 实验数量与充分性
- **实验组数**：
  - 主实验：在BoxPushing（3个地图）、Overcooked（3个地图）、Overcooked-Rand（3个地图）、Overcooked-Large（6个地图）上进行，每个环境5个随机种子。
  - 消融实验：
    - **填充消除**：对比ACAC vs. ACAC-Duplicate（复制宏观测模拟填充）。
    - **GAE折扣选择**：宏级λ折扣 vs. 微级λ折扣。
    - 超参数敏感性：裁剪比例ϵ。
    - 组件消融：时间嵌入（TE）、自注意力（SA）的影响。
  - 共涉及约9+9+9+6 ≈ 33个独立环境×5种子，以及多种消融变体。
- **充分性评价**：
  - 实验覆盖多种难度和随机化场景，环境设计具有代表性。
  - 对比方法包括切片宏动作和微观动作基线，消融实验验证了核心设计选择。
  - 统计报告（均值±标准误差）可信，5个种子数量合理。
  - **不足之处**：未在连续动作空间或更实际的任务（如机器人控制）上验证，仅局限于离散宏动作场景。基线方法未包含近年最先进的MARL算法（如QMIX的异步变体），但论文指出当前异步MARL文献中此类方法较少，可接受。

#### 6. 主要结论与发现
- **ACAC在所有任务上收敛更快、最终回报更高**，显著超过填充基线（Mac-NIACC、Mac-IAICC）以及微观动作方法。
- **消除填充至关重要**：与ACAC-Duplicate对比，ACAC避免了重复宏观测导致的误导信号，从而获得更优性能。
- **宏级λ-折扣优于微级λ-折扣**：在GAE中采用宏级折扣策略更符合异步环境特性，稳定提升学习效果。
- **ACAC-Vanilla仍优于大部分基线**，说明架构本身有效；加入PPO目标后（ACAC）进一步提升。
- **在Overcooked-Large等更大、更复杂场景中，ACAC的优势更为突出**，而基线方法常无法有效学习。

#### 7. 优点（方法或实验设计的亮点）
- **方法亮点**：
  - **智能体中心历史编码**：独立编码每个智能体轨迹，仅在观测到来时更新，避免填充冗余，且自然适配异步事件流。
  - **注意力聚合模块**：使评论家能够捕捉智能体间交互，同时保持输入维度固定，扩展性好。
  - **改进的GAE**：宏级折扣直接针对宏决策时刻，解决了异步中不同时步长带来的偏差-方差权衡问题。
  - **PPO训练稳定**：采用裁剪替代目标有效约束策略更新，结合PopArt归一化提升训练稳定性。
- **实验设计亮点**：
  - 引入随机化环境（Overcooked-Rand）和大规模环境（Overcooked-Large）测试泛化和扩展能力。
  - 消融实验设计干净：ACAC-Duplicate直接隔离填充影响，宏级/微级GAE对比明确。
  - 开放代码和超参数，可复现性好。

#### 8. 不足与局限
- **动作空间限制**：当前仅适用于离散宏动作空间，扩展到连续动作空间是作者指出的未来方向，需开发相应的连续异步基准。
- **实验覆盖局限**：仅在BoxPushing和Overcooked两类环境上测试，缺乏更多领域（如机器人、自动驾驶）的验证，可能存在过拟合特定任务的风险。
- **预定义宏动作**：假设宏动作已设计好，未解决如何自动发现或学习宏动作的问题，限制了在无先验宏动作场景的适用性。
- **通信假设**：集中式评论家训练时需获取所有智能体历史（即使智能体不发送新观测时也要访问隐状态），在实际分布式部署中可能有通信成本。
- **算力细节模糊**：虽提及时长，但未说明具体GPU数量，且未与其他方法进行同等环境下的计算开销比较（如填充方法可能更快？）。

（完）
