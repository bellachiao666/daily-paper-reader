---
title: Enhancing Cooperative Multi-Agent Reinforcement Learning with State Modelling and Adversarial Exploration
title_zh: 通过状态建模和对抗探索增强协作多智能体强化学习
authors: "Andreas Kontogiannis, Konstantinos Papathanasiou, Yi Shen, Giorgos Stamou, Michael M. Zavlanos, George Vouros"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=TCsdlqzZNL"
tags: ["query:agent-papers"]
score: 6.0
evidence: 协作多智能体RL结合状态建模与探索
tldr: 无通信部分可观测环境下的多智能体协作困难。本文提出状态建模框架，使智能体推断有用信念表示，并引入对抗探索提升协作策略。实验表明该方法提高了任务执行效率。该工作为分布式多智能体协作提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1482, \"height\": 758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1764, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1429, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1411, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1047, \"height\": 733, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1696, \"height\": 291, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1258, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 710, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 463, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 485, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 752, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 947, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1470, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1459, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1762, \"height\": 316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 734, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1567, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1765, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 580, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 569, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 567, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1728, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 682, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 691, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1457, \"height\": 890, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1687, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 568, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1653, \"height\": 1026, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 532, \"height\": 711, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 724, \"height\": 1143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 744, \"height\": 1012, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 537, \"height\": 795, \"label\": \"Table\"}]"
motivation: 无通信部分可观测环境下多智能体协作挑战大。
method: 提出状态建模框架，智能体学习信念表示，结合对抗探索。
result: 在协作任务上取得了更好的策略和探索效率。
conclusion: 信念表示和对抗探索可有效促进协作。
---

## Abstract
Learning to cooperate in distributed partially observable environments with no communication abilities poses significant challenges for multi-agent deep reinforcement learning (MARL). This paper addresses key concerns in this domain, focusing on inferring state representations from individual agent observations and leveraging these representations to enhance agents' exploration and collaborative task execution policies. To this end, we propose a novel state modelling framework for cooperative MARL, where agents infer meaningful belief representations of the non-observable state, with respect to optimizing their own policies, while filtering redundant and less informative joint state information. Building upon this framework, we propose the MARL SMPE$^2$ algorithm. In SMPE$^2$, agents enhance their own policy's discriminative abilities under partial observability, explicitly by incorporating their beliefs into the policy network, and implicitly by adopting an adversarial type of exploration policies which encourages agents to discover novel, high-value states while improving the discriminative abilities of others. Experimentally, we show that SMPE$^2$ outperforms a plethora of state-of-the-art MARL algorithms in complex fully cooperative tasks from the MPE, LBF, and RWARE benchmarks.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：在无通信能力的分布式部分可观测环境中，多智能体深度强化学习（MARL）面临严重挑战。许多现实应用（如多机器人协作、仓储物流、无人机搜索救援等）都要求智能体在仅凭局部观测的情况下协同完成共同目标，且执行时无法进行显式通信。
- **核心问题**：如何让每个智能体从自身局部观测中推断出有意义的全局状态信念（belief），并利用这些信念提升探索效率和协作策略？现有方法存在的问题包括：
  - 智能体建模（agent modelling）推断的信念表示不针对最大化个体价值函数进行优化，可能次优。
  - 未考虑联合状态中的冗余/非信息性特征，导致性能下降。
  - 未利用信念表示改进初始随机探索策略，在稀疏奖励设置中效果差。
- **论文提出目标**：回答两个研究问题：
  - **Q1**：智能体能否学习从其局部观测中推断信息性（潜在）状态表示，以增强自身策略进行协调？
  - **Q2**：智能体能否利用推断出的状态表示高效探索状态空间，发现更优策略？

## 2. 方法论

### 2.1 核心思想

- 提出**状态建模（State Modelling, SM）优化框架**：每个智能体 i 学习一个参数化模型 \(p_{\omega_i}(z_i | o_i)\)，从自身观测 \(o_i\) 推断关于未观测联合状态的有意义信念 \(z_i\)。该信念用于增强自身策略 \(\pi_{\psi_i}(a_i | h_i, z_i)\)，同时通过**AM（Agent Modelling）过滤器**\(w_i\) 滤除冗余/非信息性的联合状态特征（即其他智能体观测中与自身未来奖励最大化无关且无法通过 \(z_i\) 推断的特征）。
- 优化目标：最大化联合价值函数 \(V_{SM}(\omega, \psi)\)，同时加入ELBO项约束重建质量。理论证明 \(V_{SM}^* = V^*\)（与标准Dec-POMDP最优值一致），说明该框架不限制策略的最优性。

### 2.2 关键技术细节

#### （a）自监督状态建模

- 每个智能体 i 使用**变分编码器-解码器（ED）**：编码器 \(q_{\omega_i}(z_i|o_i)\) 输出高斯分布，解码器 \(p_{\phi_i}(\hat{o}_{-i}|z_i)\) 重建其他智能体的观测。
- 引入**AM过滤器**\(w_i = \sigma(\phi_{w_i}(o_i))\)（MLP加 sigmoid），对重建目标 \(o_{-i}\) 进行逐元素加权，过滤掉不相关特征。联合优化以下损失：
  - 重建损失 \(L_{\text{rec}} = \| \tilde{w}_i \cdot o_{-i} - w_i \cdot \hat{o}_{-i} \|^2\)（使用目标网络 \(\tilde{w}_i\) 稳定训练）
  - 正则化损失 \(L_{\text{norm}} = -\|w_i\|_2^2\)（防止过滤器全部归零）
  - KL散度 \(L_{\text{KL}} = \text{KL}(q_{\omega_i}(z_i|o_i) \| \mathcal{N}(0,I))\)
- 策略优化部分基于MAA2C（CTDE架构）：
  - 标准评论家 \(V_\xi(s)\) 提供优势用于演员更新。
  - 额外评论家 \(V_k(\hat{s})\) 基于过滤后的联合观测 \(\hat{s} = o_i \oplus (w_i \cdot o_{-i})\) 训练，用于确保 \(w_i\) 与价值最大化相关。
  - 总编码损失：\(L_{\text{encodings}} = L_{\text{w critic}} + \lambda_{\text{rec}} L_{\text{rec}} + \lambda_{\text{norm}} L_{\text{norm}} + \lambda_{\text{KL}} L_{\text{KL}}\)
- 演员损失：标准策略梯度 + 熵正则，其中条件包含历史 \(h_i\) 和当前信念 \(z_i\)。

#### （b）对抗式计数型内在探索

- 利用信念 \(z_i\) 设计内在奖励，采用**SimHash函数**\(SH\)：\(\hat{r}_i = 1/\sqrt{n(SH(z_i))}\)，\(n(\cdot)\) 为计数。
- 实际奖励为 \(\tilde{r}_i = r_i + \beta \hat{r}_i\)。
- 核心思想：智能体 i 被激励发现新观测（从而新 \(z_i\)），该新观测同时成为其他智能体重建训练中“对抗性”的目标，帮助其他智能体形成更好的全局信念，从而促进协作。
- 为稳定训练，定期硬更新ED参数（每 \(N_{\text{ED}}\) 步）。

### 2.3 算法流程（文字说明）

1. 初始化N个并行的环境，N个演员网络，两个评论家网络及目标网络，N个ED网络和AM过滤器网络及目标过滤器网络。
2. 在每个时间步，每个智能体获取观测 \(o_i\)，采样信念 \(z_i \sim q_{\omega_i}(z_i|o_i)\)，根据策略 \(\pi_{\psi_i}(a_i|h_i, z_i)\) 采样动作。
3. 执行动作，得到下一状态、观测和共享奖励 \(r_t\)。
4. 计算内在奖励 \(\hat{r}_i\)，得到总奖励 \(\tilde{r}_i = r_t + \beta \hat{r}_i\)，存入经验缓冲池。
5. 当并行回合结束，依次更新演员、标准评论家、w评论家。
6. 每 \(N_{\text{ED}}\) 步，从缓冲池采样一批数据，更新ED参数（最小化 \(L_{\text{rec}} + L_{\text{KL}}\)）和AM过滤器参数（最小化 \(L_{\text{rec}} + L_{\text{norm}}\)）。
7. 定期软/硬更新目标网络。

## 3. 实验设计

### 3.1 使用的Benchmark和任务

- **MPE (Multi-Agent Particle Environment)**：包含两个完全协作任务：
  - **Spread**（N个智能体覆盖N个地标），测试规模3、4、5、8个智能体。
  - **Double Speaker-Listener**（说话者-听者通信任务）。
- **LBF (Level-Based Foraging)**：六个任务，包括2s-12x12-2p-2f、2s-9x9-3p-2f、4s-11x11-3p-2f、7s-20x20-5p-3f等（s=视距，p=智能体数，f=食物数）；其中一些被先前工作标注为“开放挑战”（稀疏奖励，高度协调）。
- **RWARE (Multi-Robot Warehouse)**：三个困难任务tiny-2ag-hard、tiny-4ag-hard、small-4ag-hard（稀疏奖励，需序列动作）。

### 3.2 对比方法

- **MPE**：MAA2C、COMA、MAPPO、ATM（基于Transformer的工作记忆）。
- **LBF和RWARE**：额外对比基于内在动机的方法：EOI（多样性）、EMC（好奇心）、MASER（子目标生成），以及QMIX（仅作为基线）。
- **消融实验**：对比SMPE（无内在奖励）、SMPE（无AM过滤器）、SMPE（无KL）、SMPE（无L2范数）、标准SimHash替换对抗探索（obs rew）；对比MLIAM（多智能体扩展的LIAM）、SIDE（状态推断方法）；对比SMPE$^2$ vs SMPE(no intr)、SMPE$^2$ vs SMPE(no critic w)等。
- **灵活性测试**：SMPE PPO（以MAPPO为backbone）。

### 3.3 实验设置

- 评估指标：**未归一化的平均每回合奖励**，报告25%-75%置信区间（基于6个随机种子）。
- 时间步数：MPE和LBF为10M，RWARE为40M。
- 超参数：详细列于附录表格（包括学习率、隐藏层维度、潜在维度、各种损失系数等）。

## 4. 资源与算力

- 论文中**未明确说明**使用了多少GPU（型号、数量）以及总训练时长。仅提及一台机器的规格用于运行时间比较（附录E.4.12）：**GPU RTX 3080ti，CPU 11th Gen Intel Core i9-11900，64GB RAM**。
- 在该机器上，不同方法在LBF任务上的运行时间对比（表2）显示SMPE$^2$运行约1小时13分钟，远快于EOI（17h）、EMC（1d5h）、MASER（1d1h），稍慢于MAA2C（37min）和COMA（54min）。但**未说明训练一次完整实验的总GPU时间**，也未提及并行环境数量对实际计算的影响。

## 5. 实验数量与充分性

- **实验数量**：较为充分。在三个基准（MPE、LBF、RWARE）上共进行了约5+6+3=14个主要任务的对比，每个任务6个种子。此外，在附录中进行了多项消融实验：
  - 组件消融（内在奖励、AM过滤器、KL、L2范数、标准SimHash）。
  - 策略优化相关消融（第二评论家必要性）。
  - 超参数灵敏度（\(\lambda_{\text{rec}}\)、\(\lambda_{\text{norm}}\)）。
  - 嵌入表达性分析（t-SNE+逻辑回归）。
  - 灵活性与多backbone验证（MAPPO）。
  - 与其他建模方法对比（MLIAM、SIDE）。
- **充分性评价**：实验设计较为全面，覆盖了不同复杂度、不同奖励密度的任务，消融实验验证了每个关键组件的贡献。基准对比考虑了多种代表性算法（基于价值、基于策略、基于内在动机、基于注意力）。**公平性**方面：所有方法使用相同或接近的超参数设置，代码基于统一框架（EPyMARL），运行时间对比显示SMPE$^2$计算效率可观。但需注意：某些基线（如EMC、MASER）在LBF上表现极差，可能因为其依赖QMIX基础，而QMIX本身在LBF上表现不佳，但论文已指出这一点。

## 6. 主要结论与发现

- SMPE$^2$在**所有三个benchmark的多数任务上显著优于state-of-the-art方法**，特别是在高复杂度、稀疏奖励任务（如LBF 2s-9x9-3p-2f和4s-11x11-3p-2f，RWARE small-4ag-hard）中优势明显，能完全解决一些被标注为“开放挑战”的任务。
- **自监督状态建模**（尤其是AM过滤器）对于提取有用信念至关重要；去掉过滤器或KL散度会导致性能下降。
- **对抗式探索**（基于信念哈希的内在奖励）比标准观测哈希探索更有效，因为其隐式促进多智能体间的协作探索。
- **将信念表示与策略优化直接关联**（通过额外w评论家）比仅作为辅助任务（如MLIAM）更优。
- 方法具有灵活性：可与不同backbone（如MAPPO）结合，仍优于原backbone。
- t-SNE可视化表明，带有KL正则的信念嵌入具有更好的内聚性，有利于协作。

## 7. 优点

- **方法创新**：将状态建模与策略优化联合学习，并引入AM过滤器自动筛选信息性特征，解决冗余信息问题；提出对抗式探索思想，利用信念进行相互激励性探索，区别于简单计数。
- **理论支撑**：证明状态建模框架的最优值与原问题一致，不约束策略类。
- **实验扎实**：多benchmark、多任务、多对比方法、详尽消融，涵盖密集和稀疏奖励、不同智能体规模。
- **实用性强**：不需要通信通道，执行时仅依赖局部观测和信念，适用于现实去中心化系统；计算量相对较小（与许多探索方法相比速度快一个数量级）。
- **可扩展验证**：展示了与MAPPO等不同backbone的兼容性。

## 8. 不足与局限

- **实验覆盖的局限**：只测试了三个离散动作空间的模拟环境（MPE、LBF、RWARE），未在连续控制或更大规模场景（如SMAC、Google Research Football）中评估。MPE任务相对简单，主要验证密集奖励下的状态建模效果；高难度任务仅见于LBF和RWARE的少数场景。
- **超参数敏感性**：多个损失系数（\(\lambda_{\text{rec}}, \lambda_{\text{norm}}, \lambda_{\text{KL}}, \beta\)）需要调参，文中虽提供消融但未给出高度鲁棒性的保证。尤其是 \(\lambda_{\text{norm}}\) 取值较敏感（0.1-1影响不大，但必须非零）。
- **理论基础**：虽然证明了价值等价性，但实际优化是非凸的，收敛性分析缺乏；对抗探索部分仅基于启发式计数，缺乏理论稳定性证明。
- **潜在偏差**：所有实验基于单一实现框架（EPyMARL）和固定种子集（6个）；不同随机种子下方差未完全消除（置信区间较宽）。某些基线（如EMC、MASER）在LBF上的差表现可能部分由于超参数未针对该环境优化，但作者已声明使用原始论文默认参数。
- **资源报告不充分**：未披露完整训练所需总GPU时间，不利于可重复性评估。
- **可扩展性**：推理时每个智能体需要使用ED推断z_i，且需维护计数表，在大规模智能体（如>50）或高维连续观测下，计算与内存开销可能成问题。文中未讨论智能体数量对性能的影响（MPE只到8个，LBF到7个）。
- **假设限制**：假设联合观测足以区分状态，且环境状态转移满足马尔可夫性；对于严重非平稳或具隐藏信息的环境可能受限。另外，AM过滤器的正则化依赖 -\|w_i\|_2^2，可能鼓励大权重而非真正信息性权重。

（完）
