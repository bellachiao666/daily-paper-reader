---
title: "From Debate to Equilibrium: Belief‑Driven Multi‑Agent LLM Reasoning via Bayesian Nash Equilibrium"
title_zh: 从辩论到均衡：基于贝叶斯纳什均衡的信念驱动多智能体LLM推理
authors: "Xie Yi, Zhanke Zhou, Chentao Cao, Qiyu Niu, Tongliang Liu, Bo Han"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=RQwexjUCxm"
tags: ["query:agent-papers"]
score: 9.0
evidence: 多智能体LLM协作推理与均衡
tldr: 多智能体LLM框架常面临高计算成本且缺乏收敛保证。本文将多LLM协调建模为不完美信息博弈，提出ECON范式，通过层次强化学习寻求贝叶斯纳什均衡。每个智能体基于信念独立选择响应最大化期望奖励，结合分布式推理与集中输出。实验表明ECON在推理任务上高效且收敛。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 858, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1731, \"height\": 846, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 884, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1760, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1036, \"height\": 859, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 964, \"height\": 882, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1389, \"height\": 864, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1382, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1381, \"height\": 880, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1384, \"height\": 881, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1381, \"height\": 877, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1494, \"height\": 937, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1727, \"height\": 836, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1631, \"height\": 722, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 845, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 832, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1783, \"height\": 2165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1779, \"height\": 2247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1783, \"height\": 1502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 687, \"height\": 1770, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 689, \"height\": 1773, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 686, \"height\": 1775, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 689, \"height\": 1778, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 686, \"height\": 1774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 688, \"height\": 1778, \"label\": \"Table\"}]"
motivation: 多智能体LLM框架计算成本高且缺乏收敛性。
method: 将协调建模为不完美信息博弈，通过层次RL寻求贝叶斯纳什均衡。
result: ECON实现高效收敛的多智能体推理。
conclusion: 博弈论视角可有效提升多LLM协调的效率和稳定性。
---

## Abstract
Multi-agent frameworks can substantially boost the reasoning power of large language models (LLMs), but they typically incur heavy computational costs and lack convergence guarantees. To overcome these challenges, we recast multi-LLM coordination as an incomplete-information game and seek a Bayesian Nash equilibrium (BNE), in which each agent optimally responds to its probabilistic beliefs about the strategies of others. We introduce Efficient Coordination via Nash Equilibrium (ECON), a hierarchical reinforcement-learning paradigm that marries distributed reasoning with centralized final output. Under ECON, each LLM independently selects responses that maximize its expected reward, conditioned on its beliefs about co-agents, without requiring costly inter-agent exchanges.
We mathematically prove that ECON attains a markedly tighter regret bound than non-equilibrium multi-agent schemes. Empirically, ECON outperforms existing multi-LLM approaches by 11.2% on average across six benchmarks spanning complex reasoning and planning tasks. Further experiments demonstrate ECON’s ability to flexibly incorporate additional models, confirming its scalability and paving the way toward larger, more powerful multi-LLM ensembles. The code is publicly available at: https://github.com/tmlr-group/ECON.

---

## 论文详细总结（自动生成）

# 论文总结：From Debate to Equilibrium: Belief‑Driven Multi‑Agent LLM Reasoning via Bayesian Nash Equilibrium

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：多智能体LLM框架（如多智能体辩论MAD）能显著提升推理能力，但存在三大障碍：① 大量令牌交换导致高计算开销；② 多轮信息交换超出上下文窗口限制，阻碍可扩展性；③ 缺乏明确的协调协议，性能可能不如简单的集成或自一致性方法。
- **核心问题**：如何构建一个原则性强、可扩展的多智能体协调框架，使其高效收敛并降低通信成本。
- **整体含义**：本文将多LLM交互建模为不完美信息博弈，通过追求贝叶斯纳什均衡（BNE）来取代直接的令牌交换，从而在保证推理性能的同时大幅降低计算负担，并提供理论收敛保证。

## 2. 方法论：核心思想、技术细节与算法流程
- **核心思想**：将多LLM协调转化为不完美信息博弈，每个智能体基于关于其他智能体策略的概率信念（belief）选择自己的最优策略，寻求贝叶斯纳什均衡（BNE）。框架名为ECON（Efficient Coordination via Nash Equilibrium），采用层次强化学习范式，将分布式推理与集中式输出相结合。
- **关键技术细节**：
  - **问题形式化**：建模为DEC-POMDP（分散部分可观测马尔可夫决策过程），包含N个智能体（N-1个执行LLM + 1个协调LLM），每个执行LLM维护本地历史并生成信念状态。
  - **BNE存在性证明**：通过Glicksberg不动点定理证明存在BNE。
  - **ECON框架包含两个阶段**：
    - **推理阶段**：协调LLM生成策略和格式，分发给执行LLM；每个执行LLM独立生成回答；协调LLM聚合得到最终输出。
    - **优化阶段**：每个执行LLM拥有信念网络（Belief Network），将本地轨迹映射为信念状态，并输出提示嵌入（温度、重复惩罚）和局部Q值；信念编码器（Belief Encoder）通过多头注意力聚合所有信念状态为群体表示；集中混合网络（Centralized Mixing Network）结合局部Q值和特征变换计算全局Q值，并通过TD损失和相似差异损失进行优化。
  - **奖励设计**：包含三个组成部分：动作似然奖励（与最终输出一致性）、任务特定奖励、协作贡献奖励，均被截断到Rmax。
  - **早停机制**：基于最终输出稳定性、平均奖励阈值和损失收敛性判断。
  - **理论贡献**：得到子线性遗憾界 O(N√T/(1-γ))，而现有非均衡多智能体方法为线性遗憾 O(δmax T/(1-γ))。

## 3. 实验设计：数据集、基准与对比方法
- **数据集**：5个推理任务（GSM8K、GSM-Hard、MATH、SVAMP、StrategyQA）以及一个极具挑战性的规划任务TravelPlanner（使用GPT-4 Turbo）。
- **基准（Baselines）**：
  - 单轮CoT提示（零样本、少样本）
  - 多轮CoT提示（自一致性SC@64）
  - 值引导搜索方法（TS-LLM、PPO-MCTS）
  - 多轮自我改进方法（ToT、RAP、ReAct）
  - 多LLM推理框架（rStar、多智能体辩论MAD）
- **对比设置**：所有对比在同一LLM基座上公平进行（如LLaMA3.1 8B/70B/405B、Mistral-7B、Mixtral-8x22B、Qwen1.5 110B等），零样本设置。

## 4. 资源与算力
- 论文未明确说明**具体的GPU型号、数量、训练时长**等硬件资源细节。仅提及使用了开源LLM并通过Together API进行调用，训练采用离线方式。未量化计算开销的具体数值（除令牌使用量外）。

## 5. 实验数量与充分性
- **实验数量**：文章报道了大量实验，包括：
  - 主实验结果（5个推理数据集，4种模型，对比9种方法，共约180组结果）
  - 旅行规划任务（GPT-4，另加多个基线）
  - 模型配置与成本效率分析（异构/同构、令牌消耗对比）
  - 扩展性实验（执行LLM数量从3增加到9，以及协调器数量按比例增加）
  - 消融实验（BNE前后性能、奖励组件、策略设置、信念编码器、连接操作等）
- **充分性与公平性**：
  - 实验覆盖多个主流模型和数据集，对比方法全面。
  - 消融实验验证各模块贡献，令牌消耗对比体现效率优势。
  - 但是，未在更多任务（如代码、常识问答）上进行测试，仅聚焦数学和规划。
  - 所有实验均在零样本设置下进行，可能未充分挖掘模型微调潜力。
  - 异构模型实验显示性能下降，但未深入分析原因。

## 6. 主要结论与发现
- ECON在6个基准上平均超过现有多智能体方法11.2%，超过单智能体方法10.9%。
- 相比3轮MAD，ECON减少令牌消耗平均21.4%。
- 将执行LLM从3个扩展到9个（伴随协调器按比例增加）可带来18.1%的额外性能提升。
- 理论证明ECON实现子线性遗憾界，而MAD方法为线性遗憾。
- ECON能灵活整合异构模型，尽管同构模型性能更优。

## 7. 优点
- **理论坚实**：首次为多LLM系统形式化BNE，提供存在性证明和精细的遗憾界分析。
- **高效可扩展**：用信念协调代替显式消息传递，大幅降低通信成本；层次结构支持扩展到多个协调器和大量执行LLM。
- **实验全面**：覆盖多种模型、任务和基线，消融实验验证各组件必要性。
- **实用性强**：代码开源，易于复现和进一步应用。

## 8. 不足与局限
- **资源算力未量化**：未给出GPU型号、训练时间等硬件消耗，不利于成本估算。
- **任务覆盖面有限**：主要集中在数学推理和规划，未在更广泛的NLP任务（如常识问答、代码生成、翻译）上验证。
- **异构模型性能下降**：当执行LLM为异构时，性能低于同构，且低于最强模型单独的结果，表明BNE在异质智能体间更难达成。
- **早期停止阈值依赖人工设定**：ϵC、Rthreshold等需要手动调整，可能影响泛化性。
- **仅在零样本设置下评估**：未测试微调或提示工程进一步优化的情况。
- **与多智能体辩论的公平性**：虽然ECON令牌消耗更低，但直接比较时MAD的总令牌可能因轮数不同而差异较大，论文仅以3轮作为标准对比。

（完）
