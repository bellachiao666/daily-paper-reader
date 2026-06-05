---
title: "DISCOVER: Automated Curricula for Sparse-Reward Reinforcement Learning"
title_zh: DISCOVER：面向稀疏奖励强化学习的自动课程
authors: "Leander Diaz-Bone, Marco Bagatella, Jonas Hübotter, Andreas Krause"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=guZBnsKPsw"
tags: ["query:agent-papers"]
score: 7.0
evidence: 自动课程用于通过强化学习构建自改进智能体
tldr: 稀疏奖励环境中构建自改进智能体需要有效探索。DISCOVER从现有强化学习检查点中提取方向信号，自动生成与目标任务相关的课程，引导智能体由简到难学习。在复杂高维任务中，该方法显著提升了样本效率和最终性能，为自我改进智能体提供了可行路径。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-guzbnskpsw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1306, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-guzbnskpsw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-guzbnskpsw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1455, \"height\": 884, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-guzbnskpsw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1429, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-guzbnskpsw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 600, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-guzbnskpsw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 602, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-guzbnskpsw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 664, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-guzbnskpsw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1259, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-guzbnskpsw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 673, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-guzbnskpsw/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1460, \"height\": 996, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-guzbnskpsw/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1451, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-guzbnskpsw/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1462, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-guzbnskpsw/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 568, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-guzbnskpsw/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1433, \"height\": 1196, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-guzbnskpsw/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1432, \"height\": 690, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-guzbnskpsw/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1466, \"height\": 516, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-guzbnskpsw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-guzbnskpsw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 597, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-guzbnskpsw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1192, \"height\": 619, \"label\": \"Table\"}]"
motivation: 构建自改进智能体需要高效探索，但稀疏奖励任务中随机探索不可行。
method: 从现有RL检查点中提取方向信号，自动生成与目标任务相关的课程序列，引导智能体逐步学习。
result: 在复杂高维稀疏奖励任务中，自动课程显著提升了样本效率和成功率。
conclusion: 定向课程学习是实现自改进智能体的关键方法。
---

## Abstract
Sparse-reward reinforcement learning (RL) can model a wide range of highly complex tasks.
Solving sparse-reward tasks is RL's core premise — requiring efficient exploration coupled with long-horizon credit assignment — and overcoming these challenges is key for building self-improving agents with superhuman ability.
We argue that solving complex and high-dimensional tasks requires solving simpler tasks that are *relevant* to the target task.
In contrast, most prior work designs strategies for selecting exploratory tasks with the objective of solving *any* task, making exploration of challenging high-dimensional, long-horizon tasks intractable.
We find that the sense of direction, necessary for effective exploration, can be extracted from existing reinforcement learning algorithms, without needing any prior information.
Based on this finding, we propose a method for _**di**rected **s**parse-reward goal-**co**nditioned **ve**ry long-horizon **R**L_ (DISCOVER), which selects exploratory goals in the direction of the target task.
We connect DISCOVER to principled exploration in bandits, formally bounding the time until the target task becomes achievable in terms of the agent's initial distance to the target, but independent of the volume of the space of all tasks.
Empirically, we perform a thorough evaluation in high-dimensional simulated environments. We find that the directed goal selection of DISCOVER solves exploration problems that are beyond the reach of prior state-of-the-art exploration methods in RL.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：稀疏奖励的强化学习（RL）中，长时域、高维的任务（如机器人导航、操作）需要有效的探索策略。传统方法（如好奇心驱动、随机探索）在高维目标空间中难以找到稀疏的最终奖励，而现有自动课程方法（如 MEGA）虽然考虑了可达性和新颖性，但缺乏对**目标任务的方向引导**，导致探索范围爆炸。
- **整体含义**：本文认为，解决复杂稀疏奖励任务的关键在于**自动生成与目标任务相关的课程**——即从简单到困难的子任务序列，且子任务必须同时满足**可达性**、**新颖性**和**相关性**。作者从现有 RL 批评网络（critic）中提取方向信号（无需先验知识），提出 DISCOVER 方法，实现了高效的定向探索，为解决自我改进智能体（self-improving agents）提供了可行路径。

### 2. 论文提出的方法论

- **核心思想**：在每一轮探索中，从“已实现目标集”（achieved goals）中选择一个中间目标，使得该目标：
  - **可达性**（Achievability）：从当前状态容易达到；
  - **新颖性**（Novelty）：对代理是不确定的（高方差）；
  - **相关性**（Relevance）：接近最终目标（从该目标到最终目标的价值高）。
- **关键技术细节**：
  - 使用**集成批评网络**（ensemble of critics）估计价值函数均值 \(V(s,g)\) 和方差 \(\sigma^2(s,g)\)。
  - DISCOVER 目标函数：
    \[
    g_t = \arg\max_{g \in \mathcal{G}_{\text{ach}}} \alpha_t \left[ V(s_0, g) + \beta_t \sigma(s_0, g) \right] + (1-\alpha_t)\left[ V(g, g^*) + \beta_t \sigma(g, g^*) \right]
    \]
    其中 \(s_0\) 为初始状态，\(g^*\) 为最终目标。
  - **在线参数自适应**：根据近期目标达成率动态调整 \(\alpha_t\)（初始为 0），维持约 50% 的达成率；\(\beta_t\) 固定为 1。
  - **理论联系 UCB**：将 DISCOVER 视为线性 bandit 中的 UCB 采样，并证明在简化假设下，达到最终目标所需的 episode 数上界仅依赖于初始距离 \(D\) 和特征维度 \(d\)，而与目标空间体积无关（避免了维度灾难）。
- **训练流程**：每个 episode 先用 DISCOVER 选择目标 \(g_t\)，智能体执行策略直到达到 \(g_t\)，然后进行随机探索；轨迹存入经验回放池；使用 off-policy RL（TD3）和 hindsight goal relabeling 更新参数。

### 3. 实验设计

- **环境与场景**：使用 JaxGCRL 库中的三个复杂连续控制任务：
  - **Point Maze**：点状智能体在迷宫中导航，可自定义维度（2D–6D）。
  - **Ant Maze**：四足机器人（27D 状态，8D 动作）在迷宫中导航。
  - **Arm**：机械臂（23D 状态，5D 动作）移动积木至目标位置（可能有障碍物）。
  每个环境有**简单**和**困难**两种配置（迷宫更大、障碍更多、维度更高）。
- **对比方法（Baselines）**：
  - **HER**：始终选择最终目标。
  - **DISCERN (uniform)**：从已实现目标均匀采样。
  - **MEGA**：基于最大熵增益选择可达且低似然的目标。
  - **Achievability + Novelty**：去掉 DISCOVER 中的相关性项。
  - 标准 RL 方法（无目标条件）：TD3、SAC、RND、SAC + MaxInfoRL。
- **评估指标**：目标任务的成功率随环境步数变化（10 个随机种子，报告均值和标准误）。

### 4. 资源与算力

- **硬件**：单块 NVIDIA GeForce RTX 2080 Ti GPU（每项实验），内存 ≤ 16 GB。
- **训练时长**：最长实验约 50 小时，所有实验总计约 **800 个独立运行**，累计约 **8000 计算小时**（在内部集群完成）。
- **未明确说明**：超参数搜索细节未提及（但主要超参数见附录表 2）。

### 5. 实验数量与充分性

- **实验数量**：共包含三大环境 × 两个难度 × 10 种子 = 至少 60 组主要实验。此外还有：
  - 高维点迷宫维度消融（2D–6D，五种方法）。
  - 消融实验：α 自适应策略、集成大小（2/4/6/8）、σ(g,g*) 系数、方向噪声鲁棒性、手写/预训练先验、各分量贡献可视化等。
- **充分性与公平性**：
  - 覆盖了从简单到困难、低维到高维的多种场景，对比基线包括有/无方向、有/无课程、普通 RL 等，对比全面。
  - 所有方法基于同一代码库（JaxGCRL），共享相同环境和训练流程，种子一致，公平性较好。
  - 消融实验细致，验证了各个组件（方向、不确定性、自适应参数）的必要性。
  - 但未在离散控制或语言/数学等领域测试，实验范围集中于连续控制。

### 6. 论文的主要结论与发现

1. **DISCOVER 显著优于所有基线**：在复杂控制任务（尤其是困难配置）中，成功率提升幅度大，学习速度更快。
2. **方向性探索至关重要**：缺乏相关性项的“Achievability+Novelty”在高维（>3D）点迷宫中完全失败，而 DISCOVER 能在 6D 中成功（表 1）。
3. **标准 RL 方法无法解决**：TD3、SAC、RND、MaxInfoRL 在简单难度的 Ant/Point/ Arm 上成功率始终为 0，说明无目标条件的探索不足以处理长时域稀疏奖励。
4. **先验知识可加速**：DISCOVER 可整合手工先验（如 L2 距离）或预训练 critic 作为方向信号，进一步提升探索效率（图 5）。
5. **理论保证**：在简化线性 bandit 假设下，到达目标所需 episode 数上界与初始距离 D 线性相关，与目标空间体积无关（避开了维度灾难）。

### 7. 优点

- **新颖性**：首次将“方向性（relevance）”显式纳入自监督课程学习，并理论联系 UCB，既有理论基础又有实证优势。
- **高效性**：无需任何先验知识，完全从批评网络 bootstrap 方向信号；在线自适应参数免去手工调参。
- **可扩展性**：理论边界不依赖于目标空间体积，在高维场景中可扩展；实验验证了最高 6D 的点迷宫（其他方法在 3D 已失败）。
- **实验全面且透明**：提供了详细消融、可视化、鲁棒性测试，开源代码，利于复现。
- **实际意义**：为自我改进智能体（self-improving agents）提供了可行的端到端探索课程方法。

### 8. 不足与局限

- **理论假设较强**：假设价值函数在特征空间线性、反馈噪声 sub-Gaussian、目标空间满足测地凸性等，在实际神经网络值函数训练中未必成立（存在 bootstrap 偏差和非平稳性）。
- **计算开销**：使用集成批评（ensemble of critics）进行不确定性估计，默认 6 个 critic，增加了训练时间（约 26% overhead），对于大模型（如语言模型）可能不可接受。
- **仅评估连续控制**：未在离散动作（Atari）、语言推理、数学证明等场景测试，通用性有待验证。
- **目标空间假设**：方法要求目标状态必须被智能体在历史中“实现过”才能被选为子目标（只能 select，不能 generate），限制了对全新区域的探索能力。
- **实验配置固定**：虽然包含难易变化，但未系统测试超大规模（如 10D+）环境；每个任务仅一个固定目标，未考虑多目标分布。

（完）
