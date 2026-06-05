---
title: "R3DM: Enabling Role Discovery and Diversity Through Dynamics Models in Multi-agent Reinforcement Learning"
title_zh: R3DM：通过动力学模型实现多智能体强化学习中的角色发现与多样性
authors: "Harsh Goel, Mohammad Omama, Behdad Chalaki, Vaishnav Tadiparthi, Ehsan Moradi Pari, Sandeep P. Chinchali"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=VSIjdKPGp8"
tags: ["query:agent-papers"]
score: 6.0
evidence: 多智能体角色发现方法，提升复杂任务协作
tldr: 该论文针对多智能体强化学习中角色发现不足的问题，提出R3DM框架，通过动力学模型捕捉角色对智能体未来行为的影响，从而引导角色有效塑造协作行为。实验表明该方法在复杂协作任务中显著提升性能，为多智能体系统在交通控制、自动驾驶等领域的应用提供了新途径。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vsijdkpgp8/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vsijdkpgp8/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 854, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vsijdkpgp8/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1780, \"height\": 660, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vsijdkpgp8/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1660, \"height\": 1411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vsijdkpgp8/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1688, \"height\": 386, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vsijdkpgp8/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1115, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vsijdkpgp8/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1781, \"height\": 750, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vsijdkpgp8/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 929, \"height\": 638, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vsijdkpgp8/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1867, \"height\": 662, \"label\": \"Table\"}]"
motivation: 现有角色学习方法仅基于过去经验，忽略了角色对未来行为的影响。
method: 利用动力学模型学习角色表示，并通过角色影响未来轨迹来实现协调。
result: 在多个MARL基准任务上优于现有角色发现方法。
conclusion: R3DM通过动力学模型增强了角色发现的表达能力和协调效果。
---

## Abstract
Multi-agent reinforcement learning (MARL) has achieved significant progress in large-scale traffic control, autonomous vehicles, and robotics. Drawing inspiration from biological systems where roles naturally emerge to enable coordination, role-based MARL methods have been proposed to enhance cooperation learning for complex tasks. However, existing methods exclusively derive roles from an agent's past experience during training, neglecting their influence on its future trajectories. This paper introduces a key insight: an agent’s role should shape its future behavior to enable effective coordination. Hence, we propose Role Discovery and Diversity through Dynamics Models (R3DM), a novel role-based MARL framework that learns emergent roles by maximizing the mutual information between agents' roles, observed trajectories, and expected future behaviors. R3DM optimizes the proposed objective through contrastive learning on past trajectories to first derive intermediate roles that shape intrinsic rewards to promote diversity in future behaviors across different roles through a learned dynamics model. Benchmarking on SMAC and SMACv2 environments demonstrates that R3DM outperforms state-of-the-art MARL approaches, improving multi-agent coordination to increase win rates by up to 20%. The code is available at https://github.com/UTAustin-SwarmLab/R3DM.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：多智能体强化学习（MARL）在交通控制、自动驾驶、机器人等复杂协作任务中取得了显著进展。基于角色的MARL方法受生物系统中自然浮现的协作角色启发，旨在通过学习不同角色的行为来增强协同能力。然而，现有方法（如ACORM、RODE、ROMA等）仅从智能体的**过去经验**（观察-动作历史）中提取角色，忽略了角色对智能体**未来行为**的影响。这导致角色只反映已发生的行为，而非引导未来协作，容易造成行为冗余（如两个无人机同时扑向同一火灾点）。
- **核心问题**：如何使角色不仅编码过去，还能塑造未来，从而驱动智能体产生互补、多样化的行为以实现有效协调。
- **整体含义**：R3DM（Role Discovery and Diversity through Dynamics Models）通过引入动力学模型，将角色的影响延伸到未来轨迹，在共享参数训练框架下促进智能体分工和探索，显著提升了MARL在复杂场景下的协作性能。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 提出信息论目标：最大化智能体的角色 \( m_i^t \)、已观测轨迹 \( \tau_i^{t+k} \) 与未来预期行为之间的互信息 \( I(\tau_i^{t+k}; m_i^t) \)。
- 通过定理4.1将互信息分解为两项：
  1. 从观察-动作历史中学习中间角色嵌入 \( z_i^t \)（通过对比学习）；
  2. 最大化角色嵌入与未来轨迹的互信息 \( I(\tau_i^{t+1:t+k}; z_i^t) \)，通过内在奖励实现。

### 关键技术细节
- **角色表示学习**：采用ACORM的对比学习框架，将智能体历史嵌入 \( e_i^t \) 聚类为 \( |M| \) 个角色，使用动量对比（MoCo）和双线性相似度函数优化角色嵌入。
- **内在奖励设计**：
  - **策略内在奖励**：通过角色条件化策略与平均策略之间的KL散度，鼓励不同角色采取不同行动。
  - **动力学内在奖励**：利用DreamerV3风格的循环状态空间模型（RSSM），分别训练角色条件化动力学模型和角色无关动力学模型，计算未来观察的对数似然差，激励角色引导可区分的未来轨迹。
- **最终学习目标**：结合任务奖励 \( r_t \) 和内在奖励 \( r_t^{\text{int}} \)（加权系数α），使用QMIX风格的值函数分解训练。

## 3. 实验设计

- **数据集/场景**：
  - **SMAC**（StarCraft Multi-Agent Challenge）：6个硬和超硬地图（5m vs 6m, MMM2, 3s5z vs 3s6z, 27m vs 30m, 6h vs 8z, Corridor）。
  - **SMACv2**：引入初始条件随机性，包括3个5v5场景（protoss, terran, zerg）和3个10v11不对称场景。
- **基准方法**：与QMIX、ACORM、CIA、GoMARL、CDS、EMC比对，涵盖角色学习、分组、多样性探索等类别。
- **评估指标**：测试胜率（Test Win Rate）和测试累计奖励。

## 4. 资源与算力

- 文中未明确说明使用的GPU型号、数量及训练总时长。仅提及使用SMAC版本SC 2.4.10，以及超参数（如批大小、优化器等）。未提供算力统计细节。

## 5. 实验数量与充分性

- **实验数量**：
  - SMAC上6个地图，SMACv2上6个场景，共12个基准场景。
  - 每个实验使用5个随机种子取均值和标准差。
  - 额外进行3组消融实验：想象步长（1,2,5,10）、角色数量（2,3,5,8）、对比学习有无。
  - 定性分析：可视化策略和TSNE角色嵌入（图4）。
- **充分性**：实验覆盖多种难度和随机性场景，对比方法全面（6个基线），消融设计合理。但未在更多真实世界或连续控制任务上验证，且仅使用StarCraft环境，泛化性需进一步检验。公平性方面，使用相同网络和超参数设置，但内在奖励超参数（α,β1,β2,β3）在不同地图上需手动调整，可能引入一定偏差。

## 6. 主要结论与发现

- R3DM在SMAC和SMACv2的多个复杂场景中优于所有基线，胜率提升最高达20%。
- 在严重不对称场景（如3s5z vs 3s6z, Corridor）和随机性强的SMACv2中，R3DM展现出更快的收敛速度和更高的最终胜率。
- 定性分析表明，R3DM学会让单个智能体承担诱敌等差异化角色，实现战略分工，而ACORM则倾向于集中攻击。
- 消融实验表明：短想象步长（k=1或2）效果最佳；中等角色数量（3个）平衡效率与性能；对比学习与内在奖励互补，缺一不可。

## 7. 优点

- **方法创新**：首次将角色与未来行为通过动力学模型直接关联，弥补了现有“过去导向”角色学习的不足。
- **技术完整**：互信息分解、对比学习、内在奖励（策略+动力学）三者紧密结合，理论推导清晰。
- **实验结果**：在多个标准基准上取得显著优势，且通过消融和可视化验证了设计合理性。
- **可复现**：开源代码，超参数和网络结构详细列出。

## 8. 不足与局限

- **先验角色数量**：需要手动设定角色数量 \( |M| \)，缺乏动态调整机制。
- **动力学模型局限**：仅使用局部观察建模，未考虑其他智能体动作或角色对自身观察的影响，可能导致预测误差累积（尤其在长想象步长时性能下降）。
- **实验环境单一**：仅在StarCraft微操场景验证，未在连续动作空间或机器人真实任务中测试，泛化能力存疑。
- **超参数敏感性**：内在奖励权重α、β1、β2、β3需针对不同地图手工调节，可能限制易用性。
- **计算开销**：额外训练两个RSSM模型和对比学习模块，相比QMIX增加训练时间（但文中未量化）。

（完）
