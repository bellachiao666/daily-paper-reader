---
title: "PARCO: Parallel AutoRegressive Models for Multi-Agent Combinatorial Optimization"
title_zh: PARCO：面向多智能体组合优化的并行自回归模型
authors: "Federico Berto, Chuanbo Hua, Laurin Luttmann, Jiwoo Son, Junyoung Park, Kyuree Ahn, Changhyun Kwon, Lin Xie, Jinkyoo Park"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=9F2Cmgo17M"
tags: ["query:agent-papers"]
score: 7.0
evidence: 通过强化学习实现多智能体协调解决组合优化
tldr: 该论文提出PARCO，一个基于Transformer通信层和并行自回归解码的多智能体强化学习框架，用于高效解决多智能体组合优化问题。在多种任务中，PARCO在解质量和计算速度上均优于现有方法，展示了多智能体协作在复杂问题求解中的潜力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-9f2cmgo17m/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 656, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9f2cmgo17m/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9f2cmgo17m/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 468, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9f2cmgo17m/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 643, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9f2cmgo17m/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 734, \"height\": 759, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9f2cmgo17m/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1321, \"height\": 1489, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-9f2cmgo17m/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 521, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9f2cmgo17m/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 1327, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9f2cmgo17m/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9f2cmgo17m/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 514, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9f2cmgo17m/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1094, \"height\": 508, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9f2cmgo17m/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1235, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9f2cmgo17m/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1311, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9f2cmgo17m/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 337, \"label\": \"Table\"}]"
motivation: 现有方法在智能体协调、泛化性和计算延迟方面存在不足。
method: 提出集成了Transformer通信层和并行解码的通用强化学习框架。
result: 在多个基准上实现更优解和更低延迟。
conclusion: PARCO为多智能体组合优化提供了高效且可扩展的解决方案。
---

## Abstract
Combinatorial optimization problems involving multiple agents are notoriously challenging due to their NP-hard nature and the necessity for effective agent coordination. Despite advancements in learning-based methods, existing approaches often face critical limitations, including suboptimal agent coordination, poor generalization, and high computational latency. To address these issues, we propose PARCO (Parallel AutoRegressive Combinatorial Optimization), a general reinforcement learning framework designed to construct high-quality solutions for multi-agent combinatorial tasks efficiently. To this end, PARCO integrates three key novel components: (1) transformer-based communication layers to enable effective agent collaboration during parallel solution construction, (2) a multiple pointer mechanism for low-latency, parallel agent decision-making, and (3) priority-based conflict handlers to resolve decision conflicts via learned priorities. We evaluate PARCO in multi-agent vehicle routing and scheduling problems, where our approach outperforms state-of-the-art learning methods, demonstrating strong generalization ability and remarkable computational efficiency. We make our source code publicly available to foster future research: https://github.com/ai4co/parco.

---

## 论文详细总结（自动生成）

# PARCO: Parallel AutoRegressive Models for Multi-Agent Combinatorial Optimization 论文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：多智能体组合优化问题（如车辆路径、调度）是NP难的，现有学习方法存在智能体协调不足、泛化性差、计算延迟高三大瓶颈。
- **动机**：传统自回归（AR）模型在单智能体上表现良好，但扩展到多智能体时，要么顺序构造（一个智能体完再下一个），导致高延迟和弱协调；要么并行但缺乏有效的通信和冲突解决机制。
- **目标**：提出一个通用的并行自回归强化学习框架PARCO，同时提升解质量、泛化能力和计算效率。

## 2. 方法论：核心思想、关键技术细节、算法流程

### 核心思想
将多智能体CO建模为**合作式多智能体MDP**，所有智能体在每步**并行**选择动作，通过通信层协调、多指针机制高效解码、优先级冲突处理器保证可行性。

### 关键技术细节
- **并行自回归公式**：  
  ![公式](pθ(a|x) ≜ ∏_{t=1}^T ψ(∏_{m=1}^M gθ(a_t^m | a_{<t}, h)))  
  其中h为编码器输出，gθ为解码器，ψ为冲突解决函数。总构造步骤数从顺序的 ∑T_m 降至 max T_m。

- **多智能体编码器**：  
  分别对智能体和节点进行嵌入（线性投影），然后通过L层Transformer（自注意力或交叉注意力）获得联合表示 h = {h_a, h_n}。

- **通信层（Communication Layers）**：  
  每步解码时，为每个智能体构建动态上下文嵌入 d_m（包含静态智能体嵌入、动态状态、环境特征），投影为查询 q_m。然后通过**多头自注意力+MLP**（式3-4）在智能体间通信，输出更新后的q。该层与智能体数量无关，支持任意M。

- **多指针机制（Multiple Pointer Mechanism）**：  
  - 对更新后的q，通过**掩码交叉注意力**（式5）与节点嵌入交互，得到智能体特定表示。  
  - 计算联合logits u（式6），用tanh缩放，屏蔽不可行动作。  
  - 得到所有智能体的联合概率分布 p(at|a<t, h) = ∏_m exp(u_{m,a_t^m}) / ∑_j exp(u_{m,j})。

- **优先级冲突处理器（Priority-based Conflict Handler）**：  
  - 当多个智能体选择相同动作（如同一客户）时，按优先级排序，仅让优先级最高的执行，其余分配**回退动作**（如原地等待）。  
  - 优先级可基于启发式（如成本最小）或**学习到的概率值**（p(at)越高优先级越高）。  
  - 算法1给出了向量化实现：按优先级降序排序→检测冲突→分配回退→恢复原始顺序。

- **训练**：采用REINFORCE + 共享baseline（POMO风格），损失函数为式(8)，使用B个实例、S个样本计算优势。

## 3. 实验设计

### 测试场景与数据集
| 问题 | 问题规模（N节点/智能体M） | 目标 | 训练数据生成 | 测试数据 |
|------|--------------------------|------|--------------|----------|
| HCVRP（异构容量车辆路径） | N∈{60,100}, M∈{3,5,7} | 最小化最长路径（min-max） | N~U(60,100), M~U(3,7), 坐标、需求、容量、速度随机 | 1280个实例/设置 |
| OMDCPDP（多仓库开放式取送货） | N∈{50,100}, M∈{5,7,10,15,20}；大规模泛化N∈{500,1000}, M∈{50,75,100,100,150,200} | 最小化延迟总和（lateness） | N~U(50,100), M~U(5,20), 需求=1，容量=3 | 1000个实例（in-distribution），100个实例（大规模泛化） |
| FFSP（柔性流水车间调度） | N∈{20,50,100}, M∈{12,18,24,30}（分3个阶段） | 最小化完工时间（makespan） | 按Kwon et al. (2021)方式生成处理时间U(2,10) | 100个实例/设置 |

### 对比方法
- **传统精确/启发式**：SISRs、GA、SA、OR-Tools、Gurobi、Random、SJF、PSO、GA等。
- **神经方法**：AM、ET、DPN、DRL Li、2D-Ptr（HCVRP）；HAM、MAPDP（OMDCPDP）；MatNet（FFSP）。
- 每个神经方法均报告**贪心（g.）**和**采样（s.）**（1280或128个样本）结果。

### 实验包括
- 主结果表（Table 1）：三个问题、多个规模、所有baseline对比。
- 消融实验（图3）：
  - 通信层效果（W/o Comm. vs MLP vs MHA vs Comm.）
  - 冲突处理器效果（Random vs Smallest vs Closest vs Learned）
  - 解码步数和训练时间（与MatNet对比）
- 大规模泛化实验（Table 2）：OMDCPDP上N/M各10倍于训练。
- 推理时间缩放对比（图4）：PARCO vs AR方法随M增加。
- 额外附录实验：mTSP与GNN/分散方法对比、XXL（N=5000）实例。

## 4. 资源与算力

- **硬件**：2×Intel Xeon Gold 6338 CPU + 8×NVIDIA RTX 4090 (24GB VRAM each)。  
- **软件**：Python 3.12, PyTorch 2.5, PyTorch Lightning, RL4CO库。  
- **训练时长**：每个模型训练<24小时（具体：HCVRP约15小时，OMDCPDP<5小时，FFSP按epoch数配置）。  
- **推理**：单CPU+单GPU。

## 5. 实验数量与充分性

- **多问题覆盖**：覆盖路径规划（HCVRP, OMDCPDP）和调度（FFSP）两类典型多智能体CO，增强结论通用性。
- **多规模测试**：每个问题测试多个(N, M)组合，且训练时采用混合分布（不固定大小），测试时看泛化。
- **消融实验充分**：图3对通信层、冲突处理器分别做了A/B测试，并展示了训练效率（解码步数、时间）。
- **与SOTA对比公平**：所有baseline采用官方/reported配置；神经方法同样使用贪心和采样；传统方法给足时间（如OR-Tools 600s）。
- **大规模泛化实验**：Table 2展示了零样本泛化到10倍规模；Table 7进一步验证XXL（N=5000）。
- **稳定性实验**：附录C.3给出收敛速率（不同训练预算下的解质量）。
- **补充对比**：附录C.2对比分散方法（DAN、ScheduleNet等）。

综上，实验覆盖全面、控制变量清晰、结果可靠。

## 6. 主要结论与发现

1. PARCO在所有三个问题上**一致超越**所有神经baseline和传统求解器，在解质量和速度上均达到新SOTA。  
2. 并行自回归机制显著降低推理延迟（相对AR方法加速3.3×~24.7×），且推理时间随智能体数M增加而减少（因为并行步数减少）。  
3. **通信层**有效提升协调性（减少Gap约1-2%），**学习到的优先级冲突处理器**优于随机或启发式规则（减少Gap约0.5%）。  
4. 单模型能够**零样本泛化**到训练时未见的大规模（N, M各10倍以上），且仍优于OR-Tools（300-600s求解时）。  
5. 训练稳定、收敛快（见附录C.3）。

## 7. 优点

- **创新性**：将并行自回归思想系统引入多智能体CO，提出通信层、多指针机制、优先级冲突处理三合一框架。
- **通用性**：可适用于路径规划和调度等多种问题，且支持任意数量的智能体。
- **效率**：通过并行解码大幅降低构造步骤，推理时间远快于顺序AR方法，适合实时部署。
- **鲁棒性**：训练时混合分布、测试时零样本泛化；冲突处理通过学习优先级，更加智能。
- **可复现**：开源代码、详细超参数附录、多种消融和扩展实验。

## 8. 不足与局限

- **智能体数量必须事先指定**：PARCO需要已知M，不能直接用于M未定的问题（如动态增加/减少）。作者在Limitations中承认，未来可通过预测模块或滚动优化解决。
- **回退动作效率损失**：当冲突频繁时，回退（原地等待）可能导致额外步骤，尽管实验显示影响小。
- **实验范围有限**：虽然测试了三个经典问题，但缺少对更多类型多智能体CO（如组合拍卖、网络设计）的验证。
- **与某些最新方法对比不充分**：主实验未包含所有2024/2025年方法（如某些LLM-based方法），但附录补充了mTSP与GNN方法对比。
- **随机性**：采样模式下性能依赖样本数（1280），但已展示在贪心模式下依然领先。
- **训练资源**：需要多GPU（8×RTX 4090），对一般研究者有一定门槛，但相较于传统求解器仍可接受。

（完）
