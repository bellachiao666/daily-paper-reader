---
title: "UI-Genie: A Self-Improving Approach for Iteratively Boosting MLLM-based Mobile GUI Agents"
title_zh: UI-Genie：一种迭代提升多模态大模型移动GUI智能体的自改进方法
authors: "Han Xiao, Guozhi Wang, Yuxiang Chai, Zimu Lu, Weifeng Lin, Hao He, Lue Fan, Liuyang Bian, Rui Hu, Liang Liu, Shuai Ren, Yafei Wen, Xiaoxin Chen, Aojun Zhou, Hongsheng Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=3uUmJzSSOW"
tags: ["query:agent-papers"]
score: 8.0
evidence: 用于移动GUI智能体的自改进框架，包含奖励模型
tldr: 本文提出UI-Genie自改进框架，用于提升多模态大模型驱动的移动GUI智能体。该框架包含一个图像文本交织架构的奖励模型，实现动作级和任务级奖励统一，并通过规则验证、轨迹破坏和困难负样本挖掘等数据生成策略训练奖励模型。自改进流水线逐步提升智能体性能。实验证明该方法有效解决了轨迹验证和数据扩展两大挑战。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-3uumjzssow/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 462, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3uumjzssow/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1430, \"height\": 706, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3uumjzssow/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1435, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3uumjzssow/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 587, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3uumjzssow/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 360, \"height\": 763, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3uumjzssow/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1172, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3uumjzssow/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1210, \"height\": 1836, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3uumjzssow/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1315, \"height\": 1505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3uumjzssow/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1308, \"height\": 672, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3uumjzssow/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1453, \"height\": 1458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3uumjzssow/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1456, \"height\": 1425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3uumjzssow/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1451, \"height\": 1705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3uumjzssow/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1462, \"height\": 1696, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-3uumjzssow/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 874, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3uumjzssow/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 962, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3uumjzssow/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 795, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3uumjzssow/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 493, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3uumjzssow/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3uumjzssow/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1267, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3uumjzssow/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 795, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3uumjzssow/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1435, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3uumjzssow/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1219, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3uumjzssow/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 935, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3uumjzssow/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1129, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3uumjzssow/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 841, \"height\": 404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3uumjzssow/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1067, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3uumjzssow/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 994, \"height\": 387, \"label\": \"Table\"}]"
motivation: GUI智能体面临轨迹验证困难和高质量训练数据难以扩展的问题。
method: 构建奖励模型与自改进流水线，通过规则验证和轨迹破坏等生成策略进行训练。
result: 在多种移动GUI任务上显著提升性能，验证了自改进框架的有效性。
conclusion: 自改进方法能有效提升GUI智能体，且奖励模型设计是关键。
---

## Abstract
In this paper, we introduce UI-Genie, a self-improving framework addressing two key challenges in GUI agents: verification of trajectory outcome is challenging and high-quality training data are not scalable. These challenges are addressed by a reward model and a self-improving pipeline, respectively. The reward model, UI-Genie-RM, features an image-text interleaved architecture that efficiently processes historical context and unifies action-level and task-level rewards. To support the training of UI-Genie-RM, we develop deliberately-designed data generation strategies including rule-based verification, controlled trajectory corruption, and hard negative mining. To address the second challenge, a self-improvement pipeline progressively expands solvable complex GUI tasks by enhancing both the agent and reward models through reward-guided exploration and outcome verification in dynamic environments. For training the model, we generate UI-Genie-RM-517k and UI-Genie-Agent-16k, establishing the first reward-specific dataset for GUI agents while demonstrating high-quality synthetic trajectory generation without manual annotation. Experimental results show that UI-Genie achieves state-of-the-art performance across multiple GUI agent benchmarks with three generations of data-model self-improvement. We open-source our complete framework implementation and generated datasets to facilitate further research in https://github.com/Euphoria16/UI-Genie.

---

## 论文详细总结（自动生成）

以下是基于论文《UI-Genie: A Self-Improving Approach for Iteratively Boosting MLLM-based Mobile GUI Agents》的详细中文总结，按照要求结构化呈现。

---

# UI-Genie 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：当前基于多模态大语言模型（MLLM）的移动 GUI 智能体面临两大关键挑战：
  1. **轨迹结果验证困难**：传统方法依赖人工或专有模型（如 GPT‑4o）进行验证，成本高、难以扩展，且无法提供中间步骤的细粒度反馈。
  2. **高质量训练数据难以规模化**：现有训练数据多依赖人工标注的操作轨迹，耗时昂贵，且缺乏复杂多步任务的高质量示范。
- **整体含义**：为突破上述瓶颈，本文提出 **UI‑Genie**，一个自改进框架，能够在不依赖大量人工标注的前提下，通过奖励模型（Reward Model）和自改进流水线（Self‑improvement Pipeline）自动生成高质量合成轨迹，并持续提升智能体性能。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 构建一个专门用于 GUI 轨迹评估的奖励模型 **UI‑Genie‑RM**，统一动作级和任务级奖励，并在其指导下进行奖励引导的轨迹探索，从而自动生成高质量合成数据。
- 引入迭代自改进机制：智能体模型与奖励模型交替提升，逐步解决更复杂的 GUI 任务。

### 关键技术细节
- **奖励模型架构（UI‑Genie‑RM）**：
  - 基于 Qwen2.5-VL-7B 构建，采用 **图像-文本交错架构**，可高效处理历史上下文（最多保留最近 5 张截图）。
  - 将早期动作总结为自然语言描述以降低计算开销。
  - 将“任务完成”视为一个特殊动作，统一动作级和任务级奖励，使用二分类 next‑token 生成任务训练（正标签 `⟨|+|⟩`，负标签 `⟨|−|⟩`）。
- **奖励模型训练数据构建策略**：
  1. **基于规则的验证（Rule‑based Verification）**：利用初始智能体采样候选动作，与真实动作进行类型对齐、坐标准确性、语义一致性三种验证。
  2. **受控轨迹破坏（Controlled Trajectory Corruption）**：对成功轨迹进行早期截断、跨任务替换、多余延续三种破坏，生成负样本。
  3. **困难负样本挖掘（Hard Negative Mining）**：利用初始奖励模型识别被误判为正样本的负动作。
  - 最终得到 **UI‑Genie‑RM‑517k** 数据集（含 458k 初始样本 + 59k 自改进样本）。
- **自改进流水线**：
  - **奖励引导轨迹探索**：采用 beam search（每步采样 10 个候选动作，由 RM 打分，保留 top‑5 路径），替代昂贵的 MCTS。
  - **训练数据扩展**：成功轨迹直接加入智能体训练集；失败轨迹的中间步骤通过 continuation rollouts 标注为正确或错误（基于潜在正确性）。
  - **迭代微调**：三轮自改进，任务难度逐步增加（从原始任务指令 → 新增指令 → 复杂手动设计任务）。

## 3. 实验设计：数据集、benchmark 及对比方法

### 数据集
- **开放数据集**：AndroidControl、AMEX、AndroidLab（用于初始模型训练和奖励模型数据生成）。
- **自生成数据集**：UI‑Genie‑RM‑517k（奖励模型训练），UI‑Genie‑Agent‑16k（智能体合成轨迹，无人工标注）。

### Benchmark
- **静态评估**：AndroidControl（低/高级任务），指标：Success Rate (SR)、Type Accuracy、Grounding Accuracy。
- **动态评估**：
  - AndroidLab（138 个任务，9 类离线应用），指标：Sub‑Goal SR、Redundancy Ratio、Reasonable Operation Ratio、Overall SR。
  - Android Agent Arena (A3)（201 个任务，20 个在线应用，含复杂多步任务），指标：Func SR、LLM SR、ESAR。

### 对比方法
- **商业系统**：Claude Computer Use、GPT‑4o、Gemini 系列、Claude 系列。
- **开源基础模型**：Qwen2.5-VL、UI-TARS、OS-Atlas、Aria-UI、SeeClick、Aguvis 等。
- **微调变体**：UI-TARS-ft、Qwen2.5-VL-ft 等。
- 部分 benchmark 还对比了专用智能体（AutoGLM、AppAgent 等）。

## 4. 资源与算力

- 论文明确说明：
  - 使用 **20 台 L40s 机器，每台 4 张 GPU**（共 80 张 GPU）。
  - 训练超参数：学习率 1e-5，批次大小 160，AdamW 优化器。
  - 智能体 72B 模型采用 **LoRA**（rslora，rank=256，alpha=256，PiSSA 初始化）以节省显存。
- **未明确提供**：总训练时长（小时）、单次自改进循环所需时间等信息。

## 5. 实验数量与充分性

- **实验数量丰富**：
  - 三个主 benchmark（AndroidControl、AndroidLab、A3），涉及多个模型尺寸（3B/7B/72B）。
  - 奖励模型评估：自建 1050 个配对样本的 benchmark，分步骤级与任务级，按难易度（easy/medium/hard）报告 F1 分数。
  - 消融实验：① 历史窗口大小（1/3/5/8/10 截图）对 RM 性能与效率的影响；② 自改进轮次效果（round 0→3）；③ 复杂任务生成与 RM 更新的贡献；④ 测试时缩放（best-of-N）。
- **充分性**：实验覆盖了多种任务类型（静态/动态、低/高级、在线/离线），对比了主流商业与开源方法，消融设计合理，验证了各组件有效性。
- **客观公平**：奖励模型评估时，对基线方法精心设计了提示（prompt）以公平比较，但仍存在提示优化偏差风险（如 GPT-4o 可能因提示不够最优而表现略低）。

## 6. 论文的主要结论与发现

1. **UI‑Genie‑RM 显著优于所有基线**：在步骤级（79.6% F1）和任务级（82.1% F1）奖励评估上全面领先 GPT-4o、Gemini 等，尤其在困难任务上优势更明显（+约 14–24%）。
2. **智能体模型达到 SOTA**：在 AndroidControl 高难度任务上，UI-Genie-Agent-7B 以 74.2% SR 超过 UI-TARS-7B（72.5%）；72B 版本达到 77.0%。在 AndroidLab 上，7B 模型实现 38.7% SR，超越所有商业与开源方法。在 A3 上，7B 模型将 Func SR 从 16.9%（UI-TARS）提升至 20.4%。
3. **自改进循环有效**：经过三轮迭代，智能体成功率从 18.1% 提升至 38.7%，奖励模型准确率从 68.2% 提升至 79.6%。
4. **无人工标注合成数据可行**：仅利用公开数据集和自生成数据即可获得高质量轨迹，证明了框架的可扩展性。

## 7. 优点

- **创新性**：首次提出专用于 GUI 智能体的统一奖励模型，并实现动作级与任务级奖励的联合评估。
- **实用性**：自改进框架消除了对大量人工标注的依赖，大幅降低数据构建成本，且开源了完整代码与数据集。
- **全面性**：实验覆盖多种 benchmark 和模型尺寸，消融实验深入，结果具有说服力。
- **效率平衡**：通过限制历史窗口为最近 5 张截图、使用语言摘要替代早期截图，在性能与计算开销间取得良好折中。

## 8. 不足与局限

- **奖励模型偶尔产生次优信号**：可能导致轨迹探索失败，进而产生低质量合成数据，影响后续轮次。
- **无法保证所有 GUI 任务均能生成完全正确的轨迹**：框架能力上限受限于初始智能体与奖励模型的初始性能。
- **计算成本依然较高**：需要 80 张 GPU 进行训练，且多次迭代会累积碳排放。
- **存在潜在滥用风险**：如论文所述，全自动 GUI 机器人可能被用于欺诈或窃取隐私。
- **实验覆盖不够广泛**：虽然测试了在线应用（A3），但未涉及跨设备或跨操作系统场景（如 iOS、桌面端）。
- **超参数未充分探索**：如 beam width（5）、候选数（10）等未进行系统调优。

---

（完）
