---
title: Learning Progress Driven Multi-Agent Curriculum
title_zh: 学习进度驱动的多智能体课程
authors: "Wenshuai Zhao, Zhiyuan Li, Joni Pajarinen"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Al6qG8BlKg"
tags: ["query:agent-papers"]
score: 6.0
evidence: 基于学习进度的多智能体强化学习课程
tldr: 多智能体强化学习中基于智能体数量的课程设置存在方差大和信用分配问题。本文提出基于TD误差的学习进度指标，自动控制课程难度，使智能体从初始分布渐进到目标任务。实验表明该方法有效提升了多智能体学习效率和最终性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 676, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 805, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 823, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1763, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1763, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1767, \"height\": 1743, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 821, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1766, \"height\": 1751, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1765, \"height\": 881, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1274, \"height\": 1063, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1765, \"height\": 867, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-al6qg8blkg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1569, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-al6qg8blkg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1183, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-al6qg8blkg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 614, \"height\": 600, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-al6qg8blkg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 484, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-al6qg8blkg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 562, \"height\": 861, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-al6qg8blkg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 563, \"height\": 863, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-al6qg8blkg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 636, \"height\": 1180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-al6qg8blkg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 567, \"height\": 966, \"label\": \"Table\"}]"
motivation: 现有基于智能体数量的课程方法在高方差和信用分配困难问题。
method: 使用TD误差度量学习进度，自动控制课程从初始分布向目标任务推进。
result: 在多种多智能体任务上提升了学习速度和最终性能。
conclusion: 基于学习进度的课程可有效解决多智能体训练中的难度适应问题。
---

## Abstract
The number of agents can be an effective curriculum variable for controlling the difficulty of multi-agent reinforcement learning (MARL) tasks. Existing work typically uses manually defined curricula such as linear schemes. We identify two potential flaws while applying existing reward-based automatic curriculum learning methods in MARL: (1) The expected episode return used to measure task difficulty has high variance; (2) Credit assignment difficulty can be exacerbated in tasks where increasing the number of agents yields higher returns which is common in many MARL tasks. To address these issues, we propose to control the curriculum by using a TD-error based *learning progress* measure and by letting the curriculum proceed from an initial context distribution to the final task specific one. Since our approach maintains a distribution over the number of agents and measures learning progress rather than absolute performance, which often increases with the number of agents, we alleviate problem (2). Moreover, the learning progress measure naturally alleviates problem (1) by aggregating returns. In three challenging sparse-reward MARL benchmarks, our approach outperforms state-of-the-art baselines.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：在多智能体强化学习（MARL）中，任务难度常与智能体数量相关。现有方法（如FewToMore、EPC、VACL）通常采用手动定义的线性课程（从少到多或从多到少），但这种方式存在两个关键缺陷：
  - **高方差问题**：基于稀疏回合回报（episode return）评估任务难度，方差大、不稳定；
  - **信用分配加剧问题**：许多任务中增加智能体数量反而会提高回合回报（例如Simple-Spread任务中更多智能体更容易覆盖地标），这会让以最大化回报为目标的课程偏向选择更多智能体，从而加重信用分配困难，反而阻碍策略学习。
- **整体含义**：本文提出一种**基于学习进度（learning progress）**的多智能体自动课程方法，利用TD误差作为进度指标，自适应地控制智能体数量分布，使课程从初始分布平滑过渡到目标任务，从而缓解上述两个问题。

## 2. 论文提出的方法论

- **核心思想**：将单智能体自动课程方法SPRL扩展到多智能体场景，但用**期望TD误差**替代回合回报作为任务难度/学习进度的度量。TD误差天然具备低方差特性，并且反映了值函数的收敛程度，从而指示了策略在不同任务上的改进潜力。
- **关键技术细节**：
  - **上下文强化学习框架**：将智能体数量作为上下文变量c，目标分布μ(c)为Dirac delta（对应目标智能体数）。课程学习通过优化上下文分布ν(c)从初始分布逐步逼近μ(c)。
  - **两阶段优化**（继承自SPRL）：
    - **阶段1（提升性能）**：当当前上下文分布下的期望值函数低于阈值V<sub>LB</sub>时，最大化期望学习进度（即TD误差的期望），公式为：
      ```
      max_{ν_{k+1}} (1/M) Σ (p(c_i|ν_{k+1}) / p(c_i|ν_k)) * LP_θ(c_i)
      ```
      其中LP(c) = 0.5 * E[‖R(s,a)−V(s)‖²] 为值函数损失（TD误差的平方）。
    - **阶段2（逼近目标）**：当性能达标后，最小化当前分布与目标分布的KL散度，同时保持性能不低于V<sub>LB</sub>。
  - **实现细节**：使用高斯分布参数化连续上下文，再离散化为整数智能体数；采用参数共享处理新加入智能体；上下文每轮迭代通过信任域优化器更新。
- **算法流程**（文字说明）：
  1. 初始化上下文分布ν₀、策略θ₀、目标分布μ(c)、阈值V<sub>LB</sub>等；
  2. 对于每一轮k：
     - **策略学习**：采样M个上下文c_i，执行轨迹，用MAPPO更新策略；
     - **估计学习进度**：对每个c_i计算TD误差并平均；
     - **上下文更新**：若平均性能< V<sub>LB</sub>，执行阶段1（最大化LP）；否则执行阶段2（最小化KL）；
  3. 重复直至收敛。

## 3. 实验设计

- **数据集/场景**（三个基准）：
  - **MPE Simple-Spread**：8个智能体、8个地标，稀疏奖励（至少覆盖4个地标才给奖励）。
  - **XOR矩阵游戏**：20个玩家，需输出不同动作才能获得正奖励，稀疏奖励。
  - **SMAC-v2 Protoss**：5v5、6v6、7v7、8v8共4个任务，稀疏奖励（+1赢/-1输）。另有额外实验：Terran 5v5、6v6，Zerg 5v5、6v6，以及BenchMARL的Balance和Wheel任务（密集奖励）。
- **Benchmark**：与以下方法对比：
  - **Linear**：线性课程（从少到多或从多到少），代表现有启发式方法。
  - **VACL**：变分自动课程学习，但使用回报作为目标。
  - **ALPGMM**：基于绝对学习进度的高斯混合模型，但其进度仍基于回报差值。
  - **SPRLM**：本文直接扩展的SPRL（基于回报）。
  - **W/O teacher**：无课程，直接在目标任务上训练（因稀疏奖励始终得零回报，图中省略）。
  - **SPMARL**：本文提出的基于TD误差学习进度的方法。
- **对比方法**：覆盖了手工课程、回报式自动课程、以及基于回报差值的进度方法，对比全面。

## 4. 资源与算力

- 论文致谢部分提到使用了**LUMI超级计算机**（EuroHPC联合事业）、**Aalto Science-IT**计算资源，以及**芬兰研究委员会资助**。但**未明确说明具体的GPU型号、数量、训练时长**等详细硬件配置。
- 实验设置中给出每个任务的具体超参数（如rollout线程数：MPE 256，XOR 50，SMACv2 25等），但未汇总总计算时间。

## 5. 实验数量与充分性

- **主实验**：6个任务（SimpleSpread、XOR、SMACv2的4个Protoss任务），每个任务5个随机种子，汇报均值和95%置信区间。
- **额外实验**：
  - 4个更多SMACv2任务（Terran 5v5/6v6，Zerg 5v5/6v6），验证跨种族泛化。
  - 2个BenchMARL任务（Balance、Wheel），验证密集奖励场景下的表现。
  - **方差对比**：在SMACv2 5v5/6v6/7v7/8v8及BenchMARL任务上比较SPMARL和SPRLM的目标估计标准差。
  - **V<sub>LB</sub>消融**：在Protoss 5v5和6v6上测试不同阈值（0.3~0.8）的敏感性。
  - **显著性检验**：使用Mann-Whitney U检验，报告p值（大部分<0.05）。
- **充分性评价**：
  - **覆盖充分**：包含稀疏和密集奖励、不同任务类型（合作、矩阵博弈、微观管理）、不同智能体数量（5~20）。
  - **公平性**：所有方法使用相同的底层算法MAPPO，超参数统一；重复5次随机种子；报告置信区间和显著性检验，结论可靠。
  - **客观性**：实验设计考虑了不同课程方向（增、减、自适应），对比基线覆盖了代表性方法。

## 6. 论文的主要结论与发现

1. **智能体数量作为课程变量有效**：在稀疏奖励任务中，通过控制智能体数量进行课程学习显著优于无课程训练（后者完全失效）。
2. **回报式课程存在缺陷**：SPRLM（基于回报）在SMACv2上除5v5外均失败，表明回报式目标导致上下文分布无法收敛到有效解。
3. **基于TD误差的学习进度方法（SPMARL）稳定且高效**：
   - 在所有任务上**一致优于或持平于所有基线**。
   - 方差显著低于回报式方法，从而更稳定地生成有效课程。
   - 能自动生成先多后少（如Simple-Spread）或先少后多（如XOR）的合理课程，无需人工预设方向。
4. **自动课程比手工线性课程更优**：线性课程常因先验错误（如Simple-Spread中小智能体数更难）失败，或需要大量探索（如XOR线性增才最终收敛）。SPMARL自动找到高效课程路径。
5. **对V<sub>LB</sub>超参数鲁棒**：消融实验显示在0.3~0.8范围内性能稳定。

## 7. 优点

- **方法创新**：首次将**学习进度（TD误差）**引入多智能体课程学习，解决了回报式方法的高方差和信用分配恶化问题。该思想可推广到其他回报式ACRL方法。
- **自动自适应**：无需人工指定课程顺序（线性增/减），算法自动根据学习状态调整智能体数量分布，适应不同任务特性。
- **低方差、高稳定性**：TD误差在每个时间步均可计算，方差远低于回合回报，上下文更新更平滑。
- **实现简洁**：在MAPPO上直接集成，仅需修改上下文更新损失函数，代码已开源。
- **实验严谨**：多基准、多种子、显著性检验、消融实验、方差分析，验证方法鲁棒性和有效性。

## 8. 不足与局限

- **仅测试了MAPPO作为底层算法**：虽然MAPPO是主流，但未验证其他MARL算法（如QMIX、VDN、MADDPG）下的兼容性，通用性有待扩展。
- **V<sub>LB</sub>需经验设定**：文中设置为最大期望回报的80%左右，虽然消融显示鲁棒，但不同任务需人工估计，可能限制实用性。
- **KL约束的必要性未深入探讨**：作者自己在讨论部分指出，当使用学习进度作为目标时，KL约束可能不再是必需的，但未做实验验证解除KL约束的效果。
- **环境限制**：仅在有限智能体数量（≤20）任务上验证，更大规模（如50+）场景的课程效果未报告。
- **参数共享假设**：使用全局策略参数共享来处理新智能体，可能不利于异构智能体任务（如不同角色），论文未讨论异构场景。
- **信用分配问题仅通过课程避免，未从底层算法角度解决**：课程选择避免过多智能体，但本质上未改进CTDE框架下的信用分配机制。
- **资源消耗未量化**：未提供训练时间、GPU内存等具体数据，不便复现和比较计算成本。

（完）
