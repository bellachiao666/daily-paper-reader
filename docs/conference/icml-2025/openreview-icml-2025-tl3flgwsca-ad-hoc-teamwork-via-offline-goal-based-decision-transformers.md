---
title: Ad Hoc Teamwork via Offline Goal-Based Decision Transformers
title_zh: 基于离线目标决策Transformer的临时团队合作
authors: "Xinzhi Zhang, Hohei Chan, Deheng Ye, Yi Cai, Mengchen Zhao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=tl3FlgWScA"
tags: ["query:agent-papers"]
score: 7.0
evidence: 离线临时团队合作与层次化决策Transformer用于长程推理
tldr: 该论文将临时团队合作扩展到离线设置，提出TAGET框架。通过层次化序列建模，动态预测队友感知的未来奖励，克服了离线数据有限、部分可观测和在线适应问题。实验证明在多种场景下有效。该方法支持长程推理和多智能体协作。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tl3flgwsca/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 721, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tl3flgwsca/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1685, \"height\": 881, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tl3flgwsca/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1773, \"height\": 970, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tl3flgwsca/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1765, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tl3flgwsca/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1775, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tl3flgwsca/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1760, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tl3flgwsca/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1396, \"height\": 870, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tl3flgwsca/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1629, \"height\": 419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tl3flgwsca/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 914, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tl3flgwsca/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 981, \"height\": 455, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tl3flgwsca/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1752, \"height\": 905, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tl3flgwsca/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1767, \"height\": 570, \"label\": \"Table\"}]"
motivation: 现有临时团队合作需要在线交互和精心设计的队友，实际中难以实现。
method: 提出TAGET层次化序列建模框架，使用离线多智能体数据集训练，通过预测队友感知奖励进行在线适应。
result: 在多个任务上，TAGET在有限数据和部分可观测条件下表现出色，实现了有效的在线协作。
conclusion: 为离线临时团队合作提供了可行方案，扩展了多智能体协作的适用范围。
---

## Abstract
The ability of agents to collaborate with previously unknown teammates on the fly, known as ad hoc teamwork (AHT), is crucial in many real-world applications. Existing approaches to AHT require online interactions with the environment and some carefully designed teammates. However, these prerequisites can be infeasible in practice. In this work, we extend the AHT problem to the offline setting, where the policy of the ego agent is directly learned from a multi-agent interaction dataset. We propose a hierarchical sequence modeling framework called TAGET that addresses critical challenges in the offline setting, including limited data, partial observability and online adaptation. The core idea of TAGET is to dynamically predict teammate-aware rewards-to-go and sub-goals, so that the ego agent can adapt to the changes of teammates’ behaviors in real time. Extensive experimental results show that TAGET significantly outperforms existing solutions to AHT in the offline setting.

---

## 论文详细总结（自动生成）

## 论文总结：Ad Hoc Teamwork via Offline Goal-Based Decision Transformers

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：在现实世界中，智能体常常需要与从未见过的队友临时协作（即 Ad Hoc Teamwork，AHT），例如救援机器人、自动驾驶等场景。现有的 AHT 方法大多依赖在线交互与精心设计的队友，但在实际中，环境模拟器可能不可用或成本高昂，且难以覆盖所有队友策略空间。
- **核心问题**：本文首次将 AHT 问题扩展到**离线设置**——即智能体从静态的多智能体交互数据集中直接学习协作策略，而无需在线探索。这面临三大挑战：①离线数据往往有限，无法覆盖多样的队友行为；②部分可观测环境下，队友建模困难；③现有序列决策模型（如 Decision Transformer）依赖的简单回报信号难以捕捉频繁变化的队友意图。
- **整体含义**：提出一种名为 **TAGET** 的层次化序列建模框架，通过动态预测“队友感知的回报-to-go”和“子目标”，使智能体在仅凭局部观测的情况下，实时适应队友行为变化，从而在离线设置下实现有效的临时团队合作。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：采用**层次化决策**结构——高层模块负责预测队友感知的子目标（TA-Goal），低层模块基于子目标生成动作。整体框架将离线多智能体轨迹建模为条件序列学习问题。
- **关键技术细节**：
  1. **离线数据预处理——轨迹镜像策略**：将一条多智能体轨迹中每个智能体轮流作为自我智能体，生成多条镜像轨迹，从而充分利用数据，缓解数据稀疏问题。
  2. **高层：队友感知子目标预测**：
     - 设计两个编码器：团队上下文编码器（基于全局观测）和代理编码器（仅基于自我观测）。通过 KL 散度正则化使代理编码器的潜变量接近团队上下文，从而在部分可观测下推断团队状态。
     - 预测**队友感知回报-to-go（TA-RTG）**：基于团队上下文预测未来回报，比传统 RTG 更准确。
     - 进一步解码**队友感知子目标（TA-Goal）**：即未来 k 步的全局状态，作为高层目标指导低层决策。
  3. **低层：目标条件动作生成**：使用 Causal Transformer（类似 Decision Transformer）以 TA-Goal、自我观测和动作序列为条件，预测当前动作，损失为交叉熵。
  4. **训练损失**：包含三项：正则化损失（KL）、TA-RTG 预测 MSE 损失、TA-Goal 预测二元交叉熵损失，以及低层动作预测损失。

### 3. 实验设计：数据集/场景、基准、对比方法
- **场景**：三个经典多智能体合作环境：
  - **Predator-Prey (PP)**：捕食者协作捕捉猎物。
  - **Level-Based Foraging (LBF)**：智能体根据等级收集食物，需同时同地执行采集动作。
  - **Overcooked**：厨房协作做菜送餐，布局强制分工（“Surrounding”布局）。
- **数据集生成**：采用 SVD 方法训练多样化策略池，每个环境训练 4 个策略种群，其中 3 个用于收集离线数据，1 个作为未见过的测试队友集。每个种群包含多个 checkpoint，保证多样性。
- **对比方法**：**DT**（Decision Transformer）、**Prompt-DT**、**ODITS-off**、**LIAM-off**、**CQL**、**MADT**（Multi-Agent Decision Transformer）。其中 DT/Prompt-DT 为序列模型，ODITS/LIAM 为在线 AHT 的离线变体，CQL 为传统离线 RL，MADT 为多智能体 DT。
- **评价指标**：平均返回（return），每个实验在 50 个 episode 上取平均并报告 95% 置信区间。

### 4. 资源与算力
- 论文中**未明确说明**使用的 GPU 型号、数量或训练时长。仅在附录 E 提到网络配置（嵌入维度 64，层数 2，batch size 2048 等），但未给出硬件细节。

### 5. 实验数量与充分性
- **主要实验**：在三个环境各两种测试集大小（4 个队友集和 8 个队友集）上对比 6 个基线，共 6 组对比实验，每组绘制训练曲线和最终表格。
- **消融实验**：完整 TAGET 与去掉轨迹镜像、去掉 TA-Goal 解码器、去掉 TA-RTG 等变体进行对比，共 4 种条件 × 3 环境 = 12 个比较。
- **超参数分析**：探索了目标步数（goal steps 取 1/2/3/6）的影响。
- **可视化案例**：展示了 PP 环境中 TA-Goal 引导自我智能体的轨迹。
- **充分性**：实验设计全面，覆盖多种环境、不同队友数量，消融实验验证了每个组件的必要性。但跨环境泛化性测试较少（仅三个环境），且队友策略多样性仅由一个 SVD 方法生成，可能存在分布偏差。

### 6. 论文的主要结论与发现
- TAGET 在所有环境和测试集上**显著优于**所有基线方法，平均提升 37.83%。
- 轨迹镜像策略有效缓解了数据稀疏问题；TA-Goal 解码器对性能贡献最大（尤其是在 Overcooked 中）；TA-RTG 和正则化均起关键作用。
- 目标步数的最优值因环境而异：简单环境（PP）需更大步数（6），复杂环境（Overcooked）需适中步数（3）。
- 可视化表明 TA-Goal 能引导智能体协调队友移动而非直接追捕猎物，实现更高效的协作。

### 7. 优点：方法或实验设计上的亮点
- **方法亮点**：
  - 首次将 AHT 成功拓展到离线设置，并针对离线三大挑战提出了系统解决方案。
  - 轨迹镜像策略简单有效，提升了数据利用率。
  - 潜变量正则化巧妙利用 KL 散度使部分观测下也能推断全局团队上下文。
  - TA-Goal 作为高层目标，比传统 RTG 更富含信息，且能动态调整，适应队友变化。
  - 层次化框架结合序列建模，兼具灵活性和鲁棒性。
- **实验亮点**：
  - 使用 SVD 生成多样化策略池，保证训练集和测试集的覆盖与区分。
  - 对比基线涵盖序列模型、传统离线 RL、多智能体 DT 等不同流派，公平性较好。
  - 消融实验充分，清晰展示了各组件贡献。

### 8. 不足与局限
- **实验覆盖有限**：仅三个环境，且均为网格世界模拟器，缺乏真实世界复杂场景验证。队友策略多样性来源于单一生成方法（SVD），可能未完全覆盖现实中的极端行为。
- **部分可观测假设**：代理编码器仅依赖局部观测，但正则化依赖于训练时全局观测的存在；测试时全局观测不可用，潜在误差可能积累。
- **离线数据集依赖**：假设数据集已包含多样玩家，但实际中收集涵盖所有关键行为的数据集成本高，且静态数据无法应对环境动态变化（如新手队友）。
- **长期依赖问题**：Transformer 上下文长度 K=30，对于超长 episode（如 400 步 Overcooked）可能不足以建模长期协作。
- **计算资源**：未披露训练成本，且 batch size 2048 较大，可能对资源要求较高。
- **公平性**：部分基线（如 ODITS-off、LIAM-off）是原始在线方法的简单离线改编，可能未优化适配，对比结果可能存在偏向。

（完）
