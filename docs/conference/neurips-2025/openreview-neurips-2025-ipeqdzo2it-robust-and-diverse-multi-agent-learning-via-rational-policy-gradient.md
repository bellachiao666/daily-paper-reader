---
title: Robust and Diverse Multi-Agent Learning via Rational Policy Gradient
title_zh: 基于理性策略梯度的鲁棒多样化多智能体学习
authors: "Niklas Lauffer, Ameesh Shah, Micah Carroll, Sanjit A. Seshia, Stuart Russell, Michael D Dennis"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ipEqdzO2IT"
tags: ["query:agent-papers"]
score: 6.0
evidence: 保持理性的对抗优化方法，用于多智能体协作任务
tldr: 多智能体对抗优化在协作场景容易导致智能体自我破坏，论文提出理性保持策略优化（RPO），通过确保智能体行为始终相对于某合作策略最优，避免自我破坏。实验结果证明RPO能有效训练鲁棒且多样化的协作策略，为多智能体系统安全学习提供了保障。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1424, \"height\": 739, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 479, \"height\": 200, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 726, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1411, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1419, \"height\": 1753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1426, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 447, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 597, \"height\": 207, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1386, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 305, \"height\": 305, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1437, \"height\": 281, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 987, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 856, \"height\": 209, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 658, \"height\": 172, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 989, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 987, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 986, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 988, \"height\": 371, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ipeqdzo2it/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 950, \"height\": 419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ipeqdzo2it/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 517, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ipeqdzo2it/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1380, \"height\": 616, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ipeqdzo2it/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 659, \"height\": 137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ipeqdzo2it/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 809, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ipeqdzo2it/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 667, \"height\": 226, \"label\": \"Table\"}]"
motivation: 对抗优化在协作环境中会引发智能体自我破坏，阻碍任务完成。
method: 引入理性保持约束，使智能体策略相对于某可能伙伴策略最优。
result: 在多种多智能体协作任务中，RPO成功避免了自我破坏并提升了策略多样性。
conclusion: 理性保持是解决协作对抗学习问题的关键。
---

## Abstract
Adversarial optimization algorithms that explicitly search for flaws in agents' policies have been successfully applied to finding robust and diverse policies in the context of multi-agent learning. However, the success of adversarial optimization has been largely limited to zero-sum settings because its naive application in cooperative settings leads to a critical failure mode: agents are irrationally incentivized to *self-sabotage*, blocking the completion of tasks and halting further learning. To address this, we introduce *Rationality-preserving Policy Optimization (RPO)*, a formalism for adversarial optimization that avoids self-sabotage by ensuring agents remain *rational*—that is, their policies are optimal with respect to some possible partner policy. To solve RPO, we develop *Rational Policy Gradient (RPG)*, which trains agents to maximize their own reward in a modified version of the original game in which we use *opponent shaping* techniques to optimize the adversarial objective. RPG enables us to extend a variety of existing adversarial optimization algorithms that, no longer subject to the limitations of self-sabotage, can find adversarial examples, improve robustness and adaptability, and learn diverse policies. We empirically validate that our approach achieves strong performance in several popular cooperative and general-sum environments. Our project page can be found at https://rational-policy-gradient.github.io.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在多智能体强化学习（MARL）中，对抗优化算法（如自博弈）在零和博弈中能成功训练鲁棒和多样化的策略，但在合作或一般和（general-sum）环境中，直接应用会导致**自我破坏（self-sabotage）** 行为——智能体为了最小化同伴的奖励而主动破坏任务完成，从而阻碍学习。
- **研究动机**：如何将对抗优化的优势（发现漏洞、提高鲁棒性、学习多样化策略）扩展到合作/一般和场景，同时避免智能体的非理性行为。
- **整体含义**：本文提出**理性保持策略优化（RPO）** 形式化框架，以及具体求解算法**理性策略梯度（RPG）**，使得智能体在对抗优化过程中始终保持**理性**（即其策略相对于某个可能的同伴策略是最优的），从而消除自我破坏，实现鲁棒、多样的策略学习。

## 2. 论文提出的方法论

- **核心思想**：
  - **RPO形式化**：将原始对抗优化问题增加约束——每个智能体的策略必须是针对至少一个可能的同伴策略的最优响应（即理性策略）。数学上表示为：
    \[
    \max_{\pi_i} O_i(\pi_1,\dots,\pi_m) \quad \text{s.t.} \quad \exists \pi'_{-i} \in \Pi_{-i}, \pi_i \in \text{BR}(\pi'_{-i})
    \]
  - **RPG算法**：通过引入**操纵者（manipulator）** 智能体来间接满足理性约束。每个基智能体（base agent）仅负责最大化自身奖励（与自己的操纵者互动），确保理性；而操纵者负责优化原始对抗目标，通过**对手塑形（opponent shaping）** 技术（利用高阶梯度）影响基智能体的学习方向。
- **关键技术细节**：
  - 基智能体使用标准策略梯度更新；操纵者基于**Loaded DiCE**损失函数计算高阶梯度，通过未来基智能体参数更新后的效果来优化。
  - 引入**同伴游戏正则化（partner-play regularization）**：在基智能体的训练数据中加入与评估对象（其他基智能体）的少量对局，减少分布偏移。
  - 算法流程：对基智能体进行N步前瞻更新（模仿最佳响应），然后基于更新后的基智能体计算对抗目标的高阶梯度更新操纵者，最后一步更新基智能体自身。
- **衍生算法**：基于RPG扩展了多种现有对抗优化方法，包括：
  - **AP-RPG**（对抗策略-RPG）、**AT-RPG**（对抗训练-RPG）、**PAIRED-RPG**、**PAIRED-Attack-RPG**、**XPD-RPG**（交叉博弈多样性-RPG）。

## 3. 实验设计

- **环境/场景**：
  - **矩阵博弈**：包含零和、合作、混合动机的多种支付矩阵（如囚徒困境变体、石头剪刀布等）。
  - **Overcooked**：标准合作烹饪游戏，使用多种布局（Cramped Room、Forced Coordination、Counter Circuit、Coordination Ring）。
  - **STORM**：空间-时间矩阵博弈，智能体需收集相同颜色的硬币。还使用了修改版（隐藏同伴位置、可破坏版）。
  - **Hanabi**：简化版（3色3等级和4色4等级）。
- **基准方法**：
  - **自博弈（SP）**（不同熵系数），**对抗策略（AP）**，**对抗训练（AT）**，**PAIRED**，**交叉博弈多样性（XPD）** 基线，**CoMeDi**（之前防止自我破坏的SOTA）。
- **对比方式**：
  - 多样化策略：比较自博弈、交叉博弈奖励；使用**交叉博弈网格图**展示不同种子间的相互表现；计算**群体内交叉博弈平均奖励**。
  - 鲁棒性：训练后的策略与不同对手配对测试（cross-play）。
  - 对抗攻击：训练攻击者（AP-RPG、PAIRED-A-RPG）攻击固定受害者，比较受害者reward。

## 4. 资源与算力

- **明确说明**：论文在附录E.3中给出算力细节。
- **详情**：
  - 单GPU实验（A4000或A6000），本地SLURM集群，每实验使用32个CPU核心、50GB内存。
  - 每个种子运行时间从1分钟到24小时不等。
  - 未给出精确总GPU时数，但表明实验规模中等。

## 5. 实验数量与充分性

- **实验数量**：涵盖4大类环境（矩阵、Overcooked、STORM、Hanabi），每个环境多种布局/变体，多个种子（如Overcooked中每个算法5个种子），包括训练曲线、交叉博弈网格、消融实验（如RPG前瞻步数影响）。
- **充分性**：
  - 对比了多种基线（SP、XPD、CoMeDi等），覆盖鲁棒性、多样性、对抗攻击三个维度。
  - 提供了统计误差（95%置信区间、标准差）。
  - 实验设计客观：使用固定种子、独立运行，评估指标包括自博弈和交叉博弈奖励。
  - 不足：缺少大规模环境（如全尺寸Hanabi 5色5等级）的实验；消融实验仅针对矩阵博弈（前瞻步数），对其他超参数（如同伴游戏系数、学习率）未系统消融。

## 6. 论文的主要结论与发现

- **RPO/RPG有效防止自我破坏**：在合作和一般和环境中，所有RPG变体（AT-RPG、XPD-RPG等）均避免了非理性自毁行为，而基线（XPD、CoMeDi、AP、AT）出现明显的自我破坏（如故意站在盘子前阻碍、捡负面颜色的硬币）。
- **发现真正多样化的策略**：XPD-RPG学到的策略在交叉博弈中仍能获得正奖励（而非降至0），说明其多样性源于策略不兼容而非自毁。在Overcooked的Cramped Room中，XPD-RPG交叉博弈奖励高，说明该环境本身不存在真正多样性。
- **提升鲁棒性**：XPD-RPG训练的智能体与不同伙伴配对时表现稳定，显著优于自博弈（特别是高熵SP）。在Forced Coordination布局中，XPD-RPG作为列玩家能适应任何洋葱传递策略。
- **发现有理的对抗样本**：AP-RPG和PAIRED-A-RPG能发现实际漏洞（如受害者假设的顺时针绕行策略），而原始的AP直接自毁。
- **稳定学习动力学**：增加RPG前瞻步数可以稳定矩阵博弈中的振荡，帮助收敛到混合策略均衡。

## 7. 优点

- **方法论创新**：RPO形式化简洁有力，首次将“理性”约束引入对抗优化通用框架；RPG利用对手塑形技术巧妙实现该约束，无需显式枚举所有同伴策略。
- **通用性强**：可扩展多种现有对抗算法（AP、AT、PAIRED、XPD），适用于零和、合作、一般和场景。
- **实证充分**：在多个典型MARL基准上展示效果，覆盖全面；使用交叉博弈网格图直观展示鲁棒性差异；可视化对抗样本（如Overcooked中的绕行冲突）增强了可解释性。
- **防止分布偏移**：同伴游戏正则化设计合理，确保基智能体训练分布与评估分布一致。
- **代码开源**：提供了项目页面和代码仓库，便于复现。

## 8. 不足与局限

- **计算开销**：RPG依赖高阶梯度，需要较大批量稳定训练（文中提及高方差问题），且每个基智能体需要额外操纵者，计算成本高（XPD-RPG约为普通XPD的3倍时间）。在更高维域可能难以扩展。
- **缺乏收敛保证**：目前无理论保证RPG一定收敛到RPO的解，仅凭经验观察稳定。
- **环境局限性**：实验未覆盖全尺寸Hanabi（5色5等级）、大规模部分可观测场景；Overcooked布局相对简单（Lauffer等人指出其协调需求低）。
- **超参数敏感性**：不同环境需要调整超参数（学习率、同伴游戏系数、前瞻步数等），缺乏系统调参指导。
- **多样性度量的局限**：论文主要使用自博弈与交叉博弈奖励差异作为多样性指标，未与其他多样性度量（如互信息、行为距离）对比。
- **未与最新方法（如LIPO、ADVERSITY）充分区分**：XPD基线几乎等同于ADVERSITY，但未直接复现其结果；与CoMeDi的对比仅在一个环境中显示失效，未深入分析原因。

（完）
