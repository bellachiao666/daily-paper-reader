---
title: Cross-environment Cooperation Enables Zero-shot Multi-agent Coordination
title_zh: 跨环境协作实现零样本多智能体协调
authors: "Kunal Jha, Wilka Carvalho, Yancheng Liang, Simon Shaolei Du, Max Kleiman-Weiner, Natasha Jaques"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=zBBYsVGKuB"
tags: ["query:agent-papers"]
score: 7.0
evidence: 跨环境零样本多智能体协调
tldr: 现有零样本协调研究局限于单一任务。本文提出跨环境协作（CEC）范式，通过在环境分布上进行强化学习训练，使智能体学会通用协作技能。实验表明，CEC在新任务和新伙伴上实现了优异的零样本协调能力。该工作提升了多智能体系统的泛化性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 813, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 528, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 860, \"height\": 180, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 854, \"height\": 179, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 726, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 842, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 863, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 776, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 849, \"height\": 228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1505, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 888, \"height\": 1209, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 863, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1782, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 854, \"height\": 564, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 850, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 847, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 848, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 816, \"height\": 845, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1772, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 814, \"height\": 844, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 474, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 473, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1765, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 449, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1724, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1730, \"height\": 999, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 851, \"height\": 323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 853, \"height\": 323, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zbbysvgkub/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1709, \"height\": 1404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zbbysvgkub/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1578, \"height\": 778, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zbbysvgkub/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1246, \"height\": 911, \"label\": \"Table\"}]"
motivation: 现有零样本协调方法无法泛化到新任务。
method: 提出跨环境协作（CEC），在环境分布上训练单一伙伴的RL。
result: 在新任务和新伙伴上实现了优于基线的零样本协调。
conclusion: 环境分布训练可学习通用协作技能。
---

## Abstract
Zero-shot coordination (ZSC), the ability to adapt to a new partner in a cooperative task, is a critical component of human-compatible AI. While prior work has focused on training agents to cooperate on a single task, these specialized models do not generalize to new tasks, even if they are highly similar. Here, we study how reinforcement learning on a **distribution of environments with a single partner** enables learning general cooperative skills that support ZSC with **many new partners on many new problems**. We introduce *two* Jax-based, procedural generators that create billions of solvable coordination challenges. We develop a new paradigm called **Cross-Environment Cooperation (CEC)**, and show that it outperforms competitive baselines quantitatively and qualitatively when collaborating with real people. Our findings suggest that learning to collaborate across many unique scenarios encourages agents to develop general norms, which prove effective for collaboration with different partners. Together, our results suggest a new route toward designing generalist cooperative agents capable of interacting with humans without requiring human data.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：如何训练AI智能体具备**零样本协调（Zero-shot Coordination, ZSC）** 能力，即能够与从未见过的伙伴在从未见过的任务上进行有效合作。
- **背景**：现有零样本协调研究主要聚焦于**单一任务**，通过伙伴多样性（如种群训练PBT）提升对新伙伴的适应性。但这些方法无法泛化到新环境，即便是非常相似的任务也需要重新训练。
- **本文动机**：探究**环境多样性**是否比伙伴多样性更能促进通用协作技能的学习，从而同时实现对新伙伴和新任务的泛化。

## 2. 论文提出的方法论

### 核心思想
- **Cross-Environment Cooperation (CEC)**：使用**自我对弈（Self-Play）** 训练一个单一的智能体策略，但训练环境来自一个**大规模程序化生成的环境分布**，而非单一固定任务。
- 环境多样性迫使智能体学习更高层次的协作规范（如关注相关物体、避免碰撞），而非低层次的固定动作序列。

### 关键技术细节
- **目标函数**：
  \[
  J(\pi_C) = \mathbb{E}_{m_i \sim \mathcal{M}} [S(\pi_C, \pi_C, m_i)]
  \]
  其中 \(\pi_C\) 是合作者策略，\(\mathcal{M}\) 是任务分布，\(S\) 是联合奖励。
- **算法**：使用**IPPO**（独立PPO）作为基础强化学习算法，无需要额外辅助损失或伙伴种群。
- **环境生成**：
  - **Dual Destination 玩具环境**：随机化智能体起始位置和目标方格位置。
  - **Overcooked 程序化生成**：基于5个原始布局（图4），随机采样墙结构、物体位置（盘子堆、洋葱堆、锅、目标），并旋转布局，确保可解性，生成多达 \(1.16 \times 10^{17}\) 种布局。
- **网络架构**：使用**LSTM**循环网络实现基本的元学习（meta-learning），以在动态环境中适应伙伴行为。无LSTM的CEC无法收敛。
- **实现**：全部基于**Jax**编写，可在单GPU上实现每分钟1000万步的训练速度。

## 3. 实验设计

### 数据集/场景
- **Dual Destination 游戏**：简单网格世界，两个智能体需移动到不同的目标方格。
- **Overcooked**：两人合作烹饪游戏，用于人类-AI协调基准测试。
  - 5个**原始手工布局**（图4）：Asymmetric Advantages, Coordination Ring, Counter Circuit, Cramped Room, Forced Coordination。
  - 100个**程序化生成的保留布局**（CEC训练时未见过）。

### 基准方法
- **IPPO**（自我对弈基线）
- **FCP**（Fictitious Co-Play，种群训练基线，学习对多样伙伴的最佳响应）
- **E3T**（Efficient End-to-End Training，当前单任务ZSC SOTA方法，通过为伙伴策略添加随机性和辅助预测网络提升适应能力）
- **CEC**（本文方法，仅环境多样性）
- **CEC-FT**（CEC微调：CEC预训练后在单个布局上额外训练1亿步）
- **CEC-E3T**（结合环境与伙伴多样性的消融变体）

### 评估设置
- **AI-AI 零样本协调（ZSC）**：评估交叉播放（Cross-Play, XP）表现，即不同种子训练的智能体相互协作。
- **交叉算法评估（Ad-hoc Teamplay）**：不同算法训练的智能体相互协作，形成经验博弈论分析。
- **人类-AI 实验**：招募80名参与者，在Counter Circuit和Coordination Ring两个布局上进行协作，同时收集主观评分（7个指标）。
- **消融实验**：部分可观测环境、多任务版本、结合环境与伙伴多样性、无循环网络。

## 4. 资源与算力

- **训练规模**：所有模型（CEC、IPPO、FCP、E3T等）均训练**30亿步（3 billion steps）**，以公平比较。
- **硬件**：使用**Jax**实现，在**单GPU**上可达到每分钟1000万步的训练速度。文中未明确说明GPU型号和数量，但强调单GPU高效性。
- **人类实验**：通过 **NiceWebRL** 框架，利用Jax并行性在网页端高效进行多人实验。
- *注：论文未提供具体GPU型号、节点数等详细信息。*

## 5. 实验数量与充分性

- **实验数量**：涵盖玩具环境、Overcooked五种布局、100个程序化布局、AI-AI交叉播放、交叉算法博弈论分析、人类研究（80人，每人约30分钟）、多种消融实验（部分可观测、多任务、伙伴+环境多样性、无LSTM）。
- **充分性**：实验设计全面，从简单到复杂场景，从模拟到真人评估，并进行了统计显著性检验（t检验）。在AI-AI实验中，CEC在保留布局上评估，而基线在训练布局上评估，但CEC仍优于基线，保证了公平性。人类实验中包含了主观偏好指标，弥补了仅使用奖励的不足。
- **客观性**：遵循标准协议（如Overcooked公开布局），并报告均值和标准误，同时引入经验博弈论分析验证鲁棒性。

## 6. 论文的主要结论与发现

1. **环境多样性优于伙伴多样性**：在交叉播放性能上，CEC显著优于基于伙伴多样性的FCP和E3T。
2. **CEC实现零样本协调**：即使训练时仅使用单伙伴自我对弈，CEC也能与从未见过的新伙伴（包括人类）和从未见过的新环境进行有效协作。
3. **CEC-FT可进一步提升单任务性能**：微调后的CEC在原始布局上超越FCP和IPPO，但牺牲了对新布局的泛化能力。
4. **人类主观偏好**：CEC和CEC-FT在人类评价中（适应性、一致性、低挫败感、享受度等）显著优于所有基线，尽管奖励略低于E3T。
5. **学习通用协作规范**：CEC智能体学会避免碰撞、关注任务相关物体，访问状态分布更均匀，从而更好地适应人类行为。
6. **结合环境与伙伴多样性未直接受益**：CEC-E3T在原始布局上性能下降，说明如何有效结合二者仍需进一步研究。

## 7. 优点

- **方法简洁高效**：CEC仅通过环境多样性（自我对弈）就达到了超越复杂种群训练方法的性能，无需维护伙伴种群，降低训练复杂度。
- **强大的泛化能力**：从玩具环境到复杂Overcooked，CEC均展示出对新任务和新伙伴的零样本泛化，突破了以往方法的环境限制。
- **高质量工程实现**：基于Jax的高效程序化生成器（10M步/分钟）使大规模训练成为可能；NiceWebRL框架简化了人类实验部署。
- **全面的评估体系**：不仅关注奖励，还考虑人类主观体验（适应性、挫败感等），并引入经验博弈论分析，揭示了CEC作为均衡策略的稳定性。
- **可解释性分析**：通过对访问频率热图的分析，直观展示了CEC学习到更通用的环境表示，而非固定路线。

## 8. 不足与局限

- **训练尚未收敛**：论文指出CEC在30亿步后交叉播放性能仍在提升（图7），更长时间训练可能达到更高上限，但受限于成本未进行。
- **人类样本偏差**：人类实验仅包含英语流利参与者，可能导致文化偏差（WEIRD人群问题），影响泛化性。
- **环境多样性设计局限**：程序化生成基于预设的5种布局结构，并未完全探索开放式空间；且生成算法可能仍存在某些不可解难题。
- **与SOTA方法奖励差距**：在人类实验中CEC奖励低于E3T，说明环境多样性在最大化奖励方面可能不如针对特定任务的精细调优。
- **结合环境与伙伴多样性的初步尝试失败**：CEC-E3T效果不佳，表明两种多样性如何协同仍需更多研究。
- **应用场景有限**：仅在网格世界和Overcooked上验证，未在更复杂、更现实的多智能体场景（如自动驾驶、机器人团队）中测试。
- **依赖循环网络**：无LSTM的CEC无法收敛，表明时间记忆对于跨环境适应可能是必要的，但这也增加了模型复杂性和训练难度。

（完）
