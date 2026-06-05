---
title: "Divide and Conquer: Grounding LLMs as Efficient Decision-Making Agents via Offline Hierarchical Reinforcement Learning"
title_zh: 分而治之：通过离线分层强化学习将LLM落地为高效决策智能体
authors: "Zican Hu, Wei Liu, Xiaoye Qu, Xiangyu Yue, Chunlin Chen, Zhi Wang, Yu Cheng"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=pdNtji3ktF"
tags: ["query:agent-papers"]
score: 7.0
evidence: 通过分层离线强化学习实现LLM智能体自我改进
tldr: LLM在长程稀疏奖励任务中探索不足。本文提出GLIDER框架，通过离线分层强化学习引入层级策略，高层规划低层执行。实验表明，该方法显著提升了LLM在复杂决策任务中的表现。该工作展示了强化学习提升LLM智能体的有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-pdntji3ktf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 742, \"height\": 630, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pdntji3ktf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1747, \"height\": 776, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pdntji3ktf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 864, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pdntji3ktf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 866, \"height\": 339, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pdntji3ktf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 476, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-pdntji3ktf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1680, \"height\": 829, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pdntji3ktf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pdntji3ktf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 825, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pdntji3ktf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1418, \"height\": 1139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pdntji3ktf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1229, \"height\": 606, \"label\": \"Table\"}]"
motivation: LLM在长程稀疏奖励任务中表现不佳。
method: 提出GLIDER，采用分层RL，高层指导低层执行抽象计划。
result: 在多个复杂决策任务上性能优于基线。
conclusion: 分层离线RL可有效增强LLM决策能力。
---

## Abstract
While showing sophisticated reasoning abilities, large language models (LLMs) still struggle with long-horizon decision-making tasks due to deficient exploration and long-term credit assignment, especially in sparse-reward scenarios. Inspired by the divide-and-conquer principle, we propose an innovative framework **GLIDER** (**G**rounding **L**anguage Models as Eff**I**cient **D**ecision-Making Agents via Offline Hi**E**rarchical **R**einforcement Learning) that introduces a parameter-efficient and generally applicable hierarchy to LLM policies. We develop a scheme where the low-level controller is supervised with abstract, step-by-step plans that are learned and instructed by the high-level policy. This design decomposes complicated problems into a series of coherent chain-of-thought reasoning sub-tasks, providing flexible temporal abstraction to significantly enhance exploration and learning for long-horizon tasks. Furthermore, GLIDER facilitates fast online adaptation to non-stationary environments owing to the strong transferability of its task-agnostic low-level skills. Experiments on ScienceWorld and ALFWorld benchmarks show that GLIDER achieves consistent performance gains, along with enhanced generalization capabilities.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：大型语言模型（LLM）在长时域决策任务中表现不佳，主要受限于**探索不充分**和**长期信用分配困难**，尤其是在**稀疏奖励**场景下。尽管LLM具备强大的推理能力，但直接用于交互式决策时，基于提示的方法（如ReAct）容易超出上下文长度限制，监督微调方法依赖昂贵专家数据且缺乏环境探索，而强化学习方法面临样本效率低、动作空间大等问题。
- **整体含义**：受“分而治之”原则启发，论文提出**GLIDER**框架，通过**离线分层强化学习**为LLM策略引入高效且通用的层级结构，将复杂任务分解为高层规划（子任务）与低层执行（原子动作），从而显著提升长时域任务的探索效率和性能。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：构建一个**两层层次结构**：
  - **高层策略**（High-level policy, πₕ）：每c步生成一个**子目标**（subtask），将任务分解为一系列连贯的链式推理子任务。
  - **低层策略**（Low-level policy, πₗ）：根据当前子目标和观测生成**原子动作**，并接收高层提供的**内在奖励**（子任务是否完成的二元信号）。
  - 层次结构提供**时间抽象**（temporal abstraction），减少高层的决策频率，增强探索和长期信用分配。
- **关键技术细节**：
  - **参数高效模型架构**：高层和低层**共享同一个LLM backbone**（通过LoRA微调），仅通过**层级提示（hierarchy prompt）** 区分当前角色；critic通过附加MLP层实现。这避免了传统分层方法中独立模型的参数倍增问题。
  - **训练流程**（三阶段，如算法1所示）：
    1. **行为克隆（SFT）**：使用专家演示轨迹分别对高层（状态→子目标）和低层（子目标→动作）进行监督学习，并加入**长度正则化**（鼓励生成简洁输出）。损失函数：  
       \( \mathcal{L}_{SFT}(\theta) = -\mathbb{E}_{(d,o;g)\sim\mathcal{D}_h}[\log \pi_\theta^h(g|d,o)] + \lambda n_h - \mathbb{E}_{(g,o;a)\sim\mathcal{D}_l}[\log \pi_\theta^l(a|g,o)] + \lambda n_l \)
    2. **离线强化学习（ORL）**：使用奖励标注的数据（高/低水平经验回放缓冲）训练**token级演员**和**句子级评论家**。评论家包括Q函数和价值函数，使用**implicit Q-learning**（不对称损失，expectile τ∈[0.5,1)）保持保守估计；演员通过**优势加权最大似然**（类似AWAC）进行策略优化：  
       \( \mathcal{L}_\pi(\theta) = -\mathbb{E}_{(s,u)\sim\mathcal{D}} [\exp(\frac{1}{\lambda}(Q_\phi(s,u)-V_\psi(s))) \cdot \log \pi_\theta(u|s)] \)
    3. **离线到在线适应（O2O）**：可选阶段。固定任务无关的低层技能，仅使用环境奖励在线微调高层策略，实现快速适应非平稳环境。
- **算法流程**（文字描述）：首先通过SFT初始化策略；然后在ORL阶段交替更新评论家和演员（从缓冲采样）；最后（可选）在在线环境中冻结低层，更新高层。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集/场景**：
  - **ScienceWorld**：30个任务（涉及10个科学实验类别），**密集奖励**（0到1），评估在**已见**和**未见**任务上的性能。
  - **ALFWorld**：6类家庭操纵任务（如导航、物体操作），**稀疏二元奖励**（成功=1，否则0），同样包含已见和未见场景。
  - **离线数据集**：由专家演示（benchmark提供的最优轨迹）和中质量轨迹（通过分布内采样和跨任务泛化采样得到）按**1:2比例**混合构成，形成高层缓冲（\(\mathcal{D}_h\)）和低层缓冲（\(\mathcal{D}_l\)）。
- **对比方法**：
  - **基于提示**：ReAct、Reflexion、SwiftSage（均不更新模型参数）。
  - **微调方法**：NAT（从失败轨迹学习）、ETO（使用DPO的迭代优化）。
  - 所有方法均在**三个LLM backbone**上比较：Mistral-7B、Gemma-7B、Llama-3-8B（均使用LoRA）。
- **其他实验**：
  - 消融实验：层次 vs 无层次，SFT/ORL/SFT+ORL阶段，不同模型规模（Llama 1B/3B/8B）。
  - **数据混合比例**实验：从纯专家到纯medium共9种比例。
  - **在线微调泛化**实验：在ScienceWorld中，从三个领域（电气、生物、热力学）各选一个未见任务进行O2O评估，对比AC和AWAC。

## 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU 型号、数量、训练时长等）。若未明确说明，也请指出这一点。

- **未明确说明**：论文正文和附录中**没有透露**具体的GPU型号、数量或训练时长。虽然附录C给出了超参数（batch size=64，epoch数，学习率等），但未提及计算资源规格。这属于实验报告中常见的缺失细节。

## 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平

- **实验数量丰富**：
  - 主表（Table 1）：3个backbone × 2个benchmark × 2种场景（seen/unseen） = 12个主要性能对比项，每个对比5个基线 + GLIDER。
  - 消融实验（Figure 3, Table 2）：5种层次/训练阶段组合 × 3个backbone（Figure 3），以及3种模型规模（Table 2）。
  - 数据混合比例实验（Figure 5）：9种比例 × 2种模型（w/ Hier vs w/o Hier）。
  - 在线微调泛化实验（Figure 4）：3个新任务 × 3种方法（GLIDER、AWAC、AC），展示学习曲线。
- **充分性评估**：
  - **覆盖全面**：包括标准性能、消融、泛化、数据敏感性，实验设计较为系统。
  - **客观性和公平性**：所有方法使用相同backbone和LoRA设置；对比基线包括当时SOTA（如ETO）；SFT和ORL阶段超参数一致。但**未报告多次运行的标准差或统计显著性**（可能只运行一次或取最佳），这削弱了结果的稳健性证据。
  - **局限性**：未与最新的分层方法（如SayCan、InnerMonologue）直接对比；仅在两个文本环境上测试，未在更复杂或者真实环境（如机器人）中验证。

## 6. 论文的主要结论与发现

- **性能显著提升**：在ScienceWorld和ALFWorld上，GLIDER在所有backbone和场景下均大幅超过基线，尤其在**未见任务**上提升最高（+22.28% ~ +30.59%），表明强大的泛化能力。
- **层次结构是关键**：所有消融实验中，带层次结构的模型始终优于无层次版本，且组合SFT+ORL达到最佳。
- **离线到在线适应快**：在三个新任务上，GLIDER的零样本初始得分更高，且在线微调收敛更快、最终性能更好。
- **数据比例影响**：专家/medium数据比例在1:2时最优；纯专家数据性能反而不如仅使用medium数据，说明多样化的（包括失败）覆盖对RL训练有益。

## 7. 优点：方法或实验设计上有哪些亮点

- **方法优点**：
  - **参数高效**：高层和低层共享同一个LLM backbone（仅通过prompt区分），避免传统分层RL中独立模型的参数倍增。
  - **通用性广**：低层技能使用内在奖励（子任务完成信号），无需领域专家设计子任务结构；高层通过环境奖励自动学习分解。
  - **离线样本高效**：先在离线数据上通过SFT初始化+ORL精细调整，无需大量在线交互。
  - **O2O快速适应**：冻结任务无关的低层技能，只调整高层，实现零样本迁移和快速在线微调。
- **实验亮点**：
  - 多backbone验证（Gemma、Mistral、Llama），减少模型偏见。
  - 模型规模消融（1B/3B/8B），验证层次结构对小模型同样有效（3B层次模型甚至超过7B非层次模型）。
  - 考虑数据混合比例的影响，分析质量与多样性的权衡。

## 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **实验覆盖不足**：
  - 仅测试了两个文本环境（ScienceWorld和ALFWorld），未在**现实物理环境**或**更复杂的长时域任务**（如机器人操纵、网页导航）上验证。
  - 未与其他**分层LLM方法**（如SayCan、RT-2、Grounded Decoding）直接比较。
  - 未报告**多次运行的标准差或置信区间**，结果可靠性存疑。
- **偏差风险**：
  - 离线数据集中专家轨迹来自Benchmark本身，可能引入**数据分布偏差**（任务较规范）。
  - 中质量轨迹由SFT模型收集，可能引入**模型依赖的探索偏差**。
- **应用限制**：
  - 训练流程相对复杂（三阶段），在工程部署中可能不够轻量。
  - 低层技能依赖**内在奖励**（子任务完成信号），该信号需要从环境观测中自动判断（通过prompt判断），在某些环境中可能不直观或不可靠。
  - 层次结构引入超参数c（子任务步长），论文未深入讨论其影响。

（完）
