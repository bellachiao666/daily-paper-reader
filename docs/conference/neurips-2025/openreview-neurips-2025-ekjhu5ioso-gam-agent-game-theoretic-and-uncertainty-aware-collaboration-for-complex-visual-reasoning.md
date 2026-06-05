---
title: "GAM-Agent: Game-Theoretic and Uncertainty-Aware Collaboration for Complex Visual Reasoning"
title_zh: GAM-Agent：博弈论与不确定性感知的复杂视觉推理协作框架
authors: "Jusheng Zhang, Yijia Fan, Wenjun Lin, Ruiqi Chen, Haoyi Jiang, Wenhao Chai, Jian Wang, Keze Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=EKJhU5ioSo"
tags: ["query:agent-papers"]
score: 8.0
evidence: 博弈论多智能体协作用于复杂视觉推理
tldr: 复杂视觉推理中单一模型能力受限。GAM-Agent将推理过程建模为非零和博弈，基座智能体从不同视角提取信息，批评智能体验证逻辑一致性，并通过不确定性驱动的动态协作和辩论机制，提升预测的鲁棒性和可解释性。在MMMU等四个基准上验证了有效性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ekjhu5ioso/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1142, \"height\": 944, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ekjhu5ioso/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ekjhu5ioso/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1430, \"height\": 512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ekjhu5ioso/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 685, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ekjhu5ioso/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1426, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ekjhu5ioso/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1410, \"height\": 815, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ekjhu5ioso/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1130, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ekjhu5ioso/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1126, \"height\": 744, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ekjhu5ioso/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 974, \"height\": 693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ekjhu5ioso/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 884, \"height\": 148, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ekjhu5ioso/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1276, \"height\": 137, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ekjhu5ioso/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 958, \"height\": 755, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ekjhu5ioso/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 961, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ekjhu5ioso/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1074, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ekjhu5ioso/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 726, \"height\": 724, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ekjhu5ioso/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 957, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ekjhu5ioso/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 957, \"height\": 517, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ekjhu5ioso/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1100, \"height\": 1038, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ekjhu5ioso/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1096, \"height\": 1070, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ekjhu5ioso/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1460, \"height\": 1026, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ekjhu5ioso/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1462, \"height\": 1191, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ekjhu5ioso/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1462, \"height\": 1350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ekjhu5ioso/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1463, \"height\": 1287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ekjhu5ioso/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1462, \"height\": 1314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ekjhu5ioso/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1464, \"height\": 1421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ekjhu5ioso/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1465, \"height\": 1442, \"label\": \"Table\"}]"
motivation: 现有视觉语言模型在复杂推理中缺乏多视角协作和纠错机制。
method: 提出博弈论多智能体框架，基座智能体负责不同视觉感知子任务，批评智能体进行逻辑验证，不确定性控制器动态调节协作与辩论。
result: 在MMMU、MMBench等多个基准上取得了鲁棒的改进。
conclusion: 博弈论框架为多模态推理提供了有效的协作范式。
---

## Abstract
We propose **GAM-Agent**, a game-theoretic multi-agent framework for enhancing vision-language reasoning. Unlike prior single-agent or monolithic models, GAM-Agent formulates the reasoning process as a non-zero-sum game between base agents—each specializing in visual perception subtasks—and a critical agent that verifies logic consistency and factual correctness. Agents communicate via structured claims, evidence, and uncertainty estimates. The framework introduces an uncertainty-aware controller to dynamically adjust agent collaboration, triggering multi-round debates when disagreement or ambiguity is detected. This process yields more robust and interpretable predictions. Experiments on four challenging benchmarks—MMMU, MMBench, MVBench, and V*Bench—demonstrate that GAM-Agent significantly improves performance across various VLM backbones. Notably, GAM-Agent boosts the accuracy of small-to-mid scale models (e.g., Qwen2.5-VL-7B, InternVL3-14B) by 5–6\%, and still enhances strong models like GPT-4o by up to 2–3\%. Our approach is modular, scalable, and generalizable, offering a path toward reliable and explainable multi-agent multimodal reasoning.

---

## 论文详细总结（自动生成）

以下是基于提供的论文《GAM-Agent: Game-Theoretic and Uncertainty-Aware Collaboration for Complex Visual Reasoning》的详细中文总结。

---

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有视觉语言模型（VLM）在复杂视觉推理（如多步推理、视觉歧义）中通常依赖单一模型或简单集成策略（如平均或投票），缺乏多视角协作与纠错机制，导致在高难度任务（如MMMU）上表现不佳。
- **整体含义**：受人类专家通过博弈达成共识的启发，论文将视觉推理过程建模为一个**非零和博弈**，引入**基座智能体**（负责不同视觉感知子任务）和**批评智能体**（验证逻辑一致性和事实正确性），并通过**不确定性感知控制器**动态调节协作、触发多轮辩论，最终得到更鲁棒和可解释的预测。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 将多智能体视觉推理视为一个**非零和博弈**。基座智能体提供初始分析与证据，批评智能体进行验证与批判，**不确定性**作为核心变量驱动权重分配与辩论触发。

### 关键技术细节
1. **系统形式化定义（六元组）**：
   - 智能体集合 E
   - 分析能力映射函数集合 A（Ai:图像×问题 → 响应）
   - 不确定性评估函数集合 Φ（Φi:响应→[0,1]）
   - 证据定位映射函数集合 M（Mi:声明×图像 → 视觉区域+置信度）
   - 声明解析函数 P（非结构化响应→结构化元组）
   - 辩论模块 D

2. **基座智能体与批评智能体**：
   - 基座：对象识别、场景描述、OCR
   - 批评：事实检查、完整性检查、逻辑检查

3. **不确定性量化（Φ）**：
   - **生成过程不确定性**（Φigen+）：利用 token 生成概率计算信息熵与 top-2 概率差的综合指标。
   - **语义标记不确定性**（Φisem）：当概率不可获取时，通过识别文本中的不确定性标记（如“可能”“模糊”）并加权计算 sigmoid 得分。

4. **证据映射与声明解析**：将文本声明与图像特定视觉区域关联，构建可追溯的证据链路。

5. **初始整合与冲突检测**：
   - 基于不确定性用 softmax 分配初始权重 w(0)i = e^{-βUi}/∑e^{-βUj}。
   - 判断系统加权平均不确定性 U_sys 和智能体间冲突分数是否超过阈值，以触发多轮辩论。

6. **迭代辩论过程**：
   - 每轮辩论由五个步骤组成：识别争议焦点、生成针对性论点、动态权重更新（基于不确定性变化）、生成该轮集成响应、评估系统不确定性。
   - 终止条件：U_sys 低于阈值、达到最大轮次、不确定性变化小于收敛阈值。

## 3. 实验设计

### 使用的数据集 / 场景
- **图像理解**：MMMU（多学科多模态理解）、MMBench_V11_Test（视觉推理与感知）
- **视频时序推理**：MVBench_Test
- **引导视觉搜索（细粒度定位）**：V*Bench（属性识别 AR、空间推理 SR）

### 对比方法
- 多智能体框架：DMAD、DMPL、ChatEval、MAD、DebUnc
- 作为基座的 VLM：Qwen2.5VL（7B、72B）、InternVL3（14B、78B）、GPT-4o-0513
- 部分实验使用更多模型（如Qwen2.5VL 3B/32B、InternVL3 2B/8B/38B）进行更广泛分析。

### 实验设置
- 默认 3 个基座智能体 + 3 个批评智能体，最大辩论轮次 3，贪心解码。
- 开源模型在 NVIDIA A100 GPU 本地部署，GPT-4o 通过 OpenRouter API 调用。

## 4. 资源与算力

- **本地部署**：使用 NVIDIA A100 GPU（型号未具体说明，但提到单 A100）。
- **成本估算**（附录 A）：按 AWS p4d.24xlarge 实例（8x A100 40GB，$32.77/小时）折算，单 A100 约 $4.10/小时。
- **训练**：论文未涉及训练（仅推理阶段使用预训练 VLM 作为智能体），因此未报告训练算力。
- **推理开销**：辩论过程增加 token 消耗，附录 B 详细分析了多轮辩论的成本动态。

## 5. 实验数量与充分性

- **主实验**：表 1（MMMU, MMBench, MVBench）覆盖 5 种基座模型 × 6 种多智能体方法 × 3 个基准，共约 90 个配置的对比。
- **V*Bench 实验**（表 2）：同上规模，另与 SEAL 对比。
- **消融实验**（图 3）：5 种消融变体（去除多智能体、去除不确定性、去除证据映射等）在 MMBench 上分析准确率、辩论轮次、触发率、成本。
- **最大辩论轮次研究**（图 2）：从 0 到 9 轮，观察准确率饱和点。
- **专家权重演化**（图 4）：在 8 种不同规模的 Qwen2.5VL 和 InternVL3 模型上展示 3 轮辩论中三个专家权重与系统不确定性的变化。
- **超参数消融**（附录 H）：对 β_weight、θU、θC、αΦ 等进行了系统分析。
- **不确定性处理能力分析**（附录 C）：对比 UA、CE、DA 指标。
- **成本-性能平衡分析**（附录 A、B）：对比 API 模型与本地推理成本。

**结论**：实验丰富，涵盖多个独立测试基准、多种模型规模、详细消融和敏感性分析，对比方法均为当前主流多智能体框架，设置公平、结果客观。

## 6. 论文的主要结论与发现

1. **GAM-Agent 在所有基准和基座模型上一致提升性能**：小模型（如 Qwen2.5VL-7B）提升 5–6%，大模型（如 GPT-4o）提升 2–3%。
2. **关键组件不可或缺**：去除不确定性、证据映射、动态权重或迭代辩论均导致性能下降（消融实验）。
3. **辩论轮次 3 轮左右达到饱和**：继续增加轮次收益微乎其微。
4. **不确定性驱动有效**：系统不确定性随辩论轮次指数下降，专家权重动态调整，与模型能力相关。
5. **成本可控**：在本地部署下，GAM-Agent 可实现优于高价 API 模型的性价比（如 InternVL3-78B/Ours 达 92.2% 准确率，成本仅 $0.00022/指令）。

## 7. 优点

- **创新性**：将博弈论引入多智能体 VLM 推理，以不确定性为核心变量建模协作与辩论，区别于简单投票或固定角色方法。
- **可解释性**：证据映射和结构化的声明-证据元组使推理过程可追溯、可验证。
- **鲁棒性与泛化性**：在多个模型（从 7B 到 78B，开源与闭源）和多种任务（图像、视频、细粒度搜索）上均有效。
- **模块化设计**：基座智能体与批评智能体可灵活替换、扩展。
- **详细的理论支撑**（附录 D、E、F、G）：形式化定义了非零和博弈、效用函数、最优权重推导，与 DMAD 等传统方法进行了数学对比。

## 8. 不足与局限

- **计算开销**：迭代辩论增加推理延迟和 token 消耗，对实时应用可能不友好。
- **主观/歧义问题**：案例中（如“哪个图像更颜色丰富？”）专家对概念理解不一致，批评模块未能纠正语义歧义，导致错误。
- **专家选择机制不完善**：对无文本图像仍激活 OCR 专家，缺乏自适应屏蔽能力。
- **批评模块能力有限**：当专家都给出高置信度但错误答案时，批评智能体未能识别和纠正。
- **超参数敏感**：辩论触发阈值等超参数需要根据基座模型和任务调优（附录 H 显示性能有波动）。
- **未验证真实世界部署**：实验仅基于公开基准，未涉及实际应用中的噪声、对抗样本或长尾情况。
- **仅评估推理阶段**：未探索是否可通过训练或微调智能体进一步提升协作效率。

---

（完）
