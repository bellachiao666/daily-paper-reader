---
title: Does Reinforcement Learning Really Incentivize Reasoning Capacity in LLMs Beyond the Base Model?
title_zh: 强化学习真的能激励LLM超越基础模型的推理能力吗？
authors: "Yang Yue, Zhiqi Chen, Rui Lu, Andrew Zhao, Zhaokai Wang, Yang Yue, Shiji Song, Gao Huang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=4OsgYD7em5"
tags: ["query:agent-papers"]
score: 5.0
evidence: 批判性考察RLVR对LLM推理的作用，质疑自改进假设
tldr: 该论文系统考察了带可验证奖励的强化学习（RLVR）是否真的赋予LLM超越基础模型的推理能力。通过多个模型系列、RL算法和推理基准的对比实验，发现RLVR的性能提升主要源于对训练分布内模式的记忆，而非真正的泛化。这挑战了RL使智能体自改进的假设，提示需要更谨慎看待当前RLVR的实际效果。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1429, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1321, \"height\": 1248, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 448, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 537, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 667, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 356, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1378, \"height\": 802, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 815, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1394, \"height\": 721, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 888, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1095, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 481, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1461, \"height\": 1716, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 795, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1372, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1251, \"height\": 803, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1281, \"height\": 899, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1165, \"height\": 1959, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1000, \"height\": 973, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4osgyd7em5/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 985, \"height\": 346, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-4osgyd7em5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1414, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4osgyd7em5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 610, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4osgyd7em5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1156, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4osgyd7em5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1152, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4osgyd7em5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1305, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4osgyd7em5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1014, \"height\": 212, \"label\": \"Table\"}]"
motivation: 当前RLVR被广泛用于提升LLM推理能力，但其是否真正带来超越基础模型的新能力尚不明确。
method: 系统对比多种模型、RL算法和推理基准，测试RLVR训练后LLM的推理边界。
result: RLVR的提升主要来自记住训练模式，在分布外推理上提升有限。
conclusion: 对RLVR的自我改进假设提出质疑，提示未来研究需关注泛化能力。
---

## Abstract
Reinforcement Learning with Verifiable Rewards (RLVR) has recently demonstrated notable success in enhancing the reasoning performance of large language models (LLMs), particularly in mathematics and programming tasks. 
It is widely believed that, similar to how traditional RL helps agents to explore and learn new strategies, RLVR enables LLMs to continuously self-improve, thus acquiring novel reasoning abilities that exceed the capacity of the corresponding base models. 
In this study, we take a critical look at \textit{the current state of RLVR} by systematically probing the reasoning capability boundaries of RLVR-trained LLMs across diverse model families, RL algorithms, and math/coding/visual reasoning benchmarks, using pass@\textit{k} at large \textit{k} values as the evaluation metric.
While RLVR improves sampling efficiency towards the correct path, we surprisingly find that current training does \emph{not} elicit fundamentally new reasoning patterns.
We observe that while RLVR-trained models outperform their base models at smaller values of $k$ (\eg, $k$=1), base models achieve higher pass@$k$ score when $k$ is large.
Moreover, we observe that the reasoning capability boundary of LLMs often narrows as RLVR training progresses.
Further coverage and perplexity analysis shows that the reasoning paths generated by RLVR models are already included in the base models' sampling distribution, suggesting that their reasoning abilities originate from and are \textit{bounded} by the base model. 
From this perspective, treating the base model as an upper bound, our quantitative analysis shows that six popular RLVR algorithms perform similarly and remain far from optimal in fully leveraging the potential of the base model.
In contrast, we find that distillation can introduce new reasoning patterns from the teacher and genuinely expand the model’s reasoning capabilities.
Taken together, our findings suggest that current RLVR methods have not fully realized the potential of RL to elicit genuinely novel reasoning abilities in LLMs. This underscores the need for improved RL paradigms—such as continual scaling and multi-turn agent-environment interaction—to unlock this potential.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义
- 研究背景：强化学习与可验证奖励（RLVR）被广泛用于提升大型语言模型（LLM）在数学、编程等任务中的推理能力，主流观点认为其能类似传统RL那样让模型自主探索并习得全新的推理策略（如枚举、自我反思等）。
- 核心问题：当前RLVR是否真的赋予了LLM超越其基础模型的全新推理能力？还是仅仅利用了基础模型中已存在的推理模式，通过提高采样效率来提升平均表现？
- 整体含义：对RLVR“自改进”假设提出系统性挑战，强调需要更谨慎地看待现有RLVR的实际效果，并为未来RL范式（如持续扩展、多轮交互）提供了方向。

## 2. 方法论
- **核心思想**：通过`pass@k`（在`k`次采样中至少一次正确即为可解）评估模型的推理边界，以此严格检验RLVR是否扩展了模型能解决的问题集合。如果RLVR赋予新能力，则RLVR模型应在更大的`k`下解决更多基础模型无法解决的问题。
- **关键技术细节**：
  - 采用无偏低方差估计器计算`pass@k`。
  - 对比基础模型（Base）与RLVR模型（RL）的`pass@k`曲线（从`k=1`到`k=1024`）。
  - 准确率分布分析（Accuracy Histogram）、可解问题覆盖分析（Solvable-Problem Coverage）、困惑度分析（Perplexity Analysis）——验证RLVR生成的推理路径是否已存在于基础模型的输出分布中。
  - 定义了**采样效率差距∆SE** = RL模型的`pass@1` – 基础模型的`pass@k`（`k=256`作为上限代理），量化RL算法逼近最优的效率。
  - 对比蒸馏（Distillation）与RLVR：蒸馏从更强教师模型中引入新推理模式，可真正扩展推理边界。
- **算法流程**：使用策略梯度类方法（PPO、GRPO、Reinforce++、RLOO、ReMax、DAPO），在可验证奖励（二进制0/1）上最大化期望奖励。采用Zero-RL设置（直接对预训练基础模型进行RL，无SFT），但代码和视觉推理任务因稳定性原因使用指令微调模型作为起点。

## 3. 实验设计
- **数据集与基准（Benchmark）**：
  - **数学推理**：GSM8K、MATH500、Minerva、Olympiad、AIME24、AMC23。
  - **代码生成**：LiveCodeBench（v5，含279个问题）、HumanEval+、MBPP+。
  - **视觉推理**：MathVista-TestMini、MathVision-TestMini（移除多选题）。
- **模型家族**：
  - 数学：Qwen2.5（7B/14B/32B Base）、LLaMA-3.1-8B；Oat-Zero-7B、DAPO-32B。
  - 代码：Qwen2.5-7B-Instruct-1M、DeepSeek-R1-Distill-Qwen-14B（作为CodeR1和DeepCoder基础）。
  - 视觉：Qwen2.5-VL-7B。
  - 大规模验证：Magistral-Medium（基于Mistral-Medium-3，约前沿推理模型）。
- **对比方法**：
  - 基础模型（Base） vs RLVR训练模型（RL）。
  - 不同RL算法：PPO、GRPO、Reinforce++、RLOO、ReMax、DAPO（使用VeRL框架统一实现）。
  - 蒸馏模型（DeepSeek-R1-Distill-Qwen-7B）。
  - 消融实验：KL损失、rollout数量（n=8 vs n=32）、温度调节、训练步数影响。
- **评估协议**：统一采样温度0.6，top-p 0.95，最大生成长度16384 tokens；基础模型使用与RL模型相同的zero-shot prompt，避免few-shot干扰。

## 4. 资源与算力
- 文中未明确列出GPU型号、数量及总训练时长。仅在实验描述中提到使用了VeRL框架，训练设置：AdamW优化器，恒定学习率1e-6，prompt batch size 256，每个prompt采样8个响应（rollout n=8），最大rollout长度8192 tokens，采样温度1.0。对于n=32的实验，因计算资源限制仅训练了220步。
- 对于大规模模型（如Magistral-Medium），通过API查询，最大上下文长度40k。

## 5. 实验数量与充分性
- **实验数量**：覆盖3大任务领域（数学、代码、视觉），多种模型尺寸（7B至32B），6种RL算法，多个基准（共约10+个数据集），以及大量消融实验（KL、rollout数、温度、训练步数等）。
- **充分性**：
  - 系统性：实验设计对比全面，包括in-domain和out-of-domain测试（如Omni-MATH训练/测试、MATH500）。
  - 客观性：手动检查CoT有效性（在GSM8K、AIME24、MathVista中验证低准确率问题的正确推理路径存在性），排除随机猜测干扰；使用相同prompt和温度避免偏差。
  - 公平性：基础模型不使用few-shot，RLVR模型使用其原始训练prompt，两者在同一起跑线评估。
  - 局限性：部分实验因计算资源仅训练较短步数（如n=32时220步），可能未收敛；未对真正的超大规模RLVR（如DeepSeek-R1-Zero）进行pass@k评估（因API限制）；未包含多轮交互RL场景。

## 6. 主要结论与发现
1. **RLVR不扩展推理边界，反而收缩**：在`pass@k`曲线上，小`k`时RLVR优于基础模型（提升采样效率），但大`k`时基础模型反超，说明RLVR模型可解问题集是基础模型的子集，且训练后覆盖范围缩小。
2. **推理路径已存在于基础模型**：准确率分布显示RLVR提高了已可解问题的采样概率，但未新增可解问题；困惑度分析表明RLVR生成路径的困惑度落在基础模型高概率区域内，即所有RLVR路径都包含在基础模型分布中。
3. **不同RL算法表现相似且远离最优**：∆SE（采样效率差距）均在约40-42之间，远未达到充分利用基础模型潜能的上限。
4. **蒸馏与RLVR本质不同**：蒸馏从强教师中引入新推理模式，可真正扩展推理边界，而RLVR受限于基础模型。
5. **训练负效应**：随着RLVR训练步数增加，`pass@1`上升但`pass@256`下降，推理边界持续收窄。
6. **规模扩展到前沿模型仍成立**：对Magistral-Medium（接近o1级别）的初步实验显示类似趋势，说明结论在更大/更强模型下依然成立。

## 7. 优点
- **方法论创新**：采用`pass@k`大`k`值评估推理边界，替代了仅依赖平均准确率的传统做法，更全面地揭示模型潜力。
- **系统性与多维度验证**：跨模型家族、任务领域、RL算法进行严格对比，并结合准确率分布、覆盖分析、困惑度分析，提供了坚实的实证证据。
- **公平的实验设计**：统一评估协议，排除few-shot干扰，手动验证CoT有效性，排除随机猜测，确保结论可靠。
- **清晰的概念区分**：明确区分“提升采样效率”与“扩展推理能力”，并指出蒸馏与RLVR的本质差异，为后续研究提供了理论框架。

## 8. 不足与局限
- **计算资源限制**：未对最先进的大规模RLVR模型（如DeepSeek-R1-Zero、GPT-o1）进行充分的`pass@k`评估（base不可访问或API吞吐限制），限制了结论的普适性。
- **训练规模不足**：部分消融实验（如n=32）因算力仅训练220步，可能未充分展现RLVR在大规模计算下的潜力，未来仍需探索持续扩展能否最终超越base。
- **仅考虑单轮交互**：当前RLVR框架局限于单回合回应，缺乏多轮代理-环境交互，而传统RL的探索能力在多轮场景中更发挥优势。论文未测试多轮RL设置。
- **视觉任务验证较弱**：视觉推理仅在两个过滤后的mini测试集上进行，未覆盖更多模态任务。
- **手动检查局限性**：尽管手动验证了CoT，但样本量有限，且对于极难问题仍存在模糊情况（如跳过推理步骤的答案）。
- **随机猜测风险无法完全排除**：尽管通过过滤和手动检查尽力排除，但理论上大`k`下基础模型仍可能因随机猜测得到正确答案，但论文已通过合理方法（如过滤可猜测问题）减轻该偏差。

（完）
