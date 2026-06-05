---
title: Group-in-Group Policy Optimization for LLM Agent Training
title_zh: 组内组策略优化：面向大语言模型智能体训练
authors: "Lang Feng, Zhenghai Xue, Tingcong Liu, Bo An"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=QXEhBMNrCW"
tags: ["query:agent-papers"]
score: 6.0
evidence: 面向LLM智能体训练的组内组策略优化算法，实现细粒度信用分配
tldr: 现有基于组的RL方法（如GRPO）在单轮任务中表现优异，但难以扩展到多轮LLM智能体训练，因为稀疏延迟奖励导致信用分配困难。本文提出组内组策略优化（GiGPO），通过两级结构估计相对优势：组间级别和组内级别，实现细粒度信用分配，同时保持无评论家、低内存和稳定收敛的特性。实验证明，GiGPO在多个多轮智能体基准上显著提升了RL训练效果，为LLM通过强化学习自改进提供了高效算法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qxehbmnrcw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 300, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qxehbmnrcw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1407, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qxehbmnrcw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 652, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qxehbmnrcw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qxehbmnrcw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 418, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qxehbmnrcw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 560, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qxehbmnrcw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1434, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qxehbmnrcw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 640, \"height\": 366, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qxehbmnrcw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 520, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qxehbmnrcw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 758, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qxehbmnrcw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 930, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qxehbmnrcw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 950, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qxehbmnrcw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1166, \"height\": 184, \"label\": \"Table\"}]"
motivation: 基于组的RL方法在多轮智能体训练中信用分配困难，限制了LLM自改进的扩展。
method: 提出GiGPO算法，构建两级优势估计结构，实现细粒度信用分配且无需评论家网络。
result: 在多轮智能体基准上，GiGPO的训练效率和最终性能均优于现有方法。
conclusion: GiGPO是一种高效且可扩展的RL算法，适用于LLM智能体的多步自改进训练。
---

## Abstract
Recent advances in group-based reinforcement learning (RL) have driven frontier large language models (LLMs) in single-turn tasks like mathematical reasoning. However, their scalability to multi-turn LLM agent training remains limited. Unlike static tasks, agent-environment interactions unfold over many steps and often yield sparse or delayed rewards, making credit assignment across individual steps significantly more challenging. In this work, we propose Group-in-Group Policy Optimization (GiGPO), a novel RL algorithm that achieves fine-grained credit assignment for LLM agents while preserving the appealing properties of group-based RL: critic-free, low memory, and stable convergence. GiGPO introduces a two-level structure for estimating relative advantage: (i) At the episode-level, GiGPO computes macro relative advantages based on groups of complete trajectories; (ii) At the step-level, GiGPO introduces an anchor state grouping mechanism that retroactively constructs step-level groups by identifying repeated environment states across trajectories. Actions stemming from the same state are grouped together, enabling micro relative advantage estimation. This hierarchical structure effectively captures both global trajectory quality and local step effectiveness without relying on auxiliary models or additional rollouts. We evaluate GiGPO on challenging agent benchmarks, including ALFWorld and WebShop, as well as tool-integrated reasoning on search-augmented QA tasks, using Qwen2.5-1.5B/3B/7B-Instruct. Crucially, GiGPO delivers fine-grained per-step credit signals, achieves performance gains of > 12\% on ALFWorld and > 9\% on WebShop over GRPO, and obtains superior performance on QA tasks (42.1\% on 3B and 47.2\% on 7B): all while maintaining the same GPU memory overhead, identical LLM rollout, and incurring little to no additional time cost.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：现有基于组的强化学习（group-based RL）算法（如GRPO、RLOO）在单轮任务（如数学推理）中表现优异，但在多轮LLM智能体训练中面临严重的信用分配问题。多轮交互中，奖励稀疏且延迟，单个动作的影响可能很久后才显现，导致难以区分每个步骤的贡献。
- **整体含义**：为了解决这一局限，本文提出**组内组策略优化（GiGPO）**，在保持组RL“无评论家、低内存、稳定收敛”优势的同时，实现细粒度的每步信用分配，从而提升LLM智能体在多轮环境中的训练效果。

### 2. 论文提出的方法论

- **核心思想**：构建一个两级相对优势估计结构：
  - **Episode级（宏观）**：基于完整轨迹组的总体回报计算相对优势，反映整条轨迹的整体有效性。
  - **Step级（微观）**：通过**锚点状态分组机制**，在不同轨迹中自动识别相同的环境状态（锚点状态），将这些状态下采取的不同动作聚合为一个步骤级组，然后基于折扣回报计算相对优势。
- **关键技术细节**：
  - 锚点状态分组无需额外rollout，仅通过哈希表离线完成。
  - 步骤级优势使用折扣回报（公式5）而非即时奖励，以捕捉长期影响。
  - 最终优势结合：\( A(a_t^{(i)}) = A_E(\tau_i) + \omega \cdot A_S(a_t^{(i)}) \)，其中\(\omega\)为平衡系数。
  - 优化目标为裁剪的PPO目标加KL惩罚（公式9）。
- **伪代码流程**（Algorithm 1）：
  1. 采样任务，初始化N个相同环境的智能体。
  2. 多步 rollout，收集轨迹。
  3. 计算 episode 级优势。
  4. 通过锚点状态构建 step 级组，计算 step 级优势。
  5. 组合优势，最大化 GiGPO 目标更新策略。

### 3. 实验设计

- **数据集/场景**：
  - **ALFWorld**：具身任务规划，包含6类子任务（Pick, Look, Clean, Heat, Cool, Pick2），共3827个实例。
  - **WebShop**：复杂网页交互购物，110万商品，1.2万指令。
  - **搜索增强QA**：单跳（NQ, TriviaQA, PopQA）和多跳（HotpotQA, 2Wiki, MuSiQue, Bamboogle）问答任务。
- **基准方法**：
  - 闭源LLM：GPT-4o, Gemini-2.5-Pro。
  - 提示法：ReAct, Reflexion。
  - RL方法：PPO（带评论家）、RLOO、GRPO、Search-R1、ZeroSearch、StepSearch等。
- **模型**：Qwen2.5-1.5B/3B/7B-Instruct。
- **评估指标**：成功率（ALFWorld/WebShop）、得分（WebShop）、准确率（QA）。

### 4. 资源与算力

- **ALFWorld / WebShop**：
  - 1.5B模型：2×H100 GPU，150次迭代。
  - 7B模型：4×H100 GPU，150次迭代。
- **搜索增强QA**：
  - 3B模型：4×H100 GPU，200次迭代。
  - 7B模型：8×H100 GPU，200次迭代。
- 论文未给出具体训练时长，但指出GiGPO的额外计算开销不到总时间成本的0.002%。

### 5. 实验数量与充分性

- **实验数量**：
  - 在ALFWorld和WebShop上各进行了3种模型大小（1.5B, 7B；QA用3B和7B）的实验。
  - 所有结果均报告3次随机种子的均值和标准差。
  - 消融实验：去除了AE或AS分别测试。
  - 敏感性分析：对\(\omega\)在WebShop上测试了多个值。
  - 动态分析：跟踪step级组大小分布随训练变化。
  - 正交性验证：结合DAPO技术测试。
  - 额外VLM实验：Sokoban和EZPoints。
- **充分性与公平性**：
  - 所有RL方法（含基线）使用相同超参数和rollout设置。
  - 对比方法覆盖了当前主流基线，实验设计较为全面。
  - 但在更复杂的环境（如真实机器人、多模态、超长轨迹）上未覆盖，可能存在泛化性不足。

### 6. 论文的主要结论与发现

- GiGPO在ALFWorld上比GRPO提升>12%，在WebShop上提升>9%，在搜索QA上达到42.1%（3B）和47.2%（7B），显著优于现有方法。
- 两级优势信号缺一不可：去除任意一级都导致性能大幅下降。
- GiGPO的计算开销极低（<0.002%时间增加），和GRPO一样高效。
- 步骤级优势在训练中动态演化：随着策略成熟，组大小分布从极端值集中到合理范围，表明智能体学会了有效规划。

### 7. 优点

- **方法创新**：首次将两步式信用分配（宏观轨迹级+微观步骤级）融入组RL，无需额外评论家或rollout。
- **高效性**：保持GRPO所有优点（无评论家、低内存、稳定），额外计算几乎可忽略。
- **正交性**：GiGPO可以与DAPO等单轮改进技术结合，进一步提升性能。
- **鲁棒性**：在多种任务、多个模型规模上一致优于基线；对关键超参数\(\omega\)不敏感（0.4~1.2范围内表现稳定）。
- **开源贡献**：提供了基于veRL的verl-agent框架，支持多轮、多环境、多算法。

### 8. 不足与局限

- **状态匹配依赖**：锚点分组依赖于精确的状态匹配，在噪声大、状态表示复杂的真实环境中可能难以正确检测，极端情况下（无重复状态）退化为GRPO。
- **实验覆盖有限**：主要测试了文本交互的环境（ALFWorld/WebShop/搜索QA），未涉及真实机器人操作、多模态长序列、多人协作等更复杂场景。
- **泛化风险**：论文主要基于Qwen2.5系列，其他架构（如LLaMA、DeepSeek）上是否同样有效未验证。
- **稀疏奖励假设**：GiGPO设计天然适用于稀疏奖励，但在密集奖励场景下，步骤级优势可能过于嘈杂，论文未深入讨论此情况下的表现。
- **状态等价判定**：虽然提到了相似度分组，但未提供完整的鲁棒性分析，阈值选择可能影响性能。

（完）
