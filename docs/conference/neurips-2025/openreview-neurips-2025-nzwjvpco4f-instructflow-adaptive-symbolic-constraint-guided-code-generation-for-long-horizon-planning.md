---
title: "InstructFlow: Adaptive Symbolic Constraint-Guided Code Generation for Long-Horizon Planning"
title_zh: InstructFlow：面向长时域规划的自适应符号约束引导代码生成
authors: "Haotian Chi, Zeyu Feng, Yueming Lyu, Chengqi Zheng, Linbo Luo, Yew-Soon Ong, Ivor Tsang, Hechang Chen, Yi Chang, Haiyan Yin"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=nzwjvpCO4F"
tags: ["query:agent-papers"]
score: 7.0
evidence: 多智能体代码生成用于长时域机器人规划
tldr: 机器人长时域任务需要将非符号化目标转化为满足时空约束的可执行程序。InstructFlow通过多智能体协作，规划者构建层次化指令图分解目标，代码生成器产生对应代码片段，并利用符号反馈进行自适应恢复。在多个操作任务上验证了其优势。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-nzwjvpco4f/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1422, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nzwjvpco4f/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 441, \"height\": 732, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nzwjvpco4f/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1129, \"height\": 597, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nzwjvpco4f/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 305, \"height\": 283, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nzwjvpco4f/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 703, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nzwjvpco4f/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1428, \"height\": 823, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nzwjvpco4f/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1262, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nzwjvpco4f/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1432, \"height\": 900, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nzwjvpco4f/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1252, \"height\": 924, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-nzwjvpco4f/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nzwjvpco4f/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nzwjvpco4f/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1417, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nzwjvpco4f/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1454, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nzwjvpco4f/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1469, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nzwjvpco4f/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1462, \"height\": 139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nzwjvpco4f/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1469, \"height\": 118, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nzwjvpco4f/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1120, \"height\": 1374, \"label\": \"Table\"}]"
motivation: 语言模型在长时域任务分解、约束满足和故障恢复方面存在不足。
method: 提出多智能体框架，规划者构建层次化指令图分解任务，代码生成器生成满足约束的代码片段，并通过符号反馈循环进行自适应调整。
result: 在机器人操作任务上，相比基线方法提高了任务成功率和约束满足率。
conclusion: 符号引导的多智能体协作有效解决了长时域规划中的分解与自适应问题。
---

## Abstract
Long-horizon planning in robotic manipulation tasks requires translating underspecified, symbolic goals into executable control programs satisfying spatial, temporal, and physical constraints. However, language model-based planners often struggle with long-horizon task decomposition, robust constraint satisfaction, and adaptive failure recovery. We introduce InstructFlow, a multi-agent framework that establishes a symbolic, feedback-driven flow of information for code generation in robotic manipulation tasks. InstructFlow employs a InstructFlow Planner to construct and traverse a hierarchical instruction graph that decomposes goals into semantically meaningful subtasks, while a Code Generator generates executable code snippets conditioned on this graph. Crucially, when execution failures occur, a Constraint Generator analyzes feedback and induces symbolic constraints, which are propagated back into the instruction graph to guide targeted code refinement without regenerating from scratch. This dynamic, graph-guided flow enables structured, interpretable, and failure-resilient planning, significantly improving task success rates and robustness across diverse manipulation benchmarks, especially in constraint-sensitive and long-horizon scenarios.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：在机器人长时域操作任务中，需要将非符号化（underspecified）的自然语言目标转化为满足空间、时间、物理约束的可执行控制程序。现有基于大语言模型（LLM）的规划器在长时域任务分解、约束的鲁棒满足以及执行失败的自适应恢复方面存在严重不足：它们往往生成语法正确但物理上不可行的代码，且在失败后只会盲目重试或局部调整，难以推理失败的深层结构原因。
- **核心挑战**：自然语言指令本质上是欠定的、模糊的，难以在物理世界中落地。LLM 缺乏层次化结构和反馈整合机制，导致在动态、约束丰富的场景中推理能力有限。
- **整体含义**：本文旨在通过构建一个符号化、反馈驱动的多智能体框架，将任务分解、代码生成与失败恢复有机整合，使机器人规划变得结构化、可解释、抗失败，从而在长时域与约束敏感任务中取得显著提升。

## 2. 方法论

### 核心思想
- 引入一个**层次化指令图（Hierarchical Instruction Graph）** 来组织任务目标，并配合**符号约束诱导（Symbolic Constraint Induction）** 机制，使系统能够从执行失败中提取结构化知识，实现**定向、局部代码修复**，而非整体重新生成。

### 三个协作智能体

1. **InstructFlow 规划器（Planner）**
   - 根据任务目标和初始状态构建指令图 \( G_t = (V_t, E_t) \)。
   - 节点分为**规划节点**（可直接翻译为机器人可执行代码的子目标）和**推理节点**（进行空间关系推断、对象选择、参数范围调整等符号变换）。
   - 根据符号约束反馈动态更新图结构，插入或修改推理节点。

2. **代码生成器（Code Generator）**
   - 将指令图中的每个规划节点转换为可执行的 Python 代码，包括 `get_plan()`（动作序列）和 `get_domain()`（参数采样域）。
   - 代码生成过程受到推理节点输出的符号细化（如空间关系、参数范围）的引导。

3. **约束生成器（Constraint Generator）**
   - 分析执行失败反馈（如碰撞、放置不稳），按照四阶段工作流：**失败相关实体检索 → 代码级推理 → 诊断推理（几何/物理分析） → 符号约束归纳**。
   - 输出逻辑约束 \( \phi \)，形式为关系约束与物理约束的合取，例如 `ClearOf(gripper, object_5) ∧ ProximitySafe(...)`。

### 符号约束诱导
- 基于物理谓词（实体、关系、物理函数、阈值）进行诊断，将低层失败抽象为可复用的符号规则。
- 这些约束被注入指令图，指导规划器和代码生成器进行局部修复。

### 算法流程
1. 初始构建指令图（仅含规划节点）。
2. 代码生成器根据指令图生成代码，执行并在仿真中检查约束。
3. 若失败，约束生成器分析反馈，归纳符号约束。
4. 规划器根据约束动态更新指令图（添加推理节点）。
5. 代码生成器仅重新生成受影响的子目标代码，避免全文重写。
6. 重复直至成功或达到迭代上限。

## 3. 实验设计

### 环境与任务
- **仿真平台**：Ravens（基于 PyBullet 物理引擎），使用 UR5 六自由度机械臂和 Robotiq 2F-85 夹爪。
- **三大领域**：
  - **Drawing**：绘制星形、箭头、字母等，需避开随机摆放的障碍物。
  - **Arrange-Blocks**：堆叠金字塔、排列直线、包装（packing）、解堆（unstack）等。
  - **Arrange-YCB**：操作 YCB 数据集中不规则形状物体，进行包装和堆叠。

### 约束类型
- 运动学可达性、碰撞避免、抓取稳定性、放置有效性。

### 基线方法
- **PRoC3S**（最直接相关）：两阶段 LLM 规划器 + 约束满足，带反馈。
- **LLM³**：LLM 直接输出带连续参数的技能序列。
- **Code-as-Policies (CaP)**：LLM 生成完整 Python 程序。

### 评估指标
- **任务成功率**：最终机器人状态满足目标条件且不违反任何约束。

### 补充评估
- 使用 VLM（GPT-4o）进行语义验证，修正原 PRoC3S 协议中“仅无约束违反即算成功”的漏洞。
- 还评估了反馈查询次数、端到端延迟、对感知噪声和反馈歧义的鲁棒性。

## 4. 资源与算力

- **文中明确说明**：仿真实验在配备 **32GB RAM 的 CPU** 上运行，未使用 GPU。
- **所有方法均通过 OpenAI GPT-4o API 查询**，因此计算资源主要依赖远程 API。
- **未提供**具体的 API 调用次数、训练时长或 GPU 型号/数量等详细信息（因为方法无需模型训练）。

## 5. 实验数量与充分性

- **主要实验**：在 10 个任务（3 个领域 × 各若干子任务）上，每个方法运行 **10 个随机种子**，结果取平均。
- **消融实验**：对比完整 InstructFlow 与去掉规划器智能体、去掉约束生成器智能体的变体，覆盖 10 个任务。
- **鲁棒性实验**：添加感知噪声（σ=0.005~0.02）、反馈错误/不完整场景，在 6 个任务上测试。
- **额外实验**：引入 VLM 视觉输入、统计反馈查询次数和延迟、提供多个案例研究。
- **评价**：实验设计比较全面，覆盖了多种任务类型、噪声和反馈干扰，消融实验验证了各模块贡献，基线对比公平（采用相同设定）。但所有实验限于仿真，无真实机器人验证。

## 6. 主要结论与发现

- **成功率显著提升**：InstructFlow 在各任务上比 PRoC3S 等基线高出 **20–40 个百分点**。
- **反馈效率更高**：平均反馈查询次数减少约 **37%**，端到端延迟降低约 **4.7%**。
- **强鲁棒性**：在感知噪声（σ=0.02）下平均成功率仅下降 18.3%；在错误/不完整反馈下，成功率下降 11–16%。
- **符号约束可有效引导修复**：案例研究（解堆、金字塔、YCB堆叠）展示了约束归纳和指令图更新如何实现定向代码修正（如调整参数范围、重新排序子目标）。
- **消融分析**：去除规划器或约束生成器均导致性能大幅下降（最高 50%），证明层次结构化和符号反馈驱动修复是关键。

## 7. 优点

- **创新性**：将符号约束诱导与层次化指令图结合，实现了从失败中学习可复用约束并进行局部修复，不同于传统“全局重规划”或“盲目重试”。
- **可解释性**：符号约束和指令图为规划过程提供了透明、可理解的中间表征。
- **模块化与通用性**：三个智能体各司其职，推理节点类型可扩展，约束形式化统一，易于迁移到新任务。
- **实验严谨**：修正了原 PRoC3S 评估协议的缺陷（添加 VLM 语义验证），进行了鲁棒性测试和消融，结果可信。
- **实际潜力**：尽管仅在仿真中，但噪声和反馈歧义实验表明其对真实世界不确定性有良好容忍度。

## 8. 不足与局限

- **仿真局限性**：所有实验均在 Ravens/PyBullet 仿真中进行，未部署到真实机器人。虽然模拟了噪声，但真实机器人面临的感知、控制、硬件不确定性更复杂。
- **依赖特定 LLM**：基于 GPT-4o，性能可能受模型特性影响；未测试开源模型或更小模型。
- **符号约束的局限性**：约束归纳依赖于预定义的物理谓词（如 ProximitySafe、ClearOf），尽管可扩展，但仍需人工设计这些基元，可能限制完全自动化。
- **计算开销**：虽然延迟有所降低，但多智能体多轮交互仍比单次生成慢，且依赖外部 API（GPT-4o），可能不适合实时或边缘部署。
- **任务范围**：仅覆盖简单几何堆叠与操作，未涉及精细操作（如螺丝拧紧）或动态环境（如移动障碍物）。
- **未处理隐式常识**：对于需要深度物理知识（如材料属性）的失败，约束归纳可能力不从心。

（完）
