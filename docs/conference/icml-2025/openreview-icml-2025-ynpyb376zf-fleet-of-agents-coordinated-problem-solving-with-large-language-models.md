---
title: "Fleet of Agents: Coordinated Problem Solving with Large Language Models"
title_zh: 智能体舰队：基于大语言模型的协作问题求解
authors: "Lars Henning Klein, Nearchos Potamitis, Roland Aydin, Robert West, Caglar Gulcehre, Akhil Arora"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=yNpYb376zf"
tags: ["query:agent-papers"]
score: 7.0
evidence: 多智能体协作，动态树搜索，复杂问题求解
tldr: 现有方法在平衡成本与质量方面存在不足。本文提出Fleet of Agents框架，利用LLM作为智能体，通过遗传型粒子滤波方法进行动态树搜索，实现多智能体协同探索与开发。实验表明该方法在多种复杂任务上有效提升了求解质量与效率。该工作为多智能体协作求解复杂问题提供了新范式。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 792, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1754, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1424, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1249, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1757, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1240, \"height\": 1312, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1433, \"height\": 1185, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1186, \"height\": 1186, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1185, \"height\": 1186, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1189, \"height\": 1189, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1763, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1761, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1758, \"height\": 578, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 852, \"height\": 393, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 850, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 848, \"height\": 530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 850, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1760, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1020, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1749, \"height\": 635, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 905, \"height\": 1609, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 907, \"height\": 1417, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1259, \"height\": 896, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 904, \"height\": 706, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1237, \"height\": 199, \"label\": \"Table\"}]"
motivation: 现有推理增强方法在成本与质量之间难以平衡。
method: 提出Fleet of Agents框架，利用LLM作为智能体，采用遗传型粒子滤波进行动态树搜索。
result: 在多种复杂任务上实现了高质量求解，同时控制了成本。
conclusion: 所提方法有效平衡了探索与利用，提升了多智能体协作效率。
---

## Abstract
While numerous frameworks have been developed to enhance the reasoning abilities of large language models (LLMs), there is a scarcity of methods that effectively balance the trade-off between cost and quality. 
In this paper, we introduce Fleet of Agents (FoA), a novel and intuitive yet principled framework utilizing LLMs as agents to navigate through dynamic tree searches, employing a genetic-type particle filtering approach. 
FoA spawns a multitude of agents, each exploring the search space autonomously, followed by a selection phase where resampling based on a heuristic value function optimizes the balance between exploration and exploitation. 
This mechanism enables dynamic branching, adapting the exploration strategy based on discovered solutions. 
We conduct extensive experiments on four benchmark tasks, \``Game of 24\'', \``Mini-Crosswords\'', \``WebShop\'' and \``SciBench\'', utilizing four different LLMs, GPT-3.5, GPT-4, LLaMA3.2-11B, and LLaMA3.2-90B. 
On average across all tasks and LLMs, FoA obtains an absolute quality improvement of $\simeq 5\%$ while requiring only $\simeq 35\%$ of the cost of previous SOTA methods. Notably, our analyses reveal that (1) FoA achieves the best cost-quality trade-off among all benchmarked methods, and (2) FoA+ LLaMA3.2-11B surpasses the Llama3.2-90B model. FoA is publicly available at [https://github.com/au-clan/FoA](https://github.com/au-clan/FoA).

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：现有提升大语言模型（LLM）推理能力的框架在成本与质量之间难以取得良好平衡。单查询方法（如CoT、CoT-SC）成本低但质量有限，尤其不适合需要与环境交互的序贯决策任务；多查询方法（如ToT、GoT、LATS）通过搜索多条推理路径获得高质量结果，但代价高昂、效率低下。
- **背景**：LLM在推理和问题求解方面展现强大能力，催生了众多基于提示的推理框架。然而，设计一个既能保持高质量又能控制成本的通用框架仍然是一个关键挑战。
- **动机**：本文旨在改进多查询方法的成本效率，提出一种能同时适用于通用问题求解和序贯决策任务的推理框架。

## 2. 提出的方法论（核心思想、关键技术细节、算法流程）

- **核心思想**：将**遗传型粒子滤波（genetic-type particle filtering）** 概念引入动态树搜索。通过一个“智能体舰队”（Fleet of Agents）协同探索状态空间，利用变异（mutation）和选择（selection）阶段实现探索与利用的平衡。
- **关键技术细节**：
    - **舰队初始化**：生成 \(n\) 个智能体，每个独立维护当前状态 \(s_{i,t}\)。
    - **变异阶段**：每个智能体自主进行 \(k\) 步状态转移（称为“突变”），从当前状态下采样动作 \(a_{i,t}\sim\pi_a(a|s_{i,t})\)，然后环境返回新状态 \(s_{i,t+1}\)。支持“强制变异”（禁止原地不动）和“突然死亡”（无效状态被删除，随机复制另一智能体填充）。
    - **选择阶段**：每 \(k\) 步后，用启发式价值函数 \(v(s)\) 评估所有当前状态，计算重采样权重（支持线性、指数、贪婪等方案），然后按权重有放回地重采样 \(n\) 个新智能体状态。这使得高价值状态获得更多复制，低价值状态被淘汰。
    - **回溯机制**：通过折扣因子 \(\gamma\) 允许从历史状态中重采样，以纠正局部错误。折扣因子对较早访问的状态价值进行衰减。
- **算法流程**（文字描述）：
    1. 初始化 \(n\) 个智能体的状态为初始状态。
    2. 循环：
        - 每个智能体独立执行 \(k\) 步突变（生成新状态），期间检查是否找到解。
        - 执行选择阶段：计算所有当前状态的价值，根据重采样分布进行有放回重采样，得到新的智能体集合。
        - 如果找到解或达到预算，停止。
- **核心优势**：动态分支——搜索宽度（分支数）根据状态价值自动调整，而非固定的分支因子。通过调整智能体数量 \(n\) 和步数 \(t\) 可精确控制计算延迟和成本。

## 3. 实验设计

- **数据集/场景**：采用四个具有不同需求的基准任务：
    1. **Game of 24**：数学谜题（使用4个数字通过四则运算得到24），测试集为1000个谜题中的索引901-1000。
    2. **Mini-Crosswords**：5×5纵横填字游戏，测试集为156个谜题中每隔5个选取的20个。
    3. **WebShop**：模拟电子商务网站导航，根据用户指令购买产品，测试集为50个随机子任务。
    4. **SciBench**：科学推理任务（涉及物理、化学、生物），取每个领域前15%作为验证集，剩余85%作为测试集。
- **评测指标**：
    - Game of 24：成功率（%）
    - Mini-Crosswords：字母重叠率（%）
    - WebShop：平均分数（环境奖励）
    - SciBench：准确率（%）
    - 所有任务均报告成本（美元）。
- **对比方法**：
    - Game of 24：IO、CoT、CoT-SC、AoT、ToT、GoT、RAFA、ReST-MCTS*。
    - Mini-Crosswords：IO、CoT、CoT-SC、ToT、GoT。
    - WebShop：Act、ReAct、Reflexion、LASER、LATS，以及多个监督/强化学习基线（IL、IL+RL、WebN-T5、WebGUM）和人类专家。
    - SciBench：IO、CoT、CoT-SC、ToT、ReST-MCTS*。
- **基础模型**：GPT-4（主结果），GPT-3.5（WebShop和SciBench因成本限制），Llama3.2-11B和90B（泛化性测试）。

## 4. 资源与算力

- 论文中未明确说明GPU型号、数量或训练时长。所有实验均为**推理阶段**，无模型训练。使用了OpenAI API（GPT-3.5/4）和TogetherAI API（Llama3.2）。成本以美元计，具体API价格在附录中列出（例如GPT-4输入$30/百万tokens，输出$60/百万tokens）。没有提及硬件资源。

## 5. 实验数量与充分性

- **实验数量**：
    - 主实验：4个任务 × 多个基线（总共约30+个对比配置）。每个任务至少采用一种基础模型（GPT-4或GPT-3.5）。额外用Llama3.2-11B和90B在全部任务上做了泛化测试。
    - 消融实验：在Game of 24上使用GPT-3.5、Llama3.2-11B和90B进行5项消融（选择阶段、重采样、回溯、缓存、批处理）。其余三个任务也有类似消融（见附录D.2）。
    - 模型分析：成本-质量权衡（图5右）、模型大小-质量权衡（图5左）等。
    - 每个实验（除GPT-4外）重复5次，报告均值。GPT-4因成本只运行一次。
- **充分性**：实验设计较为全面，覆盖了数学推理、填字游戏、网页导航和科学问答四种不同难度和类型的任务。对比方法覆盖了当时主流的单查询和多查询方法。消融实验验证了各组件贡献。但WebShop和SciBench没有使用GPT-4（因成本过高），这可能影响对最强模型的公平比较。另外，SciBench仅用GPT-3.5和Llama3.2-11B，缺少更强大模型对比。总体而言，实验设计相对客观公平，但存在一定的模型覆盖局限。

## 6. 主要结论与发现

- FoA在所有四个任务上均**超越所有现有方法**，在质量上取得平均约5%的绝对提升，而成本仅为之前SOTA方法的约35%。
- FoA实现了**最佳成本-质量权衡**，在不同价格点均优于ToT、GoT、RAFA、ReST-MCTS*等。
- **小模型+FoA可超越大模型**：例如，FoA+LLaMA3.2-11B在多个任务上性能超过单独的LLaMA3.2-90B，表明这种方法能够缩小模型规模带来的性能差距。
- **各组件均有正面贡献**：消融实验显示移除选择阶段、重采样、回溯、缓存或批处理均会导致性能下降或成本增加。

## 7. 优点

- **新颖性**：首次将遗传型粒子滤波应用于LLM智能体协作，不同于固定分支的树搜索，实现了动态分支，平衡探索与利用。
- **实用性**：FoA是一个**运行时（runtime）**，而非提示方案，可以集成任何现有AI代理，无需修改其行为，即插即用。
- **成本可控**：通过调整智能体数量 \(n\) 和步数 \(t\) 可精确预测延迟和成本，适合资源受限场景。
- **实验严谨**：采用了多种LLM（GPT-3.5/4、Llama3.2-11B/90B），并做了充分消融和模型分析。代码公开可复现。

## 8. 不足与局限

- **固定舰队大小**：当前为每个任务分配固定数量的智能体，缺乏自适应分配更难任务的机制。
- **价值函数设计**：仅使用简单的启发式价值函数，未来可探索更智能的价值估计（如利用相邻状态信息）和更丰富的重采样方案。
- **舰队组织**：目前为同质舰队，没有代理间的层级结构或嵌套粒子滤波等高级协作模式。
- **实验覆盖偏差**：部分任务（WebShop、SciBench）因成本未用GPT-4最强模型，可能低估了FoA在更大模型上的潜在优势。此外，SciBench仅用GPT-3.5和Llama3.2-11B，未能评估最先进模型。
- **应用限制**：方法依赖于可定义状态转移和启发式价值函数的任务，对完全开放式的生成任务适用性可能有限。未讨论在实时性要求极高的场景下的工程优化。

（完）
