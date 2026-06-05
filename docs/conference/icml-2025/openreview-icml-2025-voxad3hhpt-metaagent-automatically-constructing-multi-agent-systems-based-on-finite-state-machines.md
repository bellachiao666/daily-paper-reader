---
title: "MetaAgent: Automatically Constructing Multi-Agent Systems Based on Finite State Machines"
title_zh: MetaAgent：基于有限状态机的多智能体系统自动构建
authors: "Yaolun Zhang, Xiaogeng Liu, Chaowei Xiao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=vOxaD3hhPt"
tags: ["query:agent-papers"]
score: 6.0
evidence: 自动构建多智能体系统以求解复杂任务
tldr: 现有手工设计的多智能体框架适用范围有限。本文提出MetaAgent，基于有限状态机自动生成多智能体系统，并利用优化算法进行迭代改进。实验表明该方法能有效构建适用于多种复杂任务的MAS。该工作简化了多智能体系统的设计过程，提升了自动化程度。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1743, \"height\": 753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1702, \"height\": 829, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1743, \"height\": 922, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1813, \"height\": 2157, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1821, \"height\": 1895, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1820, \"height\": 2062, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1828, \"height\": 1394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1810, \"height\": 889, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1555, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 757, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1434, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1453, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1406, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1606, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 808, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1020, \"height\": 941, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 586, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 409, \"height\": 205, \"label\": \"Table\"}]"
motivation: 手工设计多智能体系统难以泛化到新场景。
method: 提出基于有限状态机的框架，自动生成并优化多智能体系统。
result: 在多种任务上成功构建了有效的多智能体系统。
conclusion: MetaAgent实现了多智能体系统的自动设计与优化。
---

## Abstract
Large Language Models (LLMs) have demonstrated the ability to solve a wide range of practical tasks within multi-agent systems. However, existing human-designed multi-agent frameworks are typically limited to a small set of pre-defined scenarios, while current automated design methods suffer from several limitations, such as the lack of tool integration, dependence on external training data, and rigid communication structures. In this paper, we propose \textbf{MetaAgent}, a  \textbf{finite state machine} based framework that can automatically generate a multi-agent system. Given a task description, MetaAgent will design a multi-agent system and polish it through an optimization algorithm. When the multi-agent system is deployed, the finite state machine will control the agent's actions and the state transitions. To evaluate our framework, we conduct experiments on both text-based tasks and practical tasks. The results indicate that the generated multi-agent system surpasses other auto-designed methods and can achieve a comparable performance with the human-designed multi-agent system, which is optimized for those specific tasks.

---

## 论文详细总结（自动生成）

# 论文《MetaAgent: Automatically Constructing Multi-Agent Systems Based on Finite State Machines》详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的大语言模型（LLM）多智能体系统主要由人类手工设计，针对特定场景优化，缺乏泛化能力且设计成本高。少数自动设计方法（如SPP、AutoAgents、ADAS等）存在工具集成缺失、依赖外部训练数据、通信结构僵化（如线性、仅有有限回溯能力）等缺陷。
- **整体含义**：论文提出 **MetaAgent**，一种基于**有限状态机（FSM）** 的框架，能够根据任务描述自动生成并优化多智能体系统，提升系统在多种复杂任务上的部署效率和性能，同时降低开发成本。

## 2. 论文提出的方法论

### 核心思想
- 将多智能体系统的执行过程建模为一个**有限状态机**（FSM），每个状态对应一个子任务，由指定的任务求解Agent、条件验证器（Condition Verifier）、状态指令和监听器（Listeners）组成。
- 通过一个“设计师”LLM自动完成Agent设计、状态和转移条件设计，然后通过**优化算法**合并冗余状态，简化FSM，最后部署执行。

### 关键技术细节
- **Agent设计**：设计师LLM根据任务描述生成Agent的角色、系统提示词和可用工具（如代码解释器、搜索引擎），以JSON格式输出。
- **状态与过渡条件设计**：设计师LLM预见任务求解中的各种情况，定义每个状态的指令、分配Agent、指定监听器，以及基于自然语言的条件转移（包括向前、回溯、停留在当前状态的Null-Transition）。
- **优化算法（FSM State Optimization）**：对状态集合进行两两比较，由适配器LLM判断是否可合并（基于角色区分度、信息传递必要性、工具一致性），迭代直至稳定。该过程**无需外部数据**。
- **部署流程**（Algorithm 2）：从初始状态开始，Agent执行指令，条件验证器检查输出是否符合转移条件；若符合则转移到目标状态（可能回溯），并将输出存入监听器的内存；若无条件满足，则执行Null-Transition，提供反馈让当前Agent重试，直至达到最大迭代次数或最终状态。

### 关键特征
- **Null-Transition**：允许Agent在同一状态内迭代优化自身输出。
- **State Traceback**：当后续状态检测到前序步骤的错误时，可回溯到之前的修正状态。
- **通用性**：论文证明线性结构、分散辩论结构、协调器结构均可视为FSM的特例，MetaAgent的FSM结构更灵活。

## 3. 实验设计

### 使用数据集/场景
- **文本型任务**：
  - **Trivial Creative Writing**（100个任务）：要求写一篇故事包含指定问题的所有答案，评估成功覆盖比例。
  - **GPQA(Diamond)**（198个问题）：研究生级别的科学多选题，评估正确率。
- **实际编码任务**：
  - **Machine Learning Bench（ML Bench）**：5个数据集的机器学习任务（Titanic, House Prices, SCTP, ICR, SVPC），评估归一化性能分数（NPS）。
  - **Software Development**：5个软件（2048游戏、贪吃蛇、打砖块、Excel应用、天气应用），按客观检查点（界面、功能、操作等）计算通过率。

### 对比方法
- 文本任务基准：Direct、CoT、CoT-SC、llm-debate、Self-Refine、SPP（自动设计方法）。
- ML Bench基准：AutoGen、OpenInterpreter、TaskWeaver、MetaGPT、DataInterpreter（人为设计）；以及SPP、AutoAgents（自动设计）。
- 软件开发基准：MetaGPT（人为设计）、AutoAgents、SPP（自动设计）。

### 评估指标
- 文本任务：成功率（故事覆盖问题比例、正确回答比例）。
- ML Bench：归一化性能分数（NPS）。
- 软件开发：检查点通过率。

## 4. 资源与算力

- 论文**未明确说明**使用的GPU型号、数量、训练时长等硬件资源信息。
- **仅提及**：主要实验使用GPT-4o作为基础模型，temperature设为0以确保可复现性。无额外训练过程，所有生成和推理均通过LLM调用完成。
- 在成本分析中，报告了各方法在ML Bench和软件开发任务上的总token消耗，但未给出具体耗时或计算资源。

## 5. 实验数量与充分性

- **实验组数**：主要在4组主要实验（文本2组、ML Bench、软件开发）及多种消融实验和基础模型对比实验。
  - 表2：文本任务对比（4个基线+1个自动方法）。
  - 表3：ML Bench对比（7个基线+2个自动方法）。
  - 表4：软件开发对比（3个基线）。
  - 表5：基础模型质量实验（GPT-4o vs. GPT-3.5-Turbo组合）。
  - 表6：消融实验（工具使用、优化、回溯，在4个任务上分别报告）。
  - 图/附录：统计FSM状态数、过渡数等。
- **充分性与公平性**：
  - 实验覆盖了不同难度和类型的任务（文本、编码、ML），消融实验验证了关键组件的贡献。
  - 但部分基线在某些任务上表现极差（得分为0），可能是由于缺乏工具支持或任务不适应，这一点作者已讨论。
  - 缺乏在更多样化真实场景（如对话、机器人控制）的验证。对超参数（如M最大迭代次数）的影响未深入探讨。

## 6. 论文的主要结论与发现

- **性能优越性**：MetaAgent在文本任务上超越所有对比方法（写作0.86，GPQA 0.60）；在ML Bench上平均0.83，仅次于专为ML设计的DataInterpreter（0.86），超越所有其他人为设计和自动设计框架；在软件开发上平均0.85，大幅超过MetaGPT（0.35）和AutoAgents（0.20）、SPP（0.15）。
- **消融实验重要性**：移除工具使用、优化、回溯均导致显著性能下降（例如软件开发任务移除回溯下降58.8%）。
- **基础模型质量影响**：执行者（Executor）的模型质量比设计师（Designer）更关键（GPT-4o执行者比GPT-3.5-Turbo执行者得分更高）。
- **成本优势**：MetaAgent的总token消耗（设计+部署）低于MetaGPT和AutoAgents，说明自动设计+优化可降低运行成本。

## 7. 优点

- **完全自动化**：无需人工设计多智能体系统的复杂通信拓扑，只需任务自然语言描述即可自动生成。
- **工具集成**：支持代码解释器和搜索引擎，增强Agent的求解能力，这是许多自动设计方法（如SPP、AutoAgents）所缺乏的。
- **灵活的FSM架构**：引入Null-Transition和State Traceback，比固定线性结构更鲁棒，能处理错误和迭代。
- **无需外部训练数据**：优化过程仅依赖LLM的判断，不依赖额外标注数据或强化学习，适合快速原型。
- **通用性证明**：将现有多种MAS结构统一归入FSM框架，理论贡献清晰。
- **实验设计全面**：从文本到实际编码任务，对比多种最新方法，并进行了多角度消融。

## 8. 不足与局限

- **依赖强大LLM**：实验基于GPT-4o，当使用较弱模型（GPT-3.5-Turbo）时性能大幅下降，框架的有效性高度依赖底层模型的推理和生成能力。
- **任务描述需求**：仍需要人类提供清晰的任务描述，系统本身不具备自主发现新任务的能力。
- **未在更多动态/实时任务中验证**：如机器人控制、实时博弈等，这些场景对延迟和状态管理要求更高。
- **实验可复现性**：虽然提供了代码链接，但具体环境配置、随机种子管理、实验次数等未充分说明，可能存在一定偏差。
- **成本分析局限**：仅比较了token数，未涉及实际API调用延时、并发性能等；且设计阶段的token成本可能随着任务复杂度增加而剧增，论文未分析极端复杂任务的情况。
- **安全性/鲁棒性**：未讨论自动生成的Agent行为的安全风险、幻觉或恶意利用问题。

（完）
