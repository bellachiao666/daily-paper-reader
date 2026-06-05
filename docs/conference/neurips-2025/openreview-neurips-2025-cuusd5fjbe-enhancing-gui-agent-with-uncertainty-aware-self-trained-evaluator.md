---
title: Enhancing GUI Agent with Uncertainty-Aware Self-Trained Evaluator
title_zh: 增强GUI智能体：不确定性感知的自训练评估器
authors: "Gongwei Chen, Lirong Jie, Lexiao Zou, Weili Guan, Miao Zhang, Liqiang Nie"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=cuUsD5FJbe"
tags: ["query:agent-papers"]
score: 4.0
evidence: 不确定性感知强化自训练评估器
tldr: GUI代理训练中标注数据噪声大，现有评估器依赖大型专有模型。URST框架利用不确定性感知的强化自训练，让轻量级多模态模型迭代自我改进评估能力，从而有效筛选高质量轨迹。实验证明该方法在多个GUI基准上提升了代理性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-cuusd5fjbe/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 845, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cuusd5fjbe/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1431, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cuusd5fjbe/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 688, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cuusd5fjbe/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 684, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cuusd5fjbe/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1450, \"height\": 739, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cuusd5fjbe/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1436, \"height\": 1174, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cuusd5fjbe/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1450, \"height\": 758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cuusd5fjbe/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1372, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cuusd5fjbe/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 479, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cuusd5fjbe/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1438, \"height\": 969, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cuusd5fjbe/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1438, \"height\": 758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cuusd5fjbe/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1444, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cuusd5fjbe/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1445, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cuusd5fjbe/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1447, \"height\": 1207, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cuusd5fjbe/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1443, \"height\": 322, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-cuusd5fjbe/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1459, \"height\": 674, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cuusd5fjbe/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1302, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cuusd5fjbe/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1470, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cuusd5fjbe/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1400, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cuusd5fjbe/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1249, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cuusd5fjbe/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 595, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cuusd5fjbe/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 853, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cuusd5fjbe/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 961, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cuusd5fjbe/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 818, \"height\": 579, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cuusd5fjbe/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1192, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cuusd5fjbe/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1189, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cuusd5fjbe/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 731, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cuusd5fjbe/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 565, \"height\": 298, \"label\": \"Table\"}]"
motivation: GUI代理训练数据集噪声大，需要有效的轨迹质量评估方法，但现有评估器依赖昂贵的大模型。
method: 提出不确定性感知的强化自训练框架，迭代微调轻量级多模态模型，利用自身生成的想法和判断进行自我改进。
result: 在多个GUI导航任务上，自训练评估器显著提升了轨迹筛选质量和代理执行成功率。
conclusion: 不确定性驱动的自训练为GUI代理提供了一种高效、可扩展的评估方案。
---

## Abstract
Benefiting from the availability of extensive navigation trajectories, both manually and automatically annotated, current graphical user interface (GUI) agents have achieved remarkable advancements in performance. However, these annotated datasets often contain substantial noise, which impedes effective agent training and underscores the necessity for rigorous trajectory quality assessment. In contrast to existing prompting-based evaluators that rely on proprietary multimodal large language models (MLLMs), we propose an Uncertainty-aware Reinforced Self-Training (URST) framework to train lightweight MLLMs for efficient and reliable trajectory evaluation. URST iteratively fine-tunes MLLMs using their own generated thoughts and judgments to enable self-improvement, while its uncertainty-aware sampling strategy ensures the selection of the most informative training examples. To further enhance reasoning and judgment capabilities, we propose a simplified group policy optimization approach that effectively leverages diverse positive and negative samples for evaluator learning. Our evaluator demonstrates superior judgment performance across both in-domain and out-of-domain datasets. When used to filter navigation datasets, it consistently leads to performance improvements in training GUI agents.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将根据您提供的论文内容，进行结构化、深入、客观的总结。

---

### 论文核心总结

**标题：** Enhancing GUI Agent with Uncertainty-Aware Self-Trained Evaluator (用不确定性感知的自训练评估器增强GUI智能体)

**作者：** Gongwei Chen, Lirong Jie, Lexiao Zou, Weili Guan, Miao Zhang, Liqiang Nie (哈尔滨工业大学（深圳）)

**发表会议：** NeurIPS 2025

---

#### 1. 核心问题与整体含义 (研究动机和背景)

*   **核心问题：** 当前图形用户界面(GUI)智能体（如手机、电脑上的自动化操作代理）的性能极大依赖于大规模导航轨迹数据集。然而，这些数据集（无论是人工标注还是自动收集）普遍包含大量**噪声和错误轨迹**，这会严重干扰智能体的训练，导致其性能下降。因此，如何有效评估并筛选出高质量的轨迹数据成为一个关键挑战。
*   **现有方法的局限：** 已有的轨迹评估方法（如AutoEval, WebVoyager）大多依赖**提示工程(Prompting)** 调用昂贵的专有大型多模态模型（如GPT-4V）。这导致两大问题：
    1.  **领域差距：** 通用大模型缺乏对GUI场景特化的知识和判断力。
    2.  **高成本与延迟：** API调用成本高昂，且存在推理延迟。
*   **研究意义：** 本文旨在训练一个**轻量级、可本地部署**的开源多模态模型作为轨迹评估器，通过对数据进行高质量筛选，最终提升下游GUI智能体的性能。这为构建更高效、可扩展的GUI智能体训练流程提供了新思路。

#### 2. 方法论 (提出的方法)

*   **核心思想：** 提出一种**不确定性感知的强化自训练(URST)** 框架。该方法不依赖外部昂贵的专有模型，而是让轻量级多模态模型通过**自我迭代**的方式，利用自身生成的“思考”和“判断”来学习和提升评估能力。
*   **算法流程 (URST):**
    1.  **冷启动 (初始化):** 首先使用少量由专有模型（如Qwen-VL-Max）生成的轨迹评估数据（包含任务指令、轨迹、思维链和最终判断）对开源模型（如Qwen2.5VL-3B）进行**监督微调(SFT)**，得到初始评估器 $E_{init}$。
    2.  **不确定性感知采样:**
        *   对于一未标记的轨迹数据 $x_j$，使用当前评估器 $E_m$ 生成K个不同的评估结果 $(c_{kj}, y_{kj})$。
        *   计算这些结果中判断 $y$ 的**熵(Entropy)**。如果模型对同一个输入产生矛盾判断（高熵），说明该样本是模型难以处理的“硬样本”，信息量大。
        *   选择熵最高的Top-L个样本用于下一轮训练，从而避免引入“简单样本”导致的低效学习。
    3.  **迭代强化自训练 (使用简化组策略优化):**
        *   对选出的高不确定性样本，为其生成的K个结果分配奖励（格式奖励 + 判断正确性奖励）。
        *   **使用简化组策略优化(SGPO)** 进行微调。SGPO借鉴了组相对策略优化(GRPO)的思想，但**移除了标准差归一化**。作者认为，经过不确定性采样后，各组内奖励的标准差差异不大，归一化反而会过度强调信息量少的样本。
        *   SGPO通过计算每个输出相对于同组其他输出的**相对优势(Advantage)**，并利用`clip`机制和KL散度约束来稳定更新模型。这允许模型同时从**正样本和负样本**中学习，优于只学习正样本的拒绝采样微调。
    4.  重复步骤2和3，迭代M次，得到最终强大的评估器 $E_M$。

#### 3. 实验设计

*   **数据集/场景：**
    *   **训练集：** 基于Android-in-the-Wild (AITW)数据集的子集，分为1500条轨迹（全量SFT）和300条轨迹（URST初始阶段）。
    *   **测试集 (3个)：**
        1.  **AITW-ID-traj (域内):** AITW测试集中由人类执行的轨迹，人工标注了是否正确。
        2.  **AITW-OOD-traj (域外):** 与AITW-ID具有相同任务目标，但由另一智能体(CogAgent)生成，具有不同的轨迹分布。
        3.  **AW-OOD-traj (域外):** 在AndroidWorld在线环境中，由Agent Q智能体自动生成的轨迹，经人工标注。
*   **Benchmark (对比方法):**
    *   **基于提示的方法 (基线):** AgentTrek, WebVoyager, WebJudge, AutoEval, 以及 AutoEval的增强版 (AutoEval*)。
    *   **基于微调的基线:** 监督微调(SFT)，以及两种自训练方法( STaR, ReST$^{EM}$)。
*   **模型:** 基线方法使用QwenVL-Max，本文方法主要基于Qwen2.5VL-3B，也尝试了更小的Qwen2VL-2B。

#### 4. 资源与算力

*   **文中明确说明：** 所有实验均在**4块NVIDIA A100 40GB GPU**上运行。
*   **训练细节:**
    *   初始化SFT阶段使用300-1500条样本，训练2个epoch。
    *   每次URST迭代使用400条样本，训练4个epoch。
    *   所有训练均采用**全参数微调(Full-parameter Fine-tuning)**。
    *   使用了DeepSpeed Zero-3优化阶段和Flash Attention来提升内存效率。

#### 5. 实验数量与充分性

*   **实验数量：** 实验非常丰富，涵盖了：
    *   **主要结果对比 (Table 1):** 在3个测试集上与8种方法进行对比，涵盖了准确率和F1分数。
    *   **消融实验 (Table 2):** 验证了URST中各关键组件（不确定性采样、SGPO、归一化移除）的有效性。
    *   **关键参数分析 (Tables 3, 4):** 分析了迭代次数、采样数量K、不同熵计算方法的影响。
    *   **下游应用验证 (Tables 5, 6):** 验证了用URST评估器筛选数据后，对GUI导航智能体性能的提升，并测试了其在在线环境的反思(Reflexion)增强中的应用。
    *   **统计显著性 (Table 10):** 报告了使用3个随机种子的平均值和标准差，证实了结果的稳定性。
    *   **泛化性验证 (Table 13):** 将URST应用到Web任务评估基准(AgentRewardBench)上，证明了其泛化能力。
*   **充分性与公平性：**
    *   实验非常充分，从方法内部组件到外部应用，从域内到域外，从离线筛选到在线增强，覆盖全面。
    *   对比方法均为当前主流或经典方法，实现细节描述清楚。
    *   统计分析（误差棒）增强了结论的可靠性。
    *   消融实验清晰地证明了提出策略的必要性。

#### 6. 主要结论与发现

1.  **URST显著优于所有基线方法：** 在3个轨迹评估测试集上，URST的平均F1分数 (84.13%) 显著高于最好的提示方法 AutoEval* (81.48%) 和最好的微调方法 SFT (79.01%)。
2.  **自我生成数据优于蒸馏数据：** 使用URST自我生成的数据训练的评估器 (84.13% F1) 显著优于仅使用专有模型标注数据训练的SFT (79.01% F1)，证明了“自我改进”范式的强大潜力。
3.  **关键组件有效：** 消融实验证实，不确定性采样和SGPO对性能提升至关重要。去除任何一项都会导致性能大幅下降（分别下降6%和9.49%以上）。
4.  **提升下游智能体性能：** 将URST评估器用于筛选AITW和OS-Genesis等导航数据集，训练出的GUI智能体在步骤成功率上**一致提升**，尤其在噪声更高的数据上效果更显著。
5.  **具有良好的泛化性：** 在域外数据集上表现依然出色，并且能成功泛化到Web导航领域 (AgentRewardBench)。

#### 7. 优点 (亮点)

*   **方法创新性强：** 将**不确定性感知采样**和**简化组策略优化(SGPO)** 创新性地结合到自训练框架中，有效解决了传统自训练中容易陷入简单样本、利用负样本能力弱的问题。SGPO移除归一化的设计简洁且有效。
*   **实用性强且性价比高：** 目标是训练轻量级开源模型，摆脱了对昂贵专有API的依赖，降低了成本和部署门槛，具有很强的实际应用价值。
*   **实验设计严谨且全面：** 从基准测试、消融分析、参数影响、下游任务验证到泛化性评估，实验链条完整，论证过程逻辑严谨。提供了统计误差，保证了结果的可信度。

#### 8. 不足与局限

*   **模型泛化性有限：** 本文仅对Qwen2-VL / Qwen2.5-VL这一个系列模型进行了微调。虽然作者预期结论在其他模型上一致，但这仍需进一步验证。
*   **可能存在初始偏差放大：** 启动自训练的初始“种子数据”来自专有MLLM，其中可能包含特定偏见或错误。在自我改进的迭代循环中，这些初始偏差有被放大的风险，可能导致最终评估器在处理某些边缘案例或陌生界面时做出不公或错误的判断。
*   **任务覆盖有限：** 受限于计算资源，实验仅在AITW相关任务上进行训练和测试，未覆盖所有可能的移动或桌面场景。
*   **长上下文缺失风险：** 为降低计算开销，评估器在判断时**仅使用轨迹的最后两个状态截图**和动作历史。如案例分析所示，某些任务（如判断是否删除了特定项目）的关键证据可能位于更早的步骤，导致评估器因信息不足而判断错误。这是一个为了效率而牺牲部分精度的重要权衡。

（完）
