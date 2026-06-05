---
title: "ThinkAct: Vision-Language-Action Reasoning via Reinforced Visual Latent Planning"
title_zh: ThinkAct：通过增强视觉潜在规划进行视觉-语言-动作推理
authors: "Chi-Pin Huang, Yueh-Hua Wu, Min-Hung Chen, Yu-Chiang Frank Wang, Fu-En Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=72UR53jN7T"
tags: ["query:agent-papers"]
score: 7.0
evidence: 强化学习用于代理规划与自改进
tldr: 该论文提出ThinkAct双系统框架，通过增强视觉潜在规划连接高层推理与低层动作执行，利用任务完成和轨迹一致性奖励训练多模态LLM生成规划。在视觉语言动作任务中，该方法提升了长期规划能力和自适应性，体现了强化学习在代理自改进中的应用。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-72ur53jn7t/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-72ur53jn7t/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-72ur53jn7t/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1436, \"height\": 748, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-72ur53jn7t/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 869, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-72ur53jn7t/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 642, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-72ur53jn7t/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1362, \"height\": 242, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-72ur53jn7t/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1369, \"height\": 239, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-72ur53jn7t/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 582, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-72ur53jn7t/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 594, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-72ur53jn7t/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 757, \"height\": 275, \"label\": \"Table\"}]"
motivation: 现有端到端方法缺乏显式推理，难以进行多步规划与适应复杂任务变体。
method: 提出双系统框架，用强化学习训练多模态LLM生成基于视觉奖励的推理规划。
result: 在多种VLA基准上实现优于以往方法的长期规划与自适应能力。
conclusion: ThinkAct通过强化学习整合显式规划，为自改进代理提供了有效框架。
---

## Abstract
Vision-language-action (VLA) reasoning tasks require agents to interpret multimodal instructions, perform long-horizon planning, and act adaptively in dynamic environments. Existing approaches typically train VLA models in an end-to-end fashion, directly mapping inputs to actions without explicit reasoning, which hinders their ability to plan over multiple steps or adapt to complex task variations. In this paper, we propose ThinkAct, a dual-system framework that bridges high-level reasoning with low-level action execution via reinforced visual latent planning. ThinkAct trains a multimodal LLM to generate embodied reasoning plans guided by reinforcing action-aligned visual rewards based on goal completion and trajectory consistency. These reasoning plans are compressed into a visual plan latent that conditions a downstream action model for robust action execution on target environments. Extensive experiments on embodied reasoning and robot manipulation benchmarks demonstrate that ThinkAct enables few-shot adaptation, long-horizon planning, and self-correction behaviors in complex embodied AI tasks.

---

## 论文详细总结（自动生成）

# ThinkAct 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **问题**：现有的视觉-语言-动作（VLA）模型通常采用端到端训练方式，直接将多模态输入映射为动作，缺乏显式的推理过程。这导致模型在多步规划、长程任务以及复杂环境变体上的适应能力不足。
- **背景**：虽然多模态大语言模型（MLLM）在视觉问答等任务上取得显著进展，但在需要长期规划和与环境交互的具身任务中仍面临挑战。现有的链式思维（CoT）方法依赖人工标注或全监督微调，成本高且易过拟合。
- **目标**：提出一个能够“先思考后行动”的推理型 VLA 框架，通过强化学习激励 MLLM 生成具身推理规划，并通过视觉潜在规划连接高层推理与低层动作执行，实现长程规划、少样本适应和自我纠错。

## 2. 方法论

### 2.1 核心思想
- **双系统架构**：将推理 MLLM（系统1）与动作执行模型（系统2）分离，通过视觉潜在规划（visual plan latent）连接两者。
- **动作对齐的视觉反馈**：设计基于目标完成度和轨迹一致性的奖励信号，引导 MLLM 进行具身推理。
- **强化学习（GRPO）**：使用组相对策略优化（Group Relative Policy Optimization）激励 MLLM 生成高质量推理链和视觉规划。
- **异步运行**：推理 MLLM 每 N 步生成一次规划，动作模型则高频执行，实现“慢思考、快控制”。

### 2.2 关键技术细节
1. **奖励塑造**：
   - 目标奖励 \( r_{\text{goal}} \)：比较预测的起始/终点位置与真实轨迹的对应点。
   - 轨迹奖励 \( r_{\text{traj}} \)：通过动态时间规整（DTW）衡量预测轨迹与真实轨迹的分布匹配度。
   - 格式奖励 \( r_{\text{format}} \)：确保输出格式正确。
   - 总奖励：\( r = 0.9 r_{\text{visual}} + 0.1 r_{\text{format}} \)，其中 \( r_{\text{visual}} = 0.5 r_{\text{goal}} + 0.5 r_{\text{traj}} \)。

2. **GRPO 优化**：
   - 从旧策略 \( F_{\theta_{\text{old}}} \) 采样 M 个响应，计算每个响应的奖励，再优化新策略 \( F_\theta \)。
   - 目标函数包括优势项和 KL 散度正则项。

3. **视觉潜在规划**：
   - MLLM 生成推理步骤后，将推理压缩为紧凑的视觉潜在向量 \( c_t \)，代表高层意图。
   - 该潜在向量通过 Q-Former 投影，作为条件输入到动作模型（DiT-based policy）中。

4. **动作模型训练**：
   - 冻结推理 MLLM，仅更新状态编码器、潜在投影器和动作模型，通过模仿学习（行为克隆）优化。

### 2.3 训练流程
- **阶段1：冷启动（SFT）**：用含轨迹标注的开放数据集和 VQA 数据微调 MLLM，使其学会输出正确格式的推理和规划。
- **阶段2：强化学习（GRPO）**：使用动作对齐的视觉奖励和 QA 奖励进一步优化 MLLM。
- **阶段3：动作适应**：冻结 MLLM，在目标环境上微调动作模型，条件于视觉潜在规划。

## 3. 实验设计

### 3.1 数据集与基准
- **训练数据**：
  - 冷启动：Open X-Embodiment (OXE) 子集、RoboVQA、EgoPlan-IT、Video-R1-CoT。
  - RL 训练：OXE 子集、Something-Something v2 人类视频、EgoPlan-IT/Val、RoboVQA、Reflect、LLaVA-Video-178K。
- **评估基准**：
  - **机器人操作**：SimplerEnv（Google-VM、Google-VA、Bridge-VM）和 LIBERO（Spatial、Object、Goal、Long）。
  - **具身推理**：EgoPlan-Bench2（多步规划）、RoboVQA（长程推理）、OpenEQA（零样本具身理解）。

### 3.2 对比方法
- **操作任务**：Octo-Base、RT1-X、OpenVLA、DiT-Policy、TraceVLA、CoT-VLA、Magma。
- **推理任务**：GPT-4V、LLaVA-Video、InternVL2.5/3、NVILA、Qwen2.5-VL、Magma 等。

### 3.3 评价指标
- 操作任务：任务成功率（Success Rate）。
- 推理任务：多选题准确率（EgoPlan-Bench2）、BLEU 分数（RoboVQA）、LLM 评分（OpenEQA）。

## 4. 资源与算力
- **GPU**：16 块 NVIDIA A100（80GB 显存）。
- **训练时长**：冷启动 20K 迭代（batch size 32，lr 1e-5），GRPO 6K 迭代（batch size 64，rollout size 5），动作模型微调 120K 迭代（batch size 256），LIBERO 额外 75K 迭代（batch size 128）。
- **推理速度**：相比 OpenVLA，ThinkAct 增加 17% 的执行时间，但性能大幅提升。

## 5. 实验数量与充分性

- **操作任务**：在 SimplerEnv 的三种设置（Google-VM、Google-VA、Bridge-VM）和 LIBERO 的四个子任务上均进行了评估，共约 7 组实验。每组报告全局成功率。
- **推理任务**：三个基准（EgoPlan-Bench2、RoboVQA、OpenEQA），每个基准细分子类别，共 10+ 组实验。
- **消融实验**：在 SimplerEnv、EgoPlan-Bench2、RoboVQA 上分别测试了去掉轨迹奖励、去掉目标奖励、去掉两者、仅 SFT 冷启动等设置，共 4 组对比。
- **少样本适应实验**：在 LIBERO 三个子任务上使用 10 个 demo 微调，对比 OpenVLA、Magma。
- **定性分析**：提供了多组推理过程可视化及自我纠错案例。
- **充分性**：实验覆盖多领域、多姿态、多种对比方法，消融充分，结论可信。但未报告误差棒（仅在 LIBERO 上注明使用 3 个随机种子，每任务 500 次评估共 1500 次），部分基准可能缺少统计显著性检验。

## 6. 主要结论与发现

- ThinkAct 在 SimplerEnv 上均显著优于所有对比方法（例如 Google-VM 总体 71.5% vs 第二名 68.4%）。
- 在 LIBERO 上取得 84.4% 的总体成功率，优于 CoT-VLA 的 83.9% 和 DiT-Policy 的 76.8%。
- 在推理基准上，EgoPlan-Bench2 达到 48.2%（第二 45.7%），RoboVQA 达到 59.8 BLEU（第二 55.7），OpenEQA 达到 56.2%（第二 55.5）。
- 消融实验验证了目标奖励和轨迹奖励均有贡献，去除后性能下降；仅 SFT 冷启动最低，证明 RL 的重要性。
- 少样本适应实验显示 ThinkAct 在 10 个演示条件下显著优于 Magma 和 OpenVLA。
- 模型具备自我纠错能力：可通过观察视频片段检测失败并重新规划。
- 推理时间虽增加 17%，但带来的性能提升（尤其是长程任务）是值得的。

## 7. 优点

- **方法创新**：首次将强化学习（GRPO）与视觉潜在规划结合用于 VLA 推理，提出动作对齐的视觉奖励，紧密连接推理与执行。
- **双系统设计**：异步运行实现了慢思考与快控制，兼具灵活性和效率。
- **丰富实验验证**：横跨操作与推理两个领域，覆盖多种环境与任务，对比方法全面。
- **少样本适应能力**：10 个演示即可取得显著提升，实用性强。
- **自我纠错行为**：展示了推理驱动的失败检测与重新规划，是具身智能的关键能力。
- **代码与项目页面开放**：促进可复现性与后续研究。

## 8. 不足与局限

- **继承 MLLM 的局限性**：可能产生幻觉，如错误的对象属性或空间关系，影响下游执行。
- **奖励仅基于 2D 轨迹**：未包含接触力等信息，虽可扩展但当前版本未纳入。
- **推理速度增加**：虽然性能提升显著，但实时性可能受限，尤其在高频控制场景。
- **实验无误差棒**：仅提及 LIBERO 使用3种子，其他实验未报告方差，统计严谨性可加强。
- **训练资源大**：需要 16 块 A100 进行训练，对硬件要求较高。
- **泛化性验证有限**：主要在模拟环境中测试，真实机器人部署效果待验证。
- **消融实验仅覆盖主要成分**：未深入分析不同 backbone、不同交互步数 N 等超参数的影响（补充材料中提到，但正文未充分展示）。

（完）
