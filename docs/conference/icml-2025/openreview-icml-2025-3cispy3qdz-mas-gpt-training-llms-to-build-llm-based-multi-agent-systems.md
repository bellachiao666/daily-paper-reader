---
title: "MAS-GPT: Training LLMs to Build LLM-based Multi-Agent Systems"
title_zh: MAS-GPT：训练LLM构建基于LLM的多智能体系统
authors: "Rui Ye, Shuo Tang, Rui Ge, Yaxin Du, Zhenfei Yin, Siheng Chen, Jing Shao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=3CiSpY3QdZ"
tags: ["query:agent-papers"]
score: 6.0
evidence: 训练LLM生成多智能体系统
tldr: 构建基于LLM的多智能体系统通常需要手动配置或多次调用高级LLM。本文将MAS构建视为生成任务，统一表示为可执行代码，并通过一致性数据管道训练MAS-GPT。该模型可根据用户查询直接生成相应MAS，降低了部署成本和计算开销，推动了多智能体系统的自动化构建。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-3cispy3qdz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 860, \"height\": 208, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3cispy3qdz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3cispy3qdz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1780, \"height\": 674, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3cispy3qdz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1710, \"height\": 471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3cispy3qdz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1716, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3cispy3qdz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1781, \"height\": 1055, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3cispy3qdz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1666, \"height\": 2324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3cispy3qdz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1668, \"height\": 561, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1766, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 132, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 758, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 859, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 133, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1743, \"height\": 1443, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1780, \"height\": 403, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1735, \"height\": 880, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1727, \"height\": 1765, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1227, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1585, \"height\": 1336, \"label\": \"Table\"}]"
motivation: 多智能体系统设计依赖手动配置或高级LLM多次调用，成本高且适应性差。
method: 将MAS构建视为生成任务，统一表示为代码，构建一致性数据对训练LLM。
result: MAS-GPT能根据查询直接生成多功能多智能体系统，降低推理成本。
conclusion: 生成式方法可有效简化多智能体系统的构建流程。
---

## Abstract
LLM-based multi-agent systems (MAS) have shown significant potential in tackling diverse tasks.
However, to design effective MAS, existing approaches heavily rely on manual configurations or multiple calls of advanced LLMs, resulting in inadaptability and high inference costs.
In this paper, we simplify the process of building an MAS by reframing it as a generative language task, where the input is a user query and the output is a corresponding MAS.
To address this novel task, we unify the representation of MAS as executable code and propose a consistency-oriented data construction pipeline to create a high-quality dataset comprising coherent and consistent query-MAS pairs.
Using this dataset, we train MAS-GPT, an open-source medium-sized LLM that is capable of generating query-adaptive MAS within a single LLM inference. The generated MAS can be seamlessly applied to process user queries and deliver high-quality responses. Extensive experiments on 9 benchmarks and 5 LLMs show that the proposed MAS-GPT consistently outperforms 10+ baseline MAS methods on diverse settings, indicating MAS-GPT's high effectiveness, efficiency and strong generalization ability.
The codes are released at \url{https://github.com/rui-ye/MAS-GPT}.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的基于LLM的多智能体系统（MAS）在构建时高度依赖人工手动配置或多次调用高级LLM（如GPT-4），导致两个主要缺陷：
  - **不适应性与高人力成本**：MAS的结构、角色和提示词通常是静态预定义的，无法针对具体查询自适应调整。
  - **高推理成本**：自适应MAS（如GPTSwarm、AFlow）需要多次LLM推理以及预先准备的验证集，计算开销大。
- **整体含义**：本文旨在将构建MAS的过程简化为一个生成式语言任务，使构建MAS像查询ChatGPT一样简单高效，从而降低部署门槛、促进MAS的大规模应用。

---

### 2. 论文提出的方法论

- **核心思想**：将用户查询作为输入，直接生成一个可执行的MAS（Python代码片段），从而实现“一次推理，自适应生成MAS”。
- **关键技术细节**：
  - **统一MAS表示**：将MAS表示为Python函数（forward函数），其中：
    - 每个Agent的提示词定义为变量。
    - LLM调用定义为函数调用。
    - Agent间交互通过字符串拼接（表示输入输出传递）实现。
  - **一致性导向的数据构建管道**（四步）：
    1. **构建查询池和MAS池**：从公开数据集收集多领域查询（数学、编程、通用问答）；实现并手动设计超过40种基础MAS候选（包括链式思考、角色扮演、专家辩论等）。
    2. **评估查询-MAS对**：对每个查询与每个MAS配对执行推理，根据结果正确性评分（1/0）。
    3. **间一致性导向的选择**：将相似查询聚类，为每类选出一个累计得分最高的MAS，确保相似查询映射到相同的高效MAS，便于模型学习泛化模式。
    4. **内一致性导向的精炼**：使用高级LLM（如GPT-4o）根据具体查询调整MAS内容（如修改Agent角色提示），并生成推理说明（解释为何该MAS适合该查询），然后验证精炼后MAS的性能是否不降，保留最优版本。
  - **训练**：使用上述高质量数据集对开源中规模LLM（Qwen2.5-Coder-32B-Instruct）进行监督微调（SFT），系统指令描述任务，指令为用户查询，响应为推理过程+可执行代码。
- **推理流程**：用户输入查询 → MAS-GPT一次推理生成MAS → MAS直接执行处理查询并输出答案。

---

### 3. 实验设计

- **数据集与基准**：
  - **训练数据**：来自MATH、GSM8K、MBPP、MMLU、SciQ的约1.1万对查询-MAS样本，覆盖数学、代码、通用问答。
  - **测试基准**（9个）：
    - 数学：MATH、GSM8K、GSM-Hard、AIME-2024
    - 代码：HumanEval、HumanEval+
    - 通用问答：MMLU
    - 科学：GPQA、SciBench（后两者为域外测试）
- **对比方法**：超过10种基线，包括：
  - 单Agent、CoT、Self-Consistency、LLM-Debate、Self-Refine、Quality-Diversity、SPP、AgentVerse、GPTSwarm、DyLAN，以及任务特定方法AFlow（在MATH上优化）。
- **MAS驱动LLM**：使用5种LLM（Llama-3-70B-Instruct、Qwen2.5-72B-Instruct、GPT-4o-mini、o1-preview、DeepSeek-R1）在相同设置下驱动所有MAS方法，保证公平对比。

---

### 4. 资源与算力

- 文中明确说明：训练MAS-GPT使用了**16块A100 GPU**，有效批次大小为32，训练3个epoch，学习率1e-5。未具体说明训练总时长，但称训练是一次性成本。
- 推理时：MAS-GPT仅需一次32B模型推理（约0.5次70B模型推理成本），而基线方法通常需要多次LLM调用。

---

### 5. 实验数量与充分性

- **实验组数**：非常充分。
  - 主实验：在8个基准上对比10+方法（表1）。
  - 不同MAS驱动LLM的泛化实验：3种驱动LLM（Qwen2.5-72B、GPT-4o-mini、Llama-3-70B），结果表3。
  - 与强推理模型o1-preview、DeepSeek-R1结合实验（图4a）。
  - 与任务特定方法AFlow的对比（图4b）。
  - 性能与推理成本的权衡分析（图4c）。
  - 消融实验（表4）：证明间一致性选择、内一致性精炼（调整MAS+推理过程）各自的有效性。
  - 数据规模缩放实验（图5a,b）。
  - 模型规模缩放实验（图5c）：7B、14B、32B。
  - 生成的MAS新颖性分析（表5）。
  - 案例研究（附录B）：展示生成MAS的定制性、泛化性、新颖性。
- **公平性**：所有基线使用相同驱动LLM，保持环境一致；训练和测试数据完全分离；域外测试确保泛化能力评估客观。
- **结论**：实验数量多、覆盖全面，充分验证了MAS-GPT的有效性、效率和泛化能力。

---

### 6. 论文的主要结论与发现

- MAS-GPT在9个基准上平均性能超越所有基线，尤其在不熟悉的域外任务上也表现优异。
- 相比固定MAS或多次调用优化，MAS-GPT仅需一次推理即可生成自适应MAS，大幅降低成本。
- MAS-GPT可进一步提升强推理LLM（如o1、DeepSeek-R1）的性能，在AIME-2024上分别提升13.3%和10.0%。
- 与任务特定方法AFlow相比，MAS-GPT在AFlow的域内任务（MATH）上反而更优，且无需验证集。
- 数据规模、模型规模均呈正向缩放趋势，表明该方法具有持续改进潜力。

---

### 7. 优点

- **方法创新**：将MAS构建重新框定为生成任务，统一以可执行代码表示，降低了手工设计门槛。
- **数据构造巧妙**：提出一致性导向的流水线，确保查询-MAS映射的间一致性和内一致性，有利于模型学习泛化模式。
- **实验全面**：覆盖多领域、多LLM、多基线，消融和分析详尽，证明各模块必要性。
- **实用性强**：推理成本极低（单次32B模型推理），且可即插即用，适合实际部署。
- **可扩展性**：展示了数据量和模型规模的正向缩放，且生成MAS具有新颖性（非记忆）。

---

### 8. 不足与局限

- **数据多样性限制**：初始MAS池仅40+种，训练集可能对高性能MAS有选择偏差，未能覆盖所有可能的 MAS 结构。
- **工具集成不足**：当前仅支持代码执行，未整合多模态处理、网络搜索等外部工具，限制了应对复杂任务的能力。
- **训练方法单一**：仅使用SFT，未探索强化学习（RL）自主探索和优化MAS的可能性，未来可提升自适应性。
- **未提供训练具体耗时**：虽给出GPU数量、配置，但未说明训练总时长，对成本预估不够透明。
- **潜在偏差**：训练集来自有限来源，可能偏向数学、编程和通用知识，其他领域（如医学、法律）未覆盖。
- **依赖外部LLM精炼数据**：内一致性精炼阶段依赖GPT-4o等高级模型，可能引入额外成本或偏差。

（完）
