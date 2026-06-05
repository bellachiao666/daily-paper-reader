---
title: "MAGELLAN: Metacognitive predictions of learning progress guide autotelic LLM agents in large goal spaces"
title_zh: MAGELLAN：元认知学习进度预测引导自组织LLM智能体探索大型目标空间
authors: "Loris Gaven, Thomas Carta, Clément ROMAC, Cédric Colas, sylvain lamprier, Olivier Sigaud, Pierre-Yves Oudeyer"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=hRMAo5N66M"
tags: ["query:agent-papers"]
score: 7.0
evidence: 元认知智能体通过预测学习进展和自我改进，结合强化学习
tldr: 开放学习智能体需高效优先目标，但学习进度预测依赖大量采样或专家定义。本文提出MAGELLAN，一种元认知框架，使LLM智能体在线预测自身能力和学习进度，通过语义关系实现样本高效估计。结合强化学习训练，智能体在大型目标空间中自主探索，符合自进化递归智能体主题。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 830, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 841, \"height\": 597, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 694, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 860, \"height\": 666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 823, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 759, \"height\": 1173, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 832, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 783, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 810, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1724, \"height\": 1714, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1029, \"height\": 674, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1608, \"height\": 1184, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1070, \"height\": 862, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1071, \"height\": 862, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1074, \"height\": 864, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1689, \"height\": 861, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1764, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1772, \"height\": 906, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1421, \"height\": 1100, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1626, \"height\": 1200, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1708, \"height\": 1430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 575, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 575, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 571, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 573, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 577, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 842, \"height\": 1298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1718, \"height\": 1206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1389, \"height\": 604, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 679, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 884, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1669, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1594, \"height\": 714, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 713, \"height\": 665, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 524, \"height\": 490, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 410, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 444, \"height\": 315, \"label\": \"Table\"}]"
motivation: 开放学习智能体在大目标空间中优先目标困难，学习进度预测效率低。
method: 提出元认知框架，让LLM智能体在线学习预测能力和学习进度，利用语义关系。
result: 实现了样本高效的学习进度估计，在大型目标空间中有效指导自主探索。
conclusion: 元认知预测可有效实现智能体自组织学习与自我改进。
---

## Abstract
Open-ended learning agents must efficiently prioritize goals in vast possibility spaces, focusing on those that maximize learning progress (LP). When such autotelic exploration is achieved by LLM agents trained with online RL in high-dimensional and evolving goal spaces, a key challenge for LP prediction is modeling one’s own competence, a form of metacognitive monitoring. Traditional approaches either require extensive sampling or rely on brittle expert-defined goal groupings. We introduce MAGELLAN, a metacognitive framework that lets LLM agents learn to predict their competence and learning progress online. By capturing semantic relationships between goals, MAGELLAN enables sample-efficient LP estimation and dynamic adaptation to evolving goal spaces through generalization. In an interactive learning environment, we show that MAGELLAN improves LP prediction efficiency and goal prioritization, being the only method allowing the agent to fully master a large and evolving goal space. These results demonstrate how augmenting LLM agents with a metacognitive ability for LP predictions can effectively scale curriculum learning to open-ended goal spaces.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：开放学习智能体必须在大目标空间中高效地优先选择那些能最大化学习进度（Learning Progress, LP）的目标。当将自组织探索（autotelic exploration）与大型语言模型（LLM）智能体结合，并通过在线强化学习（RL）在高维、动态变化的目标空间中训练时，一个关键挑战是如何预测智能体自身的能力——即一种元认知监控能力。
- **背景**：传统方法要么需要大量采样（如定期评估所有目标的成功率），要么依赖脆弱的专家定义的目标分组（expert-defined groupings）。这些方法难以扩展到离散、结构化、自然语言描述的巨大目标空间，且无法有效利用目标间的语义关系来估计能力传递（competence transfer）。
- **意义**：本文提出一种元认知框架 MAGELLAN，赋予 LLM 智能体在线预测自身学习进度的能力，从而实现高效的自动课程学习，为开放场景下的智能体自主学习提供了新范式。

## 2. 方法论：核心思想、关键技术细节与算法流程
- **核心思想**：学习一个目标条件的能力估计器 \(C_{\theta_t}(g)\)，用来近似智能体在策略 \(\pi_t\) 下对目标 \(g\) 的成功概率 \(P_{\pi_t}(g)\)。通过利用 LLM 的语义表征，使得语义相似的目标在隐空间中靠近，从而实现样本高效的能力估计泛化。
- **关键技术细节**：
  - **能力估计器**：使用 LLM（如 Flan-T5 248M）的最后一层解码器输出的隐状态，连接一个单层 MLP（128 单元，Tanh 激活），输出估计的胜任度（competence）。训练时使用在线交互获得的 (目标, 结果) 对，通过二元交叉熵损失优化。
  - **缓冲机制**：
    - \(D_t\)：存储最近 \(M\) 次训练回合的 (目标, 结果) 对。
    - \(B_t\)：存储最近 \(N\) 次更新的能力估计器权重。
  - **绝对学习进度（ALP）估计**：\(\widehat{ALP}_{\pi_t}(g) = |C_{\theta_t}(g) - C_{\theta_{t-N}}(g)|\)，利用当前与过去权重的估计差值来衡量能力变化（包括进步和遗忘）。
  - **目标选择**：采用多臂赌博机方案，每个目标作为一支臂，其效用由 MAGELLAN 估计的 ALP 值决定。按与 ALP 成比例的概率采样目标，并加入退火 \(\epsilon\)-greedy 策略（\(\epsilon\) 从 1 衰减至 0.2）。
  - **独立训练**：策略和 MAGELLAN 的能力估计器使用不同的 LoRA 适配器，避免干扰。
- **算法流程（文字描述）**：
  1. 初始化策略网络和 MAGELLAN 的能力估计器（LLM + MLP）。
  2. 对于每个训练回合：
     a. 使用当前目标选择策略（基于 ALP 估计）采样一个目标 \(g\)。
     b. 智能体执行一系列动作生成轨迹，获得结果（成功/失败）。
     c. 将 (目标, 结果) 加入缓冲区 \(D_t\)。
     d. 使用在线 RL（SAC-GLAM）更新策略参数。
     e. 每隔固定步数，使用 \(D_t\) 中的数据更新能力估计器 \(C_{\theta}\)（仅更新 LoRA 和 MLP）。
     f. 将更新后的权重存入 \(B_t\)。
     g. 对于每个目标，利用 \(B_t\) 中的新旧权重计算 ALP，用于下一轮目标选择。
  3. 重复直到达到训练预算。

## 3. 实验设计：数据集/场景、Benchmark、对比方法
- **环境/场景**：
  - **Little-Zoo**：新设计的文本环境，基于 Playground 改造。包含隐藏类目标（家具、植物、草食动物、肉食动物），目标空间约 2000 万组合。80% 为不可行目标，其余按难度递增分布（抓取 16%、种植植物 3.2%、养草食动物 0.7%、养肉食动物 0.1%）。目标是评测常识驱动的泛化能力。
  - **OpenR1-Math-220k**：数学目标模拟场景（代数、几何、数论），用于验证 MAGELLAN 的泛化能力。
  - **BabyAI-Text**：额外的文本环境，包含五个难度递增的指令类别。
- **Baselines**：
  - **Eval-ALP**：每 N 轮评估所有目标，计算 ALP。
  - **EK-Eval-ALP**：利用专家定义分组评估每组平均能力。
  - **Online-ALP**：仅使用在线交互结果，为每个目标或分组维护一个缓冲，计算 ALP。
  - **EK-Online-ALP**：类似 Online-ALP，但使用专家分组。
  - **Uniform**：均匀随机采样目标。
- **评估指标**：成功概率（Success Rate, SR），即平均目标完成率。

## 4. 资源与算力
- 论文附录 C.4 明确说明：
  - 使用 4-bit 量化（QLoRA）优化 VRAM 占用。
  - 32 个 Little-Zoo 环境实例同步并行运行。
  - 2 个 LLM 实例（Flan-T5 250M），每个分布在 1 个 Nvidia H100 80GB GPU 上（数据并行），总计 2 个 H100 GPU。
  - 对于每次实验（8 个种子之一，50万训练回合）需要约 80 GPU 小时。

## 5. 实验数量与充分性
- **实验组数**：
  - **Q1**: 三种目标空间大小（25k, 50k, 100k），各 8 个种子，对比 Eval-ALP 误差与成本。
  - **Q2**: 四种方法（MAGELLAN, Online-ALP, EK-Online-ALP, Uniform）在 25k 目标空间上训练 500k 回合，8 个种子，每 5000 轮评估一次 SR。
  - **Q3**: 在训练集上训练后评估测试集（未见目标）的预测能力误差。
  - **Q4**: 10 个不同的替换时间点（每 50k 轮替换所有目标），每个时间点四种方法各 8 个种子训练 50k 轮。
  - **消融实验**：四种架构（A: 分离 LoRA, B: 共享 LoRA, C: 共享但仅策略梯度, D: 冻结 LLM）。不同 LLM 大小对比（Flan-T5-small/base, Qwen2.5-0.5B）。额外 BabyAI-Text 环境验证。
- **充分性**：实验设计覆盖了核心科学问题的四个子问题（Q1-Q4），采用标准随机种子、统计显著性检验（p-value < 8×10^{-4}），结果具有统计效力。对比方法全面，且控制了专家知识的使用，公平性较好。

## 6. 主要结论与发现
- MAGELLAN 能准确且样本高效地估计能力（Q1）：其估计误差与需要大量评估的 Eval-ALP 相当，但无需额外评估成本。
- 在无专家知识的情况下，MAGELLAN 是唯一能使 LLM 智能体完全掌握所有目标（包括最难类别）的方法（Q2）；其他非专家方法在困难类别上失败。
- MAGELLAN 能有效泛化到未见目标（Q3）：在测试集上的预测误差显著低于 Online-ALP，与使用专家分组的 EK-Online-ALP 相当。
- 当目标空间动态演变时，MAGELLAN 能快速适应（Q4），尤其在高学习进度场景下表现优于 baselines；而在零学习进度场景下，专家分组方法因能直接跳过不可能目标而略快。
- 隐空间分析显示 MAGELLAN 在训练后会自动根据目标类别和可行性进行聚类，与专家分组形成的高质量聚类高度一致。

## 7. 优点
- **免于专家知识**：MAGELLAN 自动学习目标间的语义关系，无需人工定义分组，更具通用性和扩展性。
- **样本高效**：仅需在线交互数据即可更新能力估计，无需额外评估（Eval-ALP 需要大量额外采样），大幅降低计算开销。
- **泛化能力强**：利用 LLM 的语义表征，能对未见目标和动态变化的目标空间快速做出合理估计。
- **动态适应**：能力估计随策略更新不断演化，支持遗忘和进步的跟踪，形成有效课程。
- **设计平衡**：分离策略和估计器 LoRA 避免干扰（消融实验验证），使用优先采样缓冲提高稳定性。
- **验证充分**：在多个场景（Little-Zoo, Math, BabyAI）和多种规模下验证了方法的鲁棒性。

## 8. 不足与局限
- **实验规模与场景局限**：所有实验均在受控的文本环境 (Little-Zoo) 和小规模 LLM (Flan-T5 250M) 上进行。未在真实世界机器人或大规模实际任务中验证，泛化性需进一步研究。
- **不可行目标处理**：虽然 MAGELLAN 能识别不可行目标，但初期仍会采样它们（导致效率低于专家分组方法）。论文未提出显式的不可行目标过滤机制。
- **困难类别估计误差较高**：对于最难类别（”养肉食动物”），MAGELLAN 的泛化估计误差较大（约 0.30），说明当策略尚未掌握该类时，语义聚类可能不够精确。
- **算法复杂性**：需要维护两个 LLM 实例（策略和估计器）及多个缓冲区，训练成本仍较高（80 GPU小时/种子），对于更大模型可能难以承受。
- **未涉及人类学习**：论文提及在教育技术中的应用潜力，但未进行任何人类实验，实际的人体元认知效果未知。
- **依赖 LLM 表征质量**：MAGELLAN 的性能高度依赖 LLM 初始的语义理解能力；若 LLM 本身对目标领域的语义理解不足，聚类和学习效果可能受限。

（完）
