---
title: "OWL: Optimized Workforce Learning for General Multi-Agent Assistance in Real-World Task Automation"
title_zh: OWL：面向真实世界任务自动化通用多智能体协助的优化工作力学习
authors: "Mengkang Hu, Yuhang Zhou, Wendong Fan, Yuzhou Nie, Ziyu Ye, Bowei Xia, Tao Sun, Zhaoxuan Jin, Yingru Li, Zeyu Zhang, Yifeng Wang, Qianshuo Ye, Bernard Ghanem, Ping Luo, Guohao Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=MBJ46gd1CT"
tags: ["query:agent-papers"]
score: 7.0
evidence: 分层多智能体框架用于任务自动化
tldr: 本文提出OWL（Workforce）分层多智能体框架，包含领域无关的规划器、子任务管理协调器和专职工人，通过解耦战略规划与具体执行实现跨域迁移。该框架在多个真实世界任务自动化基准上验证了其通用性和效率，解决了现有方法需要完全重新设计的问题。Workforce为通用多智能体协助提供了可扩展方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-mbj46gd1ct/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1352, \"height\": 772, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mbj46gd1ct/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1425, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mbj46gd1ct/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 501, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mbj46gd1ct/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1435, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mbj46gd1ct/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1352, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mbj46gd1ct/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1396, \"height\": 834, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1496, \"height\": 1079, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 931, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1404, \"height\": 374, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1435, \"height\": 601, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1388, \"height\": 672, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1505, \"height\": 378, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1448, \"height\": 738, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1018, \"height\": 705, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1158, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1382, \"height\": 310, \"label\": \"Table\"}]"
motivation: 现有LLM多智能体系统跨域迁移时需要完全重新设计和重训练。
method: 提出分层多智能体框架Workforce，包含规划器、协调器和专职工人，解耦规划与执行。
result: 在多个域的任务上展示了无需重训练的跨域迁移能力。
conclusion: 解耦架构实现了多智能体系统的通用性和可扩展性。
---

## Abstract
Large Language Model (LLM)-based multi-agent systems show promise for automating real-world tasks but struggle to transfer across domains due to their domain-specific nature.
Current approaches face two critical shortcomings: they require complete architectural redesign and full retraining of all components when applied to new domains.
We introduce **Workforce**, a hierarchical multi-agent framework that decouples strategic planning from specialized execution through a modular architecture comprising:
*(i)* a *domain-agnostic* **Planner** for task decomposition,
*(ii)* a **Coordinator** for subtask management, and
*(iii)* specialized **Workers** with *domain-specific* tool-calling capabilities.
This decoupling enables cross-domain transferability during both inference and training phases:
During inference, Workforce seamlessly adapts to new domains by adding or modifying worker agents;
For training, we introduce **Optimized Workforce Learning (OWL)**, which improves generalization across domains by optimizing a domain-agnostic planner with reinforcement learning from real-world feedback.
To validate our approach, we evaluate Workforce on the GAIA benchmark, covering various realistic, multi-domain agentic tasks.
Experimental results demonstrate Workforce achieves open-source state-of-the-art performance (**69.70%**), outperforming commercial systems like OpenAI's Deep Research by **2.34%**.
More notably, our OWL-trained 32B model achieves **52.73%** accuracy (**+16.37%**) and demonstrates performance comparable to GPT-4o on challenging tasks.
To summarize, by enabling scalable generalization and modular domain transfer, our work establishes a foundation for the next generation of general-purpose AI assistants.

*Our code is available at [Anonymous URL](https://anonymous.4open.science/r/annonymous-owl/), and our data is available at [Anonymous URL](https://huggingface.co/anonymous21016).*

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：当前基于大语言模型（LLM）的多智能体系统（MAS）在真实世界任务自动化中展现出潜力，但其设计高度领域特定，导致跨域迁移时面临两大短板：  
  - 推理阶段：部署到新领域需要完全重新设计架构（如MetaGPT针对软件工程定制，无法扩展至其他领域）。  
  - 训练阶段：现有方法（如MALT）需对每个智能体分别进行重训练，灵活性极低。  
- **动机**：提出一种通用、模块化的多智能体架构，通过解耦战略规划与领域特定执行，实现快速、低成本的跨域适应。

## 2. 方法论：核心思想、关键技术细节、算法流程

### 核心思想
- **Workforce框架**：分层多智能体推理架构，将任务分解与领域无关的规划、子任务协调、领域具体的执行三者解耦。  
  - **Planner（规划器）**：领域无关，负责根据高层目标生成抽象任务分解。  
  - **Coordinator（协调器）**：将子任务分配给合适的Worker，管理依赖并整合结果。  
  - **Worker Nodes（工人节点）**：一组领域特定的智能体，配备专用工具执行子任务（例如Web Agent、文档处理Agent、推理/编码Agent）。  
- **OWL训练范式**：仅对领域无关的Planner进行优化（SFT初始化 + DPO强化学习），Worker无需重训练，实现跨域泛化。

### 关键技术细节
- **通信机制**：通过共享的任务通道（Task Channel）集中通信，Worker只向通道发布最终结果，保持上下文干净。  
- **重规划机制（Replanning）**：Worker在子任务失败时报告失败信息，Planner根据反馈生成新子任务，实现测试时缩放。  
- **训练数据**：使用HotpotQA、WikiTableQuestions、数学问题、Infinity-MM四个数据集，覆盖多跳推理、表格操作、代码执行、多模态处理。  
- **轨迹合成**：用GPT-4o-mini在Workforce框架下生成轨迹，经准确性过滤后得到1,599条SFT轨迹和1,009对DPO偏好对。  
- **训练配置**：两阶段训练：SFT（初始化Planner） + DPO（偏好优化）。输入序列截断至32,768 tokens，学习率1e-5，训练2个epoch，bfloat16混合精度。

## 3. 实验设计

- **数据集/场景**：GAIA Benchmark（验证集），包含Level 1、Level 2、Level 3三个难度等级，涵盖网络浏览、多模态推理、代码执行等真实任务。
- **基准对比**：  
  - 专有框架：OpenAI Deep Research (O3)、h2oGPTe Agent、Trase Agent、Langfun Agent等。  
  - 开源框架：Magnetic-One、Open Deep Research、TapeAgents、AutoAgent等。  
  - 基线：单智能体（Single Agent）、角色扮演（Role Playing）——均使用与Workforce相同的工具集。
- **评价指标**：准确率（Accuracy，%）。  
- **实验分组**：  
  - 表1：Workforce在GAIA上与所有基线对比。  
  - 表3：不同Planner模型（含OWL训练）对比。  
  - 消融实验：轨迹过滤、训练组件（Planner vs Worker）、重规划次数、能力类型分析、错误分析等。

## 4. 资源与算力

- 文中明确说明训练使用 **8块NVIDIA H100 GPU**，采用LlamaFactory框架。  
- 超参数：学习率1e-5，训练2个epoch，batch size = 12（per-device 1 + 梯度累积12步），bfloat16混合精度。  
- 推理时通过API调用模型，无需本地GPU。  
- **资源充分性**：训练资源适中，但未报告具体训练时长（仅提到数据量3,466条轨迹，过滤后1,599条）。

## 5. 实验数量与充分性

- **实验数量**：  
  - 主实验（表1）：对比15+个基线（专有+开源），报告Level 1/2/3及平均准确率。  
  - Planner训练实验（表3）：4种不同Planner对比（含OWL SFT、SFT+DPO）。  
  - 消融实验（图2a）：轨迹过滤的影响。  
  - 消融实验（图4c）：训练Planner vs Worker vs 两者。  
  - 分析实验（图3左、右）：按能力类型性能、测试时缩放。  
  - 错误分析（表7、表8）：手动分类200+个案例的失败模式。  
  - 统计显著性（附录H）：Wilcoxon检验验证Workforce优于基线的显著性。  
- **充分性与客观性**：  
  - 严格控制工具集（单智能体和角色扮演与Workforce使用相同工具）。  
  - 采用pass@3（GPT-4o）和pass@1（Claude-3.7-sonnet）采样，并屏蔽已泄露答案的网站。  
  - 对比覆盖专有和开源的最强基线，实验设计全面、公平。

## 6. 主要结论与发现

1. **Workforce达到开源SOTA**：在GAIA上准确率69.70%，超越OpenAI Deep Research（67.36%）2.34%，且首次有开源系统超过它。  
2. **OWL显著提升中小型模型**：Qwen2.5-32B-Instruct经OWL训练后提升16.37%（从36.36%到52.73%），超越GPT-4o-mini（47.27%）和Qwen2.5-72B-Instruct（49.09%），在Level 3任务上与GPT-4o持平。  
3. **模块化设计带来跨域迁移性**：仅需替换/添加Worker即可适应新领域，无需重训练Planner。  
4. **训练Planner比训练Worker更关键**：单独训练Planner（45.45%）远超单独训练Worker（31.51%），两者联合训练（46.68%）提升极小。  
5. **重规划机制实现测试时缩放**：增加重规划次数可稳定提升性能。  
6. **错误主要由工具限制和规划错误引起**：工具限制（32.69%）和规划器错误（21.15%）是主要失败原因。

## 7. 优点

- **架构创新**：解耦领域无关规划与领域特定执行，实现真正的“即插即用”扩展。  
- **训练效率**：仅优化Planner，避免全组件重训练，大幅降低计算成本。  
- **性能领先**：开源系统中首次超越专有Deep Research，缩小开源与商用的差距。  
- **全面开源**：代码、模型、数据全部开放，可复现性强。  
- **实验严谨**：包含丰富的消融、错误分析、统计检验、多种基线，对比公平。  
- **通用性验证**：在GAIA多领域、多模态任务上验证，且训练数据不含GAIA数据，证明真实泛化能力。

## 8. 不足与局限

1. **对工具体系的依赖**：模块化扩展性依赖高质量领域特定工具，若缺乏可靠工具包可能形成执行瓶颈。  
2. **强化学习反馈延迟**：从真实世界反馈（如在线搜索）中学习需要时间，导致训练耗时。  
3. **算力报告不完整**：未给出具体训练时长（如GPU小时数），影响复现成本估算。  
4. **错误分析表明工具限制占比高**（32.69%），提示当前工具能力是主要瓶颈，模型本身尚有提升空间。  
5. **仅在一个基准（GAIA）上评估**，缺乏其他真实任务（如软件工程、医疗等）的跨域验证，泛化能力有待进一步检验。  
6. **数据污染与网络不稳定**（附录G、F）：真实环境中可能遭遇信息源不一致、过时信息、权限拒绝等问题，实际部署稳健性需更多测试。

（完）
