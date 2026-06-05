---
title: "T1: Advancing Language Model Reasoning through Reinforcement Learning and Inference Scaling"
title_zh: T1：通过强化学习和推理缩放推进语言模型推理
authors: "Zhenyu Hou, Xin Lv, Rui Lu, Jiajie Zhang, Yujiang Li, Zijun Yao, Juanzi Li, Jie Tang, Yuxiao Dong"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=tnxONP8zTE"
tags: ["query:agent-papers"]
score: 7.0
evidence: 强化学习用于LLM推理中的自我探索和推理缩放
tldr: LLM在复杂推理中依赖模仿学习，测试时缩放效果差。本文提出T1，通过合成思维链数据初始化，利用强化学习和过采样促进探索，实现推理缩放。实验表明T1在开放LLM上表现出推理扩展性，为智能体通过RL自我改进提供新方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tnxonp8zte/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 681, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tnxonp8zte/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 857, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tnxonp8zte/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1746, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tnxonp8zte/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 741, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tnxonp8zte/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 738, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tnxonp8zte/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1765, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tnxonp8zte/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1761, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tnxonp8zte/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1135, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tnxonp8zte/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 549, \"height\": 411, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tnxonp8zte/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 916, \"height\": 751, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tnxonp8zte/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 832, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tnxonp8zte/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 829, \"height\": 265, \"label\": \"Table\"}]"
motivation: 现有LLM推理依赖模仿学习，测试时缩放困难，强化学习探索不足。
method: 使用合成思维链数据初始化模型，通过过采样增加多样性，结合强化学习进行缩放训练。
result: 在开放LLM上实现推理缩放，性能提升。
conclusion: 强化学习与推理缩放结合可促进LLM自我探索和改进。
---

## Abstract
Large language models (LLMs) have demonstrated remarkable capabilities in complex reasoning tasks. However, existing approaches mainly rely on imitation learning and struggle to achieve effective test-time scaling. While reinforcement learning (RL) holds promise for enabling self-exploration, recent attempts yield modest improvements in complex reasoning. In this paper, we present T1 to scale RL by encouraging exploration and understand inference scaling. We first initialize the LLM using synthesized chain-of-thought data that integrates trial-and-error and self-verification. To scale RL training, we promote increased sampling diversity through over-sampling. We demonstrate that T1 with open LLMs as its base exhibits inference scaling behavior and achieves superior performance on challenging math reasoning benchmarks. More importantly, we present a simple strategy to examine inference scaling, where increased inference budgets directly lead to T1’s better performance without any additional verification. The model weights and training data are publicly available at https://github.com/THUDM/T1.

---

## 论文详细总结（自动生成）

# 论文《T1: Advancing Language Model Reasoning through Reinforcement Learning and Inference Scaling》中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：大型语言模型在复杂推理任务中表现出色，但现有方法主要依赖模仿学习（如监督微调），难以实现有效的测试时扩展（test-time scaling）。强化学习（RL）有望让模型通过自我探索提升推理能力，但近期尝试在复杂推理中的改进仍有限。
- **核心问题**：如何通过强化学习实现推理能力的可扩展训练（training scaling），并使模型展现推理扩展（inference scaling）行为——即增加推理计算量直接带来性能提升，而无需依赖外部验证器。
- **整体含义**：本文提出T1框架，通过鼓励探索的RL训练策略，使开放LLM（如Qwen、GLM）具备推理扩展能力，在数学推理基准上取得显著性能提升，并揭示训练计算量与推理扩展之间的正相关关系。

## 2. 方法论

### 核心思想
- 通过初始化模型使其具备丰富的推理模式（包含试错、反思、验证），然后在RL训练中促进高多样性探索，同时施加适当惩罚以保持稳定，最终实现RL扩展和测试时扩展。

### 关键技术细节
1. **初始化策略（SFT阶段）**：
   - 使用合成思维链（CoT）数据微调初始模型，这些数据整合了试错（trial-and-error）和自我验证（self-verification）过程，不同于以往只关注正确步骤的方法。
   - 具体：对每个问题从多个LLM生成多个尝试答案，由LLM进行批评（识别错误原因、验证正确性），然后将这些尝试与批评整合成单一推理路径，并抽象重写为最终训练数据。

2. **RL训练中的探索鼓励**：
   - **过采样（Over-sampling）**：对每个提示采样K=64个响应（高温度τ>1），使用留一法（leave-one-out）归一化奖励。
   - **辅助熵奖励（Entropy Bonus）**：在损失中加入token级熵奖励，鼓励模型探索低概率token。
   - **在策略KL归一化（On-policy KL normalization）**：减去KL发散的平均值使奖励中心化，并采用指数移动平均（EMA）动态更新参考模型，避免固定参考限制优化。

3. **惩罚意外模式**：
   - 对重复、超长、乱码（混合语言、乱字符）等不良响应赋予负奖励-1，防止训练崩溃。

### 公式或算法流程（文字说明）
- 奖励函数：对每个响应，若检测到不良模式则r′ = -1，否则r′ = 原始奖励（正确为1，错误为0）。
- 优化目标：最大化期望奖励−β×KL正则化+α×熵奖励，其中KL使用归一化和EMA动态参考。
- 生成和优化交替进行：每轮对一批提示采样多个响应，计算奖励，更新策略。

## 3. 实验设计

### 数据集/场景与基准
- **数学推理基准**：
  - **MATH500**（摘自MATH测试集）
  - **AIME2024**（30道竞赛题）
  - **Omni-MATH-500**（从Omni-MATH中抽取500道）
  - **GPQA**（研究生级科学问题，作为领域外泛化测试）
- 所有评估使用Pass@1（准确率），对AIME进行32次采样取平均。

### 对比方法
- 基础模型：GLM-4-9B, Qwen2.5-14B, Qwen2.5-32B及其原始Chat/Instruct版本。
- 对比的强基线：GPT-4o、Claude-3.5-sonnet、Llama-3.3-70B-Instruct、o1-preview、QwQ-32B-preview、Qwen2.5-Math-7B-Instruct等。

## 4. 资源与算力

- 文中未明确说明使用的GPU型号、数量或训练时长。
- 训练细节：SFT训练3个epoch，学习率1e-5；RL训练使用1.5e-6学习率、KL=2e-4，每次更新基于32个prompt（每个采样64响应）。硬件资源未提及。

## 5. 实验数量与充分性

- **主要实验**：在4个数据集上对比了多个模型（表1），包含不同尺寸和基础模型。
- **消融实验**：
  - 采样数量K的影响（K=4,16,64）的对比（图3、图4、表2）。
  - 采样温度的影响（表2，温度0.9~1.3，及min-p）。
  - 惩罚机制的影响（表3，是否惩罚以及效果）。
- **推理扩展分析**：通过截断响应长度并评估，展示了不同RL训练步数下的推理扩展曲线（图7），并分析了推理模式（图8）。
- **充分性**：实验较为充分，覆盖了主要消融、参数影响和扩展行为验证。但缺乏对更大模型规模（如70B+）的实验，也未提供算力成本和训练时间的具体数据。

## 6. 主要结论与发现

1. **T1模型显著提升推理能力**：T1(Qwen2.5-32B)在MATH500上达到92.4%，超过QwQ-32B-preview（90.6%）；在AIME上达到50.6%，与o1-preview相当。
2. **RL扩展有效**：增加训练步数和采样数量（K=64）持续提高性能，且带来更好的奖励-KL权衡。
3. **推理扩展行为**：T1展现出随着推理token数增加而准确率上升的趋势，且RL训练步数越多，推理扩展越明显（从30%到100%步骤，AIME提升66%）。
4. **学习到反思和验证**：关键推理步骤包含“wait”、“perhaps”、“alternate”等词语，表明模型学会了自我纠正和探索不同方法。

## 7. 优点

- **方法创新**：通过合成CoT数据初始化模型，结合过采样、熵奖励、动态KL归一化，系统性地鼓励探索，解决了RL在复杂推理中扩展困难的问题。
- **推理扩展测量策略**：提出截断响应并用摘要模型生成答案的方法，来模拟不同推理预算并评估性能，该策略简单有效。
- **开源贡献**：公开模型权重和训练数据，促进社区研究。
- **泛化性**：在领域外（GPQA）也观察到性能提升，说明学习到的推理能力具有一定迁移性。

## 8. 不足与局限

- **未明确资源消耗**：未报告GPU型号、数量和训练时长，难以评估方法可复现性和成本。
- **模型规模局限**：最大模型为32B参数，未在更大模型（如70B/180B）上验证，可能影响结论的普适性。
- **任务范围有限**：主要聚焦数学推理，虽然GPQA显示泛化，但其他类型推理（如常识、逻辑、代码）未测试。
- **奖励信号依赖真实答案**：使用正确/错误作为奖励，可能限制更细粒度学习；且需要标注数据，对于没有标准答案的开放任务不适用。
- **推理扩展分析假设**：截断响应并用基模型摘要可能产生噪声，且假设越长的推理必然更好，实际可能包含冗余。
- **温度选择敏感**：高温度（>1.2）会导致性能下降，且低温度（≤1.0）训练容易崩溃，说明方法对超参数敏感。

（完）
