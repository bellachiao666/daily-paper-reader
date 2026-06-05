---
title: Towards Efficient Online Tuning of VLM Agents via Counterfactual Soft Reinforcement Learning
title_zh: 通过反事实软强化学习实现VLM智能体的高效在线调优
authors: "Lang Feng, Weihao Tan, Zhiyi Lyu, Longtao Zheng, Haiyang Xu, Ming Yan, Fei Huang, Bo An"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=H76PMm7hf2"
tags: ["query:agent-papers"]
score: 5.0
evidence: 在线强化学习调优VLM智能体以提升其多步能力
tldr: 该论文针对VLM智能体在线强化学习调优中文本动作空间探索爆炸的问题，提出反事实软强化学习（CoSo）。通过反事实推理动态评估每个token的因果影响，CoSo有效降低了探索空间，使在线调优更高效。实验表明CoSo在多种视觉语言下游任务中提升了智能体的多步目标导向能力。该方法为通过RL实现VLM智能体自我改进提供了实用途径。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1664, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 846, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1711, \"height\": 1199, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 833, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 800, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1592, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1592, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 894, \"height\": 339, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 543, \"height\": 83, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 293, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 294, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 293, \"height\": 290, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-h76pmm7hf2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 858, \"height\": 782, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-h76pmm7hf2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1644, \"height\": 584, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-h76pmm7hf2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1726, \"height\": 485, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-h76pmm7hf2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1236, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-h76pmm7hf2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1560, \"height\": 275, \"label\": \"Table\"}]"
motivation: VLM智能体在线RL调优时文本动作空间巨大导致探索困难。
method: 利用反事实推理评估token因果重要性，指导软RL探索。
result: 在多个VLM智能体任务上调优效率显著提升。
conclusion: CoSo通过反事实方法有效解决了VLM智能体在线RL的探索问题。
---

## Abstract
Online fine-tuning vision-language model (VLM) agents with reinforcement learning (RL) has shown promise for equipping agents with multi-step, goal-oriented capabilities in dynamic environments. However, their open-ended textual action space and non-end-to-end nature of action generation present significant challenges to effective online exploration in RL, e.g., explosion of the exploration space. We propose a novel online fine-tuning method, Counterfactual Soft Reinforcement Learning (CoSo), better suited to the textual output space of VLM agents. Compared to prior methods that assign uniform uncertainty to all tokens, CoSo leverages counterfactual reasoning to dynamically assess the causal influence of individual tokens on post-processed actions. By prioritizing the exploration of action-critical tokens while reducing the impact of semantically redundant or low-impact tokens, CoSo enables a more targeted and efficient online rollout process. We provide theoretical analysis proving CoSo's convergence and policy improvement guarantees, and extensive empirical evaluations supporting CoSo's effectiveness. Our results across a diverse set of agent tasks, including Android device control, card gaming, and embodied AI, highlight its remarkable ability to enhance exploration efficiency and deliver consistent performance gains. The code is available at https://github.com/langfengQ/CoSo.

---

## 论文详细总结（自动生成）

# 论文总结：Towards Efficient Online Tuning of VLM Agents via Counterfactual Soft Reinforcement Learning

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：视觉-语言模型（VLM）被用作智能体（agent）在动态环境中执行多步、目标导向的任务（如手机控制、游戏、具身AI）。为了提升 VLM 智能体的任务适应性，近年来采用强化学习（RL）进行在线调优。
- **核心问题**：VLM 智能体的动作空间是开放式的文本，生成 utterance（包含思考、规划、动作等）后需经解析函数转换为可执行动作。文本的探索空间随词表大小和序列长度指数增长（如 32,100^100），且很多 token（如格式固定、语义冗余）对最终动作无重要影响。传统的 RL 探索（对所有 token 施加均匀熵或随机探索）导致效率极低，难以驱动有意义的学习。
- **整体含义**：针对 VLM 智能体文本动作空间的特殊性，设计更高效的在线探索方法是提升 RL 调优效果的关键。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
### 核心思想
- 提出 **Counterfactual Soft Reinforcement Learning (CoSo)**，通过反事实推理评估每个 token 对最终解析动作的因果重要性，从而在软 RL 的目标函数中对不同 token 的熵进行加权，优先探索关键 token（<10%），抑制冗余 token（>80%），大幅缩小有效探索空间。

### 关键技术细节
1. **Token-to-Action 因果结构**：引入因果权重向量 \( B_{y\to a} \in \mathbb{R}^n \)，表示每个 token 对动作的因果影响大小。通过反事实推理计算：
   - 假设将 token \( y_i \) 替换为 null 值（如特殊字符），其余 token 不变，测量动作输出概率的变化（式6）。
   - 使用轻量级 BERT 网络作为结构因果模型（SCM）来模拟 \( P(a|y) \)。
2. **因果加权熵正则化**：在软 RL 的目标函数中，将每个 token 的熵乘以其因果权重：
   \[
   \max_\pi \sum_t \mathbb{E}_{(s_t,a_t)\sim\rho_\pi} \left[ \gamma^t \left( r(s_t,a_t) + \alpha H_B(\pi(\cdot|s_t)) \right) \right]
   \]
   其中 \( H_B(\pi(\cdot|s)) = \sum_{i=1}^n B_{y\to a}^i \cdot H(y_i|y_{1:i-1}) \)。
3. **理论保证**：论文证明 CoSo 的 Bellman 算子收敛（策略评估）、策略单调改善，以及策略迭代收敛到最优策略（Lemma 4.2-4.3, Proposition 4.4）。

### 算法流程（文字说明）
- 离线阶段：使用 SFT 初始化 VLM 智能体。
- 在线阶段（每轮迭代）：
  - Rollout：智能体与环境交互，采样 utterance \( y_t \)，解析为动作 \( a_t \)，收集经验。
  - 反事实推理：对每个 token 生成 nullified 序列，用 SCM 计算因果权重 \( B_{y\to a} \)。
  - 模型更新：更新 SCM（交叉熵损失），使用 CoSo 目标更新 VLM。

## 3. 实验设计：数据集/场景、benchmark、对比方法
### 数据集/场景
- **Android-in-the-Wild (AitW)**：真实世界手机控制任务，包括 General（545 训练/96 测试）和 WebShopping（438 训练/96 测试）。动作如点击、滑动、输入等。
- **Gym Cards**：卡牌推理环境，包含 NumberLine、EZPoints、Points24、Blackjack 四个任务。
- **ALFWorld**：具身 AI 环境，包含 Pick&Place、ExamineInLight、Clean&Place、Heat&Place、Cool&Place、PickTwo&Place 六个子任务。

### Benchmark 与对比方法
- **Prompting 方法**：Gemini 1.5 Pro、GPT-4V（有/无 AppAgent 增强）、LLaVA-1.6。
- **Learning 方法**：CogAgent、AutoUI+SFT、Online Filtered BC、DigiRL（基于 AWR）、RL4VLM（基于 PPO）。
- 所有对比使用官方的实现和报告结果（部分来自原始论文）。

## 4. 资源与算力（文中说明部分）
- 论文在附录 D 中给出了计算开销表格（Table D.1）：
  - 使用 NVIDIA H100 GPU。
  - VLM 参数量 7.96B，SCM 仅 0.01B。
  - CoSo 相比基线（RL）额外增加约 0.5 H100 GPU 小时（训练时间从 13.9 小时到 14.5 小时），GPU 内存增加 0.7 GB（从 37.0 GB 到 37.7 GB）。
- 未明确说明具体使用的 GPU 数量，但通常单卡训练（基于提供的时间）。总体上计算开销增量可接受。

## 5. 实验数量与充分性
- **实验数量**：
  - 三大类任务：AitW（General + WebShopping）、Gym Cards（4 个子任务）、ALFWorld（6 个子任务），每个实验使用 3 个随机种子取平均。
  - 额外实验：AitW 上与 DigiRL 对比（ Table 1）；Gym Cards 和 ALFWorld 上与 RL4VLM 对比（ Table 2）。
  - 消融实验：在 WebShopping 和 NumberLine 上比较 RL, RL+Entropy, CoSo（Figure 4）。
  - 探索效率分析：可视化 token 因果权重分布（Figure E.2）、重复动作采样对比（Figure 3、F.1-F.3）。
  - 可视化 counterfactual 结果（Figure E.1）。
- **充分性评价**：实验覆盖了多种任务领域（移动控制、游戏、具身 AI），对比了代表性方法，并提供了消融和可视化分析，比较充分。但训练/测试集划分和超参数设置未详细讨论（部分沿用基线）。结果使用多次随机种子平均，统计可信度好。总体客观、公平。

## 6. 论文的主要结论与发现
- CoSo 显著提升了 VLM 智能体的在线 RL 调优效果：在 AitW 上平均成功率提升 12.3%（达到 72.9%），Gym Cards 提升 9.3%，ALFWorld 提升 16.7%。
- 因果加权探索能有效聚焦关键 token（<10% 的 token 具有高因果权重），减少无效探索（>80% 的 token 权重低于 0.2）。
- CoSo 在恢复错误动作场景中成功采样到正确的纠正动作（如“Home”），而 naive RL 和均匀熵 RL 则失败。
- 理论分析证明了 CoSo 的收敛性和策略改善保证。

## 7. 优点：方法或实验设计上的亮点
- **方法创新**：首次将反事实推理与软 RL 结合，针对性解决 VLM 智能体文本动作空间探索问题，具有通用性（可适配 AWR 或 PPO 等不同 RL 目标）。
- **理论支撑**：给出了策略评估、改善和收敛的完整证明。
- **实验设计**：
  - 使用真实世界的 Android 控制数据和具身 AI 环境，有实际意义。
  - 消融实验清晰展示了因果加权的重要作用。
  - 直观展示了 token 因果权重分布，验证了方法的合理性。
  - 重复采样实验直观对比了几种探索策略的行为差异。
- **轻量级计算增量**：仅用 0.01B 参数的 SCM 和少量额外训练时间。

## 8. 不足与局限
- **应用限制**：实验中最大 utterance 长度小于 300 tokens，未探索超长链式思考（CoT）场景。论文指出这是未来方向。
- **依赖 SCM**：需要额外训练一个 SCM 模型，虽然轻量但增加了实现复杂度。且 SCM 的质量直接影响因果权重的准确性。
- **未讨论超参数敏感性**：如熵系数 α 的设定未给出详细消融。
- **基线不完整**：未与最新的大规模 VLM 智能体方法（如 GPT-4 的 computer use）进行对比，部分基线结果来自原论文而非复现。
- **计算资源**：虽然增量小，但总训练时长仍较长（约 14.5 H100 GPU 小时），对资源有限的研究者可能仍有门槛。

（完）
