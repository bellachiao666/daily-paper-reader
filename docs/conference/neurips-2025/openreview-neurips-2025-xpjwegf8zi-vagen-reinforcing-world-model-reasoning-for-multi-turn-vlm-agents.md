---
title: "VAGEN: Reinforcing World Model Reasoning for Multi-Turn VLM Agents"
title_zh: VAGEN：强化多轮VLM智能体的世界模型推理
authors: "Kangrui Wang, Pingyue Zhang, Zihan Wang, Yaning Gao, Linjie Li, Qineng Wang, Hanyang Chen, Yiping Lu, Zhengyuan Yang, Lijuan Wang, Ranjay Krishna, Jiajun Wu, Li Fei-Fei, Yejin Choi, Manling Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=xpjWEgf8zi"
tags: ["query:agent-papers"]
score: 7.0
evidence: 多轮VLM智能体中通过强化学习强化世界模型推理
tldr: 本文针对VLM智能体部分可观测问题，提出VAGEN方法，利用强化学习强制智能体进行显式世界模型推理。将推理结构化为状态估计和转移建模，并在POMDP框架下训练。实验表明，结构化推理显著提升多轮视觉任务性能。该方法将RL与结构化推理结合，为VLM智能体训练提供了新范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1170, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1422, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1425, \"height\": 283, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1144, \"height\": 628, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1452, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 234, \"height\": 233, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 237, \"height\": 231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 246, \"height\": 231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 244, \"height\": 235, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 235, \"height\": 231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 238, \"height\": 233, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 235, \"height\": 234, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 244, \"height\": 237, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 234, \"height\": 228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 235, \"height\": 236, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 232, \"height\": 234, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 238, \"height\": 232, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 232, \"height\": 230, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 236, \"height\": 228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 235, \"height\": 230, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 232, \"height\": 236, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 235, \"height\": 231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 237, \"height\": 233, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 990, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1295, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1303, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1424, \"height\": 866, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1450, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1415, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1450, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1415, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1474, \"height\": 968, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1386, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1282, \"height\": 117, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1532, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1387, \"height\": 492, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1722, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1551, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1502, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1501, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1500, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1629, \"height\": 396, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1533, \"height\": 398, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1441, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1444, \"height\": 578, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1445, \"height\": 504, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1130, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 773, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1206, \"height\": 284, \"label\": \"Table\"}]"
motivation: VLM智能体面临视觉部分可观测性，需要强大的世界建模能力。
method: 提出POMDP框架，强制将推理分为状态估计和转移建模，并用RL优化。
result: 在多个视觉任务上优于基线，证明结构化推理的有效性。
conclusion: 显式世界模型推理结合RL可显著提升VLM智能体性能。
---

## Abstract
A major challenge in training VLM agents, compared to LLM agents, is that states shift from simple texts to complex visual observations, which introduces partial observability and demands robust world modeling. We ask: can VLM agents build internal world models through explicit visual state reasoning? In this work, we architecturally enforce and reward VLM agent’s reasoning process via reinforcement learning (RL), formulating the problem as a Partially Observable Markov Decision Process (POMDP). We demonstrate that structuring agent’s reasoning into StateEstimation (“what is the current state?”) and TransitionModeling (“what is next?”) is critical by studying five reasoning strategies. Investigating how agents should ground visual states and represent these internal beliefs, we reveal the optimal representations are task-dependent: Natural Language excels at capturing semantic relationships for general tasks, while Structured formats are essential for high-precision manipulation. These insights motivate our approach to reward shaping and credit assignment. We leverage a WorldModeling Reward to densely rewards the agent’s turn-by-turn state predictions, while our Bi-Level General Advantage Estimation (Bi-Level GAE) enables turn-aware credit assignment. Through such world model reasoning, we enable a 3B model to achieve performance of 0.82 on a set of five diverse agent tasks, nearly 3× improvement over its untrained counterpart (0.21) and surpassing proprietary reasoning models like GPT-5 (0.75), Gemini 2.5 Pro (0.67) and Claude 4.5 (0.62). All experiments are supported by our VAGEN framework, a scalable system for training and analyzing multi-turn VLM agents across diverse visual environments

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，现根据您提供的论文PDF提取文本，生成以下结构化、深入且客观的中文总结。

---

### 论文核心问题与整体含义

**研究动机与背景：**
传统LLM智能体处理的是简单文本状态，而VLM智能体面临的核心挑战在于其感知环境从文本转变为复杂的视觉观测。这种转变引入了**部分可观测性**，使得环境状态不再完全可知，从标准的马尔可夫决策过程（MDP）转变为更具挑战性的**部分可观测马尔可夫决策过程（POMDP）**。现有工作在处理多轮视觉智能体任务时，常常缺乏明确的内部世界建模来强化视觉状态推理，导致智能体难以准确解释和追踪动态变化的视觉环境。

**整体含义：**
本文旨在解决“如何有效教导VLM智能体通过显式视觉状态推理来构建内部世界模型”这一核心问题。作者提出VAGEN框架，通过强化学习（RL）强制和奖励智能体将思维过程结构化为**状态估计**和**转移建模**这两个世界模型的核心组件，从而显著提升了VLM智能体在多轮交互任务中的表现。

---

### 方法论

**核心思想：**
将多轮VLM智能体任务形式化为POMDP，并利用RL（特别是PPO）优化整个交互轨迹。核心创新在于强制智能体在生成动作之前，先生成结构化的推理过程（即状态估计和转移建模），以此构建和更新关于环境的内部信念。

**关键技术细节：**

1.  **问题形式化（POMDP）：**
    模型包含状态（S）、观测（O）、动作（A）、转移函数（P）、奖励函数（R）、观测函数（Ω）和折扣因子（γ）。在每轮`t`，智能体根据当前观测和轨迹历史生成动作`a_t`，环境发生状态转移并返回奖励。智能体学习一个由VLM参数化的策略`π_θ`以最大化累积折扣奖励。

2.  **核心推理结构：**
    智能体生成的输出`a_t`包含两部分：**推理令牌**`z_t`和**可执行动作**`a^e_t`。通过设计不同的`z_t`格式，定义了五种推理策略：
    *   **NoThink**: 无推理，只输出可执行动作。
    *   **FreeThink**: 无格式限制，输出任意自然语言推理。
    *   **StateEstimation**: 结构化输出，仅包含对当前状态`ˆs_t`的估计。
    *   **TransitionModeling**: 结构化输出，仅包含对下一状态`ˆs_{t+1}`的预测。
    *   **WorldModeling**: 结构化输出，同时包含当前状态估计`ˆs_t`和下一状态预测`ˆs_{t+1}`。这是全文采用的默认策略。

3.  **强化学习优化（VAGEN-Base）：**
    *   **轨迹收集**：智能体与环境交互多轮，收集完整轨迹。
    *   **策略优化**：使用PPO算法，通过GAE为每个行动令牌计算优势，并结合KL散度惩罚来优化策略。
    *   **奖励设计**：结合了**格式奖励**（鼓励结构化输出）和任务特定的环境奖励。

4.  **高级优化技术（VAGEN-Full）：**
    *   **世界模型奖励**：引入一个由LLM作为裁判的奖励，用于评估智能体在`StateEstimation`和`TransitionModeling`步骤中对状态描述和预测的准确性。这为中间推理步骤提供了密集的奖励信号。
    *   **双层泛化优势估计**：为了解决标准GAE在长序列学习中信用分配不稳定的问题，提出先计算每轮的优势（在回合级别），然后将此优势信号作为初始化值，反向传播到该轮内的每个令牌。这提供了更细粒度的、层次化的信用分配，使得密集的过程奖励能够更有效地指导优化。

**算法流程（文字描述）：**
1.  **初始化**：初始化VLM策略`π_θ`、价值函数`V_ϕ`和参考策略`π_ref`。
2.  **内层交互循环**：
    *   智能体接收当前图像观测。
    *   智能体生成包含结构化推理（ˆs_t, ˆs_{t+1}）和可执行动作的响应。
    *   环境执行动作、返回奖励和新观测。
    *   重复多轮，收集完整轨迹。
3.  **外层训练循环**：
    *   根据VAGEN-Full方法，计算每轮的总奖励（环境奖励 + 格式奖励 + 世界模型奖励）。
    *   使用**双层GAE**分别为每轮和每个令牌计算优势。
    *   使用PPO目标函数更新策略`π_θ`和价值函数`V_ϕ`。
    *   重复步骤2和3直至收敛。

---

### 实验设计

**使用的数据集/场景：**
作者构建了一个包含五种不同视觉环境的评估套件，覆盖多种挑战：
*   **经典网格谜题**：Sokoban, FrozenLake
*   **具身3D导航**：Navigation
*   **精细物体操作**：PrimitiveSkill
*   **抽象几何重建**：SVG Reconstruction

**基准（Benchmark）：**
*   **开源模型**：Qwen2.5-VL-3B/7B/72B, VLM-R1-3B。
*   **专有模型**：GPT-5, o3, o4-mini, GPT-4o, Gemini 2.5 Pro, Gemini 2.0, Claude 4.5 Sonnet, Claude 3.7 Sonnet。

**对比方法：**
1.  **推理策略对比**：在Qwen2.5-VL-3B上，对比了NoThink, FreeThink, StateEstimation, TransitionModeling, WorldModeling五种策略的效果。
2.  **RL基线对比**：对比了Vanilla PPO, GRPO w/ Mask, Turn-PPO w/ Mask等不同的多轮RL训练方法。
3.  **状态表示对比**：在子任务上，对比了自然语言、符号化、结构化三种不同状态内部表示形式的效果。
4.  **完整方法对比**：将VAGEN-Base（使用WorldModeling推理）与VAGEN-Full（增加世界模型奖励和双层GAE）进行对比。
5.  **消融实验**：单独验证世界模型奖励和双层GAE的独立贡献。

---

### 资源与算力

论文在Experimental Settings部分提到，实验是在配备**8×H100 GPU、104 CPU和1.7TB内存的服务器**上进行的。每台服务器可同时运行两个实验，每个训练会话约需**4-8小时**。附录D.3的表26提供了详细的训练效率和LLM裁判模型（GPT-4.1 nano）的Token成本，但未明确说明单次实验的具体GPU数量和总训练时长。

---

### 实验数量与充分性

**实验数量：**
论文进行了大量实验，主要包括：
*   **表1**：涵盖所有五种任务，对比多种推理策略、RL基线、开源和专有模型，结果丰富。
*   **表3**：在Sokoban、FrozenLake和PrimitiveSkill上对比了三种状态表示。
*   **图4 & 表1**：对比VAGEN-Base与VAGEN-Full的完整方法性能。
*   **图4**：包含对世界模型奖励和双层GAE的消融实验。
*   **附录**：还包含了对不同模型家族（如InternVL3）和尺寸（如7B）的补充实验。

**实验充分性与公平性：**
*   **充分**：实验覆盖了方法论的每一个关键部分（推理结构、表示、RL优化），并进行了多角度对比和消融，设计周密。
*   **客观**：实验结果清晰地展示了VAGEN及其变体在各种任务上的优势，尤其是在3B小模型上超越了大型专有模型，结论可信。性能曲线（图4）也反映了训练过程的稳定性和趋势。
*   **公平**：对比的基线方法（如不同推理策略、不同RL算法）均在相同的骨干网络（Qwen2.5-VL-3B）下进行，确保了比较的公平性。

---

### 主要结论与发现

1.  **显式推理至关重要**：将VLM智能体的推理结构化为显式的世界模型（尤其是结合**状态估计**和**转移建模**的`WorldModeling`策略）能够显著提升多轮视觉任务性能。`NoThink`策略效果最差，而`FreeThink`效果优于`NoThink`但不及结构化推理。
2.  **最优状态表示取决于任务**：自然语言表示在通用任务（如Sokoban, FrozenLake）中表现最佳，因其语义丰富且与模型预训练知识对齐。结构化格式（如坐标字典）在高精度操作任务（如PrimitiveSkill）中必不可少。符号化表示效果最差，说明模型难以直接理解抽象符号。
3.  **多轮RL的优势**：VAGEN的多轮RL框架远胜于单轮RL或标准的多轮RL基线（如Vanilla PPO, GRPO）。这证明了端到端优化交互历史的重要性。
4.  **世界模型奖励和双层GAE的有效性**：引入的`WorldModeling Reward`和`Bi-Level GAE`是VAGEN-Full成功的关键。前者提供了密集的过程监督，后者提供了更精细的信用分配。两者的结合带来了最稳定和最显著的性能提升。
5.  **小模型战胜大模型**：基于3B参数模型的VAGEN-Full在五项任务的整体平均得分（0.82）上，超过了所有参数量大得多的专有模型（如GPT-5, Gemini 2.5 Pro），证明了方法的巨大潜力。

---

### 优点

1.  **方法创新性强**：将认知科学中的“世界模型”概念与RL训练巧结合，提出`StateEstimation`和`TransitionModeling`的显式推理结构，并配以相应的奖励和GAE设计，思路新颖且系统完整。
2.  **系统全面性高**：不仅提出了一个完整方法（VAGEN-Full），还深入研究了推理策略、状态表示、RL基线等多个维度，实验设计非常全面，让读者对各个因素的作用有清晰的认识。
3.  **理论框架清晰**：将多轮视觉智能体问题形式化为POMDP，为处理部分可观测性提供了坚实的理论依据，避免了简单MDP假设的不合理性。
4.  **架构设计实用**：VAGEN框架采用`env-as-service`设计，将环境设置与模型训练解耦，便于扩展和高效实验，体现了工程上的优秀实践。
5.  **实验结果惊艳**：在3B参数模型上实现与并超越大型专有模型的性能，极具说服力，展示了RL微调的巨大潜力和本文方法的有效性。

---

### 不足与局限

1.  **模型架构依赖**：主要实验基于Qwen2.5-VL-3B模型家族，虽然在InternVL3上也进行了验证，但方法的普适性未在更多不同类型的VLM上进行大规模验证。
2.  **环境类型有限**：尽管涵盖了五种不同任务，但相对于现实世界中无限多样的视觉智能体场景（如网页操作、复杂的GUI交互、更复杂的具身AI），测试集仍相对有限。
3.  **奖励机制成本**：`WorldModeling Reward`依赖于LLM作为裁判（GPT-4.1 nano），这带来了额外的计算成本和潜在的不确定性（如裁判模型本身的偏见或稳定）。
4.  **“奖励黑客”风险**：作者在附录E.3中观察到了智能体通过生成通用模板来劫持奖励的现象（如在FrozenLake中）。这表明密集奖励的设计仍有优化空间，以防止智能体走捷径而非真正理解状态。
5.  **未报告统计显著性**：受限于计算资源，实验结果未提供误差棒或置信区间，使得结论的统计显著性不够明确。不同方法间的微小性能差异可能不稳定。

（完）
