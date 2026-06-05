---
title: Adaptive Self-improvement LLM Agentic System for ML Library Development
title_zh: 面向ML库开发的自适应自改进LLM智能体系统
authors: "Genghan Zhang, Weixin Liang, Olivia Hsu, Kunle Olukotun"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=gdsZ3uMPsY"
tags: ["query:agent-papers"]
score: 8.0
evidence: 自适应自改进LLM智能体系统，通过迭代改进进行复杂推理
tldr: 该论文提出一个自适应自改进智能体系统，使LLM能迭代地为ML库开发生成高性能代码。系统通过迭代改进机制，在有限数据下进行复杂推理。实验表明生成代码质量逐步提升，适用于架构特定语言。体现了递归自改进在LLM智能体中的应用。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-gdsz3umpsy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 858, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdsz3umpsy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 831, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdsz3umpsy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 867, \"height\": 821, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdsz3umpsy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 858, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdsz3umpsy/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1707, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdsz3umpsy/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1723, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdsz3umpsy/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1675, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdsz3umpsy/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 849, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdsz3umpsy/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 848, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdsz3umpsy/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 844, \"height\": 630, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdsz3umpsy/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1776, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdsz3umpsy/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1773, \"height\": 439, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-gdsz3umpsy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 1069, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdsz3umpsy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 844, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdsz3umpsy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 659, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdsz3umpsy/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1158, \"height\": 450, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdsz3umpsy/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1701, \"height\": 714, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdsz3umpsy/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1363, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdsz3umpsy/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 620, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdsz3umpsy/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 751, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdsz3umpsy/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1101, \"height\": 324, \"label\": \"Table\"}]"
motivation: ML库开发需要专家知识，LLM在有限示例下难以完成复杂ASPL编程。
method: 构建自改进循环：智能体迭代生成代码，评估错误并反馈，微调LLM以改进后续生成。
result: 在ML库生成任务中，代码性能和正确性随迭代显著提升。
conclusion: 验证了自改进LLM智能体在复杂领域代码生成中的有效性。
---

## Abstract
ML libraries, often written in architecture-specific programming languages (ASPLs) that target domain-specific architectures, are key to efficient ML systems. However, writing these high-performance ML libraries is challenging because it requires expert knowledge of both ML algorithms and the ASPL. Large language models (LLMs), on the other hand, have shown general coding capabilities. However, challenges remain when using LLMs for generating ML libraries using ASPLs because 1) this task is complicated even for human experts and 2) there are limited code examples due to the esoteric and evolving nature of ASPLs. We present an adaptive self-improvement agentic system that enables LLMs to perform such complex reasoning under limited data by iteratively improving their capability through self-generated experience. In order to evaluate the effectiveness of our system, we construct a benchmark of a typical ML library and generate ASPL code with both open and closed-source LLMs on this benchmark. Our results show improvements of up to $3.9\times$ over a baseline single LLM.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- ML库通常使用面向特定领域架构的架构特定编程语言（ASPL，如CUDA、HIP、Pallas、STeP）编写，是高效ML系统的关键。
- 然而，开发此类库需要同时精通ML算法和ASPL，即便对人类专家也极具挑战。同时，ASPL发展迅速、示例代码稀缺，LLM直接生成面临困难。
- 论文目标是使LLM能在有限数据下进行复杂推理，自动生成高质量ML库代码。

## 2. 方法论：核心思想、关键技术细节

### 核心思想

- 构建**自适应自改进循环**：LLM智能体通过自身生成的体验迭代提升能力。该循环完全自动化，无需人工干预（除ASPL设计者初始告知基元用法）。

### 关键技术细节

1. **自适应自改进学习算法（Algorithm 1）**
   - 输入：任务集X，自适应粒度m
   - 过程：
     - 并行采样：当前智能体对剩余任务生成多个解答，记录成功率Ct
     - 筛选高质量答案：过滤函数σ用AST同构分组，随机选一人代表，再取纯代码最短的作为经验存储
     - 分层与选择：函数β按成功率升序将经验分为m个难度级别，演示从最硬开始逐步加入更易的
     - 自适应更新：若在某层有新完成的任务，则加入经验，然后重新从最硬层开始采样；若该层无新任务，则增加演示包含更易数据
     - 终止条件：所有任务完成或所有演示用完
   - 特点：优先利用"艰苦获得"的经验（类似课程学习），自适应增大测试时计算量，提高数据效率。

2. **智能体系统组织**
   - **提议者（Proposer）**：生成候选STeP实现，基座提示包含ASPL引用和用法模式。
   - **守护者（Guardian）**：检查并纠正仿射类型约束（每个流只能被消费一次），由融合门和纠正器组成。
   - **代码生成器**：将智能体输出转换为自包含的可执行Python脚本（含功能模拟器）。
   - **验证器**：两个验证器——功能正确性（将输出与PyTorch参考结果对比）和仿射类型约束（静态分析AST）。
   - **结构化中间表示（Structural IR）**：使用YAML序列化任务信息，减少冗余提示，提升接口效率。

## 3. 实验设计

- **基准测试**：构建了包含26个任务、8组ML算子的基准，覆盖常见LLM层（注意力、矩阵乘法、归一化、RoPE、MoE的索引/专家/端到端等）。任务难度均匀，包含动态、静态矩阵、静态向量三类。
- **对比方法**：
  - 单个LLM基线
  - 无结构IR的单个LLM
  - 智能体系统（提议者+守护者）
  - 自适应自改进智能体系统（本文方法）
- **模型**：Claude 3.5 Sonnet, GPT-4o, DeepSeek-V3, Llama 3.1-405B（也测试了OpenAI-o1但不作为主要对比）。
- **指标**：Pass@k（期望成功率），主要用Pass@n（所有样本下解决问题比例）。

## 4. 资源与算力

- 论文**未明确说明**使用的GPU型号、数量或训练时长。仅提及在API调用中采样64次（温度0.4, 0.7, 1.0）进行实验，以及使用OpenAI、Anthropic等商业API。缺乏硬件资源详细披露。

## 5. 实验数量与充分性

- **实验数量**：较多，包括：
  - 自适应学习曲线分析（图7、8、11）：对3个主要模型分别记录多轮迭代
  - 不同模型性能对比（表4、图2、图12）
  - 消融研究：结构IR vs 无IR（图9、表1）、代理系统 vs 单个LLM（表2）、自适应粒度m调参（图8）
  - 额外实验：监督微调对比（表6）、复杂度与可维护性评估（表7）、泛化到AIME-2024等
  - 公平性实验：匹配token数后对比（表5）
- **充分性**：消融全面，覆盖关键设计决策，对比了多种开源/闭源模型，并且在部分实验中控制了测试时计算。但自适应粒度调参仅在GPT-4o上进行，泛化实验仅用AIME-2024数学题，领域覆盖有限。

## 6. 主要结论与发现

- 自适应自改进系统在所有模型上显著提升，最高达**3.9倍**（GPT-4o Pass@n从0.23到0.81；Claude Sonnet从0.73到0.96）。
- 硬示例比混合示例更高效；混合示例是发现新硬示例所必需的。
- 结构IR通过增加样本多样性提升性能；守护者代理有效纠正仿射类型错误（解决5个重用任务），但可能破坏正确输出（轻微降低Arith-Once的Pass@1）。
- 自改进优于监督微调（SFT），相同初始数据下Pass@n从0.62提升到0.81（SFT） vs 0.81（自改进）。
- 系统能完成高达96%的任务，并发现非平凡的STeP程序（如FlashAttention-2风格的在线softmax）。

## 7. 优点

- **方法创新**：将课程学习思想融入智能体自改进，自适应分层选择经验，提高数据效率；结构化IR接口设计提升多样性。
- **实验全面**：涵盖多种模型、多维度消融、公平性控制、泛化验证、维护性评估。
- **显著效果**：相对单LLM基线提升3.9倍，任务完成率96%。
- **可复现与开放**：代码开源，提示示例公开。

## 8. 不足与局限

- **仅验证功能正确性**，未考虑性能优化（如吞吐、内存效率）。模拟器仅仿真功能，未评估实际硬件性能。
- **仅针对STeP语言**，对CUDA/HIP等其他ASPL的适应性未充分验证（虽讨论泛化，但未实验）。
- **守护者代理可能引入错误**（降低Arith-Once Pass@1），表明多轮验证仍有改进空间。
- **自适应粒度调参仅对GPT-4o**，可能不具普遍性。
- **算力资源未汇报**，难以评估训练/推理成本；API调用实验受限于模型供应商的收费和速率限制。
- **未与真实人类专家直接对比**（仅提试点性观察，无系统对比）。
- **基准规模较小**（26个任务），可能不足以代表真实ML库的多样性。
- **泛化实验薄弱**：仅在AIME-2024数学题上验证，未在更广泛的代码生成或推理任务上测试。

（完）
