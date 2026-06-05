---
title: "Wonder Wins Ways: Curiosity-Driven Exploration through Multi-Agent Contextual Calibration"
title_zh: 奇异制胜：通过多智能体上下文校准进行好奇心驱动探索
authors: "Yiyuan Pan, Zhe Liu, Hesheng Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=1fOGTbO5Sx"
tags: ["query:agent-papers"]
score: 6.0
evidence: 多智能体强化学习中的好奇心驱动探索
tldr: 该论文针对多智能体强化学习中稀疏奖励下的探索难题，提出通过观察同伴行为校准好奇心的机制，区分环境随机性与有意义新奇。在通信受限的分散式多智能体设置中，该方法提升了探索效率和最终性能，属于多智能体协作与长期推理范畴。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-1fogtbo5sx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1377, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1fogtbo5sx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1fogtbo5sx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1410, \"height\": 341, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1fogtbo5sx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1409, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1fogtbo5sx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1011, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1fogtbo5sx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1402, \"height\": 436, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-1fogtbo5sx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 699, \"height\": 139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1fogtbo5sx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1436, \"height\": 796, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1fogtbo5sx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1428, \"height\": 545, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1fogtbo5sx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1441, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1fogtbo5sx/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1452, \"height\": 621, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1fogtbo5sx/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 858, \"height\": 935, \"label\": \"Table\"}]"
motivation: 现有好奇心机制混淆随机性与新颖性，且忽视同伴行为中的潜在任务动态。
method: 受人类儿童观察同伴校准行为启发，提出多智能体上下文校准的好奇心方法。
result: 在多个MARL基准中探索效率和任务表现均有提升。
conclusion: 该工作为多智能体系统中的自激励探索提供了新范式。
---

## Abstract
Autonomous exploration in complex multi-agent reinforcement learning (MARL) with sparse rewards critically depends on providing agents with effective intrinsic motivation. While artificial curiosity offers a powerful self-supervised signal, it often confuses environmental stochasticity with meaningful novelty. Moreover, existing curiosity mechanisms exhibit a uniform novelty bias, treating all unexpected observations equally. However, peer behavior novelty, which encode latent task dynamics, are often overlooked, resulting in suboptimal exploration in decentralized, communication-free MARL settings. To this end, inspired by how human children adaptively calibrate their own exploratory behaviors via observing peers, we propose a novel approach to enhance multi-agent exploration. We introduce CERMIC, a principled framework that empowers agents to robustly filter noisy surprise signals and guide exploration by dynamically calibrating their intrinsic curiosity with inferred multi-agent context. Additionally, CERMIC generates theoretically-grounded intrinsic rewards, encouraging agents to explore state transitions with high information gain. We evaluate CERMIC on benchmark suites including VMAS, Meltingpot, and SMACv2. Empirical results demonstrate that exploration with CERMIC significantly outperforms SoTA algorithms in sparse-reward environments.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

论文聚焦于**多智能体强化学习（MARL）在稀疏奖励环境下的有效探索问题**。现有好奇心驱动方法存在两个关键缺陷：（1）容易将环境随机性（如“Noisy-TV”问题）误认为有意义的新颖性；（2）对所有意外观察给予均等的新颖性偏置，忽视了同伴行为中蕴含的潜在任务动态信息。在部分可观测、无通信的分散式执行设定下，这些问题尤为突出。受人类儿童通过观察同伴校准自身探索行为的启发，论文提出 **CERMIC（Curiosity Enhancement via Robust Multi-Agent Intention Calibration）**，一个即插即用的模块，用于动态校准内在好奇心与推断出的多智能体上下文，从而产生更鲁棒、更具信息性的探索信号。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：基于**信息瓶颈（IB）** 原则，学习一个多智能体上下文化的探索表示，过滤不可预测的虚假新颖性，同时保留对任务有价值的预测信息。
- **关键技术细节**：
  - **新颖性驱动探索**：最大化当前状态-动作对 \(X_t\) 与下一状态 \(S_{t+1}\) 的互信息，通过最大化变分下界实现，使编码器 \(p_\phi(s_{t+1}|x_t)\) 准确预测下一状态。
  - **多智能体上下文化压缩**：最小化 \(X_t\) 与当前状态-动作对 \([S_t, A_t]\) 的互信息，但引入**分布鲁棒的机会约束**，利用其他智能体的推断图特征 \(f_{\text{on}}\) 对压缩过程进行校准。具体地，对变量 \(\Psi_t = \log\frac{p(x_t|s_t,a_t)}{q(x_t)}\) 施加机会约束 \(\Pr(\Psi_t \leq \bar{c}) \geq 1-\epsilon\)，并使其对均值和方差的扰动鲁棒，最终转化为一个二阶锥损失。
  - **任务自适应校准**：通过信息瓶颈因子 \(\gamma = I([r_{t-1}, f_{\text{on}_{t-1}}]; f_{\text{on}})\) 动态调节上下文对压缩的贡献，使用 InfoNCE 损失对 \(\gamma\) 进行近似计算。
  - **内在奖励**：采用贝叶斯惊奇思想，计算参数 \(\Theta\) 在观测新转移前后的 KL 散度，并利用数据处理不等式推导出一个可计算的下界近似 \(r_t \approx \mathbb{E}_\Theta [D_{\text{KL}}(R_\phi(x_t|s_t,a_t) \| \mathcal{N}(0,I))]^{1/2}\)。
- **算法流程**：在每个 episode 中，智能体执行动作，收集转移经验，计算内在奖励（与外在奖励相加），然后更新策略网络与 CERMIC 模块（损失函数 \(L_C = L_{\text{exploit}}^{\text{UB}} + L_{\text{exploit}}^{\text{LB}} - \alpha L_{\text{explore}}\)）。
- **理论分析**：在线性 MDP 设定下，证明所提出的内在奖励与 LSVI-UCB 探索奖励有界，保证探索的衰减性。

## 3. 实验设计：数据集/场景、基准、对比方法

- **基准测试套件**：
  - **VMAS**：9 个任务（包括 Flocking、Navigation、Balance 等，均适配为稀疏奖励版本）。
  - **MeltingPot**：4 个任务（如 StagHunt、Cleanup、ChickenGame、PrisonersDilemma）。
  - **SMACv2**：2 个任务（Protoss5v5、Zerg5v5，奖励稀疏化）。
- **对比方法**：
  - **标准 MARL**：MAPPO、QMIX、MAPPO-εGreedy。
  - **当前 SoTA**：CPM（VMAS）、QMIX-SPECTRA（SMACv2）。
  - **好奇心方法**：MAPPO-DB、MACE、QPLEX-ICES（均要求通信受限的分散式执行以确保公平比较）。
- **评估指标**：VMAS 使用平均回合奖励，MeltingPot 使用平均回合回报，SMACv2 使用平均测试胜率。所有结果报告均值和标准差。

## 4. 资源与算力

论文在**附录 H** 中提到使用 **NVIDIA Quadro RTX 8000 GPU**，基于 **BenchMARL 套件**进行训练。但**未明确说明 GPU 数量、训练时长等具体算力消耗细节**。

## 5. 实验数量与充分性

- **主要对比**：表 1 覆盖 15 个任务（VMAS 9 个、MeltingPot 4 个、SMACv2 2 个），对比 10 种方法，结果具有广泛代表性。
- **消融实验**：表 3 对损失模块（w/o \(L_{\text{explore}}\)、w/o \(L_{\text{exploit}}\)）、超参数 \(\alpha\)（1.0、0.5、0.2）、记忆类型（GRU vs. Graph）进行消融，覆盖 5 个任务。
- **泛化实验**：表 4 在三种 VMAS 任务上测试从密集奖励训练到稀疏奖励测试的迁移性能。
- **可视化分析**：图 2 展示了智能体轨迹和潜在状态的 t-SNE 可视化；图 3 展示了学习曲线；图 5 为噪声鲁棒性实验；图 6 展示了内在奖励的时间演变。
- **实验充分性评价**：实验数量充足，对比方法全面，消融设计合理，报告了均值与标准差，并提供了定性分析。但部分实验（如噪声鲁棒性）只在两个任务上进行，泛化性略有不足。

## 6. 论文的主要结论与发现

1. **CERMIC 在 12/16 个场景中取得 SoTA 性能**，显著优于基线和现有好奇心方法，尤其是在需要动态交互的 MeltingPot 任务上提升最大。
2. **上下文校准有效过滤噪声**：在与预训练意图模块结合时，收敛速度更快；在噪声环境下，CERMIC 的曲线更稳定、波动更小。
3. **好奇心引导对同伴的探索**：可视化显示 CERMIC 智能体更频繁地靠近其他智能体，且内在奖励在同伴遭遇时出现峰值，说明其有效捕捉了社会性学习信号。
4. **泛化能力强**：从密集奖励训练迁移到稀疏奖励测试时，CERMIC 的性能下降幅度小于所有基线（表 4）。

## 7. 优点

- **理论坚实**：以信息瓶颈和贝叶斯惊奇为基础，并在线性 MDP 中证明内在奖励与 UCB 探索奖励的等价边界，保证探索衰减性质。
- **即插即用**：CERMIC 作为模块化组件，可轻松集成到现有 MARL 算法中（如 MAPPO 和 QMIX）。
- **鲁棒性**：通过分布鲁棒机会约束和任务自适应校准，有效缓解了“Noisy-TV”问题和同伴行为造成的误导。
- **实验充分**：覆盖多个基准、多种基线、消融和泛化实验，并提供定性分析，证据链完整。

## 8. 不足与局限

- **意图建模困难**：在部分可观测、无通信条件下从零学习其他智能体的意图仍然具有挑战性，初始学习速度较慢（论文中曲线显示初期低于部分基线）。
- **扩展性**：当前的图构建和一步潜在转移模型可能难以扩展到高维或复杂多模态任务（论文自身指出这一点）。
- **计算资源细节缺失**：未提供 GPU 数量、训练时间等，可重复性受影响。
- **部分实验覆盖有限**：噪声鲁棒性实验仅两个任务，泛化实验仅三个任务，样本量较小。
- **依赖预训练**：部分变体需要预训练检测器，增加了部署成本（论文在消融中对比了不同记忆类型，但未全面讨论预训练对结果的影响）。
- **某些场景提升不显著**：在 SMACv2 的部分配置中，CERMIC 相对于 SoTA 的增益较小（如表 1 中 zer5v5，MAPPO-CERMIC 仅与 MACE 持平）。

（完）
