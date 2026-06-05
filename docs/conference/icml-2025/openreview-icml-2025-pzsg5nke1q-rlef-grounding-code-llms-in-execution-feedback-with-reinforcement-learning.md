---
title: "RLEF: Grounding Code LLMs in Execution Feedback with Reinforcement Learning"
title_zh: RLEF：用强化学习将代码LLM锚定于执行反馈
authors: "Jonas Gehring, Kunhao Zheng, Jade Copet, Vegard Mella, Taco Cohen, Gabriel Synnaeve"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=PzSG5nKe1q"
tags: ["query:agent-papers"]
score: 8.0
evidence: 基于强化学习的代码生成智能体自我改进，利用执行反馈
tldr: 代码LLM作为智能体时需要利用反馈自我改进，但现有方法迭代改进困难。本文提出RLEF，一种端到端强化学习方法，教导模型利用执行反馈迭代优化代码。在竞赛编程任务上，8B和70B模型均取得大幅性能提升，采样量减少一个数量级。该方法为智能体通过RL自我改进提供了有效范式。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-pzsg5nke1q/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 837, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pzsg5nke1q/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1426, \"height\": 818, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pzsg5nke1q/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1776, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pzsg5nke1q/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 871, \"height\": 1475, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-pzsg5nke1q/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1477, \"height\": 922, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pzsg5nke1q/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 858, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pzsg5nke1q/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 772, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pzsg5nke1q/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 796, \"height\": 388, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pzsg5nke1q/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1731, \"height\": 614, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pzsg5nke1q/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 617, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pzsg5nke1q/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 695, \"height\": 340, \"label\": \"Table\"}]"
motivation: 代码LLM智能体在迭代改进中难以有效利用执行反馈进行自我优化。
method: 提出端到端强化学习方法RLEF，利用执行反馈信号训练模型迭代改进代码。
result: 在竞赛编程任务上，8B和70B模型性能大幅提升，采样量减少一个数量级。
conclusion: RL结合执行反馈可有效实现代码智能体的自我改进。
---

## Abstract
Large language models (LLMs) deployed as agents solve user-specified tasks over multiple steps while keeping the required manual engagement to a minimum. Crucially, such LLMs need to ground their generations in any feedback obtained to reliably achieve the desired outcomes. We propose an end-to-end reinforcement learning method for teaching models to leverage execution feedback in the realm of code synthesis, where state-of-the-art LLMs struggle to improve code iteratively compared to independent sampling. We benchmark on competitive programming tasks and achieve large performance gains with both small (8B parameters) and large (70B) models, outperforming previous work while reducing the number of samples required by an order of magnitude. Our analysis of inference-time behavior demonstrates that our method produces LLMs that effectively leverage automatic feedback over multiple steps.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：代码生成大型语言模型（LLMs）在作为智能体进行多步任务时，需要利用执行反馈来迭代改进生成结果。然而现有 LLMs（如 GPT-4、Llama 3.1）在代码合成任务中，使用执行反馈的多轮迭代生成相对于独立采样并没有明显优势，甚至性能下降。
- **研究背景**：LLMs 部署为智能体时，需具备两种技能：（1）准确推断用户意图（通过指令微调实现）；（2）根据中间反馈（如代码执行错误、运行超时等）调整后续动作。当前代码生成领域，利用执行反馈进行自我修复的效果有限，且计算效率低下。本文旨在通过强化学习端到端训练模型，使其学会在推理时自动利用执行反馈进行迭代改进，从而提升代码合成的可靠性和样本效率。

## 2. 方法论

- **核心思想**：将代码生成建模为部分可观测马尔可夫决策过程（POMDP），模型作为策略，通过多轮对话与执行环境交互。每轮模型生成一个代码解决方案，然后执行该代码对公共测试集（public tests）获取反馈（如错误信息、超时等），并将反馈作为下一轮对话的上下文。当公共测试全部通过或达到最大轮次时，使用隐藏的私有测试集（private tests）给出最终二元奖励（通过得+1，失败得-1）。使用近端策略优化（PPO）最大化该奖励，同时加入 KL 散度惩罚以保持与初始模型的分布接近，并对无效代码生成施加小惩罚（-0.2）。
- **关键技术细节**：
  - **奖励函数**：\( R(s_t, a_t) = r(s_t, a_t) - \beta \log \frac{\pi(a_t|c_t)}{\rho(a_t|c_t)} \)，其中 \( r \) 为任务奖励（+1 全部通过，-1 任何失败，-0.2 无效代码），\( \beta \) 为 KL 惩罚系数（设为 0.05）。
  - **值函数**：采用回合级（turn-level）价值估计，即对每个完整响应预测一个值，而非每个 token，此混合方法经实验优于纯 token 级或纯回合级。
  - **KL 惩罚中的概率计算**：使用几何平均而非乘积，以避免对较短生成的不公平偏置。
  - **训练流程**：在线异步框架，推理和优化解耦，使用重要性采样和 PPO 裁剪（clip=0.2），每 1024 次 rollout 后做 4 次更新，每 800 步评估一次模型。
- **算法流程**（文字描述）：
  1. 初始观察 \( o_0 \) 为问题描述。
  2. 模型生成响应 \( a_0 \)（代码），执行公共测试获得反馈 \( o_1 \)。
  3. 若公共测试未全通过且未达到最大轮次，将反馈拼接进对话，模型生成新响应 \( a_1 \)，重复直到公共测试通过或达到轮次限制。
  4. 最终解决方案提交至私有测试，获得奖励信号。使用 PPO 更新策略和值函数。

## 3. 实验设计

- **数据集/场景**：
  - 主要基准：**CodeContests**（Li et al., 2022），包含训练集（13,328 题，去除 669 个缺失测试的题目）、验证集（117 题）、测试集（165 题），问题难度高，需算法、数据结构及运行时效率。
  - 泛化基准：**HumanEval+** 和 **MBPP+**（Liu et al., 2023a），修改为类似的多轮迭代设置，使用基础测试作为执行反馈，“plus”测试作为最终正确性评估。还附加了 **LiveCodeBench**（截止 2024 年 10 月）。
- **对比方法**：
  - 先前工作：AlphaCode（9B/41B）、Code Llama 34B + PPO、AlphaCodium（GPT-3.5/4）、MapCoder（GPT-3.5/4）。
  - 自身基线：Llama 3.0/3.1 Instruct 8B 和 70B 的初始版本（单轮和多轮）。
  - 消融：与单轮强化学习训练（ST）、监督微调（SFT）、少样本提示、随机反馈、无反馈、token 级值函数、单独修复模型等的对比。
- **评估指标**：n@k 平均解决率（solve rate）。对于多轮，每轮计为一个样本，确保与独立采样的公平比较。

## 4. 资源与算力

- 训练使用 **Nvidia H100 GPU**。
- 8B 模型：共 **288 块 GPU**（其中 128 块用于训练，160 块用于推理）。
- 70B 模型：共 **2304 块 GPU**（其中 1024 块用于训练，1280 块用于推理）。
- 训练时长：约 **20 个墙钟小时**（wall time hours）。
- 优化器：AdamW，学习率 2e-7，权重衰减 0.1，线性预热 50 步。

## 5. 实验数量与充分性

- **主要实验**：在 CodeContests 验证集和测试集上报告 1@3 和 10@100 解决率，每个结果基于 200 次 rollout 并采用 95% 置信区间（通过重采样 200 次得到）。
- **泛化实验**：在 HumanEval+、MBPP+、LiveCodeBench 上报告 1@3 结果，每次 20 次 rollout，同样包含置信区间。
- **消融实验**：包括以下多个维度：
  - 多轮 vs. 单轮训练（表 4）
  - 不同训练方法比较：RLEF、SFT、少样本提示（表 3）
  - 随机执行反馈（图 3、图 4a）
  - 不同轮次限制下的 pass@1 和 pass@10（图 4a、4b）
  - 无公共测试反馈（附录 B.5）
  - token 级值函数（附录 B.6）
  - 单独修复模型（附录 B.4）
  - 私有测试反馈（附录 B.3）
  - 基座模型 vs. 指令模型（附录 B.2）
- **充分性评价**：实验设计较为全面，覆盖了多种基线、多个数据集、多种消融条件，统计显著性通过置信区间体现。但 CodeContests 的泛化性可能有限（竞赛编程领域），其他基准（HumanEval+ 等）规模较小。

## 6. 主要结论与发现

- **性能提升显著**：RLEF 训练后，Llama 3.1 8B 和 70B 在 CodeContests 上解决率大幅提高。70B 模型以 3 个样本（1@3）超越 AlphaCodium（GPT-4）用 100 个样本的结果（测试集 40.1 vs. 29），样本效率提升一个数量级。
- **多轮迭代能力增强**：初始模型在多轮设置下性能不稳定（甚至下降），而 RLEF 模型能有效利用执行反馈，错误修复率显著提高（图 3）。
- **泛化能力**：在 HumanEval+、MBPP+、LiveCodeBench 上，多轮 RLEF 模型也优于初始模型，表明训练学到的能力可迁移至不同格式和难度的任务。
- **反馈敏感性**：随机反馈实验表明，RLEF 模型对真实反馈有明确依赖，随机反馈下 pass@1 大幅下降，但 pass@10 下降较小，说明模型会转向多样化采样策略。
- **最佳轮次**：在固定样本预算下，使用 5 轮比 1 轮或 10 轮表现更优（图 4b）。

## 7. 优点

- **端到端强化学习**：无需单独的修复模型或复杂的手工提示工程，单个模型同时学习代码生成和修复。
- **通用性**：方法不依赖特定领域知识，可迁移至不同代码生成基准，表明其广泛适用性。
- **样本效率高**：显著减少推理时需要生成的样本数量，降低计算成本。
- **深入的行为分析**：通过错误类型统计、代码相似度（chrF）、随机反馈消融等揭示了模型能力提升的来源（更好的初始解、更高的多样性、目标导向的修复）。
- **与主流模型兼容**：适用于 Llama 3.0/3.1 系列，并能进一步提升已具备较强代码能力的指令微调模型。

## 8. 不足与局限

- **任务范围有限**：当前只考虑在单个问题内迭代改进单一解决方案，未推广到需任务分解的更大规模环境（如软件工程级代码生成）。
- **依赖测试用例**：执行反馈需要公共测试集，实际场景中可能缺失。作者提出可结合自动单元测试生成，但未实验验证。
- **计算资源要求高**：训练 70B 模型需要 2304 块 H100 GPU，成本较高。
- **缺乏与其他 RL 方法的公平对比**：未与 SCoRe 等最新并发方法进行直接比较，仅在表中提及。
- **泛化验证范围有限**：主要在竞赛编程领域测试，HumanEval/MBPP 题目难度较低且数量少，对更复杂任务（如 SWE-bench）的迁移效果未知。
- **未探讨奖励函数设计的优化空间**：使用简单二元奖励，可能无法提供细粒度信号，文中也未尝试其他奖励设计。

（完）
