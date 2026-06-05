---
title: Agent Workflow Memory
title_zh: 智能体工作流记忆
authors: "Zora Zhiruo Wang, Jiayuan Mao, Daniel Fried, Graham Neubig"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=NTAhi2JEEE"
tags: ["query:agent-papers"]
score: 7.0
evidence: 工作流记忆解决长时任务
tldr: 基于语言模型的智能体在长时任务中表现不佳。本文提出AWM方法，从过去经验中归纳常用工作流，并在后续推理中选择性提供，引导智能体生成。AWM适用于离线与在线场景。在Mind2Web等基准上显著提升了任务成功率。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 853, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 703, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 864, \"height\": 276, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1417, \"height\": 709, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1485, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1247, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 841, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1422, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 512, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 883, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 797, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 834, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1058, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1594, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1592, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 890, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 791, \"height\": 206, \"label\": \"Table\"}]"
motivation: 现有方法在复杂长时任务中性能不佳。
method: 从经验中归纳可重用工作流并在推理时选择性提供。
result: 在网页导航基准上显著提升任务成功率。
conclusion: 学习工作流能有效增强智能体的长时任务能力。
---

## Abstract
Despite the potential of language model-based agents to solve real-world tasks such as web navigation, current methods still struggle with long-horizon tasks with complex action trajectories. In contrast, humans can flexibly solve complex tasks by learning reusable task workflows from past experiences and using them to guide future actions. To build agents that can similarly benefit from this process, we introduce Agent Workflow Memory (AWM), a method for inducing commonly reused routines, i.e., workflows, and selectively providing workflows to the agent to guide subsequent generations. AWM flexibly applies to both offline and online scenarios, where agents induce workflows from training examples beforehand or from test queries on the fly. We experiment on two major web navigation benchmarks — Mind2Web and WebArena — that collectively cover 1000+ tasks from 200+ domains across travel, shopping, and social media, among others. AWM substantially improves the baseline results by 24.6% and 51.1% relative success rate on Mind2Web and WebArena while reducing the number of steps taken to solve WebArena tasks successfully. Furthermore, online AWM robustly generalizes in cross-task, website, and domain evaluations, surpassing baselines from 8.9 to 14.0 absolute points as train-test task distribution gaps widen.

---

## 论文详细总结（自动生成）

# Agent Workflow Memory (AWM) 论文总结

## 1. 论文的核心问题与整体含义

- **研究动机**：基于语言模型的智能体（如网页导航代理）虽然取得了进展，但在处理长时域、复杂动作轨迹的任务时仍表现不佳。相比之下，人类能够从过往经验中学习可重用的任务工作流，并灵活指导未来行动。现有方法通常依赖固定示例或上下文学习，缺乏从经验中提取和复用通用子程序的能力，导致对新任务或环境变化的鲁棒性差。
- **整体含义**：本文提出 Agent Workflow Memory (AWM)，旨在赋予智能体类似人类的学习机制——从过去的成功或失败轨迹中归纳出常用子程序（工作流），将其存入记忆，并在后续任务中动态提供这些工作流以引导动作生成，从而显著提升任务成功率、泛化能力和效率。

## 2. 论文提出的方法论

- **核心思想**：AWM 的核心是“工作流记忆”，即从智能体先前完成的经验中抽取可复用的子程序（工作流），以自然语言描述和步骤序列的形式存储，并在推理时作为额外上下文注入智能体的提示中。
- **关键技术细节**：
  - **工作流表示**：每个工作流包含一个文本描述（d）和一个步骤序列（p₁, p₂, ...）。每个步骤包括当前环境状态的自然语言描述、智能体的推理过程以及可执行的动作（如 `click('id')`）。工作流会抽象掉示例中的具体值（如将“猫粮”替换为 `{product-name}`），以增强泛化性。
  - **工作流归纳模块（I）**：使用 LLM 将一组经验（指令+轨迹）作为输入，生成子任务级别的工作流。方法采用提示工程，要求模型提取常用子程序，并确保粒度合适、不重叠。也可使用基于规则的归纳（去重+过滤无效动作）。
  - **使用场景**：
    - **离线模式**：利用已有的训练数据（如人为标注或模型合成的示例）预先归纳工作流，测试时直接加载到记忆中使用。
    - **在线模式**：无监督场景，智能体按流式处理测试查询。每解决一个任务后，使用评估模块判断是否成功；若成功则从该轨迹中归纳工作流并添加到记忆，用于后续查询。无需任何额外标注数据。
- **算法流程**（文字说明）：初始化默认记忆 M → 对于每个任务指令 q，智能体与环境交互生成轨迹 e → 更新记忆过程（在线模式）：使用评估器判断 e 是否成功 → 若成功则调用归纳模块 I(e) 得到工作流 w → 将 w 加入记忆 M 得到 M' → 用 M' 处理下一个任务。离线模式则先在训练集上整体归纳出 W_offline，然后对所有测试任务统一使用 M+W_offline。

## 3. 实验设计

- **数据集与场景**：
  - **WebArena**：包含 812 个网页导航任务，覆盖 5 个网站（购物、CMS、Reddit、GitLab、地图），提供基于执行正确性的严格评估。
  - **Mind2Web**：强调跨任务、跨网站、跨域泛化，提供训练/测试分割，每个任务有固定步数，评估指标包括元素准确率、动作 F1、步成功率、任务成功率。
- **Benchmark 设置**：
  - WebArena 上采用标准在线设置（只有测试集），将 AWM 与 BrowserGym（当前最先进的自主方法）、SteP（使用人工专家编写的工作流）、AutoEval 等对比。
  - Mind2Web 上分别测试离线、在线模式，与 MindAct、Synapse、CogAgent 等对比。此外还构造了跨模板子集以测试跨任务泛化。
- **对比方法**：包括使用人工工程工作流的 SteP、自主基线 BrowserGym、AutoEval、MindAct、Synapse、CogAgent 等。

## 4. 资源与算力

- **文中明确说明**：使用 GPT-4o（gpt-4o-2024-05-13）和 GPT-3.5-turbo，温度为 0.0。所有实验均在 1 个 GPU 上完成？**未明确说明 GPU 型号、数量、训练时长**。只提到了 “We use the same model for neural workflow induction and agent action generation.” 但未提及具体硬件资源。因此，无法量化算力开销。

## 5. 实验数量与充分性

- **主要实验组数**：
  - **WebArena**：主实验（Table 1）+ 跨模板子集实验（Table 2）+ 效率分析（Figure 4）+ 步骤数统计（Table 1）+ 工作流质量分析（Table 9）+ 规则 vs LM 归纳对比（Table 5）。
  - **Mind2Web**：离线主实验（Table 3）+ 在线泛化实验（四组：跨任务、跨网站、跨域，Table 4）+ 工作流表示消融（子程序抽象 Table 5&6、文本 vs 代码 Table 7、环境抽象 Table 8）+ 离线+在线联合（Table 10）+ 示例顺序敏感性（Table 12）+ 行动空间扩展（Table 13）。
  - **总计约 10+ 个表格的实验**，涵盖主结果、跨任务/域泛化、多种消融（归纳方法、表示格式、环境抽象、示例顺序、记忆 vs 动作空间等）。
- **充分性与公平性**：实验设计较为全面，覆盖了核心假设（工作流可复用）、泛化性（不同分布）、效率、表示细节。对比基线均为当时 SOTA 且控制了模型变体。但部分消融仅基于 WebArena 或 Mind2Web 单一数据集，跨模态（如视觉任务）未涉及。另外，在线模式中评估器（Pan et al. 2024）的准确性可能引入噪声，但文中未专门分析此偏差。

## 6. 论文的主要结论与发现

- **核心结论**：AWM 在 WebArena 上取得了 35.5% 的总成功率，比 BrowserGym 基线提高 51.1% 相对成功率，甚至超过使用人工编写工作流的 SteP（7.9% 相对提升）。在 Mind2Web 跨任务、跨网站、跨域测试中，AWM 均大幅超越基线（绝对提升 8.9–16.9 个百分点）。
- **泛化性**：跨模板（即不同任务模板）子集上仍保持领先，表明工作流不仅适用于同模板示例。“在线 AWM” 在分布差距更大的场景下（如跨域）表现更佳，因为它直接从测试分布中学习。
- **效率**：AWM 平均步数比基线少 2.0，比 AutoEval 少 40.8 步，实现高成功率与高效率兼顾。
- **工作流表示**：抽象、子程序形式优于完整示例；LM 归纳优于规则；自然语言描述比 HTML 更有效；文本与代码格式性能相近。

## 7. 优点

- **方法设计亮点**：
  - 无监督在线学习：无需额外标注数据，仅利用测试查询即可持续改进，接近真实应用场景。
  - 工作流抽象化：自动替换具体值为占位符，增强泛化性，避免过拟合。
  - 可组合性：工作流可逐步构建更复杂的子程序（如从“查找地点”到“获取邮政编码”），形成“雪球效应”。
  - 灵活性：既适用于有离线训练数据的场景，也适用于纯在线场景。
- **实验设计亮点**：
  - 全面涵盖跨任务、跨网站、跨域泛化测试，充分验证通用性。
  - 包含多种消融实验（归纳方式、表示格式、环境抽象、示例顺序、行动空间扩展），深入分析各组件贡献。
  - 报告了步骤数、计算开销等效率指标，证明 AWM 不仅提高成功率，还不显著增加计算成本（仅增加约 10.8% 的计算量）。

## 8. 不足与局限

- **实验覆盖局限**：
  - 仅评估了网页导航任务（WebArena、Mind2Web），未涉及移动端、桌面应用或机器人控制等更广泛领域。
  - 未测试多模态输入（如截图）场景，仅使用文本表示（HTML 或可访问性树），可能限制在视觉依赖任务上的应用。
  - 模型仅限于 GPT-4o 和 GPT-3.5-turbo，未探索其他开源模型（如 Llama、Mistral）以验证泛化性。
- **偏差风险**：
  - 在线模式依赖评估器（Pan et al. 2024），其准确性可能影响工作流质量，但文中未分析评估器错误率及对最终结果的影响。
  - 工作流归纳可能引入 LLM 本身的偏见（如偏好某些动作模式），且抽象过程可能丢失关键上下文（如动态页面变化，见 Figure 6 示例）。
  - 示例顺序敏感性实验（Table 12）虽显示鲁棒，但仅涉及小样本（每网站少于 20 个示例），在大规模场景下结论可能不成立。
- **应用限制**：
  - 工作流记忆在长上下文提示中可能增加 token 消耗，尽管文中报告实际开销不大，但大规模部署时仍需考虑。
  - 系统需可靠的自动评估器（在线模式）或高质量训练数据（离线模式），在低资源环境中可能限制使用。
  - 跨模板实验虽证明泛化，但 WebArena 任务本身基于模板生成，自然环境中的任务多样性可能更高，效果有待验证。

（完）
