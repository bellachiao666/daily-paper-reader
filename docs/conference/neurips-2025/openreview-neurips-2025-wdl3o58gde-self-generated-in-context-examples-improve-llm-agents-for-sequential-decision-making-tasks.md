---
title: Self-Generated In-Context Examples Improve LLM Agents for Sequential Decision-Making Tasks
title_zh: 自我生成的上下文内示例改进用于序列决策任务的LLM智能体
authors: "Vishnu Sarukkai, Zhiqiang Xie, Kayvon Fatahalian"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=WdL3O58gde"
tags: ["query:agent-papers"]
score: 9.0
evidence: 自我生成的轨迹改进LLM智能体无需人工干预，是清晰的自改进机制
tldr: "该论文研究LLM智能体如何通过自身成功经验自动改进。方法构建并精炼一个自生成轨迹数据库，作为未来任务的上下文示例。在ALFWorld、Wordcraft和InterCode-SQL三个基准上，即使简单累积成功轨迹也能将成功率分别从73%提升至89%、55%提升至64%、75%提升至79%，提升超过传统微调方法。这项工作展示了无需人工干预的自改进机制，为递归自改进智能体提供了直接思路。"
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-wdl3o58gde/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 515, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wdl3o58gde/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wdl3o58gde/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1439, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wdl3o58gde/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wdl3o58gde/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 931, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wdl3o58gde/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 924, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wdl3o58gde/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 465, \"height\": 451, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1453, \"height\": 667, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1321, \"height\": 796, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1453, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1171, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1453, \"height\": 977, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1275, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1565, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1170, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1181, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1315, \"height\": 409, \"label\": \"Table\"}]"
motivation: LLM智能体在序列决策中需要大量任务特定工程，缺乏自动改进能力。
method: 构造并精炼自生成轨迹数据库，用于未来任务作为上下文示例，实现免人工干预的自改进。
result: 在三个基准上成功率显著提升，且改进幅度超过有监督微调。
conclusion: 利用自身成功经验是有效的自改进策略，无需外部知识工程。
---

## Abstract
Improving Large Language Model (LLM) agents for sequential decision-making tasks typically requires extensive task-specific knowledge engineering—custom prompts, curated examples, and specialized observation/action spaces. We investigate a different approach where agents automatically improve by learning from their own successful experiences without human intervention. Our method constructs and refines a database of self-generated trajectories that serve as in-context examples for future tasks. Even naive accumulation of successful trajectories yields substantial performance gains across three diverse benchmarks: ALFWorld (73\% to 89\%), Wordcraft (55\% to 64\%), and InterCode-SQL (75\% to 79\%). These improvements exceed those achieved by upgrading from gpt-4o-mini to gpt-4o and match the performance of allowing multiple attempts per task. We further enhance this approach with two innovations: database-level curation using population-based training to propagate high-performing example collections, and exemplar-level curation that selectively retains trajectories based on their empirical utility as in-context examples. With these enhancements, our method achieves 93\% success on ALFWorld—surpassing approaches that use more powerful LLMs and hand-crafted components. Our trajectory bootstrapping technique demonstrates that agents can autonomously improve through experience, offering a scalable alternative to labor-intensive knowledge engineering.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究动机**：当前提升LLM智能体在序列决策任务中的性能，通常依赖大量任务特定的知识工程（如自定义提示、人工构造的上下文示例、专门的观察/动作空间），这些方法需要大量人工投入，且难以规模化。
- **核心问题**：能否让LLM智能体通过利用自身成功的经验，在无需人工干预的情况下自动改进自身性能？即通过自举（bootstrapping）成功轨迹来构建和精炼上下文示例数据库，从而实现持续自我提升。
- **整体含义**：本文证明了“自我生成的上下文示例”是一种可行的、可扩展的替代方案，能够替代劳动密集型的知识工程，为LLM智能体的自动化改进提供了新的维度。

### 2. 论文提出的方法论

- **核心思想**：采用ReAct风格智能体，在每一步通过检索机制从数据库中选取最相关的轨迹片段作为上下文示例。聚焦于如何构建和精炼这个轨迹数据库，使其包含的高质量示例能提升未来任务的表现。
- **关键技术细节**：
  - **Traj-Bootstrap（简单自举）**：从少量人工提供的初始轨迹开始，让智能体在训练任务上运行，仅将成功完成的轨迹（奖励为1）添加到数据库中，形成正面反馈循环。
  - **+DB-Curation（数据库级筛选）**：受种群训练启发，维护多个数据库实例并行收集轨迹，定期根据近期成功率评估每个数据库的性能，用表现最好的数据库替换最差的，以识别和传播整体性能优越的数据库。
  - **+Exemplar-Curation（示例级筛选）**：针对每个训练任务，从所有数据库实例的成功轨迹中选取“最有价值”的轨迹，价值通过**检索加权质量指标** \( Q(\tau) \) 衡量：
    \[
    Q(\tau) = \frac{\sum_{i \in R(\tau)} o_i \cdot f_i(\tau)}{\sum_{i \in R(\tau)} f_i(\tau)}
    \]
    其中 \( R(\tau) \) 是轨迹τ被检索的任务集合，\( o_i \) 是任务i的成功与否，\( f_i(\tau) \) 是检索频率。该指标衡量轨迹作为上下文示例时的贡献度。
- **算法流程**：
  - ReAct智能体循环（Algorithm 1）：包括规划（LLM_plan）、推理（LLM_reason）和动作（LLM_act）三步，每一步检索不同的轨迹片段。
  - 数据库筛选（Algorithm 2）：在训练过程中定期评估多个数据库实例的滚动性能，淘汰最差的，复制最好的。
  - 示例筛选（Algorithm 3）：对每个训练任务，在所有数据库中收集成功轨迹，按 \( Q \) 值选出最佳示例，构建复合数据库。

### 3. 实验设计

- **数据集/Benchmark**：
  - **ALFWorld**：文本环境，导航和物体操作任务，3500个训练任务，134个测试任务（6类子任务）。
  - **InterCode-SQL**：SQL查询生成任务，800个训练任务，234个测试任务。
  - **Wordcraft**：组合推理任务（类似Little Alchemy），4000个训练任务，500个测试任务。
- **对比方法**：
  - **基线**：Fixed-DB（固定初始人工示例，不增长）。
  - **本文方法**：Traj-Bootstrap，+DB-Curation，+Exemplar-Curation，组合方法（+DB+Exemplar-Curation）。
  - **外部对比**：Autoguide（层次化规则学习），AutoManual（使用手工设计的观察/动作空间），以及测试时采样（pass@k）、模型升级（从gpt-4o-mini到gpt-4o）等。
- **评价指标**：任务成功率（平均成功率及标准差，5次随机种子）。

### 4. 资源与算力

- 论文在附录M中说明了计算资源：
  - 1块NVIDIA A5000 GPU（24GB显存）用于嵌入计算。
  - 64GB RAM。
  - 主要计算开销来自OpenAI API调用，总API费用约3000美元（其中ALFWorld调用约200万次，InterCode-SQL约20万次，Wordcraft约50万次）。
  - 数据库操作（嵌入、存储、检索）占比<5%的计算时间。
- 注意：未明确写出训练时长（小时数），但提供了详细的token使用和成本分析（附录D），例如ALFWorld训练数据库构建最坏成本约595美元。

### 5. 实验数量与充分性

- **实验数量**：每组实验均报告5次独立随机种子的平均值和标准差，涵盖三个不同任务域的基准测试。消融实验包括：
  - Traj-Bootstrap vs. Fixed-DB。
  - +DB-Curation和+Exemplar-Curation的单独和组合效果。
  - 不同数据库大小下的性能趋势。
  - 与测试时采样、模型升级、层次化方法、手工方法等多维度对比。
  - 跨模型泛化实验（Mixtral 8x7B使用GPT-4o-mini收集的数据库）。
  - 微调实验（ReAct-Finetune）。
  - 初始示例消融（-Human_Examples）。
  - 预测任务成功率的实验。
- **充分性与公平性**：
  - 实验覆盖多个领域（导航、代码、组合推理），基准选择具有代表性。
  - 对比方法均源自已发表工作，且对自身方法的变体进行了系统比较。
  - 虽然部分外部对比的LLM不同，但作者明确指出了差异并提供了额外的上下文解释（如ALFWorld手工方法的额外设计）。整体上实验设计较为充分、客观。

### 6. 论文的主要结论与发现

- **简单自举即可显著提升**：即使仅累积成功轨迹（Traj-Bootstrap），在ALFWorld上成功率从73%提升到89%，Wordcraft从55%到64%，InterCode-SQL从75%到79%。
- **筛选进一步改进**：结合数据库级和示例级筛选（+DB+Exemplar-Curation），在ALFWorld上达到93%，超过了使用更强大LLM和手工组件的AutoManual（91%）。
- **改进幅度超过模型升级**：在ALFWorld上，从gpt-4o-mini升级到gpt-4o只用15个百分点的提升（73%→88%），而本文方法提升了20个百分点（73%→93%）。
- **与测试时采样相当**：自举方法仅用一次尝试就能达到基线方法pass@2或pass@3的水平。
- **跨模型泛化**：使用GPT-4o-mini收集的数据库能有效提升Mixtral 8x7B的性能（ALFWorld从0.27到0.55）。
- **可结合微调**：收集的示例用于微调也能获得竞争力（ALFWorld 96%）。

### 7. 优点

- **自动化自改进**：无需人工提示工程、无需手动选择示例，智能体能自主从成功经验中学习。
- **灵活性**：方法与具体LLM无关，可跨模型迁移；且与多种增强技术（如微调）兼容。
- **成本效益**：一次性训练成本后，测试时推理成本与基线相同；长期运行可大幅节省开销（附录D详细分析）。
- **可诊断性**：收集的示例可用于预测新任务的成功率，提供有价值的诊断能力。
- **系统性**：提出了数据库级和示例级两种互补的筛选策略，系统性地提升了数据库质量。

### 8. 不足与局限

- **依赖初始人工示例**：虽然可以从空数据库开始，但实验表明性能明显更差，说明少量人工示例对启动至关重要。
- **非单调提升**：成功率随数据库增长并非严格单调上升，存在波动，尤其是早期数据库较小时。
- **失败轨迹未直接利用**：仅筛选成功轨迹；失败轨迹虽有用于示例筛选中的价值评估，但未作为上下文示例直接使用，缺乏对失败原因的显式利用。
- **计算开销在训练侧**：+DB-Curation和+Exemplar-Curation需并行维护多个数据库实例，训练时LLM调用量是单数据库的N倍（N=5），但测试时无额外开销。
- **假设局限性**：假设POMDP设置、稀疏奖励、训练任务可访问等，可能不适用于所有现实场景（如无法提供验证信号的场景）。
- **未测试更复杂QA任务**：由于性能受检索器和自我评估能力混淆，未在HotPotQA等问答基准上测试，泛化性有待验证。

（完）
