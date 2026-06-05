---
title: "Oryx: a Scalable Sequence Model for Many-Agent Coordination in Offline MARL"
title_zh: Oryx：面向离线多智能体强化学习中多智能体协调的可扩展序列模型
authors: "Juan Claude Formanek, Omayma Mahjoub, Louay Ben Nessir, Sasha Abramowitz, Ruan John de Kock, Wiem Khlifi, Daniel Rajaonarivonivelomanantsoa, Simon Verster Du Toit, Arnol Manuel Fokam, Siddarth Singh, Ulrich Armel Mbou Sob, Felix Chalumeau, Arnu Pretorius"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=XzXGqoUNUa"
tags: ["query:agent-papers"]
score: 7.0
evidence: 离线多智能体强化学习中可扩展序列模型实现多智能体协调
tldr: 本文提出Oryx算法，用于离线协作多智能体强化学习。该算法结合保留机制架构与隐式约束Q学习，实现自回归策略更新，有效处理长轨迹上的多智能体协调。在SMAC、RWARE等基准上验证了其在复杂环境中的可扩展性和协调能力。Oryx为大规模多智能体协调提供了高效离线方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1364, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 265, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1182, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 1357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1326, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 425, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1302, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1360, \"height\": 1186, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 732, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 732, \"height\": 459, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 741, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1170, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 656, \"height\": 417, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 636, \"height\": 418, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1167, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 865, \"height\": 414, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 642, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 709, \"height\": 411, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1317, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1026, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 707, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1452, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1451, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 702, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 795, \"height\": 418, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 700, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 703, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 719, \"height\": 419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 741, \"height\": 419, \"label\": \"Table\"}]"
motivation: 离线多智能体强化学习面临多智能体多步协调的挑战。
method: 提出基于保留机制的自回归策略更新，结合隐式约束Q学习。
result: 在多个基准上优于现有方法，保持长轨迹时序连贯性。
conclusion: 自回归序列模型有效解决离线多智能体协调问题。
---

## Abstract
A key challenge in offline multi-agent reinforcement learning (MARL) is achieving effective many-agent multi-step coordination in complex environments. In this work, we propose Oryx, a novel algorithm for offline cooperative MARL to directly address this challenge. Oryx adapts the recently proposed retention-based architecture Sable and combines it with a sequential form of implicit constraint Q-learning (ICQ), to develop a novel offline autoregressive policy update scheme. This allows Oryx to solve complex coordination challenges while maintaining temporal coherence over long trajectories. We evaluate Oryx across a diverse set of benchmarks from prior works—SMAC, RWARE, and Multi-Agent MuJoCo—covering tasks of both discrete and continuous control, varying in scale and difficulty. Oryx achieves state-of-the-art performance on more than 80% of the 65 tested datasets, outperforming prior offline MARL methods and demonstrating robust generalisation across domains with many agents and long horizons. Finally, we introduce new datasets to push the limits of many-agent coordination in offline MARL, and demonstrate Oryx's superior ability to scale effectively in such settings.

---

## 论文详细总结（自动生成）

# 论文总结：Oryx——面向离线多智能体强化学习中多智能体协调的可扩展序列模型

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：离线多智能体强化学习（Offline MARL）旨在仅从静态数据集中训练多智能体策略，无需与环境交互。但面临两大核心挑战：①**外推误差**：智能体在训练中选择超出数据集分布的动作，随着智能体数量增加呈指数级放大；②**协调失败**：智能体依赖历史行为（通常来自次优策略），导致策略不兼容。现有方法多聚焦于少量智能体的场景，尚未验证在大量智能体下的可扩展性。
- **整体含义**：本文提出 **Oryx**，一种全新的离线合作 MARL 算法，通过将可扩展的序列建模与约束离线策略改进相结合，同时克服外推误差和协调失败，并显著提升多智能体协调的规模上限（最高 50 个智能体）。

## 2. 方法论

### 核心思想
- 将 **Sable**（基于保留机制的高效序列模型）与 **隐式约束 Q 学习（ICQ）** 相结合，设计自回归策略更新方案。
- 利用 **优势分解定理**（Kuba et al., 2021），将联合策略分解为每个智能体依次更新的条件策略，保证单调改进。

### 关键技术细节
- **网络架构**：修改 Sable 编码器-解码器架构。编码器处理观测序列，解码器同时输出**策略分布**和 **Q 值估计**（双输出头）。不使用原始 Sable 中的值头，改为端到端联合训练。
- **自回归 ICQ 损失**：
  - 策略损失：按顺序更新每个智能体 i_j，优化目标为  
    `E[ -1/Z(τ) log(π_ij(a_ij|τ, a_i1:j-1)) exp(A_i1:j(τ, a_i1:j)/α) ]`  
    其中 Z 为分区函数，α 为拉格朗日系数。
  - 批评家损失：类似 ICQ 的 SARSA 更新，使用数据集中的目标动作计算隐式重要性权重。
- **反事实基线**：采用 Counterfactual Multi-Agent Policy Gradients（Foerster et al., 2018）中的优势计算方式，降低方差（避免随智能体数量线性增长的方差上界）。
- **算法流程**（Algorithm 1）：随机抽取 mini-batch，随机排列智能体顺序，依次更新每个智能体的批评家和策略。

### 关键创新
1. 首次将保留机制序列模型（Sable）引入离线 MARL。
2. 推导出自回归 ICQ 策略更新定理，实现顺序约束策略改进。
3. 双解码器联合输出 Q 值和策略，支持反事实优势计算。

## 3. 实验设计

### 数据集与场景
- **SMAC**（StarCraft Multi-Agent Challenge）：43 个数据集，涵盖 9 个场景（如 2c_vs_64zg、3s_vs_5z、corridor 等），包含不同数据质量（Good/Medium/Poor/Expert/Mixed/Med. Replay）。
- **MAMuJoCo**（连续控制）：16 个数据集，包括 2x3 HalfCheetah、6x1 HalfCheetah、2x4 Ant、3x1 Hopper。
- **RWARE**（仓库物流）：6 个数据集，Tiny (11×11) 和 Small (11×20)，智能体数量 2/4/6。
- **Connector**（协作网格世界）：7 个数据集，智能体数量从 3 到 50，含新引入的 30/40/50 智能体场景。
- **T-Maze**：自建两个智能体的协调环境，用于消融实验。

### 对比方法
- 主流离线 MARL 算法：MAICQ、IQL-CQL、MADT、ComaDICE、CFCQL、OMIGA、AlberDICE、DoF、OMAR、BCQ、IQL、AWAC 等。
- 消融实验：去除自回归动作、去除记忆（缩短序列长度）、去除 ICQ 损失。
- 架构对比：将 Oryx 与 **MAT+ICQ**（使用相同 ICQ 损失的 Transformer 序列模型）比较。

### 评估指标
- 胜率（Win Rate）或累计回报（Episode Return），归一化分数（相对于随机和专家策略）。
- 统计显著性：异方差双侧 t 检验（95% 置信区间），遵循 Papoudakis et al., 2021 和 Formanek et al., 2024b 的协议。

## 4. 资源与算力

- 论文未提供详细的算力清单（GPU 型号、数量、训练总时长）。
- 提及使用 **Google TPU Research Cloud (TRC)** 支持研究。
- 在 Connector 实验部分提到“所有 Connector 实验均分布在 NVIDIA A100 GPU（40GB 和 80GB VRAM）上”。
- 各任务训练步数为 10 万次梯度更新（SMAC/RWARE/Connector），每次更新包含 64 个样本批。

## 5. 实验数量与充分性

- **总实验规模**：65 个数据集（SMAC 43 + MAMuJoCo 16 + RWARE 6）水平对比，加上 Connector 7 个规模扩展实验和 T-Maze 消融实验。
- **重复次数**：大部分实验使用 10 个随机种子（部分大型 Connector 场景使用 3 个种子），最终回报取均值和标准差。
- **公平性**：统一采用 OG-MARL 框架的标准化数据与评估流程；所有对比方法结果来自原始论文或公开基准，Oryx 在不同设定下使用固定或根据数据集质量调整的超参数（如 ICQ 策略温度）。
- **消融实验**：在 T-Maze 上系统性地验证了自回归动作、记忆机制、ICQ 损失三个核心组件的必要性；在 Connector 上与 MAICQ 对比，并在 SMAC/RWARE 上与 MAT+ICQ 对比以验证架构优势。
- **充分性**：覆盖离散/连续控制、不同智能体数量（2~50）、不同数据质量（随机/中等/专家）、不同任务类型（部分可观测、稀疏奖励、密集奖励），实验设计较为全面客观。

## 6. 主要结论与发现

- Oryx 在 **80% 以上（34/43 SMAC, 14/16 MAMuJoCo, 6/6 RWARE）** 的数据集上达到或超越当前最优（SOTA），部分提升幅度接近 20%。
- 在大量智能体场景（Connector 23~50 智能体）中，Oryx 保持接近专家水平的性能，而基线 MAICQ 性能急剧下降，证明了 Oryx 在规模扩展上的显著优势。
- 消融实验表明：**自回归动作、长程记忆、ICQ 约束**三者缺一不可，共同实现稳定的离线多智能体协调。
- 与 MAT+ICQ 对比，Oryx 在所有聚合指标（中位数、IQM、均值、最优间隙）上均更优，验证了 Sable 保留机制作为骨干网络的优势。

## 7. 优点

1. **方法创新**：巧妙融合保留机制序列模型与离线约束策略优化，理论推导自回归 ICQ 损失，降低方差。
2. **大规模可扩展**：在高达 50 个智能体的设定下仍保持有效协调，突破此前离线 MARL 方法的规模限制。
3. **实验系统全面**：65 个数据集覆盖多种环境和数据质量，消融实验设计清晰，对比方法全面，统计检验规范。
4. **开放贡献**：公开所有代码和数据集（含新的大型 Connector 数据集），利于社区复现和后续研究。

## 8. 不足与局限

1. **实验覆盖有限**：虽然环境多样，但仍是模拟环境，未在真实工业场景（如物流、交通）中验证，通用性待进一步检验。
2. **超参数敏感性**：ICQ 策略温度需根据数据集质量调整（论文中提到在 SMAC 上范围为 0.1~0.9），实际应用中可能增加调参成本。
3. **算力报告不详细**：未给出单次实验的 GPU 耗时、总训练算力等，不利于对比计算成本。
4. **时序依赖假设**：自回归顺序更新假设智能体间可观测顺序，部分实际系统可能难以满足（如通信延迟或局部观测）。
5. **未讨论计算效率**：序列模型（尤其是保留机制）在长序列上的内存和计算开销未与基线方法量化对比。

（完）
