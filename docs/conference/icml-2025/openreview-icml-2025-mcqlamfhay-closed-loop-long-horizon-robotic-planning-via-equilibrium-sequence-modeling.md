---
title: Closed-Loop Long-Horizon Robotic Planning via Equilibrium Sequence Modeling
title_zh: 通过均衡序列建模的闭环长时域机器人规划
authors: "Jinghan Li, Zhicheng Sun, Yadong MU"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=MCqlamfhAy"
tags: ["query:agent-papers"]
score: 8.0
evidence: 自求精迭代计划优化用于长时域规划
tldr: 本文针对机器人长时域任务规划易出错的问题，提出了一种自求精规划方法，通过迭代优化初始计划直至达到均衡状态，无需额外验证器或奖励模型，即可端到端优化。实验表明该方法在复杂长期任务上显著优于基线，为智能体自主规划提供了简洁高效的训练范式。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-mcqlamfhay/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1658, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mcqlamfhay/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1694, \"height\": 692, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mcqlamfhay/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1697, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mcqlamfhay/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1774, \"height\": 963, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mcqlamfhay/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 870, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mcqlamfhay/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1758, \"height\": 1037, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mcqlamfhay/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1574, \"height\": 623, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mcqlamfhay/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1786, \"height\": 1944, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mcqlamfhay/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1784, \"height\": 1868, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mcqlamfhay/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 575, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mcqlamfhay/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 577, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mcqlamfhay/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 573, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mcqlamfhay/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 575, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mcqlamfhay/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1382, \"height\": 1253, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-mcqlamfhay/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 620, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mcqlamfhay/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 585, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mcqlamfhay/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1766, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mcqlamfhay/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 859, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mcqlamfhay/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 859, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mcqlamfhay/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1766, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mcqlamfhay/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1760, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mcqlamfhay/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1764, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mcqlamfhay/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 904, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mcqlamfhay/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1784, \"height\": 1868, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mcqlamfhay/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 580, \"height\": 2055, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mcqlamfhay/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 580, \"height\": 1264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mcqlamfhay/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 590, \"height\": 1928, \"label\": \"Table\"}]"
motivation: 现有语言模型智能体在长时域规划中容易出错，且难以提前规划。
method: 提出迭代自精益方案，通过均衡序列建模框架，以监督学习方式训练自求精规划器。
result: 在多个机器人规划基准上实现了更高的任务完成成功率，验证了方法的有效性。
conclusion: 该工作展示了自精益迭代在长时域规划中的潜力，无需额外反馈即可提升规划质量。
---

## Abstract
In the endeavor to make autonomous robots take actions, task planning is a major challenge that requires translating high-level task descriptions to long-horizon action sequences. Despite recent advances in language model agents, they remain prone to planning errors and limited in their ability to plan ahead. To address these limitations in robotic planning, we advocate a self-refining scheme that iteratively refines a draft plan until an equilibrium is reached. Remarkably, this process can be optimized end-to-end from an analytical perspective without the need to curate additional verifiers or reward models, allowing us to train self-refining planners in a simple supervised learning fashion. Meanwhile, a nested equilibrium sequence modeling procedure is devised for efficient closed-loop planning that incorporates useful feedback from the environment (or an internal world model). Our method is evaluated on the VirtualHome-Env benchmark, showing advanced performance with improved scaling w.r.t. inference-time computation. Code is available at https://github.com/anonymous-icml-2025/equilibrium-planner.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：机器人任务规划要求将高层任务描述转化为长时域（long-horizon）动作序列。现有基于大语言模型（LLM）的智能体在规划时容易出错，且存在单向依赖（无法预视未来 token）、缺乏错误修正机制、推理计算固定等局限性。
- **背景**：自求精（self-refinement）方案可迭代改进初始计划，但训练困难，现有方法依赖过程监督或强化学习，复杂度高。本文旨在提出一种简单、可端到端监督学习的自求精规划框架。

### 2. 论文提出的方法论
- **核心思想**：将自精炼过程建模为固定点问题（fixed-point problem），将理想规划视为均衡点（equilibrium point）。通过深度均衡模型（Deep Equilibrium Model）的理论，利用隐函数定理计算梯度，避免反向传播通过无限次迭代。
- **关键技术细节**：
  - **均衡序列建模（Equilibrium Sequence Modeling）**：两步交替：①通过固定点迭代求解均衡计划 x*；②将 x* 与真实计划 y 配对，使用监督损失 L(fθ(x*,c), y) 训练。
  - **梯度近似**：使用 Jacobian-free 近似（A ≈ I）简化梯度计算，即 ∂L/∂θ ≈ ∂L/∂x* · ∂fθ/∂θ。
  - **闭环反馈整合**：设计嵌套均衡求解（nested equilibrium solving）：内环在固定反馈下自我精炼，外环与环境交互更新反馈。通过重用前一次均衡解加速收敛。
  - **世界模型**：额外训练一个 LLM 作为世界模型，在缺乏环境交互时模拟反馈，提高实用性。
  - **经验记忆缓存**：缓存所有均衡点及反馈，用于训练时的重采样。

### 3. 实验设计
- **数据集/场景**：VirtualHome-Env 基准，包含1360个长时域任务（平均计划长度10.8），提供场景图反馈。划分为训练集和三个测试子集：新场景、新任务、新场景+新任务。
- **对比方法**：基线包括 GPT-3.5 API 的方法（Zero-shot Planner, ProgPrompt, Iterative-Planner, Tree-Planner, Local/Global Replan）以及基于微调 Llama 3 8B 的 Supervised SFT、SELF-REFINE、Tree-Planner（N=25/50）。
- **评估指标**：可执行性（Exec.）、成功率（SR）、目标条件召回率（GCR），并区分无修正和最多10次修正两种设置。

### 4. 资源与算力
- 论文未明确说明使用的 GPU 型号、数量及详细训练时长。仅提到训练时间约36小时（包括均衡求解过程约24小时），推理评估时间约16小时（Tree-Planner 需24小时）。模型基于 Llama 3 8B 微调，学习率0.0002，训练6个epoch。

### 5. 实验数量与充分性
- 实验较为充分：在三个测试子集上报告了无修正和有修正两种设置的结果；进行了多组消融实验（反馈类型、内环有效性、计算效率、鲁棒性、固定点收敛性等）；提供了可视化案例对比。实验设计客观公平，与主流的 Tree-Planner、SELF-REFINE 等在相同基础模型下对比。

### 6. 主要结论与发现
- 本文提出的均衡序列建模方法在多数指标上领先，尤其在闭环设置下 SR 和 GCR 提升显著（最高达19%）。无修正时也带来14%的 SR 提升。
- 缩放性能分析表明，该方法在推理计算增加时性能增长优于 Tree-Planner，尤其擅长处理超长计划（长度>20时成功率翻倍）。
- 均衡点可在少量迭代（平均约3步）内收敛，且通过重用均衡解可显著减少环境交互次数。

### 7. 优点
- 方法简洁：只需监督学习即可训练自精炼规划器，无需额外验证器或强化学习，降低了实现复杂度。
- 推理高效：嵌套均衡求解和均衡解重用机制大幅降低计算开销，且可动态分配计算资源。
- 鲁棒性好：对噪声反馈（10%以内）表现稳定；结合世界模型后可在少环境交互下维持高性能。

### 8. 不足与局限
- 训练效率较低：因均衡求解需要约24小时，导致总训练时间比基线长（36h vs 12h）。
- 泛化能力有限：训练依赖真实计划和环境反馈，难以直接迁移到新领域。
- 仅处理文本输入，缺乏视觉模态，限制了现实世界中的应用。
- 存在 LLM 的幻觉问题及历史上下文遗忘问题（如已抓取物体信息），文中提及可通过上下文模块或推理技术缓解但未实现。
- 实验仅在 VirtualHome-Env 上开展，未在更多机器人规划基准（如 ALFRED, PlanBench）上全面验证（仅做零样本泛化测试）。
- 梯度近似（Jacobian-free）理论上在严格条件下成立，实际中可能引入偏差。

（完）
