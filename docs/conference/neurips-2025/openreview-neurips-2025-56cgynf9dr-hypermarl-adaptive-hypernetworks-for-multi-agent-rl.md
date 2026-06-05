---
title: "HyperMARL: Adaptive Hypernetworks for Multi-Agent RL"
title_zh: 超网络多智能体强化学习：自适应超网络用于多智能体合作
authors: "Kale-ab Tessera, Arrasy Rahman, Amos Storkey, Stefano V. Albrecht"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=56CgYnf9Dr"
tags: ["query:agent-papers"]
score: 6.0
evidence: 多智能体自适应协作超网络
tldr: 多智能体强化学习中，参数共享策略往往抑制行为多样性。HyperMARL提出自适应超网络框架，通过生成个性化策略参数实现同质、特化或混合行为的灵活切换，避免了梯度干扰和额外复杂性。实验表明该方法在多个MARL基准上提升了合作效率。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 732, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1424, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1192, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 480, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1448, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1414, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 496, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1309, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1307, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 851, \"height\": 692, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1430, \"height\": 651, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 864, \"height\": 617, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 939, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1418, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1362, \"height\": 902, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 654, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1192, \"height\": 237, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1445, \"height\": 1116, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1444, \"height\": 1294, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1400, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 861, \"height\": 739, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 932, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 664, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1594, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1458, \"height\": 374, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1490, \"height\": 1714, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1344, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1453, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 864, \"height\": 1552, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 871, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 474, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 846, \"height\": 895, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 545, \"height\": 671, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 655, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 872, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1007, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1175, \"height\": 1360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 689, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 725, \"height\": 1544, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 729, \"height\": 1543, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 702, \"height\": 1541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1422, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 702, \"height\": 1549, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1218, \"height\": 812, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1459, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1710, \"height\": 443, \"label\": \"Table\"}]"
motivation: 多智能体强化学习需要策略能够自适应表达同质、特化或混合行为，但现有参数共享方法因梯度干扰而抑制多样性。
method: 提出自适应超网络框架，每个智能体从共享超网络中生成个性化策略参数，无需手动设定多样性水平或顺序更新。
result: 在多个MARL基准任务上，超网络方法在保持参数共享效率的同时显著提升了行为多样性和合作性能。
conclusion: 自适应超网络为多智能体系统提供了一种无需复杂设计的灵活合作范式。
---

## Abstract
Adaptive cooperation in multi-agent reinforcement learning (MARL) requires policies to express homogeneous, specialised, or mixed behaviours, yet achieving this adaptivity remains a critical challenge. While parameter sharing (PS) is standard for efficient learning, it notoriously suppresses the behavioural diversity required for specialisation. This failure is largely due to cross-agent gradient interference, a problem we find is surprisingly exacerbated by the common practice of *coupling agent IDs with observations*. Existing remedies typically add complexity through altered objectives, manual preset diversity levels, or sequential updates -- raising a fundamental question: *can shared policies adapt without these intricacies?* We propose a solution built on a key insight: an agent-conditioned hypernetwork can generate agent-specific parameters and *decouple* observation- and agent-conditioned gradients, directly countering the interference from coupling agent IDs with observations. Our resulting method, **HyperMARL**, avoids the complexities of prior work and empirically reduces policy gradient variance. Across diverse MARL benchmarks (22 scenarios, up to 30 agents), HyperMARL achieves performance competitive with six key baselines while preserving behavioural diversity comparable to non-parameter sharing methods, establishing it as a versatile and principled approach for adaptive MARL. The code is publicly available at https://github.com/KaleabTessera/HyperMARL.

---

## 论文详细总结（自动生成）

### 论文详细中文总结

#### 1. 核心问题与整体含义（研究动机和背景）
- **问题**：在多智能体强化学习（MARL）中，自适应协作需要策略能够灵活展现同质、特化或混合行为。然而，标准的**参数共享（PS）** 方法虽然高效，却会抑制行为多样性，导致特化失败。根本原因在于**跨智能体梯度干扰**，而作者发现将智能体ID与观测耦合会进一步加剧这一问题。
- **现有解决方案的局限**：现有改进方法（如内在奖励、角色分配、顺序更新等）引入了额外的复杂性（修改目标函数、手动预设多样性水平、需要预训练或顺序更新），缺乏简洁性。
- **核心研究问题**：能否设计一种共享的MARL架构，在不改变学习目标、不预设多样性水平、不依赖顺序更新的前提下，同时支持特化与同质行为？

#### 2. 方法论
- **核心思想**：利用**智能体条件超网络（agent-conditioned hypernetwork）**，为每个智能体动态生成策略与价值网络的参数，从而解耦观测条件与智能体条件梯度，直接缓解由ID-观测耦合导致的梯度干扰。
- **关键技术细节**：
  - **超网络架构**：超网络输入为智能体嵌入（one-hot ID或可学习嵌入），输出为每个智能体的专用参数 \( \theta_i = h_\pi^\psi(e_i), \phi_i = h_V^\phi(e_i) \)。
  - **梯度解耦**：通过链式法则，策略梯度分解为**智能体条件因子**（依赖于智能体嵌入，确定性）和**观测条件因子**（依赖于轨迹样本，随机）。这一分解使得超网络先对每个智能体的噪声进行平均，再应用确定性变换，从而降低梯度方差。
  - **初始化缩放**：超网络初始参数确保生成的智能体参数符合标准初始化分布（如正交初始化、保持fan-in/out），促进训练稳定性。
  - **MLP与线性变体**：线性超网络使用one-hot ID直接映射；MLP变体使用可学习嵌入和隐藏层，提升表达能力。

#### 3. 实验设计
- **环境与场景**：使用5种MARL环境（22个场景），涵盖离散/连续动作、2～30个智能体，要求同质、异质或混合行为。
  - **Dispersion（VMAS）**：4个智能体离散动作，需特化。
  - **Navigation（VMAS）**：2/4/8个智能体连续动作，配置共享、唯一或混合目标。
  - **Multi-Agent MuJoCo**：2~17个智能体连续控制，需异质协作。
  - **SMAX**：2~20个智能体离散动作（星际争霸简化版），通常需同质行为。
  - **Blind-Particle Spread (BPS)**：15~30个智能体离散动作，需推断角色。
- **Baseline方法**：对比六种代表性方法：
  - **FuPS+ID**（全参数共享）、**NoPS**（无参数共享）
  - **DiCo**（预设多样性水平）
  - **HAPPO**（顺序更新）
  - **Kaleidoscope**（可学习掩码+多样性损失）
  - **SePS**（选择性参数共享+预聚类）
- **评价指标**：平均回报（IQM + 95% bootstrap CI）、策略梯度方差、行为多样性（Jensen-Shannon距离计算的系统神经多样性SND）。

#### 4. 资源与算力
- 论文附录J明确列出了计算资源表：
  - **Specialisation/Synchronisation & Dispersion**：8核AMD EPYC CPU，每run 2-6小时（依赖智能体数量），总250小时。
  - **Navigation**：8核CPU + NVIDIA RTX A4500，每run 4-10小时，总320小时。
  - **MAMuJoCo**：8核CPU + NVIDIA RTX A4500，每run 8-24小时，总1680小时（场景与算法依赖）。
  - **SMAX**：8核CPU + NVIDIA RTX A4500，每run 2-5小时，总160小时。
- 所有实验在单个NVIDIA T4或A4500 GPU上进行，未说明使用多卡并行。

#### 5. 实验数量与充分性
- **实验总数**：覆盖22个场景，至少5个随机种子（Dispersion用10种子），数量充分。
- **消融实验**：包括梯度解耦（w/o GD）和初始化缩放（w/o RF）的消融，验证了核心机制的必要性。
- **敏感性分析**：对SMAX任务中学习率、嵌入维度、隐藏层尺寸进行了扫描（见表5）。
- **公平性**：与baseline使用相同算法骨干（IPPO/MAPPO/A2C/MATD3），遵循原论文超参数；仅对DiCo在n>2时进行额外调参；HyperMARL与baseline使用等价容量的网络。
- **统计严谨性**：采用IQM（interquartile mean）和95% bootstrap置信区间，遵循Agarwal等（2021）推荐的最佳实践。

#### 6. 主要结论与发现
- **核心验证**：超网络梯度解耦能有效实现自适应行为，无需修改目标、预设多样性或顺序更新。
- **性能结果**：
  - 在需要特化的Dispersion中，HyperMARL匹配NoPS性能，远超FuPS+ID。
  - 在MAMuJoCo（含17智能体Humanoid）中，HyperMARL与HAPPO等非共享/顺序方法竞争，且是唯一稳定学习的共享actor方法。
  - 在Navigation中（同质、异质、混合目标），HyperMARL在所有规模下表现稳健，n=8优势明显。
  - 在SMAX（同质主导）中，HyperMARL与FuPS基线性能相当，表明无内在特化偏见。
- **多样性测量**：HyperMARL达到NoPS级别的行为多样性（SND），而FuPS多样性低。
- **梯度方差**：HyperMARL的策略梯度方差低于FuPS+ID，印证了解耦机制带来的稳定性。
- **嵌入分析**：可学习嵌入在需要同质行为时收缩靠近，在需要特化时保持正交，说明超网络自适应调整。

#### 7. 优点
- **简洁性**：不改变RL目标，无需预设多样性水平或顺序更新，架构直观。
- **通用性**：兼容多种算法（PPO、A2C、MATD3）和环境（离散/连续、同质/异质），并支持循环网络。
- **可扩展性**：MLP超网络参数数量几乎不随智能体数量增长，适合大规模MARL。
- **理论支撑**：明确分析梯度解耦机制及其对梯度方差的影响，并与多任务RL/元RL中的分解建立类比。
- **实验全面**：覆盖22个场景、6种基线、多种任务类型，消融和敏感性分析充分。

#### 8. 不足与局限
- **参数开销**：MLP超网络在小规模智能体场景下参数较多（但随智能体数量几乎恒定），论文指出可通过分块超网络或低秩近似改进。
- **实验覆盖**：未测试完全异构（如不同动作空间）场景；未与更多近期方法（如GradPS、AdaPS）对比（因时间或实现原因）。
- **依赖超网络输出规模**：生成深层网络时输出维度大，可能影响计算效率，但RL中actor-critic网络通常较小。
- **初始化敏感性**：初始化缩放对复杂任务（Humanoid）至关重要，简单任务影响较小，需根据任务调整。
- **未讨论隐私或公平性等社会影响**（实际论文明确表示无特定社会影响需强调）。

（完）
