---
title: "Behavior Injection: Preparing Language Models for Reinforcement Learning"
title_zh: 行为注入：为大语言模型进行强化学习做好准备
authors: "Zhepeng Cen, Yihang Yao, William Han, Zuxin Liu, Ding Zhao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=mzlwDAQkgJ"
tags: ["query:agent-papers"]
score: 6.0
evidence: 通过行为注入数据增强提升LLM对RL微调的响应，使自改进更有效
tldr: LLM对RL微调的响应差异巨大，有些提升显著而有些甚至退化。本文首先分析RL每步影响，识别出两个关键条件：RL信息性rollout准确性和强数据共影响。基于此提出行为注入，一种任务无关的数据增强方法，在RL微调前丰富监督微调数据。实验表明，行为注入显著提升了LLM在RL后的推理能力，为通过强化学习实现自改进奠定了数据基础。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzlwdaqkgj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 489, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzlwdaqkgj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 535, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzlwdaqkgj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1403, \"height\": 877, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzlwdaqkgj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1434, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzlwdaqkgj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 452, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzlwdaqkgj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 892, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzlwdaqkgj/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1240, \"height\": 715, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzlwdaqkgj/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 871, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzlwdaqkgj/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1422, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzlwdaqkgj/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 947, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzlwdaqkgj/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1006, \"height\": 624, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzlwdaqkgj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1382, \"height\": 539, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzlwdaqkgj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1382, \"height\": 540, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzlwdaqkgj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 547, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzlwdaqkgj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 625, \"height\": 374, \"label\": \"Table\"}]"
motivation: LLM对RL微调响应不一致，需要理解并改进RL微调的有效性条件。
method: 分析RL目标每步影响，提出行为注入数据增强方案，在RL前提升数据质量。
result: 行为注入使LLM在多种推理任务上RL微调后的性能显著提升，且收敛更稳定。
conclusion: 行为注入是一种简单有效的预处理方法，可增强LLM通过RL自改进的效果。
---

## Abstract
Reinforcement learning (RL) has emerged as a powerful post-training technique to incentivize the reasoning ability of large language models (LLMs). However, LLMs can respond very inconsistently to RL finetuning: some show substantial performance gains, while others plateau or even degrade. To understand this divergence, we analyze the per-step influence of the RL objective and identify two key conditions for effective post-training: (1) RL-informative rollout accuracy, and (2) strong data co-influence, which quantifies how much the training data affects performance on other samples. Guided by these insights, we propose behavior injection, a task-agnostic data augmentation scheme applied prior to RL. Behavior injection enriches the supervised finetuning (SFT) data by seeding exploratory and exploitative behaviors, effectively making the model more RL-ready. We evaluate our method across two reasoning benchmarks with multiple base models. The results demonstrate that our theoretically motivated augmentation can significantly increase the performance gain from RL over the pre-RL model.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：大语言模型（LLM）对强化学习（RL）微调的响应非常不一致——有的模型性能大幅提升，有的则停滞甚至退化。论文旨在理解这种差异的根源，并提出一种数据层面的预处理方法，使LLM在后续RL微调时能更有效地提升性能。
- **研究背景**：RL已成为LLM后训练的重要范式，尤其在数学推理、代码生成、Agent决策等任务中。传统RL关注算法改进和数据质量，但对初始化模型（特别是经过SFT后的模型）的质量关注不足。论文认为SFT阶段的数据质量决定性地影响后续RL的有效性。

## 2. 方法论：核心思想、关键技术细节与算法流程

- **核心思想**：通过分析RL目标的每步影响（per-step influence），识别出两个关键因素：  
  1. **RL信息性rollout准确率**（α）：中等准确率（0<α<1）的样本对RL更新贡献最大，准确率极端（0或1）时贡献为零。  
  2. **数据共影响系数（Kθ）**：衡量训练样本对目标域性能变化的影响强度，本质是模型梯度之间的内积（与神经正切核NTK相关）。

- **关键技术细节**：
  - **理论推导**：基于GRPO算法，在on-policy和小KL系数假设下，推导出每步影响ΔJ ∝ √(α(1-α)) × (正样本Kθ - 负样本Kθ)。因此，要增强RL效果，需（a）使rollout准确率分布更集中在中等区间；（b）增强正样本与目标样本的正共影响，减小负样本的负共影响。
  - **行为注入（BRIDGE）**：在SFT阶段对原始CoT数据进行数据增强，注入两类行为：
    - **探索行为**（exploration）：如提前尝试求解尚未可解的节点（locked node）然后反思（reflection），提高模型探索能力。
    - **利用行为**（exploitation）：如子目标计算（subgoal computation）、信息聚合分析（information analysis），增强模型从已知路径中学习的能力。
  - **算法流程**：  
    1. 从原始问答对中提取有向无环图（DAG）表示。  
    2. 生成探索行为：尝试解决一个locked节点后反思。  
    3. 生成利用行为：聚合信息以求解unlocked节点或计算子目标。  
    4. 以概率p将行为注入原始CoT，形成增强数据集。  
    5. 在增强数据集上做SFT，再执行RL微调。

## 3. 实验设计

- **数据集/场景**：
  - **iGSM**：可控难度的数学应用题，通过操作数（operation number）控制难度。SFT和RL用15~20操作数的数据训练，测试时分为in-distribution（20操作数）和out-of-distribution（25操作数）两组，各500个问题。
  - **PromptBench**：算数和逻辑推理任务，通过推理深度和冗余前提数控制难度。SFT用深度4、RL用深度5（0~8冗余前提）；测试集包括in-distribution（深度5，0~8冗余）和OOD（深度5，20~22冗余）两组。
- **基准模型**：Qwen-2.5（1.5B和3B）、Llama-3.2（1B）。
- **对比方法**：
  - Vanilla（原始SFT数据，无增强）
  - PP-Aug（前提排列增强）
  - RC-Aug（推理链拓扑序增强）
- **主要指标**：严格匹配准确率（strict match accuracy）。

## 4. 资源与算力

- **硬件**：2×NVIDIA A100（80GB）GPU服务器。
- **训练时长**：
  - SFT每个实验<1小时。
  - RL实验：Qwen-1.5B和Llama-1B在iGSM上200步约8小时，Qwen-3B在iGSM上100步约6小时；PromptBench上100步约2小时。
- 论文未明确说明使用的GPU数量（可能是单节点双卡），但提供了相对详细的资源信息。

## 5. 实验数量与充分性

- **主要实验组数**：
  - 在两个数据集（iGSM、PromptBench）、三个基座模型（总共6个主要实验）上评估。
  - 每个实验报告SFT和RL两个阶段的准确率，以及RL带来的增量（Δ）。
- **消融实验**：
  - 不同行为（子目标计算、反思、分析）的单独贡献（图4）。
  - 不同注入概率p（0.0, 0.1, 0.2, 0.3）的对比（图5）。
  - 与拒绝采样（rejection sampling）的对比（附录B.6，图11）。
- **分析实验**：
  - 展示不同方法下rollout准确率分布（图3中图）。
  - 计算并比较近似每步影响（图3右图）。
  - 测量模型熵和困惑度以验证探索/利用行为的有效性（图6）。
- **充分性和公平性**：
  - 实验覆盖了不同规模、不同家族的模型，以及分布内和分布外场景，结论较稳健。
  - 对比方法在计算量上做了公平处理（PP-Aug、RC-Aug通过扩增数据量保持大致相当的总计算量）。
  - 但iGSM和PromptBench都是合成数据，缺乏真实世界的复杂推理任务验证，覆盖面有限。

## 6. 主要结论与发现

- **核心发现**：行为注入（BRIDGE）显著提升了RL微调后的性能，且增量远大于其他数据增强方法。例如在iGSM上，Qwen-1.5B的RL增量从Vanilla的6%提升到46.6%（In-Dist），OOD上从7.4%提升到48.8%。
- **机制验证**：
  - BRIDGE使得rollout准确率更集中在中高区间（0<acc<1），增加了信息量。
  - BRIDGE显著提高了数据共影响系数（每步影响），即每个训练样本对目标性能的贡献更强。
- **行为效果**：
  - 探索行为（反思）增加模型生成熵（探索能力）。
  - 利用行为（子目标计算、分析）降低困惑度（利用能力）。
  - 组合使用比单一行为效果更好，尤其在较小模型（Llama-1B）上。
- **注入概率不敏感**：p=0.1,0.2,0.3效果差异不大，说明行为只要成功注入即可。
- **拒绝采样效果不佳**：仅通过筛选中等准确率样本未提升数据共影响，因此RL效果不如BRIDGE。

## 7. 优点

- **理论驱动**：从RL目标每步影响的数学分析出发，定量推导出影响RL效果的两个关键因子，增强方法有坚实的理论依据。
- **方法简洁高效**：BRIDGE无需修改RL算法或增加大量计算，仅通过SFT数据增强即可显著提升后续RL效果，且为任务无关的数据增强方案。
- **实验设计严谨**：使用合成数据避免数据污染，控制难度进行分布内/外测试，消融实验全面，分析实验深入（每步影响可视化、模型熵/困惑度）。
- **通用性**：在两种不同推理基准、三种不同基座模型上均取得一致效果，表明方法具有较好的泛化能力。

## 8. 不足与局限

- **任务覆盖有限**：仅评估了数学和逻辑推理的合成任务，未在真实世界的复杂推理（如竞赛数学、代码生成、多步Agent决策）上验证，泛化性有待进一步检验。
- **数据集规模较小**：SFT数据量仅2000~5000条，RL训练步数100~200步，在更大规模数据上的表现未知。
- **行为注入依赖DAG结构**：对于没有明显图结构或链式推理的任务，如何构造探索/利用行为不明确，附录虽提到可用LLM提取但未做充分实验。
- **计算开销隐忧**：虽然单次实验耗时在合理范围，但若要扩展到更大模型（如7B+）或更大数据规模，算力需求可能显著增加。
- **潜在负社会影响**：论文指出不安全行为注入可能造成危害，但未提供具体防护措施。
- **公平性**：对比的PP-Aug和RC-Aug主要是数据扩增，而非针对RL准备的行为级增强，与BRIDGE在动机上不完全对标，但论文通过实验表明拒绝采样等直接方式也无效，说明数据增强方向正确。

（完）
