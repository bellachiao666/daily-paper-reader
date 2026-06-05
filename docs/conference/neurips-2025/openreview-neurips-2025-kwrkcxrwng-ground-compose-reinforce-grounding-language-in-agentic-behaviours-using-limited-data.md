---
title: "Ground-Compose-Reinforce: Grounding Language in Agentic Behaviours using Limited Data"
title_zh: Ground-Compose-Reinforce：基于有限数据的语言与智能体行为接地
authors: "Andrew C Li, Toryn Q. Klassen, Andrew Wang, Parand A. Alamdari, Sheila A. McIlraith"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=KWRKCXRwNg"
tags: ["query:agent-papers"]
score: 5.0
evidence: 端到端神经符号框架，从任务规范直接训练RL智能体，无需奖励设计
tldr: 针对语言与感知行动接地需要大量标注数据或手工设计的难题，论文提出Ground-Compose-Reinforce框架，通过奖励机自动从高层任务规范生成训练信号，无需手动奖励函数。实验表明该方法能在有限数据下有效训练智能体，为语言智能体的自动化学习提供了新途径。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwrkcxrwng/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1419, \"height\": 853, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwrkcxrwng/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwrkcxrwng/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 717, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwrkcxrwng/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 560, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwrkcxrwng/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 413, \"height\": 204, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwrkcxrwng/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1256, \"height\": 1699, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwrkcxrwng/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1220, \"height\": 1284, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwrkcxrwng/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1458, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwrkcxrwng/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1466, \"height\": 519, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwrkcxrwng/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1429, \"height\": 451, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwrkcxrwng/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1435, \"height\": 1242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwrkcxrwng/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 914, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwrkcxrwng/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1421, \"height\": 625, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwrkcxrwng/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1459, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwrkcxrwng/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1206, \"height\": 1102, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwrkcxrwng/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1448, \"height\": 1255, \"label\": \"Table\"}]"
motivation: 传统语言接地需要大量人工标注或领域知识，限制了智能体部署。
method: 集成神经符号推理，将任务规范转换为奖励机，端到端训练RL智能体。
result: 在多个语言交互环境中，该方法用极少量数据即可获得与全监督相当的性能。
conclusion: 奖励机结合神经符号方法可有效降低语言智能体训练数据需求。
---

## Abstract
Grounding language in perception and action is a key challenge when building situated agents that can interact with humans, or other agents, via language. In the past, addressing this challenge has required manually designing the language grounding or curating massive datasets that associate language with the environment. We propose Ground-Compose-Reinforce, an end-to-end, neurosymbolic framework for training RL agents directly from high-level task specifications—without manually designed reward functions or other domain-specific oracles, and without massive datasets. These task specifications take the form of Reward Machines, automata-based representations that capture high-level task structure and are in some cases autoformalizable from natural language. Critically, we show that Reward Machines can be grounded using limited data by exploiting compositionality. Experiments in a custom Meta-World domain with only 350 labelled pretraining trajectories show that our framework faithfully elicits complex behaviours from high-level specifications—including behaviours that never appear in pretraining—while non-compositional approaches fail.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：在构建能够通过语言与人类或其他智能体交互的具身智能体时，**语言接地**（grounding language in perception and action）是一个根本性挑战。传统方法要么需要手动设计领域特定的语言解释（如语言条件奖励函数），要么需要收集海量的语言-环境配对数据集进行端到端训练，这些方法在复杂、非模拟场景或数据稀少的机器人应用中难以实施或容易失败。
- **研究动机**：本文希望利用任务的组合性结构（compositionality），通过极少量标注轨迹数据就能将高层任务规范（如自然语言指令或形式化规范）接地到智能体的感知和动作中，从而在不依赖人工奖励函数或大规模数据集的情况下训练强化学习智能体。
- **整体含义**：提出 **Ground-Compose-Reinforce (GCR)** 框架，将任务表示为 **奖励机（Reward Machines, RMs）**——一种基于自动机的规范语言，能够捕获任务的时序和逻辑结构。通过先学习原子命题符号的含义（基于少量数据），再组合这些符号来表达复杂任务，最后让智能体基于自生成的密集奖励通过强化学习学习策略。该框架在有限数据下展现出强大的组合泛化能力，为非数据密集型场景下的语言驱动智能体提供了可行路径。

## 2. 论文提出的方法论

- **核心思想**：利用奖励机的组合性，将底层原子命题的接地学习与高层任务的组合执行解耦。先通过监督学习在少量标注轨迹上学习每个原子命题的标签函数（labelling function），然后训练每种命题及其否定的**原始值函数（Primitive Value Functions, PVFs）**，最后通过组合这些PVFs来近似任意RM任务的最优值函数，并以此作为塑形奖励指导强化学习。
- **关键技术细节**：
  1. **预训练阶段**：
     - 学习标签函数 \(\hat{L}(s) \approx L^*(s)\)：对所有命题进行二分类监督学习。
     - 学习PVFs：\(V^*_{3x}(s)\) 和 \(V^*_{3\neg x}(s)\) 分别表示从状态s出发最优地满足命题x或¬x的期望折扣回报（到达目标得1分）。使用离线RL（如Fitted Q-Iteration）从预训练数据集D中学习。
  2. **行为诱导阶段（给定RM任务R）**：
     - 利用学习到的标签函数 \(\hat{L}\) 在线模拟RM的奖励和状态转移。
     - **组合奖励塑形**（核心贡献）：为了解决“命题稀疏性”问题（即某些命题在随机探索中极少满足），作者提出用组合方式近似最优值函数 \(V^*_R(s,u)\)。具体如下：
       - 对于RM中的每个转移 \(\langle u, u', \varphi, r \rangle\)，将其视为一个“选项”（option），选项的内在目标是满足逻辑公式 \(\varphi\)，其值函数由 \(V^*_{3\varphi}(s)\) 近似。
       - 逻辑公式进一步分解：\(\varphi\) 写成析取范式，取各子句的最大值；每个合取子句取各文字最小值的近似。
       - 最终只需学习 \(2|AP|\) 个PVFs（每个命题及其否定），即可近似任意公式的值函数。
       - 使用势能函数塑形：每个时间步的塑形奖励为 \(\lambda(\gamma v' - v)\)（实际实现中使用 \(\lambda(v' - v)\)，发现效果更好）。
  3. **强化学习**：使用PPO算法训练策略 \(\pi(a_t | s_t, u_t)\)，其中 \(u_t\) 是当前RM状态，由模拟的 \(\hat{L}\) 更新得到。
- **算法流程**（文本描述）：
  1. 预训练：在数据集D上训练 \(\hat{L}\) 和PVFs。
  2. 为当前RM任务R初始化策略。
  3. 每个episode：初始化环境状态s和RM状态u（初始状态）。
  4. 循环（直到u为终止状态）：
     - 采样动作a，执行，观察s'。
     - 计算 \(\hat{\omega} = \hat{L}(s')\)，更新RM得新状态u'和奖励r。
     - 使用PVFs估计当前值v'和v，计算塑形奖励。
     - 用PPO更新策略（基于塑形后的奖励）。

## 3. 实验设计

- **使用的场景（域）**：
  1. **GeoGrid**：8×8图像格世界，有6个随机放置的物体（红/绿/蓝，三角/圆）。状态为8×8×6图像，命题集{红,绿,蓝,三角,圆}。任务包括顺序、循环、逻辑约束、安全约束等4个RM任务。
  2. **DrawerWorld**：基于Meta-World的机器人操作环境，有2个抽屉和3个盒子（红、蓝、绿）。观察为78维向量（物体和夹爪位置）。命题包括抽屉打开、盒子被拿起、盒子在抽屉中。设计了3个任务：Hold-Red-Box（长时持有）、Pickup-Each-Box（顺序拿起三个盒子）、Show-Green-Box（揭示并拿起绿盒）。
- **数据集D**：
  - GeoGrid：5000条随机策略轨迹（每条100步）。
  - DrawerWorld：350条人工操控轨迹，每条涉及与至多一个盒子的直接交互，包含打开抽屉、拿取盒子、失败行为等。轨迹用手工标签函数标注了命题真值。
- **Benchmark & 对比方法**：
  - **GCR（ours）**：带组合奖励塑形的完整框架。
  - **GCR变体**：No RS（无塑形）、High-Level RS（仅基于RM状态塑形）。
  - **非组合方法**：
    - LTL-BC：将轨迹用LTL公式标注，训练行为克隆策略（条件于LTL）。
    - Bespoke Reward Model：在D上预训练一个网络同时预测所有下游任务的奖励、终止和最优值函数，再用RL训练策略（用学习到的值函数塑形）。
    - Bespoke BC：直接从D中成功的轨迹进行行为克隆（每个任务）。
- **评价指标**：每个方法运行5次，报告平均地面真相（ground-truth）折扣回报±标准误差。GeoGrid评估100个episode，DrawerWorld评估20个episode。还报告了学习曲线（自己的奖励模型 vs 地面真相）。

## 4. 资源与算力

- **监督训练**（预训练阶段）：使用单个GPU和CPU，内存≤24GB，每个方法训练不超过30分钟（100个epoch）。
- **RL训练**：每个RL实验使用：
  - 1个GPU，16个CPU核心，48GB RAM。
  - GeoGrid：训练至多15M帧，单次运行最长6小时。
  - DrawerWorld：训练至多20M帧，单次运行最长16小时。
- 文中未明确说明GPU型号或具体集群配置（可能为通用GPU）。
- 总计算量：每个方法5次重复×7个任务×两个域，加上不同变体，总计数百次RL运行。作者承认计算资源中等。

## 5. 实验数量与充分性

- **实验组数**：两个域，共7个RM任务（GeoGrid 4个，DrawerWorld 3个）。每个任务比较了5种方法（GCR全版本、No RS、High-Level RS、LTL-BC、Bespoke Reward Model、Bespoke BC——其中Bespoke BC只在DrawerWorld？文本显示GeoGrid也列出了BC，但与表格不完全一致？见表2包含GCR、LTL-BC、Bespoke Reward Model、Bespoke BC、No RS、High-Level RS，共6行。此外，GeoGrid还进行了自然语言自动形式化实验（GPT-4o和o3各5次尝试）。
- **充分性**：
  - 覆盖了不同复杂度（简单顺序到逻辑约束、安全约束、循环重复、长时持有）。
  - 包含了OOD任务（Pickup-Each-Box需要同时处理三个盒子，数据集中最高只与一个盒子互动）。
  - 消融实验：验证了组合塑形的必要性（No RS、High-Level RS对比）。
  - 每个条件5次独立随机种子，报告标准误，统计上合理。
  - 学习曲线显示了收敛情况和奖励对齐（图6、7）。
- **公平性**：基线方法同样使用D进行训练，且使用相同的时间步数进行RL（Bespoke Reward Model训练更长因为GRU）。奖励模型也都基于学习到的东西进行塑形。对比合理。

## 6. 论文的主要结论与发现

1. **GCR能够从有限数据中可靠地诱导出复杂行为**：在所有7个任务上，GCR（带组合塑形）都达到或接近最优回报，而所有非组合基线（LTL-BC、Bespoke Reward Model、Bespoke BC）几乎全部失败。
2. **组合泛化能力强**：GCR能在OOD任务（如Pickup-Each-Box，需要同时处理三个盒子）上成功，尽管预训练数据中从未出现过与多于一个盒子交互的轨迹。
3. **组合奖励塑形是长时域任务的关键**：在DrawerWorld中，无塑形（No RS）或仅基于RM状态塑形（High-Level RS）都无法学到任何有效策略，而组合塑形则使RL能够探索并成功完成任务。
4. **自然语言可自动形式化为RM**：GPT-4o和o3可以零样本将自然语言描述自动转化为RM（GeoGrid任务成功率大部分100%，除逻辑任务GPT-4o 0%但o3 100%），表明该框架可延伸到自然语言接口。
5. **非组合方法在有限数据下严重欠拟合或奖励误解**：Bespoke Reward Model在DrawerWorld中尽管学到高“自感知奖励”，但地面真相回报极差，表明其奖励模型严重错位。

## 7. 优点

- **数据高效性**：仅350条机器人轨迹（或5000条格世界随机轨迹）即可泛化到从未见过的行为组合，远低于传统数据驱动方法所需的大规模数据。
- **无需手动奖励函数或特征检测器**：整个流程完全自监督（预训练+RL），没有使用任何环境内部奖励或成功检测器。
- **组合性利用充分**：通过将复杂任务分解为原子命题的最优值函数，并进一步组合，实现了指数级任务空间的覆盖（\(2^{2^{|AP|}}\) 个逻辑任务和无穷RM任务）。
- **可解释性与可验证性**：任务以RM形式明确表示，便于审计和形式验证；并且可利用LLM从自然语言自动生成。
- **奖励塑形方法创新**：提出的基于PVFs的组合塑形有效解决了命题稀疏性，为长时间跨度任务中的探索提供了连续信号。
- **实验全面细致**：包括了多种域、多种任务类型、多个消融，并报告学习曲线和奖励对齐分析，显示出方法的鲁棒性。

## 8. 不足与局限

1. **依赖标注的命题标签**：预训练数据D需要轨迹自带每个时间步的命题真值标签（由手工标签函数提供）。在实际应用中，获取这种标签可能需要人工标注或自监督学习，文中未充分讨论标签噪声影响。
2. **组合近似误差**：组合塑形假设公式的合取/析取可用min/max近似，这可能导致低估或高估真实最优值，例如当两个文字互斥时，合取的min可能高估。作者承认这些误差。
3. **需要固定命题集AP**：框架要求所有任务都在相同的命题词汇上定义，无法像开放词汇的视觉-语言模型那样处理未见过的概念。
4. **自我循环转移的处理有局限**：对于带非零奖励的自循环转移（如每步扣分直到退出某个状态），文中给出的近似公式（式4）假设只有最大自循环奖励被累加，但在多个不同奖励的自循环同时存在时可能不精确。
5. **奖励破解风险**：如果学习到的标签函数 \(\hat{L}\) 与真实 \(L^*\) 误差较大，智能体可能利用标签错误进行奖励黑客。虽然RM规范本身明确，但命题接地的不确定性仍存在风险。
6. **实验覆盖有限**：仅测试了两个域（简单格世界和单臂机器人操作），未在更复杂的环境（如真实图像、多机器人、自然语言开放空间）验证。所有实验均为仿真环境。
7. **预训练数据收集方式**：GeoGrid用随机策略（低成本），但DrawerWorld需要人工操控收集（相对专业，可能难以大规模复制）。同时，数据中仅包括与至多一个盒子的交互，虽然故意限制以测试泛化，但实际场景中数据集可能无法如此精确控制。
8. **计算资源统计不详细**：未报告GPU型号和总计算预算（如GPU小时），不利于复现和比较能耗。

（完）
