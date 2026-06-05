---
title: Self-Challenging Language Model Agents
title_zh: 自挑战语言模型智能体
authors: "Yifei Zhou, Sergey Levine, Jason E Weston, Xian Li, Sainbayar Sukhbaatar"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=9yusqX9DpR"
tags: ["query:agent-papers"]
score: 9.0
evidence: 代理自我生成挑战性任务并自我改进的框架
tldr: 训练工具使用智能体需要大量人工标注的任务和评估标准，成本高昂。本文提出自挑战智能体框架，代理首先扮演挑战者角色，通过与环境工具交互生成高质量任务（形式化为Code-as-Task，含指令、验证函数和测试用例），然后扮演执行者角色完成任务并从结果中学习。该框架实现了无需人工干预的递归自改进，显著提升了智能体的泛化能力和任务完成率。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-9yusqx9dpr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1373, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9yusqx9dpr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9yusqx9dpr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 577, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9yusqx9dpr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1426, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9yusqx9dpr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9yusqx9dpr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1445, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9yusqx9dpr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 857, \"height\": 868, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9yusqx9dpr/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1378, \"height\": 1034, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9yusqx9dpr/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1396, \"height\": 1882, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9yusqx9dpr/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1385, \"height\": 1857, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9yusqx9dpr/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1398, \"height\": 1001, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9yusqx9dpr/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1402, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9yusqx9dpr/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1394, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9yusqx9dpr/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1390, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9yusqx9dpr/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1308, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9yusqx9dpr/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1339, \"height\": 677, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-9yusqx9dpr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 543, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9yusqx9dpr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1453, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9yusqx9dpr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1454, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9yusqx9dpr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 661, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9yusqx9dpr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1448, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9yusqx9dpr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 946, \"height\": 928, \"label\": \"Table\"}]"
motivation: 训练工具使用智能体需要大量人工创建和标注的任务，限制了扩展性。
method: 智能体自我生成Code-as-Task任务并执行，通过筛选高质量任务进行自我训练。
result: 自挑战智能体在多种工具使用任务上取得了优于人类标注数据的性能，且具备持续改进能力。
conclusion: 自生成任务框架是实现智能体递归自改进的有效途径。
---

## Abstract
Large language models  are quickly becoming the foundation for intelligent agents that are capable of using tools. However, training such agents is challenging because it requires human creation and annotation of a diverse set of tasks, tools, and evaluation criteria. In this paper, we propose  the Self-Challenging Agent framework for training an agent on high-quality tasks that are generated by itself. The agent first plays the role of challenger and generates a task after interacting with the given tools. The tasks take the form of a novel general class of problems termed Code-as-Task, which are defined by an instruction, a verification function and solution and failure cases which serve as tests, allowing to filter only for high-quality tasks.  
The agent then takes an executor role and trains on those tasks with reinforcement learning using the evaluation feedback as a reward.  We show our method improves the performance of Llama-3.1-8B-Instruct on two existing multi-turn tool-use agent benchmarks, M$^3$ToolEval and TauBench, with a two-fold average success rate increase, despite using only self-generated training data.

---

## 论文详细总结（自动生成）

# 自挑战语言模型智能体（Self-Challenging Language Model Agents）——论文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：训练大型语言模型（LLM）作为智能体（agent）时，需要大量高质量的任务数据、工具集和评估标准。传统依赖人工创建和标注的成本高、扩展性差，限制了智能体在开放环境（如多轮工具使用、GUI 导航）中的泛化能力。
- **研究动机**：探索一种自动化的任务生成与自我改进框架，使 LLM 智能体能够通过与环境交互自主生成挑战性任务，并利用这些任务进行强化学习训练，从而在不依赖人工数据的情况下提升性能。
- **整体含义**：本文提出 **自挑战智能体（Self-Challenging Agent, SCA）** 框架，智能体同时扮演“挑战者”（生成任务）与“执行者”（学习完成任务）两个角色，通过“代码即任务”（Code-as-Task, CaT）格式确保任务的高质量（可行、可验证、有难度），实现了自我改进与蒸馏两种学习范式。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：智能体自发探索环境，生成带有验证函数的任务，然后在这些任务上通过强化学习（RL）或监督微调（SFT）进行训练。
- **关键技术细节**：
  - **两角色架构**：
    - **挑战者（Challenger）**：与环境工具交互，收集信息，生成任务规范。任务规范包含：指令（instruction）、验证函数（verification function）、示例解决方案（example solution）、三个失败案例（failure cases）。验证函数以 Python 代码形式给出，可自动执行。
    - **执行者（Executor）**：在验证通过的任务上进行轨迹采样，根据验证函数的 0/1 奖励进行训练。
  - **代码即任务（Code-as-Task, CaT）**：一种任务表示形式，将指令、验证函数、示例解决方案、失败案例均以代码形式表达，利用外部代码执行器自动过滤低质量任务（如不可行、验证函数有误等），保证任务质量。
  - **学习方式**：
    - **自我改进（Self-Improvement）**：挑战者与执行者为同一模型（Llama-3.1-8B），生成任务后，执行者采样轨迹，使用 REINFORCE 或等价于“拒绝微调”的算法训练，只保留验证函数返回 1 的成功轨迹。
    - **蒸馏（Distillation）**：使用更强的模型（如 Llama-3.1-70B）作为执行者，在自生成任务上采样轨迹，对弱模型（Llama-3.1-8B）进行监督微调。
- **公式与流程**：文本中给出了 REINFORCE 目标函数（公式 2）和 SFT 损失（公式 3），但核心流程是：挑战者探索 → 生成 CaT → 自动过滤 → 执行者采样 → 利用奖励更新策略。

## 3. 实验设计：数据集、Benchmark、对比方法

- **数据集/场景**：两个多轮工具使用基准：
  - **M$^3$ToolEval**：包含 **Calculation**（工具计算）和 **Web Browsing**（文本网络浏览）两个环境。
  - **TauBench**：包含 **Retail**（零售客服）和 **Airline**（航空订票）两个环境，模拟真实用户服务场景。
- **Benchmark**：每个环境都有自带的验证器，用于评估最终成功与否（Pass@1 和 Pass@4）。
- **对比方法**：
  - **零样本基线**：GPT-4o、Llama-3.1-70B、Llama-3.1-8B（无微调）。
  - **PAE（Proposer-Agent-Evaluator）**：之前最先进的自发任务合成与自我改进方法，仅通过 API 文档或初始观察生成指令，并用同一模型自评成功性（不使用代码验证）。
  - **SCA（本文方法）**：分为自我改进和蒸馏两个设置，均使用 800 个自生成任务和 12k 条离线轨迹。

## 4. 资源与算力

- **明确说明**：参看论文附录 E（Table 5）。主要实验在 **8×A100 80G** 上运行。
  - 各环境任务生成：Calculation 和 Web Browsing 各 8 小时，Retail 和 Airline 各 32 小时。
  - 轨迹生成：每个环境 24 小时。
  - 拒绝微调：每个环境 3 小时。
  - 评估：Calculation 和 Web Browsing 各 0.5 小时，Retail 2 小时，Airline 1 小时。
  - 总计算量较大，但具体总 GPU 小时数可由上述数据加总。

## 5. 实验数量与充分性

- **主要实验**：在 4 个环境上进行了蒸馏和自我改进两个设置的对比，每个设置报告了 Pass@1 和 Pass@4 四次独立运行的平均结果。
- **消融实验**：
  - 不同 RL 算法（Rejection Fine-Tuning, DPO, PPO, GRPO）在 Calculation 上的对比（图 3）。
  - CaT 各组件（仅指令+验证、加解决方案、再加失败案例）的人类标注质量分析（图 4）。
  - 任务难度分布对比（图 5）。
  - 数据量标度分析（任务数量 vs 轨迹数量，图 6）。
  - 蒸馏中是否使用失败轨迹的消融（表 3）。
  - 跨环境迁移分析（表 2）。
  - 与 oracle 任务的对比（图 7）。
  - 过滤有效性的消融（表 4）。
- **充分性**：实验覆盖了多个环境、多种学习设置（零样本、自我改进、蒸馏）、多种 RL 算法、任务组件消融、数据量标度等，比较全面。但缺乏在更多样化环境（如真实网站、机器人控制）上的验证，且仅使用一种基础模型（Llama-3.1-8B），可能限制泛化结论。

## 6. 主要结论与发现

- **蒸馏设置**：SCA 在 Llama-3.1-8B 上实现平均绝对成功率提升 +20.2%（从 12.0% 到 32.2%），优于 PAE（30.1%）。在部分可观测环境（Web Browsing、Retail、Airline）中优势更明显。
- **自我改进设置**：SCA 将成功率从 12.0% 提升至 23.5%，比 PAE（12.9%）高出约 10.6 个百分点，尤其在 Airline 环境上 SCA 获得了 4.2% 而 PAE 为 0%。
- **CaT 过滤效果**：自动过滤大幅减少假阳性（FP）和假阴性（FN），任务质量显著提升。完整 CaT 的假阳性被完全消除。
- **任务多样性**：过滤不会破坏弱模型的合理任务分布，但对强模型（70B）保持多样性更好。
- **数据标度**：增加任务数量比增加每个任务的轨迹数量更能提升 OOD 泛化性能。
- **RL 算法兼容性**：在线方法（PPO、GRPO）可进一步提升性能但更不稳定；离线方法（拒绝微调、DPO）稳定且已有显著提升。

## 7. 优点：方法或实验设计上的亮点

- **创新性**：首次将“代码即任务”（CaT）形式化用于自生成任务的质量控制，利用代码执行器自动过滤不可行或错误的验证函数，显著提升任务质量。
- **完全自主**：不需要任何人工标注或预定义任务集，智能体通过与环境交互即可产生高质量训练数据。
- **通用性强**：适用于多种工具丰富的环境（计算、网络浏览、零售、航空），不依赖于特定环境设计。
- **实验设计细致**：包括人类标注分析（图 4）验证各组件必要性，数据标度分析（图 6）指导资源分配，与 oracle 任务对比（图 7）说明上限，方法消融全面。
- **实用性**：同时支持蒸馏（利用强模型）和自我改进（单一模型自提升）两种实用场景。

## 8. 不足与局限

- **剩余假阴性**：尽管 CaT 减少了假阴性，但仍存在因指令语义模糊或缺失信息导致的假阴性（图 4），论文未提出有效解决此问题的方案。
- **任务分布偏差**：CaT 过滤可能对较弱模型造成任务分布收敛（图 5a），强模型则保持较好多样性，说明该方法依赖模型的初始能力。
- **跨环境迁移有限**：表 2 显示联合训练并未提升性能，说明改进主要针对环境特定技能，而非通用的 agentic 能力。
- **环境覆盖有限**：仅在 4 个模拟环境中测试，未在真实网站（如 WebArena）或机器人控制等更复杂场景验证。
- **计算成本高**：任务生成和轨迹采样需要大量 GPU 时间（尤其 Retail 和 Airline 各 32+24 小时），且重复多次实验成本更高。
- **稳定性问题**：在线 RL 方法（GRPO）在训练后期可能崩溃（图 3），需额外调参。

（完）
