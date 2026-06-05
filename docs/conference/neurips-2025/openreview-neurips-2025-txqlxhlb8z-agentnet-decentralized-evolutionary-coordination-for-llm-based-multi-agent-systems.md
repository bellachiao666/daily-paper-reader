---
title: "AgentNet: Decentralized Evolutionary Coordination for LLM-based Multi-Agent Systems"
title_zh: AgentNet：基于大语言模型的多智能体系统的去中心化进化协调
authors: "Yingxuan Yang, Huacan Chai, Shuai Shao, Yuanyi Song, Siyuan Qi, Renting Rui, Weinan Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=tXqLxHlb8Z"
tags: ["query:agent-papers"]
score: 8.0
evidence: 去中心化进化协调框架使多智能体系统自主进化协作能力
tldr: 现有LLM多智能体系统大多依赖中心化协调，导致可扩展性瓶颈、单点故障和跨组织协作困难。本文提出AgentNet，一种基于检索增强生成（RAG）的去中心化框架，智能体在有向无环图（DAG）结构中自主进化能力和协作。每个智能体动态注册和发现能力，通过RAG实现知识共享。实验表明，AgentNet在复杂协作任务中显著优于中心化方法，并支持跨组织隐私保护协作，为构建自进化的多智能体系统提供了基础。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1365, \"height\": 643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 558, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 699, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1376, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 677, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1376, \"height\": 270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1436, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1352, \"height\": 326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 675, \"height\": 95, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 744, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1402, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1477, \"height\": 748, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-txqlxhlb8z/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1480, \"height\": 1055, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-txqlxhlb8z/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1284, \"height\": 156, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-txqlxhlb8z/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 741, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-txqlxhlb8z/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1402, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-txqlxhlb8z/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1402, \"height\": 1379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-txqlxhlb8z/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 825, \"label\": \"Table\"}]"
motivation: 中心化多智能体系统存在可扩展性差、单点故障和隐私问题，限制了跨组织协作。
method: 提出去中心化RAG框架，智能体在DAG中自主注册能力并动态协作。
result: AgentNet在多种复杂协作任务中优于中心化基线，且支持隐私保护的跨组织协作。
conclusion: 去中心化进化协调是实现可扩展、自演进多智能体系统的有效途径。
---

## Abstract
The rapid advancement of Large Language Models (LLMs) has catalyzed the development of multi-agent systems, where multiple LLM-based agents collaborate to solve complex tasks.   However, existing systems predominantly rely on centralized coordination, which introduces scalability bottlenecks, limits adaptability, and creates single points of failure.   Additionally, concerns over privacy and proprietary knowledge sharing hinder cross-organizational collaboration, leading to siloed expertise.   To address these challenges, we propose AgentNet, a decentralized, Retrieval-Augmented Generation (RAG)-based framework that enables LLM-based agents to autonomously evolve their capabilities and collaborate efficiently in a Directed Acyclic Graph (DAG)-structured network.   Unlike traditional multi-agent systems that depend on static role assignments or centralized control, AgentNet allows agents to specialize dynamically, adjust their connectivity, and route tasks without relying on predefined workflows.
AgentNet’s core design is built upon several key innovations: (1) Fully Decentralized Paradigm: Removing the central orchestrator, allowing agents to coordinate and specialize autonomously, fostering fault tolerance and emergent collective intelligence. (2) Dynamically Evolving Graph Topology: Real-time adaptation of agent connections based on task demands, ensuring scalability and resilience.
(3) Adaptive Learning for Expertise Refinement: A retrieval-based memory system that enables agents to continuously update and refine their specialized skills.
By eliminating centralized control, AgentNet enhances fault tolerance, promotes scalable specialization, and enables privacy-preserving collaboration across organizations.      Through decentralized coordination and minimal data exchange, agents can leverage diverse knowledge sources while safeguarding sensitive information.      Experimental results demonstrate that AgentNet outperforms traditional centralized multi-agent systems, significantly improving efficiency, adaptability, and scalability in dynamic environments, making it a promising foundation for next-generation autonomous, privacy-respecting multi-agent ecosystems.

---

## 论文详细总结（自动生成）

# 论文总结：AgentNet: Decentralized Evolutionary Coordination for LLM-based Multi-Agent Systems

## 1. 核心问题与研究动机
**问题**：现有的基于大语言模型（LLM）的多智能体系统（Multi-Agent Systems, MAS）大多依赖**中心化协调**（如静态工作流、固定角色分配或中央控制器），导致以下严重缺陷：
- **可扩展性瓶颈**：随着智能体数量增加，中心控制器成为性能瓶颈。
- **单点故障**：中心控制器一旦失效，整个系统崩溃。
- **适应性差**：无法实时响应任务需求变化或智能体性能波动。
- **跨组织协作困难**：隐私和专有知识保护问题导致数据孤岛，知识无法共享。

**动机**：迫切需要一种**去中心化、动态自适应**的多智能体框架，既能保持高可扩展性和容错性，又能保护隐私，使不同组织的智能体能够安全协作。

## 2. 方法论：核心思想与关键技术细节

### 核心思想
AgentNet 是一个**完全去中心化**的框架，智能体在**有向无环图（DAG）** 结构中自主进化、协作和任务路由。每个智能体包含两个核心模块：
- **路由器（Router）**：负责分析路由查询并做出任务分发决策（转发、拆分、执行）。
- **执行器（Executor）**：负责实际执行任务。

系统无需中央协调器，智能体通过**本地经验和RAG（检索增强生成）** 动态调整连接和分工。

### 关键技术细节

#### a) 去中心化网络拓扑
- 网络表示为图 \( G = (A, E) \)，其中 \( A \) 为智能体集合，\( E \) 为通信边。
- 维护权重矩阵 \( w^m \)，边权重根据任务执行成功度动态更新：  
  \[
  w^{m+1}(i,j) = \alpha \cdot w^m(i,j) + (1-\alpha) \cdot S(a_i^{m+1}, a_j^{m+1}, t_{m+1})
  \]
  其中 \( \alpha \) 为衰减因子，\( S \) 为成功度量。
- 定期剪枝权重低于阈值 \( \theta_w \) 的边，保持高效连接。

#### b) 自适应学习与专业化
- 每个智能体维护**两个记忆模块**（路由器记忆 \( M^{rou}_i \) 和执行器记忆 \( M^{exe}_i \)），存储自身参与的任务片段（观察、上下文、动作）。
- 新任务到来时，检索最相关的 \( k \) 个片段，通过语义嵌入相似度选择。
- 使用 ReAct（Reasoning+Acting）框架增强推理和行动。
- 记忆容量有限（\( C_{max} \)），自动剪枝不重要的轨迹，维持高质量经验池，促进自然专业化。

#### c) 动态任务分配
- 任务表示为 \( t = (o_t, c_t, p_t) \)，其中 \( o_t \) 为描述，\( c_t \) 为能力需求向量，\( p_t \) 为优先级。
- 初始入口智能体选择：通过能力向量匹配，选择与任务需求最相似的智能体。
- 智能体可执行三种操作：
  1. **Forward**：将任务原样转发给更合适的智能体。
  2. **Split**：拆分任务，执行自身擅长的子任务，其余路由给其他智能体。
  3. **Execute**：直接完成整个任务。
- 智能体的能力向量动态更新：\( c_i^{m+1} = \beta \cdot c_i^m + (1-\beta) \cdot \Delta c_i^{m+1} \)。

### 算法流程（伪代码描述）
1. 初始化智能体集合、边、能力向量、权重矩阵和记忆模块。
2. 对每个任务 \( t_{m+1} \)：
   - 分析任务需求，选择入口智能体。
   - 循环：当前智能体通过RAG检索经验，由路由器决定操作（Forward/Split/Execute），更新任务状态，直至任务完成。
   - 更新智能体间的权重矩阵并剪枝。
   - 更新参与智能体的能力向量和记忆模块。
3. 返回优化后的网络 \( G^* \)。

## 3. 实验设计

### 数据集/基准
- **MATH**：数学问题（7种类型，训练700题，测试140题）。
- **BBH (Big-Bench Hard)**：逻辑推理与问答（训练627题，测试100题）。
- **API-Bank**：工具增强的API调用任务（训练100题，测试100题）。

### 对比方法
- **单智能体基线**：Direct, Chain-of-Thought (CoT), ReAct, Synapse, Self-Consistency, Self-Refinement。
- **多智能体基线**：MetaGPT, AFLOW, GPTSwarm, MorphAgent。

### 评估指标
- MATH 和 BBH：准确率（Accuracy）。
- API-Bank：准确率。

## 4. 资源与算力
论文**未明确说明**使用的GPU型号、数量或训练时长。仅提及使用LLM API（如DeepSeek-V3, GPT-4o-mini, Qwen-turbo）进行推理，温度设为0.0，最大token数2048，top-p=1.0。未报告训练的计算成本。

## 5. 实验数量与充分性

### 实验组数
- **主实验**（表1）：在3个数据集上，使用3种LLM骨干（DeepSeek-V3, GPT-4o-mini, Qwen-turbo），对比5种单智能体和4种多智能体方法，共约27个配置。
- **异质性实验**（表2）：在BBH上测试4种异质性设置（完全同构、技能异构、LLM异构、两者异构），3智能体和5智能体两种情况。
- **消融实验**（表3、图5）：
  - 路由器决策消融：对比完全随机、随机操作、随机下一智能体、全局路由器。
  - 进化机制消融：对比无进化版本的AgentNet。
- **可扩展性分析**（图6）：不同智能体数（3/5/7/9）和执行器池上限（30/40）的组合。
- **案例分析**（图9、10）：ReAct与AgentNet在BBH上一个问题的轨迹对比。

### 充分性与公平性
- **充分**：覆盖了多个领域、多种基线、不同LLM骨干、不同规模，并包含多个消融实验来验证设计组件的重要性。
- **客观公平**：所有多智能体方法统一设置3个智能体；单智能体方法使用标准提示技术；参数设置（温度=0）确保可重复性。但未报告多次运行的标准差或置信区间，可能缺乏统计显著性验证。

## 6. 主要结论与发现
1. **性能优势**：AgentNet在MATH、BBH、API-Bank上均达到或超过所有基线，尤其在BBH上准确率最高（94% with DeepSeek-V3）。
2. **异构智能体的影响**：在小规模（3智能体）时，完全同构效果最好；在更大规模（5智能体）时，异构配置反而更好，说明多样化在足够大的团队中能促进互补协作。
3. **路由器的重要性**：随机化路由决策导致性能大幅下降，而AgentNet的自适应路由接近全局路由器的性能。
4. **进化机制的有效性**：移除进化（即不更新记忆和能力）后，MATH准确率从85.00%降至77.86%，API-Bank从32.00%降至23.00%，BBH从86%降至76%。
5. **可扩展性与鲁棒性**：增加智能体数和执行器池大小，性能稳定提升（训练准确率从80.38%提高到81.18%），显示良好可扩展性。

## 7. 优点（亮点）
- **完全去中心化**：无需中央控制器，消除了单点故障，增强了系统鲁棒性和容错性。
- **动态图拓扑**：边权重实时调整，智能体连接可自适应剪枝，优化通信效率。
- **自适应学习与专业化**：通过RAG和记忆管理，智能体自然形成专长，无需人工设计角色。
- **隐私保护**：每个智能体仅共享最少任务元数据，数据和知识本地存储，适合跨组织协作。
- **全面的实验验证**：在多个任务类型、多种LLM骨干、多种基线上进行对比，并设计了充分的消融实验。

## 8. 不足与局限
- **异构环境挑战**：论文承认在异构智能体（不同模型、能力）的环境下，路由和协作仍需进一步优化。
- **路由器探索机制不足**：当前路由器从有限候选集中选择，在数百甚至数千智能体的大规模网络中，如何高效识别最合适的智能体尚未解决。
- **缺乏统计显著性报告**：未提供多次运行的方差或置信区间，结果的可靠性可能受单次运行影响。
- **计算资源未报告**：未说明实验所需GPU算力与时间，不利于复现和成本评估。
- **任务类型覆盖有限**：虽然覆盖了数学、逻辑推理、API调用，但未涉及开放域对话、视觉任务或物理机器人控制等更复杂场景。
- **记忆管理可能存在偏差**：使用LLM进行轨迹质量评估和剪枝，可能引入主观偏差或遗忘重要知识。

（完）
