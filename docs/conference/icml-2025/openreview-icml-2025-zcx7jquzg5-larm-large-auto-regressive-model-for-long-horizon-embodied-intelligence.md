---
title: "LARM: Large Auto-Regressive Model for Long-Horizon Embodied Intelligence"
title_zh: LARM：用于长程具身智能的大型自回归模型
authors: "Zhuoling Li, Xiaogang Xu, Zhenhua Xu, Ser-Nam Lim, Hengshuang Zhao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=zcx7jqUZg5"
tags: ["query:agent-papers"]
score: 5.0
evidence: 长程具身智能结合强化学习
tldr: 大型LLM具身智能体资源消耗巨大。本文提出LARM，利用轻量级LLM结合裁判强化学习，解决长程探索中奖励消失问题。实验表明，LARM在多个具身任务上表现高效。该工作为长程具身决策提供了低资源方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zcx7jquzg5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1762, \"height\": 772, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcx7jquzg5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1760, \"height\": 904, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcx7jquzg5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1762, \"height\": 1023, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zcx7jquzg5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1505, \"height\": 598, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zcx7jquzg5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 856, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zcx7jquzg5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 771, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zcx7jquzg5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 814, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zcx7jquzg5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 821, \"height\": 246, \"label\": \"Table\"}]"
motivation: 大型LLM具身智能体资源消耗高，而RL代理任务有限。
method: 提出LARM，结合轻量级LLM和裁判RL，直接输出动作。
result: 在长程具身任务上实现了高效的决策性能。
conclusion: 轻型LLM结合特定RL可兼顾效率与泛化。
---

## Abstract
Recent embodied agents are primarily built based on reinforcement learning (RL) or large language models (LLMs). Among them, RL agents are efficient for deployment but only perform very few tasks. By contrast, giant LLM agents (often more than 1000B parameters) present strong generalization while demanding enormous computing resources. In this work, we combine their advantages while avoiding the drawbacks by conducting the proposed referee RL on our developed large auto-regressive model (LARM). Specifically, LARM is built upon a lightweight LLM (fewer than 5B parameters) and directly outputs the next action to execute rather than text. We mathematically reveal that classic RL feedbacks vanish in long-horizon embodied exploration and introduce a giant LLM based referee to handle this reward vanishment during training LARM. In this way, LARM learns to complete diverse open-world tasks without human intervention. Especially, LARM successfully harvests enchanted diamond equipment in Minecraft, which demands significantly longer decision-making chains than the highest achievements of prior best methods.

---

## 论文详细总结（自动生成）

## 论文总结：LARM: Large Auto-Regressive Model for Long-Horizon Embodied Intelligence

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **问题**：现有具身智能体主要基于强化学习（RL）或大型语言模型（LLM）。RL 智能体部署高效但只能完成极少任务；而巨型 LLM（超过 1000B 参数）泛化能力强但计算资源需求巨大，部署困难。
- **动机**：希望结合两者的优势——轻量级部署与强泛化能力，同时避免各自缺陷。特别是在 Minecraft 这类开放世界长程决策任务中，现有方法难以完成如“获得附魔钻石工具”这类高难度长链任务。
- **整体含义**：提出 LARM（Large Auto-Regressive Model），基于轻量级 LLM（<5B 参数）直接输出动作（而非文本），并设计裁判强化学习（Referee RL）来解决长程探索中经典 RL 的奖励消失问题，最终实现高效、泛化的具身智能。

### 2. 方法论：核心思想、关键技术细节
- **核心思想**：将具身任务建模为马尔可夫决策过程，使用一个轻量级 LLM 作为策略网络（LARM），直接以自回归方式预测下一个技能动作；同时引入一个巨型 LLM（GPT-4）作为“裁判”，为每个动作提供即时辅助奖励，弥补环境奖励稀疏导致的梯度消失。
- **关键技术细节**：
  - **LARM 架构**：主体为 TinyLLaVA-3.1B（解码器-only LLM），参数冻结，添加可训练的 LoRA 模块。输入包括任务描述、文本观测（如库存）、视觉观测（图像）和一个可学习的 skill token。通过两个预测头（动作头、价值头）输出动作和状态价值。
  - **裁判机制（Referee RL）**：裁判（GPT-4）根据任务目标、执行动作前后的状态，将反馈分为四类并赋予不同奖励值（ra > rb > 0 > rc > rd）。辅助奖励与环境奖励相加，使长程探索中 TD 误差和 GAE 不再趋近于零。
  - **训练流程**：基于 PPO 框架，但奖励改为环境奖励 + 辅助奖励。每轮收集 T 步数据，用 GAE 估计优势，对 actor 和 critic 进行优化（见 Algorithm 1）。预训练时使用 34G 网页数据（Wiki 爬取）增强领域知识。
- **数学解释**：经典 RL 在长程任务中，因只有最终步有正奖励，导致 TD 误差除最后一步外均为零，GAE 随链长指数衰减至零，优化梯度消失。裁判提供中间步骤的正负反馈，打破这一局面。

### 3. 实验设计：数据集 / 场景、benchmark、对比方法
- **场景**：Minecraft 环境，使用两个平台：
  - **MineDojo**：技能基于 RL 动作，任务包括收集资源、合成工具等（14 个任务）。
  - **Mineflayer**：技能基于 API（如 Harvest a log），任务从木质剑到附魔钻石剑（5 个难度递增的任务）。
- **Benchmark**：在 MineDojo 上沿用之前工作的测试协议；在 Mineflayer 上测试从简单到高级的工具获取。
- **对比方法**：
  - **MineDojo**：MineAgent、Plan4MC、LLaMA-Rider、RL-GPT。
  - **Mineflayer**：AutoGPT、Voyager（基于 GPT-4）、STEVE（基于 LLaMA 微调）。
- **评估指标**：成功率（每个任务测试 30 次）。

### 4. 资源与算力
- **训练**：完成最挑战的任务（附魔钻石工具）大约需要 **42 小时** 的单卡 **RTX 4090 GPU** 探索时间。
- **推理**：在 RTX 4090 上，单次推理耗时 **0.58 秒**，满足在线高层动作调度要求。
- 文中未说明其他实验（如多个任务联合训练）的总算力，但整体资源需求远低于巨型 LLM（>1000B）。

### 5. 实验数量与充分性
- **主要实验**：
  - Table 1：MineDojo 上 14 个任务的成功率对比（与 4 种方法），其中 LARM 在所有任务上均取得最高分。
  - Table 2：Mineflayer 上 5 个任务的成功率对比（与 3 种方法），LARM 在钻石剑（28/30）和附魔钻石剑（16/30）上显著领先，后一个任务此前无方法成功。
- **消融实验**：
  - Table 3：奖励设计（仅环境奖励、环境+LLaVA奖励、二分类裁判奖励、四分类裁判奖励），验证四分类裁判最优。
  - Table 4：LLM 基座选择（0.5B vs 3.1B，以及预训练影响），表明更大模型和网页预训练均提升性能。
  - Table 5：噪声奖励分析（0%、10%、30%、50%），发现噪声超过 10% 时性能显著下降。
  - 另附用例分析（图 3）展示探索、建造、多智能体协作等行为。
- **充分性评价**：实验覆盖了多种任务类型、多个对比方法，消融实验全面验证了关键设计。但 MineDojo 上部分任务缺少 RL-GPT 结果（用“-”表示），可能因该方法未测试那些任务；噪声实验只做了随机替换，未探讨其他噪声类型。总体充分且客观。

### 6. 论文的主要结论与发现
- LARM 在 MineDojo 和 Mineflayer 上均优于之前所有对比方法，尤其在长程任务（如附魔钻石剑）上取得突破性成果（首次成功）。
- 裁判 RL 有效解决了长程探索中奖励消失问题，是提升训练效率的核心。
- 轻量级 LLM 结合 LoRA 微调与网页预训练，能在有限资源下获得足够领域知识。
- 裁判的质量至关重要：噪声过大会严重损害性能；仅限于巨型 LLM（如 GPT-4）才能提供可靠反馈。

### 7. 优点
- **方法创新**：首次将轻量级 LLM 与基于 LLM 裁判的 RL 结合，直接输出动作而非文本，既降低了计算开销，又保留了泛化能力。
- **理论分析**：数学推导了经典 RL 在长程探索中的奖励消失问题，并针对性地提出裁判 RL。
- **实验充分**：在两个不同技能粒度的环境下验证，消融实验覆盖了奖励设计、模型大小、预训练、噪声鲁棒性等多方面。
- **实际效果**：成功完成此前未达成的附魔钻石装备任务，展示了长程决策能力。

### 8. 不足与局限
- **依赖外部裁判**：裁判使用 GPT-4，需要在线 API 调用，存在延迟、成本、可用性问题；且裁判质量对噪声敏感（>10% 噪声即显著下降）。
- **环境局限**：所有实验仅在 Minecraft 中进行，未在真实机器人或其它具身模拟器中验证，泛化性存疑。
- **技能预设**：LARM 输出的动作是预定义的技能（RL 技能或 API），技能库需要人为构造，不是完全自主发现。
- **轻量级 LLM 初始能力有限**：如 TinyLLaVA-3.1B 初始回答 Minecraft 问题错误严重，需大量网页预训练矫正，且最终性能仍不及 GPT-4 直接裁判的潜力。
- **训练效率**：完成最复杂任务仍需 42 小时单卡训练，对于更多任务或更大规模可能仍需优化。

（完）
