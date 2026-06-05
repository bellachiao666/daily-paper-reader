---
title: "WebDancer: Towards Autonomous Information Seeking Agency"
title_zh: WebDancer：迈向自主信息搜索智能体
authors: "Jialong Wu, Baixuan Li, Runnan Fang, Wenbiao Yin, Liwen Zhang, Zhenglin Wang, Zhengwei Tao, Ding-Chu Zhang, Zekun Xi, Xiangru Tang, Yong Jiang, Pengjun Xie, Fei Huang, Jingren Zhou"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=quJdphBcdP"
tags: ["query:agent-papers"]
score: 7.0
evidence: 强化学习微调用于自主信息搜索智能体
tldr: 构建自主信息搜索智能体需要多步推理和数据效率。WebDancer提出从数据构建到强化学习微调的四阶段范式，基于ReAct格式的web代理在GAIA和WebWalkerQA基准上取得领先结果，验证了该范式的有效性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qujdphbcdp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1393, \"height\": 713, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qujdphbcdp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 692, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qujdphbcdp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qujdphbcdp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 570, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qujdphbcdp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1439, \"height\": 309, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qujdphbcdp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 1268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qujdphbcdp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 574, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qujdphbcdp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 734, \"height\": 161, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qujdphbcdp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 684, \"height\": 148, \"label\": \"Table\"}]"
motivation: 复杂现实问题需要深度的信息搜索和多步推理，现有系统在数据效率和泛化性上存在不足。
method: 提出四阶段构建方法：浏览数据构建、轨迹采样、监督微调冷启动、强化学习增强泛化，并实例化为WebDancer代理。
result: 在GAIA和WebWalkerQA等挑战性基准上取得了先进的性能。
conclusion: 该范式为开发自主信息搜索智能体提供了系统化的训练蓝图。
---

## Abstract
Addressing intricate real-world problems necessitates in-depth information seeking and multi-step reasoning. 
Recent progress in agentic systems, exemplified by Deep Research, underscores the potential for autonomous multi-step research. 
In this work, we present a cohesive paradigm for building end-to-end agentic information seeking agents from a data-centric and training-stage perspective.
Our approach consists of four key stages: (1) browsing data construction, (2) trajectories sampling, (3) supervised fine-tuning for effective cold start, and (4) reinforcement learning for enhanced generalisation.
We instantiate this framework in a web agent based on the ReAct format, WebDancer.
Empirical evaluations on the challenging GAIA and WebWalkerQA benchmarks demonstrate the strong performance of WebDancer, achieving considerable results and highlighting the efficacy of our training paradigm. 
Further analysis of agent training provides valuable insights and actionable, systematic pathways for developing more capable agentic models.

---

## 论文详细总结（自动生成）

# WebDancer：迈向自主信息搜索智能体 — 详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：现实世界中的复杂问题（如多跳信息检索、长链推理）往往需要深度信息搜索与多步推理能力。现有系统（如 Deep Research）虽展现出潜力，但普遍面临以下挑战：
  - 高质量、细粒度的浏览数据获取困难；
  - 可靠的长序列推理轨迹构建不足；
  - 训练策略难以在开放、动态的 web 环境中实现泛化。
- **核心问题**：如何从零开始，系统化构建一个端到端的自主信息搜索 web 代理（agent），使其具备类似 Deep Research 的自主多步搜索与推理能力？
- **研究含义**：本文提出了一整套从数据生成到强化学习微调的范式，为社区提供了一份构建长周期信息搜索代理的“蓝图”，并通过实例化 WebDancer 验证了其有效性。

## 2. 方法论

### 2.1 核心思想

本文提出一个四阶段构建流程，以数据为中心、分阶段训练为导向，逐步赋予代理自主信息搜索能力：

1.  **浏览数据构建**：自动生成高质量、多样化、多步推理的 QA 对。
2.  **轨迹采样**：使用大语言模型（LLM）和大型推理模型（LRM）采样高质量 ReAct 格式轨迹。
3.  **监督微调（SFT）冷启动**：在轨迹上训练模型，使其学会交替推理与工具调用的模式。
4.  **强化学习（RL）泛化增强**：使用 DAPO 算法在线优化策略，提升泛化能力和决策质量。

### 2.2 关键技术细节

#### 2.2.1 浏览数据构建

- **CRAWL QA**：通过爬取知识类网站（如 arxiv、github、wiki），递归访问子页面，使用 GPT-4o 基于爬取内容生成指定类型（如 COUNT、MULTI-HOP、INTERSECTION）的 QA 对。
- **E2HQA**：从简单事实型 QA 对（SimpleQA 风格）出发，迭代地用搜索到的信息替换原始问题中的实体，逐步构建更难的多步问题，且保证答案不变。

#### 2.2.2 轨迹采样

- **代理设置**：采用 ReAct 框架，动作空间包括 `search`（搜索）、`visit`（访问 URL）和 `answer`（回答）。
- **短/长 CoT 构造**：
  - **短 CoT**：使用 GPT-4o 直接以 ReAct 格式运行，收集轨迹。
  - **长 CoT**：使用 QwQ-Plus 分步决策，但排除上一步的 thought 只保留 action/observation，将其中间推理过程作为当前步的 thought。
- **轨迹过滤**：通过三阶段漏斗过滤：
  - 有效性控制（丢弃格式不合规的轨迹）
  - 正确性验证（使用 GPT-4o 判断答案是否正确）
  - 质量评估（过滤掉幻觉、严重重复、信息冗余等）

#### 2.2.3 监督微调冷启动

- 将轨迹中的 Thought、Action、Observation 用特殊标记（`<think>`、`<tool_call>`、`<tool_response>`、`<answer>`）格式化。
- 训练时，只对模型生成的 tokens（thought、action）计算损失，屏蔽来自环境的 observation：
  \[
  L = -\frac{1}{\sum_{i=1}^{|H|} \mathbb{I}[x_i \neq o]} \sum_{i=1}^{|H|} \mathbb{I}[x_i \neq o] \cdot \log \pi_\theta(x_i | tc, x_{<i})
  \]
  其中 \( \mathbb{I}[x_i \neq o] \) 用于过滤 observation 部分。

#### 2.2.4 强化学习泛化增强

- **算法**：采用 DAPO（Decoupled Clip and Dynamic Sampling Policy Optimization），其动态采样机制可忽略 SFT 阶段未利用的 QA 对中可能存在的噪声样本。
- **奖励设计**：由格式奖励（10%权重）和答案奖励（90%权重）组成，答案奖励通过 LLM-as-Judge 判断。
- **Rollout**：每次 rollout 包含多轮 `<think>` + `<tool_call>` 交互，直到生成 `<answer>` 结束。

## 3. 实验设计

### 3.1 数据集与基准

- **GAIA**（文本验证集 103 题）：评估复杂信息检索能力。
- **WebWalkerQA**（测试集 680 题）：专注于深度 web 信息检索。
- **附加基准**：BrowseComp（英文版 1,266 题）和 BrowseComp-zh（中文版），用于更极端的挑战。

### 3.2 对比方法

| 类别 | 方法 |
|------|------|
| **无代理** | Qwen-2.5-7B/32B/72B-Instruct、QwQ-32B、DeepSeek-R1-671B、GPT-4o 的 Base 模式或简单 RAG |
| **闭源代理** | OpenAI Deep Research |
| **开源代理** | Search-o1、R1-Searcher、WebThinker（Base/RL）、SimpleDeepSearcher |
| **ReAct 代理** | Vanilla ReAct（使用 GPT-4o、Qwen-2.5、QwQ-32B 等）|

- 评估指标：Pass@1、Pass@3、Consistency@3（多次尝试中正确次数的比例）。
- 奖励模型：使用 Qwen-72B-Instruct 作为 Judge，并与 GPT-4o 对比验证一致性。

## 4. 资源与算力

- **硬件配置**：32 个节点，每个节点配备 8 张 NVIDIA H20（显存 96GB）。
- **训练时长**：论文未明确说明每阶段的具体训练时长，但提到 RL rollouts 成本高，实验中 rollout 数设为 16。
- **数据规模**：SFT 数据集共约 14,228 条轨迹（短 CoT 7,678 条，长 CoT 6,550 条）。RL 阶段使用约 5,000 对未被 SFT 利用的 QA 对。

## 5. 实验数量与充分性

- **主要实验**：在 GAIA 和 WebWalkerQA 上对比了多种模型和方法，包括不同 backbone 大小的 WebDancer 与 Vanilla ReAct 的对比（表 1）。
- **附加基准**：在 BrowseComp 和 BrowseComp-zh 上进行了测试（表 2）。
- **消融分析**：
  - **数据效率消融**（图 3）：比较了 Open-only、Crawl-only、E2H-only、All、Final 数据集下的表现，表明高质量过滤至关重要。
  - **CoT 类型对比**（表 3）：短 CoT 与长 CoT 在不同模型上的效果及无效率。
  - **训练步数与 RL 效果**（图 5a）：Pass@3 和 Consistency@3 随 RL 步数提升。
  - **动作数量与推理长度演化**（图 5b）：SFT 和 RL 对轨迹长度的影响。
  - **温度对性能的影响**（图 5c）：解码温度调整影响不大，表明环境动态变化是主要不稳定因素。
  - **记忆压力测试**：在 GAIA 子集上过拟合，但 greedy 解码仅 37.4%，说明任务难以稳定。
- **充分性评价**：实验覆盖了多个数据集、多种 backbone（7B、32B、QwQ-32B）、多种对比方法，并进行了丰富的消融和深入分析，实验设计比较客观且充分。但缺乏对更多工具（如 Python 沙箱）的扩展实验。

## 6. 主要结论与发现

1. **训练范式的有效性**：所提出的四阶段构建流程可以显著提升代理在复杂信息搜索任务上的性能，WebDancer 在 GAIA 上达到 51.5%（Pass@1），WebWalkerQA 上达到 47.9%，超越多数开源代理。
2. **RL 提升多样性与一致性**：强化学习可以提升 Pass@3 和 Consistency@3，尤其对非推理模型效果明显，但对推理模型的提升边际递减。
3. **长 CoT 对推理模型友好**：长 CoT 显著提升了推理模型（QwQ-32B）的性能，但对非推理模型会引入格式错误和重复问题。
4. **高质量数据与过滤至关重要**：Final 过滤后的数据集在低数据量下表现最优，证明了筛选的价值。
5. **SFT 冷启动是 RL 成功的前提**：单独 RL 训练效果很差（Pass@3 仅 5%），说明 SFT 建立基础模式后 RL 才能发挥作用。
6. **环境动态性是主要挑战**：解码温度对性能影响小，性能波动主要源于 web 环境的非平稳性。

## 7. 优点

- **系统化的端到端范式**：从数据构建到训练，给出了一套可复制的四阶段流程，为社区提供了清晰的建设路线。
- **数据自动合成策略**：CRAWL QA 和 E2HQA 方法能自动生成多样化、高难度的多步推理 QA 对，解决了现有数据集规模小、难度低的问题。
- **长短 CoT 轨迹构造**：分别针对 LLM 和 LRM 设计轨迹生成策略，充分利用了推理模型的长链思考能力。
- **创新的 RL 训练**：使用 DAPO 算法进行在线策略优化，动态采样机制有效过滤噪声样本，提升了数据效率和政策稳健性。
- **全面的实验分析**：不仅在两个主流基准上取得领先，还进行了丰富的消融、能力演化、跨模型迁移等分析，结论可靠。

## 8. 不足与局限

- **工具种类有限**：目前仅支持 `search` 和 `visit` 两种工具，缺乏浏览器全功能（如滚动、表单填写）和 Python 环境，限制了在更复杂任务上的表现。
- **任务泛化范围窄**：仅在短答案信息搜索任务上评估，未扩展到长文档级研究和开放域生成任务，后者在奖励建模上更具挑战。
- **数据利用率低**：RL 阶段仅使用了约 5,000 对 QA，大量数据未充分利用，存在数据效率瓶颈。
- **Rollout 成本高**：RL 阶段需要多次工具调用和模型补全，计算和时间开销大，限制了大规模迭代。
- **混合推理模式缺失**：目前训练采用单一 CoT 类型（短或长），未来需要自适应混合推理能力。
- **环境不稳定性**：web 环境动态变化，同一方法多次运行结果波动大（如记忆测试仅 37.4%），系统的稳定性仍需提升。
- **对推理模型迁移效果有限**：长 CoT 知识从推理模型迁移到指令模型效果不佳，存在跨模型推理能力迁移的脆弱性。

（完）
