---
title: Multi-Agent Collaboration via Evolving Orchestration
title_zh: 通过演化编排实现多智能体协作
authors: "Yufan Dang, Chen Qian, Xueheng Luo, Jingru Fan, Zihao Xie, Ruijie Shi, Weize Chen, Cheng Yang, Xiaoyin Che, Ye Tian, Xuantang Xiong, Lei Han, Zhiyuan Liu, Maosong Sun"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=L0xZPXT3le"
tags: ["query:agent-papers"]
score: 8.0
evidence: 通过强化学习实现多智能体协作的演化编排，支持灵活适应
tldr: 静态组织结构限制了多智能体系统的可扩展性和灵活性。本文提出一种提线木偶式范式，通过集中式编排器（puppeteer）利用强化学习学会根据动态任务状态自适应调度智能体（puppets）。实验证明该方法在处理复杂任务时比静态结构具有更高的效率和适应性，为多智能体协作中的自我进化提供了新机制。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1436, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 576, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 775, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1438, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 564, \"height\": 610, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 849, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1443, \"height\": 1768, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1424, \"height\": 1391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1445, \"height\": 1193, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1344, \"height\": 1090, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-l0xzpxt3le/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 755, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-l0xzpxt3le/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 674, \"height\": 630, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-l0xzpxt3le/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1125, \"height\": 259, \"label\": \"Table\"}]"
motivation: 静态多智能体结构在任务复杂度和智能体数量增加时产生协调负担。
method: 使用RL训练一个集中编排器，动态指导智能体协作。
result: 在需要多步协作的复杂任务上，该方法优于静态基线。
conclusion: 演化编排实现了灵活的多智能体协作，可视为一种系统级的自改进。
---

## Abstract
Large language models (LLMs) have achieved remarkable results across diverse downstream tasks, but their monolithic nature restricts scalability and efficiency in complex problem-solving. While recent research explores multi-agent collaboration among LLMs, most approaches rely on static organizational structures that struggle to adapt as task complexity and agent numbers grow, resulting in coordination overhead and inefficiencies. To this end, we propose a puppeteer-style paradigm for LLM-based multi-agent collaboration, where a centralized orchestrator ("puppeteer") dynamically directs agents ("puppets") in response to evolving task states. This orchestrator is trained via reinforcement learning to adaptively sequence and prioritize agents, enabling flexible and evolvable collective reasoning. Experiments on closed- and open-domain scenarios show that this method achieves superior performance with reduced computational costs. Analyses further reveal that the key improvements consistently stem from the emergence of more compact, cyclic reasoning structures under the orchestrator’s evolution. Our code is available at https://github.com/OpenBMB/ChatDev/tree/puppeteer.

---

## 论文详细总结（自动生成）

# 论文详细中文总结：Multi-Agent Collaboration via Evolving Orchestration

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：现有基于大语言模型（LLMs）的多智能体系统大多采用静态的、预先定义的组织结构（如链、树、固定图）。随着任务复杂度提升和智能体数量增加，这种静态结构会导致协调开销大、效率低下、冗余计算和性能下降。
- **研究动机**：受提线木偶表演的启发，作者提出一个集中式的、可学习的“木偶师”（Puppeteer）来动态编排多个“木偶”智能体。该编排器根据任务状态的演变自适应地选择和排序智能体，实现灵活且可演化的集体推理。
- **整体含义**：将多智能体协作建模为一种动态、可优化、图结构的推理过程（图-思维），通过强化学习持续提升协作性能与效率。

## 2. 论文提出的方法论

- **核心思想**：采用“提线木偶”范式，由中心化的编排器（Puppeteer，即策略网络）根据当前全局状态和任务描述，在每个推理步骤选择一个激活的智能体（Puppet）进行推理。智能体完成推理后更新系统状态，编排器再根据新状态选择下一个智能体，如此迭代直至满足终止条件。
- **关键技术细节**：
  - **动态编排（Dynamic Orchestration）**：将协作推理序列化为一个图遍历过程。每个智能体被抽象为 `a = (m, r, t)`，其中 `m` 是基础模型，`r` 是推理模式，`t` 是可用工具集。编排器 `π` 输出下一步要激活的智能体分布：
    - `a_t ∼ π(S_t, τ) = P(a | S_t, τ)`
    - 智能体输出 `o_t = f_{a_t}(s_t(a_t), S_t)`，状态更新 `S_{t+1} = Φ(S_t, o_t)`。
  - **自适应演化（Adaptive Evolution）**：基于REINFORCE算法优化策略参数 `θ`，目标是最大化完整推理轨迹 `τ` 的期望回报：
    - `J(θ) = E_{π_θ}[R(τ)]`
    - 策略梯度：`∇_θ J(θ) ≈ 1/N Σ_n Σ_t ∇_θ log π_θ(a_t|S_t) · R(τ)`
  - **奖励设计**：终端奖励 `r`（正确性/质量）与累积计算代价结合：
    - `R_t = r - λ·C_T`（终端），`R_t = γ·R_{t+1} - λ·C_t`（前期），其中 `C_t = F·log(1 + t/φ)`。
    - `λ` 控制准确率与效率的权衡，`γ` 为折扣因子。
  - **智能体组成**：包含多种推理模式（分解、反思、批判、修改、总结、终止等）和外部工具（网页搜索、维基搜索、代码解释器等）。

## 3. 实验设计

- **使用数据集**：
  - **闭域任务**：
    - **GSM-Hard**：含超大数的算术推理题，评估数学推理精度。
    - **MMLU-Pro**：多学科多选知识题，评估逻辑推理与事实知识。
  - **开域任务**：
    - **SRDD**：真实软件需求描述，要求构建软件，评估完整性、可执行性、一致性。
    - **CommonGen-Hard**：生成连接不相关概念的连贯句子，评估创造性、语法、相关性。
- **Benchmark与对比方法**：
  - **纯模型基线**：LLaMA-3.1-8B/405B、GPT-4o-mini、GPT-4-Turbo 等。
  - **单智能体方法**：Self-refine（迭代自修正）、AFlow（蒙特卡洛树搜索优化工作流）。
  - **多智能体方法**：MacNet（静态DAG图结构）、EvoAgent（进化算法自动生成多智能体系统）。
  - **Ablations**：Mono设置（所有智能体同模型）、Default（异质智能体）；初始阶段 vs 演化阶段。
- **实验设置**：
  - 在两个子空间进行：**Titan**（大模型：GPT-4-Turbo、LLaMA-3.1-405B等）、**Mimas**（小模型：LLaMA-3.1-8B、Qwen-2.5-7B等）。
  - 默认参数：episode length = 4, parallel exploration = 3, λ = 0.1, γ = 0.99。

## 4. 资源与算力

- 文中附录C明确给出了算力信息：使用 **8 张 NVIDIA A800 GPU**，峰值显存占用 **28.8–78.4 GB/GPU**，训练时间为 **2–6 小时**（因数据集和任务复杂度而异）。
- 注意：训练时间包含在线强化学习中与多智能体推理交错的参数更新，难以完全分解；且与某些基线（如AFlow使用推理时搜索）资源模态不同，不宜直接比较。

## 5. 实验数量与充分性

- **主要实验**：表1展示了在4个数据集×2个子空间（Mimas/Titan）×多种基线下的性能对比，主表结果覆盖几十个条件。
- **额外分析**：
  - Token消耗与智能体数量演化曲线（图2、图3、图8）。
  - 拓扑结构分析：图密度分布、循环分布（图6）。
  - 超参数影响（图7）：探索宽度/深度对性能与开销的非单调关系。
  - 性能-成本权衡曲线（图9）。
  - 行为模式可视化（图10）：展示多种涌现模式（链、反思、多智能体通信、复杂拓扑）。
  - 泛化到具身环境（ALFWorld）的案例（图11）。
- **充分性评价**：实验覆盖了闭域和开域任务、大小模型规模、多种强基线、消融（Mono vs. Default、演化前后），并提供了统计显著性标记（†）。总体设计较全面、客观、公平。但附录D指出探索样本数仅200，可能限制复杂任务上的充分优化。

## 6. 论文的主要结论与发现

- **性能提升**：Puppeteer（演化后）在所有任务上平均性能超越所有基线，且无论是在Titan还是Mimas子空间均取得最优或次优。
- **效率提升**：Token消耗随训练持续下降（图2），证明性能提升不以额外计算为代价；奖励设计中λ控制效率权重，系统学会提前终止或选用低成本智能体。
- **拓扑结构演化**：
  - **压缩**：图密度增加，智能体连接更紧密，形成高交互子网络（图6a）。
  - **循环性**：循环次数增多（反馈、递归批判与精炼），形成闭环推理结构（图6b）。
  - 演化导致更紧凑、循环的推理图，是性能提升的核心来源。
- **超参数影响**：深度/宽度过大导致冗余和性能下降，存在最优权衡（图7）。
- **泛化能力**：在ALFWorld具身任务上成功应用，展示了框架可扩展至交互环境。

## 7. 优点

- **方法创新**：提出动态编排+RL驱动的演化范式，突破静态多智能体系统的限制，实现自适应协作。
- **奖励设计巧妙**：联合优化准确率与Token效率，使系统自然地压缩推理路径。
- **实验全面**：覆盖闭域、开域任务，多规模模型，多种基线，并深入分析拓扑结构演化。
- **可视化丰富**：通过图密度、循环分布、行为模式等分析，增强了可解释性。
- **开源代码**：提供完整代码仓库，便于复现和扩展。
- **泛化性强**：在具身环境（ALFWorld）得到验证，说明框架可适应不同交互类型任务。

## 8. 不足与局限

- **奖励粗糙**：仅依赖最终输出和Token量，缺乏中间步骤的细粒度监督（如子步骤正确性）。
- **静态智能体集合**：假设智能体与工具固定，无法在推理中动态添加或修改，限制灵活性与鲁棒性。
- **协调失误**：观察到偶尔的误协调或虚假一致（deceptive agreement），表明需要更强健的交互协议。
- **探索预算有限**：当前实验仅使用200个优化样本，在复杂任务或弱模型上可能未充分搜索高质量配置。
- **计算资源比较困难**：与基线（如AFlow使用推理搜索）资源消耗类型不同，直接比较成本不恰当。
- **缺乏更开放场景验证**：虽测试了开域任务，但更多复杂现实世界场景（如多轮对话、动态环境）有待进一步验证。

（完）
