---
title: "Collaborative Reasoner: Self-Improving Social Agents with Synthetic Conversations"
title_zh: 协作推理者：通过合成对话实现自改进社交智能体
authors: "Ansong Ni, Ruta Desai, Yang Li, Xinjie Lei, Dong Wang, Jiemin Zhang, Jane Yu, Ramya Raghavendra, Gargi Ghosh, Shang-Wen Li, Asli Celikyilmaz"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=dye9w8IOV0"
tags: ["query:agent-papers"]
score: 8.0
evidence: 通过合成对话提升多智能体协作推理能力
tldr: 当前LLM在多智能体协作场景中缺乏有效的说服、断言等协作技能。本文提出Collaborative Reasoner（Coral）框架，通过生成合成对话训练智能体，使其在协作推理任务中学会提出异议、说服伙伴等行为。实验表明，Coral显著提升了多智能体系统的协作推理成功率，为构建能够与人类和其他AI无缝协作的智能体提供了新范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-dye9w8iov0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1464, \"height\": 643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dye9w8iov0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1426, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dye9w8iov0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1432, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dye9w8iov0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 867, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dye9w8iov0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 573, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dye9w8iov0/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1150, \"height\": 703, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dye9w8iov0/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1213, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dye9w8iov0/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1421, \"height\": 550, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-dye9w8iov0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1309, \"height\": 452, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dye9w8iov0/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1323, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dye9w8iov0/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 637, \"height\": 396, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dye9w8iov0/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1341, \"height\": 597, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dye9w8iov0/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 782, \"height\": 418, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dye9w8iov0/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1238, \"height\": 378, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dye9w8iov0/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1453, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dye9w8iov0/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1280, \"height\": 176, \"label\": \"Table\"}]"
motivation: LLM智能体在协作场景中缺乏说服、异议等关键协作技能，而现有训练多关注单轮交互。
method: 提出Coral框架，利用合成对话数据训练智能体，使其学会在协作推理中有效互动。
result: Coral训练后的智能体在协作推理任务中表现出更高的成功率和更自然的社交行为。
conclusion: 合成对话是一种有效的自改进方法，可赋予LLM智能体协作社交技能。
---

## Abstract
With increasingly powerful large language models (LLMs) and LLM-based agents tackling an ever-growing list of tasks, we envision a future where numerous LLM agents work seamlessly with other AI agents and humans to solve complex problems and enhance daily life. To achieve these goals, LLM agents must develop collaborative skills such as effective persuasion, assertion and disagreement, which are often overlooked in the prevalent single-turn training and evaluation of LLMs. In this work, we present Collaborative Reasoner (Coral), a framework to evaluate and improve the collaborative reasoning abilities of language models. In particular, tasks and metrics in Coral necessitate agents to disagree with incorrect solutions, convince their partners of a correct solution, and ultimately agree as a team to commit to a final solution, all through a natural multi-turn conversation. Through comprehensive evaluation on six collaborative reasoning tasks covering domains of coding, math, scientific QA and social reasoning, we show that current models cannot effectively collaborate due to undesirable social behaviors, collapsing even on problems that they can solve singlehandedly. To improve the collaborative reasoning capabilities of LLMs, we propose a self-play method to generate synthetic multi-turn preference data and further train the language models to be better collaborators. Experiments with Llama-3.1, Ministral and Qwen-2.5 models show that our proposed self-improvement approach consistently outperforms finetuned chain-of-thought performance of the same base model, yielding gains up to 16.7% absolute. Human evaluations show that the models exhibit more effective disagreement and produce more natural conversations after training on our synthetic interaction data.

---

## 论文详细总结（自动生成）

# 论文《Collaborative Reasoner: Self-Improving Social Agents with Synthetic Conversations》详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：当前大型语言模型（LLM）和基于LLM的智能体在单轮问答或问题求解任务上表现出色，但在多轮自然语言对话的 **协作推理** 场景中，缺乏关键的社交技能，如有效说服、坚持正确观点（断言）、提出异议等。现有训练和评估多聚焦于单轮交互，忽略了多智能体/人机协作所需的社交能力。
- **整体含义**：为实现未来AI智能体与人类及其他AI的无缝协作，必须开发具备协作推理能力的通用智能体。论文提出 **Coral** 框架，用于评估和提升LLM的协作推理能力，并通过合成对话数据进行自我改进，使模型学会在对话中提出异议、说服伙伴、达成一致。
- **背景**：多智能体系统虽有研究（如角色分工、辩论结构），但缺乏通用、自由形式的对话协作训练方法，且高质量协作数据匮乏。论文填补了这一空白。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 通过 **自对弈（self-play）** 生成合成多轮对话数据，并利用偏好学习（DPO）训练LLM，使其在协作推理中表现出更有效的社交行为（断言、说服、异议），提升团队最终答案的正确率。

### 关键技术细节
- **Coral 框架**：
  - 两个智能体A和B就一个推理问题进行多轮对话（最多20轮），需在对话中达成一致并给出最终答案。
  - **信念提取**：使用LLM-as-judge在每个回合后提取智能体对最终答案的信念（belief），判断其正确性。
  - **对话级指标**：一致性（agreement）和一致性正确率（agreement correctness，主指标）。
  - **回合级社交指标**：说服力（persuasiveness：一方改变另一方的信念）和断言力（assertiveness：坚持自身信念不受影响）。
- **自我改进流水线**（图2）：
  1. **树采样（Tree Sampling）**：每轮对话采样d个候选回复（d=5），独立构建5棵对话树，增加多样性。
  2. **信念过滤（Belief Filtering）**：根据信念与标准答案是否匹配，将每个回合标注为正/负样本，生成偏好对。
  3. **偏好微调（Preference Finetuning）**：使用DPO算法，以正确/错误回复作为对比信号进行训练。
- **Matrix 基础设施**：为支持大规模合成对话生成，构建了可扩展的模型服务框架，集成vLLM、SGLang、Ray、Slurm等，支持数百模型并行、自动缩放、gRPC通信，吞吐量较llm-swarm提升最高1.87倍。

## 3. 实验设计：数据集、基准、对比方法

### 数据集（6个推理任务）
- **MATH**（数学）、**MMLU-Pro**（通用知识）、**GPQA**（研究生级科学QA）、**ExploreToM** / **Hi-ToM**（心智理论推理）、**MBPP-CR**（代码正确性推理，由MBPP改编为二分类）。
- 每个数据集划分训练/测试集，GPQA和Hi-ToM仅用于评估泛化能力。

### 基准（Baselines）
- **单智能体方法**：CoT（思维链）、CoT+SFT（拒绝采样后监督微调）、CoT+DPO（单层树采样偏好微调）。
- **多智能体方法**：Coral、Coral+SFT（正确信念回合监督微调）、Coral+DPO（论文主要方法）。
- **强推理模型对比**：GPT-4o、O1、Gemini-1.5/2.5、Claude-3.7、Llama-3.1-405B等。

### 模型
- 开放模型：Llama-3.1-8B/70B-Instruct、Qwen-2.5-7B-Instruct、Ministral-8B-Instruct。
- 闭源模型：GPT-4o、O1、Gemini系列、Claude-3.7。

### 实验设置
- 每个问题最多20轮对话；树采样d=5，5棵树，每问题最多20个偏好对。
- 训练超参数：SFT/DPO训练1000-3000步，批大小20-50，序列长度8192。

## 4. 资源与算力
- **硬件**：所有实验在AWS p5.48xlarge实例上运行，每个实例配备8×H100 80GiB GPU。
- **训练细节**：使用fairseq2和TRL库进行全参数微调。未明确给出总GPU小时数或具体训练时长，但提及单个实例可运行1000-3000步，批大小20-50。
- **数据生成**：通过Matrix并行生成，规模达数万至数十万回合（表9：例如MMLU-Pro生成160.6k回合）。

## 5. 实验数量与充分性
- **实验数量**：论文进行了大量实验：
  - 在6个任务上对8个不同模型进行主实验（表1、图3、表2）。
  - 与强推理模型对比（图4）。
  - 交叉协作泛化实验（表3）：将训练后的模型与4种不同伙伴模型配对。
  - 不对称协作实验（表5）：训练前与训练后模型配对。
  - 跨数据集泛化实验（表4）：MMLU-Pro→GPQA，ExploreToM→Hi-ToM。
  - CoT与Coral互相评估（表6）。
  - 人类评估（图5）：100个例子，每例3名标注者，评价有效异议、自然度等。
  - 社交指标分析（表7）。
- **充分性**：实验覆盖多领域、多模型、多基线，包含消融、泛化、人类评估，设计全面且公平（对比方法一致、资源相同）。实验结论一致，统计稳定（方差约1%）。因此实验设计充分且客观。

## 6. 论文的主要结论与发现
1. **当前LLM不擅长协作推理**：在Coral设定下，多数模型（包括O1、Gemini）无法一致超越单智能体CoT表现，甚至因社交行为不当（过度顺从、缺乏断言）而在自己能解决的任务上失败。
2. **自我改进方法显著提升协作能力**：Coral + DPO在所有模型和任务上持续优于CoT基线（包括CoT+SFT/DPO），最大绝对提升16.7%。训练后的70B模型在MMLU-Pro和ExploreToM上可媲美O1、Gemini-Pro。
3. **泛化能力强**：训练后的协作推理器能推广到不同伙伴模型（平均提升4.9%~32.2%）和同领域不同数据集（如MMLU-Pro→GPQA提升5.2%~9.2%）。
4. **社交行为改善**：人类评估表明，训练后模型表现出更有效的异议、更自然的对话，但伴随便利性增加（更冗长）。
5. **Coral训练也提升单智能体CoT能力**：Coral DPO训练后，模型在单轮CoT评估中也有提升（表6），说明其同时增强了推理逻辑。

## 7. 优点
- **框架新颖完整**：首次系统定义并评估多轮对话中的协作推理社交指标（断言、说服、异议），并设计自改进流程。
- **数据可扩展**：通过合成对话的树采样和信念过滤，无需人工标注即可生成大规模高质量偏好数据。
- **基础设施先进**：Matrix框架支持大规模并行生成，解决了多智能体数据生成的工程瓶颈，并开源。
- **实验全面严谨**：覆盖多模型、多领域、多基线，包含大量消融、泛化和人类评估，结论可靠。
- **实际效果显著**：协作性能提升幅度大，且训练后的模型可跨伙伴、跨数据集泛化，实用价值高。

## 8. 不足与局限
- **信念提取不完美**：依赖LLM-as-judge提取信念，对长上下文或强推理模型（如O1）表现不稳定，可能引入噪声。
- **生成任务测量困难**：当前方法仅适用于答案简短的任务（如分类、选择题），对代码生成等语义复杂任务的一致性测量需进一步探索。
- **学习信号过于二值**：仅根据回合信念是否匹配最终答案进行正/负标注，缺乏过程监督，可能鼓励“版本化”协作而非逐步推理。
- **模型仍过于礼貌和冗长**：人类评估显示训练后对话更自然但更冗长，可能影响效率；过度顺从问题虽有改善但未完全解决。
- **计算成本高于CoT**：因对话历史变长，平均提示长度比CoT长89%，训练和推理计算量更大。
- **局限性附录提及**：未进行蒙特卡洛回滚估算中间信念的进步；协作仅限AI-AI，未扩展到人类-AI交互（但已展望未来工作）。

（完）
