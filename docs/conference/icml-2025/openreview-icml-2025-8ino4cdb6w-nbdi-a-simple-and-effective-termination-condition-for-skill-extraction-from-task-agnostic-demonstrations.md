---
title: "NBDI: A Simple and Effective Termination Condition for Skill Extraction from Task-Agnostic Demonstrations"
title_zh: NBDI：一种简单有效的基于新奇度的技能提取终止条件
authors: "Myunsoo Kim, Hayeong Lee, Seong-Woong Shim, JunHo Seo, Byung-Jun Lee"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=8ino4CdB6w"
tags: ["query:agent-papers"]
score: 5.0
evidence: 长时任务技能学习
tldr: 当前技能学习中使用固定长度技能容易错过关键决策点，限制了探索和策略学习。本文提出基于新奇度的决策点识别方法NBDI，利用智能体经验数据学习终止条件，自适应地识别决策点。在复杂长时任务上，NBDI优于先前方法，提升了技能学习的效率和泛化能力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-8ino4cdb6w/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1594, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8ino4cdb6w/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1723, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8ino4cdb6w/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 858, \"height\": 264, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8ino4cdb6w/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1744, \"height\": 772, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8ino4cdb6w/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1756, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8ino4cdb6w/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1565, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8ino4cdb6w/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 865, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8ino4cdb6w/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 670, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8ino4cdb6w/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1782, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8ino4cdb6w/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 373, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8ino4cdb6w/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1783, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8ino4cdb6w/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1488, \"height\": 1026, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8ino4cdb6w/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1647, \"height\": 885, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8ino4cdb6w/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1701, \"height\": 1912, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8ino4cdb6w/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1770, \"height\": 1014, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8ino4cdb6w/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 878, \"height\": 645, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8ino4cdb6w/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1573, \"height\": 2098, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-8ino4cdb6w/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 722, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8ino4cdb6w/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 857, \"height\": 143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8ino4cdb6w/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1014, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8ino4cdb6w/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1401, \"height\": 916, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8ino4cdb6w/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1763, \"height\": 598, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8ino4cdb6w/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1212, \"height\": 1069, \"label\": \"Table\"}]"
motivation: 固定长度技能会跳过有价值的决策点，限制探索和策略学习。
method: 利用智能体经验数据，通过新奇度模块学习终止条件以识别决策点。
result: 在复杂长时任务上NBDI优于先前方法。
conclusion: 自适应终止条件能有效提升技能学习性能。
---

## Abstract
Intelligent agents are able to make decisions based on different levels of granularity and duration. Recent advances in skill learning enabled the agent to solve complex, long-horizon tasks by effectively guiding the agent in choosing appropriate skills. However, the practice of using fixed-length skills can easily result in skipping valuable decision points, which ultimately limits the potential for further exploration and faster policy learning.
In this work, we propose to learn a simple and effective termination condition that identifies decision points through a state-action novelty module that leverages agent experience data.
Our approach, Novelty-based Decision Point Identification (NBDI), outperforms previous baselines in complex, long-horizon tasks, and remains effective even in the presence of significant variations in the environment configurations of downstream tasks, highlighting the importance of decision point identification in skill learning.

---

## 论文详细总结（自动生成）

# NBDI：一种简单有效的基于新奇度的技能提取终止条件——论文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：在强化学习的技能学习中，现有方法多采用**固定长度技能**，这会导致智能体容易跳过重要的**决策点**（如迷宫岔路口、子任务完成后的状态），从而限制探索效率和政策学习速度。
- **背景**：层级强化学习（如Option框架）通过终止条件实现时间抽象，但传统Option学习计算复杂；技能发现框架（如SPiRL）使用固定长度技能，虽简化了训练，但丢失了关键决策时机。
- **核心目标**：提出一种简单有效的**终止条件学习机制**，利用任务无关的演示数据自动识别决策点，使技能在关键时刻终止，从而提升下游复杂长时任务的求解性能。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：使用**状态-动作新奇度（state-action novelty）** 作为终止条件的依据。新奇度高的状态-动作对往往出现在关键决策点（如多路径选择、罕见状态）。将新奇度分解为**状态新奇度**（探索新区域）和**条件动作新奇度**（状态中动作多样性高），两者乘积即为状态-动作新奇度。
- **关键技术细节**：
  - **新奇度估计模块**：采用**内在好奇心模块（ICM）** 预训练在任务无关的离线演示数据上。ICM的预测误差作为新奇度度量，误差大表示该(s,a)对在数据中稀疏。
  - **终止条件学习**：将新奇度高于预设阈值的(s,a)标记为终止点（β=1），训练一个**终止条件分布 p(β|s,a)**。同时，采用**变分自编码器（VAE）** 架构联合学习技能嵌入空间、低层策略和终止分布，最大化ELBO（包括重构损失和KL正则项）。
  - **下游强化学习**：使用**SAC**算法学习高层策略 π(z|s)，执行时低层策略解码动作并持续运行，直到终止条件 β=1 被采样或达到最大长度 H=30。奖励为累积折扣奖励，Q学习适配变长技能（SMDP框架）。
- **理论支撑**：引用**终止改进定理**（Sutton, 1998）：当当前技能值函数小于状态值函数时应终止。新奇度高的状态往往对应多可选动作，满足终止条件。

## 3. 实验设计

- **环境与数据集**：
  - **导航任务**：30x30和40x40迷宫（连续状态、动作），离线数据为随机迷宫布局下的目标到达轨迹（85,000条）。
  - **机器人操作**：Kitchen环境（D4RL，7个可操作物体，400条轨迹）和**稀疏方块堆叠**（MuJoCo，5块→11块，37,000条轨迹）。下游任务环境配置与训练数据明显不同（迷宫布局全新、方块数量增多且位置随机）。
- **对比方法**：
  - **Flat RL**：SAC、SAC+Novelty（新奇度作为内在奖励）
  - **离线预训练+微调**：BC+SAC、IQL+SAC
  - **固定长度技能**：SPiRL
  - **其他变长方法**：Relative Novelty（基于相对新奇度）、LOVE（基于最小描述长度）
  - **消融变体**：NBDI-χ(s)（仅状态新奇度）、NBDI-χ(a|s)（仅条件动作新奇度）、NBDI-NoTermDistr（不预训练终止分布）、NBDI-CumulativeSum（累积新奇度终止）
- **评价指标**：迷宫任务的成功率；Kitchen的完成子任务数；方块堆叠的堆叠高度（稀疏奖励下为堆叠块数）。

## 4. 资源与算力

- 论文在Appendix I.5明确说明：
  - 每个实验使用**单个CPU（Intel Xeon Gold 6330）** 和**单个GPU（NVIDIA RTX 3090）**。
  - 训练总时长约**36小时**（12小时先验学习+24小时下游学习），占用约30% RAM和25% GPU内存。
  - 所有RL算法基于**PyTorch v1.3**，操作系统Ubuntu 22.04.04 LTS。
- 未提及多GPU并行或多机训练，算力开销合理。

## 5. 实验数量与充分性

- **主实验**：在4个环境（2个迷宫、Kitchen、稀疏方块堆叠）上，与至少5种基线方法对比，每个实验**5个不同随机种子**，绘制学习曲线和95%置信区间。
- **消融实验**：
  - 不同新奇度类型（状态新奇度 vs 条件动作新奇度）
  - 无终止分布与有终止分布
  - 不同阈值（th0.1, th0.3, th0.5）
  - 累积新奇度 vs 单步新奇度
  - 模型容量（不同网络宽度/深度）和数据集使用比例的影响
  - 次优数据质量（带噪声BC策略生成的数据）效果
- **扩展实验**：将NBDI集成到技能元学习方法SiMPL中，验证在元学习场景下的有效性。
- **充分性评价**：实验设计全面，覆盖多种任务、多种基线、多种消融，结果统计可靠（95%置信区间），对比公平（控制变量）。结论具有泛化说服力。

## 6. 主要结论与发现

- NBDI在所有测试任务上**显著优于固定长度技能SPiRL**及其他基线方法（最大提升177.78%）。
- NBDI在**环境配置显著变化**的下游任务中仍保持有效，说明其决策点识别能力具有可迁移性。
- **条件动作新奇度**是识别决策点的关键因素，**状态新奇度**有助于探索，二者结合效果最佳。
- 终止条件分布需与技能嵌入空间**联合优化**（单独使用新奇度模块直接终止性能下降）。
- 模型对**数据集质量**敏感：专家级或弱随机数据有效，完全随机数据无法提取有意义决策点。
- NBDI可成功集成到其他技能学习框架（如SiMPL），提升样本效率和收敛速度。

## 7. 优点

- **方法简单有效**：仅需预训练一个ICM和VAE，无需任务标签或奖励信号，利用任务无关数据即可学习终止条件。
- **理论动机清晰**：基于终止改进定理，从状态新奇度和条件动作新奇度两个角度解释决策点识别原理。
- **强泛化性能**：在环境布局、尺寸、物体数量显著改变的复杂下游任务上依然领先。
- **丰富的消融与分析**：系统验证了各组件贡献，提供模型容量、数据量、阈值等参数的鲁棒性分析。
- **兼容性好**：可与现有技能学习方法（如SPiRL、SiMPL）无缝衔接，无需改变高层RL算法。
- **实验充分、结果可信**：多环境、多种子、多基线、多消融，统计严谨。

## 8. 不足与局限

- **对演示数据质量敏感**：当离线数据来自次优策略或高度随机策略时，ICM预测误差尺度下降，决策点识别能力减弱（Table 1及Appendix C显示完全随机数据无效）。
- **阈值需手动调整**：不同环境需设定不同新奇度阈值（虽然可参考97%分位，但仍需实验调参）。
- **未在真实机器人上验证**：所有实验均为模拟环境（MuJoCo），实际物理世界中的噪声和动态可能带来挑战。
- **新奇度模块依赖离线预训练**：若下游环境与预训练数据差异极大（如完全不同的传感器模态），可能需要重新训练。
- **未与更多最新变长技能方法比较**：仅对比了Relative Novelty和LOVE，缺乏与近期其他Option学习方法（如DIGIT、skill-based meta-learning中的其他变长方案）的比较。

（完）
