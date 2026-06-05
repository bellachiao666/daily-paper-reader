---
title: Partner Modelling Emerges in Recurrent Agents (But Only When It Matters)
title_zh: 递归智能体中的伙伴建模涌现（但仅在需要时）
authors: "Ruaridh Mon-Williams, Max Taylor-Davies, Elizabeth Mieczkowski, Natalia Vélez, Neil R Bramley, Yanwei Wang, Thomas L. Griffiths, Christopher G. Lucas"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=WydxWM2xNb"
tags: ["query:agent-papers"]
score: 6.0
evidence: 研究递归智能体在多智能体协作中的伙伴建模
tldr: 该论文探讨在开放协作环境中，简单的无模型递归智能体是否能自发产生伙伴建模能力。通过在Overcooked-AI环境中训练数千个协作团队并分析智能体的隐藏状态，发现伙伴建模的行为会涌现，但仅在需要时才出现。该研究揭示了协作建模的涌现机制，为构建灵活协作AI系统提供了启示，但未直接提出自改进方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-wydxwm2xnb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 732, \"height\": 667, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wydxwm2xnb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 1166, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wydxwm2xnb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 1308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wydxwm2xnb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1456, \"height\": 887, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wydxwm2xnb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1449, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wydxwm2xnb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1453, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wydxwm2xnb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1174, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wydxwm2xnb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1453, \"height\": 338, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-wydxwm2xnb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 569, \"height\": 771, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wydxwm2xnb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1174, \"height\": 262, \"label\": \"Table\"}]"
motivation: 人类能推断伙伴优缺点，AI是否也需要显式建模？本文研究简单模型是否可自发涌现。
method: 在Overcooked-AI中训练无模型RNN智能体与多样化伙伴协作，并分析内部状态。
result: 伙伴建模涌现，但仅在任务需要时才出现，说明协作压力可驱动建模能力。
conclusion: 简单模型可在协作压力下发展出表征，无需显式建模模块。
---

## Abstract
Humans are remarkably adept at collaboration, able to infer the strengths and weaknesses of new partners in order to work successfully towards shared goals. To build AI systems with this capability, we must first understand its building blocks: does such flexibility require explicit, dedicated mechanisms for modelling others—or can it emerge spontaneously from the pressures of open-ended cooperative interaction? To investigate this question, we train simple model-free RNN agents to collaborate with a population of diverse partners. Using the 'Overcooked-AI' environment, we collect data from thousands of collaborative teams, and analyse agents' internal hidden states. Despite a lack of additional architectural features, inductive biases, or auxiliary objectives, the agents nevertheless develop structured internal representations of their partners' task abilities, enabling rapid adaptation and generalisation to novel collaborators. We investigated these internal models through probing techniques, and large-scale behavioural analysis. Notably, we find that structured partner modelling emerges when agents can influence partner behaviour by controlling task allocation. Our results show that partner modelling can arise spontaneously in model-free agents—but only under environmental conditions that impose the right kind of social pressure.

---

## 论文详细总结（自动生成）

# 论文总结：《Partner Modelling Emerges in Recurrent Agents (But Only When It Matters)》

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：人类能通过推断伙伴的优缺点实现灵活协作，而这种能力是否需要在AI中引入显式、专门的建模模块，还是可以从无模型的协作压力中自发涌现？
- **核心问题**：简单的无模型递归神经网络（RNN）智能体，在仅以任务奖励作为监督信号、没有任何显式伙伴建模机制或辅助目标的情况下，能否自发发展出对伙伴能力的结构化内部表征，从而实现快速适应和泛化？
- **背景意义**：该研究探讨了“社交智能”的起源——是否仅靠通用学习机制与合适的环境压力即可产生，而不必依赖特殊架构；这对于构建能与人类灵活协作的AI系统具有重要启示。

## 2. 论文提出的方法论

- **核心思想**：将智能体（ego agent）训练在需与多样化伙伴合作的环境中，伙伴在两类子任务（如准备食材和盛汤）上具有不同的速度（冷却间隔）。智能体可通过一个额外动作控制伙伴当前应执行哪个子任务，从而在“任务分配”上施加影响，迫使其学习伙伴的能力差异。
- **关键技术细节**：
  - **网络架构**：基于GRU的循环策略网络，输入为局部观测（经CNN降维），隐藏状态作为动态记忆；策略使用PPO算法优化，仅使用共享任务奖励。
  - **伙伴生成**：伙伴的“能力”定义为每种子任务的动作冷却间隔（1–9步不等），训练与评估时使用不同的冷却值集合，保证测试伙伴在训练中未见过。
  - **在线适应实验**：训练时在中途随机切换伙伴（50%概率），测试时在固定时刻切换，测试智能体能否动态更新内部表征。
  - **盲智能体实验**：仅给智能体自身坐标、朝向和持有的物品等自我中心信号，无伙伴视觉信息，考察仅从任务奖励推断伙伴能力。
- **公式与算法流程**：训练目标为最大化期望累计折扣奖励 \( \mathbb{E}_{z^*\sim p(z^*)} \mathbb{E}_{\tau\sim\pi,\pi_2(z^*)} \left[ \sum_{t=0}^T \gamma^t r_t \right] \)，其中 \( z^* \) 是伙伴的潜在能力参数。算法流程为标准的PPO与环境互动，同时将隐藏状态用于行动选择。

## 3. 实验设计

- **环境与场景**：
  - 主要实验使用 **Overcooked-AI** 环境（5种厨房布局：cramped room, fivebyfive, coord ring, cramped room v3/v4），要求两个智能体协作制作汤，最大化汤产量。
  - 附录中补充了 **CoinGame** 环境（收集红蓝硬币），验证结论的通用性。
- **基准方法**：
  - **MLP**（无记忆的前馈网络）
  - **单伙伴RNN**（只与一个固定伙伴训练）
  - **无影响RNN**（多伙伴训练，但不能控制伙伴子任务分配）
  - 与完整设定的 **多伙伴RNN（有影响）** 对比。
- **评价指标**：
  - 平均每回合汤产量（reward）与吞吐率（throughput）。
  - 线性探针（linear probe）从RNN隐藏状态解码伙伴任务速度的准确率。
  - UMAP投影可视化隐藏状态的组织结构。
  - 任务分配正确性（伙伴擅长任务的时间占比）。
- **实验充分性**：所有实验包括多个随机种子（至少5个种子训练，20个种子评估），每个配置有大量rollout（如每伙伴20次），统计置信区间通过bootstrap计算。消融实验覆盖了记忆、训练多样性、影响力三个因素。

## 4. 资源与算力

- 原文附录 B.8 明确说明：
  - 所有实验在 **NVIDIA A100 GPU** 上运行。
  - 总计 **462 GPU-hours**，其中策略训练耗费 **225 GPU-hours**，评估（共约37,400次rollout）耗费 **207 GPU-hours**。
  - 具体训练时长未逐一列出，但提供了总资源消耗，足以复现。

## 5. 实验数量与充分性

- **实验数量**：
  - 三大核心实验（分配压力驱动建模、在线适应、盲智能体建模）均在Overcooked的5种布局上执行，每个布局下不同的伙伴配置（训练/测试集分离）。
  - 附录中在CoinGame环境重复了实验1，增加了结果稳健性。
  - 每个条件使用5个训练种子，选取最佳种子进行后续评估，评估时每伙伴20个随机种子rollout。
- **客观性与公平性**：所有比较均控制变量（仅有架构、训练多样性、影响力差异），且测试伙伴均未在训练中出现，避免过拟合。探针实验使用随机数据基线证明解码精度不是偶然。置信区间报告了95% bootstrap区间。
- **充分性评价**：实验设计较为系统，覆盖了关键假设（影响力、记忆、多样性），并补充了不同环境、盲智能体等极端情况，总体上足够支撑核心结论。

## 6. 论文的主要结论与发现

- **结论1**：在多伙伴训练且具有控制任务分配能力的条件下，RNN智能体自发形成了对伙伴任务能力的结构化内部表征，并能泛化到未见过的伙伴。
- **结论2**：线性探针显示，隐藏状态中包含的伙伴能力信息随交互进行而增加，且当智能体失去对伙伴行为的影响能力时，这种表征显著减弱，甚至低于只与单伙伴训练的智能体。
- **结论3**：智能体能在单个episode内在线适应伙伴的突然切换（如从擅长任务1切换到擅长任务2），吞吐率下降后再次回升，且隐藏状态投影随伙伴变化而移动。
- **结论4**：盲智能体仅凭自我中心信号和任务奖励也能发展出伙伴建模能力，并显著优于单伙伴RNN和MLP基线，证明交互结构本身足以驱动涌现。

## 7. 优点

- **方法简洁优雅**：不使用任何显式建模模块、辅助损失或架构先验，仅靠任务导向强化学习与合适的协作环境压力，即涌现出伙伴表征。
- **实验设计精巧**：通过控制“影响力”这一关键变量，清晰揭示了涌现的必要条件；在线适应和盲智能体实验进一步深化了结论。
- **分析工具丰富**：结合UMAP可视化、线性探针、行为相关性分析等多种手段，从多个尺度验证了内部表征的存在与结构。
- **可复现性好**：作者开源代码（GitHub），并详细列出了超参数和算力消耗。

## 8. 不足与局限

- **环境单一性**：主要实验仅在Overcooked-AI上进行，虽有CoinGame作为补充，但环境复杂度仍较低，任务仅涉及两项子任务，与现实多智能体协作场景存在差距。
- **影响力机制过于直接**：智能体通过“直接分配”伙伴的子任务来施加影响，而人类的影响方式（如语言指令、隐性协作信号）更为复杂和微妙。
- **伙伴数量有限**：训练和测试的伙伴能力分布来自离散集合，未探索连续或更大规模伙伴空间；伙伴数量增加时推理难度将上升，智能体可能退化为平均建模。
- **缺乏与显式建模方法的直接对比**：论文未与Rabinowitz等人提出的Machine Theory of Mind等显式建模方法进行性能、表征可解释性等方面的比较，无法确定涌现模型与专用模型的优劣势。
- **短期记忆分析**：主要依赖于最后一个时间窗口的隐藏状态平均值，未深入分析序列动态或注意机制在建模中的作用。

（完）
