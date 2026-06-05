---
title: "ARIA: Training Language Agents with Intention-driven Reward Aggregation"
title_zh: ARIA：基于意图驱动奖励聚合的语言智能体训练
authors: "Ruihan Yang, Yikai Zhang, Aili Chen, Xintao Wang, Jiangjie Chen, Siyu Yuan, Deqing Yang, Yanghua Xiao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=eumRwpgdMU"
tags: ["query:agent-papers"]
score: 7.0
evidence: 在意图空间聚合奖励，实现大语言模型智能体的高效强化学习训练
tldr: 大语言模型智能体在开放语言环境中面临动作空间巨大、奖励稀疏问题，导致强化学习困难。论文提出ARIA方法，将自然语言动作映射到意图空间并聚合奖励，显著降低奖励方差。在谈判和问答游戏等任务中，ARIA相比基线大幅提升样本效率和最终性能，为语言智能体强化学习提供了可行方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-eumrwpgdmu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1429, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eumrwpgdmu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 666, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eumrwpgdmu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1174, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eumrwpgdmu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1263, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eumrwpgdmu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1270, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eumrwpgdmu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1435, \"height\": 1067, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-eumrwpgdmu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 603, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eumrwpgdmu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 757, \"height\": 555, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eumrwpgdmu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1008, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eumrwpgdmu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1368, \"height\": 1704, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eumrwpgdmu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1447, \"height\": 530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eumrwpgdmu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 825, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eumrwpgdmu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 805, \"height\": 218, \"label\": \"Table\"}]"
motivation: 语言智能体动作空间巨大，奖励稀疏且方差大，阻碍RL有效训练。
method: 将语言动作投影到低维意图空间，在该空间聚合奖励，减少方差。
result: 在多个语言环境中，ARIA收敛更快，最终回报更高。
conclusion: 意图空间聚合是解决语言RL奖励稀疏的有效思路。
---

## Abstract
Large language models (LLMs) have enabled agents to perform complex reasoning and decision-making through free-form language interactions. However, in open-ended language action environments (e.g., negotiation or question-asking games), the action space can be formulated as a joint distribution over tokens, resulting in an extremely large and combinatorial action space. Sampling actions in such a space can lead to extreme reward sparsity, which brings large reward variance, hindering effective reinforcement learning (RL). To address this, we propose **ARIA**, a method that **A**ggregates **R**ewards in **I**ntention space to enable efficient and effective language **A**gents training. ARIA aims to project natural language actions from the high-dimensional joint token distribution space into a low-dimensional intention space, where semantically similar actions are clustered and assigned shared rewards. This intention-aware reward aggregation reduces reward variance by densifying reward signals, fostering efficient and effective policy optimization. Extensive experiments demonstrate that ARIA not only significantly reduces gradient variance, but also delivers substantial performance gains of average 9.95% across four downstream tasks (e.g., negotiation and text-based games), consistently outperforming strong offline and online RL baselines.

---

## 论文详细总结（自动生成）

# 论文《ARIA: Training Language Agents with Intention-Driven Reward Aggregation》详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **背景**：大语言模型（LLM）作为智能体可通过自由形式的自然语言与环境交互（例如谈判、问答游戏），其动作空间为 token 序列的联合分布，规模随词汇量 V 和序列长度 L 呈指数级增长（VL），导致**巨大而稀疏的动作空间**。
- **核心问题**：在开放语言动作任务中，传统强化学习（RL）面临**奖励极度稀疏**和**高方差**问题。采样型 RL 方法（如 PPO、REINFORCE）在此环境下难以有效学习，因为每个动作采样得到的二值奖励噪声大，难以稳定优化。
- **整体含义**：ARIA 提出通过“语义投影”将高维 token 空间中的自然语言动作映射到低维的“意图空间”，并在该空间内对语义相似的动作进行**奖励聚合**，从而**稠密化奖励信号、降低方差**，使得 RL 在开放语言环境中可行且高效。

## 2. 方法论：核心思想、关键技术细节与流程

- **核心思想**：利用 LLM 生成的自然语言动作背后隐含的意图（如“通过让步换取妥协”）远少于 token 组合数量。将语义相似的动作聚类为意图类，共享奖励，借此压缩动作空间、降低梯度方差。
- **关键技术细节**：
  - **意图空间构建**：使用预训练编码器（text-embedding-3-small）将动作和观测向量化，然后采用**层次凝聚聚类（HAC）** 将嵌入空间划分为 k 个簇，每个簇代表一个意图。
  - **奖励聚合**：定义聚类函数 ck，将每个动作和观测映射到簇标签。对同一历史-动作对（h̃, ã）的所有样本，计算其折扣奖励的平均值作为聚合回报 R̃(k)(h̃, ã)，作为优势估计。
  - **奖励导向的粒度选择（SplitScore）**：提出基于奖励变化的自适应粒度选择机制，避免传统聚类指标（如轮廓系数）偏好过粗聚类。通过计算 SplitScore(k) = δk/|D|，其中 δk 是聚类数从 k 增至 k+1 时全部历史-动作对的奖励变化之和。设置阈值 ε=0.01 和窗口 τ=10，当连续多个 k 的 SplitScore 均低于 ε 时停止分裂，选择最小 k 作为最优粒度。
  - **离线 REINFORCE**：使用聚合奖励作为优势，优化策略目标 J(θ) = E[∑ log πθ(a|h)·Ã(h,a)]。
- **理论分析**：
  - 证明聚合优势的方差 ≤ 原始优势方差（Lemma 4.1）。
  - 证明梯度估计方差降低（Lemma 4.2）。
  - 给出收敛界限（Theorem 4.1），表明相同样本量下误差更小。
  - 证明在簇内动作满足 ε-双模拟条件下，聚合引入的偏差为 O(ε)（Theorem 4.2）。

## 3. 实验设计

- **数据集/场景**：
  - **单智能体任务**：Twenty Questions（20问猜物体，157候选）、Guess My City（猜城市，100候选）。
  - **对抗性任务**：Bargaining（谈判分钱，2玩家轮流出价）、Negotiation（议价，买卖双方交替出价）。
- **Benchmark**：使用 Llama-3-8B-Instruct 作为策略模型，对手模型分别为 GPT-4o、DeepSeek-V3、Claude-3.5（涉及多种LLM后台，保证结果泛化性）。
- **对比方法**：
  - **离线基线**：Behavior Cloning (BC)、Trajectory-wise DPO、Step-wise DPO、SPAG（离线PPO）。
  - **在线基线**：ArCHer（层次RL）、StarPO（GRPO）。
- **评估指标**：
  - 单智能体：平均最终奖励（正确率）。
  - 对抗性：平均胜率（作为卖/买方时获得更高收益的比例），每种配置重复 25 次，共 48 种配置。

## 4. 资源与算力

- 论文明确说明：所有实验均使用 **8 块 NVIDIA A100-80GB GPU**，采用 LoRA（rank=8, α=16）参数高效微调。
- 离线训练：每个场景收集 1000 个轨迹，训练 3 个 epoch（单智能体每 epoch 16 batch，对抗 32 batch）。
- 在线训练：150 次迭代，每次迭代 32 个游戏（自对弈或与环境交互）。
- 推理阶段使用 GPT-4o、DeepSeek-V3、Claude-3.5 作为对手（通过 API 调用），未披露具体 GPU 时长。

## 5. 实验数量与充分性

- **充分性**：
  - **主实验**：4 个任务，3 种对手模型（对抗任务），3 次迭代（离线 ARIA 迭代 3 轮），共 4×3×3=36 种主要设置（对抗任务表格含 3 种对手×2 任务×3 轮=18 行）。
  - **消融实验**：奖励聚合 vs 无聚合 vs 无聚合+无衰减（图 5）；阈值 ε 消融（表 5）；嵌入模型消融（text-embedding-3-small、Qwen3-Embedding、e5-large-v2）（表 6）。
  - **在线扩展实验**：比较 ARIA 与 ArCHer、StarPO 在单智能体上的迭代曲线（图 3）。
  - **模型泛化实验**：在 Qwen2.5-7B/1.5B 上验证（表 3）。
  - **统计显著性检验**：对每个基线做 t 检验（表 7），所有 p < 0.05。
  - **理论分析**：方差降低、收敛界、偏差界。
- **客观性**：实验设计合理，覆盖单智能体和多智能体、不同LLM对手、多种基线；但对手均为API固定模型，未做自对弈迭代训练（仅在线ARIA有动态对手），可能存在一定局限性。

## 6. 主要结论与发现

- **ARIA 显著提升性能**：在对抗任务中平均胜率比最优基线高 9.67%~9.83%，单智能体任务高 9.82%。
- **奖励聚合有效降低方差**：图 4 显示聚合后奖励分布从二值极化变为平滑，方差显著下降。
- **迭代更新可持续改进**：3 次迭代后性能额外提升约 3%（对抗任务）。
- **在线 ARIA 比在线基线更快收敛**：图 3 显示 ARIA 在迭代过程中奖励上升更快、最终更高。
- **对模型架构不敏感**：在 Qwen2.5 系列上同样有效，验证了通用性。
- **理论支撑**：方差降低且偏差有界，解释训练稳定性提升。

## 7. 优点

- **方法创新性**：提出“语义投影”和意图空间奖励聚合概念，直接针对开放语言任务中动作空间过大、奖励稀疏的根本问题，思路清晰且合理。
- **实用性**：无需修改 LLM 架构，仅需预训练嵌入和层次聚类，计算开销小（离线训练仅需 8 块 A100 数小时）。
- **理论与实验结合**：不仅提供经验证明，还给出方差、偏差、收敛性的理论分析，增强了说服力。
- **实验设计全面**：覆盖多种任务类型（单/多智能体）、多种基线、多种LLM对手、多次迭代、消融实验、泛化性验证，结果可信度高。
- **可复现性**：提供了超参数、算法伪代码（附录 D）、提示词（附录 N）等细节。

## 8. 不足与局限

- **实验覆盖有限**：仅 4 个文本游戏任务，未在真实人机对话或复杂工具使用场景（如WebArena、SWE-bench）上验证。
- **嵌入质量依赖**：性能受嵌入模型质量影响（见表 6，e5-large-v2 表现较差），且聚类粒度阈值 ε 需要人工设定（消融显示敏感）。
- **对手假设**：对抗任务中对手为固定 API 模型，未进行完全自对弈训练，可能低估 ARIA 在交互式进化中的能力。
- **仅使用离散意图空间**：假设意图可被离散聚类，对意图连续或重叠的任务可能不适用。作者也在局限中承认这一点。
- **未与基于奖励模型的方法充分比较**：如 RLHF/DPO 使用偏好而非二值奖励，但未在相同设置下对比（仅对比了轨迹/步骤DPO，但用的是最终成功失败标签而非人类偏好）。
- **计算资源细节有限**：虽然给出了 GPU 型号和数量，但未说明每个训练/推理任务的具体耗时，难以评估整体效率。

## （完）
