---
title: "Boosting Virtual Agent Learning and Reasoning: A Step-Wise, Multi-Dimensional, and Generalist Reward Model with Benchmark"
title_zh: 提升虚拟智能体学习和推理：逐步多维通用奖励模型与基准
authors: "Bingchen Miao, Yang Wu, Minghe Gao, Qifan Yu, Wendong Bu, Wenqiao Zhang, Yunfei Li, Siliang Tang, Tat-Seng Chua, Juncheng Li"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=OKWlVPHeW1"
tags: ["query:agent-papers"]
score: 6.0
evidence: 为虚拟智能体训练提供逐步多维奖励模型，结合强化学习
tldr: 通用虚拟智能体训练依赖结果监督和人工标注，缺乏细粒度信号。本文提出Similar，一个逐步多维通用奖励模型，定义五个评估维度，并设计MCTS-P算法自动收集和标注数据。该模型可为智能体提供细粒度训练信号，并支持推理时缩放，助力智能体学习与推理能力提升。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 804, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1729, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 627, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 889, \"height\": 268, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1603, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 856, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 179, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 179, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 178, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 186, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-okwlvphew1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 577, \"height\": 343, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-okwlvphew1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 889, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-okwlvphew1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 884, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-okwlvphew1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 898, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-okwlvphew1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 886, \"height\": 759, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-okwlvphew1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 793, \"height\": 753, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-okwlvphew1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 840, \"height\": 377, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-okwlvphew1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1312, \"height\": 1517, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-okwlvphew1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1598, \"height\": 2176, \"label\": \"Table\"}]"
motivation: 通用虚拟智能体训练缺少细粒度奖励信号，过度依赖结果监督和人工标注。
method: 定义五个评估维度，设计MCTS-P算法自动收集逐步多维奖励数据，训练通用奖励模型。
result: 所提模型为虚拟智能体提供有效训练信号，支持推理时缩放。
conclusion: 逐步多维奖励模型可显著提升虚拟智能体的学习与推理能力。
---

## Abstract
The development of Generalist Virtual Agents (GVAs) has shown significant promise in autonomous task execution. However, current training paradigms face critical limitations, including reliance on outcome supervision and labor-intensive human annotations. To address these challenges, we propose **Similar**, a **s**tep-w**i**se **m**ult**i**-dimensiona**l** gener**a**list **r**eward model, which offers fine-grained signals for agent training and can choose better actions for inference-time scaling. Specifically, we begin by systematically defining five dimensions for evaluating agent actions. Building on this framework, we design an MCTS-P algorithm to automatically collect and annotate step-wise, five-dimensional agent execution data. Using this data, we train **Similar** with our crafted Triple-M strategy. Furthermore, we introduce the first benchmark in the virtual agent domain for step-wise, multi-dimensional reward model training and evaluation, named ***SRM***. This benchmark consists of two components: ***SRMTrain***, which serves as the training set for **Similar**, and ***SRMEval***, a manually selected test set for evaluating the reward model. Experimental results demonstrate that **Similar**, through its step-wise, multi-dimensional assessment and synergistic gain, provides GVAs with effective intermediate signals during both training and inference-time scaling. The code is available at [https://github.com/antgroup/Similar](https://github.com/antgroup/Similar).

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：当前通用虚拟智能体（Generalist Virtual Agent, GVA）的训练主要依赖**结果监督**（outcome supervision）和**人工标注的轨迹**。这种方式存在三大局限：①缺乏多维度细粒度的过程监督信号，无法定位中间步骤的失败原因；②人工标注成本极高，难以规模化；③推理时难以通过搜索进行扩展（inference-time scaling）。
- **整体含义**：为了解决上述问题，论文提出一种**逐步、多维的通用奖励模型（Similar）**，能够自动提供细粒度的过程反馈，既用于训练阶段的强化学习，也用于推理阶段的选择优化。同时，作者构建了首个面向虚拟智能体奖励模型的基准 **SRM**，以推动该方向的研究。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将虚拟智能体的每一步动作从多个维度进行量化评估，利用蒙特卡洛树搜索（MCTS）自动收集标注数据，并设计多阶段训练策略（Triple-M）使奖励模型能够输出综合评分。
- **关键技术细节**：
  - **五个评估维度**：
    - *Helpfulness（帮助度）*：该步骤对任务完成的贡献度（可正可负）。
    - *Odds of Success（成功几率）*：从该步骤出发完成任务的成功概率。
    - *Efficiency（效率）*：该步骤减少剩余步数的程度。
    - *Task Relevance（任务相关性）*（二进制，由MLLM评估）：步骤是否与任务指令相关。
    - *Coherence（连贯性）*（二进制，由MLLM评估）：步骤是否与上一步逻辑连贯。
  - **MCTS-P算法**：在MCTS的节点选择中，将五个维度的加权和作为节点价值，自动模拟N条轨迹，计算每个步骤的Helpfulness、Odds of Success和Efficiency，再调用MLLM（GPT-4o）评估Task Relevance和Coherence。最终筛选完整、正确的轨迹作为训练数据。
  - **Triple-M训练策略**：
    - 第一阶段：使用预训练的MLLM（如Llama-3.2-11B-Vision）作为骨干，提取隐藏状态，通过回归层输出五维分数，优化回归损失 \( \mathcal{L}_{RG} \)。
    - 第二阶段：固定骨干和回归层，引入提示感知的门控网络（浅层MLP），利用Bradley-Terry损失 \( \mathcal{L}_{BT} \) 动态调整五个维度的权重，输出综合奖励分数。
    - 最终奖励：\( R = g_{\phi}(f_{\theta}(x))^{\top} \mathbf{r} \)，其中 \( \mathbf{r} \) 是五维分数。

## 3. 实验设计：数据集、场景、基准与对比方法

- **数据集与场景**：
  - 使用四个环境平台：**WebArena**、**VisualWebArena**、**Android World**、**OSWorld**，覆盖Web、Android、Linux、Windows。
  - 构建 **SRM** 基准：包含 **SRMTrain**（78k自动标注的偏好对）和 **SRMEval**（32k人工精选的测试样本）。每个样本包含指令、观察截图、步骤索引、轨迹、评估类型和候选动作对。
  - 评估类型：五个单一维度 + 综合维度（Total）+ 轨迹级维度（Traj）。
- **对比方法**：
  - 基线：GPT-4-Turbo、GPT-4o、InternVL-2.5-8B、Qwen2-VL-7B、Llama-3.2-11B-Vision，直接提示打分。
  - 消融：Similar-RL（仅用强化学习训练，不含门控网络），Similar-TM（完整Triple-M策略）。
  - 在训练阶段：使用DPO训练两个开源智能体 **OS-Atlas** 和 **UGround**，对比不同奖励模型的效果。
  - 在推理阶段：将奖励模型与MCTS结合，评估智能体（GPT-4o、GPT-4-Turbo、OS-Atlas）的任务成功率。
- **评估指标**：Accuracy（在SRMEval上选择更好动作的准确率）；Task Success Rate（在具体环境任务上的完成率）。

## 4. 资源与算力

- **论文中未明确说明使用的GPU型号、数量、训练时长**。仅提及代码已开源，但未提供训练配置细节。
- 所使用的基线模型包括闭源API（GPT-4系列）和开源模型（Qwen2-VL、Llama-3.2-Vision等），其中Similar模型基于开源MLLM进行微调。

## 5. 实验数量与充分性

- **实验数量**：论文进行了多组实验：
  - SRMEval上的偏好对齐测试（表1），对比7种模型设置。
  - 训练阶段测试（表2），在两个智能体（OS-Atlas、UGround）和两个环境（Android World、WebArena）上对比。
  - 推理阶段测试（表3），在三个智能体（GPT-4-Turbo、GPT-4o、OS-Atlas）和两个环境（Android World、OSWorld）上对比。
  - 消融实验（表4），逐步添加不同维度组合，在Android World和WebArena上测试。
  - 推理时缩放研究（图6a），改变MCTS子节点数N。
  - 相关性分析（图6b），计算五个维度的皮尔逊相关系数。
- **充分性与公平性**：
  - 实验覆盖了多个环境、多个智能体、多个基线，对比层次丰富。
  - 消融实验系统地展示了每个维度及组合的贡献，验证了多维度的必要性。
  - 在数据收集时，使用了各基准中70%的数据用于训练，30%用于测试，避免数据泄露。
  - 但测试环境仍限于四个基准，未涉及更复杂或动态的界面；且未报告多次运行的方差，可能影响稳定性判断。

## 6. 论文的主要结论与发现

- **有效性**：使用自动标注的五维数据训练的Similar-RL模型在SRMEval上比基线Llama-3.2-11B-Vision提升13.2%，甚至超过GPT-4o。
- **协同增益**：Triple-M策略使Similar-TM在SRMEval上达到61.2的平均分，相比Similar-RL（53.9）提升13.5%，在所有维度上均有显著提高。
- **训练阶段**：使用Similar-TM作为奖励模型进行DPO训练，在WebArena上将OS-Atlas的成功率从20.2%提升至35.6%，提升幅度明显。
- **推理阶段**：Similar-TM与MCTS结合，在Android World上将GPT-4o的成功率从25.4%提升至34.6%，在OSWorld上从10.8%提升至16.5%。
- **维度重要性**：Helpfulness维度影响最大，Coherence影响最小，但五个维度整体协同才能达到最佳效果。
- **推理时缩放**：当MCTS子节点数N ≤ 8时性能提升，超过8后饱和或下降，体现了智能体自身的限制。

## 7. 优点

- **创新性**：首次提出针对虚拟智能体的逐步、多维、通用奖励模型，并构建了专门的基准SRM。
- **自动化程度高**：MCTS-P算法完全自动生成标注数据，大幅降低人工成本，且可跨平台扩展。
- **多维度设计**：五个维度覆盖步骤对任务的不同贡献，具有独立性和解释性，减少过拟合风险。
- **训练策略巧妙**：Triple-M策略分两阶段，先回归预测五维分数，再通过门控网络动态融合，实现协同增益，且可适应不同任务对维度的不同需求。
- **应用广泛**：模型同时适用于训练和推理阶段，提升了智能体学习效率和推理能力。

## 8. 不足与局限

- **自动标注偏差**：MCTS-P依赖模拟和GPT-4o评估，可能引入系统性偏差，特别在复杂或含糊任务场景下准确性有限。
- **环境覆盖有限**：仅测试了四个基准环境（Web、Android、Linux、Windows），未涵盖移动端App多样性、动态网页、实时交互等更广泛场景。
- **算力资源未公开**：论文未说明训练Similar所需的GPU型号、数量和时间，难以评估复现成本和可扩展性。
- **维度间相关性**：虽声称各维度独立，但相关性分析显示部分维度间相关系数达0.4-0.5，仍存在一定冗余，可能影响模型解释性。
- **实验可重复性**：未报告多次运行的标准差或置信区间，也未详细说明超参数设置，可能影响结论的稳健性。
- **长期推理限制**：推理时缩放实验显示当N>8时性能饱和，说明智能体模型本身存在瓶颈，奖励模型无法完全弥补。

（完）
