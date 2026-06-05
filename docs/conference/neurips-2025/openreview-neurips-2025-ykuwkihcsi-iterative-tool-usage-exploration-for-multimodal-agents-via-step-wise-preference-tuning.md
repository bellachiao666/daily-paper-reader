---
title: Iterative Tool Usage Exploration for Multimodal Agents via Step-wise Preference Tuning
title_zh: 通过逐步偏好优化实现多模态智能体的迭代工具使用探索
authors: "Pengxiang Li, Zhi Gao, Bofei Zhang, Yapeng Mi, Xiaojian Ma, Chenrui Shi, Tao Yuan, Yuwei Wu, Yunde Jia, Song-Chun Zhu, Qing Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=yKUwkihcsi"
tags: ["query:agent-papers"]
score: 7.0
evidence: 通过逐步偏好优化实现多模态智能体的迭代自改进
tldr: 该论文提出SPORT方法，无需预收集数据，通过逐步偏好优化迭代探索工具使用轨迹，使多模态智能体自主发现和改进复杂任务中的工具调用策略。该方法迭代式地提升代理性能，体现递归自改进的思想，适用于复杂任务求解。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ykuwkihcsi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ykuwkihcsi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1451, \"height\": 752, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ykuwkihcsi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 722, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ykuwkihcsi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1444, \"height\": 849, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ykuwkihcsi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1444, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ykuwkihcsi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1418, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ykuwkihcsi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 916, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ykuwkihcsi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 246, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ykuwkihcsi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1438, \"height\": 1386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ykuwkihcsi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1446, \"height\": 1935, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ykuwkihcsi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1432, \"height\": 1070, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ykuwkihcsi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1456, \"height\": 554, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ykuwkihcsi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 638, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ykuwkihcsi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 758, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ykuwkihcsi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 611, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ykuwkihcsi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 721, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ykuwkihcsi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 700, \"height\": 126, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ykuwkihcsi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 646, \"height\": 124, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ykuwkihcsi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1157, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ykuwkihcsi/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1448, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ykuwkihcsi/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 864, \"height\": 149, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ykuwkihcsi/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1291, \"height\": 145, \"label\": \"Table\"}]"
motivation: 复杂多模态任务中人工标注工具轨迹成本高昂且不可行。
method: 提出基于逐步偏好优化的迭代探索方法，自动优化工具调用轨迹。
result: 在多个多模态基准上达到或超越有监督方法性能。
conclusion: SPORT为多模态智能体提供了无监督的迭代自改进框架。
---

## Abstract
Multimodal agents, which integrate a controller (e.g., a vision language model) with external tools, have demonstrated remarkable capabilities in tackling complex multimodal tasks.
Existing approaches for training these agents, both supervised fine-tuning and reinforcement learning, depend on extensive human-annotated task-answer pairs and tool trajectories.
However, for complex multimodal tasks, such annotations are prohibitively expensive or impractical to obtain.
In this paper, we propose an iterative tool usage exploration method for multimodal agents without any pre-collected data, namely SPORT, via step-wise preference optimization to refine the trajectories of tool usage. Our method enables multimodal agents to autonomously discover effective tool usage strategies through self-exploration and optimization, eliminating the bottleneck of human annotation.
SPORT has four iterative components: task synthesis, step sampling, step verification, and preference tuning.
We first synthesize multimodal tasks using language models. 
Then, we introduce a novel trajectory exploration scheme, where step sampling and step verification are executed alternately to solve synthesized tasks.
In step sampling, the agent tries different tools and obtains corresponding results. 
In step verification, we employ a verifier to provide AI feedback to construct step-wise preference data. 
The data is subsequently used to update the controller for tool usage through preference tuning, producing a SPORT agent.
By interacting with real environments, the SPORT agent gradually evolves into a more refined and capable system.
Evaluation in the GTA and GAIA benchmarks shows that the SPORT agent achieves 6.41% and  3.64% improvements, underscoring the generalization and effectiveness introduced by our method.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

多模态智能体将视觉语言模型（VLM）作为控制器，通过调用外部工具（如网络搜索、视觉推理、文件理解、目标定位等）来执行复杂多模态任务。现有方法（监督微调 SFT 和强化学习 RL）高度依赖人工标注的任务-答案对和工具调用轨迹。然而，对于复杂多模态任务，此类标注成本极高甚至不可行。论文旨在探索一种**无需任何预收集数据**的自探索机制，使多模态智能体能通过与真实环境交互，自主发现并优化工具使用策略，从而摆脱人工标注的瓶颈，提升泛化性。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
提出 **SPORT**（**S**tep-wise **P**reference **O**ptimization to **R**efine **T**rajectories），一种通过**逐步偏好优化**进行迭代工具使用探索的方法。智能体自行生成任务、采样步骤、验证步骤质量，并利用偏好数据调优控制器，形成闭环自改进。

### 关键技术细节
SPORT 包含四个迭代组件，在一个迭代周期内顺序执行：

1. **任务合成**：利用 LLM（如 Qwen2.5-7B）基于种子任务生成自然语言查询，再根据查询生成所需多模态文件（图片从现成数据集检索，非图片由 LLM 写 Python 代码生成）。生成后经修订与过滤保证质量。
2. **步骤采样**：对于给定任务，控制器在每个步骤采样 n 个候选动作（包含 thought 和 code），并行执行得到观测结果。
3. **步骤验证**：使用一个多模态验证器（同样基于 LLM），给定任务上下文、历史、当前步骤动作及其执行结果，**选择最佳动作**作为偏好样本，其余为不偏好样本，构建逐步偏好数据对 $(x_i, a_i^{\text{pre}}, a_i^{\text{dis}})$。
4. **偏好调优**：收集所有偏好对，使用 DPO（Direct Preference Optimization）损失更新控制器参数：
   
   $$L(\theta)=-\mathbb{E}_{(x_i,a_i^{\text{pre}},a_i^{\text{dis}})\sim\mathcal{D}}\left[\log\sigma\left(\beta\log\frac{\pi_\theta(a_i^{\text{pre}}|x_i)}{\pi_{\text{ref}}(a_i^{\text{pre}}|x_i)}-\beta\log\frac{\pi_\theta(a_i^{\text{dis}}|x_i)}{\pi_{\text{ref}}(a_i^{\text{dis}}|x_i)}\right)\right]$$

   其中 $\pi_\theta$ 为当前控制器，$\pi_{\text{ref}}$ 为参考控制器（初始为 SFT 后的模型），$\beta$ 控制偏离程度。

**训练流程**：先通过 SFT 阶段（使用 MAT 的 20K 轨迹）使控制器具备基本工具调用能力；然后进入自探索阶段，迭代执行上述四步，每轮用构造的偏好数据更新一次控制器。算法伪代码见论文算法 1。

## 3. 实验设计：数据集、Benchmark 与对比方法

### 数据集 / Benchmark
- **GTA**：229 个任务，252 张图片，任务需要 2-8 步，主要评估感知、推理、工具调用。
- **GAIA**：446 个任务，109 个文件（PPTX、PDF、XLSX 等），分三个难度级别，评估文档理解、网络导航、逻辑推理、总结能力。

### 对比方法
- **闭源控制器**：Lego Agent (GPT-4/4o)、Warm-up Agent (GPT-4-turbo)、HF Agent (GPT-4o / GPT-4o-mini)
- **开源控制器**：HF Agent (LLaVA-NeXT-8B, InternVL2-8B, MiniCPM-V-8.5B, Qwen2-VL-7B) 以及经过 SFT 的 T3-Agent（MAT 版本）

### 评估指标
- GTA：AnsAcc（答案准确率）、ToolAcc（工具选择正确率）、CodeExec（代码无错误执行率）
- GAIA：不同级别（Level 1/2/3）及整体 AnsAcc

## 4. 资源与算力

论文明确使用了 8 × A100 GPU 进行训练，采用 LoRA（rank=32）微调 Qwen2-VL-7B 的语言部分，冻结视觉编码器。学习率 1e-6，batch size 2 per device，最大上下文窗口 10240 tokens。训练时间与迭代次数和步长正相关。

附录 C 进一步给出了与基线 MAT 的计算开销对比：SPORT 总计算时间约 36.56 GPU 小时（包括数据生成与训练），而 MAT 约 173.75 GPU 小时，SPORT 速度提升约 4.75 倍，GPU 成本降低约 32.7%。

## 5. 实验数量与充分性

论文进行了**多组实验**，覆盖：
- **主实验**：在 GTA 和 GAIA 上与 10+ 种方法对比。
- **消融实验**：
  - 迭代步长 d（200/500/1000）：d=500 最优。
  - 静态偏好数据 vs 在线探索：SPORT 远超 MAT-SFT-DPO。
  - 不同基础模型（Qwen2-VL-7B 直接应用 vs MAT 之后应用）：SPORT 独立有效且可互补。
  - 任务多样性与质量敏感性（种子减少）：性能略有下降但仍优于 SFT。
- **统计数据**：分析偏好数据中工具分布差异（45.62%）、代码错误率（选择步 18.35% vs 拒绝步 81.94%）、BLEU 分数（验证器选择更 discriminate）。
- **人类评估**：20 位研究者对任务质量（自然性、合理性）和轨迹质量（代码、工具、参数）打分均高于 8 分，验证器与人类偏好一致率达 82%。

实验设计较为充分，对比基线多样，消融覆盖关键因素，结果具有统计学显著性（给出了方差）。评价公平：推理时关闭采样与验证，与基线一致。

## 6. 论文的主要结论与发现

- SPORT 无需任何人工标注数据即可持续改进多模态智能体工具使用能力。
- 在 GTA 上，SPORT Agent 的 AnsAcc 达到 **60.26%**，相比 SFT 基线（MAT-Qwen2-VL-7B 53.85%）提升 **6.41%**；ToolAcc 提升 7.78%，CodeExec 提升 7.55%。
- 在 GAIA 上，SPORT Agent 达到 **20.61%** AnsAcc，相比 SFT 基线（16.97%）提升 **3.64%**。
- 逐步偏好数据优于轨迹级或静态偏好数据，能更高效学习且利用失败轨迹中的有用信息。
- SPORT 方法在开源模型中达到最佳，并缩小了与闭源模型的差距。

## 7. 优点

- **完全无监督**：无需任何人工预收集数据，通过自探索生成任务、验证步骤、构造偏好数据。
- **高效数据利用**：逐步偏好验证可从失败轨迹中提取有益偏好对，提高样本效率。
- **逐步验证更易**：验证单步质量比验证完整轨迹简单，降低了验证难度。
- **可扩展和泛化**：通过迭代交互，模型能不断适应新环境和工具分布，提升泛化性。
- **开源友好**：所有代码与 16K 偏好数据集将开源，促进后续研究。

## 8. 不足与局限

- **验证器依赖人工规则**：当前验证器基于启发式规则和提示，对于异常情况泛化有限。论文计划未来探索“学会验证”的方法。
- **与闭源模型仍有差距**：在 GAIA 上与 GPT-4 等闭源模型相比仍有约 13% 的性能差距，归因于模型规模和训练数据差异。
- **任务多样性影响性能**：消融显示减少种子任务数量会导致性能下降（60.26% → 58.33%），虽仍强于 SFT，但表明任务合成质量是重要因素。
- **计算资源需求**：虽然比 MAT 节省计算，但整体仍需多 GPU 支持，可能限制资源有限的研究者。
- **未评估理论保证**：验证器缺乏形式化收敛性分析，在开放场景下的可靠性需进一步研究。

（完）
