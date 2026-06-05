---
title: "SiriuS: Self-improving Multi-agent Systems via Bootstrapped Reasoning"
title_zh: SiriuS：基于自举推理的自改进多智能体系统
authors: "Wanjia Zhao, Mert Yuksekgonul, Shirley Wu, James Zou"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=IDSTtDw4Cs"
tags: ["query:agent-papers"]
score: 9.0
evidence: 自改进多智能体系统，通过自举推理构建经验库
tldr: 多智能体LLM系统依赖脆弱的手工提示，优化困难。论文提出SiriuS框架，通过保留成功推理轨迹构建“经验库”，并利用自举推理增强库中数据，实现系统自我改进。实验证明SiriuS能自动优化智能体行为，显著提升复杂任务求解成功率，是递归自改进智能体的重要实践。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1426, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 725, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 686, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 680, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 514, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 681, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 418, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 686, \"height\": 472, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1364, \"height\": 704, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 703, \"height\": 517, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 449, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1009, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1446, \"height\": 534, \"label\": \"Table\"}]"
motivation: 多智能体系统的手工提示和启发式脆弱，缺乏自动化优化。
method: 通过成功推理轨迹构建经验库，并利用自举推理扩展库，用于训练和优化智能体。
result: 在多种复杂任务上，SiriuS自动提升系统性能，超越手工提示方法。
conclusion: 自举推理和经验库是自改进多智能体系统的可行方向。
---

## Abstract
Multi-agent AI systems powered by large language models (LLMs) are increasingly applied to solve complex tasks. However, these systems often rely on fragile, manually designed prompts and heuristics, making optimization difficult. A key challenge in optimizing multi-agent systems is acquiring suitable training data for specialized agents. We introduce SiriuS, a self-improving, reasoning-driven optimization framework for multi-agent systems. Central to our approach is the construction of an experience library: a repository of high-quality reasoning trajectories. The library is built by retaining reasoning steps that lead to successful outcomes, providing a robust training set for optimizing multi-agent system. Additionally, we introduce a library augmentation procedure that refines unsuccessful trajectories, further enriching the library. SiriuS boosts performance by 2.86% to 21.88% on reasoning and biomedical QA and enhances agent negotiation in competitive settings. Our results show that SiriuS enhances multi-agent performance while generating reusable data for self-correction and self-play enhancement in the future.

---

## 论文详细总结（自动生成）

# SiriuS: Self-improving Multi-agent Systems via Bootstrapped Reasoning 论文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：多智能体大语言模型（LLM）系统在复杂任务中表现出色，但依赖脆弱的手工提示和启发式规则，优化极其困难。主要挑战在于：(1) 难以获取针对每个智能体的合适训练信号；(2) 系统对多个运动部件高度敏感，且任务级奖励难以在智能体间进行信用分配。
- **研究动机**：现有方法（如纯提示工程、TextGrad、DSPy等）优化效果有限或需要大量人工干预。作者希望利用自举推理（bootstrapped reasoning）思想，从成功的智能体交互轨迹中自动学习有效协作策略，避免对中间步骤的直接监督。
- **整体含义**：提出一个名为 **SiriuS** 的通用框架，通过构建“经验库”（experience library）——即保留导致成功结果的推理轨迹，并增强失败轨迹，使多智能体系统能够自我改进，无需精细的人工标注。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：当多个智能体成功协作解决任务时，它们的整个交互轨迹很可能包含有用的模式，即使无法准确定位哪些步骤关键。通过收集并学习这些成功交互，系统可以迭代发现有效的协作策略。同时，对失败轨迹进行增强（augmentation），通过引入外部智能体的反馈重新生成正确轨迹，丰富经验库。
- **关键技术细节**：
  - **多智能体系统定义**：形式化为元组 ⟨S, A, T, R, N, G⟩，其中智能体使用语言模型策略 πᵢ，按有向图 G 定义的顺序交互。每个智能体生成动作 aᵢ 依赖于先前智能体的输出。
  - **SiriuS 训练流程**（Algorithm 1）：
    1. 初始化每个智能体的策略参数。
    2. 对每一轮微调迭代 t：
       - 对每个问题 xᵢ，智能体按顺序采样动作。
       - 使用奖励函数 R 评估联合轨迹，将高奖励轨迹（R > ε）加入“好轨迹集” Cₜ⁽ⁿ⁾。
       - 对低奖励轨迹进行增强（Augmentation）：利用一个外部智能体（基于真实答案）生成反馈，驱动原智能体重新生成并改写，形成新的正确轨迹。
       - 使用标准监督微调（SFT）分别在每个智能体的好轨迹集上更新参数。
  - **三种多智能体设置**：
    - **问题解决设置**：角色分工（如物理学家→数学家→总结者；或上下文分析师→问题求解者）。
    - **Actor-Critic设置**：包含Actor（生成答案）、Judgment（判断正确性）、Critic（提供反馈）、Actor（根据反馈重新生成）。
    - **竞争性设置**：如资源交换、最后通牒博弈、买卖博弈，每个智能体最大化自身效用。
- **公式与算法**：文中给出了详细的联合策略采样公式（式1）和训练算法伪代码（Algorithm 1 和 Algorithm 2），核心是迭代采样、评估、增强、SFT。

## 3. 实验设计：数据集/场景、基准、对比方法
- **数据集与场景**：
  - **College Physics/Chemistry**：由 MMLU、GPQA、TheoremQA 中的大学物理/化学问题混合构建，训练/测试分割约 2:1。
  - **PubMedQA**：1000 道生物医学问答（500训练/500测试），需理解 PubMed 摘要。
  - **竞争性场景**：资源交换（初始资源不对称）、多轮最后通牒博弈、买卖博弈（价值 40/60 的物件）。
- **基准方法**：单智能体、STaR（自举推理）、CoMM（多智能体协作提示）、TextGrad（文本梯度优化）、DSPy（MIPROv2 提示优化）。
- **对比方法**：在每种设置下，SiriuS 与上述基线进行准确率、胜率、收益等指标对比。
- **消融实验**：是否混合基础智能体、是否仅用一个LLM微调所有角色、是否去除增强模块、是否增加微调轮次。

## 4. 资源与算力
- **论文未明确说明使用的具体算力**（如GPU型号、数量、训练时长）。仅提到使用 OpenAI 的 gpt-3.5-turbo-0125 和 gpt-4o-mini-2024-07-18 作为骨干模型，并通过 OpenAI 的 Fine-tuning API 进行监督微调。未提供本地训练资源细节。
- **推测**：由于主要依赖 OpenAI API，算力消耗体现在 API 调用次数和微调费用上，而非自有 GPU。

## 5. 实验数量与充分性
- **实验数量**：
  - 在问题解决设置下，对 GPT-3.5-turbo、GPT-4o-mini、LLaMA-3.2-3B 三个模型，在三个数据集（College Physics、College Chemistry、PubMedQA）上各运行多次（表中给出均值±标准差，通常为 3 次或更多）。
  - Actor-Critic 设置下进行 PubMedQA 上的对比和消融。
  - 竞争性设置包含三种游戏（资源交换、最后通牒、买卖），并测试了跨配置泛化。
  - 消融实验：在 PubMedQA 上进行了 5 种消融（混合基础智能体、单一LLM微调所有角色、无增强、额外迭代等）。
- **充分性与公平性**：
  - 对比了多种主流方法（STaR、CoMM、TextGrad、DSPy），基线合理。
  - 报告了误差范围（±标准差），显示统计稳定性。
  - 竞争性设置中评估了泛化能力（改变初始资源/估值）。
  - **不足之处**：未在更多样的多智能体架构（如辩论、混合结构）上测试；仅覆盖了有限的任务类型（QA、博弈），未涉及编程、药物发现等。

## 6. 论文的主要结论与发现
- **SiriuS 在所有任务上一致超越了所有基线**，准确率提升 2.86%–21.88%。
- **在 Actor-Critic 设置中**，SiriuS 显著提高了真阳性准确率（从 18.40% 到 35.00% 在 GPT-3.5-turbo 上），减少了正确答案被错误修改的问题。
- **在竞争性设置中**，SiriuS 显著提高了弱势玩家的胜率和收益，且泛化到不同的初始配置。
- **消融实验表明**：联合优化所有智能体比单独优化更好；角色专用微调优于统一微调；经验增强模块对性能有重要贡献；额外迭代可带来边际收益。
- **核心贡献**：提供了一种无需中间监督、可扩展的多智能体自改进框架，生成了可复用的训练数据。

## 7. 优点
- **方法新颖**：将自举推理思想成功扩展到多智能体系统，构建经验库并增强失败轨迹，思路清晰。
- **实验扎实**：覆盖多种骨干模型、多种任务类型（推理、生物QA、竞争性博弈），包含消融和泛化测试。
- **无需人工标注**：完全利用自生成的成功轨迹和增强轨迹，降低了人工成本。
- **通用性强**：框架可适用于不同角色分工和交互拓扑，具有推广潜力。
- **代码开源**（论文中提到 Code is available），有利于复现和后续研究。

## 8. 不足与局限
- **依赖骨干模型能力**：性能受限于底层 LLM（如 GPT-3.5/4o-mini）的能力，在弱模型（LLaMA-3.2-3B）上提升幅度较小。
- **信用分配难题未完全解决**：虽然通过整体成功轨迹规避了直接分配，但框架仍无法精确追溯每个步骤的贡献，可能限制了优化效率。
- **交互协议设计仍需人工**：当前探索的角色和通信结构（如物理-数学-总结）是手动设定的，最优协议可能因任务而异。
- **实验覆盖有限**：未在更复杂多智能体系统（如多轮辩论、工具使用、动态创建/删除智能体）上评估；仅测试了三种竞争游戏，且均为对称或近似对称场景。
- **未讨论计算开销**：虽然避免了人工标注，但多次采样（max_sol, max_f, max_re）和 API 微调可能产生较高成本。
- **公平性与偏差风险**：论文提到会继承骨干模型的偏见，但未进行具体偏差分析或缓解措施。

（完）
