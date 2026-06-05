---
title: Progress Reward Model for Reinforcement Learning via Large Language Models
title_zh: 通过大语言模型实现强化学习的进度奖励模型
authors: "Xiuhui Zhang, Ning Gao, Xingyu Jiang, Yihui Chen, Yuheng Pan, Mohan Zhang, Yue Deng"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=TJhHb6CscW"
tags: ["query:agent-papers"]
score: 7.0
evidence: 基于LLM的奖励模型用于RL，符合代理RL和自改进方向
tldr: 传统强化学习在处理长期任务时面临稀疏奖励的挑战，现有方法依赖预定义技能库或大量人工反馈。本文提出进度奖励模型PRM4RL，利用大语言模型进行高层任务规划，将复杂任务分解为一系列简单子任务，并为每个子任务生成密集的进度奖励。实验表明，PRM4RL在多个连续控制任务上显著提升了学习效率和最终性能，证明了将LLM的世界知识与RL结合的有效性，为构建自适应智能体提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 953, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 886, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1436, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1404, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 372, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1422, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1456, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1449, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1345, \"height\": 880, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-tjhhb6cscw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1455, \"height\": 516, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tjhhb6cscw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 613, \"height\": 578, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tjhhb6cscw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 574, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tjhhb6cscw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1279, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tjhhb6cscw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1293, \"height\": 300, \"label\": \"Table\"}]"
motivation: 传统RL在处理长期稀疏奖励任务时存在局限，现有LLM增强方法依赖预定义技能库或人工反馈。
method: 提出PRM4RL框架，使用LLM将复杂任务分解为子任务并生成密集进度奖励，结合任务规划与RL。
result: 在连续控制任务上，PRM4RL相比基线方法显著提升学习效率和任务成功率。
conclusion: 证明了LLM可用于生成进度奖励以增强RL，为设计自适应智能体提供了有效方法。
---

## Abstract
Traditional reinforcement learning (RL) algorithms face significant limitations in handling long-term tasks with sparse rewards. 
Recent advancements have leveraged large language models (LLMs) to enhance RL by utilizing their world knowledge for task planning and reward generation. 
However, planning-based approaches often depend on pre-defined skill libraries and fail to optimize low-level control policies, while reward-based methods require extensive human feedback or exhaustive searching due to the complexity of tasks.
In this paper, we propose the Progress Reward Model for RL (PRM4RL), a novel framework that integrates task planning and dense reward to enhance RL. 
For high-level planning, a complex task is decomposed into a series of simple manageable subtasks, with a subtask-oriented, fine-grained progress function designed to monitor task execution progress. 
For low-level reward generation, inspired by potential-based reward shaping, we use the progress function to construct a Progress Reward Model (PRM), providing theoretically grounded optimality and convergence guarantees, thereby enabling effective policy optimization.
Experimental results on robotics control tasks demonstrate that our approach outperforms both LLM-based planning and reward methods, achieving state-of-the-art performance.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究动机**：传统强化学习在处理长期任务时面临**稀疏奖励**的严重挑战，导致智能体难以获得有效反馈。现有的LLM增强方法分为两类：**LLM作为规划器**（依赖预定义技能库，无法优化底层控制策略）和**LLM作为奖励器**（需要大量人工反馈或穷举搜索），两者均未能充分利用高层规划与低层奖励的协同作用。
- **整体含义**：本文提出PRM4RL框架，通过**LLM将复杂任务分解为子任务**，并基于子任务进度构建**具有理论收敛保证的密集奖励函数**，从而显著提升RL在长期稀疏奖励任务上的学习效率与最终性能。

### 2. 方法论

- **核心思想**：结合高层任务规划与低层密集奖励生成，利用LLM的世界知识实现端到端优化。
- **关键技术细节**：
  - **子任务分解**：使用LLM（GPT-4o）以Pythonic提示将任务分解为“动词+名词”形式的子任务列表（如`['move to object', 'grasp object', ...]`），并生成**子任务判定函数Ψ(s)**，根据当前状态实时返回正在执行的子任务索引。
  - **进度函数Φ(s)**：为每个子任务设计归一化的进度指标（如距离归一化），融合成全局进度。
  - **基于势能的进度奖励模型（PRM）**：借鉴势能奖励塑形，将Φ(s)作为势能函数，构造奖励：  
    \( R_t^{\text{PRM}} = \gamma \cdot \Phi(s_{t+1}) - \Phi(s_t) + I(s_{t+1}) \cdot r_{\text{bonus}} \)  
    其中\( I \)为成功指示函数，\( r_{\text{bonus}} \)为稀疏成功奖励。
  - **理论保证**：证明策略不变性（Theorem 4.1）和收敛效率（Theorem 4.3），说明PRM不改变最优策略且加速收敛等价于Q值初始化。
- **算法流程**（Algorithm 1）：  
  ① 将环境信息、任务描述以Pythonic提示输入LLM，输出`plan_list`、判定函数Ψ(s)、进度函数Φ(s)；  
  ② 使用SimCSE对当前子任务文本编码，扩充状态空间为`S + P`；  
  ③ 用PRM奖励替换原始奖励，得到增强MDP `M'`；  
  ④ 使用SAC或PPO等RL算法优化策略。

### 3. 实验设计

- **环境**：MetaWorld（9个任务，如button-press、pick-place等）+ ManiSkill（5个任务，如LiftCube、PickCube等），均为机器人连续控制长期稀疏奖励任务。
- **基准**：对比了**ELLM**（LLM规划器）、**Text2Reward (T2R)**（LLM奖励器）、**Oracle**（专家密集奖励）。
- **对比方法**：还包括消融变体（去掉PRM、去掉子任务先验、去掉势能塑形）。
- **评估指标**：成功率（Success Rate），所有实验5个随机种子。

### 4. 资源与算力

- **明确说明**：使用4块NVIDIA GeForce RTX-3090 GPU、128核CPU、256 GiB内存服务器。每个任务训练约1小时（MetaWorld）或1-10小时（ManiSkill，视难度而定），5个种子同时运行。

### 5. 实验数量与充分性

- **实验数量**：
  - 主实验：在MetaWorld和ManiSkill共14个任务上对比3种基线+ Oracle。
  - 消融实验：在多个MetaWorld任务上评估3个变体（w.o. prm, w.o. prior, w.o. potential reward）。
  - 泛化实验：在2组原始任务上测试到4个未见过任务的迁移能力。
  - 额外对比：验证势能效应（图6）。
- **充分性与公平性**：所有实验使用相同的RL算法（SAC/PPO）和超参数，基线按照原论文重新实现或使用其公开代码。5个随机种子取平均和标准差，结果具有统计意义。实验覆盖了不同复杂度任务，消融设计合理，结论客观。

### 6. 主要结论与发现

- PRM4RL在几乎所有任务上显著优于LLM规划器和奖励器方法，尤其在复杂多阶段任务（如pick-out-of-hole、LiftPegUpright）上成功率从<15%提升至近100%。
- 子任务先验和基于势能的PRM奖励**协同作用**，缺一不可：去掉先验降低收敛速度，去掉PRM奖励导致性能大幅下降（甚至不如Oracle）。
- 直接使用进度函数作为奖励（无势能塑形）会导致策略学习异常（奖励上升但成功率下降），验证了势能塑形的必要性。
- 泛化实验表明，子任务先验（“动词+名词”格式）显著增强了策略对新任务的泛化能力。

### 7. 优点

- **方法论亮点**：巧妙地结合LLM的高层规划能力和潜在势能奖励塑形的理论保证，实现了端到端学习，无需预定义技能库或人工反馈。
- **理论贡献**：明确证明了PRM奖励的最优性保持和收敛加速性质，提供了坚实的数学基础。
- **实用性**：只需单次LLM调用即可生成完整的子任务分解和进度函数，后续RL训练中不再需要LLM，效率高。
- **泛化性**：通过结构化的子任务先验，训练的policy能较好迁移到新任务。
- **消融充分**：通过多个消融变体和对比实验，清晰揭示了各组件的贡献。

### 8. 不足与局限

- **依赖LLM推理质量**：LLM可能产生幻觉，导致任务分解或进度函数设计错误（作者在限制中已指出）。
- **应用范围**：仅在机器人连续控制任务上验证，未探索其他领域（如游戏、推荐系统、自然语言交互）。
- **实验覆盖**：虽包含14个任务，但均为模拟环境，真实机器人部署的鲁棒性未知。
- **效率**：LLM调用虽然在训练前完成，但GPT-4o API成本较高，且提示设计需专家知识（环境抽象），对非专家用户不友好。
- **未讨论**：对状态空间大小和子任务数量的可扩展性分析不足。

（完）
