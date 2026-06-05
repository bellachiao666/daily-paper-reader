---
title: Retrospective In-Context Learning for Temporal Credit Assignment with Large Language Models
title_zh: 基于回顾性上下文学习的大语言模型时序信用分配
authors: "Wentse Chen, Jiayu Chen, Fahim Tajwar, Hao Zhu, Xintong Duan, Ruslan Salakhutdinov, Jeff Schneider"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=QAVpe6a3rp"
tags: ["query:agent-papers"]
score: 9.0
evidence: 利用LLM进行自进化智能体的时间信用分配
tldr: 该论文针对自进化智能体训练中稀疏反馈问题，提出回顾性上下文学习（RICL），利用预训练LLM知识将稀疏奖励转化为密集优势函数，并构建在线学习框架RICOL迭代优化策略。该方法无需领域特定的值函数，提升了样本效率和泛化能力，直接支持递归自改进机制。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qavpe6a3rp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1090, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qavpe6a3rp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 569, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qavpe6a3rp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 574, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qavpe6a3rp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1373, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qavpe6a3rp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1368, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qavpe6a3rp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 513, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qavpe6a3rp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 499, \"height\": 145, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qavpe6a3rp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1453, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qavpe6a3rp/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 692, \"height\": 576, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qavpe6a3rp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 729, \"height\": 592, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qavpe6a3rp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1375, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qavpe6a3rp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1390, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qavpe6a3rp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1191, \"height\": 145, \"label\": \"Table\"}]"
motivation: 自进化智能体从稀疏反馈中学习困难，现有信用分配方法样本效率低且泛化差。
method: 提出RICL，用LLM的预训练知识通过回顾性上下文转换稀疏奖励为密集优势信号，结合在线迭代优化。
result: 在多个控制任务中优于基线，实现了高效的自改进策略学习。
conclusion: RICOL为自进化智能体提供了一种通用且高效的训练范式。
---

## Abstract
Learning from self-sampled data and sparse environmental feedback remains a fundamental challenge in training self-evolving agents. Temporal credit assignment mitigates this issue by transforming sparse feedback into dense supervision signals. However, previous approaches typically depend on domain-specific value functions for credit assignment, which suffer from poor sample efficiency and limited generalization. In this work, we propose to leverage pre-trained knowledge from large language models (LLMs) to transform sparse rewards into dense training signals (i.e., the advantage function) through retrospective in-context learning (RICL).  We further propose an online learning framework, RICOL, which iteratively refines the policy based on the credit assignment results from RICL. We empirically demonstrate that RICL can accurately estimate the advantage function with limited samples and effectively identify critical states for temporal credit assignment. Extended evaluation on the BabyAI benchmark shows that RICOL significantly improves sample efficiency compared to traditional online RL algorithms while achieving performance comparable to imitation learning from expert demonstartions.  Our findings highlight the potential of leveraging LLMs for temporal credit assignment, paving the way for more sample-efficient and generalizable RL paradigms.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：自进化智能体在稀疏环境反馈下学习困难，时序信用分配可缓解问题，但传统方法依赖领域特定的值函数，样本效率低且泛化能力差。
- **整体含义**：本文提出利用大语言模型（LLM）的预训练知识，通过回顾性上下文学习（RICL）将稀疏奖励转换为密集的优势函数信号，并结合在线学习框架（RICOL）实现高效的策略迭代，从而提升样本效率和泛化性。

## 2. 方法论

- **核心思想**：基于定理4.1，任意两个策略之间存在隐式的优势函数关系；通过比较原始策略与上下文更新后策略的对数概率之差，可估计优势函数。
- **关键技术细节**：
  - **RICL（回顾性上下文学习）**：对每个状态 \(s_t\)，收集其事后轨迹，利用反射器LLM生成言语反馈；将反馈注入原始策略的提示中，得到更新策略 \(\pi'(\cdot|s_t)\)。
  - **优势估计**：根据公式 \(\beta \log \frac{\pi'(a|s)}{\pi_0(a|s)} \propto A^{\pi_0}_r(s,a)\)，利用多个轨迹的样本平均估计优势函数。
  - **RICOL（回顾性上下文在线学习）**：使用AWR风格目标函数，将 \(\pi_0\) 与 \(\pi'\) 插值得到目标分布，通过KL散度最小化更新策略参数；引入信任区域约束以增强对噪声反馈的鲁棒性。
- **算法流程**（文字说明）：
  1. 策略 \(\pi_k\) 与环境交互收集轨迹 \(\tau_k\)。
  2. 对轨迹中每个状态，执行RICL：反射器生成反馈 → 上下文更新得到 \(\pi'_{k+1}\) → 计算平均优势函数 → 得到 \(\pi'_{k+1}(\cdot|s_t)\)。
  3. 通过梯度下降优化目标函数（式5），更新策略 \(\pi_k\) 至 \(\pi_{k+1}\)。

## 3. 实验设计

- **数据集/场景**：
  - **1D Key-Door**：一维网格世界，可精确计算真实优势函数，用于评估信用分配精度。
  - **BabyAI**：四个语言条件下的2D网格世界任务：`goto`、`pickup`、`pick_up_seq_go_to`、`open`。
- **基准（Benchmark）**：BabyAI平台（基于BALROG实现），部分可观测，输出离散动作（6个），最大步长设为16或32。
- **对比方法**：
  - **GPT-4o mini**：零样本性能基线。
  - **Reflexion**：基于轨迹级言语反馈的上下文学习方法。
  - **PPO (3B)**：使用Qwen2.5-3B-Instruct作为策略和评论家，基于VeRL框架实现。
  - **PPO (10M)**：随机初始化的3层MLP策略和评论家。
  - **RWR**：直接使用轨迹级奖励进行AWR更新，无信用分配。
- **评估指标**：环境交互步数（样本效率）和任务成功率。

## 4. 资源与算力

- **明确说明**：附录D中的表2列出了各方法在BabyAI任务上的训练时间及GPU配置：
  - **RWR**：A40 × 2，任务时间72–585分钟。
  - **RICOL**：A40 × 2，任务时间96–594分钟。
  - **PPO (10M)**：GeForce RTX 2080 Ti × 1，任务时间198–258分钟。
  - **PPO (3B)**：A40 × 4，每个任务约1440分钟。
- 此外，实验使用Delta超算资源（通过ACCESS项目分配），但未详细说明总计算量。

## 5. 实验数量与充分性

- **实验组数**：
  - **1D Key-Door**：8个随机种子，在多个样本数下比较RICL与蒙特卡洛（MC）的优势估计误差。
  - **BabyAI**：每个任务3个随机种子，报告均值与标准差，共4个任务。
  - **ICL vs RICL精度对比**：在1000条轨迹上比较。
  - **RWR vs RICOL**：在4个任务上对比。
  - **噪声反馈鲁棒性**：在`goto`任务上测试不同反馈准确率（100%、80%、70%、50%）。
  - **关键状态识别可视化**：在1D Key-Door上展示RICL与真实策略的吻合度。
- **充分性与公平性**：实验覆盖信用分配精度、样本效率、鲁棒性等维度；对比方法涵盖多种RL范式且超参数一致；报告了误差带和随机种子，结论可靠。

## 6. 主要结论与发现

- **RICL样本效率高**：在1D Key-Door中，RICL仅需约10条轨迹即可达到与MC需1000条轨迹相当的精度（效率提升100倍）。
- **RICOL样本效率显著优于基线**：在BabyAI四个任务上，RICOL比PPO (10M)减少约50倍交互，比PPO (3B)减少约10倍交互，且性能优于Reflexion和GPT-4o mini。
- **信用分配是关键**：RWR因缺乏信用分配，仅在初始成功率较高的`goto`任务上表现尚可，在稀疏奖励任务上远不如RICOL。
- **对噪声反馈鲁棒**：即使言语反馈准确率降至70%，RICOL仍保持良好性能；归因于信任区域约束。
- **RICL能准确识别关键状态**：在1D Key-Door中，RICL识别的关键状态与真实策略高度一致。

## 7. 优点

- **创新性**：首次将LLM的预训练知识与回顾性上下文学习结合用于时序信用分配，无需额外训练值函数或反射器。
- **理论支撑**：定理4.1保证了任意两个策略间存在隐式优势函数，为方法提供了理论基础。
- **实验设计全面**：涵盖多维度评估（精度、效率、鲁棒性、可解释性），并设置多个基线（包括PPO、Reflexion、RWR）。
- **鲁棒性好**：对不完美的言语反馈（准确率70%仍有效）和噪声环境具有较强适应能力。
- **实用性强**：在有限交互预算（1000–10000步）场景下性能显著优于现有方法。

## 8. 不足与局限

- **动作空间限制**：仅支持离散、可枚举动作空间，因为计算KL散度需要枚举所有动作；对于长思维链或连续动作空间需采用采样近似，但未实验验证。
- **环境截断可能引入偏差**：为提升样本效率将最大步长设为16或32，可能影响长期信用分配效果。
- **反射器LLM的质量影响**：虽然实验显示对噪声鲁棒，但仍依赖反射器生成有效反馈；若反射器能力不足可能影响性能。
- **计算成本**：尽管样本效率高，但每次评估需多次调用LLM（每个状态枚举动作），训练时间仍较长（如`pick_up_seq_go_to`需约10小时）。

（完）
