---
title: On the Resilience of LLM-Based Multi-Agent Collaboration with Faulty Agents
title_zh: 基于LLM的多智能体协作系统在故障智能体下的鲁棒性研究
authors: "Jen-tse Huang, Jiaxu Zhou, Tailin Jin, Xuhui Zhou, Zixi Chen, Wenxuan Wang, Youliang Yuan, Michael Lyu, Maarten Sap"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=bkiM54QftZ"
tags: ["query:agent-papers"]
score: 4.0
evidence: 多智能体协作系统在故障智能体下的鲁棒性研究
tldr: 该论文研究了基于LLM的多智能体协作系统在面对故障智能体时的鲁棒性。通过提出AutoTransform和AutoInject两种方法模拟智能体出错，系统分析了不同拓扑结构（如链式、环式）在故障下的表现，并探索了提升鲁棒性的策略。研究为构建更可靠的多智能体系统提供了重要见解，但并未直接涉及自改进机制。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-bkim54qftz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 806, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkim54qftz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1511, \"height\": 1289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkim54qftz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1721, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkim54qftz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 871, \"height\": 867, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkim54qftz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1716, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkim54qftz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 951, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 859, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1099, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1307, \"height\": 514, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1507, \"height\": 536, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1355, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1690, \"height\": 412, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1277, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1175, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1750, \"height\": 1697, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1748, \"height\": 1656, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1758, \"height\": 723, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1752, \"height\": 1073, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1754, \"height\": 1727, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1742, \"height\": 886, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1745, \"height\": 1024, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1731, \"height\": 455, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1742, \"height\": 558, \"label\": \"Table\"}]"
motivation: 多智能体系统中故障智能体的影响尚未被充分研究。
method: 提出AutoTransform和AutoInject两种故障注入方法，分析不同系统结构下的鲁棒性。
result: 揭示了不同结构在故障下的性能差异，并提出防御策略。
conclusion: 该工作为设计鲁棒的多智能体协作系统提供了指导。
---

## Abstract
Large language model-based multi-agent systems have shown great abilities across various tasks due to the collaboration of expert agents, each focusing on a specific domain. However, the impact of clumsy or even malicious agents—those who frequently make errors in their tasks—on the overall performance of the system remains underexplored. This paper investigates: (1) What is the resilience of various system structures (e.g., A$\rightarrow$B$\rightarrow$C, A$\leftrightarrow$B$\leftrightarrow$C) under faulty agents, on different downstream tasks? (2) How can we increase system resilience to defend against these agents? To simulate faulty agents, we propose two approaches—AutoTransform and AutoInject—which introduce mistakes into the agents' responses. Experiments on four downstream tasks using six systems show that the "hierarchical" structure, i.e., A$\rightarrow$(B$\leftrightarrow$C), exhibits superior resilience with the lowest performance drop of 5.5%, compared to 10.5% and 23.7% of other two structures. To further improve resilience, we introduce (1) Challenger, that introduces a mechanism for each agent to challenge others' outputs, and (2) Inspector, an additional agent to review and correct messages, recovering up to 96.4% errors made by faulty agents. Our code and data are available at https://github.com/CUHK-ARISE/MAS-Resilience.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：基于大语言模型（LLM）的多智能体协作系统已在代码生成、数学推理、翻译、文本评估等任务上展现出优异性能。然而，系统中可能混入“笨拙”甚至“恶意”的智能体（faulty agents），它们会频繁产生错误，破坏整体协作。现有研究多关注攻击诱发的毒性输出或错误信息传播，但忽略了系统结构对故障鲁棒性的影响以及如何恢复协作。
- **整体含义**：本文首次系统性地探究不同多智能体系统拓扑结构（线性、扁平、层级）在面对故障智能体时的鲁棒性，并提出增强鲁棒性的防御机制。研究结果为设计更可靠的多智能体协作系统提供了指导。

## 2. 方法论：核心思想、关键技术细节

### 2.1 故障注入方法
- **AutoTransform**：通过LLM重写智能体的prompt/profile，使其保留原有功能但暗中注入隐蔽错误。步骤包括：（1）分析目标智能体任务；（2）列举错误注入方式（强调隐蔽性）；（3）重写prompt，加入错误生成指令。适用于任意角色和任务。
- **AutoInject**：直接在智能体之间传输的消息中注入错误，可精确控制错误率（消息层面 \(P_m\) 和消息内错误比例 \(P_e\)）和错误类型（语义错误 vs 语法错误）。通过LLM自动生成错误内容并替换原消息。

### 2.2 系统结构分类
- **线性（Linear）**：单向链式通信，如A→B→C。代表系统：MetaGPT、Self-collab。
- **扁平（Flat）**：全双向通信，如A↔B↔C。代表系统：Camel、SPP。
- **层级（Hierarchical）**：混合单向与双向通信，如A→(B↔C)。代表系统：MAD、AgentVerse。

### 2.3 防御机制
- **Challenger**：在每个智能体的profile中添加挑战能力，使其能够质疑其他智能体的输出。
- **Inspector**：引入一个独立的“检查员”智能体，拦截并纠正所有中间消息中的错误。两者可组合使用。

## 3. 实验设计

- **下游任务与数据集**：
  - 代码生成：HumanEval（164道手写编程题），评估指标Pass@1（0-100）。
  - 数学推理：CIAR（50道反直觉算术题），Accuracy。
  - 翻译：CommonMT（Lexical子集，100句），BLEURT-20。
  - 文本评估：FairEval（80条人类标注的“胜/平/负”标签），Accuracy。
- **基准系统**：共6个多智能体系统，涵盖三种结构：
  - Linear：MetaGPT（5智能体）、Self-collab（3角色）。
  - Flat：Camel（2智能体）、SPP（2～5人格）。
  - Hierarchical：MAD（2辩论者+1法官）、AgentVerse（4智能体）。
- **对比方法**：
  - 单智能体基线（使用相同LLM但无协作）。
  - 无故障智能体的原始多智能体系统（Vanilla）。
  - 使用AutoTransform或AutoInject引入故障后的系统表现。
- **实验设置**：使用GPT-3.5和GPT-4o作为骨干LLM（温度0）；每次仅注入一个故障智能体；正常智能体不知晓故障存在（信息不对称场景）。

## 4. 资源与算力

- 论文**未明确说明**使用的具体GPU型号、数量或训练时长。文中仅提到使用OpenAI的GPT-3.5和GPT-4o API（通过调用），因此未涉及本地训练或微调所需的专用算力。实验成本主要来源于API调用次数。

## 5. 实验数量与充分性

- **实验数量**：覆盖三个结构×六个系统×四个任务×两种故障注入方法×两种骨干LLM，共约96组主实验（6系统×4任务×2方法×2模型）。此外还包括：
  - 错误率消融：9种 \(P_m\) 与 \(P_e\) 组合（表6）。
  - 错误类型对比：语义错误 vs 语法错误（表7）。
  - 防御机制实验：Challenger、Inspector及其组合在Self-collab和Camel上的结果（表3）。
  - 附加实验：单智能体对比、多故障智能体、更复杂任务（Snake游戏）、更多模型（LLaMA-3.1-70B、o1-Mini）及链式思考（CoT）。
- **充分性**：实验设计比较系统，覆盖了不同结构、任务、错误率、错误类型和防御方法。但存在以下局限性：
  - 每个结构仅选取两个代表性系统，可能受特定prompt设计影响。
  - 所有智能体共享同一骨干LLM（GPT-3.5/4o），未测试异构模型。
  - 仅评估了四类文本任务，未涉及多模态或长程规划。

## 6. 主要结论与发现

1. **层级结构鲁棒性最强**：在GPT-3.5和GPT-4o上，层级结构的平均性能下降最少（5.5%），扁平结构下降10.5%，线性结构下降23.7%。这是因为高层智能体（如法官）能综合多个低层智能体的输出，检测并纠正错误。
2. **客观任务受故障影响更大**：代码生成和数学推理对错误最敏感（平均下降22.6%和9.9%），而翻译和文本评估受影响较小（下降4.7%和5.4%）。原因在于前两者要求严格的形式正确性。
3. **错误类型影响不同**：语义错误比语法错误更严重——LLM能较好识别语法错误，但语义错误更难检测（如边界条件错误）。
4. **错误率效应**：增加错误消息的比例（\(P_m\)）比增加单条消息内错误比例（\(P_e\)）对性能影响更大；但过高错误率会“暴露”故障，反而使系统主动纠正。
5. **意外收益**：在某些系统中（如MAD、Camel），故意注入错误可能通过“双重检查”或“发散思维”机制提升性能（最高提升12.1%）。
6. **防御有效性**：Challenger和Inspector组合可恢复最多96.4%的性能损失，尤其对较脆弱的线性与扁平结构有效。

## 7. 优点

- **研究视角新颖**：首次系统比较不同多智能体系统结构对故障的鲁棒性，而非仅关注攻击方法。
- **方法论可控**：AutoInject提供精确的错误率、错误类型控制，便于消融分析。
- **防御机制实用**：Challenger和Inspector无需修改原始系统架构，可即插即用。
- **实验覆盖面广**：6个系统、4个任务、两种模型、多种错误设置，并包括附加分析（多故障、更复杂任务、非GPT模型）。
- **启发设计原则**：建议采用层级结构（类似真实组织）以提高鲁棒性。

## 8. 不足与局限

- **模型同质化**：所有智能体使用同一骨干LLM（GPT系列），未测试异构模型（如混合GPT+开源模型）的鲁棒性。
- **任务局限性**：仅关注文本任务（代码、数学、翻译、评估），未涉及其它领域（如对话、规划、多模态）。
- **自动化指标**：依赖自动评估（Pass@1、Accuracy、BLEURT），缺乏人工验证，尤其对主观任务（翻译、评估）可能不够准确。
- **提示工程偏差**：每个系统有各自的prompt设计，结构差异与prompt工程混杂，难以完全归因于拓扑。
- **未考虑长时协作**：实验中智能体间通信轮次有限，未模拟长时间运行中的累积误差。
- **算力资源未披露**：未提及API调用总成本或计算约束，影响可复现性。

（完）
