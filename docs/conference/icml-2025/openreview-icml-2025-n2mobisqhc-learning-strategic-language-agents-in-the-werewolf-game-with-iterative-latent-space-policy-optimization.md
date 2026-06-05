---
title: Learning Strategic Language Agents in the Werewolf Game with Iterative Latent Space Policy Optimization
title_zh: 通过迭代潜在空间策略优化学习狼人游戏中的战略性语言智能体
authors: "Zelai Xu, Wanjun Gu, Chao Yu, Yi Wu, Yu Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=N2mOBiSqhc"
tags: ["query:agent-papers"]
score: 4.0
evidence: 通过迭代策略优化实现LLM智能体的自我改进
tldr: 该论文针对大型语言模型智能体在策略性语言游戏（如狼人杀）中探索不足和行动偏差的问题，提出迭代潜在空间策略优化（LSPO）。通过结合博弈论方法和LLM微调，LSPO在迭代过程中逐步优化智能体的策略分布，显著提升了在复杂语言博弈中的表现。该工作展示了迭代自我改进在构建战略型语言智能体中的有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-n2mobisqhc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1736, \"height\": 811, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-n2mobisqhc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1742, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-n2mobisqhc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1735, \"height\": 388, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-n2mobisqhc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 434, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-n2mobisqhc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1575, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-n2mobisqhc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 860, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-n2mobisqhc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 851, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-n2mobisqhc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 849, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-n2mobisqhc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1400, \"height\": 687, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-n2mobisqhc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1354, \"height\": 192, \"label\": \"Table\"}]"
motivation: LLM智能体在策略游戏中行动有偏且探索有限。
method: 结合博弈论和LLM微调，通过迭代潜在空间策略优化改进智能体。
result: 在狼人游戏等任务上超越现有LLM智能体基线。
conclusion: 迭代策略优化为构建战略语言智能体提供了有效范式。
---

## Abstract
Large language model (LLM) agents have recently demonstrated impressive capabilities in various domains like open-ended conversation and multi-step decision-making. However, it remains challenging for these agents to solve strategic language games, such as Werewolf, which demand both strategic decision-making and free-form language interactions. Existing LLM agents often suffer from intrinsic bias in their action distributions and limited exploration of the unbounded text action space, resulting in suboptimal performance. To address these challenges, we propose Latent Space Policy Optimization (LSPO), an iterative framework that combines game-theoretic methods with LLM fine-tuning to build strategic language agents. LSPO leverages the observation that while the language space is combinatorially large, the underlying strategy space is relatively compact. We first map free-form utterances into a finite latent strategy space, yielding an abstracted extensive-form game. Then we apply game-theoretic methods like Counterfactual Regret Minimization (CFR) to optimize the policy in the latent space. Finally, we fine-tune the LLM via Direct Preference Optimization (DPO) to align with the learned policy. By iteratively alternating between these steps, our LSPO agents progressively enhance both strategic reasoning and language communication. Experiment on the Werewolf game shows that our agents iteratively expand the strategy space with improving performance and outperform existing Werewolf agents, underscoring their effectiveness in free-form language games with strategic interactions.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：大型语言模型（LLM）智能体在开放对话和多步决策中表现优异，但在需要战略决策和自由形式语言交互的策略性语言游戏（如狼人杀）中仍面临挑战。具体挑战包括：LLM生成的动作存在固有偏差（intrinsic bias），且对无限文本动作空间的探索不足，导致次优性能。
- **整体含义**：本文旨在构建能够进行战略推理和自然语言沟通的智能体，以狼人杀为测试平台，提出一种结合博弈论方法和LLM微调的迭代框架，逐步提升智能体的战略水平。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：虽然语言空间组合巨大，但底层策略空间相对紧凑。因此，将自由形式话语映射到有限的潜在策略空间，在抽象博弈上应用博弈论方法求解最优策略，再通过偏好优化对齐LLM，并迭代扩展策略空间，从而同时缓解偏差和探索不足问题。
- **关键技术细节**：框架包含三个组成部分，迭代进行：
  1. **潜在空间构建**：通过LLM自对弈生成大量讨论动作，利用嵌入模型（如text-embedding-3-small）将话语向量化，并执行k-means聚类得到离散的潜在策略空间。
  2. **潜在空间策略优化**：将原始游戏抽象为有限动作的扩展式博弈，应用反事实遗憾最小化（CFR）或其深度版本（Deep CFR）学习各角色的最优策略。
  3. **潜在空间扩展**：利用CFR学习到的策略生成偏好数据，通过直接偏好优化（DPO）微调LLM，使其输出与最优策略对齐；然后使用微调后的LLM重新生成和扩展潜在策略空间（增加聚类数量）。
- **算法流程**：迭代交替执行上述三步，每次迭代潜在空间扩大，策略逐渐逼近原游戏的纳什均衡。

## 3. 实验设计：数据集/场景、基准、对比方法

- **场景**：以七人狼人杀游戏作为测试环境（2狼、1预言家、1女巫、3村民），纯文本交互。
- **基准/评估指标**：预测准确率（角色识别）和胜率。
- **对比方法**：
  - ReAct（推理与行动协同）
  - ReCon（递归沉思，原用于阿瓦隆游戏）
  - Cicero-like（为外交游戏设计的策略与对话模块，此处预定义13个原子动作）
  - SLA（战略语言智能体，结合RL与LLM）
- **实验设置**：
  - 使用Llama-3-8B-Instruct作为基础模型。
  - 在1000场自对弈游戏中收集数据。
  - 评估不同迭代次数（Iter.1~3）的LSPO智能体性能，并与基线方法对比。
  - 进行消融实验：移除微调组件（w/o Fine-Tuning）、移除策略学习组件（w/o Policy Learning）。
  - 敏感性分析：不同初始聚类数k=1,2,3；不同DPO超参数β=0.05,0.1,0.2（在简化四人游戏上）。

## 4. 资源与算力

- **文中未明确说明**使用的GPU型号、数量和训练时长。仅提及在Llama-3-8B-Instruct上微调，使用OpenAI的嵌入服务，Deep CFR训练迭代1500次，DPO训练2个epoch等细节，但未报告具体硬件配置和耗时。

## 5. 实验数量与充分性

- **实验数量**：
  - 迭代性能评估：在3次迭代中，分别报告狼方和村民方的预测准确率和胜率（各100场游戏）。
  - 与四个基线方法对比：两种角色互换设置，各100场游戏。
  - 消融实验：在Iter.1下比较完整LSPO与变体（w/o Fine-Tuning, w/o Policy Learning），各报告胜率。
  - 额外敏感性分析：在四人游戏上测试不同聚类数k和DPO β值（各3次迭代）。
  - 额外收敛性实验：进行5次迭代，结果显示性能趋于稳定。
- **充分性**：实验设计较为全面，覆盖了主要对比、消融和敏感性分析。但缺少与人类玩家的对比、跨游戏泛化实验，且所有实验基于7人狼人杀，未在其他语言游戏上验证。

## 6. 论文的主要结论与发现

- LSPO智能体在迭代过程中逐步扩展策略空间，学习到越来越复杂的战略行为（如狼人伪装预言家、村民协调投票）。
- 预测准确率和胜率随迭代次数稳步提升，表明迭代框架的有效性。
- 在狼方和村民方胜率上均超过所有基线方法，证明LSPO优于纯提示方法（ReAct、ReCon）和固定动作集方法（Cicero-like、SLA）。
- 消融实验表明策略学习组件和微调组件均不可或缺。
- 在简单概念验证游戏（石头剪刀布蜥蜴史波克）中，LSPO经过3次迭代成功学到纳什均衡，而基线方法因固有偏差或探索不足而失败。

## 7. 优点

- **方法创新**：将博弈论求解（CFR）与LLM微调（DPO）有机结合，通过潜在空间抽象解决了无限动作空间的策略优化难题。
- **迭代自我改进机制**：通过“抽象→求解→对齐→扩张”的闭环，智能体可以自主探索新策略并克服LLM的固有偏差。
- **实验充分**：在狼人杀这一复杂语言游戏中进行了多角度评估，包括预测准确率、胜率、消融和敏感性分析，且与多个强基线对比。
- **可视化分析**：通过t-SNE可视化展示了潜在策略空间随迭代的演变，直观验证了策略多样性的提升。

## 8. 不足与局限

- **实验覆盖**：仅在一个游戏（狼人杀）上验证，未在其他自由形式语言游戏（如阿瓦隆、外交）测试，泛化性存疑。
- **算力资源不透明**：未报告训练所需的GPU型号、数量和时长，难以评估可复现性。
- **有限场景**：仅测试了7人局，未探索不同玩家数量或角色配置下的性能。
- **与人类对比缺失**：未进行与人类玩家的对抗评估，现实交互效果未知。
- **依赖外部嵌入模型**：使用OpenAI的嵌入服务，存在API依赖和成本问题，且聚类数量需人为设定。
- **收敛保证**：理论上次数有限，但实际可能需要多次迭代才能覆盖足够策略，收敛速度可能受限于LLM探索能力。

（完）
