---
title: "The Lighthouse of Language: Enhancing LLM Agents via Critique-Guided Improvement"
title_zh: 语言灯塔：通过批评引导改进增强LLM智能体
authors: "Ruihan Yang, Fanghua Ye, Jian Li, Siyu Yuan, Yikai Zhang, Zhaopeng Tu, Xiaolong Li, Deqing Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=D88yhLFzDR"
tags: ["query:agent-papers"]
score: 8.0
evidence: 通过自然语言批评的迭代自我改进
tldr: LLM智能体在环境中需要自我改进，但数值奖励缺乏上下文指导。CGI框架包含一个探索环境的行动者和一个生成详细反馈的批评者，行动者根据批评迭代优化动作。实验显示，语言引导的改进比纯奖励信号更有效，在多个规划任务中取得了更高成功率。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-d88yhlfzdr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1428, \"height\": 723, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d88yhlfzdr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1435, \"height\": 952, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d88yhlfzdr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1315, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d88yhlfzdr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 616, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d88yhlfzdr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 568, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d88yhlfzdr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 604, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d88yhlfzdr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 661, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d88yhlfzdr/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1302, \"height\": 399, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-d88yhlfzdr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 640, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d88yhlfzdr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1456, \"height\": 815, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d88yhlfzdr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1435, \"height\": 327, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d88yhlfzdr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d88yhlfzdr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1455, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d88yhlfzdr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 283, \"label\": \"Table\"}]"
motivation: 数值奖励信号缺乏上下文指导，自然语言反馈更丰富但难以有效实现。
method: 提出批评引导改进框架，包含行动者和批评者，行动者根据批评者的自然语言反馈迭代改进其动作。
result: 在多个智能体规划任务中，批评引导的改进超越了基于奖励的方法。
conclusion: 语言反馈为LLM智能体自我改进提供了更有效的信号。
---

## Abstract
Large language models (LLMs) have recently transformed from text-based assistants to autonomous agents capable of planning, reasoning, and iteratively improving their actions. While numerical reward signals and verifiers can effectively rank candidate actions, they often provide limited contextual guidance. In contrast, natural language feedback better aligns with the generative capabilities of LLMs, providing richer and more actionable suggestions. However, parsing and implementing this feedback effectively can be challenging for LLM-based agents. In this work, we introduce Critique-Guided Improvement (CGI), a novel two-player framework, comprising an actor model that explores an environment and a critic model that generates detailed nature language feedback. By training the critic to produce fine-grained assessments and actionable revisions, and the actor to utilize these critiques, our approach promotes more robust exploration of alternative strategies while avoiding local optima. Experiments in three interactive environments show that CGI outperforms existing baselines by a substantial margin. Notably, even a small critic model surpasses GPT-4 in feedback quality. The resulting actor achieves state-of-the-art performance, demonstrating the power of explicit iterative guidance to enhance decision-making in LLM-based agents.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

**研究动机**：大型语言模型（LLM）已从文本助手发展为能够规划、推理和迭代改进动作的自主智能体。在智能体任务中，如何获取和有效利用高质量反馈是一个核心挑战。

**现有方法的不足**：
- **数值反馈（如奖励模型、验证器）**：只能提供标量分数，用于筛选候选动作，但缺乏上下文指导，无法给出具体改进建议。
- **自然语言反馈（如自我修正、LLM-as-judge）**：更丰富且可操作，但存在两个主要问题：
  1. **弱反馈**：依赖模型自身能力，容易产生幻觉或质量低下的反馈。
  2. **利用不佳**：智能体难以准确解析和整合语言指导，常缺乏灵活性。

**整体含义**：本文提出一种新的两玩家框架——**Critique-Guided Improvement (CGI)**，通过分离行动者和批评者的角色，训练批评者生成精细评估和可操作建议，训练行动者有效利用这些批评，从而提升LLM智能体在交互环境中的决策能力。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程

### 核心思想
- **两玩家框架**：行动者（Actor）与环境交互产生候选动作，批评者（Critic）对每个候选动作生成结构化自然语言批评（包括判别和修订建议），行动者根据批评细化最终动作。
- **两个关键阶段**：
  1. **Critique Generation（批评生成）**：训练批评模型生成高质量、结构化的步骤级反馈。
  2. **Action Refinement（动作细化）**：通过迭代监督微调，让行动者学会有效利用批评。

### 关键技术细节
#### 批评结构
批评包含两部分：
- **判别**：从三个维度评估候选动作：
  - **贡献（Contribution）**：动作对完成任务的帮助程度。
  - **可行性（Feasibility）**：动作是否符合预定义动作列表。
  - **效率（Efficiency）**：是否最优，避免冗余。
- **修订**：给出总体等级（Excellent/Good/Neutral/Poor/Very Poor）和具体的修订建议。

#### 训练批评模型
- 使用专家批评者（如GPT-4）基于参考专家轨迹生成步骤级批评。数据收集仅在正确轨迹（R(τ′)=1）上进行，形成数据集 \( D_{\text{critique}} \)。
- 通过标准语言模型损失微调批评模型：
  \[
  \mathcal{L}_{\text{critic}}(\phi) = \mathbb{E}_{(c_t, \tau'_t, a_t, e) \sim D_{\text{critique}}} [-\log \pi_\phi(c_t | \tau'_t, a_t, e)]
  \]

#### 迭代动作细化
- **探索步骤**：行动者与环境交互，批评者提供批评；只保留正确轨迹及对应的批评-动作对，形成 \( D_{\text{correct}} \) 和 \( D_{\text{refine}} \)。
- **学习步骤**：用 \( D_{\text{correct}} \)、\( D_{\text{refine}} \) 以及专家轨迹 \( D_{\text{expert}} \) 和通用数据集 \( D_{\text{general}} \) 联合微调行动者。损失函数：
  \[
  \mathcal{L}_{\text{actor}}(\theta) = \beta \left[ \mathbb{E}_{(\tau, x, e) \sim D_{\text{train}}} [-\log \pi_\theta(\tau | x, e)] + \mathbb{E}_{(a'_t, \tau'_t, c_t, e) \sim D_{\text{refine}}} [-\log \pi_\theta(a'_t | \tau'_t, c_t, e)] \right] + (1-\beta) \mathbb{E}_{(x,y) \sim D_{\text{general}}} [-\log \pi_\theta(y | x)]
  \]
  其中 \( D_{\text{train}} = D_{\text{expert}} \cup D_{\text{correct}} \)，\( \beta \) 控制权重（通常设为0.8）。

- **迭代**：每次迭代从上一轮的行动者开始，重复探索和学习，共进行K轮（本文设为3轮）。

## 3. 实验设计

### 数据集/场景
- **WebShop**：在线购物环境，12K条指令，超100万真实商品。评估平均最终得分（200次模拟）。
- **ScienceWorld**：基于小学科学课程的标准文本环境，30种科学任务。评估平均最终得分（200次模拟）。
- **TextCraft**：基于Minecraft合成树的文本环境，任务包括合成目标物品。评估成功率（100次模拟）。

### 基准（Baseline）
#### 批评方法对比（表1）
- **数值方法**：DGAP（步骤级判别器）、Explicit RM（预测Q值的奖励模型）。
- **语言方法**：Self-Critique（自我批评）、GPT-4o作为批评者。
- **无批评**：直接行动。
- 行动者固定为：Llama-3-8B-Instruct、Llama-3-70B-Instruct、以及经过专家数据微调的Llama-3-8B-Instruct。

#### 整体框架对比（表2）
- **闭源模型**：DeepSeek-Chat、Claude-3系列、GPT-3.5-Turbo、GPT-4o。
- **开源模型**：Llama-3-70B-Instruct、AgentLM-13B/70B、Agent-FLAN、Llama-3-8B-Instruct 及其变体（Reflexion、Iterative SFT、CGI）。

### 训练数据
- 批评模型训练：从WebShop采样500条、ScienceWorld 350条、TextCraft 374条指令，使用GPT-4o生成批评。
- 动作细化：每个环境每个迭代收集正确轨迹和批评-动作对（见表4）。

## 4. 资源与算力

论文在附录F.2明确说明：
- **GPU**：8块NVIDIA A100-40GB GPU。
- **训练时长**：
  - 批评生成阶段：约5小时46分24秒。
  - 动作细化阶段（每次迭代）：约11小时11分55秒。
- **优化器**：Adam（β₁=0.9, β₂=0.98, ε=1e-8）。
- **学习率**：2e-5，warmup ratio 0.05，序列长度4096，批次大小64。

## 5. 实验数量与充分性

### 实验数量
- **表1**：对比了6种批评方法 × 3种基座模型 = 18组实验，每个环境重复200/100次。
- **表2**：对比了12+种模型/方法，每个环境重复200/100次。
- **图2**：展示了迭代次数（1-3次）对三种迭代方法（CGI、Iterative SFT、Reflexion）的影响。
- **消融实验**（图6）：移除 \( D_{\text{correct}} \)、\( D_{\text{refine}} \)、\( D_{\text{general}} \) 对性能的影响。
- **图3**：轨迹不同阶段的修订比率分析。
- **图4**：不同难度任务性能分析。
- **图5**：候选动作数量M的影响。
- **附录**：额外分析（如迭代次数影响、专家轨迹依赖性等）。

### 充分性与客观性
- 实验覆盖三种不同复杂度的交互环境，任务类型多样（购物、科学推理、合成）。
- 基线和对比方法全面，包括数值/语言反馈、闭源/开源模型、以及现有SOTA方法。
- 设置温度=0，确保结果可重复；报告平均得分，但未给出误差棒（文中说明因温度=0）。
- 消融实验验证了各数据组件的贡献。整体实验设计较为充分、客观。

## 6. 主要结论与发现

1. **语言批评优于数值信号**：在三个环境中，训练过的批评模型（8B）始终优于DGAP等数值方法，平均提升约43% vs 5%。
2. **小批评模型超过GPT-4o**：仅8B参数的Llama-3批评模型在反馈质量上超越GPT-4o，平均提升约29%。
3. **微调模型难以有效利用批评**：经过监督微调的行动者在接受批评时性能提升不如未微调模型，但CGI的迭代动作细化可缓解此问题。
4. **CGI可持续提升性能**：与Reflexion和Iterative SFT相比，CGI在多次迭代中持续改进，尤其是在长时程任务中表现突出。
5. **早期阶段改进最大**：批评主要引导行动者早期探索，减少无效搜索；随着迭代增加，修订比率在早期阶段显著上升。
6. **候选动作数量影响有限**：M≥1时即有显著提升，M=5时接近饱和，而自我批评方法不随M增加而改善。

## 7. 优点

- **创新性的两玩家框架**：将批评生成与动作细化分离，缓解了自我批评的弱反馈和利用不佳问题。
- **结构化批评设计**：三个维度的评估和可操作修订建议，使批评更具体、可解释。
- **高效小模型**：仅8B的批评模型即可超越GPT-4o，计算成本低且可扩展。
- **迭代训练策略**：通过持续收集高质量批评-动作对，解决策略漂移问题，实现持续性能提升。
- **通用性**：三个截然不同的环境（购物、科学推理、合成）均表现优异，且对候选动作数量不敏感。
- **可扩展性**：批评模型可随行动者更新而动态更新（附录F.4显示进一步性能提升）。

## 8. 不足与局限

- **计算开销增加**：相比无批评基线，CGI推理时间增加约4倍（但仍在合理范围，且优于GPT-4o等语言方法）。
- **依赖专家轨迹**：批评模型训练需要专家轨迹（如GPT-4o生成的轨迹），但论文表明即使不使用专家轨迹（仅用GPT-4o轨迹）仍显著优于基线（表6）。
- **未给出误差棒**：虽然设置温度=0，但多次模拟结果可能受随机性影响，缺乏置信区间报告。
- **迭代次数有限**：实验仅进行3轮迭代，第4轮出现性能下降，表明可能存在饱和或过拟合风险。
- **环境局限**：仅测试文本交互环境（WebShop、ScienceWorld、TextCraft），未涉及更复杂的视觉/物理环境。
- **批评质量评估依赖自动指标**：未进行人工评估批评的准确性或可理解性。
- **潜在的偏见风险**：批评模型由GPT-4o生成训练数据，可能继承其偏见。

（完）
