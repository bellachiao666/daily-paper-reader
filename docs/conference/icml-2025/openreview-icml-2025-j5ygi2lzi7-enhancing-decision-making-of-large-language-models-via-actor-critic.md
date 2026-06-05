---
title: Enhancing Decision-Making of Large Language Models via Actor-Critic
title_zh: 通过Actor-Critic增强大语言模型的决策能力
authors: "Heng Dong, Kefei Duan, Chongjie Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=J5YGi2LzI7"
tags: ["query:agent-papers"]
score: 7.0
evidence: 基于Actor-Critic的LLM决策增强强化学习框架
tldr: 本文针对大语言模型在复杂决策中缺乏长期规划的问题，提出LAC框架，通过Actor-Critic结构计算基于token logits的Q值，提供长期动作评估。该方法在不增加大规模数据条件下有效提升了LLM的决策质量，在多个推理和决策任务上取得显著改进，为将强化学习引入LLM自改进提供了可扩展的方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-j5ygi2lzi7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 820, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j5ygi2lzi7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1761, \"height\": 725, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j5ygi2lzi7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1763, \"height\": 715, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j5ygi2lzi7/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1761, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j5ygi2lzi7/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1601, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j5ygi2lzi7/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1760, \"height\": 2230, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j5ygi2lzi7/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1763, \"height\": 728, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j5ygi2lzi7/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1764, \"height\": 602, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j5ygi2lzi7/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1759, \"height\": 660, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j5ygi2lzi7/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1740, \"height\": 1047, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j5ygi2lzi7/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1118, \"height\": 1109, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j5ygi2lzi7/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 615, \"height\": 1125, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j5ygi2lzi7/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1761, \"height\": 540, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1642, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1662, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1281, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1275, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1287, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1282, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1108, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1107, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1253, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1289, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1279, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1144, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 935, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1607, \"height\": 374, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1614, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1536, \"height\": 494, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1588, \"height\": 749, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1599, \"height\": 802, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j5ygi2lzi7/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1109, \"height\": 189, \"label\": \"Table\"}]"
motivation: LLM在需要长期推理和高级目标对齐的决策场景中表现不佳。
method: 提出LLM-Actor-Critic框架，利用token logits估计Q值指导动作改进。
result: 在多个复杂决策任务上，LAC优于已有方法，提升了长期决策的准确性。
conclusion: 该工作展示了Actor-Critic框架有效增强LLM的长期决策能力，具有良好可扩展性。
---

## Abstract
Large Language Models (LLMs) have achieved remarkable advancements in natural language processing tasks, yet they encounter challenges in complex decision-making scenarios that require long-term reasoning and alignment with high-level objectives. Existing methods either rely on short-term auto-regressive action generation or face limitations in accurately simulating rollouts and assessing outcomes, leading to sub-optimal decisions. This paper introduces a novel LLM-based Actor-Critic framework, termed LAC, that effectively improves LLM policies with long-term action evaluations in a principled and scalable way. Our approach addresses two key challenges: (1) extracting robust action evaluations by computing Q-values via token logits associated with positive/negative outcomes, enhanced by future trajectory rollouts and reasoning; and (2) enabling efficient policy improvement through a gradient-free mechanism. Experiments across diverse environments -- including high-level decision-making (ALFWorld), low-level action spaces (BabyAI-Text), and large action spaces (WebShop) -- demonstrate the framework’s generality and superiority over state-of-the-art methods. Notably, our approach achieves competitive performance using 7B/8B parameter LLMs, even outperforming baseline methods employing GPT-4 in complex tasks. These results underscore the potential of integrating structured policy optimization with LLMs’ intrinsic knowledge to advance decision-making capabilities in multi-step environments.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：大语言模型（LLM）在自然语言处理任务中表现出色，但在需要长期推理和与高层次目标对齐的复杂决策场景中面临挑战。现有方法要么依赖短期的自回归动作生成（缺乏长期规划），要么依赖模拟 rollout 并评估结果（但模拟可能偏离现实，评估不准确），导致次优决策。
- **整体含义**：本文提出了一种新颖的 LLM 基础 Actor-Critic 框架（LAC），以原则性和可扩展的方式，利用长期动作评估来改进 LLM 策略。核心目标是有效整合 LLM 先验知识中的决策信息与融入长期规划的鲁棒动作评估中的洞察，提升多步环境中的决策能力。

## 2. 方法论

- **核心思想**：LAC 将 LLM 同时用作 Actor（策略生成）和 Critic（动作价值评估）。Actor 基于 LLM 先验策略 πLLM 生成候选动作；Critic QLLM 通过对每个候选动作进行未来轨迹 rollout 和推理，计算 Q 值以评估长期价值。然后通过梯度自由的 KL 约束优化，更新动作分布，实现策略改进。
- **关键技术细节**：
  - **Critic 构建**：将 QLLM 与任务成功概率连接，使用逻辑斯蒂函数：`P(success) = 1/(1+exp(-Q))`。通过 LLM 输出中代表正负意义的 token（如“GOOD”/“BAD”）的对数概率计算 Q 值：`Q = log(P(yw)/P(yl))`。为提高准确性，对每个候选动作进行未来轨迹 rollout（使用 LLM 作为前向世界模型），并结合反思（reflection）提供简短判断。
  - **梯度自由策略优化**：将策略改进问题建模为 KL 散度约束优化：`max E[Q] - (1/α) KL(π || πLLM)`。推导出闭式解：`πnew(ai) ∝ πLLM(ai) exp(α Q(ai))`。通过调节 α 平衡先验和评估的贡献，直接取新分布中概率最大的动作。该方法避免了梯度更新带来的高计算开销。
- **算法流程**：在每个时间步，从 πLLM 采样 n 个候选动作，对每个动作利用 fLLM 预测未来轨迹，计算 QLLM，然后按公式更新分布，选取概率最大的动作执行。

## 3. 实验设计

- **数据集/场景**：三个覆盖不同动作空间的基准环境：
  - **ALFWorld**：高层动作空间（134 个评估任务），稀疏二元奖励（成功=1，失败=0），要求完成家庭任务。
  - **BabyAI-Text**：低层动作空间（每个任务类型 50 个任务，共 300 个任务），栅格世界，6 个原始动作，稀疏二元奖励。
  - **WebShop**：潜在无限动作空间（100 个任务），连续奖励（0-1），要求根据指令购买产品。
- **对比方法**：ReAct、RAP、ICPI、RAFA、LATS 等基于 LLM 的决策方法，部分任务中还对比了 GPT-4+ReAct、GPT-4-turbo+ReAct 等强基线。
- **基座模型**：CodeLlama-7B、Mistral-7B、Gemma-7B、Llama-3-8B 等开源 LLM（部分扩展实验使用 Llama-3.1-8B、DeepSeek-R1 等）。

## 4. 资源与算力

- **训练**：使用 LoRA 微调，数据量为每个基准约 400-500 个 (输入,输出) 对，微调 1000 步，学习率 2.5e-5，batch size 2，在一张 A100 GPU（80GB 显存）上 1.5 小时内完成。
- **推理/测试**：使用相同 A100 GPU，ALFWorld 134 个任务约 10 小时，BabyAI-Text 每个任务类型 50 个任务 4-10 小时，WebShop 100 个任务 3-4 小时。GPU 显存占用根据输入长度在 15GB 到大于 70GB 之间变化。
- **说明**：文中明确提供了 GPU 型号、数量（单卡）、训练时长等细节。

## 5. 实验数量与充分性

- **实验数量**：在三个基准上进行了全面比较，包含多种基座模型和多种基线方法。消融实验包括：LAC w/o critic、LAC w/o rollout、LAC w/o reflection、critic-only 等。还进行了超参数 α 的网格搜索、不同 Q 值定义比较、微调数据量影响、正负样本比例影响、计算成本分析、统计相关性分析等。
- **充分性与公平性**：实验覆盖高层/低层/无限动作空间，使用相同基座模型公平比较。温度设为 0 保证确定性，无误差条。结果以成功率和奖励（WebShop）报告。论文认为实验充分且客观，但部分实验（如 Crafter 仅初步）未在主要基准中深入。

## 6. 主要结论与发现

- LAC 在所有三个基准上持续优于所有对比基线，甚至在使用 7B/8B 模型时超过 GPT-4+ReAct 在复杂任务上的表现。
- 消融实验表明每个组件（critic、rollout、reflection）均对性能有贡献，去除后性能下降。
- 统计检验显示 LAC 的 Q 值能够反映任务进度（与时间步正相关于成功轨迹，负相关于失败轨迹）。
- 梯度自由策略改进能够自动平衡先验策略和 critic 的置信度，当两者冲突时倾向于更可信的决策源。
- 方法对超参数 α 和数据比例具有鲁棒性；微调可提升性能，但即使无微调也优于基线。

## 7. 优点

- **方法论创新**：提出利用 LLM 内部 token logits 计算 Q 值，避免直接提示的不稳定性；梯度自由策略优化避免了 LLM 微调的高成本，实现高效改进。
- **通用性与可扩展性**：适用于高层、低层、无限动作空间多种决策环境，且可适配多种开源 LLM。
- **计算效率**：虽然每步额外估算 Q 值，但由于成功率提高导致总步数减少，总体 token 开销和时间成本低于多数基于树的搜索方法（如 RAP、LATS）。
- **理论基础**：KL 约束优化推导给出闭式解，提供平衡先验和评估的理论保证。
- **实验全面**：多基准、多模型、多消融、多分析，验证了方法的鲁棒性和有效性。

## 8. 不足与局限

- **反思时机限制**：反思仅在动作生成前使用，未在动作生成后应用于重新采样候选动作，若所有候选动作均失败，缺乏补救机制。
- **树搜索扩展不足**：当前仅对每个候选动作展开一个节点进行 rollout，若采用更复杂的树搜索（如 MCTS）可能进一步提升评估准确性。
- **连续奖励适应性**：方法本质上设计用于二元结果（成功/失败），尽管在 WebShop（连续奖励）上经验有效，但缺乏原理性处理连续奖励的公式，未来方向需更严谨。
- **大规模模型效果未充分验证**：虽然使用 7B/8B 模型效果优异，但更大模型（如 70B 或 175B）的适用性和效果未在主要实验中深入探索（仅初步尝试 DeepSeek-R1 因“过度思考”问题不适用）。
- **潜在偏差风险**：依赖 LLM 内部 token logits，可能继承 LLM 的偏见或对特定 token 的偏好（如“GOOD”/“BAD”）；反思内容可能受训练数据质量影响。
- **部分环境局限性**：LATS 不适用于 ALFWorld 和 BabyAI-Text 因环境不可逆，导致对比不完整；Crafter 实验仅为初步结果，未充分展开。

（完）
