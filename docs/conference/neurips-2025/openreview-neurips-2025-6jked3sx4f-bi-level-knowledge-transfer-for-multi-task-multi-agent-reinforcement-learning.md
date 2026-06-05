---
title: Bi-Level Knowledge Transfer for Multi-Task Multi-Agent Reinforcement Learning
title_zh: 面向多任务多智能体强化学习的双层知识迁移
authors: "Junkai Zhang, Jinmin He, Yifan Zhang, Yifan Zang, Ning Xu, Jian Cheng"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=6jKed3sx4f"
tags: ["query:agent-papers"]
score: 5.0
evidence: 多任务多智能体强化学习的双层知识迁移实现零样本泛化
tldr: 本文提出BiKT双层知识迁移方法，用于多任务多智能体强化学习的零样本泛化。在个体层提取可迁移技能嵌入，在团队层提取协调知识，从而在新任务中无需训练即可重用策略。实验证明该方法在多个MARL基准上有效提升了迁移性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1449, \"height\": 858, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1446, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 846, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1445, \"height\": 341, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1444, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1443, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1446, \"height\": 482, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 1294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1423, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1384, \"height\": 596, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1235, \"height\": 517, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1231, \"height\": 1072, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1348, \"height\": 1493, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1154, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 674, \"height\": 773, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1456, \"height\": 1046, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1455, \"height\": 891, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1445, \"height\": 794, \"label\": \"Table\"}]"
motivation: 在线训练成本高，需从离线数据中实现跨任务零样本策略重用。
method: 提出双层知识迁移，分别提取个体技能和团队协调知识。
result: 在多个MARL任务上实现有效的零样本泛化。
conclusion: 同时迁移个体和团队知识是跨任务迁移的关键。
---

## Abstract
Multi-Agent Reinforcement Learning (MARL) has achieved remarkable success in various real-world scenarios, but its high cost of online training makes it impractical to learn each task from scratch. 
To enable effective policy reuse, we consider the problem of zero-shot generalization from offline data across multiple tasks. 
While prior work focuses on transferring individual skills of agents, we argue that the effective policy transfer across tasks should also capture the team-level coordination knowledge.
In this paper, we propose Bi-Level Knowledge Transfer (BiKT) for Multi-Task MARL, which performs knowledge transfer at both the individual and team levels. 
At the individual level, we extract transferable individual skill embeddings from offline MARL trajectories.
At the team level, we define tactics as coordinated patterns of skill combinations and capture them by leveraging the learned skill embeddings. 
We map skill combinations into compact tactic embeddings and then construct a tactic codebook.
To incorporate both skills and tactics into decision-making, we design a bi-level decision transformer that infers them in sequence.
Our BiKT leverages both the generalizability of individual skills and the diversity of tactics, enabling the learned policy to perform effectively across multiple tasks.
Extensive experiments on SMAC and MPE benchmarks demonstrate that BiKT achieves strong generalization to previously unseen tasks.

---

## 论文详细总结（自动生成）

# 面向多任务多智能体强化学习的双层知识迁移（BiKT）—— 论文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：多智能体强化学习（MARL）在众多现实场景（如自动驾驶、机器人协作、分布式控制）中取得显著成功，但针对每个新任务从头训练代价极高，因为需要大量在线交互和复杂的协调策略。因此，利用已有任务的离线数据训练策略，并零样本迁移到未见任务，是降低学习成本的关键路径。
- **核心问题**：现有方法主要关注在个体层面迁移智能体的技能（individual skills），但忽略了团队层面的协调知识（cooperative tactics）。例如，不同任务中可能共享相同的团队战术（如“集火一个敌人”），但个体技能组合因智能体数量不同而不同。仅迁移个体技能无法传递这些协调模式，导致迁移效率不足。
- **整体含义**：多任务MARL中的有效策略迁移需要同时考虑两个层面：个体技能的可重用性和团队战术的可迁移性。作者提出BiKT框架，在个体层面提取可迁移的技能嵌入，在团队层面构造离散的战术码本，并通过双层决策Transformer（BDT）实现顺序推理，从而在新任务中实现零样本泛化。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将跨任务迁移分解为两个层级：
  1. **个体层（Individual-level）**：学习每个智能体的隐式技能表示（skill embedding），捕捉可重用的动作模式。
  2. **团队层（Team-level）**：定义“战术”（tactic）为技能组合的协调模式，将不同任务中语义相同的技能组合映射到同一个紧凑的战术嵌入，并构建离散的战术码本。
- **关键技术细节**：
  - **个体技能学习**：使用变分自编码器（VAE）框架。个体技能编码器 \( p_{\text{skill}}(\cdot | s, a, i) \) 从全局状态、联合动作和智能体索引提取技能嵌入 \( z_i \)，动作解码器 \( q_{\text{act}}(\cdot | \tau_i, z_i) \) 根据局部历史重构动作。优化目标包含动作重构的负对数似然和KL散度正则项。
  - **团队战术学习**：采用矢量量化变分自编码器（VQ-VAE）。战术编码器 \( p_{\text{tac}}(\cdot | s, \{z_i\}) \) 将状态和所有技能嵌入映射为连续表示 \( \hat{c} \)，然后通过最近邻搜索量化到战术码本 \( C = \{c_k\}_{k=1}^K \) 中的离散嵌入。技能解码器 \( q_{\text{skill}}(\cdot | \tau_i, c_k) \) 根据局部历史和战术重构每个智能体的技能。损失函数包括技能重构损失、码本承诺损失以及码本间距离正则项（促进战术多样性）。
  - **双层决策Transformer（BDT）**：作为策略模型 \( \pi_i^\theta \)，以自回归方式先预测战术索引 \( I_c \)，然后从码本检索对应战术 \( c \)，再生成个体技能 \( z \)，最后由动作解码器输出动作。训练时，使用预训练的技能编码器和战术编码器生成监督信号（技能和战术索引），优化分类交叉熵损失。同时，输入观测被解耦为实体特征以处理变数量智能体。
- **训练流程**：分为三个阶段：
  1. 训练个体技能VAE（最小化 \( L_{\text{skill}} \)）→ 获得技能嵌入和动作解码器。
  2. 训练战术码本VQ-VAE（最小化 \( L_{\text{tactic}} \)）→ 获得战术码本及技能解码器。
  3. 训练BDT策略（最小化 \( L_{\text{policy}} \)）→ 使用前两个阶段产生的标签进行监督学习。
- **执行阶段**：每个智能体运行时，根据历史预测战术索引，检索战术，生成技能，再解码为动作。

## 3. 实验设计

- **使用场景/数据集**：
  - **SMAC（StarCraft II Micromanagement）**：三个任务集：
    - Marine-Hard：源任务为3m、5m_vs_6m、9m_vs_10m；测试任务为4m、5m、10m、12m、7m_vs_8m、8m_vs_9m、10m_vs_11m、10m_vs_12m、13m_vs_15m。
    - Marine-Easy：源任务为3m、5m、10m；测试任务为4m、6m、7m、8m、9m、11m、12m。
    - Stalker-Zealot：源任务为2s3z、2s4z、3s5z；测试任务为1s3z、1s4z、1s5z、2s5z、3s3z、3s4z、4s3z、4s4z、4s5z、4s6z。
  - **MPE（Multi-Agent Particle Environment）**：Cooperative Navigation（CN）任务集，源任务为CN-2、CN-4，测试任务为CN-3、CN-5。
- **离线数据质量**：每个任务提供了四种质量的数据集：Expert、Medium、Medium-Expert、Medium-Replay。
- **对比方法**：
  - **UPDeT**：基于Transformer的通用策略架构。
  - **ODIS**：基于协调技能的多任务迁移方法。
  - **HiSSD**：层次化技能学习方法。
- **评估指标**：平均胜率（win rate）或平均回报，每项实验使用5个随机种子，每个种子评估32个episode。

## 4. 资源与算力

- **论文附录说明**：实验使用 Intel(R) Xeon(R) Gold 5220 CPU 和 NVIDIA TITAN RTX GPU。每个任务集的平均训练时长为8小时。未明确提及具体GPU数量和并行数，但综合来看算力需求适中，属于单卡可完成级别。

## 5. 实验数量与充分性

- **实验数量**：论文在3个SMAC任务集（每集包含多个源任务和9~12个测试任务）和1个MPE任务集上进行了大量实验。每个方法在每种数据质量下（Expert/Medium/Medium-Expert/Medium-Replay）分别给出结果，因此涉及大量数据点。此外，还进行了充分的消融实验（包括去掉团队战术、使用连续战术嵌入、改变上下文长度、改变战术码本大小等），以及可视化分析（技能嵌入t-SNE、战术使用频率分布、技能/战术语义示例）。
- **充分性评估**：实验设计比较全面，覆盖多种任务类型（同构/异构、对称/非对称、数量变化），数据质量多样，对比多种强基线。消融实验验证了各个组件的必要性。统计上使用5随机种子和32个episode的均值标准差，结果可复现。因此，实验是充分、客观且公平的。

## 6. 论文的主要结论与发现

- BiKT在几乎所有任务集和数据质量下都显著优于UPDeT、ODIS和HiSSD，尤其在Marine-Hard和Stalker-Zealot等复杂任务上优势明显。
- 个体技能和团队战术的两层迁移是提升跨任务泛化的关键；丢掉团队战术（w/o C）或使用连续战术（Con-Tac）均导致性能下降。
- 离散战术码本能有效捕捉跨任务共享的协调模式，并允许任务自适应选择不同战术，避免技能组合单一化。
- 技能嵌入在不同任务间呈现聚类，表明存在共享的可重用技能；战术使用频率随任务变化，说明策略具备自适应能力。
- 零样本泛化在未见任务上表现良好，尤其当任务与源任务存在相似战术时（如不对称兵力场景）。

## 7. 优点

- **创新性**：首次将多任务MARL迁移分解为个体技能和团队战术两个层级，并提出对应的学习方法，概念清晰。
- **技术合理性**：使用VAE学习技能连续表示，VQ-VAE离散化战术码本，既保留多样性又提供稳定指导。BDT自回归决策顺序与认知一致（先决定战术再执行技能）。
- **实验充分**：在多个难度级别、多种数据质量、大量测试任务上进行对比，消融实验全面，结果统计稳定。
- **可解释性**：通过可视化技能和战术分布及其语义，提供了对所学知识的直观理解，有助于分析迁移机制。

## 8. 不足与局限

- **扩展性未验证**：论文仅在有限规模的任务集（最多约15个智能体）上测试，未在更大规模（如数百智能体的场景）或更异构的任务分布上评估，泛化性有待进一步验证。
- **依赖离线数据质量**：在Medium-Replay等低质量数据上，BiKT的优势虽有但仍有限，部分任务胜率偏低，说明对数据质量有一定敏感性。
- **战术码本大小需手工设定**：实验中K=16，论文未讨论如何自动确定最优码本大小，可能需人工调参。
- **假设**：假设源任务之间共享可迁移的战术，如果任务分布极度多样（如不同单位类型、完全不同目标），战术复用可能失效。
- **计算成本**：三阶段训练流程（技能、战术、策略）相比端到端方法更复杂，但通常能接受。
- **未讨论负迁移**：当源任务与目标任务战术不兼容时，可能发生负迁移，论文未对此分析。

（完）
