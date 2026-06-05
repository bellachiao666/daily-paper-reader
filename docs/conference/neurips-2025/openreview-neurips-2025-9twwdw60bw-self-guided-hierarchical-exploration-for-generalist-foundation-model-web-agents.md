---
title: Self-Guided Hierarchical Exploration for Generalist Foundation Model Web Agents
title_zh: 面向通用基础模型网络智能体的自引导分层探索
authors: "Qianlan Yang, Xiangjun Wang, Danielle Perszyk, Yu-Xiong Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=9twwDW60Bw"
tags: ["query:agent-papers"]
score: 9.0
evidence: 面向自改进网络智能体的自引导分层探索
tldr: 该论文提出SAGE框架，通过自引导分层探索（包括预探索、顶层策略和底层技能）训练通用网络智能体，使其无需人工演示即可自主获取新技能。该方法直接支持智能体的自我改进能力，可作为递归自改进机制的基础，适用于复杂任务求解。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-9twwdw60bw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9twwdw60bw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1416, \"height\": 287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9twwdw60bw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 704, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9twwdw60bw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1459, \"height\": 598, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-9twwdw60bw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1455, \"height\": 755, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9twwdw60bw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 882, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9twwdw60bw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 808, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9twwdw60bw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 881, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9twwdw60bw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 880, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9twwdw60bw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 737, \"height\": 113, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9twwdw60bw/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 729, \"height\": 158, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9twwdw60bw/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 733, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9twwdw60bw/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 730, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9twwdw60bw/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 730, \"height\": 154, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9twwdw60bw/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 734, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9twwdw60bw/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 760, \"height\": 456, \"label\": \"Table\"}]"
motivation: 现有网络代理依赖预定义数据集和演示，限制了自改进能力。
method: 提出三分层探索策略，包括预探索、顶层策略和底层技能学习。
result: 在WebAgent基准上显著超越基线，展示出强大的自主技能获取能力。
conclusion: SAGE为实现自进化网络代理提供了可行框架。
---

## Abstract
Foundation models have recently shown strong potential as web agents, capable of interpreting high-level instructions and interacting with complex web interfaces. However, existing training paradigms for these agents often rely on predefined task datasets and curated demonstrations, limiting their scalability, adaptability, and capacity for self-improvement. In this work, we introduce *Self-guided hierArchical exploration for Generalist wEb agents* (SAGE), a new training framework designed to support autonomous skill acquisition through self-guided hierarchical exploration. Our method introduces a three-tier exploration strategy: a pre-exploration phase to build structural understanding of web environments, a top-level exploration strategy to generate a self-evolving curriculum of tasks from easy to hard, and a low-level exploration mechanism that combines planning-based rollouts with step-wise learning to improve policy efficiency. Together, these components form a scalable, supervision-free framework for web agent training. Experimental results on WebVoyager and WebArena demonstrate that our method significantly outperforms prior approaches, enabling foundation model agents to learn complex web tasks with greater generalization and robustness.

---

## 论文详细总结（自动生成）

好的，以下是根据您提供的论文内容生成的结构化、深入的总结。

### 面向通用基础模型网络智能体的自引导分层探索（SAGE）论文总结

---

#### 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的网络智能体（Web Agents）训练范式严重依赖预定义的任务数据集和专家演示。这导致了三个主要问题：
    1.  **成本高昂**：收集和标注数据非常昂贵且费时。
    2.  **泛化性差**：模型难以应对现实世界中数据分布之外的长尾复杂任务。
    3.  **缺乏自我提升能力**：模型无法通过与环境的自主交互来自我学习和改进，能力受限于训练数据。
- **研究背景**：基础模型（尤其是视觉语言模型 VLM）在理解高级指令和与网页界面交互方面展现了巨大潜力，为解决自动化网页任务（如订票、导航）提供了基础。然而，现有的训练方法未能有效利用模型的这种潜力来自主进化。
- **整体含义**：该研究旨在解决网络智能体**自主学习和自我进化**的关键瓶颈，提出一种无需人类标注、可扩展的通用训练框架，使智能体能够从零开始，通过自主探索获取并不断精进网页交互技能。

#### 2. 方法论：核心思想、关键技术细节

- **核心思想：自引导分层探索**。提出一个名为 **SAGE** 的训练框架，核心是“自我引导”的“分层”探索，模仿人类从易到难的学习过程，无需任何预定义任务或专家演示。
- **三层探索策略**：
    1.  **预探索阶段（Pre-Exploration）**：
        - 目的：在训练开始前，让智能体自主构建对目标网站结构的底层理解。
        - 方法：仅输入网站首页URL，智能体采用广度优先搜索（BFS）策略自主遍历网站。它会记录页面截图、页面间的结构转化关系（如“A页通过点击[搜索]按钮跳转到B页”）以及页面元数据。这些信息构成了任务生成所需的知识库。
    2.  **顶层探索策略（Top-Level Exploration，任务级课程学习）**：
        - 目的：动态生成和调整任务，形成一个从易到难的自进化课程。
        - 方法：包含一个**自适应任务生成器**和一个**双缓冲任务回放系统**。
            - **任务生成器**：基于预探索的知识库和历史执行轨迹的成功/失败模式，采用三种策略生成新任务：
                - **拓展**：从知识库中引入新的、未尝试过的任务。
                - **简化**：将成功率低的任务分解成更简单的子任务或放宽其约束条件。
                - **增强**：将成功率高的任务组合成更复杂的任务或增加条件。
            - **双缓冲系统**：一个缓冲区存储初始任务，另一个存储自适应生成的动态任务，用于维持基础技能和推动新技能学习的平衡。
    3.  **底层探索策略（Low-Level Exploration，动作级高效学习）**：
        - 目的：在单个任务内高效地探索最优动作序列，提高策略效率和样本利用率。
        - 方法：结合了**蒙特卡洛树搜索（MCTS）**、**多动作智能体策略**和**逐步学习（Step-DPO）**。
            - **MCTS规划**：在任务开始时，智能体不线性执行，而是用MCTS进行搜索。它通过上置信界算法（UCB）选择最有潜力的动作分支，从选定节点进行推出（Rollout），并根据成功/失败结果反向传播更新树节点价值，从而聚焦于高潜力轨迹。
            - **多动作策略**：智能体能同时输出多个候选动作及置信度，在MCTS中用于探索，在标准执行中选择置信度最高的动作。
            - **逐步学习（Step-DPO）**：将一条成功和一条失败的轨迹配对，找出它们分叉的决策点。策略学习的目标是**在分叉点之后，优先选择通向成功的动作序列**，从而实现细粒度的信用分配。
- **算法流程**：每一轮训练迭代，1) 顶层策略基于当前性能生成新任务；2) 底层策略（MCTS + 多动作策略）在采样任务上执行，收集轨迹；3) 使用Step-DPO基于收集的轨迹对策略进行更新。该过程循环进行，实现持续自我改进。

#### 3. 实验设计

- **使用数据集/场景**：两个主流的基于网页的基准测试：
    1.  **WebVoyager**：包含643个指令任务，覆盖15个真实网站（如Amazon, GitHub）。论文排除了两个因结构变化导致任务无法完成的网站，最终在13个网站上的557个任务进行评估。
    2.  **WebArena**：一个封闭的、内部服务器托管的基准测试，包含5个真实的网站环境（如Reddit, GitLab, 在线商店CMS）。论文使用了WebArena-Easy和WebArena-Lite的任务组合进行评估。
- **Benchmark**：任务完成成功率（Success Rate）。
- **对比方法**：
    - **专有模型**：Claude 3.5 Sonnet。
    - **开源模型基线**：
        - **SFT模型**：在PAE（Proposer-Agent-Evaluator）提出的任务上，基于Claude 3 Sonnet生成的轨迹进行微调的模型。
        - **PAE模型**：使用PAE框架训练的模型。
        - 使用了多种VLM作为基线，包括 **LLaVa-7B/34B** 和 **Qwen2.5VL-7B/32B**。
- **SAGE验证**：将SAGE训练框架应用于LLaVa和Qwen2.5VL系列模型，并与上述所有基线和原始模型进行对比。

#### 4. 资源与算力

- **文中明确提及的计算资源**：
    - 使用了**亚马逊云服务（AWS）**。
    - 通过ACCESS项目获得了**NCSA Delta 和 DeltaAI超算**的资源。
    - 通过NAIRR试点项目获得了**OpenAI API**的使用。
- ****重要：** 论文**未明确说明**所使用的**具体GPU型号、数量、训练时长或总计算量**。虽然提到了使用了AWS和超算资源，但没有提供可用于量化算力开销的详细数据。

#### 5. 实验数量与充分性

- **实验数量**：实验设计比较丰富，主要包括：
    - **主对比实验**：在两个基准（WebVoyager 和 WebArena）上，对比了SAGE与PAE以及多个基础模型（共18组条件组合）。
    - **难度分级实验**：在WebArena上按任务难度（易/中/难）进行了对比分析。
    - **消融实验**：对三个核心模块（预探索、顶层探索、底层探索）分别进行了消融研究。
    - **组件性能实验**：对训练后的评估器（Evaluator）的准确率进行了单独评估。
    - **错误分析**：对200个随机采样任务进行了人工标注和错误类型分布分析。
    - **其他附加实验**：评估器调优、样本效率对比、SFT基线对比。
- **充分性与公平性**：
    - **充分性**：实验覆盖了核心方法验证、模块贡献、模型规模和难度差异等多个维度，比较全面。
    - **公平性**：对比方法均为当前主流或SOTA的开源和专有模型，并复用了相似的环境设置（如PAE的标注截图），对比基线设置合理。在消融实验中，控制变量清晰，能有效证明各个组件的贡献。
    - **客观性**：使用成功率作为评价指标，并且进行了人工标注的错误分析，提供了更深层次的性能定性分析。

#### 6. 主要结论与发现

1.  **SAGE显著提升了性能**：在WebVoyager和WebArena两个基准上，SAGE在所有对比的模型上都**大幅超越**了PAE基线（例如，在WebArena上，Qwen2.5VL-32B SAGE的平均成功率达到39.7%，远超PAE的31.5%和Claude 3.5 Sonnet的35.6%）。
2.  **实现了自我进化的课程学习**：SAGE能有效自主构建从易到难的任务课程，使智能体先掌握简单执行技能，再攻克更复杂的推理任务（如错误分析所示：初期低层级错误迅速减少，后期高层级规划错误也显著下降）。
3.  **依赖于所有核心组件**：消融实验证明，**预探索、顶层策略和底层策略**三个模块都是不可或缺的，移除任何一个都会导致性能显著下降。
4.  **对复杂任务提升更大**：在困难任务（长程推理）上，SAGE相对于其他基线的性能提升最为显著（在WebArena的“困难”任务上，SAGE达到15.0%，而PAE只有9.0%）。
5.  **训练评估器是有效的**：使用小规模人类标注数据训练出的评估器（Qwen2.5VL-7B），其评估准确率（90%）甚至超过了专有模型（82%），为自监督学习提供了可靠信号。

#### 7. 优点

- **高度自主与无监督**：SAGE最大的亮点是**完全无需人工标注任务或专家演示**，智能体通过自我探索、自我评估和自我改进，实现了“从零开始学习”的范式。
- **结构化与可解释性**：它将复杂的学习过程分解为清晰的三个层次，每一步的作用和目的都很明确，不是简单的“黑箱”学习。例如，课程生成策略（简化/增强）非常直观易懂。
- **样本效率高**：MCTS结合Step-DPO的机制，避免了完全随机探索，能够更高效地收集有用轨迹并用于策略更新，从附录中的样本效率对比表（Table 10）可见一斑。
- **强大的泛化能力**：方法设计具有通用性，在多个不同的VLM模型（LLaVa, Qwen2.5VL）和大小（7B, 32B, 34B）上都展现出持续和稳定的性能提升。
- **严谨的实验和错误分析**：实验设计全面，包括了详细的消融实验和定性错误分析，有力地支持了论文的各项主张。

#### 8. 不足与局限

- **环境假设**：SAGE假设可以实现**可重置和可脚本化的浏览器环境**，这在面对现实开放网络（如需要验证码、登录和动态JavaScript的真实网站）时可能失效。这限制了其直接部署能力。
- **计算成本高**：虽然未明确给出，但大规模MCTS滚动和高质量网页渲染需要**大量的计算资源**，这可能导致复现门槛高。
- **特定环境增强**：该方法利用了网页的无障碍访问树（accessibility tree）和可恢复的环境状态——这些在标准化的基准测试中很容易获得，但在更加野生的、未结构化的网站上可能不能直接通用。
- **安全与隐私风险**：论文在受限的实验环境中进行，但将此类自探索智能体部署到真实网站可能带来**安全风险**（如访问敏感信息、执行危险操作）。作者也承认了这一点，并建议未来需要安全过滤器等防护措施。
- **依赖少数人工标注**：虽然大部分训练是无监督的，但**评估器（Evaluator）的最终调优依赖于少量（约400个）的人工标注数据**。这虽然极少量，但理论上仍引入了少量人工监督。

---

（完）
