---
title: "Vintix: Action Model via In-Context Reinforcement Learning"
title_zh: Vintix：通过上下文强化学习实现动作模型
authors: "Andrei Polubarov, Lyubaykin Nikita, Alexander Derevyagin, Ilya Zisman, Denis Tarasov, Alexander Nikulin, Vladislav Kurenkov"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=gi9MOXNfw2"
tags: ["query:agent-papers"]
score: 9.0
evidence: 上下文强化学习实现推理时递归自我改进
tldr: 上下文强化学习（ICRL）有望实现推理时自适应学习，但可扩展性不足。本文提出Vintix，通过算法蒸馏训练一个跨领域固定模型，使其能在推理时通过试错进行上下文强化学习。实验表明，该方法在多个领域上达到了有竞争力的性能，为构建可自我改进的通用智能体奠定了基础。该工作推进了ICRL在复杂任务中的应用。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 849, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1633, \"height\": 678, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 825, \"height\": 842, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1776, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 836, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 856, \"height\": 919, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1150, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1556, \"height\": 2031, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1749, \"height\": 1970, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1747, \"height\": 1675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1750, \"height\": 1975, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1749, \"height\": 1068, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1568, \"height\": 2094, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1762, \"height\": 2012, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1763, \"height\": 1664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1765, \"height\": 1995, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gi9moxnfw2/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1759, \"height\": 996, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-gi9moxnfw2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 872, \"height\": 636, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gi9moxnfw2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gi9moxnfw2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 705, \"height\": 754, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gi9moxnfw2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1693, \"height\": 972, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gi9moxnfw2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1681, \"height\": 2324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gi9moxnfw2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1693, \"height\": 592, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gi9moxnfw2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1693, \"height\": 1224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gi9moxnfw2/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1075, \"height\": 2125, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gi9moxnfw2/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1691, \"height\": 753, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gi9moxnfw2/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1693, \"height\": 1277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gi9moxnfw2/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1692, \"height\": 1446, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gi9moxnfw2/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1691, \"height\": 819, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gi9moxnfw2/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1074, \"height\": 2131, \"label\": \"Table\"}]"
motivation: 上下文RL可扩展性不足，局限于玩具任务。
method: 提出Vintix，通过算法蒸馏训练固定模型实现跨领域上下文RL。
result: 在多个领域上实现了竞争力的in-context学习性能。
conclusion: 算法蒸馏是扩展上下文RL的有效途径。
---

## Abstract
In-Context Reinforcement Learning (ICRL) represents a promising paradigm for developing generalist agents that learn at inference time through trial-and-error interactions, analogous to how large language models adapt contextually, but with a focus on reward maximization. However, the scalability of ICRL beyond toy tasks and single-domain settings remains an open challenge. In this work, we present the first steps toward scaling ICRL by introducing a fixed, cross-domain model capable of learning behaviors through in-context reinforcement learning. Our results demonstrate that Algorithm Distillation, a framework designed to facilitate ICRL, offers a compelling and competitive alternative to expert distillation to construct versatile action models. These findings highlight the potential of ICRL as a scalable approach for generalist decision-making systems.

---

## 论文详细总结（自动生成）

# 论文《Vintix：通过上下文强化学习实现动作模型》详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：上下文强化学习（ICRL）是一种有前景的范式，它使智能体能在推理时通过试错交互进行学习，类似于大语言模型的上下文适应，但侧重于奖励最大化。然而，ICRL 的可扩展性一直局限于**玩具任务和单领域环境**，无法推广到更复杂、跨领域的场景。
- **整体含义**：本文试图迈出扩展 ICRL 的第一步，证明基于算法蒸馏（Algorithm Distillation）的**固定、跨领域模型**能够实现上下文强化学习行为，为构建通用决策智能体提供了一种可行的、基于奖励驱动的新路径。

## 2. 方法论

### 2.1 核心思想
- 采用 **算法蒸馏（Algorithm Distillation, AD）** 框架，将离线收集的强化学习学习历史（或近似历史）作为训练数据，通过**下一个动作预测**任务训练一个因果 Transformer 模型，使模型在推理时能够从上下文交互中自我纠正策略。

### 2.2 关键技术细节
#### 连续噪声蒸馏（Continuous Noise Distillation）
- 为解决原始 AD 数据收集成本高、需要完整 RL 训练轨迹的问题，本文提出了**连续噪声蒸馏**的变体，扩展了 Zisman et al. (2024a) 的 ADϵ 方法到**连续动作空间**。
- 算法流程（Algorithm 1）：
  - 初始化：采样初始状态 s₀。
  - 对于每一步 t：
    - 计算噪声幅度 ϵᵢ = E(t)（噪声调度函数）。
    - 采样均匀噪声 u ~ Uniform(amin, amax)。
    - 生成混合动作 aᵢ = (1-ϵᵢ) * πD(sᵢ) + ϵᵢ * u。
    - 执行动作并收集下一状态、奖励、终止标志。
    - 将 (s, a, s', r, t) 存入缓冲区。
- **噪声调度**：使用参数化的广义衰减函数控制 ϵ 从 1 平滑下降到 0，避免线性调度导致的奖励突变。

#### 跨领域数据集
- 收集了 **87 个任务**，覆盖 4 个领域：
  - MuJoCo（11 个任务）
  - Meta-World（45 个任务）
  - Bi-DexHands（15 个任务）
  - Industrial-Benchmark（16 个任务，通过 setpoint 参数 p 生成变化）
- 数据集统计：约 160 万条轨迹，2.227 亿个时间步（表 1）。
- **数据标准化**：对观测值进行归一化，奖励按任务缩放，以减轻任务间数值差异，鼓励模型依赖上下文而非任务标识。

#### 模型架构
- 采用 **TinyLLama** 作为 Transformer 骨干，参数量 **300M**（24 层，16 头，嵌入大小 1024，前馈隐藏大小 4096）。
- **输入表示**：每个 token 由 (当前观测、上一动作、上一奖励) 堆叠而成（非独立 token），从而压缩序列长度 3 倍。
- **编码器/解码器**：根据观测/动作空间维度分组，为每组使用独立的 MLP 头，将不同维度的状态映射到共享嵌入空间。
- **位置编码**：使用 **ALiBi**（相对位置编码），支持滑动注意力窗口和 KV-cache 高效推理。
- **损失函数**：动作预测的**均方误差（MSE）**。

#### 推理
- 冷启动（空上下文），逐步追加新交互，若上下文超过最大长度 L=8192，则丢弃最旧 token（滑动窗口）。
- 利用 FlashAttention 实现 KV-cache 加速。

## 3. 实验设计

### 3.1 数据集与基准
- **训练任务**：87 个任务（各领域内）。
- **验证任务**：
  - MuJoCo：修改物理参数（粘滞系数 0.05 和 0.1，重力 ±10%）。
  - Meta-World：ML45 拆分，5 个未见任务（bin-picking, box-close, door-lock, door-unlock, hand-insert）。
  - Bi-DexHands：ML20 拆分，5 个未见任务（door-close-outward, door-open-inward, door-open-outward, hand-kettle, hand-over）。
  - Industrial-Benchmark：setpoint p ∈ [80, 100]（训练时为 [0, 75]）。

### 3.2 对比方法
- **JAT**（Gallouédec et al., 2024）：基于专家蒸馏的通用智能体。
- **REGENT**（Sridhar et al., 2024）：检索增强的通用智能体。
- **Expert Distillation（ED）**：相同架构但仅用专家数据训练（消融实验）。
- **AD w/o rewards**：去除奖励信号的 AD 模型（消融实验）。

### 3.3 评估指标
- **归一化得分**：使用 IQM（Interquartile Mean）在多个随机种子下计算，相对于随机和专家得分进行归一化。

## 4. 资源与算力

- **训练硬件**：8 块 **NVIDIA H100 GPU**。
- **超参数**：batch size 64，梯度累积 2 步，序列长度 8192，学习率 3e-4，优化器 Adam（β₁=0.9, β₂=0.99）。
- **训练精度**：bf16。
- **总参数量**：约 **3.32 亿**。
- **训练时长**：论文未明确说明具体训练时间，但提到“使用 8 块 H100 GPU 训练”。

## 5. 实验数量与充分性

- **主要实验**：
  1. **训练任务自我纠正**（图 4）：在 4 个领域的训练任务上，展示多轮推理（many-shot ICRL）时性能随 shots 增加而提升。
  2. **与相关动作模型比较**（图 5）：在 MuJoCo 和 Meta-World 上对比 Vintix vs JAT vs REGENT，Vintix 显著领先。
  3. **泛化到参数变化**（图 6）：MuJoCo 和 Industrial-Benchmark 的未见参数设置。
  4. **泛化到新任务**（图 7）：Meta-World 和 Bi-DexHands 的 5 个未见任务，仅部分成功。
  5. **消融实验**（附录 C）：
     - 对比算法蒸馏（AD）与专家蒸馏（ED）。
     - 对比有无奖励信号（AD vs AD masked rewards）。
  6. **任务级详细结果**（附录 F, H, I）：每个任务的性能表。

- **充分性评价**：
  - 实验覆盖了**训练任务、参数变化、新任务**三个层次，较全面。
  - 与两个主流基线（JAT, REGENT）进行了公平比较（归一化基准一致）。
  - 消融实验验证了算法蒸馏和奖励信号的必要性。
  - 但**新任务泛化实验仅展示了成功和失败案例，缺乏系统统计**；Bi-DexHands 中 hand-over 因维度不匹配无法评估（报告为 0）。整体上，实验设计客观，但泛化能力仍较弱。

## 6. 主要结论与发现

1. **Vintix 实现了跨领域上下文自我纠正**：在 4 个训练领域上，模型从随机策略逐渐提升到接近专家水平（多数任务归一化得分 >0.95）。
2. **算法蒸馏优于专家蒸馏**：在 MuJoCo 和 Meta-World 上，AD 模型最终得分显著高于 ED 模型（图 8），证明了策略改进结构数据的重要性。
3. **奖励信号对于上下文适应性至关重要**：移除奖励后模型无法有效自我提升（附录 C）。
4. **泛化到参数变化可行但收敛较慢**：在修改的物理参数和 setpoint 上，模型仍能达到接近专家性能，但需要更多推理轮次。
5. **新任务泛化仍有限**：仅少数任务（如 door-unlock, door-open-inward）表现出部分适应，多数失败任务仅达到随机水平。

## 7. 优点

- **首次将 ICRL 扩展到跨领域连续动作空间**，突破了原有单领域、离散动作的局限。
- **提出连续噪声蒸馏**，简化了数据收集流程，不需完整 RL 训练轨迹即可生成近似学习历史。
- **公开了大规模跨领域数据集和工具**（87 任务，220M 时间步），促进社区研究。
- **架构设计高效**：通过分组编码器处理不同维度的状态/动作空间；堆叠 token 减少序列长度；ALiBi 位置编码支持滑动窗口推理。
- **实验设计全面**：包含训练任务、参数泛化、新任务泛化及消融研究，对比了强基线。
- **结果具有可解释性**：展示了模型在推理时随 shots 增加而逐渐改善的曲线，直观体现 ICRL 行为。

## 8. 不足与局限

- **新任务泛化能力弱**：仅在 87 个训练任务上学习，无法应对全新任务类型，与 Gato 等通用智能体差距明显。
- **依赖噪声调度精细调节**：不同任务可能需要不同的衰减函数（p 参数），增加了部署难度。
- **未涉及多模态输入**（如视觉、语言），限制了在真实机器人场景中的应用。
- **Bi-DexHands 上部分任务性能不稳定**（如 catchabreast 仅 0.17），且 hand-over 因维度不匹配无法评估。
- **数据集分布偏差**：各领域数据量不均衡（MuJoCo 占比 44.9%，Bi-DexHands 仅 14.2%），可能影响模型在较少数据领域的表现。
- **训练时长未报告**，可复现性细节略欠。

（完）
