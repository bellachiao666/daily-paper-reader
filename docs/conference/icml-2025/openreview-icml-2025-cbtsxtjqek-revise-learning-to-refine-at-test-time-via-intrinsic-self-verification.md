---
title: "ReVISE: Learning to Refine at Test-Time via Intrinsic Self-Verification"
title_zh: ReVISE：通过内在自验证实现测试时细化学习
authors: "Hyunseok Lee, Seunghyuk Oh, Jaehyung Kim, Jinwoo Shin, Jihoon Tack"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=cBtsxtJqEK"
tags: ["query:agent-papers"]
score: 8.0
evidence: 通过偏好学习实现自验证与改进
tldr: LLMs缺乏自我评估与纠正能力。本文提出ReVISE框架，通过内在自验证机制让模型验证自身推理过程并持续重新思考。采用基于偏好学习的结构化课程高效实现。实验表明ReVISE在推理任务中有效提升了正确率，且无需外部验证器。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-cbtsxtjqek/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1067, \"height\": 800, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cbtsxtjqek/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 645, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cbtsxtjqek/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1521, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cbtsxtjqek/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 413, \"height\": 304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cbtsxtjqek/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 675, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cbtsxtjqek/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 747, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cbtsxtjqek/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 859, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cbtsxtjqek/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 509, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cbtsxtjqek/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 513, \"height\": 373, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 432, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 626, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 736, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 629, \"height\": 168, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 796, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 495, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1580, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1642, \"height\": 458, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1634, \"height\": 996, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1638, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1647, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1546, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1545, \"height\": 164, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1528, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1596, \"height\": 768, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1593, \"height\": 1124, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cbtsxtjqek/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1626, \"height\": 1948, \"label\": \"Table\"}]"
motivation: 现有方法依赖大量RL或外部验证器。
method: 利用偏好学习设计结构化课程，实施内在自验证与重新思考。
result: 在推理任务上提升了正确率。
conclusion: 内在自验证能以较低成本实现模型自我改进。
---

## Abstract
Self-awareness, i.e., the ability to assess and correct one's generation, is a fundamental aspect of human intelligence, making its replication in large language models (LLMs) an important yet challenging task. Previous works tackle this by employing extensive reinforcement learning or relying on large external verifiers. In this work, we propose Refine via Intrinsic Self-Verification (ReVISE), an efficient and effective framework that enables LLMs to self-correct their outputs through self-verification. The core idea of ReVISE is to enable LLMs to verify their reasoning processes and continually rethink reasoning trajectories based on its verification. To implement this efficiently, we introduce a structured curriculum based on preference learning. Specifically, as ReVISE involves two challenging tasks (i.e., self-verification and reasoning correction), we tackle each task sequentially using curriculum learning, collecting both failed and successful reasoning paths to construct preference pairs for efficient training. During inference, our approach enjoys natural test-time scaling by integrating self-verification and correction capabilities, further enhanced by our proposed confidence-aware decoding mechanism. Our experiments on various reasoning tasks demonstrate that ReVISE achieves efficient self-correction and significantly improves the reasoning performance of LLMs.

---

## 论文详细总结（自动生成）

# 中文总结：ReVISE: Learning to Refine at Test-Time via Intrinsic Self-Verification

## 1. 核心问题与整体含义（研究动机和背景）
- 大型语言模型（LLM）在复杂推理任务（如数学、编程）中容易在早期步骤积累错误，且缺乏自我评估与纠错能力（即“自我意识”）。
- 现有方法要么依赖昂贵的外部验证器（如大型奖励模型），要么采用复杂且不稳定的强化学习（RL），计算成本高且难以训练。
- 本文提出 **ReVISE**（Refine via Intrinsic Self-Verification），使LLM能够内在验证自己的推理过程，并基于验证结果主动修正错误，从而实现高效、自驱动的推理改进。

## 2. 方法论：核心思想、技术和算法流程
- **核心思想**：引入特殊 token `[refine]` 和 `[eos]`。模型首先生成初始推理结果 `y_init`，然后预测该 token：若预测 `[eos]` 则终止生成，若预测 `[refine]` 则生成修正后的推理 `y_refined`，完成自验证与自纠正循环。
- **关键技术细节**：
  - **两阶段课程学习**：
    - **阶段1：学习自验证**。基于输出正确性构造偏好对：正确推理 → 偏好 `[eos]`，错误推理 → 偏好 `[refine]`。使用 DPO（Direct Preference Optimization）损失 + SFT 损失联合优化。
    - **阶段2：学习自纠正**。从阶段1模型出发，对错误初始推理，构造正样本：`[refine]` + 正确答案；负样本：`[eos]`。同样使用 DPO + SFT 损失。
  - **偏好数据构造**：利用模型自身生成正确/错误推理路径，结合真实标签构建偏好对，无需 RL。
- **推理策略**：提出**置信度感知采样**（Confidence-Aware Majority Voting）。利用模型在验证 token 上的 softmax 概率 `M([eos] | y, x)` 作为置信度，对多次采样的答案加权投票，替代普通多数投票。

## 3. 实验设计
- **数据集**：
  - 数学推理：GSM8K（~8.8k 题）、MATH-500（MATH子集，500题）、MetaMath（增强版 MATH 训练数据）。
  - 代码生成：MBPP（编程问题）。
- **基准方法**：Few-shot CoT、SFT（监督微调）、RFT（Rejection Fine-Tuning）、STaR⁺（STaR 变体，含 SFT 初始化）。
- **模型**：Llama-3.2-1B（1B 参数，非指令调优）、Llama-3.1-8B（8B 参数）。额外验证指令调优模型（Llama-3.2-1B-Instruct）。
- **评估指标**：Maj@1（贪婪解码）、Maj@K（多数投票，K=5 为主），ReVISE 使用置信度加权投票。

## 4. 资源与算力
- **硬性配置**：训练使用 8× NVIDIA H100 GPU（显存 80GB），评估部分使用 NVIDIA RTX 4090 GPU。
- **训练细节**：AdamW 优化器，学习率 1e-4 或 1e-5，10% 预热及余弦衰减；Batch size 32（微调）或 64（偏好调优）；训练 1 个 epoch。
- **采样量**：每个样本在 GSM8K 上采样 10 次，在 MATH 上采样 4 次用于构建偏好对。
- **未明确信息**：训练总时长和 GPU 小时数未在文中报告。

## 5. 实验数量与充分性
- **主实验**：表1给出 GSM8K 和 MATH-500 上 Maj@1 和 Maj@5（2 类模型 × 2 数据集 × 4 组方法 + ReVISE），表2给出 MBPP Pass@1。
- **消融与分析实验**（约8个）：
  - 课程学习效果（图3）、DPO 损失必要性（图4）、置信度分布可视化（图5）
  - 置信度采样与其他方法对比（图6）、细化 vs 随机重试（图7）
  - 迭代细化效果（图8）、领域泛化（表4）、指令调优模型实验（表3）
  - 与 V-STaR 自验证器 AUROC 对比（表7）、与 SCoRe 效率/性能对比（表6）
  - 扩展测试时缩放（表8，Maj@2~64）
- **充分性评估**：实验数量充足，覆盖关键维度（数据集、模型规模、组件消融、泛化、迭代、与 RL 方法比较），对比公平（同一基模型、相同采样数）。但在多样化领域（如常识推理、科学问答）上未展开，略有限制。

## 6. 主要结论与发现
- ReVISE 在 GSM8K、MATH-500、MBPP 上**显著优于** SFT、RFT、STaR⁺ 等基线，尤其在 Llama-3.1-8B 上提升 4~10% 绝对准确率。
- 自验证（两阶段课程）和置信度采样式均贡献显著，**缺一不可**（图3/4）。
- 自验证置信度 `M([eos])` 与真实正确性高度对齐（图5），因此加权投票比普通多数投票更有效（图6）。
- ReVISE 能够**有意义地修正错误**，而非随机重试（图7）。
- 在指令调优模型上，ReVISE 依然保持性能，而其他基线出现灾难性遗忘（表3）。
- 领域泛化（MATH→GSM8K）效果良好（表4），迭代细化可进一步提升（图8）。
- 训练效率远高于 RL 方法（如 SCoRe），30× 更低生成量即达到更高准确率（表6）。

## 7. 优点
- **高效性**：无需外部验证器或复杂 RL，仅需偏好学习 + 课程微调，训练成本远低于同类方法。
- **内在可解释性**：显式的 `[refine]/[eos]`  token 提供推理路径是否正确的直观信号，便于分析和调试。
- **测试时扩展优势**：自验证置信度可直接用于加权采样，无需额外模型，且在少量样本下即能提升稳定性。
- **鲁棒性**：在指令调优模型、不同领域转移、迭代细化下均保持改善，不易退化。
- **开源代码**：便于复现和社区应用。

## 8. 不足与局限
- **领域覆盖有限**：仅在数学和代码任务上验证，未探索常识推理、多步问答、科学问题等更广场景。
- **依赖标签**：构造偏好对需要真实答案（ground-truth），在无标注任务上不直接适用。
- **小模型为主**：实验限于1B/8B参数量，在更大模型（如 70B）上的行为未报告。
- **阶段2的轻微退化**：训练自纠正阶段会导致自验证 AUROC 轻微下降（图3b），表明存在灾难性遗忘，文中未提出缓解策略。
- **领域泛化幅度有限**：例如 MATH 训练的 1B 模型在 GSM8K 上仅 8.8%，性能绝对值仍低，模型容量可能是瓶颈。
- **未与更先进的推理型模型比较**：如 o1 或基于过程监督的模型，缺乏最先进水平对比。
- **单项细化限制**：训练仅支持单轮自纠正，多轮细化虽可在推理时迭代，但未经专门训练，效果可能有上界。

（完）
