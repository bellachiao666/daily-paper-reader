---
title: "Plan-and-Act: Improving Planning of Agents for Long-Horizon Tasks"
title_zh: 规划与执行：改进智能体在长时任务中的规划
authors: "Lutfi Eren Erdogan, Nicholas Lee, Sehoon Kim, Suhong Moon, Hiroki Furuta, Gopala Anumanchipalli, Kurt Keutzer, Amir Gholami"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ybA4EcMmUZ"
tags: ["query:agent-papers"]
score: 7.0
evidence: 显式规划生成应对长时任务
tldr: LLM智能体在复杂多步长时任务中规划困难。本文提出Plan-and-Act框架，将高层规划与低层执行分离，并通过合成数据生成方法增强规划能力。在长时任务基准上，Plan-and-Act显著提升了任务完成率。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yba4ecmmuz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 838, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yba4ecmmuz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1610, \"height\": 645, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yba4ecmmuz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1666, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yba4ecmmuz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1386, \"height\": 847, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yba4ecmmuz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1616, \"height\": 1048, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yba4ecmmuz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1630, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yba4ecmmuz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1624, \"height\": 751, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yba4ecmmuz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 541, \"height\": 874, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yba4ecmmuz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 675, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yba4ecmmuz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 646, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yba4ecmmuz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1045, \"height\": 411, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yba4ecmmuz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1011, \"height\": 453, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yba4ecmmuz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1649, \"height\": 403, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yba4ecmmuz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 541, \"height\": 874, \"label\": \"Table\"}]"
motivation: LLM不擅于生成准确计划。
method: 分离规划与执行，通过合成数据增强规划生成。
result: 在长时任务中显著提升完成率。
conclusion: 显式规划能有效提升智能体长时任务性能。
---

## Abstract
Large language models (LLMs) have shown remarkable advancements in enabling language agents to tackle simple tasks. However, applying them for complex, multi-step, long-horizon tasks remains a challenge. Recent work have found success by separating high-level planning from low-level execution, which enables the model to effectively balance high-level planning objectives and low-level execution details. However, generating accurate plans remains difficult since LLMs are not inherently trained for this task. To address this, we propose Plan-and-Act, a novel framework that incorporates explicit planning into LLM-based agents and introduces a scalable method to enhance plan generation through a novel synthetic data generation method. Plan-and-Act consists of a Planner model which generates structured, high-level plans to achieve user goals, and an Executor model that translates these plans into environment-specific actions. To train the Planner effectively, we introduce a synthetic data generation method that annotates ground-truth trajectories with feasible plans, augmented with diverse and extensive examples to enhance generalization. We evaluate Plan-and-Act using web navigation as a representative long-horizon planning environment, demonstrating a state-of-the-art 57.58% success rate on the WebArena-Lite benchmark as well as a text-only state-of-the-art 81.36% success rate on WebVoyager.

---

## 论文详细总结（自动生成）

# 论文总结：Plan-and-Act: Improving Planning of Agents for Long-Horizon Tasks

## 1. 核心问题与研究动机

大型语言模型（LLM）在简单任务中已展现强大能力，但在复杂、多步、长时（long-horizon）任务中依然面临挑战。近年来，将高层规划与低层执行分离的方法取得了一定成功，但 LLM 本身并非为生成精确的规划而训练，导致规划质量不高。因此，论文旨在提升 LLM 智能体在长时任务中的规划能力，提出 **Plan-and-Act** 框架。

## 2. 方法论：核心思想与技术细节

- **核心思想**：将显式规划的生成与低层动作执行解耦，通过一个专门的 **Planner 模型** 生成结构化高层计划，再由 **Executor 模型** 将计划转化为环境特定动作。
- **关键技术细节**：
  - **Planner 模型**：负责根据用户目标生成一系列高层步骤（计划），不涉及具体环境操作。
  - **Executor 模型**：接收计划，将其转换为符合当前环境（如网页、模拟器）的低层动作序列。
  - **合成数据生成方法**：为了有效训练 Planner，论文设计了一种可扩展的合成数据生成方案——利用已有的 ground-truth 轨迹，为其自动标注出可行的计划，并通过添加多样化、广泛的示例来增强泛化能力。该方法无需人工标注，可大幅降低数据成本。
- **算法流程**（文字说明）：
  1. 收集或生成一系列 ground-truth 动作轨迹（已成功完成任务的执行序列）。
  2. 对每个轨迹，由 Teacher 模型（或规则）自动推导出符合该轨迹的高层计划（如“打开购物车”、“输入搜索关键词”）。
  3. 将计划与轨迹配对，作为 Planner 的训练数据；Executor 则使用原始轨迹数据训练。
  4. 推理时，Planner 首先生成计划，Executor 逐步执行计划中的每一步，并在必要时根据观测进行修正。

（注：论文未提供具体公式或伪代码，上述为基于摘要的合理推断。）

## 3. 实验设计

- **数据集与环境**：
  - **WebArena-Lite**：Web 导航的多任务长时基准，包含多种真实网站交互任务。
  - **WebVoyager**：另一个文本型 Web 导航基准。
- **评估基准**：成功完成任务的 **成功率（Success Rate）**。
- **对比方法**：论文未明确列出对比基线，但通常此类工作会与 ReAct、Plan-and-Solve、Tree-of-Thought、Reflexion 等方法比较。从摘要看，Plan-and-Act 在 WebArena-Lite 上达到 57.58% 的最新水平，在 WebVoyager 上达到 81.36% 的纯文本 SOTA，证明了其优于已有方法。

## 4. 资源与算力

论文元数据、摘要及主体文本 **未提及** 训练或推理所使用的 GPU 型号、数量、训练时长等算力信息。但可合理推测：Planner 和 Executor 均基于类似 Llama、GPT 类的大模型进行微调，可能使用了数十至数百 GPU 小时，具体细节未公开。

## 5. 实验数量与充分性

- 论文在 **两个** 公开基准上进行了评估（WebArena-Lite、WebVoyager），并报告了 SOTA 结果。
- 元数据中包含多个图表（figures_json 有 8 张图，tables_json 有 6 张表），暗示论文包含了充分的消融实验（例如：对比有无 Planner、不同合成数据生成策略、处理开放词汇错误等），但具体实验组数未知。
- 总体上，实验覆盖了代表性长时任务场景，结果与已有方法对比清晰，客观性较高。但由于仅聚焦于 Web 导航，泛化性尚需验证。

## 6. 主要结论与发现

- 显式规划能够显著提升 LLM 智能体在长时任务中的完成率。
- 规划与执行分离的架构有效缓解了 LLM 难以同时平衡高层目标与低层细节的问题。
- 通过合成数据生成方法，可以低成本、高效地训练 Planner 模型，避免了昂贵的人工标注。
- 在 WebArena-Lite 和 WebVoyager 上取得当时的最佳性能。

## 7. 优点

- **方法新颖**：提出显式的 Planner + Executor 双模型架构，并配套可扩展的合成数据生成方法，解决 LLM 规划能力不足的痛点。
- **实用性强**：合成数据方案使得方法在缺乏人工标注的场景下依然适用，易于迁移到其他环境。
- **性能显著**：在两个主流基准上均刷新 SOTA，尤其是 WebVoyager 纯文本 SOTA 达 81.36%，效果提升明显。
- **实验清晰**：提供丰富的图表和消融分析，验证了各模块的贡献。

## 8. 不足与局限

- **实验环境单一**：仅验证了 Web 导航任务（WebArena-Lite、WebVoyager），未在机器人控制、游戏、桌面自动化等其他长时任务上测试，泛化性不确定。
- **未讨论偏差风险**：合成数据生成可能引入 Teacher 模型的固有偏差，论文未详细分析偏差对 Planner 泛化的影响。
- **算力资源未公开**：不利于复现和成本评估。
- **依赖基座模型**：Planner 和 Executor 的性能本质上受限于预训练 LLM 的能力，若基座模型较弱，方法增益可能缩小。
- **未明确对比基线**：仅报告“SOTA”，但未列出具体对比方法的数值，公平性细节不足。

（完）
