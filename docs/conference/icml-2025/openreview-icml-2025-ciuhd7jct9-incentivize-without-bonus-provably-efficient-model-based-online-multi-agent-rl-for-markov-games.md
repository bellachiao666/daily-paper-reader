---
title: "Incentivize without Bonus: Provably Efficient Model-based Online Multi-agent RL for Markov Games"
title_zh: 无奖励激励：基于模型的多智能体RL在马尔可夫博弈中的高效在线学习
authors: "Tong Yang, Bo Dai, Lin Xiao, Yuejie Chi"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ciUHD7jcT9"
tags: ["query:agent-papers"]
score: 4.0
evidence: 多智能体强化学习中的样本效率
tldr: 该论文提出VMG算法，用于马尔可夫博弈中无奖励激励的模型基在线多智能体RL。通过偏差模型参数估计来进行探索，样本效率高。理论保证收敛到均衡。与递归自改进无关，但属于多智能体RL高效方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ciuhd7jct9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1263, \"height\": 461, \"label\": \"Table\"}]"
motivation: 现有样本高效方法需要定制化不确定性估计或玩家协调。
method: 提出VMG算法，通过偏置模型参数估计以激励探索，无需额外奖励。
result: 理论上证明了样本效率，经验上在标准基准上验证。
conclusion: 为多智能体RL提供了一个简洁且可证明有效的模型基方法。
---

## Abstract
Multi-agent reinforcement learning (MARL) lies at the heart of a plethora of applications involving the interaction of a group of agents in a shared unknown environment. A prominent framework for studying MARL is Markov games, with the goal of finding various notions of equilibria in a sample-efficient manner, such as the Nash equilibrium (NE) and the coarse correlated equilibrium (CCE). However, existing sample-efficient approaches either require tailored uncertainty estimation under function approximation, or careful coordination of the players. In this paper, we propose a novel model-based algorithm, called VMG, that incentivizes exploration via biasing the empirical
estimate of the model parameters towards those with a higher collective best-response values of all the players when fixing the other players' policies, thus encouraging the policy to deviate from its current equilibrium for more exploration. VMG is oblivious to different forms of function approximation, and permits simultaneous and uncoupled policy updates of all players. Theoretically, we also establish that VMG achieves a near-optimal regret for finding both the NEs of two-player zero-sum Markov games and CCEs of multi-player general-sum Markov games under linear function approximation in an online environment, which nearly match their counterparts with sophisticated uncertainty quantification.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究问题**：在多智能体强化学习（MARL）的马尔可夫博弈中，如何在不依赖显式不确定性量化（如置信上界奖励）的情况下，实现样本高效的在线学习并找到均衡解（纳什均衡NE或粗相关均衡CCE）。
- **背景**：现有高效方法大多基于“乐观面对不确定性”原则，需要精心构造奖励项（bonus）来量化不确定性，这在函数近似（如神经网络）下变得复杂且难以推广。同时，许多方法要求玩家之间进行协调或非对称更新，限制了可扩展性。
- **动机**：探索一种替代的探索策略——价值激励探索（value-incentivized exploration），通过偏向模型参数估计来鼓励偏离当前均衡，从而避免显式不确定性量化，并支持所有玩家同步、解耦的策略更新。

## 2. 方法论

- **核心思想**：提出算法 **VMG（Value-incentivized Markov Game solver）**，在每一步模型更新时，不仅最小化经验损失（例如平方误差或负对数似然），还加上一个正则项：最大化所有玩家在当前其他玩家策略固定下的集体最佳响应值。这激励模型朝向“鼓励玩家偏离当前策略”的方向更新，从而自然促进探索。
- **关键技术细节**：
  - **矩阵博弈情形（两玩家零和）**：模型为参数化收益矩阵 \(A_\omega\)，正则项为 \(- \alpha f^{\star,\nu_t}(A_\omega) + \alpha f^{\mu_t,\star}(A_\omega)\)，其中 \((\mu_t,\nu_t)\) 是当前模型下的NE。更新后，分别计算每个玩家的最佳响应策略并收集新样本。
  - **有限时域多玩家一般和马尔可夫博弈**：模型为线性混合转移核 \(P_f\)，正则项为 \(-\alpha \sum_{n=1}^N V^{\star,\pi_{-n}^t}_{f,n}(\rho)\)。更新后，为每个玩家计算最佳响应策略并收集轨迹。
  - **关键等式**：当使用KL正则化（\(\beta>0\)）时，正则项具有封闭形式，可避免双层优化，提高计算效率。
  - **算法流程**（文字描述）：
    1. 初始化模型参数 \(f_0\)，数据集 \(D_0\)。
    2. 对 \(t=1,\dots,T\)：
       a. 根据当前模型 \(f_{t-1}\) 计算均衡策略 \(\pi_t\)（NE或CCE）。
       b. 模型更新：最小化正则化损失（经验损失 + 价值激励正则项）。
       c. 计算各玩家的最佳响应策略。
       d. 收集新轨迹（按照当前均衡策略和最佳响应策略）并加入数据集。
- **简化特例**：可退化为对称矩阵博弈、线性臂、单智能体MDP，并恢复或衍生出新的正则化形式。

## 3. 实验设计

- **论文性质**：纯理论论文，**未进行任何实验验证**。所有结果均为理论界（regret bound、样本复杂度分析）。
- **场景**：理论分析覆盖了两玩家零和矩阵博弈、有限时域多玩家一般和马尔可夫博弈（含线性混合模型）、无限时域折扣马尔可夫博弈。
- **Benchmark**：与现有理论结果对比（如MEX算法、Xiong et al. 2024等），主要比较regret bound和样本复杂度的阶。
- **对比方法**：未进行数值实验，仅在理论层面与基于UCB的方法、MEX等进行比较。

## 4. 资源与算力

- **未涉及**：由于是理论论文，没有提及任何计算资源（GPU型号、数量、训练时长等）。

## 5. 实验数量与充分性

- **无实验**：论文未设计任何数值实验或消融研究。理论证明本身是完备的，但缺乏实际验证。
- **充分性评价**：从理论角度，作者给出了完整证明和多个设定下的regret界，逻辑自洽。但缺乏实验验证其实际性能、收敛速度、对近似误差的鲁棒性等。

## 6. 主要结论与发现

- **矩阵博弈**：VMG在假设线性函数近似下，达到 \( \tilde{O}(d\sqrt{T}) \) 的累积后悔，匹配下界 \(\Omega(d\sqrt{T})\)，样本复杂度 \(\tilde{O}(d^2/\epsilon^2)\)。
- **有限时域马尔可夫博弈**：对一般和博弈，VMG达到 \( \tilde{O}(d\sqrt{H^3 T}) \) 的累积后悔，样本复杂度 \(\tilde{O}(N d^2 H^4 / \epsilon^2)\)（轨迹数 \(\tilde{O}(N d^2 H^3 / \epsilon^2)\)），优于Xiong et al. (2024)的 \( \tilde{O}(d H^5 \sqrt{T})\)，且比MEX（仅两玩家零和）更通用。
- **无限时域折扣情形**：样本复杂度 \(\tilde{O}(N d^2 / ((1-\gamma)^4 \epsilon^2))\)。
- **统一框架**：可退化为带值正则化的单智能体RL、线性臂等，并发现新正则化形式。
- **核心优势**：无需显式不确定性量化，支持所有玩家同时、解耦更新，计算简便，易于与函数近似结合。

## 7. 优点

- **创新性**：首次提出一种无需奖励、基于价值激励探索的通用框架，适用于多玩家一般和马尔可夫博弈，且理论保证接近最优。
- **实用性**：算法结构简单，正则项可闭式求解（当使用KL正则化时），避免双层优化；支持并行独立更新，易于扩展到大量玩家。
- **理论贡献**：给出了多个设定下（矩阵博弈、有限/无限时域）的紧致regret界，填补了无奖励探索在MARL领域的理论空白。
- **统一性**：算法可自然退化为单智能体、线性臂等，连接了现有工作并发现新形式。

## 8. 不足与局限

- **缺乏实验验证**：论文没有任何数值实验或仿真结果，无法评估算法在实际问题中的表现（如收敛速度、对近似误差的鲁棒性、与神经网络结合的效果）。
- **假设较强**：线性函数近似假设（线性混合模型、特征已知、可实现性）在实际高维问题中可能不易满足。
- **计算复杂度未分析**：虽然声称计算简单，但每步需要求解均衡（NE/CCE）和最佳响应，对于大规模状态-动作空间可能仍昂贵。
- **应用限制**：仅针对在线环境，未讨论离线或批处理设置；对抗性环境也未涉及。
- **偏差风险**：价值激励正则项可能导致模型偏向高估价值，理论证明在假设下成立，但实际中可能过激探索。

（完）
