---
title: In-Context Fully Decentralized Cooperative Multi-Agent Reinforcement Learning
title_zh: 上下文完全去中心化合作多智能体强化学习
authors: "Chao Li, Bingkun BAO, Yang Gao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=5J4IpiMKkq"
tags: ["query:agent-papers"]
score: 6.0
evidence: 完全去中心化合作多智能体强化学习方法，解决非平稳性和过度泛化
tldr: 在完全去中心化合作多智能体强化学习中，每个智能体仅能访问本地信息，导致非平稳性和相对过度泛化问题。现有方法无法同时解决两者。本文提出返回感知上下文（RAC），通过将动态变化的任务形式化为每个智能体本地感知的上下文，使智能体能够隐式建模联合策略。实验证明，RAC在多个去中心化合作任务中显著优于现有方法，为多智能体协作提供了简单有效的去中心化解决方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-5j4ipimkkq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1315, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5j4ipimkkq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 977, \"height\": 807, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5j4ipimkkq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1389, \"height\": 1016, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5j4ipimkkq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1392, \"height\": 651, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5j4ipimkkq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1389, \"height\": 1019, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-5j4ipimkkq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 367, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5j4ipimkkq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 501, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5j4ipimkkq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 502, \"height\": 177, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5j4ipimkkq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1089, \"height\": 418, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5j4ipimkkq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 937, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5j4ipimkkq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1433, \"height\": 397, \"label\": \"Table\"}]"
motivation: 完全去中心化设置下同时存在非平稳性和相对过度泛化问题，现有方法无法兼顾。
method: 提出返回感知上下文（RAC），将任务上下文形式化为本地感知表示，隐式建模联合策略。
result: 在多个去中心化基准上，RAC显著优于现有方法，同时解决了两个关键问题。
conclusion: RAC是一种简单有效的去中心化多智能体协作方法。
---

## Abstract
In this paper, we consider fully decentralized cooperative multi-agent reinforcement learning, where each agent has access only to the states, its local actions, and the shared rewards. The absence of information about other agents' actions typically leads to the non-stationarity problem during per-agent value function updates, and the relative overgeneralization issue during value function estimation. However, existing works fail to address both issues simultaneously, as they lack the capability to model the agents' joint policy in a fully decentralized setting. To overcome this limitation, we propose a simple yet effective method named Return-Aware Context (RAC). RAC formalizes the dynamically changing task, as locally perceived by each agent, as a contextual Markov Decision Process (MDP), and addresses both non-stationarity and relative overgeneralization through return-aware context modeling. Specifically, the contextual MDP attributes the non-stationary local dynamics of each agent to switches between contexts, each corresponding to a distinct joint policy. Then, based on the assumption that the joint policy changes only between episodes, RAC distinguishes different joint policies by the training episodic return and constructs contexts using discretized episodic return values. Accordingly, RAC learns a context-based value function for each agent to address the non-stationarity issue during value function updates. For value function estimation, an individual optimistic marginal value is constructed to encourage the selection of optimal joint actions, thereby mitigating the relative overgeneralization problem. Experimentally, we evaluate RAC on various cooperative tasks (including matrix game, predator and prey, and SMAC), and its significant performance validates its effectiveness.

---

## 论文详细总结（自动生成）

好的，以下是对论文《In-Context Fully Decentralized Cooperative Multi-Agent Reinforcement Learning》的详细中文总结：

### 1. 核心问题与整体含义

-   **研究动机**：在多智能体合作强化学习中，**完全去中心化学习**（每个智能体只能访问自身状态、动作和共享奖励，无法获取其他智能体的动作）面临两个核心挑战：
    1.  **非平稳性**：其他智能体的策略在不断变化，导致智能体的本地环境动态发生变化，破坏了价值函数更新的收敛性。
    2.  **相对过度泛化**：智能体的本地价值估计会受到其他智能体探索性次优动作的影响，导致对联合动作的价值评估产生偏差，使智能体偏好于次优的联合动作。
-   **现有不足**：现有的完全去中心化方法通常只能解决上述两个问题中的一个，因为它们无法在完全去中心化的设定下有效建模智能体的联合策略。
-   **论文贡献**：本文提出了一种名为**回报感知上下文（RAC）** 的简单有效方法，通过将智能体本地感知的动态变化任务形式化为一个上下文马尔可夫决策过程（Contextual MDP），并利用`训练回合回报`来隐式地建模联合策略，从而**同时解决**非平稳性和相对过度泛化两大问题。

### 2. 方法论

-   **核心思想**：
    -   **任务形式化**：将每个智能体面临的非平稳局部任务建模为上下文MDP。其中，每个上下文 \( c \) 对应其他智能体的一种特定联合策略 \( \pi^{-i} \)。智能体的非平稳性问题被归结为不同上下文之间的切换。
    -   **上下文建模**：基于联合策略仅在回合间更新这一常见假设，本文提出用`训练回合的累积回报`来区分不同的联合策略。通过将回报离散化为 \( m \) 个区间，每个区间对应一个上下文 \( c_\kappa \)。这样，每个智能体都能独立地根据其本地轨迹的回报来估计当前的联合策略。
-   **关键技术细节**：
    1.  **基于上下文的价值函数 \( Q^i(s_t, c_\kappa, a_t^i) \)**：为每个智能体学习一个价值函数，其输入除了状态和动作外，还包括上下文 \( c_\kappa \)。这使得价值函数的更新基于更平稳的增广转换 \( (s_t, a_t^i, c_\kappa, r_t, s_{t+1}) \)，从而解决了非平稳性问题。
    2.  **个体乐观边际价值 \( \phi^i(s_t, a_t^i) \)**：定义为 \( \phi^i(s_t, a_t^i) = \max_{c_\kappa} Q^i(s_t, c_\kappa, a_t^i) \)。这个值假设其他智能体总是选择其最优的协作动作，因此在估计时消除了其他智能体次优动作的影响，解决了相对过度泛化问题。
    3.  **辅助学习过程**：为了解决训练早期回报空间覆盖不全的问题，RAC额外学习了一个独立的价值函数 \( Q^{i,S}(s_t, a_t^i) \) 来负责动作选择。同时，通过一个辅助监督损失函数 \( L_{sup} \)，让 \( Q^{i,S} \) 模仿由 \( \phi^i \) 推导出的策略，从而将解决两个问题的能力迁移到最终的决策策略上。
-   **算法流程**：每个回合开始时，智能体使用 \( Q^{i,S} \) 选择动作。回合结束后，计算该回合的回报并离散化为上下文 \( c_\kappa \)。然后，采样批次数据，分别计算基于上下文的损失 \( L_C \) 和辅助学习损失 \( L_S \)，并更新所有网络参数。

### 3. 实验设计

-   **数据集/场景**：
    -   **矩阵游戏（Matrix Game）**：一个简单的双人协作博弈，用于验证对相对过度泛化的处理能力。
    -   **捕食者-猎物（Predator and Prey）**：一个部分可观测的多智能体任务（8个捕食者，8个猎物），包含合作捕获奖励和单独捕获惩罚。
    -   **星际争霸多智能体挑战赛（SMAC）**：使用了7个地图（5m_vs_6m, 10m_vs_11m, 2s3z, 3s5z, 3s_vs_4z, 3s_vs_5z, 2s_vs_1sc），这些地图涵盖了同质/异质、对称/非对称等不同挑战。
-   **基准方法 (Baselines)**：
    -   **IQL** (Independent Q-learning)：经典独立学习方法。
    -   **Hysteretic Q-learning**：使用乐观更新的独立学习方法。
    -   **I2Q**：一种通过构建理想状态转移来处理两个问题的去中心化方法。
    -   **VDN & QMIX**：中心化训练去中心化执行（CTDE）的代表性方法，用于补充对比。

### 4. 资源与算力

-   **文中说明**：论文在附录 C.5 “Computational Cost” 部分明确说明了计算资源。
-   **具体配置**：
    -   **CPU**：AMD EPYC 7542 32-Core Processor
    -   **内存**：504GB RAM
    -   **GPU**：8块 NVIDIA GeForce RTX 4090 D
-   **训练时长**：论文未明确说明每个实验的具体训练时长，但所有实验均在上述服务器上完成，总训练时间步数根据不同任务在 `50000` 到 `2050000` 之间。

### 5. 实验数量与充分性

-   **实验数量**：论文在**1个矩阵游戏、1个捕食者-猎物任务和7个SMAC地图**上进行了对比实验。此外，还进行了**多项消融实验**，包括对上下文数量 m 和辅助损失权重 β 的敏感性分析，以及验证单独使用 \( \phi^i \) 的效果（RAC_w_ \( \phi^i \)）。
-   **实验充分性**：
    -   **充分性**：实验覆盖了从简单（矩阵游戏）到高度复杂（SMAC）的不同任务，且任务类型多样（完全可观测、部分可观测、同质/异质智能体等）。对比了多种专注于去中心化学习的基线方法，实验设计比较全面。
    -   **客观性与公平性**：所有结果报告中位数和标准误差（5个随机种子），实验设置（如网络架构、超参数）在不同算法间保持一致。消融实验系统地分析了关键超参数的影响。
    -   **客观评价**：实验整体设计合理，能够有力地支撑论文提出的核心观点。但在公平性方面，需要注意RAC在劣势场景中的表现也给出了分析，例如指出在部分SMAC地图上不如I2Q或CTDE方法。

### 6. 主要结论与发现

-   RAC在大多数测试任务中**显著优于** IQL, Hysteretic Q-learning 等纯去中心化基线，证明了其同时处理非平稳性和相对过度泛化问题的有效性。
-   在复杂的SMAC任务上，RAC在`5m_vs_6m`, `10m_vs_11m`, `3s5z`, `3s_vs_4z`等地图上表现最佳，验证了其可扩展性。
-   实验证明，通过上下文建模和个体乐观边际价值的构建，RAC能够**高效地学习到最优的协作策略**。
-   消融实验表明，辅助学习过程（\( Q^{i,S} \)）在处理复杂任务时至关重要，而超参数 \( m \) 和 \( \beta \) 对性能有显著影响，需要根据任务进行调整。

### 7. 优点

-   **问题解决全面**：是首个**在完全去中心化设定下同时解决非平稳性和相对过度泛化两个核心问题**的方法。
-   **方法简洁有效**：核心思想直观（用回报代表上下文），实现简单，但在多个基准上取得了显著性能提升。
-   **隐式建模**：通过回报来间接、去中心化地建模联合策略，避免了直接对其他智能体进行显式建模的困难和通信开销。
-   **理论分析清晰**：深入分析了非平稳性和相对过度泛化问题的数学根源，并解释了RAC是如何通过上下文建模和乐观边际价值来分别解决它们的。
-   **充分的实验验证**：在多种难度的任务上进行了大量实验和消融分析，验证了方法的有效性和鲁棒性。

### 8. 不足与局限

-   **回报空间全覆盖的依赖**：基于上下文的价值函数需要在整个回报空间上进行充分覆盖才能有效学习。在复杂任务中，早期训练难以实现这一点，需要依赖辅助的 \( Q^{i,S} \) 函数，这增加了方法的复杂性。
-   **手动离散化**：目前需要手动预设回报的上下界和划分区间数量 \( m \)，这限制了方法的自适应性和泛化能力，并可能引入方差。
-   **应用场景限制**：方法基于`联合策略仅在回合间变化`的假设，对于策略在回合内频繁变化的情况（Case 1）不适用。论文将此列为未来工作。
-   **计算复杂度**：当上下文数量 \( m \) 很大时，计算个体乐观边际价值需要对所有上下文进行枚举，存在计算复杂度问题。虽然文中提出了使用CEM等近似方法，但这会引入新的复杂性。
-   **性能天花板**：在与有中心化训练优势的QMIX/VDN方法对比时，RAC在部分SMAC地图上表现仍有一定差距，说明其处理部分可观测性和全面探索的能力仍有提升空间。

（完）
