---
title: Learning “Partner-Aware” Collaborators in Multi-Party Collaboration
title_zh: 学习多方协作中的“伙伴感知”协作智能体
authors: "Abhijnan Nath, Nikhil Krishnaswamy"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=yFfWVr2TmZ"
tags: ["query:agent-papers"]
score: 6.0
evidence: 面向多方LLM智能体协作的伙伴感知协作学习
tldr: "本文研究LLM智能体协作中的'伙伴感知'行为，通过干预信息增加共同基础。基于AI对齐和安全中断理论，提出一种训练伙伴感知协作智能体的方法。实验表明，标准RLHF训练的智能体可以学会利用干预提升协作效果。该工作为评估和提高LLM智能体多轮多方向协作能力提供了新视角。"
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-yffwvr2tmz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yffwvr2tmz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1419, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yffwvr2tmz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1409, \"height\": 817, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-yffwvr2tmz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 451, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yffwvr2tmz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1349, \"height\": 438, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yffwvr2tmz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 564, \"height\": 676, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yffwvr2tmz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1466, \"height\": 706, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yffwvr2tmz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 813, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yffwvr2tmz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1452, \"height\": 891, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yffwvr2tmz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1451, \"height\": 810, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yffwvr2tmz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1452, \"height\": 927, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yffwvr2tmz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1455, \"height\": 847, \"label\": \"Table\"}]"
motivation: LLM作为人类合作者时，需要评估其多轮多方向协作能力。
method: 基于AI对齐和安全中断理论，设计伙伴感知智能体，通过干预收集信息增加共同基础。
result: 标准RLHF训练的智能体能学会伙伴感知协作行为。
conclusion: 伙伴感知是有效协作的关键，RLHF可训练此类能力。
---

## Abstract
Large Language Models (LLMs) are increasingly being deployed in agentic settings where they act as collaborators with humans. Therefore, it is increasingly important to be able to evaluate their abilities to collaborate effectively in multi-turn, multi-party tasks. In this paper, we build on the AI alignment and “safe interruptability” literature to offer novel theoretical insights on collaborative behavior between LLM-driven *collaborator agents* and an *intervention agent*. Our goal is to learn an ideal “partner-aware” collaborator that increases the group’s common-ground (CG)—alignment on task-relevant propositions—by intelligently collecting information provided in *interventions* by a partner agent. We show how LLM agents trained using standard RLHF and related approaches are naturally inclined to ignore possibly well-meaning interventions, which makes increasing group common ground non-trivial in this setting. We employ a two-player Modified-Action MDP to examine this suboptimal behavior of standard AI agents, and propose **Interruptible Collaborative Roleplayer (ICR)**—a novel “partner-aware” learning algorithm to train CG-optimal collaborators. Experiments on multiple collaborative task environments show that ICR, on average, is more capable of promoting successful CG convergence and exploring more diverse solutions in such tasks.

---

## 论文详细总结（自动生成）

# 论文《Learning “Partner-Aware” Collaborators in Multi-Party Collaboration》详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：大语言模型（LLMs）越来越多地被部署为与人类合作的智能体（agents），需要评估它们在多轮、多方任务中的协作能力。现有标准 RLHF 等方法训练的智能体倾向于忽略（甚至可能是有益的）干预行为，导致群体共同基础（common ground, CG）难以增长。
- **核心问题**：如何训练一个“伙伴感知”（partner-aware）的协作智能体，使其能够智能地区分来自干预智能体的有用建议与误导性建议，从而在小组协作中有效提升任务相关命题的一致性（即共同基础），同时保持逻辑一致性和任务焦点。
- **理论背景**：基于 AI 对齐（alignment）和“安全中断”（safe interruptibility）文献，将协作场景建模为修改动作马尔可夫决策过程（Modified-Action MDP, MAMDP），揭示了标准 Bellman 最优策略在 MAMDP 中的次优性（Theorem 3.2）。

## 2. 方法论

### 核心思想
- 提出 **Interruptible Collaborative Roleplayer (ICR)**，一种“伙伴感知”学习算法，通过引入**反事实不变性**（counterfactual invariance）作为 KL 散度正则化项，训练智能体在干预被声明为无效的反事实状态下仍保持与原策略一致，从而学会区分干预质量。
- 协作智能体策略 πC 在 MAMDP 框架中与固定干预智能体 πI 交互。状态包含对话历史，每轮干预智能体先发言，协作智能体随后回应。

### 关键技术细节
1. **MAMDP 建模**：状态 s_t 为所有之前的对话轮次；动作空间包括协作智能体的响应（以 token 序列产生）和干预智能体的干预；奖励 R(s_t, a^I_t, â^C_t, s_{t+1}) 反映任务进展。
2. **反事实状态构造**：在训练时，构造一个反事实状态 s^{CF}_t，在其中通过前缀提示明确告知协作智能体：“干预智能体的建议**不会**改善你的表现”。利用相同模型计算在该反事实条件下的策略 π^{CF}_C。
3. **优化目标**：结合三项损失：
   - 任务效用：最大化折扣累计奖励
   - 标准 KL 正则化：与参考策略（如 BC 模型）的散度
   - **反事实 KL 正则化**：事实策略与反事实策略之间的 KL 散度，系数 λ_{Intent}
4. **计算高效性**：反事实 KL 不额外采样 token，仅对已采样 token 进行第二次前向传播（带停止梯度），近似于事后信用分配。

### 算法流程（文字说明）
1. 收集专家数据：使用 GPT-4o 作为专家协作智能体和干预智能体生成 MAMDP 轨迹（15 轮），构建数据集 D_expert。
2. 训练参考策略：在 D_expert 上行为克隆（BC）获得 BC-Collaborator。
3. 初始化协作智能体 πC 为 BC 模型，使用 PPO 联合优化上述三项损失。从事实策略采样，同时计算反事实策略的 log-prob 作为分母，更新梯度。
4. 训练时仅使用任务代理奖励（无共同基础奖励），评估时计算共同基础收敛情况。

## 3. 实验设计

### 数据集/场景
- **DeliData Wason Card Selection task**：逻辑规则验证任务（卡片选择），评估最终解决方案准确率（ACC）和共同基础增益（CG，即新引入唯一解决方案类型的净增加量）。
- **Weights Task**：协作推断隐藏块重量（红=10，蓝=10，绿=20，紫=30，黄=50），评估 ACC（正确性与共同基础大小复合指标）。
- 每个任务均有 **full-press**（全自然语言对话）和 **no-press**（仅离散动作/信念）两种变体。

### 方法对比
| 类别 | 方法 |
|------|------|
| 行为克隆 | BC-Collaborator |
| 偏好对齐 | DPO, IPO |
| 在线强化学习 | PPO |
| 因果意图基线 | PSO-Intent |
| 本文方法 | **ICR** |

- 所有方法均基于 Meta-Llama-3-8B-Instruct，除 ICR 外也使用了 PPO 框架。
- 干预智能体固定为 GPT-4o（温度 0，top-p=0.9）。

### 评估指标
- Weights Task：ACC（正确命题占比乘以共同基础大小，最高 37）
- DeliData：ACC（解决方案准确率）和 CG（对话期间引入的新解决方案类型数量减去初始数量）

## 4. 资源与算力

- 训练使用 **两个 NVIDIA A100 GPU**（full-press），单个 A100（no-press）。
- 标准基线训练约 **12 GPU 小时**（2000 步），PPO 训练约 **24 小时**（6000 mini-batch，有效 batch size 8）。
- 大型 GPT-4o 仅用于数据生成和评估，不作为训练主体。
- 文中未明确说明总 GPU 小时数，但给出了相对时间。

## 5. 实验数量与充分性

- **主要实验**：每个任务进行 100 个对话（每个对话 15 轮），每个方法报告均值和标准误。表格 1 展示了两个任务、两个设置下的主要结果。
- **补充实验**（50 个对话）：
  - ICR-Masked（掩盖干预）
  - ICR-Small（弱干预智能体）
  - PSO-Skeptical（负极性前缀）
  - ICR-Phrasing（反事实前缀变体）
  - PPO-CF（仅用反事实提示但无正则化）
  - GPT-4o-mini 配对、GPT-4o 配对（同一模型作为两个智能体）
- **消融实验**：不同 λ_{Intent} 值（0.01, 0.2, 1.0）在 DeliData no-press 下训练 8k 步，每步跟踪代理奖励（图 1b）。
- **鲁棒性测试**：6 种语义相似但措辞不同的反事实前缀，分析 token 级 log-prob 差异（均值 0.0008，标准差 0.1568），表明 ICR 对提示措辞不敏感。
- **人类验证**：两名人类标注员对 GPT-4o 生成的干预质量进行评分，与 LLM-Judge 一致性高（Cohen's κ = 0.92 on DeliData, 0.58 on Weights Task）。
- 总体实验覆盖了主要场景、消融、鲁棒性和替代设置，**充分且公平**，且与人类判断对齐。

## 6. 主要结论与发现

1. **ICR 在所有设置中一致优于所有基线**：在 Weights Task full-press 下 ICR 的 ACC 达 14.06（比 DPO 提升 47%），DeliData 下 ACC 0.88 且 CG 3.35（BC 的 CG 为负值）。
2. **共同基础增长主要源于复杂关系**：在 inequality 和 order 关系上，ICR 的增长远快于其他方法（如 order 关系最终 CG 约 0.13 vs 基线约 0.05），表明 ICR 更善于整合干预逐步构建共识。
3. **反事实正则化强度需适度**：λ_{Intent}=0.2 最佳，过大（1.0）导致过于保守而牺牲任务效用，过小（0.01）则缺乏对误导干预的鲁棒性。
4. **ICR 在没有显式共同基础奖励的情况下仍能促进共识**：训练仅使用任务代理奖励，但评估时共同基础自然增长，说明该方法将协作能力作为涌现属性。
5. **在 no-press 设置下 ICR 仍保持优势**：表明反事实正则化带来的鲁棒性不依赖语言表达。

## 7. 优点

- **理论创新**：首次将 MAMDP 和反事实不变性引入 LLM 协作训练，理论证明标准偏好对齐方法在 MAMDP 中的次优性，并提供可证明的可达性边界。
- **计算效率**：反事实 KL 仅需一次额外前向传播，不增加采样成本，适合 PPO 框架。
- **实验设计严谨**：包含 full-press/no-press 两种设置、多种基线、消融实验、提示鲁棒性测试，并进行了人类验证。
- **泛化潜力**：方法支持融入人类先验（如 InstructRL），可应用于 AI 辅导等实际场景。
- **开源代码**：发布在 GitHub 上，可复现。

## 8. 不足与局限

- **模型规模受限**：仅训练了 8B 参数模型，更大模型（如 70B）可能表现不同但未验证。
- **固定干预智能体**：只使用了 GPT-4o 作为干预方，未测试人类或不同质量的干预对 ICR 鲁棒性的影响。
- **任务域有限**：仅覆盖 Wason 卡选择和重量任务，更复杂的协作场景（如 Diplomacy 游戏，涉及欺骗）未包含。
- **单一训练范式**：采用分散训练，未尝试集中式梯度通信（如 Foerster et al. 2016），可能限制性能上限。
- **缺乏人类协作数据**：无法通过 InstructRL 直接利用人工演示，因大规模多方向协作数据稀缺。
- **潜在滥用风险**：伙伴感知能力可能被用于操纵团队（欺骗性对齐），作者提到了风险并建议结合红队测试和失败检测。
- **反事实前缀手动设计**：虽经测试鲁棒，但可能依赖特定句法，未来需要更通用的反事实生成方法。

（完）
