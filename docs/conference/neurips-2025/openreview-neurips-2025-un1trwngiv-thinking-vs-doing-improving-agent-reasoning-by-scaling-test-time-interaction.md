---
title: "Thinking vs. Doing: Improving Agent Reasoning by  Scaling Test-Time Interaction"
title_zh: 思考与行动：通过扩展测试时交互改进智能体推理
authors: "Junhong Shen, Hao Bai, Lunjun Zhang, Yifei Zhou, Amrith Setlur, Shengbang Tong, Diego Caples, Nan Jiang, Tong Zhang, Ameet Talwalkar, Aviral Kumar"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=un1TRwNgiv"
tags: ["query:agent-papers"]
score: 7.0
evidence: 扩展测试时交互使智能体能探索和重规划，实现自改进
tldr: 现有测试时扩展通常只增加推理轨迹长度，但无法获取环境新信息。本文提出扩展测试时交互维度，允许智能体在单个rollout内进行探索、回溯和动态重规划。在web智能体任务中，基于提示的交互扩展已能提升成功率，进一步引入课程式训练框架TTI，显著提高了复杂Web任务的完成质量。该方法为智能体通过交互实现自改进提供了新视角。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-un1trwngiv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-un1trwngiv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 783, \"height\": 216, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-un1trwngiv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 618, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-un1trwngiv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1424, \"height\": 284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-un1trwngiv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1179, \"height\": 682, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-un1trwngiv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 406, \"height\": 276, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-un1trwngiv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 736, \"height\": 2002, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-un1trwngiv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 734, \"height\": 1947, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-un1trwngiv/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 735, \"height\": 1821, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-un1trwngiv/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 736, \"height\": 2124, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-un1trwngiv/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 736, \"height\": 2059, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-un1trwngiv/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 736, \"height\": 2046, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-un1trwngiv/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 735, \"height\": 1475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-un1trwngiv/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 735, \"height\": 1154, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-un1trwngiv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 305, \"height\": 114, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-un1trwngiv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 335, \"height\": 118, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-un1trwngiv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 465, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-un1trwngiv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1452, \"height\": 515, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-un1trwngiv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 381, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-un1trwngiv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 595, \"height\": 269, \"label\": \"Table\"}]"
motivation: 当前测试时扩展局限于增加推理长度，智能体无法从环境获取反馈以改进行为。
method: 提出TTI框架，通过增加智能体在测试时的交互步数，允许探索和回溯，并结合课程训练。
result: 在Web任务基准上，TTI相比静态推理策略大幅提升成功率。
conclusion: 测试时交互扩展是智能体性能和自改进的有效维度。
---

## Abstract
Test-time scaling in agentic tasks often relies on generating long reasoning traces ("think" more) before acting, but this does not allow agents to acquire new information from the environment or adapt behavior over time. In this work, we propose scaling test-time interaction, an untapped dimension for test-time scaling that increases the agent's interaction horizon to enable rich behaviors such as exploration, backtracking, and dynamic re-planning within a single rollout. To demonstrate the promise of this scaling dimension, we situate our study in the domain of web agents. We first show that even prompting-based interaction scaling can improve task success on web benchmarks non-trivially. Building on this, we introduce TTI, a curriculum-based online reinforcement learning (RL) approach that trains agents by adaptively adjusting their interaction lengths during rollout. Using a Gemma 3 12B model, TTI sets a new state-of-the-art among open-source agents trained on public data on WebVoyager and WebArena. Case studies further reveal that TTI enables agents to balance exploration and exploitation adaptively. Our results establish interaction scaling as a powerful, complementary axis to scaling per-action compute, offering new avenues for training robust and adaptive agents.

---

## 论文详细总结（自动生成）

当然，以下是对给定论文《Thinking vs. Doing: Improving Agent Reasoning by Scaling Test-Time Interaction》的详细中文总结。

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：当前大型语言模型（LLM）作为智能体（agent）时，多采用“先思考后行动”的范式——即在每个决策步生成更长的推理链（chain-of-thought），试图通过增加“思考”来提升性能。然而，这种范式在交互式任务（如网页导航）中存在根本性缺陷：智能体无法从环境中获取新信息，也无法根据环境反馈实时调整行为，因此在部分可观测（如页面信息不全）或非平稳（如价格波动）场景下表现不佳。
- **整体含义**：论文提出一种全新的测试时计算扩展维度——**交互步数扩展（scaling test-time interaction）**，即允许智能体在单个任务执行中采取更多的环境交互动作（如搜索、回退、重试），从而获取新信息并实现动态重规划。作者将此视为与“每步推理扩展”正交且互补的新轴，旨在让智能体从“被动反应”转向“主动探索与自适应”。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：通过增加智能体在测试时可采取的最大动作步数（horizon），使其能够在一次 rollout 内执行探索、回溯、信息采集等丰富行为，从而提升任务完成质量。为有效训练这种能力，论文提出了 **TTI（Test-Time Interaction）** 框架。
- **关键技术细节**：
  - **框架流程**：
    1. 使用在线过滤行为克隆（filtered BC，即 REINFORCE 的一种变体）作为基础学习算法，仅保留成功轨迹用于更新策略。
    2. **课程式训练（Curriculum Learning）**：不再使用固定 horizon，而是逐步增加允许的最大交互步数。设计了两种方案：
       - **加法课程**：`h_i = clip(h_min + i, h_max)`
       - **乘法课程**：`h_i = clip(h_min · i, h_max)` （实验表明乘法课程效果更好）
    3. 使用经验回放缓冲池，并对较新的轨迹赋予更高权重。
  - **环境设置**：以网页智能体（web agent）为实验域，采用离散动作空间（click, type, scroll, go back, search, stop），观测空间包括任务目标、URL、基于可访问性树（accessibility tree）的网页结构和带标注的截图。
  - **训练过程**：每个迭代采样512个任务进行在线 rollout，使用成功轨迹更新策略，最大 horizon 从10逐步增至30。
- **伪代码与公式**：论文给出了训练算法伪代码（Algorithm 1），优化目标为最大化成功轨迹的对数似然（公式1）。

### 3. 实验设计：数据集、基准（Benchmark）及对比方法

- **实验场景与基准**：
  - **WebVoyager**：包含427个任务，涵盖13个真实网站域（如Amazon、Apple、GitHub等），用于评估在真实网站上的泛化能力。
  - **WebArena**：包含812个任务，覆盖5个自托管网站域（Shopping, CMS, Reddit, GitLab, Map），使用其内置的确定性评估器。
- **对比方法**：
  - **零样本基线**：未微调的 Gemma 3 12B 模型（直接动作生成或带 CoT）。
  - **固定horizon训练**：使用固定最大步数 h=10 或 h=30 进行在线RL。
  - **其他测试时扩展方法**：预算强制（budget forcing）、每步最佳-of-n（best-of-n）、以及提示式“重新检查”（check-again）。
  - **外部比较**：封闭源模型（GPT-4, Claude, OpenAI CUA）、开源模型（UI-TARS、PAE、AgentTrek、ScribeAgent等）。TTI 被归类为“完全开源、使用公开合成数据训练”的模型。

### 4. 资源与算力

- **明确信息**：论文提到使用 **NVIDIA H100 GPUs** 进行训练，采用 DeepSpeed Zero 3 分布式训练框架，但没有给出具体的 GPU 数量或训练时长。
- **不明确信息**：论文未披露单次训练花费的 GPU 时数或总耗费算力，只提到“全 benchmark 只运行一次”以避免高计算成本。

### 5. 实验数量与充分性

- **实验数量**：论文包含多组实验，共覆盖约**6个不同方向的实验**：
  1. 提示式交互扩展的初步验证（WebArena 子集，62个任务，3次运行取平均）。
  2. 交互扩展 vs. 每步推理扩展的对比（按 token 预算分解）。
  3. 不同固定 horizon 训练的效果对比（h=5,10,20）。
  4. 不同课程策略对比（加法/乘法）。
  5. 在 WebVoyager 和 WebArena 上的全基准评估（每个基准一次运行，但论文承认未多次重复）。
  6. 消融研究：训练过程中的轨迹长度、GoBack/Bing 动作比率、每步 token 数的变化。
  7. 案例研究：分析成功行为和失败模式。
- **充分性与客观性**：
  - **优点**：对比了多种基线（包括零样本、固定 horizon、其他扩展方法），在多个标准基准上评估，并进行了细致的案例分析。
  - **不足**：
    - 全基准实验仅执行一次，未报告统计误差（如多次重复的标准差），这削弱了结果的可靠性。
    - 训练数据可能因使用在线采集而存在探索偏差（exploration bias），但论文未对此进行量化分析。
    - 对失败模式的讨论较为简短，缺少系统性分类或量化。

### 6. 论文的主要结论与发现

- **关键发现1**：在交互式任务中，扩展**交互步数**（x轴）比扩展**每步推理 token 数**（y轴）更有效，因为前者允许智能体从环境中获取新信息，而后者仅能重组已有信息。
- **关键发现2**：简单提示式交互扩展（如“重新检查”）虽能提升性能，但效果有限且可能引入错误；**必须通过训练（如 TTI）**才能让智能体有效利用额外交互步数。
- **关键发现3**：TTI 在 WebVoyager 上的成功率达到 **64.8%**，在 WebArena 上达到 **26.1%**，均为当时开源、公开数据模型中的最高分，显著优于零样本基线（WebVoyager: 55.8%；WebArena: 18.3%）和固定 horizon 训练。
- **关键发现4**：TTI 智能体能够根据任务难度自适应调整交互策略：在复杂任务中增加搜索和回溯，在简单任务中保持高效执行。训练过程中 GoBack 和搜索动作的增多与成功率提升正相关。

### 7. 优点：方法或实验设计上的亮点

- **创新性**：首次明确提出“交互步数扩展”作为测试时计算扩展的新维度，与传统的“每步推理扩展”正交，为智能体训练提供了新思路。
- **实用性**：仅使用开源模型（Gemma 3 12B）和自动生成的合成数据进行训练，实现了完全开源的自我改进（self-improvement）流程，具有较好的可复现性和公平性。
- **课程式训练设计**：通过逐步增加 horizon，有效避免了固定长 horizon 训练的样本效率低下和过探索问题，使模型能够平滑地学习从“开发”到“探索”的转变。
- **深入分析**：对训练过程中的关键指标（轨迹长度、回退/搜索动作比例、每步 token 数）进行了追踪分析，揭示了学习动态，增强了方法解释性。

### 8. 不足与局限

- **实验覆盖**：
  - 仅验证了 web 智能体场景，尚未推广至其他交互领域（如机器人、游戏）。
  - 全基准实验仅运行一次，缺乏多次重复的统计结果，无法评估稳定性或方差。
  - 未系统分析不同超参数（如课程步长、学习率）对最终性能的影响。
- **偏差风险**：
  - 训练数据由原始模型自动采集，可能存在探索偏差（例如倾向于使用搜索而非更精细的域内操作）。
  - 评估器（verifier）为提示式模型（Gemma 3 27B），尽管准确率达到 88.9%，但其偏差可能影响训练过程（错误地将成功标记为失败或反之）。
- **应用限制**：
  - 增加交互步数会显著提高推理阶段的 token 消耗和计算成本，论文未讨论如何在不牺牲性能的前提下优化效率。
  - 训练中依赖简单的行为克隆，缺乏更高级的 RL 算法（如 PPO、GRPO）或密集奖励信号的支持，可能限制了进一步性能提升。
- **其他**：论文承认部分域（如 GitLab、Amazon）TTI 表现不如固定短 horizon 基线，表明在某些强先验知识场景中，过多探索反而有害。
- **沟通清晰度**：附录提供了大量提示模板和代码参考，但主文对某些实验细节（如温度参数、vLLM 配置）的交代不够直观，需读者查阅附录。

（完）
