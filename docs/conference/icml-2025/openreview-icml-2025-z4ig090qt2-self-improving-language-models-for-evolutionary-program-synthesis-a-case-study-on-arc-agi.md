---
title: "Self-Improving Language Models for Evolutionary Program Synthesis: A Case Study on ARC-AGI"
title_zh: 自改进语言模型用于进化程序合成：基于ARC-AGI的案例研究
authors: "Julien Pourcel, Cédric Colas, Pierre-Yves Oudeyer"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=z4IG090qt2"
tags: ["query:agent-papers"]
score: 9.0
evidence: 基于LLM的递归自改进循环用于程序合成
tldr: 该论文提出SOAR方法，将大语言模型集成到自改进进化循环中。循环交替进行：1) 使用LLM采样和优化候选解的进化搜索；2) 将搜索经验转化为问题-解对并微调LLM，提升其采样和优化能力。在ARC-AGI任务上显著优于基线，展示了递归自改进在复杂任务中的威力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-z4ig090qt2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1748, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z4ig090qt2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 680, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z4ig090qt2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 692, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z4ig090qt2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 688, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z4ig090qt2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 725, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z4ig090qt2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 683, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z4ig090qt2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1061, \"height\": 723, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z4ig090qt2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1544, \"height\": 1757, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z4ig090qt2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1549, \"height\": 1748, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z4ig090qt2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1061, \"height\": 717, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-z4ig090qt2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 877, \"height\": 513, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z4ig090qt2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 615, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z4ig090qt2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 780, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z4ig090qt2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 830, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z4ig090qt2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 856, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z4ig090qt2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1868, \"height\": 892, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z4ig090qt2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 814, \"height\": 440, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z4ig090qt2/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1734, \"height\": 2378, \"label\": \"Table\"}]"
motivation: 复杂程序合成任务难以一次性求解，进化方法受限于固定生成模型能力。
method: 提出SOAR，结合进化搜索与LLM微调，构成自改进循环：搜索生成数据，数据微调模型。
result: 在ARC-AGI基准上，SOAR生成的程序正确率显著高于单次尝试或标准进化方法。
conclusion: 验证了LLM通过自进化循环可突破自身能力限制，适用于复杂程序合成。
---

## Abstract
Many program synthesis tasks prove too challenging for even state-of-the-art language models to solve in single attempts. Search-based evolutionary methods offer a promising alternative by exploring solution spaces iteratively, but their effectiveness remain limited by the fixed capabilities of the underlying generative model. 
We propose SOAR, a method that learns program synthesis by integrating language models into a self-improving evolutionary loop. 
SOAR alternates between (1) an evolutionary search that uses an LLM to sample and refine candidate solutions, and (2) a hindsight learning phase that converts search attempts into valid problem-solution pairs used to fine-tune the LLM's sampling and refinement capabilities—enabling increasingly effective search in subsequent iterations.
On the challenging ARC-AGI benchmark, SOAR achieves significant performance gains across model scales and iterations, leveraging positive transfer between the sampling and refinement finetuning tasks. These improvements carry over to test-time adaptation, enabling SOAR to solve 52\% of the public test set.

---

## 论文详细总结（自动生成）

# 中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：许多程序合成任务（如ARC-AGI）对当前最先进的大语言模型（LLM）来说仍然过于困难，单次尝试成功率极低。传统的基于搜索的进化方法虽然可以通过迭代探索解空间，但受限于底层生成模型的固定能力，性能很快遇到瓶颈。
- **研究动机**：希望构建一个能够**从自身搜索经验中学习**的系统，通过自我改进循环持续提升采样和精化程序的能力，从而突破固定模型能力带来的性能天花板。
- **整体含义**：本文提出SOAR（Self-improving Operators for Automated program Refinements），将LLM集成到**自改进进化循环**中，使得程序合成系统可以自主地从失败和成功中学习，逐步提升搜索效率，最终在极具挑战的抽象推理基准ARC-AGI上取得显著进展。

## 2. 方法论

### 核心思想
- SOAR交替进行两个阶段：**进化搜索阶段**（Sample&Refine）和**学习阶段**（Hindsight Learning + Fine-tuning）。
- 进化搜索阶段：用当前LLM采样初始候选程序，然后通过REX（基于Thompson采样的多臂老虎机）进行迭代精化（refinement），最后加权多数投票选出最终输出。
- 学习阶段：从搜索轨迹中提取训练数据，包括：
  - **采样能力提升**：利用**后见之明重标注**（Hindsight Relabeling）——即使程序对原任务失败，它对其自身产生的输出是正确的，从而构造新的（任务，程序）对，大幅扩充训练数据。
  - **精化能力提升**：收集成功的精化案例（错误程序→正确程序），按父程序准确率分层采样，保证多样性。
- 然后使用LoRA/QLoRA对**基础模型**进行微调，获得改进后的模型，用于下一轮搜索。

### 关键技术细节
- **搜索算法**：初始采样3k个程序；精化阶段使用REX（结合训练准确率和探索奖励），再执行3k次精化，总预算6k。
- **加权多数投票**：根据每个程序在训练示例上的准确率加权，合并产生最终输出。
- **自改进循环**：在训练任务上迭代4轮（收集所有模型和轮次的数据），然后在测试任务上进行最多2轮**测试时训练**（Test-time Training），仅利用测试任务的输入输出示例（无真值）微调采样能力。
- **微调方法**：使用Unsloth库，RS-LoRA（7B/14B）或RS-QLoRA（更大模型），LoRA rank=256，α=32，训练3个epoch，学习率5e-5，bfloat16精度。

### 算法流程（文字说明）
1. 初始化：基础LLM θ₀。
2. 迭代 i = 0,1,2,...：
   a. **搜索阶段**：使用θ_i对每个训练/测试任务执行Sample&Refine（6k预算），得到搜索轨迹。
   b. **学习阶段**：
      - 从轨迹中提取采样数据：后见之明重标注，贪婪-多样化子采样（每任务≤50个）。
      - 提取精化数据：成功精化案例，按父程序准确率分层采样（每任务≤50个）。
      - 对基础模型进行联合微调（同时学习采样和精化），得到θ_{i+1}。
3. 在训练任务上重复迭代以提升基础模型；然后在测试任务上进行测试时训练（仅优化采样模型）。

## 3. 实验设计

### 数据集/场景
- **ARC-AGI**（Abstraction and Reasoning Corpus）：包含400个训练任务和400个测试任务。每个任务由2-10个输入-输出网格对组成，需要推断出隐含的变换规则，并应用于测试输入。
- 主要评估**ARC-test**（测试集）上的解决率。

### Benchmark
- 对比方法包括：
  - **单次尝试（1-shot）**：直接让LLM生成程序，包括开源模型（Qwen-2.5-Coder系列、Mistral-Large-2）和闭源模型（GPT-4.1、Claude-4-Sonnet、Gemini-2.5-Pro、o3-mini）。
  - **纯搜索方法**：仅采样6k（Sample-6k）或Sample&Refine-6k（无微调）。
  - **先前的归纳方法**：CodeIt (Butt et al., 2024), BARC-induction (Li et al., 2024), Icecuber (Wind, 2020), Greenblatt (2024)。
- SOAR最终结果与上述方法对比，并报告**所有模型集成**后的性能。

### 对比方法
- 按模型规模：7B, 14B, 32B (Qwen-2.5-Coder系列)，72B (Qwen-2.5)，123B (Mistral-Large-2407)。
- 不同精化数据选择策略（uniform, greedy, greedy-diverse等）的消融。
- 联合微调 vs. 单独微调采样/精化的对比。

## 4. 资源与算力

- 论文明确说明：**单块H100 GPU**上使用RS-LoRA/RS-QLoRA进行微调。
- 具体训练参数：LoRA rank=256, α=32, 3 epoch, 学习率5e-5, 梯度累积64步, batch size=1。
- 推理使用SGLang引擎，每任务并行采样50个完成。
- **未给出精确的GPU总时长**，但指出微调成本相对于搜索成本很低（约占总FLOPs的5%）。在附录B中给出了FLOPs分析：微调FLOPs ≈ 6N × (100·T)，搜索FLOPs ≈ 2N × (6000·T·n)，因此微调占比很小。
- 总共对5个模型大小（7B/14B/32B/72B/123B）进行了4轮训练迭代和2轮测试时训练，每轮每个任务6k搜索，工作量较大但合理。

## 5. 实验数量与充分性

- **消融实验充分**：
  - 对比了四种采样数据选择策略（correct-only, uniform, greedy, greedy-diverse），确认greedy-diverse最优。
  - 对比了两种精化数据选择策略（uniform vs. diverse），后续均采用diverse。
  - 对比了联合微调 vs. 分别微调采样/精化模型，确认联合微调效果更好。
  - 对比了是否使用后见之明重标注。
  - 在多个模型规模（7B/14B/32B/72B/123B）上一致验证。
- **公平性**：所有搜索方法均使用相同预算（6k），公平对比；闭源模型由于预算原因未运行搜索，但其单次尝试结果已列出。SOAR与先前归纳方法对比时标注了是否使用人类数据或闭源LLM，透明度高。
- **统计充分性**：结果基于400个测试任务，且多次迭代，报告了平均分数。未见多次随机运行的标准差，但搜索本身具有随机性，可能进行了单次运行。
- **整体充分**：覆盖了从1-shot到搜索再到自改进的全范围，消融实验全面，验证了各个设计选择的有效性。

## 6. 主要结论与发现

1. **单次尝试远不足**：即使Claude-4-Sonnet也只达到20.75%的准确率，开源模型仅1-2%。
2. **搜索显著提升性能**：Sample&Refine-6k使开源模型达到14-26%，甚至超过闭源非推理模型。
3. **自改进打破平台期**：通过迭代训练，SOAR在ARC-train上额外解决20-27%的任务（不同模型大小），在ARC-test上最终达到52%（所有模型集成）。
4. **联合微采样与精化具有正迁移**：同时学习两者比单独学习更好（ARC-train 44.42% vs 43.88%）。
5. **测试时训练有效**：在测试任务上额外进行2轮训练，进一步提升5%左右。
6. **跨模型互补**：集成所有模型的结果（52%）显著优于任何单个模型（最高45.5%），表明不同规模模型发现的程序具有多样性。
7. **模型大小与搜索预算的缩放曲线被抬高**：固定搜索预算下，随着模型增大性能趋于饱和；SOAR通过改善模型自身持续提升缩放曲线。

## 7. 优点

- **完全自主**：不需要任何人类编写的领域特定语言、人类解决方案或外部数据集，全部从自身搜索经验中学习。
- **后见之明重标注**：有效利用失败搜索数据，大幅增加训练样本。
- **兼顾采样与精化**：同时学习两种能力，相互促进。
- **测试时适应**：在目标任务上无需真值即可继续改进，实用性强。
- **跨模型集成**：发现了不同模型间的互补性，集成性能显著提升。
- **公开可复现**：使用开源模型和开源代码（GitHub），便于后续研究。
- **详细消融**：通过大量消实验证实每个设计选择的有效性。

## 8. 不足与局限

- **计算成本**：虽然微调成本低，但搜索阶段每任务6k次生成，在多轮迭代下总代价仍然很高（尤其对更大模型）。论文未提供精确的GPU小时数。
- **实验重复性**：未报告多次运行的误差或标准差，可能单次运行结果存在波动。
- **仅评估ARC**：方法理论上通用，但仅在一个基准上验证，泛化性尚未证明。
- **多样性下降**：随着迭代，解空间多样性降低（对已解决问题），可能限制持续改进。论文提出通过质量-多样性方法或生成新问题来缓解，是目前局限。
- **测试时训练仅改进采样**：未探索精化模型的测试时训练，留下改进空间。
- **集成策略简单**：加权多数投票并非最优，有约9.5%的差距（与oracle相比），可通过更先进的集成方法进一步缩小。
- **可能引入偏置**：后见之明重标注可能使模型偏向于简单、局部解，影响泛化。

（完）
