---
title: "DyFlow: Dynamic Workflow Framework for Agentic Reasoning"
title_zh: DyFlow：动态工作流框架用于智能体推理
authors: "Yanbo Wang, Zixiang Xu, Yue Huang, Xiangqi Wang, Zirui Song, Lang Gao, Chenxi Wang, Xiangru Tang, Yue Zhao, Arman Cohan, Xiangliang Zhang, Xiuying Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=0pbUfmwNTy"
tags: ["query:agent-papers"]
score: 6.0
evidence: 动态工作流生成用于智能体推理，适应任务，实现递归式改进
tldr: 现有LLM智能体工作流多为人工设计，适应性差。本文提出DyFlow框架，根据任务需求和实时反馈动态生成并调整推理流程。实验在复杂推理任务上展示了优于静态流程的性能，表明自适应工作流可提升智能体问题解决能力，但未涉及显式自我改进或递归结构。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-0pbufmwnty/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1455, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0pbufmwnty/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0pbufmwnty/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 658, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0pbufmwnty/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0pbufmwnty/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 587, \"height\": 715, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0pbufmwnty/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1439, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0pbufmwnty/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1438, \"height\": 691, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 492, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1424, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 601, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1413, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1331, \"height\": 923, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1257, \"height\": 633, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1022, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1451, \"height\": 448, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1201, \"height\": 979, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1339, \"height\": 404, \"label\": \"Table\"}]"
motivation: 手动设计的工作流缺乏普适性和灵活性，限制智能体推理性能。
method: 提出DyFlow，根据任务和中间反馈动态构建和调整推理程序。
result: 在多种推理基准上，DyFlow优于静态工作流和固定自动化方法。
conclusion: 动态工作流生成增强了智能体的适应性和鲁棒性。
---

## Abstract
Agent systems based on large language models (LLMs) have shown great potential in complex reasoning tasks, but building efficient and generalizable workflows remains a major challenge. Most existing approaches rely on manually designed processes, which limits their adaptability across different tasks. While a few methods attempt automated workflow generation, they are often tied to specific datasets or query types and make limited use of intermediate feedback, reducing system robustness and reasoning depth. Moreover, their operations are typically predefined and inflexible.
To address these limitations, we propose **DyFlow**, a dynamic workflow generation framework that adaptively constructs and adjusts reasoning procedures based on task requirements and real-time intermediate feedback, thereby enhancing cross-task generalization.
DyFlow consists of two core components: a designer and an executor. The designer decomposes complex problems into a sequence of sub-goals defined by high-level objectives and dynamically plans the next steps based on intermediate outputs and feedback. These plans are then carried out by the executor, which executes each operation using dynamic operators with context-aware parameterization, enabling flexible and semantically grounded reasoning.
We systematically evaluate DyFlow across diverse domains, including social reasoning, biomedical tasks, mathematical problem solving, and code generation.
Results demonstrate that DyFlow significantly outperforms existing baselines, achieving substantial Pass@k improvements and exhibiting robust generalization across diverse domains.

---

## 论文详细总结（自动生成）

# DyFlow：动态工作流框架用于智能体推理——详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **现有问题**：基于大型语言模型（LLM）的智能体系统在复杂推理任务中展现出潜力，但构建高效且可泛化的工作流仍面临重大挑战。当前大多数方法依赖人工设计的静态流程（如 MetaGPT、AutoGen、CAMEL），缺乏对不同任务的适应性；少数方法尝试自动生成工作流（如 AFlow、ADAS），但往往绑定特定数据集或查询类型，且对中间反馈利用不足，导致系统鲁棒性和推理深度受限。此外，现有操作通常是预定义的、缺乏灵活性。
- **研究目标**：提出 DyFlow，一种动态工作流生成框架，能够根据任务需求和实时中间反馈自适应构建并调整推理过程，从而增强跨任务泛化能力。核心思想是将推理建模为子目标规划与模块化算子执行的动态序列，通过“设计器-执行器”双层架构实现高层规划与低层执行的分离与协同。

## 2. 方法论：核心思想、关键技术细节、算法流程

### 核心思想
- DyFlow 将复杂推理任务形式化为一个动态决策过程。每个时间步，**设计器（designer）** 根据当前状态（包括任务、历史子图、中间输出、错误信号）生成一个阶段性子图（stage subgraph），该子图由一组算子实例（operator instances）及依赖关系构成，用于解决一个子目标。**执行器（executor）** 按照拓扑顺序执行这些算子，将结果存入全局记忆缓冲，并更新状态。设计器通过反馈循环持续调整规划，支持高层策略调整和细粒度执行修正。

### 关键技术细节
1. **状态表示与规划形式化**：
   - 每个任务 $p$ 对应一个状态序列 $s_t$，包含原始任务、先前子图 $G_0,\dots,G_{t-1}$、中间输出、错误信息等。
   - 算子模板集合 $\mathcal{O}$ 包含多种基本推理/执行步骤（如 GENERATE_ANSWER、REVIEW_SOLUTION、REFINE_ANSWER 等）。
   - 每个阶段子图 $G_t = (V_t, E_t, v_{\text{start}}, C_{\text{end}})$，其中 $V_t$ 中的每个算子实例 $o = (O_k, \phi, \psi)$：$O_k \in \mathcal{O}$ 为模板，$\phi$ 为上下文感知的细粒度指令，$\psi$ 为从记忆 $M$ 中引用的输入键列表。
   - 执行轨迹 $\tau = (s_0, G_0, s_1, G_1, \dots, G_{T-1}, s_T)$，满足状态转移 $s_t \to s_{t+1}$ 由执行 $G_t$ 产生。
2. **设计器训练**：
   - **两阶段学习策略**：第一阶段基于成功轨迹对设计器进行监督微调（SFT），使其获得基础规划能力；第二阶段采用自博弈偏好优化（KTO），让设计器与执行器交互生成自身轨迹，并基于执行成功/失败信号逐子图标注偏好，从而学习从失败中改进。训练数据仅来自自身生成的轨迹，不需额外标注。
   - 设计器模型（DyPlanner）采用 Phi-4 初始化，通过 LoRA 参数高效微调，不重新训练执行器。
3. **执行过程（算法 1）**：
   - 初始化状态 $s_0$ 和空记忆 $M$。
   - 每步 $t$：用 GPT-4o-mini 总结状态 $z_t = f_{\text{summary}}(s_t)$，设计器采样子图 $G_t \sim \pi_\theta(\cdot|z_t)$；执行器按拓扑顺序执行算子，将结果存入 $M$；更新状态 $s_{t+1}$；检查终止条件。
   - 设计器控制一切执行控制（包括是否继续、修订、回溯、终止），无需在图中硬编码分支或循环逻辑。

### 公式说明（文字）
- 监督损失：$L_{\text{SFT}}(\theta) = -\mathbb{E}_{(s, G^{\text{expert}})} [\log \pi_\theta(G^{\text{expert}} | f_{\text{summary}}(s))]$
- 偏好优化损失：使用 KTO 损失函数 $L_{\text{pref}}(\theta) = \mathbb{E}_{(s,G,l)} [L_{\text{single}}^{\text{pref}}(p_\theta, p_{\text{ref}}, l; \beta)]$，其中 $l \in \{\text{preferred}, \text{discarded}\}$ 基于轨迹整体成功与否判定。

## 3. 实验设计

### 数据集与场景
- 涵盖 **5 个推理领域**：
  - 逻辑推理：LiveBench
  - 数学推理：MATH
  - 医学推理：PubMedQA
  - 代码推理：HumanEval
  - 社会推理：SocialMaze
- **训练集**：仅使用 MATH、PubMedQA、LiveBench 的 84+84+50 条数据（共约 218 条？实际表 7 显示 #Train 分别为 84、84、50、55？但论文说明训练集为 MATH、PubMedQA、LiveBench，总计 84+84+50=218？实际表 7 中 LiveBench 训练 50，MATH 训练 84，PubMedQA 训练 84，共计 218，HumanEval 和 SocialMaze 各 55 和 87 但作为零样本测试。但论文描述中还说使用了 1.5k 设计结果进行 SFT，2k 设计结果进行 KTO，可能额外生成了更多数据？这些数据源自训练集中的查询？）
- **评测指标**：除代码任务用 pass@1 外，其余用准确率（Accuracy）。此外还报告 Pass@k（k=1~5）。

### 对比方法（Baselines）
- **提示类方法**：Vanilla、CoT、Self-Consistency (SC)、LLM-Debate、Self-Refine
- **自动化智能体框架**：ADAS、AFlow、MaAS (Multi-agent Architecture Search)

所有对比方法使用相同执行器 Phi-4 和同一算子集合，保证公平。

### 实验充分性
- **主实验**：在 5 个领域对比 8 个基线，报告平均准确率（表 1）。
- **Pass@k 分析**：对比 DyFlow 和 CoT 的 Pass@k 曲线（图 3，图 7）。
- **泛化分析**：
  - 跨设计器：使用 Claude-3.7-Sonnet、GPT-4.1、Phi-4（DyPlanner）作为设计器，结果见表 2。
  - 跨执行器：使用 GPT-4o-mini、Phi-4、GPT-4.1-mini 作为执行器，对比 CoT 和 DyFlow（图 4，表 10）。
  - 跨任务：排除一个领域进行训练，测试该领域，结果见表 3（共 4 个配置？文章给出 4 行：SR、CR、MR、QR 分别对应 SocialMaze、HumanEval、PubMedQA、MATH）。
- **消融实验**：去除 SFT、KTO、动态算子、动态规划四种变异，结果见表 4。
- **案例研究**：展示了 MATH、LiveBench、SocialMaze、Code 等任务的定性对比。
- **成本分析**：部分分析（附录表 8、9）涉及 token 数和美元成本。

总体实验数量较丰富，覆盖多种设置，消融和泛化分析完整。

## 4. 资源与算力

- **训练**：使用 2 块 NVIDIA A6000 GPU，采用 LoRA 参数高效微调。
- **SFT 阶段**：1.5k 设计结果，序列长度 2048，batch size 1（梯度累积 4），学习率 5e-6，余弦调度，预热 0.1，bf16，3 epoch。
- **KTO 阶段**：2k 设计结果，正负比 1:1，序列长度 4096，batch size 1（梯度累积 8），学习率 2e-4，KL 惩罚 β=0.1，bf16，3 epoch。
- **推理**：温度 0.01 以保证确定性输出。
- 文中未明确报告总训练时长，但两台 A6000 完成 3 epoch 的 2k 级数据 LoRA 训练通常为数小时内。

## 5. 实验数量与充分性评价

| 实验类型 | 数量/配置 | 充分性评价 |
|----------|-----------|------------|
| 主性能对比 | 1 张表，5 领域，8 基线 | 足够，覆盖主流提示和自动化方法 |
| Pass@k 分析 | 2 张图（综合+分领域） | 揭示稳定性上限，合理 |
| 跨设计器 | 1 张表，3 种骨干模型（含 DyPlanner vs 商用） | 证明训练框架鲁棒，设计器效果与大小无关 |
| 跨执行器 | 1 张图+1 张表，3 种执行器 | 证明与多种模型兼容，改善显著 |
| 跨任务泛化 | 4 种留出设置（SocialMaze, HumanEval, PubMedQA, MATH 轮流作为零样本） | 强有力证明域间泛化 |
| 消融 | 4 个变体（w/o KTO, w/o SFT, w/o Dynamic Op, w/o Dynamic Planning） | 各组件贡献明确，尤其动态规划最为关键 |
| 成本分析 | 附录中 token 数和美元成本，对比多个基线 | 显示 DyFlow 成本可控，性价比高 |
| 案例研究 | 多个领域（数学、逻辑、社会、代码）的定性对比 | 直观解释收益来源 |
| 理论分析 | 附录 B 给出性能界与收敛保证 | 提供理论支撑 |

**总体评价**：实验设计全面且公平。所有基线使用相同执行器和算子集；跨模型、跨任务泛化设置严格；消融设计合理。未报告误差条（限于计算代价），但改进幅度大且一致性高，结论可信。

## 6. 主要结论与发现

1. **性能优势显著**：DyFlow 在全部 5 个领域上平均准确率 61.45%，比最强基线 MaAS（57.74%）高 3.71 个百分点，且每个领域均优于所有基线。
2. **零样本泛化能力强**：在从未见过的 SocialMaze（社会推理）和 HumanEval（代码）上分别提升 10.69% 和 5.48%，证明自适应规划的可迁移性。
3. **跨设计器/执行器鲁棒**：即使用轻量 Phi-4 作为设计器（DyPlanner），性能仍与商用大模型（GPT-4.1、Claude-3.7-Sonnet）相当甚至更优；与不同执行器配合均稳定提升，尤其对弱执行器补偿明显。
4. **消融结果揭示关键组件**：移除动态规划后性能下降最大（从 61.45 降至 56.48），说明反馈驱动重规划是 DyFlow 的核心收益来源。
5. **理论保证**：证明 DyFlow 在动态策略搜索空间中至少不差于静态策略，且 Bellman residual 上界保证了收敛性。

## 7. 优点

- **方法创新**：首次将子目标级动态重规划与执行器分离，通过设计器-执行器双层结构实现灵活推理，避免了静态流程的僵化。
- **训练策略高效**：两阶段训练（SFT+KTO）结合自博弈，使轻量模型（Phi-4 14B）达到与商用大模型相当的设计能力，且训练成本低、无需人工标注偏好对。
- **通用性高**：框架不依赖特定数据集或执行器，仅需训练一次设计器即可泛化到多种任务和模型。
- **实验验证充分**：涵盖 5 个领域、多种基线、多个泛化设置、消融与理论分析，论证严谨。
- **开源与可复现**：公开代码和训练细节，促进后续研究。

## 8. 不足与局限

- **未集成外部工具**：当前算子集限于符号推理和文本推理，不支持搜索引擎、数据库查询、环境交互等操作，限制了在需要工具辅助的复杂任务上的表现。
- **训练数据量偏小**：SFT 和 KTO 分别使用 1.5k 和 2k 条设计结果，虽然由训练集生成，但绝对值较小，可能影响泛化的上限。
- **未报告误差条**：受限于计算成本，主实验结果未给出标准差或置信区间，但改进幅度一致且稳定，部分弥补了缺陷。
- **执行器固定**：训练过程中执行器固定，设计器优化的目标仅针对当前执行器，更换执行器后规划能力可能需要重新适配（尽管跨执行器实验表明已有一定泛化）。
- **理论分析有限**：附录的理论证明较为基础（性能界与收敛性），对更复杂的自适应特性（如重规划频率、反馈粒度的影响）缺乏深入分析。
- **潜在偏差风险**：训练数据来自特定领域（数学、逻辑、医学），可能在这些领域以外的任务（如开放域问答、创意生成）上泛化性需进一步验证。

（完）
