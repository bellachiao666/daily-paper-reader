---
title: "RF-Agent: Automated Reward Function Design via Language Agent Tree Search"
title_zh: RF-Agent：基于语言智能体树搜索的自动化奖励函数设计
authors: "Ning Gao, Xiuhui Zhang, Xingyu Jiang, Mukang You, Mohan Zhang, Yue Deng"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=dZ94ZS410X"
tags: ["query:agent-papers"]
score: 4.0
evidence: 语言模型智能体用于自动化奖励函数设计
tldr: 为低层控制任务设计奖励函数通常依赖专家经验。RF-Agent将LLM视为语言智能体，通过树搜索逐步优化奖励函数，有效利用历史反馈。在多个复杂控制任务中，该方法生成的奖励函数优于贪婪或进化算法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1355, \"height\": 658, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 1103, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1207, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1372, \"height\": 232, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1315, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1413, \"height\": 270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1380, \"height\": 738, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1450, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1354, \"height\": 1163, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1419, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1441, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1430, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1269, \"height\": 1233, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1279, \"height\": 1043, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1176, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1330, \"height\": 905, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1338, \"height\": 635, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1263, \"height\": 1232, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dz94zs410x/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1410, \"height\": 739, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-dz94zs410x/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1451, \"height\": 513, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dz94zs410x/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1402, \"height\": 817, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dz94zs410x/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1397, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dz94zs410x/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1392, \"height\": 769, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dz94zs410x/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1394, \"height\": 1964, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dz94zs410x/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 944, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dz94zs410x/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 944, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dz94zs410x/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 948, \"height\": 157, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dz94zs410x/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 949, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dz94zs410x/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1448, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dz94zs410x/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1448, \"height\": 226, \"label\": \"Table\"}]"
motivation: 现有基于LLM的奖励函数生成方法搜索效率低，历史反馈利用率差。
method: 将奖励函数设计建模为序列决策过程，利用LLM智能体在树搜索中迭代生成和评估奖励函数。
result: 在复杂控制任务中显著提升了奖励函数质量和训练效率。
conclusion: 语言智能体树搜索为自动化奖励设计提供了有效优化框架。
---

## Abstract
Designing efficient reward functions for low-level control tasks is a challenging problem. Recent research aims to reduce reliance on expert experience by using Large Language Models (LLMs) with task information to generate dense reward functions. These methods typically rely on training results as feedback, iteratively generating new reward functions with greedy or evolutionary algorithms. However, they suffer from poor utilization of historical feedback and inefficient search, resulting in limited improvements in complex control tasks. To address this challenge, we propose RF-Agent, a framework that treats LLMs as language agents and frames reward function design as a sequential decision-making process, enhancing optimization through better contextual reasoning. RF-Agent integrates Monte Carlo Tree Search (MCTS) to manage the reward design and optimization process, leveraging the multi-stage contextual reasoning ability of LLM. This approach better utilizes historical information and improves search efficiency to identify promising reward functions. Outstanding experimental results in 17 diverse low-level control tasks demonstrate the effectiveness of our method.

---

## 论文详细总结（自动生成）

好的，作为资深学术论文分析助手，以下是对论文《RF-Agent: Automated Reward Function Design via Language Agent Tree Search》的结构化、深入、客观的中文总结。

### 1. 论文的核心问题与整体含义

- **研究动机与背景**：在强化学习（RL）的低层控制任务（如机器人行走、操作）中，奖励函数的设计至关重要。手工设计奖励函数需要大量专家经验且可能次优。逆强化学习和基于偏好的RL方法虽然能缓解问题，但仍依赖专家数据且缺乏可解释性。
- **现有方法的局限**：近期利用大语言模型（LLM）自动生成稠密奖励函数的方法（如Eureka、Revolve）取得了进展。这些方法通常使用**贪婪算法**或**进化算法**来迭代优化奖励函数。然而，它们在复杂控制任务中面临两大关键问题：
    1.  **搜索效率低**：贪婪或进化算法难以有效平衡**探索与利用**，容易陷入局部最优或过度探索。
    2.  **历史信息利用差**：现有方法仅保留局部的历史信息（如当前最优个体），忽视了那些能够从低性能向高性能路径转化的潜在决策轨迹。

### 2. 论文提出的方法论

- **核心思想**：论文将**奖励函数设计问题**重新定义为**序列决策过程**。在此框架下，LLM被视为一个“**语言智能体**”，其“动作”是生成奖励函数代码，“状态”是包含历史奖励函数及其训练反馈的上下文。通过引入**蒙特卡洛树搜索（MCTS）** 来管理这个决策过程，以更好地利用历史信息并平衡搜索的探索与利用。
- **关键技术细节（RF-Agent框架）**：
    1.  **问题建模**：
        - 将奖励函数设计视为MDP。系统的“状态”是包含任务信息、当前奖励函数及其训练反馈的语言指令。
        - LLM的“动作”是基于当前状态生成一个新的奖励函数`R`。
        - “奖励”是环境对基于`R`训练出的策略`π`的评估分数`F`。
    2.  **RF-Agent算法流程**：基于MCTS的四个阶段进行迭代，直到达到最大迭代次数。
        - **选择（Selection）**：使用一个改进的**UCT（上置信界树搜索）** 公式从根节点开始选择最有潜力的节点，直至叶子节点。该公式综合考虑了节点的Q值（回报）、访问次数以及一个**自验证分数**（由LLM评估当前奖励函数达成专家级策略的可能性）。自验证分数主要用于解决早期生成奖励函数得分低、难以区分潜力的冷启动问题。
        - **扩展（Expansion）**：在被选中的节点下，利用LLM通过**五种不同的启发式动作类型**生成新的奖励函数节点。这五种动作旨在有效利用全局历史信息：
            - `am1`（结构变异）：修改奖励函数的结构，如增减奖励组件。
            - `am2`（参数变异）：调整奖励函数中的参数权重。
            - `ac3`（交叉）：从精英集中采样高分节点，结合其有效奖励组件生成新函数，以利用全局高性能信息。
            - `ar4`（路径推理）：分析从根节点到当前节点的整条优化路径，基于对路径的推理生成新函数。
            - `ad5`（不同思路）：从树中随机选择节点，迫使LLM生成结构上与此前尝试不同的奖励函数，以促进探索。
        - **模拟（Simulation）**：用新生成的奖励函数训练策略。论文还引入了一个**思路对齐**机制：在扩展时先生成设计思路再写代码；在模拟后，基于成功编译的代码重新生成设计思路，以消除LLM幻觉或修正带来的思路与代码不匹配问题。
        - **反向传播（Backpropagation）**：将新节点的评估分数（模拟结果）及其自验证分数向上传播，更新父节点的Q值和访问次数，用于指导下一轮的选择。

### 3. 实验设计

- **数据集/场景**：使用了两个低层控制基准环境。
    1.  **IsaacGym**：包含7个代表性任务，覆盖**移动**（如Ant, Humanoid）和**机械臂/手操作**（如AllegroHand, FrankaCabinet）两大类。
    2.  **Bi-DexHands**：包含10个更复杂的双手灵巧操作任务，并进一步分为**Expert-easy**（7个，人类专家成功率较高）和**Expert-hard**（3个，人类专家成功率较低）。
- **Benchmark与对比方法**：
    - **Human（人类专家）**：使用任务创建者手工设计的稠密奖励函数作为上界参考。
    - **Sparse（稀疏奖励）**：直接使用任务评估指标作为奖励，提供下界参考。
    - **Eureka**：基于贪婪迭代的LLM奖励函数设计方法，作为当前最先进方法之一。
    - **Revolve**：基于进化算法的LLM奖励函数设计方法，与Eureka形成补充。
- **评估指标**：在Bi-DexHands中使用**成功率**，在IsaacGym中根据任务目标使用相应的评估分数（如前进速度）。最终结果通过多次不同种子的独立训练取平均值和标准差得到。
- **公平性保证**：为确保比较公平，所有方法在同一个任务上的**总采样次数（即产生的奖励函数数量）** 保持一致：IsaacGym任务为80次，Bi-DexHands任务为512次。所有方法均使用GPT-4o-mini和GPT-4o两种模型进行测试。

### 4. 资源与算力

- **明确说明的部分**：
    - 部署平台为配备**4块Nvidia Geforce RTX3090显卡**、128核CPU和256GiB内存的服务器。
    - **平均运行时间**：在IsaacGym上每个任务约**9小时**；在Bi-DexHands上每个任务约**40小时**。
- **未明确说明的部分**：
    - 未明确指出训练PPO策略所需的单个种子训练的具体时长或GPU资源配置。
    - 未对比不同方法的总体计算开销（LLM调用次数和RL训练次数的总成本），仅表明“几乎相同”，并补充了Token消耗成本的对比（RF-Agent的Input Token成本更高，但Output Token与其他方法相近）。

### 5. 实验数量与充分性

- **实验数量**：
    - **主要对比实验**：在17个不同的低层控制任务上进行了评估，覆盖了移动和多种操纵任务，实验规模较大。
    - **消融实验**：系统地测试了框架核心组件的必要性，包括：搜索方法（UCT vs. DFS/BFS/Greedy）、动作类型（去除不同动作类型的影响）、推理范式（去除自验证和思路对齐）。
    - **分布外（OOD）实验**：额外设计了2个新的Ant任务（躺下、巡逻并返回）来验证方法的泛化能力。
    - **详细消融**：进一步提供了动作组合和思路对齐的详细消融实验。
- **充分性与客观性**：
    - **充分**：实验覆盖了多种控制任务和复杂度，消融实验设计全面，涵盖了算法的主要设计模块和超参数。
    - **公平**：严格控制了总采样次数，使用了多种LLM模型（4o-mini和4o），并报告了多次运行的均值和标准差，确保了统计意义上的可靠性。
    - 总体上，实验设计是充分且客观的，能够有力地支持论文的核心结论。

### 6. 论文的主要结论与发现

- **性能优势**：在IsaacGym和Bi-DexHands的几乎所有17个任务中，RF-Agent生成的奖励函数在最终性能上**显著优于Eureka和Revolve**，并在大部分任务上**匹敌乃至超越人类专家水平**。
- **训练效率**：RF-Agent设计的奖励函数不仅能达到更高的成功率，还能**更快地**训练策略收敛，说明其奖励函数的引导性更好。
- **搜索效率**：随着奖励函数生成数量的增加，RF-Agent的优化性能提升速度**明显快于**其他方法，证明了MCTS在搜索空间中的高效性。这在“专家-困难”任务中尤为明显。
- **框架有效性**：消融实验证实，RF-Agent的各个组件（改进的UCT、多样化的动作类型、自验证与思路对齐）都是提升最终性能的必要组成部分。

### 7. 优点

- **方法论的创新性**：率先将奖励函数设计问题重新概念化为**序列决策问题**，并引入**蒙特卡洛树搜索**来解决，为利用LLM进行自动化奖励设计提供了一个全新的、更强大的范式。
- **有效利用历史信息**：通过树结构和五种启发式动作类型（特别是全局性的交叉和路径推理），RF-Agent能够有效挖掘和组合不同历史决策路径中的有效信息，克服了贪婪或进化方法仅利用局部信息的弊端。
- **良好的探索-利用平衡**：改进的UCT公式和多样化的动作设计（如“不同思路”动作）确保了RF-Agent在搜索过程中既能有效利用当前认知（exploitation），又能持续探索新的空间（exploration）。
- **针对LLM不足的改进**：引入了**自验证**和**思路对齐**等机制，有效缓解了LLM在早期评估和代码生成中的潜在幻觉和不一致性，提升了框架的鲁棒性。

### 8. 不足与局限

- **计算成本高**：论文自身明确承认，RF-Agent与Eureka和Revolve同属一类，都需要**多次与LLM交互和反复进行策略训练**，总体计算开销和时间成本高昂。尽管RF-Agent用相对较小的模型取得了更好效果，但并未减少RL训练迭代的次数。
- **实验覆盖范围**：实验仅限于IsaacGym和Bi-DexHands两个基于物理模拟的环境。虽然任务种类多样，但对于真实的物理机器人环境或更复杂的连续控制问题（如非刚体操作、多机器人协作）的泛化能力尚待验证。
- **对LLM的依赖**：整个框架高度依赖基础LLM（如GPT-4o）的**代码生成**和**逻辑推理**能力。LLM本身的不稳定性和潜在的偏见（例如，在“分布外”任务中可能表现不佳）可能会影响最终结果的质量和可复现性。
- **资源与算力信息不完整**：虽然提供了硬件配置和总运行时间，但未明确每个种子单独RL训练的具体时长，且对不同方法总计算成本的对比不够直接（仅提供了Token消耗对比，未整合RL训练成本）。

（完）
