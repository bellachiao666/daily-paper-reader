---
title: "Proposer-Agent-Evaluator (PAE): Autonomous Skill Discovery For Foundation Model Internet Agents"
title_zh: 提议者-智能体-评估者（PAE）：面向基础模型互联网智能体的自主技能发现
authors: "Yifei Zhou, Qianlan Yang, Kaixiang Lin, Min Bai, Xiong Zhou, Yu-Xiong Wang, Sergey Levine, Li Erran Li"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=uCkwqAG0uS"
tags: ["query:agent-papers"]
score: 6.0
evidence: 通过提议-执行-评估循环实现自主技能发现
tldr: 基础模型智能体需要大量技能，但手动注释不可扩展。本文提出PAE系统，包含上下文感知任务提议者、智能体策略和评估者，构成自主发现和练习技能的循环。在互联网环境中，PAE有效扩展了智能体的技能库。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1586, \"height\": 751, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 853, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1507, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1407, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1603, \"height\": 285, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 821, \"height\": 188, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1680, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1517, \"height\": 2143, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1515, \"height\": 861, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1520, \"height\": 1280, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1355, \"height\": 2135, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1513, \"height\": 1280, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1599, \"height\": 1791, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1509, \"height\": 855, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1505, \"height\": 2142, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1519, \"height\": 2139, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1540, \"height\": 2138, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1515, \"height\": 860, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1520, \"height\": 856, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1511, \"height\": 1709, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckwqag0us/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1295, \"height\": 1272, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-uckwqag0us/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1752, \"height\": 913, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uckwqag0us/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 990, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uckwqag0us/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 656, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uckwqag0us/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1781, \"height\": 428, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uckwqag0us/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1771, \"height\": 1056, \"label\": \"Table\"}]"
motivation: 手动注释技能不可扩展。
method: 构建提议-执行-评估循环，让智能体自主发现并练习技能。
result: 在互联网环境中有效扩展了智能体技能库。
conclusion: 自我学习循环能实现技能自主发现。
---

## Abstract
A generalist foundation model agent needs to have a large and diverse skill repertoire, such as finding directions between two travel locations and buying specific items from the Internet. If each skill needs to be specified manually through a fixed set of human-annotated instructions, the agent’s skill repertoire will necessarily be limited due to the scalability of human-annotated instructions. In this work, we address this challenge by proposing Proposer-Agent-Evaluator (PAE), an effective learning system that enables foundation model agents to autonomously discover and practice skills in the wild. After a context-aware task proposer generates instructions based on website information, the agent policy attempts those tasks in the real world with resulting trajectories evaluated by an autonomous VLM-based success evaluator. The success evaluation serves as the reward signal for the agent to refine its policies through RL. We validate PAE on challenging vision-based web navigation, using both real-world and selfhosted websites from WebVoyager and WebArena. Our results show that PAE significantly improves the zero-shot generalization capability of VLM Internet agents (around 50% relative improvement)
to both unseen tasks and websites.

---

## 论文详细总结（自动生成）

# 论文总结：Proposer-Agent-Evaluator (PAE): Autonomous Skill Discovery for Foundation Model Internet Agents

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：通用型基础模型智能体需要大量多样化技能（如查找路线、网购），但手动为每个技能标注指令不可扩展，导致技能库受限。
- **目标**：使智能体能够**自主发现并练习**有用技能，无需人类监督，且学到的技能可泛化到未见任务和网站。
- **整体含义**：提出一种自我改进的学习系统，利用VLM（视觉语言模型）作为任务提议者和评估者，让智能体在真实网站环境中通过试错和强化学习自动扩充技能库，从而提升零样本泛化性能。

## 2. 方法论

### 核心思想：不对称能力利用
- 观察到SOTA VLM在**提议任务**和**评估结果**方面远强于**执行任务**（作为智能体）。PAE利用这一不对称性：由“提议者”生成可行任务，“智能体”尝试执行，“评估者”给出成功/失败信号，智能体通过RL优化策略。

### 关键技术细节

#### 三大组件
1. **上下文感知任务提议者（Context-Aware Task Proposer）**  
   - 基于网站上下文信息（如网站名称、用户演示截图）生成指令。  
   - 对知名网站仅用名称即可；对自托管网站需额外上下文。
2. **智能体策略（Agent Policy）**  
   - 输入：带数字标记的网页截图（标记可交互元素） + 任务描述。  
   - 输出：思维链（Chain-of-Thought）+ 具体操作（点击、输入文字等）。  
   - 使用REINFORCE或过滤行为克隆（Filtered BC）优化。
3. **自主评估者（Autonomous Evaluator）**  
   - 基于最终三张截图和智能体最终答案，给出**0/1稀疏奖励**。  
   - 评估器为VLM（如Claude Sonnet或Qwen2VL），仅判断任务是否成功完成。

#### 优化目标
使用REINFORCE：
\[
\mathcal{L}(\pi) = \mathbb{E}_{\tau} \left[ \left( \sum_{i=1}^{H} r(s_i, a_i) \right) \left( \sum_{i=1}^{H} \log \pi(a_i|s_i) \right) \right]
\]
由于奖励为终端0/1，等价于筛选成功轨迹进行行为克隆（Filtered BC）。

#### 关键设计选择
- 使用**结果基评估器**而非步骤基或函数基评估器（后者更易幻觉）。
- 加入**思维链推理步骤**，使智能体反思所学技能，提升泛化能力。

## 3. 实验设计

### 数据集/场景
- **WebVoyager**：557个任务，覆盖13个真实在线网站（如Amazon、GitHub、Coursera等），使用人类标注作为真值。
- **WebArena Easy**：从WebArena选取并简化的任务集，共208个任务，分布在OpenStreetMap（108个）、PostMill（50个）、OneStopMarket（50个），使用功能验证函数作为真值。
- **未见网站泛化测试**：额外85个在线网站，生成500个合成任务。

### 对比方法
- **专有模型**：Claude 3 Sonnet、Claude 3.5 Sonnet。
- **开源模型**：Qwen2VL-7B/72B、InternVL2.5-8B、LLaVa-1.6-7B/34B。
- **SFT基线**：用Claude生成的演示数据微调LLaVa（在85个无关网站或WebArena内收集数据）。
- **PAE变体**：使用不同任务提议者和评估者（Qwen2VL-7B/72B）、不同上下文（仅网站名 vs 用户演示截图）、有无思维链、不同评估器类型（步骤级、函数级）。

### 评估指标
- 成功率的加权平均（按任务数）。WebVoyager使用自动评估器（与人类对齐，系统级偏差1.7%）；WebArena使用真值验证函数。

## 4. 资源与算力

- **文中未明确说明**GPU型号、数量、训练时长等具体硬件信息。仅给出超参数（见表5）：
  - WebVoyager：学习率2e-5，每轮收集4096条轨迹，训练4个epoch。
  - WebArena：每轮收集2048条轨迹，训练2个epoch。
- 未提及使用的GPU类型或集群规模。

## 5. 实验数量与充分性

### 实验数量
- **主要对比**：在WebVoyager（表1）和WebArena Easy（表2）上报告了所有基线和PAE变体的成功率。
- **泛化测试**：表3展示在85个未见网站上的零样本结果。
- **消融实验**（图3）：评估器类型（结果 vs 步骤 vs 函数）、有无思维链、不同任务提议者能力（Qwen7B/72B vs Claude）、不同上下文（用户演示）。
- **人工评估对齐**（图4）：200条轨迹的system-level和instance-level相关分析。
- **失败模式分析**（图6）：对6类错误进行统计。
- **学习曲线**（图5）：不同上下文下各网站训练/测试成功率随轨迹数的变化。

### 充分性和公平性
- **充分**：覆盖了多种开源和专有模型，消融实验全面（几乎每个设计选择都单独验证），且对未见网站也进行了测试。
- **公平**：所有模型使用相同的提示模板和观测（带数字标记的截图），评估使用统一标准。但需注意：
  - WebArena仅使用了简化版（Easy），未在完整812任务上评估（因部分网站不支持多线程数据收集）。
  - SFT基线使用了Claude生成的演示数据，而PAE未使用人工演示，但初始SFT checkpoint本身也依赖了Claude数据。
  - 部分结果可能因真实网站动态变化而不可完全复现（文中已说明）。

## 6. 主要结论与发现

1. **PAE显著提升性能**：LLaVa-7B PAE在WebVoyager上相较SFT基线绝对提升7.4%（14.9%→22.3%），在WebArena Easy上提升10.8%（18.0%→24.6%），相对提升约50%。
2. **弱提议者/评估者也可改进强智能体**：甚至用Qwen2VL-7B（自身作为智能体仅1.4%成功率）作为提议者和评估者，也能使LLaVa-7B从SFT的18.0%提升至23.1%，证实了不对称能力利用的有效性。
3. **思维链至关重要**：去掉思维链后，在训练任务集上略有提升，但泛化性能显著下降（图3右）。
4. **结果基评估器优于步骤基和函数基**：步骤基评估器太“慷慨”导致失败，函数基评估器易虚构验证条件。
5. **技能可迁移到未见网站**：PAE使LLaVa-7B在未见网站上的成功率从SFT的9.1%提升至16.3%，LLaVa-34B从16.1%提升至21.4%。
6. **PAE与模型规模正相关**：从7B到34B，PAE带来的绝对改进从7.4%增加到10.8%。

## 7. 优点

- **自监督闭环**：无需任何人类标注，智能体能自主发现、练习并优化技能，具有扩展潜力。
- **设计稳健**：对提议者和评估者的能力要求低（甚至可用很差的开源模型），且关键设计选择（结果评估器、思维链）均通过消融实验验证。
- **强泛化性**：不仅提升在训练集上的表现，还能零样本迁移到未见网站和任务，接近甚至超越专有模型。
- **详细的消融和错误分析**：给出了失败模式分布，揭示PAE针对性减少幻觉（7B模型）和低层级执行错误（34B模型）。
- **与人类评估一致**：自动评估器与人类标注相关度高（系统偏差仅1.7%）。

## 8. 不足与局限

- **应用范围有限**：仅在视觉Web导航任务上验证，未涉及其他GUI（如手机、桌面）或机器人领域。
- **依赖预训练数据**：初始SFT checkpoint依赖Claude生成的演示数据，PAE虽无需人工标注，但“冷启动”仍需监督数据（若基础模型本身已具备一定能力，如Claude，则可跳过）。
- **WebArena基准不完整**：仅使用Easy子集，未在完整WebArena（812任务）上评估（因技术问题），缺少高难度任务下的比较。
- **环境动态性**：真实网站可能更新导致结果不可复现，文中已承认这一点。
- **最大步骤限制**：每轮仅10步，对于复杂长链任务可能不足。
- **安全风险**：虽然采取了限制个人账户和防火墙等防护，但未系统分析攻击面或实验中的实际风险。
- **算力信息缺失**：未报告具体训练时长和硬件配置，降低可复现性。

（完）
