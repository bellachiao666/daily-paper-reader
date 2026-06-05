---
title: "Lessons Learned: A Multi-Agent Framework for Code LLMs to Learn and Improve"
title_zh: 经验借鉴：用于代码大语言模型学习和改进的多智能体框架
authors: "Yuanzhe Liu, Ryan Deng, Tim Kaler, Xuhao Chen, Charles Leiserson, Yao Ma, Jie Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=pY65QWWFlm"
tags: ["query:agent-papers"]
score: 8.0
evidence: 多智能体框架，智能体通过分享经验来改进代码任务性能
tldr: 代码优化领域，不同大语言模型各有所长，但缺乏协同。论文提出基于教训的多智能体框架，让智能体互相传递成功与失败经验（教训），实现集体学习。实验表明该框架显著提升代码优化性能，验证了知识共享在混合智能体系统中的有效性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-py65qwwflm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 719, \"height\": 795, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-py65qwwflm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1433, \"height\": 617, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-py65qwwflm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 682, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-py65qwwflm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1429, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-py65qwwflm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 848, \"height\": 635, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-py65qwwflm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1412, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-py65qwwflm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 967, \"height\": 388, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-py65qwwflm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 965, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-py65qwwflm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 352, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-py65qwwflm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 633, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-py65qwwflm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1186, \"height\": 635, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-py65qwwflm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 695, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-py65qwwflm/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1402, \"height\": 615, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-py65qwwflm/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 833, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-py65qwwflm/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 993, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-py65qwwflm/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1031, \"height\": 575, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-py65qwwflm/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1232, \"height\": 130, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-py65qwwflm/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1452, \"height\": 219, \"label\": \"Table\"}]"
motivation: 不同代码LLM在不同优化类别上各有所长，单一模型无法全面领先。
method: 智能体在执行中产生“教训”并传递给其他智能体，形成合作学习循环。
result: 在代码优化基准上，多智能体团队通过教训共享取得优于单模型和简单集成的结果。
conclusion: 教训共享机制有效提升多LLM系统的协同能力。
---

## Abstract
Recent studies show that LLMs possess different skills and specialize in different tasks. In fact, we observe that their varied performance occur in several levels of granularity. For example, in the code optimization task, code LLMs excel at different optimization categories and no one dominates others. This observation prompts the question of how one leverages multiple LLM agents to solve a coding problem without knowing their complementary strengths a priori. We argue that a team of agents can learn from each other's successes and failures so as to improve their own performance. Thus, a lesson is the knowledge produced by an agent and passed on to other agents in the collective solution process. We propose a lesson-based collaboration framework, design the lesson solicitation--banking--selection mechanism, and demonstrate that a team of small LLMs with lessons learned can outperform a much larger LLM and other multi-LLM collaboration methods.

---

## 论文详细总结（自动生成）

好的，以下是基于您提供的论文内容生成的详细中文总结。

### 论文总结：Lessons Learned: A Multi-Agent Framework for Code LLMs to Learn and Improve

#### 1. 核心问题与整体含义

-   **研究动机**：在代码优化任务中，不同的大型语言模型（LLMs）展现出了不同的专业技能，没有一个模型能在所有问题上都表现最佳。研究者观察到，即使是性能最强的模型，在如“几何”、“直方图”等更细粒度的任务类别上，也可能被较小的模型超越。这引出一个核心问题：如何在不预知各个模型互补优势的情况下，利用多个LLM代理协作解决编码问题？
-   **整体含义**：本文提出了一种新颖的多代理协作框架——**LessonL**。该框架的核心思想是让多个代码LLM代理组成团队，通过相互学习彼此的成功经验和失败教训（文章称之为“Lessons”），来提升整个团队的整体问题解决能力。这种方法不仅超越了单一大型模型（如 GPT-4o），也优于其他现有的多代理协作方法，尤其在代码优化任务上表现突出。

#### 2. 方法论

-   **核心思想**：受课堂中同伴学习的启发，文章提出“教训”（Lesson）的概念。一个教训是代理在解决问题过程中产生的任何有助于其他代理更好解决问题的知识或信息（例如优化策略、常见陷阱、性能反馈）。多个代理通过迭代地产生、分享和利用教训，实现集体学习和性能提升。
-   **关键技术细节：教训的征求-存储-选择机制**

    1.  **教训征求（Lesson Solicitation）**：每个代理在生成解决方案后，会根据解决方案的运行结果（加速、减速、功能错误、语法错误等）被提示生成相应的教训。例如，提示代理解释为什么优化后的代码更快，或为什么会编译失败。
    2.  **教训存储（Lesson Banking）**：所有代理生成的教训都会被存入一个共享的“教训银行”（Lesson Bank）中。
    3.  **教训选择（Lesson Selection）**：在后续的迭代轮次中，为了管理提示长度和成本，系统会从银行中选择最有用的教训（最多`k`个）。选择策略结合了两个标准：
        -   **高加速效果（High-Speedup）**：优先选择那些在生成时带来高加速比的教训（约占一半）。
        -   **高语义相关性（High-Relevance）**：从剩余的教训中，选择与原始代码语义最相关的教训（约占一半）。使用CodeBERT等代码嵌入模型计算余弦相似度。
    -   **动态效果调整（Effectiveness Adjustment）**：一个教训的历史最佳加速比并不能完全代表其未来的实用性。因此，当一个教训被再次应用时，系统会动态调整其效果因子(`f`)。如果该教训帮助代理产生了比其原始速度更快的代码，其因子增加，反之则降低。后续选择时会使用调整后的 `speedup * factor` 进行排序，实现动态学习。
-   **算法流程**：
    1.  **初始化**：每个代理独立生成初始解决方案，并为自己的代码生成教训，所有教训存入银行。
    2.  **迭代循环**：对于每一轮`t`：
        a.  从银行中选择`k`个最有用的教训。
        b.  每个代理基于所选教训，尝试生成一个改进的代码版本。
        c.  每个代理为新生成的代码生成新的教训，并存入银行。
        d.  调整本轮被选中的`k`个教训的效果因子。
    3.  **返回**：在所有轮次结束后，返回性能最好的解决方案。

#### 3. 实验设计

-   **数据集/场景**：
    -   **代码优化任务**：**ParEval**（60个科学计算和并行计算问题，分串行和OpenMP模式）和 **PolyBench**（30个数值计算任务）。
    -   **代码生成任务**：**HumanEval**、**HumanEval+**、**MBPP** 和 **MBPP+**。
-   **评估基准（Baselines）**：文章将LessonL与四大类方法进行了全面比较：
    1.  **单代理标准提示**：Qwen14B、GPT-4o mini、GPT-4o。
    2.  **单代理推理模型**：DeepseekR1-14B、OpenAI o3。
    3.  **单代理推理/反思方法**：思维链 (CoT)、反思 (Reflexion)。
    4.  **多代理协作方法**：MapCoder（不同专业角色代理）、MoA（独立求解后聚合）。
-   **指标**：
    -   代码优化：**几何平均加速比**（对大异常值更鲁棒）、代码正确率、加速比 > 2x的比例。
    -   代码生成：**pass@1** 准确率。

#### 4. 资源与算力

-   **硬件配置**：
    -   对于代码优化实验（ParEval, PolyBench）：LLM部署在**Amazon EC2 g6e.12xlarge**实例上（通过vLLM），内置**4块 Nvidia L40S GPU（共192GB显存）**。代码正确性和加速比的评估在独立的**c5.4xlarge**实例上执行。
    -   对于代码生成实验（HumanEval, MBPP等）：实验在配备**8块 A6000 GPU**的服务器上进行。
-   **运行时长**：LessonL框架在ParEval基准上的一个完整运行耗时**数小时**。其他方法和基准的运行时间相似。
-   **总结**：文章明确说明了使用的GPU型号和数量，但未提供精确到分钟或小时的运行时长数据。

#### 5. 实验数量与充分性

-   **实验数量**：实验设计非常丰富和系统：
    -   **主要结果**：在两个代码优化基准（ParEval, PolyBench）的两种模式（串行， OpenMP）上，对比了所有基线方法。
    -   **代码生成**：在四个代码生成基准上进行了测试。
    -   **消融研究**：分析了教训选择策略的各个组件（仅选高速、仅选高相关、无调整、随机选、无教训）的影响。
    -   **轮次/层数影响**：比较了LessonL、Reflexion、MoA、MapCoder在不同轮次下的性能变化趋势。
    -   **代理数量影响**：测试了从1个代理增加到6个代理时性能的变化。
    -   **成本分析**：从货币成本和延迟（FLOPS）两个维度进行了深入的性能-成本权衡分析。
-   **充分性与公平性**：
    -   实验覆盖了方法的核心点和多个变体，对比的基线非常全面，包括最新的推理模型。
    -   消融实验证明了教训机制各个组件的必要性。
    -   每个实验点报告了三次运行的平均值和标准差，保证了统计上的可靠性。
    -   成本分析使用了公开或合理的估计，构建了“帕累托前沿”来分析性价比，视角非常新颖和客观。

#### 6. 主要结论与发现

1.  **LessonL框架在代码优化和代码生成任务上均达到或接近最优水平**，尤其是在代码优化方面，其性能显著超越了GPT-4o等大型模型和MapCoder、MoA等其他多代理方法。
2.  **一组小型LLM通过LessonL框架协作，可以在相似资源消耗下大幅超越一个更大的LLM** (GPT-4o)，展示了其极高的成本效益。
3.  **教训机制是实现性能提升的核心**。消融实验表明，移除教训或仅依靠子集选择机制都会导致性能下降。
4.  多轮迭代对LessonL和Reflexion有益，但对MoA和MapCoder可能并非如此，有时性能甚至会下降。
5.  **代理数量增加通常会提升性能**，但收益递减（从3个代理增加到6个，收益不大）。

#### 7. 优点

-   **方法创新性**：提出了“教训”这一新颖的概念，模拟了人类的同伴学习过程，使得多代理间的知识传递更加结构化、可解释且经济高效（教训比代码本身更简短）。
-   **实验严谨性**：设计并执行了极其全面的实验，包括多基准、多基线、详尽的消融研究和成本-性能分析。这极大地增强了结论的可信度和说服力。
-   **实用性**：证明了使用成本更低的小型LLM团队，通过协作可以达到或超越昂贵大型模型的效果，具有很高的实际应用价值。
-   **可解释性**：生成的“教训”为代码优化提供了清晰的解释，有助于开发者理解优化背后的原理，可以作为教学材料。

#### 8. 不足与局限

-   **应用范围**：目前该方法仅应用于**函数级**的代码片段，对于更复杂的**仓库级**任务（如 SWE-bench）尚未进行验证。
-   **延迟开销**：虽然总体资源消耗有竞争力，但教训的征求和多次迭代会带来**首次响应时间**的增加，可能影响用户体验。
-   **问题复杂性局限**：案例研究显示，对于某些非常复杂的问题（如计算前缀和的和），即使是协作的小模型也经常失败，表明该方法在面对超出模型能力的任务时效果有限，可能需要整合外部知识。
-   **实验环境的局限性**：虽然文章详细描述了硬件，但所有实验都基于特定的云环境和本地服务器，结果可能无法完全复现于其他软硬件环境。
-   **数据偏差**：使用的基准（ParEval, PolyBench等）主要集中于科学计算和基础编程，未能涵盖所有编程领域，其通用性有待进一步验证。

（完）
