---
title: "ReCAP: Recursive Context-Aware Reasoning and Planning for Large Language Model Agents"
title_zh: ReCAP：面向大语言模型智能体的递归上下文感知推理与规划
authors: "Zhenyu Zhang, Tianyi Chen, Weiran Xu, Alex Pentland, Jiaxin Pei"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=r2ykUnzuGt"
tags: ["query:agent-papers"]
score: 9.0
evidence: 递归上下文感知推理与规划框架，用于LLM智能体的长程任务
tldr: 现有LLM在长程多步任务中常因上下文漂移和递归失败而表现不佳。本文提出ReCAP，一种递归上下文感知推理与规划框架，通过计划分解、父计划结构化重注入以及自适应重提示机制，有效维持多级连续性和目标一致性。实验显示，ReCAP在多个长程推理基准上显著优于顺序提示和层次提示方法，为构建递归自改进智能体提供了关键技术。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-r2ykunzugt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1273, \"height\": 191, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r2ykunzugt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1349, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r2ykunzugt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1362, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r2ykunzugt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 674, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r2ykunzugt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 692, \"height\": 572, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r2ykunzugt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1418, \"height\": 1010, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r2ykunzugt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 688, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r2ykunzugt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1115, \"height\": 1027, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r2ykunzugt/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1113, \"height\": 975, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-r2ykunzugt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1162, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-r2ykunzugt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1405, \"height\": 196, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-r2ykunzugt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1312, \"height\": 157, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-r2ykunzugt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1115, \"height\": 1027, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-r2ykunzugt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1113, \"height\": 975, \"label\": \"Table\"}]"
motivation: 长程任务中顺序提示方法易导致上下文漂移和递归失败，层次提示方法则牺牲连续性或增加开销。
method: 提出ReCAP递归层次框架，包含计划分解、父计划重注入和自适应重提示三个机制。
result: 在多个长程推理基准上，ReCAP显著优于现有方法，保持目标一致性和推理连续性。
conclusion: 递归上下文感知框架是提升LLM智能体长程任务规划能力的有效途径。
---

## Abstract
Long-horizon tasks requiring multi-step reasoning and dynamic re-planning remain challenging for large language models (LLMs). Sequential prompting methods are prone to context drift, loss of goal information, and recurrent failure cycles, while hierarchical prompting methods often weaken cross-level continuity or incur substantial runtime overhead. We introduce ReCAP (Recursive Context-Aware Reasoning and Planning), a hierarchical framework with shared context for reasoning and planning in LLMs. ReCAP combines three key mechanisms: (i) plan-ahead decomposition, in which the model generates a full subtask list, executes the first item, and refines the remainder; (ii) structured re-injection of parent plans, maintaining consistent multi-level context during recursive return; and (iii) memory-efficient execution, bounding the active prompt so costs scale linearly with task depth. Together these mechanisms align high-level goals with low-level actions, reduce redundant prompting, and preserve coherent context updates across recursion. Experiments demonstrate that ReCAP substantially improves subgoal alignment and success rates on various long-horizon reasoning benchmarks, achieving a 32\% gain on synchronous Robotouille and a 29\% improvement on asynchronous Robotouille under the strict pass@1 protocol.

---

## 论文详细总结（自动生成）

# 中文总结：ReCAP 论文

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：大语言模型（LLMs）在长程任务（long-horizon tasks）中面临多步推理和动态重规划的挑战。顺序提示方法（如 ReAct、Reflexion）容易导致上下文漂移（context drift）、目标信息丢失和递归失败循环；层次提示方法（如 THREAD、ADaPT）则可能削弱跨层连续性或引入大量运行时开销。
- **背景**：真实世界任务（如组织旅行、烹饪）需要全局意图保持和不同细节层级间的连贯性，同时能根据反馈灵活调整。现有 LLM 方法难以兼顾这些要求。
- **整体含义**：本文提出一种递归上下文感知推理与规划框架 ReCAP，旨在通过共享上下文、结构化注入和高效内存使用，使 LLM 智能体在长程任务中保持目标一致性和多级推理连贯性，避免漂移和重复失败。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：ReCAP 是一个递归层次框架，所有递归深度在一个共享的 LLM 上下文（context）中运行，通过“计划分解-执行-回退细化”的循环动态推进任务。
- **关键技术细节**：
  - **计划分解（plan-ahead decomposition）**：模型一次性生成一个有序的子任务列表 S = ⟨s0, s1, ..., sm−1⟩，仅执行第一个子任务 s0，其余部分 s[1:] 保留以备后续细化。这避免了逐个生成导致的漂移。
  - **父计划结构化重注入**：当从子目标返回（回溯）时，父节点的计划（最新思考 T 和剩余子任务 s[1:]）被重新注入到当前共享上下文 C 中，确保多级上下文连贯性。递归调用前附加父计划 ⟨T, S, S[0]⟩，回溯后附加 ⟨T, S[1:]⟩。
  - **内存高效执行**：通过滑动窗口（K=64 轮对话）限制活跃 prompt 大小，老回合自动移除。关键规划信息通过结构化注入重新引入，因此截断不会丢失高层结构。外部状态存储规模为 O(d·L̅)，d 为树深度，L̅ 为平均每轮 token 数。
- **算法流程**（文字说明）：
  1. 输入任务描述 D 和初始观察 O_init，初始化上下文 C。
  2. 调用规划函数 π(C)，生成思考 T 和子任务列表 S。
  3. 循环直到 S 为空：
     - 若 S[0] 是原始动作，执行环境动作 E(S[0])，得到观察 O，追加到 C。
     - 若 S[0] 是复合任务，递归调用 ReCAP(C ∥ ⟨T, S, S[0]⟩)，完成后向上回溯。
     - 回溯后，重新注入父计划 ⟨T, S[1:]⟩，并调用细化函数 ρ(C) 更新思考和新子任务列表。
  4. 返回最终上下文 C（表示任务完成）。

## 3. 实验设计
- **数据集/场景**：四个基准。
  - **ALFWorld**：符号化家庭环境，短程任务（5-15步），评估在浅层推理下的效果。
  - **Robotouille**：长程烹饪环境，分同步（10-57步）和异步（21-82步）两种模式，子任务需多步骤完成，有资源竞争。
  - **FEVER**：知识密集型事实验证，短程工具调用（≤10步），使用 Search/Lookup/Finish 动作。
  - **SWE-bench Verified**：仓库级代码修复，动作空间无界，任务步数45-257。
- **对比方法**：
  - 顺序提示基线：Standard、CoT、ReAct、Act（仅动作）。
  - 层次提示基线：ADaPT（仅在 Robotouille 上比较）。
  - 排除的基线：THREAD、Reflexion、Ada-Planner、REPL-Plan（因与 pass@1 协议不兼容或工具链不匹配）。
- **评估设置**：严格 pass@1（一次推理-执行轨迹，无重试、无自一致性），one-shot 提示，使用 GPT-4o（2024-08-06）作为主模型，部分实验使用其他模型（Qwen2.5-32B/72B、LLaMA-4、DeepSeek-V3）。

## 4. 资源与算力
- 论文**未明确说明**使用的 GPU 型号、数量或训练时长。所有实验通过商业 API 调用进行，无本地训练或微调。
- 给出了成本估计：
  - Robotouille 任务 synchronous/6 平均每完成一次运行花费 7.77 USD（标准差 3.45），平均 LLM 调用 74.95 次。
  - ALFWorld 全部 134 个任务总成本：ReAct 为 37.89 USD，ReCAP 为 118.40 USD（约三倍，主要因额外推理轨迹和分解步骤）。
  - SWE-bench 未提供详细成本，但提及 500 个任务全部成功提交，其中 498 个成功评估，224 个解决。可推测 API 开销较大。

## 5. 实验数量与充分性
- **实验数量**：
  - Robotouille：10 个同步食谱 + 10 个异步食谱，各 10 个实例（共 200 次运行）。
  - ALFWorld：206 个官方 unseen 任务？实际测试 134 个任务（原文 3.1 节提及“134 tasks”）。
  - FEVER：随机采样 200 个 claims。
  - SWE-bench Verified：500 个任务全部运行。
  - 不同模型比较：在 Robotouille 的三个代表性任务上比较了 5 种模型（GPT-4o、Qwen2.5-32B/72B、LLaMA-4、DeepSeek-V3）。
  - 消融实验：在 Robotouille 的 synchronous/6 任务上测试了多种结构变体（不同递归深度、移除思考、仅子任务名称、传递所有历史等）以及上下文长度变体，并报告了 p 值。
- **充分性与客观性**：
  - 实验覆盖了多种任务类型（短期、长期、同步、异步、知识推理、代码修复），对比了多个强基线。
  - 采用 pass@1 和 one-shot 严格设置，公平性较好。
  - 但部分实验（如不同模型比较）只用了 3 个任务（共 30 次运行），样本量有限；消融实验只在一个任务上进行，可能不够普遍化。
  - 成本限制可能导致部分实验无法完全重复，但实验设计整体较为充分。

## 6. 主要结论与发现
- ReCAP 在长程任务上显著优于所有基线：
  - Robotouille 同步：ReCAP 70% vs ReAct 38%，提升 32%。
  - Robotouille 异步：ReCAP 53% vs ReAct 24%，提升 29%。
  - ALFWorld：ReCAP 91% vs ReAct 84%，提升 7%（但 ReAct 使用 GPT-3.5，ADaPT 使用 GPT-3.5，ReCAP 使用 GPT-4o，部分提升可能来自模型差异）。
  - FEVER：ReCAP 63.5% vs ReAct 63.5%，持平。
  - SWE-bench Verified：ReCAP 44.8% vs ReAct 39.58%（GPT-4.1），提升 5.2%。
- 在多个模型（Qwen2.5、LLaMA-4、DeepSeek-V3）上，ReCAP 一致优于 ReAct，证明框架的鲁棒性。
- 消融实验表明：推理轨迹（think）和足够的递归深度（至少 4 层）对性能至关重要；移除思考或限制深度会显著降低成功率；提供过多或过少历史对性能影响较小。
- 结论：上下文如何组织和注入与上下文长度同样重要。

## 7. 优点
- **方法创新性**：结合计划分解、结构化注入和滑动窗口，在单一共享上下文中实现递归，避免了传统递归方法的上下文碎片化和开销。
- **实验设计严格**：采用 pass@1 单次轨迹评估，无重试或 ensembling，更接近真实部署场景。
- **广泛验证**：覆盖从短期到长期、从符号化到代码修复的多种任务，并在多个 LLM 上验证。
- **消融深入**：分析了机制各部分的贡献，如深度、思考轨迹对性能的影响，为理解框架提供了依据。
- **无需训练或微调**，直接通过提示工程驱动，易于应用于现有模型。

## 8. 不足与局限
- **依赖模型质量**：所有分解、执行和回溯决策完全依赖底层 LLM，无外部验证或 grounding，错误可能传播。
- **开销增加**：递归设计导致交互轨迹变长，API 调用次数和成本显著增加（ALFWorld 成本约 3 倍），在效率敏感场景中受限。
- **部分实验限制**：不同模型比较仅使用 3 个 Robotouille 任务，样本量较小；消融实验只在一个任务上进行，泛化性存疑。
- **短任务提升有限**：在 FEVER 上性能持平，说明递归结构对浅层任务未必有优势。
- **SWE-bench 实现妥协**：由于工具调用优先于子任务分解，实际树结构与实体任务类似，计划分解没有完全发挥优势。
- **公平性争议**：ALFWorld 上 ReCAP 使用较新模型 GPT-4o，而 ReAct 和 ADaPT 使用 GPT-3.5，部分增益可能来自模型差异。作者对此有说明。
- **未报告误差范围**：虽然提及 p 值，但主表未给出标准差或置信区间，难以评估稳定性。

（完）
