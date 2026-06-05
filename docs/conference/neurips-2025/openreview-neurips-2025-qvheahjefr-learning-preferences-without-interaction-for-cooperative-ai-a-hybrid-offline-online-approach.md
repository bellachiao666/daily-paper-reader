---
title: "Learning Preferences without Interaction for Cooperative AI: A Hybrid Offline-Online Approach"
title_zh: 无交互偏好学习：面向协作AI的混合离线-在线方法
authors: "Haitong Ma, Haoran Yu, Haobo Fu, Shuai Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=QVheAhJefR"
tags: ["query:agent-papers"]
score: 4.0
evidence: 无需交互学习人类偏好的协作智能体
tldr: 该论文提出混合离线-在线方法，使协作智能体能够从少量离线偏好反馈中学习人类偏好，而无需在线交互。通过解决分布不匹配问题，智能体在保持任务性能的同时符合用户偏好。该工作涉及多智能体协作，但侧重人机协作而非代理间协作。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qvheahjefr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1201, \"height\": 682, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qvheahjefr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1430, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qvheahjefr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 563, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qvheahjefr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qvheahjefr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 792, \"height\": 579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qvheahjefr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1246, \"height\": 974, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 695, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 697, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 840, \"height\": 133, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1183, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1145, \"height\": 540, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 905, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 775, \"height\": 930, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 779, \"height\": 1148, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1440, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 847, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1186, \"height\": 327, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1441, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 800, \"height\": 238, \"label\": \"Table\"}]"
motivation: 协作智能体通常忽略人类偏好，而人类难以提供在线反馈。
method: 结合离线偏好数据和在线强化学习，缓解分布不匹配。
result: 在模拟和真实用户实验中，智能体同时优化了任务和偏好。
conclusion: 该方法提升了协作AI的实用性，但仅限于人机协作场景。
---

## Abstract
Reinforcement learning (RL) for collaborative agents capable of cooperating with humans to accomplish tasks has long been a central goal in the RL community. While prior approaches have made progress in adapting collaborative agents to diverse human partners, they often focus solely on optimizing task performance and overlook human preferences—despite the fact that such preferences often diverge from the reward-maximization objective of the environment.
Addressing this discrepancy poses significant challenges: humans typically provide only a small amount of offline, preference-related feedback and are unable to engage in online interactions, resulting in a distributional mismatch between the agent’s online learning process and the offline human data. To tackle this, we formulate the problem as an online&offline reinforcement learning problem that jointly integrates online generalization and offline preference learning, entirely under an offline training regime.
We propose a simple yet effective training framework built upon existing RL algorithms that alternates between offline preference learning and online generalization recovery, ensuring the stability and alignment of both learning objectives.
We evaluate our approach on a benchmark built upon the Overcooked environment—a standard environment  for human-agent collaboration—and demonstrate remarkable performance across diverse preference styles and cooperative scenarios.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：协作式强化学习智能体在与人类合作时，通常只优化环境奖励最大化目标，而忽视了人类用户的个性化偏好（如偏好特定菜品、操作风格等）。然而，人类用户往往无法在线交互，只能提供少量离线偏好反馈（如“点赞”轨迹），这导致智能体在线学习与离线偏好数据之间存在分布不匹配，难以在保持泛化能力的同时对齐偏好。
- **现实背景**：在多人游戏（如《英雄联盟》《王者荣耀》）中，玩家赛后通过“点赞”机制表达对队友行为的偏好，这些离线轨迹隐含了用户的风格偏好。论文旨在利用这种轻量级离线数据，训练既能泛化到未见伙伴、又能对齐特定偏好的协作智能体。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：受自然语言处理中“预训练 + 监督微调（SFT）”范式的启发，将在线泛化训练视为预训练，将离线偏好学习视为下游任务微调。提出一个三阶段混合框架，通过交替优化解决泛化与偏好对齐的目标冲突。
- **关键技术细节**：
  - **阶段1（预训练泛化先验）**：智能体与策略池（policy pool）中的多样化代理在线交互，使用MAPPO算法优化环境奖励，获得良好的零样本协作泛化能力。
  - **阶段2（偏好学习+恢复）**：对预训练智能体进行离线行为克隆（BC），拟合少量“点赞”轨迹；随后通过在线交互恢复泛化能力（恢复到预训练水平）。
  - **阶段3（逐轮交替恢复，EAR）**：迭代执行“1轮BC → 泛化恢复”的循环，直到偏好准确率恢复至阶段2收敛水平或达到预算上限。这种浅层增量训练避免过度遗忘偏好信息。
- **算法流程（文字描述）**：
  1. 输入：策略池、离线偏好数据、环境、初始智能体。
  2. 阶段1：用策略池训练智能体至收敛，记录平均环境回报`rgen`。
  3. 阶段2：在偏好数据上BC至收敛，记录准确率`η`；然后在线恢复泛化至`≥ rgen`。
  4. 阶段3：重复（1轮BC → 恢复泛化）直到偏好准确率`≥ η`或预算耗尽。
  5. 返回最终策略。

## 3. 实验设计

- **场景/数据集**：基于Overcooked环境（人机协作标准基准），使用两个布局（Coordination Ring、Many Orders）。通过定义偏好奖励函数（对特定事件加权）生成具有不同风格的“人类代理”，其“点赞”轨迹构成少量离线数据集。每个风格约有12~38条轨迹，按4:1划分训练/测试。
- **基准方法**：
  - BC（仅行为克隆）
  - ZSC/Pretrain（FCP方法，仅预训练）
  - Pretrain + BC（预训练后微调）
  - Pretrain + BC + Recover（预训练+BC+单次恢复）
  - 额外对比：MEP、TrajDi（强调策略多样性的ZSC方法）
- **评估指标**：
  - 环境回报（Env Return）：成功交付的汤数×20。
  - 偏好分数（Preference Score）：基于事件频率与偏好权重的加权和。

## 4. 资源与算力

- 所有实验在**单张 NVIDIA GeForce RTX 2080 Ti GPU** 上完成。
- 单轮行为克隆（1 epoch BC）耗时约27.1秒；一轮环境rollout（200条轨迹）约5.7秒；一轮PPO更新（15 epochs）约10.5秒。整个训练过程总环境交互步数约为2×10⁶步（每批次200×400步，共约250批次）。

## 5. 实验数量与充分性

- 在**两个布局、三种偏好风格**上各进行3次随机种子实验，报告均值与标准差。
- 包含**消融实验**：有无预训练、不同恢复策略、EAR与单次恢复对比。
- 扩展实验：与多样性增强方法（MEP、TrajDi）对比，验证偏好覆盖之外的场景。
- 补充分析：UMAP可视化行为分布、动作准确率变化曲线、回滚成本收敛表。
- **评价**：实验设计较完整，对比基线覆盖了主流范式，统计重复性良好，结果客观且公平。但仅在Overcooked单一环境上验证，泛化性受限。

## 6. 论文的主要结论与发现

1. 直接对少量偏好轨迹进行BC会导致泛化能力急剧下降（环境回报降低1/3以上），而恢复泛化过程会部分遗忘偏好信息。
2. 预训练阶段对小型智能体至关重要：从随机初始化开始微调，即使经过大量恢复也无法达到预训练的泛化水平。
3. 提出的三阶段框架（预训练→BC+恢复→EAR）有效平衡了偏好对齐与泛化：在偏好分数和环境回报上均优于所有基线。
4. 逐轮交替恢复（EAR）相比于单次恢复，能更好保留偏好信息（动作准确率更高），且收敛过程稳定、预算合理（约200批次内完成）。

## 7. 优点

- **方法简洁有效**：灵感来源于NLP成熟的预训练+微调范式，直接引入强化学习领域，实现成本低、可复现性强。
- **问题设定贴合实际**：关注用户只能提供离线“点赞”反馈的现实场景，避免了对人类在线交互的依赖，具有工程应用价值。
- **交替恢复策略创新**：通过浅层增量训练避免了传统两阶段方法的遗忘问题，为分布不匹配下的偏好学习提供了有效解决方案。
- **实验分析深入**：通过UMAP可视化、准确率动态曲线等揭示了偏好学习与泛化之间的内在冲突与折中机制。

## 8. 不足与局限

- **环境单一**：仅在Overcooked两个布局上验证，该环境相对简单（离散动作、低维状态），在更复杂的环境（如MOBA游戏、物理模拟）中的有效性未知。
- **偏好代理偏差**：使用根据人工定义偏好奖励训练出的代理模拟人类，与真实人类行为存在差异（如适应性、非理性等）。
- **未利用大量无标签轨迹**：实际场景中存在大量未标记的玩家轨迹，论文未尝试利用这些数据进行半监督或自监督预训练，可能限制偏好对齐上限。
- **仅适用于人机协作场景**：不涉及多智能体内部协作，且假设人类伙伴不可在线交互，适用范围相对狭窄。

（完）
