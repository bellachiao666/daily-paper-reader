---
title: Teaching Language Models to Critique via Reinforcement Learning
title_zh: 通过强化学习教会语言模型进行批评
authors: "Zhihui Xie, Jie chen, Liyu Chen, Weichao Mao, Jingjing Xu, Lingpeng Kong"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=UVoxPlv5E1"
tags: ["query:agent-papers"]
score: 9.0
evidence: 强化学习训练批评家实现迭代改进
tldr: 训练LLM进行自我批评和改进是重要但困难的任务。本文提出CTRL框架，通过强化学习训练一个批评模型，使其生成的反馈能最大化固定生成模型的修正效果，无需人工监督。在代码生成任务上，CTRL显著提升了通过率并减少了错误累积。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-uvoxplv5e1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 842, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uvoxplv5e1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1709, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uvoxplv5e1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 753, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uvoxplv5e1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 842, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uvoxplv5e1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 837, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uvoxplv5e1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 806, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uvoxplv5e1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 814, \"height\": 322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uvoxplv5e1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1540, \"height\": 623, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uvoxplv5e1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1574, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uvoxplv5e1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 748, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uvoxplv5e1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 783, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uvoxplv5e1/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1671, \"height\": 1283, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uvoxplv5e1/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1673, \"height\": 725, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-uvoxplv5e1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 770, \"height\": 412, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvoxplv5e1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 681, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvoxplv5e1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1686, \"height\": 869, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvoxplv5e1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 686, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvoxplv5e1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 801, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvoxplv5e1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1620, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvoxplv5e1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 862, \"height\": 737, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvoxplv5e1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 543, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvoxplv5e1/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 591, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvoxplv5e1/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1668, \"height\": 1688, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvoxplv5e1/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1671, \"height\": 1283, \"label\": \"Table\"}]"
motivation: 现有方法难以提供准确的判断和可行的建议。
method: 使用强化学习训练批评模型以优化生成模型的修正性能。
result: 在代码生成中显著提升通过率并减少错误累积。
conclusion: 强化学习可有效训练批评模型实现迭代改进。
---

## Abstract
Teaching large language models (LLMs) to critique and refine their outputs is crucial for building systems that can iteratively improve, yet it is fundamentally limited by the ability to provide *accurate judgments* and *actionable suggestions*. In this work, we study LLM critics for code generation and propose $\texttt{CTRL}$, a framework for $\texttt{C}$ritic $\texttt{T}$raining via $\texttt{R}$einforcement $\texttt{L}$earning, which trains a critic model to generate feedback that maximizes correction performance for a fixed generator model without human supervision. Our results demonstrate that critics trained with $\texttt{CTRL}$ significantly enhance pass rates and mitigate compounding errors across both base and stronger generator models.
Furthermore, we show that these critic models act as accurate generative reward models and enable test-time scaling through iterative critique-revision, achieving up to 106.1\% relative improvements across challenging code generation benchmarks.

---

## 论文详细总结（自动生成）

# Teaching Language Models to Critique via Reinforcement Learning 论文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：大型语言模型（LLM）在自我改进（self-improvement）中依赖反馈机制，但现有反馈（如奖励模型的标量分数或执行追踪的低级信息）难以同时提供**准确判别**和**可行的改进建议**，导致迭代优化效果有限甚至退化（错误累积）。
- **背景**：代码生成领域已有执行反馈（单元测试）可用，但直接使用往往难以驱动实质性改进。作者将问题归结为“反馈瓶颈”（feedback bottleneck），并指出需要一个专门的批评模型（critic）来弥补这一缺口。

## 2. 方法论：核心思想、关键技术细节、算法流程
- **核心思想**：将批评模型与任务生成模型解耦，通过强化学习训练批评模型，使其生成的文本反馈能**最大化固定生成模型**的修正成功率，无需人工监督。
- **关键技术细节**：
  - **Two-Stage Training Pipeline**:
    - **Stage I：执行引导的批评合成（Execution-guided Critique Synthesis）**
      - 利用沙盒执行结果（通过/失败/错误）构造提示模板，引导模型合成高质量批评。
      - 进行监督微调（SFT），让模型内化批评格式和判别能力。
    - **Stage II：强化批评生成（Reinforced Critique Generation）**
      - 使用**Group Relative Policy Optimization (GRPO)** 进行优化，避免价值网络导致的训练不稳定。
      - 每次采样一组批评（G=8），计算组内相对优势（advantage），并加入KL散度正则化防止过优化。
  - **批评空间设计**：包含分析（Analysis）、改进建议（Improvement suggestions）和最终判断（Correct/Incorrect）三部分，支持多轮迭代。
- **公式（简述）**：优化目标为最大化改进后解决方案的期望正确率，通过GRPO更新批评模型参数。

## 3. 实验设计
- **数据集**：
  - **训练数据**：TACO（26,443个竞赛编程问题），过滤后得到18,820个问题。
  - **评估基准**：CodeContests（竞赛难题）、LiveCodeBench（24.08-24.11，低污染）、MBPP+（基础编程）、JudgeBench（判准能力，含通用知识/推理/数学/代码）。
- **对比方法**：
  - 零样本（Zero-shot）
  - 自批评（Self-critique）和自批评+执行反馈
  - 使用更强模型（GPT-4o）作为批评
  - SFT版批评 vs RL版批评 (CTRL)
  - 多轮迭代版本（×2, ×3, ×5）
- **评估指标**：Pass@1（最终通过率）、Δ↑（错误→正确的比例）、Δ↓（正确→错误的比例）、F1分数（判别能力）、准确率（JudgeBench）。

## 4. 资源与算力
- **文中未明确说明**所使用的GPU型号、数量及训练时长。
- 仅提到使用**SandboxFusion**作为执行环境，Qwen2.5-Coder-32B-Instruct作为批评基础模型，训练使用了VeRL框架（开源RL库），SFT和RL的超参数如表8、9所示（学习率、batch size等），但未提及具体硬件配置与时间消耗。

## 5. 实验数量与充分性
- **实验数量丰富**：
  - 4个主要基准（CodeContests, LiveCodeBench, MBPP+, JudgeBench），每个基准上测试多种批评方法（自批评、GPT-4o、CTRL等）。
  - 包含单轮和多轮迭代（最多5轮）比较。
  - 进行了消融（SFT vs RL）、不同生成器（Qwen2.5-Coder vs GPT-4o）、不同模型大小（7B/14B/32B）实验。
  - 模拟分析（图3）和支持性分析（代码相似性、超时率、错误累积率等）。
- **充分性与公正性**：
  - 使用5个随机种子取平均，报告标准误差，统计严谨。
  - 评估基准覆盖多难度和领域，并特意选用LiveCodeBench避免数据污染。
  - 对比方法包括当时最强公开模型（GPT-4o）及消融变体，设置合理。

## 6. 主要结论与发现
- **RL显著提升批评能力**：CTRL在单轮迭代中Pass@1从零样本7.88%提升至11.76%（Qwen2.5-Coder生成器），且Δ↓极低（0.85% vs SFT的3.03%）。
- **实现测试时缩放（Test-time Scaling）**：多轮迭代（3-5轮）进一步提升性能（CodeContests上达106.1%相对提升），且错误累积率远低于基线方法。
- **弱-to-强泛化**：使用较弱模型（Qwen2.5-Coder-32B）训练的批评能有效指导更强模型（GPT-4o）改进。
- **作为生成式奖励模型**：在JudgeBench代码分类上达到64.3%准确率，与Claude-3.5-Sonnet持平，且优于GPT-4o。
- **稳定性与效率**：CTRL批评鼓励大的结构修改（代码相似度更低），同时通过低回归率保证迭代可靠性。

## 7. 优点
- **方法创新**：将批评模型与生成器解耦，并首次将GRPO用于批评生成训练，有效缓解价值网络不稳定问题。
- **无需人工标注**：完全依赖执行反馈和模型自身推理合成批评数据，成本低、可扩展。
- **强泛化能力**：训练于单一生成器的批评可跨不同生成器（包括更强的GPT-4o）和跨领域（从代码到JudgeBench判准）推广。
- **实验充分**：大量消融、多轮迭代、多个基准、多个种子统计，结论可靠。
- **实际意义**：为LLM自主迭代改进提供了可行且高效的训练范式，可降低对强大模型的依赖。

## 8. 不足与局限
- **计算资源未说明**：缺少GPU型号、数量及训练时间，难以复现和比较资源成本。
- **领域限制**：主要聚焦代码生成，虽在JudgeBench上测试了通用判准能力，但未在更广的自然语言生成任务（如文本摘要、问答）上验证。
- **多轮泛化的局限性**：训练仅基于单轮批评-修正，模型在多轮交互中的稳定性仍可能面临未知退化（虽实验中较低）。
- **时间效率**：CTRL批评生成的解决方案超时率较高（16.61%），可能牺牲执行效率换取准确率，需在实际部署中平衡。
- **依赖沙盒执行**：Stage I的批评合成需要可执行环境和单元测试，不适用于无自动验证的领域。
- **潜在偏差**：训练数据来自竞赛编程（TACO），可能偏向某些解题风格，对实际应用场景的覆盖有限。

（完）
