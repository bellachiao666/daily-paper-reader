---
title: Hierarchical Equivariant Policy via Frame Transfer
title_zh: 通过帧传递的层次等变策略
authors: "Haibo Zhao, Dian Wang, Yizhe Zhu, Xupeng Zhu, Owen Lewis Howell, Linfeng Zhao, Yaoyao Qian, Robin Walters, Robert Platt"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=nAv5ketrHq"
tags: ["query:agent-papers"]
score: 4.0
evidence: 层次策略通过帧传递支持长程推理
tldr: 该论文提出层次等变策略HEP，通过帧传递接口连接高层和低层策略。高层输出作为低层坐标帧，提供强归纳偏置。在需要长程推理的任务中，HEP减少了演示需求，提升了性能。虽非多智能体，但其层次结构支持复杂任务分解和长程规划。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1781, \"height\": 1061, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 862, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 849, \"height\": 347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1768, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 888, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 857, \"height\": 183, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1781, \"height\": 2052, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1775, \"height\": 1040, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1686, \"height\": 702, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 277, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 859, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 369, \"height\": 148, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 649, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1238, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 867, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 550, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 691, \"height\": 170, \"label\": \"Table\"}]"
motivation: 层次策略的层间接口未充分利用，且忽略对称性导致大量演示需求。
method: 提出帧传递接口，高层策略输出坐标帧，低层策略在该帧中动作，保持等变性。
result: 在多个长程推理基准上，HEP以更少的演示达到或超越现有方法。
conclusion: 展示了利用对称性和层次结构提升长程推理效率的潜力。
---

## Abstract
Recent advances in hierarchical policy learning highlight the advantages of decomposing systems into high-level and low-level agents, enabling efficient long-horizon reasoning and precise fine-grained control. However, the interface between these hierarchy levels remains underexplored, and existing hierarchical methods often ignore domain symmetry, resulting in the need for extensive demonstrations to achieve robust performance. To address these issues, we propose Hierarchical Equivariant Policy (HEP), a novel hierarchical policy framework. We propose a frame transfer interface for hierarchical policy learning, which uses the high-level agent's output as a coordinate frame for the low-level agent, providing a strong inductive bias while retaining flexibility. Additionally, we integrate domain symmetries into both levels and theoretically demonstrate the system's overall equivariance. HEP achieves state-of-the-art performance in complex robotic manipulation tasks, demonstrating significant improvements in both simulation and real-world settings.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：层次化策略学习中，高层与低层代理之间的接口设计尚未被充分探索；现有层次化方法往往忽略任务中的域对称性（如平移和旋转等变性），导致需要大量演示数据才能达到鲁棒性能。
- **整体含义**：提出一种新的层次等变策略框架（HEP），通过引入“帧传递”接口，让高层输出作为低层坐标帧，既提供强归纳偏置又保持灵活性，同时将对称性融入两个层级，从而显著提升样本效率和泛化能力，适用于复杂机器人操作任务。

## 2. 论文提出的方法论
- **核心思想**：将策略分解为两个层级：
  - **高层代理**预测一个粗粒度的3D平移（关键帧位置），表示为体素概率热图。
  - **低层代理**在该关键帧坐标系内预测精细的轨迹（SE(3)姿态序列）。
  - **帧传递接口**：通过平移操作将观测和动作映射到高层输出的坐标帧，实现层间通信。
- **关键技术细节**：
  - **高层代理**：使用等变3D U-Net处理堆叠体素编码后的点云，输出体素概率图，取argmax作为关键帧平移。
  - **低层代理**：采用等变扩散策略（Equivariant Diffusion Policy），将观测条件化到关键帧帧中，通过去噪过程生成轨迹。
  - **堆叠体素编码器**：用等变PointNet聚合每个体素内的点特征，保留细粒度空间信息，并保持T(3)×SO(2)等变性。
  - **公式与证明**：形式上定义了π(o) = π_low(o, t_high) 其中 t_high = π_high(o)，帧传递τ(o, t_high)=o−t_high。理论上证明了整体策略关于平移和平面旋转的等变性（Proposition 4.2, 4.3）。

## 3. 实验设计
- **模拟环境**：
  - **基准**：RLBench（基于CoppeliaSim和PyRep），30个任务（20个常见任务+10个具有挑战性任务，如Lamp On、Push 3 Buttons）。
  - **数据**：每个任务100次专家演示。
  - **对比方法**：
    - 开放循环：3D Diffuser Actor、Chained Diffuser（层次化基线）。
    - 封闭循环：Equivariant Diffusion Policy (EquiDiff)。
- **真实世界环境**：
  - 机器人：UR5e + Robotiq 2F-85 gripper + 3个Intel RealSense D455 RGB-D相机。
  - 任务：Pot Cleaning（30演示）、Blocks to Drawer（20演示）、Blocks Stacking（30演示）。
  - 额外测试：一次泛化（仅1个演示，测试未见物体姿态）；环境变化（改变桌子颜色、添加干扰物）。
- **评估指标**：任务成功率（每个设置下20次试验）。

## 4. 资源与算力
- 论文中**未明确说明**所使用的GPU型号、数量以及具体训练时长。
- 仅提及训练设置：batch size=16，训练100,000次迭代（per task），使用AdamW优化器（学习率1e-4，权重衰减5e-4），DDPM扩散步骤100步。
- 无法判断具体硬件资源消耗。

## 5. 实验数量与充分性
- **数量**：
  - 模拟：30个任务 * 2种控制设置（开放/封闭）* 100次评估/任务 → 大量实验。
  - 消融实验：在6个任务上测试5种配置（无层次、无等变、无帧传递、无堆叠体素、无等变+无帧传递），共30组。
  - 真实世界：3个任务 * 20次试验（训练分布+未见分布）* 基线比较。
  - 额外：一次泛化2个方法*20次试验；环境变化2个方法*3种条件。
- **充分性与客观性**：
  - 实验覆盖了模拟到真实、开放循环到封闭循环、标准到长程精细任务、泛化到抗干扰等维度，较为全面。
  - 对比了最相关的基线（Chained Diffuser、EquiDiff等），消融验证了各模块贡献。
  - 但未报告每个任务的方差或置信区间，也未提供多个随机种子下的结果，可能影响统计可信度。

## 6. 论文的主要结论与发现
- HEP在模拟30个任务上，开放循环平均提升10%（相对基线Chained Diffuser），封闭循环提升23%（相对EquiDiff）。
- 在真实世界的三个任务上，开放循环HEP成功率80%-90%，远高于Chained Diffuser（20%-40%）。
- 一次泛化实验中，仅用1个演示，HEP成功率达80%，基线仅5%，凸显等变性带来的强泛化能力。
- 环境变化下（颜色和干扰物），HEP仍保持60%-90%成功率，基线完全失败。
- 消融表明，等变性和帧传递是性能提升的关键（分别降低24%和16%成功率）。

## 7. 优点
- **方法设计**：
  - 帧传递接口新颖灵活，允许低层在高层给出的坐标框架中做局部精细调整，避免刚性约束。
  - 首次将等变性引入层次化策略，并理论证明整体等变性，使系统对空间变换鲁棒。
  - 堆叠体素编码器保留点云细节，比传统平均池化更有效。
- **实验验证**：
  - 综合模拟和真实实验，覆盖多种任务类型（长程、精细、泛化），证明实用价值。
  - 消融实验充分，清晰显示各组件贡献。
  - 真实世界的一次泛化和环境变化实验凸显样本效率和鲁棒性。

## 8. 不足与局限
- **实验覆盖**：
  - 仅限于桌面操作场景，未扩展到人形机器人、移动操作等更复杂设置。
  - 未报告多次重复实验的统计波动，可能存在单次结果偏差。
  - 资源消耗未公开，不利于复现和公平比较。
- **方法局限**：
  - 帧传递仅支持3D平移，未处理旋转，限制了高层指导低层的完整姿态信息。
  - 缺乏记忆机制（如Transformer），导致在封闭循环的Pot Cleaning中陷入重复清洗循环。
  - 在Take Money任务出现过拟合（后期检查点成功率下降）。
- **应用限制**：
  - 依赖点云和体素表示，计算成本较高，实时性可能受限。
  - 高层仅预测粗平移，某些需要精确姿态的任务（如精密装配）可能不足。

（完）
