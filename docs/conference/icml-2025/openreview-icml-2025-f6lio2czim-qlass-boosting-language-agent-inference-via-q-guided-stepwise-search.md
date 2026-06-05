---
title: "QLASS: Boosting Language Agent Inference via Q-Guided Stepwise Search"
title_zh: QLASS：通过Q引导逐步搜索提升语言智能体推理
authors: "Zongyu Lin, Yao Tang, Xingcheng Yao, Da Yin, Ziniu Hu, Yizhou Sun, Kai-Wei Chang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=f6lio2CZIM"
tags: ["query:agent-papers"]
score: 7.0
evidence: Q引导的语言智能体强化学习搜索
tldr: 语言智能体依赖轨迹奖励，但中间步骤缺乏标注。本文提出QLASS，通过逐步估计Q值并引入推理树进行过程奖励建模，自动生成中间标注以优化智能体推理。在交互任务上，QLASS相比只用最终奖励的方法显著提升了策略质量。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-f6lio2czim/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 835, \"height\": 486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6lio2czim/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1298, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6lio2czim/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 744, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6lio2czim/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 745, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6lio2czim/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1237, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6lio2czim/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 852, \"height\": 1020, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6lio2czim/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 881, \"height\": 748, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-f6lio2czim/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1784, \"height\": 1025, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6lio2czim/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 818, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6lio2czim/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1250, \"height\": 638, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6lio2czim/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 615, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6lio2czim/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 620, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6lio2czim/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1784, \"height\": 911, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6lio2czim/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1771, \"height\": 765, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6lio2czim/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 881, \"height\": 770, \"label\": \"Table\"}]"
motivation: 缺乏中间交互标注导致次优策略。
method: 逐步估计Q值并构建推理树进行过程奖励建模。
result: 在复杂交互任务上优于仅用最终奖励的方法。
conclusion: 过程奖励能有效提升语言智能体的决策质量。
---

## Abstract
Language agents have become a promising solution to complex interactive tasks. One of the key ingredients to the success of language agents is the reward model on the trajectory of the agentic workflow, which provides valuable guidance during training or inference. However, due to the lack of annotations of intermediate interactions, most existing works use an outcome reward model to optimize policies across entire trajectories. This may lead to sub-optimal policies and hinder the overall performance. To address this, we propose QLASS (Q-guided Language Agent Stepwise Search), to automatically generate annotations by estimating Q-values in a stepwise manner for open language agents. By introducing a reasoning tree and performing process reward modeling, QLASS provides effective intermediate guidance for each step. With the stepwise guidance, we propose a Q-guided generation strategy to enable language agents to better adapt to long-term value, resulting in significant performance improvement during model inference on complex interactive agent tasks. Notably, even with almost half the annotated data, QLASS retains strong performance, demonstrating its efficiency in handling limited supervision. We also empirically demonstrate that QLASS can lead to more effective decision making through qualitative analysis.

---

## 论文详细总结（自动生成）

# 论文总结：QLASS：通过Q引导逐步搜索提升语言智能体推理

## 一、核心问题与整体含义

语言智能体在复杂交互任务（如网页导航、科学推理、具身环境规划）中表现出色，但其成功关键在于对智能体工作流轨迹进行奖励建模，从而在训练或推理时提供指导。然而，现有方法大多仅使用最终结果奖励（outcome reward）来优化整个轨迹的策略，缺乏对中间交互步骤的标注。这会导致次优策略，因为即使最终任务成功，中间步骤可能包含低效或冗余动作。**QLASS旨在自动生成过程级别的奖励信号**，通过逐步估计Q值（Q-value）来提供中间指导，从而提升语言智能体在推理时的决策质量，并降低对人类标注的依赖。

## 二、提出的方法论

### 核心思想
QLASS引入**过程奖励模型**，通过构建**探索树（exploration tree）** 并利用贝尔曼方程估计每个状态-动作对的Q值，以此作为中间监督信号。随后训练一个**Q网络（QNet）** 来预测任意部分解的期望回报，并在推理时使用Q引导生成策略——每一步采样多个候选动作，执行Q值最高的动作。

### 关键技术细节
1. **行为克隆（Behavioral Cloning）**：首先在专家轨迹上对语言智能体进行监督微调（SFT），使其具备基本能力。
2. **探索树构建**：
   - 每个任务对应一棵树，根节点为任务描述，节点包含状态、动作、即时奖励、子节点和Q值。
   - 通过从现有节点扩展新分支（限制宽度和深度）来收集多样化轨迹，并对结果为0的叶节点进行剪枝（发送停止扩展信号）。
3. **Q值提取**：利用贝尔曼最优方程递归更新节点Q值：
   \[
   Q(s_t, a_t) = r_t + \gamma \max_{a_{t+1} \in C_t} Q(s_{t+1}, a_{t+1})
   \]
   其中 \(C_t\) 为子节点集合，\(\gamma\) 为折扣因子。之后进行min-max归一化。
4. **QNet训练**：将Q值作为监督信号，以MSE损失训练一个基于LLM的Q网络（LLM主干+值头MLP），使其能对任意状态-动作对预测长期价值。
5. **Q引导生成**：推理时，每一步从策略中采样M个候选动作，用QNet选择Q值最高的动作执行，重复直到任务完成或达到最大步数。

### 算法流程
1. Stage 1: SFT 训练策略模型 \(\pi_\theta\)。
2. Stage 2: 对每个任务构建探索树，根据公式计算Q值，收集数据集 \(D_Q\)。
3. Stage 3: 训练QNet \(Q_\phi\) 在 \(D_Q\) 上。
4. Stage 4: 使用QNet在推理时引导每一步的动作选择。

## 三、实验设计

### 数据集与场景
- **WebShop**：在线购物环境，1,938条训练轨迹，测试集200条（未见任务）。
- **SciWorld**：科学实验环境，1,483条训练轨迹，测试集含194条已见和241条未见。
- **ALFWorld**：文本版具身家居环境，3,321条训练轨迹，测试集含140条已见和134条未见。
- 所有环境仅最终提供单一结果奖励（0或1，或[0,1]区间）。

### 基准方法
- **封闭源**：GPT-4、GPT-3.5-Turbo、Reflexion（基于GPT-4o）。
- **开放源训练基础**：SFT、RFT（拒绝采样微调）、PPO、ETO（轨迹级DPO）。
- **推理时方法**：Best-of-N（N=6）、MATH-SHEPHERD、TS-LLM、QLASS。
- 所有推理时方法使用相同搜索预算。

### 评价指标
测试集上的平均奖励。

## 四、资源与算力

论文明确说明：使用 **4或8块A6000 GPU**。WebShop实验（SFT、QNet训练、自生成、Q引导探索）耗时 **1-2天**；ALFWorld和SciWorld实验耗时 **4-5天**。其他阶段（如基线训练）未单独说明，但整体资源消耗在合理范围内。

## 五、实验数量与充分性

### 实验数量
- 主要对比实验：3个数据集，每个数据集有已见/未见测试集，共5个场景（WebShop一个，SciWorld两个，ALFWorld两个）。
- 消融实验：不同过程奖励（Q值 vs. 平均奖励 vs. 直接结果奖励）在自训练设置下的对比（图4）。
- 搜索预算对比：Q引导 vs. Best-of-N，不同token消耗下的性能（图3）。
- 少标注实验：WebShop仅用1000条训练轨迹的对比（表3）。
- 不同基座模型：Llama-2-13B在SciWorld上的实验（表4）。
- 案例研究：ALFWorld中一个具体任务的可视化对比。

### 充分性与公平性
- 基线覆盖全面，包括封闭源、开放源、基于过程奖励的方法。
- 所有推理时方法使用相同搜索预算，公平比较。
- 消融实验验证了Q值设计的有效性。
- 少标注实验显示QLASS在数据稀缺下的鲁棒性。
- 但缺少对更大模型（如Llama-3）或不同规模（7B vs 13B以外）的广泛测试，以及没有在更多类型代理任务（如代码生成、多轮对话）上的评估。

## 六、主要结论与发现

1. **QLASS在所有开放源基线中达到最高分**，在WebShop/SciWorld/ALFWorld上分别达到70.3/75.3/66.4（已见）和82.8（ALFWorld未见），甚至超过GPT-4（平均提升17.9%）。
2. **Q引导生成比Best-of-N更高效**：在相同token预算下始终优于Best-of-N；仅用约一半搜索预算（240K tokens）即可超过Best-of-N的最高得分（400K tokens）。
3. **使用Q值作为过程奖励优于平均奖励和直接结果奖励**，在自训练设置中表现最好。
4. **在少量标注数据（1000条）下，QLASS仍保持强性能**，而其他方法（SFT、Best-of-N）显著下降，说明其稳健性和数据效率。

## 七、优点

1. **自动生成过程奖励**：无需人工标注中间步骤，通过探索树和贝尔曼更新有效提取Q值，降低了标注成本。
2. **推理时策略高效**：Q引导生成能动态修剪低价值动作，避免冗余循环，提升搜索效率。
3. **强泛化能力**：在少标注场景和不同基座模型上均表现优异，鲁棒性好。
4. **可解释性**：通过案例展示了Q值随步骤的变化，能识别关键决策点（如“冷却生菜”的Q值远高于“关闭冰箱”）。
5. **方法简洁**：相比MCTS+DPO/PPO等复杂训练流水线，QLASS仅需训练QNet，减少了超参数调优负担。

## 八、不足与局限

1. **实验覆盖有限**：仅测试了三个交互环境（WebShop、SciWorld、ALFWorld），缺少更广泛的基准（如代码生成、多轮问答、机器人控制等）。此外，未评估在更大型模型（如Llama-3-70B）上的表现。
2. **动作多样性增强依赖外部模型**：在WebShop中使用GPT-3.5Turbo进行任务扰动以增加动作多样性，这引入了对外部闭源模型的依赖，且成本较高（论文指出在ALFWorld和SciWorld上未使用）。
3. **探索树构建的计算开销**：虽然通过剪枝限制，但构建树仍需多次环境交互和采样，可能在大规模任务中成本较高。
4. **QNet的泛化边界**：QNet训练基于特定任务环境，是否可直接迁移到全新环境未验证。论文未讨论跨任务泛化。
5. **消融实验深度不足**：未对比不同树宽度/深度、不同折扣因子γ、不同动作候选数M对性能的影响。
6. **潜在偏差风险**：Q值估计依赖子节点最大值，可能对探索不充分的动作产生偏差；此外，SFT阶段的数据偏差可能被QNet放大。

（完）
