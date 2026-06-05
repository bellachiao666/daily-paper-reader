---
title: Learning and Planning Multi-Agent Tasks via an MoE-based World Model
title_zh: 基于MoE世界模型的多智能体任务学习与规划
authors: "Zijie Zhao, Zhongyue Zhao, Kaixuan Xu, Yuqian Fu, Jiajun Chai, Yuanheng Zhu, Dongbin Zhao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=fi24ry0BX5"
tags: ["query:agent-papers"]
score: 6.0
evidence: 多智能体强化学习结合混合专家世界模型处理复杂任务
tldr: 针对多任务多智能体强化学习任务泛化困难的挑战，论文提出M3W方法，将混合专家（MoE）应用于世界模型而非策略，利用任务间动力学的有界相似性。实验表明该方法能有效提升多任务泛化能力，为多智能体长期任务规划提供了新的范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 722, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1428, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1431, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1434, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1088, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 550, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1436, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1422, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1412, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1409, \"height\": 1150, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1436, \"height\": 260, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1362, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1368, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1360, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1368, \"height\": 583, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 605, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1205, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1264, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1376, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1459, \"height\": 709, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1462, \"height\": 1072, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1230, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1443, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 826, \"height\": 731, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1442, \"height\": 960, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1442, \"height\": 837, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1441, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1465, \"height\": 1013, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1311, \"height\": 131, \"label\": \"Table\"}]"
motivation: 多任务多智能体强化学习中，不同任务的最优策略差异大，单一策略模型难以泛化。
method: 提出M3W，将混合专家（MoE）引入世界模型，通过专家分工捕获任务组内相似动力学。
result: 在多种多任务场景下，M3W显著优于基线方法，证明其有效利用任务相似性。
conclusion: MoE世界模型是多智能体多任务学习的有效方向，能够提升泛化性能。
---

## Abstract
Multi-task multi-agent reinforcement learning (MT-MARL) aims to develop a single model capable of solving a diverse set of tasks. However, existing methods often fall short due to the substantial variation in optimal policies across tasks, making it challenging for a single policy model to generalize effectively. In contrast, we find that many tasks exhibit **bounded similarity** in their underlying dynamics—highly similar within certain groups (e.g., door-open/close) diverge significantly between unrelated tasks (e.g., door-open \& object-catch). To leverage this property, we reconsider the role of modularity in multi-task learning, and propose **M3W**, a novel approach that applies mixture-of-experts (MoE) to world model instead of policy, enabling both learning and planning. For learning, it uses a SoftMoE-based dynamics model alongside a SparseMoE-based predictor to facilitate knowledge reuse across similar tasks while avoiding gradient conflicts across dissimilar tasks. For planning, it evaluates and optimizes actions using the predicted rollouts from the world model, without relying directly on a explicit policy model, thereby overcoming the limitations of policy-centric methods. As the first MoE-based multi-task world model, M3W demonstrates superior performance, sample efficiency, and multi-task adaptability, as validated on Bi-DexHands with 14 tasks and MA-Mujoco with 24 tasks. The demos and anonymous code are available at \url{https://github.com/zhaozijie2022/m3w-marl}.

---

## 论文详细总结（自动生成）

## 论文总结：基于MoE世界模型的多智能体任务学习与规划（M3W）

### 一、论文的核心问题与整体含义（研究动机和背景）

多任务多智能体强化学习（MT-MARL）的目标是训练单一模型以解决多种不同任务。现有方法主要采用**策略中心**的范式，通过模块化设计（如子任务重组、技能发现、网络分解）来复用相似任务知识并避免冲突。然而，作者发现不同任务的最优策略分布差异巨大，而**任务动力学**却存在**有界相似性（bounded similarity）**：即同一组内（如开门/关门）动力学高度相似，不同组间（如开门与抓取）则差异显著。基于此，作者提出应将**模块化（MoE）应用于世界模型而非策略**，以更好地利用动力学相似性、避免负迁移，并通过基于模型的规划来克服策略中心方法泛化不足的局限。

### 二、论文提出的方法论：核心思想、关键技术细节

**核心思想**：构建一个基于混合专家（Mixture-of-Experts, MoE）的多智能体世界模型，通过专家分工实现任务动力学和奖励的有界相似性利用；在此基础上执行模型预测路径积分（MPPI）规划，不依赖显式策略模型。

**关键技术细节**：
- **整体框架**（M3W）：
  - **编码器**：将观测映射到潜在空间，使用任务嵌入（task embedding）作为条件。
  - **动力学模型（SoftMoE）**：将多智能体观测-动作对视为序列，通过软路由将每个智能体token分配到N个MLP专家，输出后再聚合回各智能体预测的下一潜在状态。实现知识库动态调用：相似任务激活相近专家，不同任务隔离梯度。
  - **奖励预测器（SparseMoE）**：使用稀疏路由选择Top-K个自注意力专家，聚合后输出统一标量奖励。含负载均衡损失。
  - **Actor-Critic模块**：Actor仅用于生成候选动作给规划器，Critic用于评估远期回报。
- **规划器**：基于MPPI，迭代采样动作序列→世界模型滚动预测→使用式(7)评估（短期累积奖励+终端Q值）→选择精英轨迹→更新动作分布。不依赖于显式策略，从而避免策略中心方法的冲突。
- **训练目标**：自我监督式损失，包括动态损失、奖励损失、Q损失；Actor通过HASAC算法优化，目标为最大化熵与Q值。

**公式和算法流程**（文字说明）：
- 世界模型定义：编码器、动力学、预测器、Critic、Actor均以任务嵌入为条件。
- 损失函数（式2）：多步滚动损失，含潜在状态预测、奖励预测、Q值预测的软交叉熵。
- 规划价值函数（式7）：V = 折扣终端Q值 + 折扣预测奖励之和。

### 三、实验设计

**数据集/场景**：
- **Bi-DexHands**（14个任务）：双臂灵巧手协作任务，包括开门、关门、抓取、倒水等，观测维度高达229，动作维度26。
- **MA-Mujoco**（24个任务）：多智能体MuJoCo，涵盖猎豹、人形、Walker2D、Swimmer、Hopper、Reacher等多个套件，每套件含多个子任务。

**对比基线**：
- 模型基线：MACD（基于Transformer的世界模型）
- 多任务基线：HMASD（层次化技能发现）
- 通用MARL基线：MAT、MAPPO、HATRPO
- 强基线：每个任务独立训练的MAPPO（Single-MAPPO）

**实验充分性**：
- 在38个任务（14+24）上进行了比较，M3W在27个任务上达到最优（71%）。
- 进行了消融实验：世界模型预测精度对比（Transformer、Switch-Transformer、MLP）；规划器贡献（给MACD加规划器）；Actor先验消融；奖励尺度鲁棒性；推理时延分析；早停规划器；智能体数量扩展性。
- 可视化分析：专家注意力分布（显示专家专业化）、路由输出余弦相似性（显示有界相似性利用）、t-SNE潜在轨迹（任务聚类）。

**统计显著性**：报告了95%置信区间和误差边界，并提供了p值和优势概率（PoS）分析。

### 四、资源与算力

论文正文未明确说明GPU型号、数量及总训练时长。仅在附录E.6中提及在单张RTX A6000 GPU上测试了推理时间（25.8ms/步）。但未提供完整训练算力需求。可以指出：**文中未明确报告训练算力**。

### 五、实验数量与充分性

- **实验数量**：覆盖38个任务，加上多组消融（预测精度、规划贡献、Actor先验、奖励尺度、早停、扩展性），总计不少于10组实验。
- **充分性**：实验设计较全面，涵盖了多任务性能、样本效率、世界模型精度、规划效果、可解释性、鲁棒性、扩展性。对比基线涵盖主流方法，统计分析方法合理（PoS、p值）。但未在离散动作空间验证（作者自认局限）。

### 六、论文的主要结论与发现

1. **M3W在多数任务上超越所有基线**，平均性能显著提升（Bi-DexHands: 84.1 vs 72.0；MA-Mujoco: 40.2 vs 33.1）。
2. MoE世界模型**有效利用有界相似性**：相似任务共享专家，不同任务隔离冲突，提升样本效率和泛化。
3. 基于规划的范式**避免了策略中心方法的局限性**，在奖励尺度不均等场景下仍保持学习塑性。
4. 可视化揭示了**专家专业化**和**任务聚类**现象，验证了模型的可解释性。

### 七、优点

1. **创新性**：首次将MoE应用于多智能体世界模型，而非策略网络；提出有界相似性概念，为模块化设计提供新思路。
2. **方法设计合理**：软路由适合多智能体序列预测，稀疏路由适合奖励预测，负载均衡损失保障专家平衡。
3. **实验全面且严谨**：多场景、多基线、多消融、统计检验、可视化分析，证据链完整。
4. **性能优势明显**：在连续控制任务上显著优于现有方法，且样本效率高。
5. **可解释性好**：通过路由权重和专家注意力分析，揭示了模型内部机理。

### 八、不足与局限

1. **仅限连续动作空间**：MPPI规划器无法处理离散动作，限制了在StarCraft等经典MARL基准上的应用。作者已提出未来可结合MCTS或CEM扩展。
2. **未报告完整训练算力**：读者难以评估计算成本。虽然推理时延满足实时性，但训练开销未知。
3. **未测试部分可观测极端情况**：虽然论文考虑了部分可观测性（通过通信假设），但在严格受限通信场景下未做压力测试。
4. **专家数量等超参数未深入分析**：如专家数N、稀疏度K对性能的影响仅通过消融中的模型大小对比间接展示，但未系统调参。
5. **环境局限性**：只验证了连续控制任务（Bi-DexHands, MA-Mujoco），在多智能体经典离散任务（如SMAC、MPE）上未见实验，可能影响泛化结论。

（完）
