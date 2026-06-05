---
title: "The Synergy of LLMs & RL Unlocks Offline Learning of Generalizable Language-Conditioned Policies with Low-fidelity Data"
title_zh: LLM与RL的协同作用：利用低保真数据实现可泛化语言条件策略的离线学习
authors: "Thomas Pouplin, Kasia Kobalczyk, Hao Sun, Mihaela van der Schaar"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=5hyfZ2jYfI"
tags: ["query:agent-papers"]
score: 5.0
evidence: 离线强化学习用于语言条件策略学习
tldr: 本文针对离线环境中语言条件策略泛化难的问题，提出TEDUO框架，利用大语言模型和强化学习的协同作用，从低质量无标签数据中学习可泛化的策略。该方法在符号环境中的未见目标和状态上展现了良好的迁移能力，为数据稀缺场景下的智能体训练提供了有效方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1713, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1647, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 802, \"height\": 210, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 975, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 776, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 492, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1339, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 886, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 717, \"height\": 712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1689, \"height\": 1767, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1757, \"height\": 840, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1672, \"height\": 833, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1736, \"height\": 1007, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1724, \"height\": 634, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 795, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 810, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1779, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1781, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1465, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1781, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1780, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1752, \"height\": 820, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1780, \"height\": 704, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 935, \"height\": 455, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1775, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1078, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 900, \"height\": 381, \"label\": \"Table\"}]"
motivation: 现有强化学习方法难以泛化到未见目标和状态，且需要大量标记数据。
method: 提出TEDUO离线训练流程，结合LLM和RL处理未标注低保真数据。
result: 在多个符号环境任务上，该方法显著提升了对新目标和状态的泛化能力。
conclusion: 该工作证明了LLM与RL结合能够从低质量数据中学习鲁棒的语言条件策略。
---

## Abstract
Developing autonomous agents capable of performing complex, multi-step decision-making tasks specified in natural language remains a significant challenge, particularly in realistic settings where labeled data is scarce and real-time experimentation is impractical. Existing reinforcement learning (RL) approaches often struggle to generalize to unseen goals and states, limiting their applicability. In this paper, we introduce $\textit{TEDUO}$, a novel training pipeline for offline language-conditioned policy learning in symbolic environments. Unlike conventional methods, $\textit{TEDUO}$ operates on readily available, unlabeled datasets and addresses the challenge of generalization to previously unseen goals and states. Our approach harnesses large language models (LLMs) in a dual capacity: first, as automatization tools augmenting offline datasets with richer annotations, and second, as generalizable instruction-following agents. Empirical results demonstrate that $\textit{TEDUO}$ achieves data-efficient learning of robust language-conditioned policies, accomplishing tasks beyond the reach of conventional RL frameworks or out-of-the-box LLMs alone.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

**研究动机**：  
开发能够遵循自然语言指令完成复杂多步决策任务的自主智能体是人工智能的重要目标。然而，现有方法往往需要大量标注数据或在线交互反馈，这在现实场景中难以实现；同时，强化学习方法对未见目标和状态的泛化能力不足，限制了其实际应用。

**核心问题**：  
在离线环境下，仅凭无标签的、次优（低保真）的状态-动作转换数据（\(x, a, x'\)）和一组未配对的自然语言目标描述 \(G\)，如何学习出能够泛化到全新目标和状态的策略？

**整体含义**：  
提出了 **TEDUO** 框架，首次利用大语言模型（LLM）与离线强化学习（Offline RL）的协同作用，从**低质量、无标签**的观测数据中学习可泛化的语言条件策略，挑战了传统方法对昂贵标注或在线交互的依赖。

## 2. 方法论：核心思想、关键技术细节

**核心思想**：  
将LLM的双重能力（低成本数据增强 + 可泛化的指令跟随）与传统RL的环境交互知识（最优策略学习）结合，形成三步流水线。

**三步流程**：

### 步骤1：构造可解MDP（Construction of Solvable MDPs）

- **状态抽象（可选）**：利用LLM（LLM_abstrct）基于自然语言目标 \(g\) 从原始状态 \(x\) 中提取仅与目标相关的特征，生成抽象状态 \(s_g\)，大幅降低状态空间维度。
- **目标条件事后标注（Hindsight Labeling）**：使用LLM（LLM_rwrd）判断抽象状态是否达成目标 \(g\)，生成二进制奖励标签。为减少LLM调用次数，训练轻量级代理奖励网络 \(R_\theta(\cdot; g)\) 来近似LLM标签，并将奖励分配到抽象状态空间 \(S_g\)。

### 步骤2：离线策略学习（Offline Policy Learning）

- 对每个训练目标 \(g \in G_{tr}\)，获得标注后的抽象数据集 \(D_g = \{(s_g, a, s'_g, r_g)\}\)。
- 应用离线RL算法（本文主要使用表格型Q学习，也可用DQN或过滤行为克隆）学习最优策略 \(\pi_g(a|s_g)\)。
- 得到针对每个训练目标的一组策略 \(\{\pi_g : g \in G_{tr}\}\)。

### 步骤3：LLM监督微调（LLM Supervised Fine-Tuning）

- 利用步骤2学到的策略生成监督数据集 \(D_{SFT}\)：每项数据包含目标 \(g\)、初始抽象状态 \(s_{g0}\) 以及最优动作序列 \([a^*_0, ..., a^*_{n_g}]\)。
- 对预训练LLM（如Llama-3-8B）进行标准的下一个词预测微调（SFT），将环境动态知识注入LLM。
- 微调后的LLM可作为通用语言条件策略 \(\pi^*\)，直接对未见目标和状态输出最优动作。

**算法流程（文字描述）**：
1. 输入：未标注数据集 \(D\)，训练目标集 \(G_{tr}\)。
2. 对每个 \(g \in G_{tr}\)，使用LLM进行状态抽象 + 奖励标注，形成抽象MDP。
3. 离线Q学习求解每个MDP，得到策略 \(\pi_g\)。
4. 基于 \(\pi_g\) 生成最优轨迹数据 \(D_{SFT}\)。
5. 在 \(D_{SFT}\) 上微调LLM。
6. 输出：可泛化的语言条件策略（微调后的LLM）。

## 3. 实验设计

### 环境与数据集

| 环境 | 说明 |
|------|------|
| **BabyAI**（主基准） | 符号化的网格世界，含9个房间的22×22网格。任务包括“go to”、“pick up”、“open”、“put next to”等。训练目标集 \(G_{tr}|\) = 500个，测试目标集 \(G_{test}|\) = 100个（语义新颖，经GPT-4改写）。数据集 \(D\) 含80万个非重复状态-动作-下一状态三元组，由BabyAI默认目标导向策略的随机混合生成。 |
| **Webshop**（辅助环境） | 模拟电商网站导航，动作空间动态变化，需生成自然语言搜索词。离线数据包含5000条轨迹，覆盖1500个指令。 |

### Benchmark与对比方法

- **Vanilla LLM**：Llama-3-8B / Llama-3-70B，零样本提示。
- **In-context + CoT**：链式思维推理+少量专家示范（来自TEDUO步骤2）。
- **DeepSeek-R1（蒸馏至Llama-8B）**：强推理模型。
- **BabyAI-IL-bot**：基于GRU+CNN+FILM+LSTM的模仿学习基线，在TEDUO步骤2的策略上训练。
- **TEDUO各步骤消融**：
  - Step 1 + Goal-conditioned Behavioral Cloning (GCBC)
  - Steps 1+2 (GCRL) – 离线Q学习策略
  - All steps – 全流程TEDUO-Llama-3-8B

### 评估指标

- 成功率（Success Rate）
- 平均回合长度（Episode Length）
- 无效动作比例（Invalid Actions）

## 4. 资源与算力

- **GPU型号**：4×NVIDIA A100（80GB VRAM）。
- **训练方式**：使用LoRA（rank=512）对Llama-3-8B-Instruct进行微调。
- **算力量化**：论文提供了“compute power”与性能的关系表（表4），以TFlops衡量（如5.2e7 TFlops对应266个训练目标）。但**未明确给出总训练时长**（如GPU小时数），仅提到“训练了最多20个epochs（Webshop）或3个epochs（BabyAI）”。
- **标注成本**：状态标注使用Llama-3-70B-Instruct（每个目标约5000个样本），代理奖励网络训练使用单GPU但时间较短。

## 5. 实验数量与充分性

**实验数量**：
- 主表（表1）含13个方法×2种环境设置（训练/测试）的对比，共400×2组（g, s₀）评估。
- 消融实验（表2）：3个方法对比。
- 技能转移与组合性实验（表3）：3种环境类型，多组对比。
- 缩放性实验（表4）：3种算力水平。
- 数据效率实验（图5）：多维度对比抽象 vs 原始状态。
- 可解释性实验（图4）：线性探针分析。
- 附录中还包括Webshop结果、DQN对比、数据收集策略影响分析、网格大小泛化实验。

**充分性与公平性**：
- **充分**：覆盖了泛化（新目标、新环境）、消融（各步骤贡献）、技能学习（内部化、组合性）、数据效率、计算缩放等多个维度。
- **公平**：所有baseline均在相同评估条件下测试（400个随机初始状态-目标对，统计标准误）。LLM提示模板、随机种子等细节在附录中公开。
- **潜在偏差**：主要环境BabyAI为符号网格世界，结果向真实机器人任务迁移可能存在差距；Webshop实验仅测试了目标泛化（无环境泛化）。对比的LLM baselines未使用相同微调计算量（仅推理），但论文通过消融证明了微调的关键作用。

## 6. 主要结论与发现

1. **纯LLM不足以解决多步决策**：即使使用70B参数、CoT+上下文学习，成功率低于21%，且无效动作率高。
2. **TEDUO显著提升泛化与数据效率**：全流程TEDUO在训练目标上达到65%成功率（vs vanilla LLM 17%）；在全新目标和环境中成功率达45%，远优于传统模仿学习（16%）。
3. **泛化源于技能组合而非记忆**：技能转移实验证明，分别在不同环境学习的子技能（导航、开门、捡起物体）可被组合解决全新任务；线性探针显示LLM内部学会了状态感知（如是否面对障碍物）。
4. **LLM起到“低成本数据增强器”和“可泛化策略器”的双重作用**：状态抽象使状态空间缩小10%，目标相关特征子空间缩小至20%，数据效率倍增。
5. **计算资源成为新的瓶颈**：增加训练目标数量可持续提升性能，表明在有限数据下扩展计算能力是有效路径。
6. **离线RL策略本身仍需改善**：步骤2的离线Q学习仅16%成功率，但经过LLM微调后跃升至65%，说明LLM的零样本知识弥补了离线策略的不足。

## 7. 优点

1. **数据要求极低**：仅需无标签的状态-动作转换数据和目标列表，无需奖励、最优性假设或专家示范。
2. **同时解决四大挑战（C1-C4）**：无标签、有限探索、未知数据收集策略、泛化。
3. **双LLM角色设计新颖**：LLM既作为低成本数据标注/抽象工具，又作为可泛化策略的基础模型。
4. **可解释性分析深入**：通过线性探针和动作概率分布揭示了微调前后LLM内部表示的变化，证明核心技能的习得。
5. **模块化结构**：状态抽象、离线RL算法、LLM微调均可替换或独立改进（如DQN代替Q学习）。
6. **环境泛化能力强**：能泛化到训练时未见过的更大网格（7×7对训练时的1-9房间），而CNN基线完全失败。

## 8. 不足与局限

1. **环境依赖**：要求状态可表示为文本（虽可通过VLM扩展），不适用于连续控制任务。
2. **动作空间离散化**：LLM输出需对应离散动作，不适合精细连续控制。
3. **LLM先验限制**：对于非常见领域或极端情况，LLM可能缺乏相关知识，导致策略失效。
4. **仍需要一定 practitioner knowledge**：用户需了解环境并手动拟定目标列表 \(G\)；数据收集策略与 \(G\) 的匹配程度影响性能（附录B.2分析显示需一定对齐）。
5. **实验范围相对局限**：主要结果基于BabyAI（符号网格世界），Webshop结果仅展示在附录；未在更复杂的3D或物理机器人环境验证。
6. **计算成本**：虽然数据标签成本低，但微调LLM仍需大量GPU资源（4×A100，数小时至数十小时），可能对小团队不够友好。
7. **稀疏奖励问题**：步骤2的离线RL仅依赖稀疏二进制奖励（是否达到目标），对复杂任务可能导致收敛困难；虽然TEDUO通过抽象缓解，但效果仍有限（表B.4显示某些目标召回率低）。

（完）
