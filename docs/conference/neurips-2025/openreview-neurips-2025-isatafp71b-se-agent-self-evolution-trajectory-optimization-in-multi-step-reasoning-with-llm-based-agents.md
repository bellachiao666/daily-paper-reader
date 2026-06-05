---
title: "SE-Agent: Self-Evolution Trajectory Optimization in Multi-Step Reasoning with LLM-Based Agents"
title_zh: SE-Agent：基于LLM智能体多步推理的自进化轨迹优化
authors: "Yifu Guo, Jiaye Lin, Huacan Wang, Yuzhen Han, Sen Hu, Ziyi Ni, Licheng Wang, Mingguang Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=isATAFP71B"
tags: ["query:agent-papers"]
score: 9.0
evidence: 基于LLM智能体的自进化轨迹优化
tldr: 本文针对LLM智能体多步推理中轨迹未充分利用的问题，提出SE-Agent自进化轨迹优化方法。该方法通过考虑轨迹间的相互依赖关系，利用轨迹反馈引导智能体正确方向，避免冗余搜索。实验表明该方法在复杂推理任务上显著提升性能。此工作为构建自进化智能体提供了新范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-isatafp71b/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1463, \"height\": 787, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isatafp71b/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 738, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isatafp71b/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1216, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isatafp71b/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1272, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isatafp71b/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 541, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isatafp71b/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1451, \"height\": 522, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isatafp71b/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1419, \"height\": 1210, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isatafp71b/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1432, \"height\": 1223, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-isatafp71b/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1464, \"height\": 496, \"label\": \"Table\"}]"
motivation: 现有方法忽略轨迹间依赖且搜索空间缺乏多样性，导致推理冗余。
method: 提出自进化轨迹优化框架，利用轨迹间反馈动态引导智能体。
result: 在多个推理基准上超越现有方法，提升任务完成准确率。
conclusion: SE-Agent有效利用轨迹依赖实现智能体自进化。
---

## Abstract
Large Language Model (LLM)-based agents have recently shown impressive capabilities in complex reasoning and tool use via multi-step interactions with their environments. While these agents have the potential to tackle complicated tasks, their problem-solving process—agents' interaction trajectory leading to task completion—remains underexploited. These trajectories contain rich feedback that can navigate agents toward the right directions for solving problems correctly. Although prevailing approaches, such as Monte Carlo Tree Search (MCTS), can effectively balance exploration and exploitation, they ignore the interdependence among various trajectories and lack the diversity of search spaces, which leads to redundant reasoning and suboptimal outcomes. To address these challenges, we propose SE-Agent, a Self-Evolution framework that enables Agents to optimize their reasoning processes iteratively. Our approach revisits and enhances former pilot trajectories through three key operations: revision, recombination, and refinement. This evolutionary mechanism enables two critical advantages: (1) it expands the search space beyond local optima by intelligently exploring diverse solution paths guided by previous trajectories, and (2) it leverages cross-trajectory inspiration to efficiently enhance performance while mitigating the impact of suboptimal reasoning paths. Through these mechanisms, SE-Agent achieves continuous self-evolution that incrementally improves reasoning quality. We evaluate SE-Agent on SWE-bench Verified to resolve real-world GitHub issues. Experimental results across five strong LLMs show that integrating SE-Agent delivers up to 55% relative improvement, achieving state-of-the-art performance among all open-source agents on SWE-bench Verified.

---

## 论文详细总结（自动生成）

# SE-Agent 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题背景**：基于大语言模型（LLM）的智能体通过多步交互解决复杂任务时，会产生大量交互轨迹（trajectory），这些轨迹编码了问题解决过程中的状态、动作、反馈和决策。然而，现有方法（如蒙特卡洛树搜索 MCTS）虽然能平衡探索与利用，但**忽略不同轨迹之间的相互依赖关系**，且**搜索空间缺乏多样性**，导致推理冗余和次优结果。
- **核心挑战**：
  - 轨迹被视为独立实体，无法利用跨轨迹的协同效应。
  - 即使采用多样采样（如不同温度/提示），智能体生成的轨迹在结构上仍趋于同质化，最终结果高度相似。
  - 概率语言模型天然倾向于高概率解模式，限制了搜索空间多样性。
- **研究目标**：提出一种**自进化（Self-Evolution）框架**，通过在轨迹层面进行主动干预（而非仅调整采样参数），引导智能体探索根本不同的视角和求解路径，从而扩大候选解空间，提升多步推理质量。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- **SE-Agent**：一种迭代式自进化框架，通过三种核心操作（修订、重组、精炼）在轨迹层面进行操作，利用已有轨迹的集体智慧超越孤立推理的局限。
- **类比遗传算法**：轨迹作为基因型，问题解决性能作为表型表达；但与遗传算法不同，SE-Agent 仅需少量进化循环即可达到高质量结果。
- **类比自我对弈/专家迭代**：但与 RL 方法不同，SE-Agent 显式操作完整推理轨迹，而非孤立的状态-动作对。

### 关键技术细节

1. **初始轨迹池生成**：
   - **多规划探索**：通过变化规划策略、提示技术、推理方法生成多个轨迹（5个不同规划策略）。
   - **基于突变的多样化**：对已有轨迹施加受控突变，额外产生 M 条路径，引入推理步骤、动作选择或中间结论的变化。
   - 初始池包含约 10 条轨迹。

2. **三种核心操作**：
   - **修订（Revision）**：
     - 对每条轨迹进行自我反思（Reflect），识别逻辑不一致、推理不够充分的步骤。
     - 基于反思生成修订后轨迹（Revise），消除冗余或循环推理，融入替代视角。
     - 体现“规划起源与反思性进化”原则。
   - **重组（Recombination）**：
     - **交叉（Crossover）**：识别高性能轨迹段，组合生成继承多个父代优势的混合轨迹。
     - **迁移学习（Transfer）**：将成功轨迹的知识和策略系统迁移至较弱的轨迹。
     - **重构（Restructure）**：基于轨迹池的整体洞察，对轨迹进行全局重构。
   - **精炼（Refinement）**：
     - 设计多维奖励函数评估轨迹质量：任务完成度（TaskCompletion）、推理质量（ReasoningQuality）、效率（Efficiency）。
     - 采用混合选择机制：保留高分轨迹（基于奖励分数）并确保多样性（通过轨迹相异度度量）。
     - 迭代选择直到收敛（奖励提升低于阈值或达到预设迭代次数），最终输出最高奖励轨迹。

3. **算法流程**（文字描述）：
   - 输入：任务 T；初始生成 n 条轨迹形成池 T0。
   - 对每代：执行 Revision → Recombination → Refinement，生成新轨迹池 Ti+1。
   - 选择 k 条精英轨迹进入下一代，重复直到收敛或达到最大迭代次数。
   - 输出：最高奖励轨迹 t*。

## 3. 实验设计

- **数据集/场景**：使用 **SWE-bench Verified**，包含 500 个真实世界的 GitHub issue，涉及修复实际软件工程中的功能错误。每个实例提供自然语言描述和代码仓库，使用开发者编写的单元测试验证补丁正确性。
- **Benchmark**：SWE-bench Verified（广泛认可的代码相关任务基准）。
- **对比方法**：
  - **SWE-Agent**（CodeAct 框架）
  - **SWE-Search**（MCTS 框架）
  - 两种基线均属于高性能、开源框架。
- **评价指标**：
  - **Pass@1**：首次尝试即解决的任务百分比（反映系统整体有效性）。
  - **Pass@5**：在 5 次尝试内找到正确解的任务百分比（反映搜索效率）。
- **模型覆盖**：
  - 开源：DeepSeek-V3-0324、Qwen-2.5-72b-Instruct、Llama-3.1-70b-Instruct
  - 闭源：GPT-4o、Claude-3.7-Sonnet
  - 额外报告了 Claude-4-Sonnet 的结果（SWE-Agent 集成 SE-Agent 后达到 80.0%）。

## 4. 资源与算力

- **文中说明**：
  - 所有开源模型（DeepSeek-V3-0324、Qwen-2.5-72B-Instruct、Llama-3.1-70B-Instruct）在配备 NVIDIA A100 GPU（80GB 内存）的本地服务器上运行。
  - 闭源模型（GPT-4o、Claude-3.7-Sonnet）通过官方 API 访问。
- **未明确说明**：具体 GPU 数量、训练时长、总计算成本。但提到 SE-Agent 在 10 条候选轨迹时即可达到接近最优性能，且最大 API 成本预算下优于基线。

## 5. 实验数量与充分性

- **实验组别**：
  - **主要性能对比**：在 5 个不同 LLM 上比较 SE-Agent 与 SWE-Agent、SWE-Search（Pass@1 和 Pass@5）。
  - **消融研究**：移除 Revision、Recombination、两者均移除（w/o All），观察性能变化。
  - **超参数分析**：候选轨迹数量（5、10、15、20）和最大 API 成本对性能的影响。
  - **案例研究**：具体展示 SE-Agent 在 scikit-learn 一个 issue 上的演化过程（图 6、图 7）。
  - **重叠分析**：Venn 图展示不同框架成功解决的 issue 重叠情况。
- **充分性与公平性**：
  - 对比了多个模型，涵盖开源和闭源，基线为当前最强开源框架。
  - 消融实验证明每个模块的重要性。
  - 实验设置明确（相同提示格式、评估设置）。
  - 结论：实验较充分、客观、公平。

## 6. 主要结论与发现

- **性能提升显著**：SE-Agent 在所有 5 个 LLM 上均超越基线：
  - 相对于 SWE-Agent：Llama-3.1-70B 提升 112%，GPT-4o 提升 80%，Claude-3.7-Sonnet 提升 51%。
  - 相对于 SWE-Search（MCTS）：平均相对提升 30%。
  - 与 Claude-4-Sonnet 结合达到 **80.0% Pass@1**（当前开源 SOTA）。
- **模块有效性**：Revision 和 Recombination 均不可或缺；移除任一模块后性能下降（图 2）。
- **搜索效率高**：仅需 10 条候选轨迹即可接近最优性能（图 4）。
- **独特解决能力**：SE-Agent 能解决其他方法无法解决的 12 个 issue（图 3 Venn 图）。
- **跨模型泛化**：方法对不同模型族（DeepSeek、Qwen、LLaMA、GPT、Claude）均有效。

## 7. 优点

- **方法创新**：
  - 首次在轨迹层面引入自进化机制，不同于仅依赖采样参数调整的方法。
  - 三种操作（修订、重组、精炼）设计互补，既提供局部优化（Revision）又实现全局协作（Recombination）和最终精化（Refinement）。
  - 将遗传算法思想适配至 LLM 推理，高效利用少量进化循环。
- **实验设计**：
  - 覆盖多种类型 LLM（开源/闭源、不同规模），验证泛化性。
  - 消融研究充分，清晰分离每个模块贡献。
  - 超参数分析展示方法鲁棒性。
  - 案例研究具体演示演化过程，直观可信。
- **实用价值**：
  - 可即插即用集成至现有框架（如 SWE-Agent），无需修改基础模型。
  - 在复杂软件工程任务上达到 SOTA 性能，有实际部署潜力。

## 8. 不足与局限

- **实验覆盖**：
  - 仅在一个基准（SWE-bench Verified）上评估，未涉及数学推理、策略规划等领域。泛化性需更多验证。
  - 未与其他最新自演进方法（如 Reflexion、CRITIC）进行直接对比（虽然文中提及这些方法，但未纳入实验）。
- **计算成本**：
  - 文中未提供完整计算成本对比（总 API 调用次数、GPU 小时数等）。多次轨迹生成和评估会带来额外开销，可能限制在资源受限场景的应用。
  - 最大 API 成本实验中，SE-Agent 虽优于基线，但成本峰值未明确给出。
- **偏差风险**：
  - 使用 LLM 自身进行评估（ExpertEval），可能存在自我强化偏差或质量评估不准确的问题。
  - 轨迹池的初始多样性依赖于手工设计的规划策略，可能带有设计者主观偏好。
- **应用限制**：
  - 方法依赖多步交互环境（如代码执行环境），对单步任务或无需反馈的任务无效。
  - 需要维护轨迹池并执行迭代进化，不适合实时性要求高的场景。
  - 对基础模型能力有一定依赖（如弱模型可能无法生成有意义的反思或重组）。

（完）
