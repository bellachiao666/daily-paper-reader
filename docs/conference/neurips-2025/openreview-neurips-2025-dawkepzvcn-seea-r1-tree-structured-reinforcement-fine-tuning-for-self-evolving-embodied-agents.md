---
title: "SEEA-R1: Tree-Structured Reinforcement Fine-Tuning for Self-Evolving Embodied Agents"
title_zh: SEEA-R1：面向自进化具身智能体的树结构强化学习微调
authors: "Wanxin Tian, Shijie Zhang, Kevin Zhang, Xiaowei Chi, Chun-Kai Fan, Junyu Lu, Yulin Luo, Qiang Zhou, Yiming Zhao, Ning Liu, Siyu Lin, Zhiyuan Qin, Xiaozhu Ju, Shanghang Zhang, Jian Tang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=dAwKePZvcN"
tags: ["query:agent-papers"]
score: 9.0
evidence: 树结构强化学习微调实现具身智能体自进化
tldr: 本文针对具身智能体在长程任务中自进化的需求，提出SEEA-R1树结构强化学习微调方法。该方法通过树搜索结构提供中间奖励信号，克服了传统强化学习微调在具身环境下奖励稀疏和泛化困难的问题。实验表明，该方法在多个具身推理基准上显著提升智能体性能，为自进化具身智能体提供了有效方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-dawkepzvcn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1325, \"height\": 647, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dawkepzvcn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1426, \"height\": 797, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dawkepzvcn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 657, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dawkepzvcn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1321, \"height\": 905, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dawkepzvcn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1448, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dawkepzvcn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1415, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dawkepzvcn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1391, \"height\": 622, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dawkepzvcn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1452, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dawkepzvcn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1430, \"height\": 1018, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dawkepzvcn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1430, \"height\": 1020, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dawkepzvcn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1435, \"height\": 1018, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dawkepzvcn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1082, \"height\": 750, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dawkepzvcn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1210, \"height\": 747, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dawkepzvcn/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1288, \"height\": 2309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dawkepzvcn/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1231, \"height\": 2270, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-dawkepzvcn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 408, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dawkepzvcn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1429, \"height\": 114, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dawkepzvcn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1389, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dawkepzvcn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1010, \"height\": 137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dawkepzvcn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1224, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dawkepzvcn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1379, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dawkepzvcn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1159, \"height\": 602, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dawkepzvcn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1432, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dawkepzvcn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1432, \"height\": 1652, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dawkepzvcn/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1442, \"height\": 115, \"label\": \"Table\"}]"
motivation: 强化学习微调在具身场景面临中间奖励缺失和手工奖励泛化差的问题。
method: 提出树结构强化学习微调，利用树搜索生成中间奖励并优化策略。
result: 在多个具身任务上超越现有方法，实现自进化能力。
conclusion: 树结构奖励设计有效解决了具身智能体自进化中的关键障碍。
---

## Abstract
Self-evolution, the ability of agents to autonomously improve their reasoning and behavior, is essential for the embodied domain with long-horizon, real-world tasks. Despite current advancements in reinforcement fine-tuning (RFT) showing strong performance in enhancing reasoning in LLMs, its potential to enable self-evolving embodied intelligence with multi-modal interactions remains largely unexplored. Specifically, reinforcement fine-tuning faces two fundamental obstacles in embodied settings: (i) the lack of accessible intermediate rewards in multi-step reasoning tasks limits effective learning signals, and (ii) reliance on hand-crafted reward functions restricts generalization to novel tasks and environments. To address these challenges, we present *Self-Evolving Embodied Agents-R1*, **SEEA-R1**, the first RFT framework designed for enabling the self-evolving capabilities of embodied agents. Specifically, to convert sparse delayed rewards into denser intermediate signals that improve multi-step reasoning, we propose Tree-based group relative policy optimization (**Tree-GRPO**) integrates Monte Carlo Tree Search into GRPO. To generalize reward estimation across tasks and scenes, supporting autonomous adaptation and reward-driven self-evolution, we further introduce Multi-modal Generative Reward Model (**MGRM**). To holistically evaluate the effectiveness of SEEA-R1, we evaluate on the ALFWorld benchmark, surpassing state-of-the-art methods with scores of 85.07\% (textual) and 46.27\% (multi-modal), outperforming prior models including GPT-4o. SEEA-R1 also achieves scores of 80.3\% (textual) and 44.03\% (multi-modal) without ground truth reward, surpassing all open-source baselines and highlighting its scalability as a self-evolving embodied agent. Additional experiments and qualitative analysis further support the potential of SEEA-R1 for future research in scalable embodied intelligence. Project page is at https://seea-r1.github.io/.

---

## 论文详细总结（自动生成）

# 论文《SEEA-R1: Tree-Structured Reinforcement Fine-Tuning for Self-Evolving Embodied Agents》详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：具身智能体（embodied agents）需要在复杂、长程的真实世界任务中自主执行，而现有大语言模型（LLM）或多模态大语言模型（MLLM）缺乏感知融合、结构化多步规划和动态适应能力。为此，作者提出智能体应具备“自进化”（self-evolution）能力——即通过闭环学习自主生成训练信号并改进推理。
- **核心问题**：将强化微调（RFT）应用于具身场景面临两大障碍：
  1. 多步推理任务中缺少可获取的中间奖励信号（稀疏奖励导致信用分配困难）。
  2. 手工设计的奖励函数在任务和环境中难以泛化，限制了智能体跨场景的自改进。
- **整体含义**：本文首次将RFT框架引入具身智能体自进化，提出SEEA-R1，通过树结构奖励稠密化和多模态生成式奖励模型，实现了无需手工奖励的自主策略优化。

## 2. 方法论：核心思想、关键技术细节与算法流程
- **核心思想**：SEEA-R1通过两个交替循环实现自进化：**数据进化**（Data Evolution）和**模型进化**（Model Evolution）。在数据进化中，智能体使用蒙特卡洛树搜索（MCTS）与环境交互生成经验数据；在模型进化中，策略模型和奖励模型同时利用这些数据更新。更新后的模型驱动下一轮数据进化，形成闭环。
- **关键技术**：
  - **Tree-GRPO（基于树的组相对策略优化）**：将MCTS整合进GRPO。MCTS通过模拟多轮路径为每步动作估计Q值，从而将稀疏的最终奖励转化为稠密的步骤级过程奖励。在树的每个节点，GRPO对同一状态下的多个动作组进行优势估计和策略梯度更新。公式（1）给出了Tree-GRPO的目标函数，包含裁剪的重要性采样比和KL散度正则项。
  - **MGRM（多模态生成式奖励模型）**：基于MLLM，以历史上下文（文本+图像）为输入，预测三种状态类别：`success`、`continue`、`failure`。支持两种训练范式：
    - **有GT奖励（监督）**：先用GT标签做SFT预训练，再每500轮与GT校准，防止漂移。
    - **无GT奖励（自监督）**：使用TTRL（Test-Time RL）和GRPO：对每个初始状态生成K=10条轨迹，MGRM多数投票作为伪GT，用GRPO训练（匹配伪GT得+1，否则0）。
  - **自进化循环**：迭代进行数据进化（MCTS采样）和模型进化（Tree-GRPO更新策略 + GRPO更新奖励模型）。文中给出了伪代码（Algorithm 1）。

## 3. 实验设计
- **数据集/场景**：
  - **ALFWorld**：交互式模拟家庭环境，提供文本和视觉两种观测。用于训练和评估，测试集分为`test-seen`（140游戏）和`test-unseen`（134游戏），主要报告**test-unseen**结果。
  - **EmbodiedEval**：125个复杂3D场景的跨域基准，包含属性QA、空间QA、导航、物体交互、社交交互等5类任务，评估泛化能力。
  - **真实世界实验**：使用双机械臂ARX LIFT 2 + Mobile ALOHA遥操作，在6个环境（客厅、客房、公寓、儿童房、厨房、茶室）中测试3类任务（Pick & Place、Pick Two & Place、Clean），每环境12个测试。
- **Benchmark与对比方法**：
  - 多模态（MLLM）场景：对比GPT-4o、Florence-2、Idefics-2、MiniGPT-4、InstructBLIP、Qwen2.5-VL、RL4VLM等。
  - 纯文本（LLM）场景：对比GPT-4o、Qwen2.5、Llama-3.1、以及基于SFT/DPO/ETO/MPO的多种方法。
  - 在EmbodiedEval上对比GPT-4o、Vision-R1、Ocean-R1、Qwen2.5-VL、LLaVA系列等。
  - 消融实验对比MCTS+SFT、MCTS+DPO、Tree-GRPO；以及不同奖励设置（GT、冻结MGRM、监督MGRM、自监督MGRM）。

## 4. 资源与算力
- **硬件**：8张NVIDIA A100 80GB GPU。
- **训练时长**：
  - SEEA-R1（有GT奖励）每轮约194分钟（采样190分钟+策略训练4分钟）。
  - SEEA-R1（无GT奖励）每轮约421.5分钟（采样173.5分钟+策略训练4分钟+奖励模型训练244分钟）。
  - 总训练约36小时（具体轮数根据收敛而定，但每轮平均时间如上）。
- **框架**：基于`ms-swift`框架进行分布式训练，推理使用`vLLM`。

## 5. 实验数量与充分性
- **实验数量**：
  - ALFWorld多模态（MLLM）和纯文本（LLM）各一组实验，报告每种子任务成功率及平均成功率。
  - EmbodiedEval跨域泛化实验。
  - 真实世界实验。
  - 训练算法对比（Tree-GRPO vs MCTS+SFT vs MCTS+DPO）折线图。
  - 奖励设置消融（GT、冻结MGRM、监督MGRM、自监督MGRM）折线图。
  - 样本量与Batch Size影响分析。
  - 长期训练（30轮）学习曲线。
  - 数据质量分析（SFT on生成数据）。
  - MGRM准确率对比（冻结 vs 训练）。
  - 额外多模态通用基准（MMBench, MMStar, MMMU, HallusionBench, AI2D, OCRBench等）。
  - 可视化案例与推理轨迹分析。
- **充分性与客观性**：
  - 实验覆盖了主流基准和多种设置（有/无GT、多模态/文本、模拟/真实），对比方法包括闭源SOTA（GPT-4o）和多种开源模型。
  - 消融实验设计合理，对比了不同算法、不同奖励源、不同样本量。
  - 所有结果报告了平均值，部分提供了error bar（在附录中提及）。
  - 在EmbodiedEval上展示了OOD泛化，在真实世界中验证了sim2real迁移。
  - 实验设计较为全面、公平，但不足之处在于：真实世界实验仅报告单次轨迹执行结果，未报告多次平均或方差。

## 6. 主要结论与发现
- **SEEA-R1在ALFWorld上达到新SOTA**：多模态场景46.27%（超过GPT-4o的24%），纯文本场景85.07%（超过GPT-4o的81.1%）。
- **无GT奖励的自监督版本同样出色**：多模态44.03%，纯文本80.30%，超越所有开源基线。
- **Tree-GRPO显著优于MCTS+DPO和MCTS+SFT**，证明在线策略更新和树结构奖励的优势。
- **MGRM训练后准确率从51.59%提升至91.67%**，能有效替代GT奖励，驱动自进化。
- **自进化迭代持续提升性能**：30轮训练后成功率从11.57%升至39.48%，且数据质量随轮次提高。
- **真实世界实验表现**：SEEA-R1总体成功率达68.1%，较基线（33.3%）提升34.72%，展示了反思-修正能力（如先开洗衣机门再放衣服）。

## 7. 优点
- **方法创新**：
  - 首次将RFT框架完整应用于具身智能体自进化，提出Tree-GRPO将稀疏奖励稠密化为步骤级信号。
  - MGRM采用多模态、多轮、可解释的奖励预测，支持无GT场景下的自监督进化。
  - 数据进化与模型进化的迭代闭环设计，实现了无需人类干预的持续自我提升。
- **实验设计**：
  - 在模拟、跨域基准、真实世界三重场景验证，增强了结论的泛化可信度。
  - 对比方法全面，包含闭源SOTA和多种开源模型，且报告了推理效率（Token减少38.8%）。
  - 消融实验系统，覆盖算法、奖励、样本量等关键因素。
- **开源承诺**：将开源完整框架、MGRM和训练管线，促进社区研究。

## 8. 不足与局限
- **实验覆盖局限**：
  - 真实世界实验仅采用单次轨迹执行（未报告多次平均或标准差），且遥操作引入人为因素，结果稳定性待验证。
  - ALFWorld虽然是经典基准，但场景复杂度有限，与真实家庭环境仍有差距。
  - 在EmbodiedEval等OOD基准上，SEEA-R1虽优于基线，但绝对成功率仍较低（19.88%），泛化能力有待提升。
- **方法局限**：
  - MCTS在训练时需要多次模拟，带来额外计算开销（自监督版本总训练时间约为监督版的两倍）。
  - 奖励模型MGRM在高度动态环境下可能依然误判，文末也承认当前具身AI未能完全处理动态不可预测场景。
  - 自进化循环依赖于初始的监督信号或伪GT，极冷启动场景下可能失效。
- **潜在偏差**：
  - 主要实验基于单一基准（ALFWorld），可能过拟合该环境特点。
  - 无GT版本中伪GT由MGRM多数投票产生，存在自强化偏差风险。
- **应用限制**：当前框架仍需要模拟或近似环境进行数据进化，完全无环境交互的真实世界自进化尚未验证。

（完）
