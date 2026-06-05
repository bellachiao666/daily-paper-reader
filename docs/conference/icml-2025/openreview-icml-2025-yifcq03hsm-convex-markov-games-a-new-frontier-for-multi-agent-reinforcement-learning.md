---
title: "Convex Markov Games: A New Frontier for Multi-Agent Reinforcement Learning"
title_zh: 凸马尔可夫博弈：多智能体强化学习的新前沿
authors: "Ian Gemp, Andreas Alexander Haupt, Luke Marris, Siqi Liu, Georgios Piliouras"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=yIfCq03hsM"
tags: ["query:agent-papers"]
score: 4.0
evidence: 多智能体合作与偏好建模
tldr: 该论文提出了凸马尔可夫博弈，允许一般凸偏好，扩展了传统博弈。证明了纯策略纳什均衡的存在性，并通过梯度下降近似。实验展示了在重复博弈和协作场景中的新颖解。虽然不直接涉及递归自改进，但对多智能体协作和长程推理有理论贡献。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yifcq03hsm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1653, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yifcq03hsm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1771, \"height\": 206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yifcq03hsm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1762, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yifcq03hsm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1296, \"height\": 162, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yifcq03hsm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 270, \"height\": 151, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 871, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 646, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 783, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 819, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1166, \"height\": 418, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 381, \"height\": 151, \"label\": \"Table\"}]"
motivation: 现有博弈模型无法表达非加性偏好，难以处理安全性、公平性等目标。
method: 提出凸马尔可夫博弈类，使用occupancy measure上的凸偏好，通过梯度下降优化可开拓性上界逼近均衡。
result: 在经典重复博弈中找到新解，在协作博弈中得到公平解，并在仓储环境中优化安全长程行为。
conclusion: 凸马尔可夫博弈为多智能体RL提供了更一般的框架，支持多样化偏好下的均衡求解。
---

## Abstract
Behavioral diversity, expert imitation, fairness, safety goals and others give rise to preferences in sequential decision making domains that do not decompose additively across time. We introduce the class of convex Markov games that allow general convex preferences over occupancy measures. Despite infinite time horizon and strictly higher generality than Markov games, pure strategy Nash equilibria exist. Furthermore, equilibria can be approximated empirically by performing gradient descent on an upper bound of exploitability. Our experiments reveal novel solutions to classic repeated normal-form games, find fair solutions in a repeated asymmetric coordination game, and prioritize safe long-term behavior in a robot warehouse environment. In the prisoner's dilemma, our algorithm leverages transient imitation to find a policy profile that deviates from observed human play only slightly, yet achieves higher per-player utility while also being three orders of magnitude less exploitable.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

传统多智能体强化学习（MARL）以**马尔可夫博弈（Markov Game, MG）** 为基础，假设每个智能体的目标可以表示为**线性可加**的折扣累积奖励。然而，现实生活中许多目标（如行为多样性、模仿专家、公平性、安全性等）无法在时间上被简单加性分解——它们依赖于智能体的长期访问频率（occupancy measure）的整体形状，而非逐时间步的线性组合。

- **单智能体领域**已从MDP扩展到**凸马尔可夫决策过程（convex MDP）**，允许任意凸偏好（如熵最大化、风险评估等），并取得了成功（如象棋中的创造性策略发现）。
- **多智能体领域**却缺乏对应的形式化框架：虽然研究人员在实践中已使用熵正则化等技巧，但缺乏理论保证，尤其是**纯策略纳什均衡的存在性**尚未被证明。
- **核心问题**：如何建立一个统一的、理论基础扎实的框架，将凸偏好引入多智能体顺序决策，同时保证均衡存在并给出可计算的近似算法。

**整体含义**：论文填补了表1中的空白——将凸MDP推广到多智能体环境，提出**凸马尔可夫博弈（Convex Markov Game, cMG）**，并证明了纯策略NE的存在性，提供了可微的上界来逼近均衡，在创造力、模仿、公平性、安全性等多个场景展示了全新解决方案。

## 2. 论文提出的方法论

### 2.1 核心思想

- 定义**凸马尔可夫博弈**为6元组 \( G = \langle S, A=\prod_i A_i, P, u, \gamma, \mu_0 \rangle \)，其中每个智能体的效用函数 \( u_i(\mu_i, \pi_{-i}) \) 关于其自身**占有率测度（occupancy measure）** \(\mu_i\) 是**凹函数**（即损失是凸函数），且对对手策略连续。
- 占有率测度 \(\mu_i(s,a)\) 描述了智能体 \(i\) 在状态 \(s\) 下采取动作 \(a\) 的长期折扣频率，与策略 \(\pi_i\) 一一对应（通过式(7)可双向转换）。
- 智能体优化问题本身是凸的（凹函数在凸约束集上最大化），因此每个智能体的**最佳响应集在占有率空间是凸集**，但映射回策略空间后变成**非凸**（图1b）——这打破了传统Kakutani不动点定理的假设。

### 2.2 关键技术细节

- **存在性证明**：使用拓扑学中**可收缩性（contractibility）** 的概念（Debreu, 1952; Kosowsky, 2023），证明即使最佳响应集在策略空间非凸，它们仍然是**可收缩的**，并且存在一个从任意策略剖面到某固定策略剖面的连续形变（homotopy），从而满足广义不动点定理条件，保证**纯策略NE存在**。
- **均衡计算**：直接最小化**可开拓性（exploitability）** \(\epsilon\) 需要通过求解 \(n\) 个凸规划，计算昂贵。论文提出一个**可微的上界**损失函数：
  \[
  L_\tau(\pi) = \sum_i \| \Pi_{TU_i}(\nabla_i^\tau \mu_i) \|^2,
  \]
  其中 \(\Pi_{TU_i}\) 是投影到可行集切空间的算子，\(\nabla_i^\tau \mu_i\) 是**熵正则化效用梯度**。根据定理2，\(\epsilon(\pi) \leq \tau \log(|S|\max_i|A_i|) + \sqrt{2nL_\tau(\pi)}\)，因此最小化 \(L_\tau\) 可以间接降低可开拓性。
- **算法流程**（Algorithm 1）：从初始策略剖面开始，用Adam优化器迭代最小化 \(L_\tau\)，并按照一个退火计划（温度 \(\tau\) 逐渐降低）依次逼近原始博弈的均衡。这种**同伦方法**受经典QRE（Quantal Response Equilibrium）启发，但cMG的起点（最大熵剖面）本身很难求解（联合占有率集非凸），因此论文采用经验退火策略。

### 2.3 公式与算法流程（文字说明）

1. 初始化所有策略为均匀分布。
2. 对于每个时间步 \(t\)，使用当前温度 \(\tau_t\) 计算：
   - 通过式(2)从当前策略得到每个智能体的占有率 \(\mu_i\)。
   - 计算每个智能体效用对 \(\mu_i\) 的梯度 \(\nabla_i u_i\)，加上熵正则化项 \(\tau \nabla H(\mu_i)\)。
   - 构建约束矩阵 \(A(\pi_{-i})\) 并计算投影矩阵 \(\Pi_{TU_i} = I - A^\top(AA^\top)^{-1}A\)。
   - 计算损失 \(L_{\tau_t}(\pi)\)。
   - 用Adam更新每个智能体的logits（即策略参数）。
3. 当满足条件（损失低于阈值或达到最小迭代数）时，按退火规则降低 \(\tau\)。
4. 重复直到 \(\tau\) 降到最小值或达到总迭代次数。
5. 输出最终策略剖面。

## 3. 实验设计

### 3.1 使用的场景/数据集

- **路径规划（Pathfinding）**：2×7网格，两智能体需协调穿越狭窄门到达共同目标，每个回合后重置。
- **迭代正常形式博弈**：
  - **迭代囚徒困境（IPD）**：2人，2动作（合作/背叛），状态为上一回合的联合动作。
  - **迭代公共品博弈（IPGG）**：3人，2动作（All-In/None），乘数1.3。
  - **El Farol酒吧问题**：3人，选择去酒吧或留家，少于3人时去酒吧得2分，否则0分，留家1分。
  - **巴赫-斯特拉文斯基协调博弈**：2人，2动作（Bach/Stravinsky），偏好不同。
- **合成安全域（Synthetic Safety Domain）**：2状态、2动作、2玩家，目标是将占有率限制在安全区域内（用∞范数损失定义）。
- **机器人仓库安全网格世界**：两机器人（左、右）在3格线上移动（送/取包裹），动作“慢”或“快”，快速在取货点同时移动有安全惩罚。
- **人类数据**：用于模仿实验，来自Romero & Rosokha (2023)的IPD人类策略。

### 3.2 基准方法

- **min ϵ**：直接使用CVXPYLAYERS求可开拓性最小值（因数值不稳定容易崩溃）。
- **Sim（同时梯度下降）**：所有智能体同时更新各自策略，报告运行平均。
- **RR（轮流梯度下降）**：按顺序轮流更新一个智能体。
- **SGAMESOLVER**：用于马尔可夫博弈的同伦方法包（Eibelshäuser & Poensgen, 2023）。

### 3.3 对比内容

- 收敛曲线：比较各算法的可开拓性随迭代步数的下降。
- 最终策略分析：对称性、状态依赖、公平性、与人类策略的差异等。
- 在模仿实验中，对比了论文学到的策略与人类策略的效用和可开拓性。

## 4. 资源与算力

文中明确说明：
- 所有实验（除路径规划外）均在**单个CPU**上运行，每个实验大约**一分钟**就能求解。
- 路径规划实验使用了**1个GPU**（未指明型号，可能为单张GPU）。
- 使用**CVXOPT**报告精确可开拓性会增加约**10倍**运行时间。
- 没有提及训练总时长、GPU型号、内存等详细信息。

因此算力需求较低，主要依赖CPU计算。

## 5. 实验数量与充分性

### 5.1 实验数量

论文在 **7个主要域**（路径规划、IPD、IPGG、El Farol、巴赫-斯特拉文斯基、合成安全域、机器人仓库）上进行了测试，每个域有对应的效用函数和超参数。每个实验中，PGL算法通常运行一个种子（未提及多次重复），但巴赫-斯特拉文斯基公平性实验中报告了**10次随机试验**，并发现在所有试验中收敛到相同近似NE（最大可开拓性2.5e-5）。

### 5.2 消融与对比

- 在创造力部分（IPD、IPGG、El Farol），系统对比了4种基线（min ϵ, Sim, RR, SGAMESOLVER）。
- 模仿部分：对比人类策略和学得策略的效用与可开拓性。
- 公平性部分：仅展示了PGL的结果（无基线对比）。
- 安全性：展示了有无安全损失时学习的策略差异，以及从cMG到MG的同伦路径（通过退火）。
- 未进行大规模超参数扫描或多种子消融。

### 5.3 充分性与公平性

**优点**：覆盖了多种偏好类型（熵、KL散度、平方惩罚、非光滑损失），展示了框架的通用性。基线选择合理（包含最直接的梯度方法和同伦包）。定性分析深入（如IPD中PGL找到的对称策略与tit-for-tat类似）。

**不足**：
- 缺乏对算法鲁棒性的系统评估（如不同学习率、退火计划、随机种子变异性）。
- 无大规模消融实验（如投影算子的影响、温度退火策略的敏感性）。
- 部分场景（如公平性）未与基线对比，说服力稍弱。
- 实验规模较小（迭代博弈为4~8个状态，路径规划网格很小），未在更复杂（如大规模状态/动作空间）环境中验证。

总体而言，实验设计**证明概念可行**，但在统计严谨性和大规模验证方面有提升空间。

## 6. 论文的主要结论与发现

1. **形式化定义**：凸马尔可夫博弈允许任意凸偏好，比传统马尔可夫博弈严格更一般。
2. **理论保证**：纯策略纳什均衡总是存在，尽管最佳响应集在策略空间非凸。
3. **可计算上界**：推导了一个可微损失 \(L_\tau\)，其最小化等价于降低可开拓性，可通过梯度下降优化。
4. **创造性均衡**：通过退火熵正则化，PGL在IPD中找到对称、具互惠性的策略（类似tit-for-tat），在IPGG中找到基于他人行动而贡献的策略，优于基线（如始终背叛/零贡献）。
5. **模仿人类策略**：在IPD中，PGL学到的策略与人类数据（Romero & Rosokha, 2023）接近，但效用更高且可开拓性低三个数量级（1.4e-4 vs. 0.47）。
6. **公平性**：在巴赫-斯特拉文斯基博弈中，加入公平性惩罚后双方以约60%的概率选择各自偏爱的事件，实现接近相等的长期访问。
7. **安全性**：在合成域中可以达到精确NE (\(\epsilon=0\))；在机器人仓库中，安全损失使快速动作从69%降至42%，同时保持低可开拓性。

## 7. 优点

- **理论扎实**：突破了非凸最佳响应集的障碍，用拓扑学方法证明了纯策略NE的存在，为后续研究奠定基础。
- **方法实用**：给出了一个可微的、可自动微分的损失函数，可以直接用Adam优化，不需要求解凸规划每个迭代。
- **形式优雅**：统一了多个应用（创造性、模仿、公平性、安全性）在一个框架下，并演示了同伦/退火的实际效果。
- **结果有意义**：在经典博弈（IPD）中发现新均衡，优于传统方法并更接近人类行为与更低的可开拓性。
- **开源代码**：实验中使用了OpenSpiel，并提供了部分代码片段（如安全域），可复现性较好。

## 8. 不足与局限

- **应用场景规模**：所有实验状态/行动空间都很小（最多4状态×2动作×2-3智能体），未在大型连续状态或高维行动空间验证。投影矩阵需要计算 \(AA^\top\) 的逆，其规模随 \(|S|\) 增长，限制了可扩展性。
- **算法收敛无保证**：PGL仅是一个启发性方法，没有收敛到全局最优的保证。虽然论文引用了低退火温度下的上界，但未给出整体收敛分析。
- **无模型免费实现**：算法假设已知环境转移模型（需要知道 \(P\) 来计算 \(\mu_i\) 和投影矩阵）。论文提到模型估计会导致投影算子的无偏估计问题，未给出模型免费方案。
- **实验局限性**：
  - 部分域（公平性、安全）未与强基线对比。
  - 多次运行随机性报告不足（仅巴赫-斯特拉文斯基有10次）。
  - 未做超参数敏感性研究。
- **理论限制**：存在性证明依赖有限状态、有限动作、平稳策略；连续状态/动作空间的情况未处理。此外，效用函数要求对占有率凹且连续，可能不涵盖某些重要非凹目标（如部分安全约束）。
- **与同伦方法的衔接**：论文指出其同伦方法不同于经典QRE，因为最大熵起始点本身难以计算（联合占有率集非凸）。这意味着退火路径可能不连续，可能错过某些均衡。

（完）
