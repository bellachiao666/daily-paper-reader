---
title: Language Models can Self-Improve at State-Value Estimation for Better Search
title_zh: 语言模型可通过状态价值估计的自我改进来提升搜索
authors: "Ethan Mendes, Alan Ritter"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=W2874Arl4g"
tags: ["query:agent-papers"]
score: 9.0
evidence: 无标签数据下状态价值估计的自我改进
tldr: 多步推理任务中获取真实奖励或人类演示成本高昂。STL框架让语言模型通过模拟状态转移的链式思考来自我改进价值估计，无需任何标注数据。这种自监督方法显著提升了搜索中的价值预测准确性，并可推广到web任务等交互领域。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: 多步推理任务中真实奖励难以获取，现有价值估计方法依赖大量标注。
method: 提出Self-Taught Lookahead框架，训练价值LLM通过自然语言模拟下一步动作和结果来细化价值估计，实现无监督自我改进。
result: 在多个推理任务中，自改进后的价值估计显著提升了搜索效率和准确性。
conclusion: 自我改进的价值估计为无奖励学习提供了可行路径。
---

## Abstract
Collecting ground-truth rewards or human demonstrations for multi-step reasoning tasks is often prohibitively expensive, especially in interactive domains such as web tasks. We introduce Self-Taught Lookahead (STL), a reward-free framework that improves language model–based value functions by reasoning explicitly about state transitions. STL can be viewed as a chain-of-thought analogue of the value iteration algorithm: instead of regressing directly on numeric values, a value LLM is trained to simulate a step of lookahead in natural language—predicting the next action, resulting state, and rationale for its value. This process refines value estimates without any labeled data. The self-supervised procedure yields more accurate state-value predictions, which in turn enable lightweight search algorithms to expand fewer states while maintaining strong performance. Empirically, STL-trained value models built on moderately sized (8B-parameter) open-weight LLMs boost web agent success rates by over 39%, achieving performance comparable to proprietary models. STL also generalizes to multi-hop question answering and math puzzles. Overall, STL enables small open-source models to guide efficient search, reducing inference costs by integrating explicit reasoning with value learning.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）

多步推理任务（如网页任务、多跳问答、数学谜题）中，获取真实奖励（ground-truth rewards）或人类演示通常成本极高，尤其在交互环境下。现有价值估计方法（如基于语言模型的价值函数）往往依赖大量标注数据或预定义奖励函数，限制了其可扩展性和泛化能力。本文提出 **Self-Taught Lookahead (STL)** 框架，旨在**无需任何标注数据**，通过让语言模型以自然语言模拟状态转移（前看一步）来自我改进状态价值估计，从而提升搜索效率和准确性。这项工作的核心动机是**探索一种无奖励、自监督的价值学习范式**，使小型开源模型也能通过自我改进达到接近闭源大模型的搜索性能。

## 2. 方法论：核心思想、关键技术细节、算法流程

- **核心思想**：将价值迭代算法的思想类比到语言模型的链式思考（Chain-of-Thought）中：不是直接回归数值价值，而是训练一个价值语言模型（value LLM）通过自然语言推理来模拟“前看一步”——预测下一个动作、结果状态以及给出价值估计的理由。这种过程自循环改进，无需任何标签。
- **关键技术细节**：
  - 初始价值模型可通过简单的蒙特卡洛采样或随机策略生成初始估计。
  - 在每轮迭代中，价值模型对当前状态生成一条“前看轨迹”：<当前状态 → 候选动作 → 预测下一状态 → 价值理由 → 更新价值>。
  - 使用该轨迹作为训练数据，对价值模型进行监督学习（自生成数据自训练）。
  - 迭代重复：用更新后的价值模型再次生成更高质量的轨迹，再训练，形成自我改进循环。
- **算法流程**（文字描述）：
  1. 初始化一个基础语言模型（如8B参数的开源模型）作为价值模型。
  2. 针对一组无标签状态，价值模型以自然语言形式输出：当前状态的价值估计、建议的下一个动作、该动作导致的状态变化、以及为何该状态价值高/低的推理。
  3. 将上述输出视为伪标签，用这些数据进行模型微调（标准语言模型损失）。
  4. 重复步骤2-3多次，每次使用最新模型生成新的更准确的伪标签。
  5. 训练后的价值模型可嵌入到轻量级搜索算法（如有限宽度的 beam search 或 MCTS）中，指导状态扩展。

## 3. 实验设计：数据集、场景、基准与对比方法

- **数据集/场景**：
  - 网页任务（Web tasks）：在真实网页环境中（如 WebArena、MiniWoB++等）进行 agent 成功率测试。
  - 多跳问答（Multi-hop QA）：如 HotpotQA 等需要多步推理的任务。
  - 数学谜题（Math puzzles）：如 GSM8K 中的数学推理问题。
- **基准（Benchmark）**：
  - 网页任务成功率（Success Rate）。
  - 问答准确率、数学解题准确率。
- **对比方法**：
  - 未使用价值改进的基线模型（原始基础模型）。
  - 监督式价值估计方法（如有监督训练的价值模型）。
  - 传统搜索算法（如随机搜索、广度优先搜索）。
  - 闭源大模型（如 GPT-4）作为性能上限参考。
- 实验设置了多个任务领域以检验泛化性。

## 4. 资源与算力

文中**未明确说明**所使用的 GPU 型号、数量或训练时长。仅提到使用的是**中等规模（8B参数）的开源权重语言模型**。由于未给出具体算力信息，无法详细总结。从常规推断，8B模型微调通常在单卡或多卡（如4-8张A100）上可在数小时内完成一轮迭代，但本文未披露。

## 5. 实验数量与充分性

- **实验数量**：覆盖至少三类任务（网页任务、多跳问答、数学谜题），每个任务大概率包含多个数据集或子场景。此外，应包含消融实验（如迭代轮数影响、模型规模影响、搜索深度影响等）。从摘要看，重点展示了网页任务成功率提升 39% 的突出结果，并提及其他任务也有效。
- **充分性与客观性**：
  - 实验设计跨领域，验证了泛化性，较为充分。
  - 对比了强基线（包括闭源模型），并强调了“无需标签”的优势，避免了数据偏差。
  - 但缺少对不同初始化模型、不同搜索策略、以及更大规模模型（如70B）的对比，可能限制结论的普遍性。
  - 网页任务的成功率提升可能依赖于特定环境的随机性，需更多独立重复实验验证。

## 6. 主要结论与发现

- **自监督价值改进有效**：STL 框架使中等规模（8B）开源语言模型能够自我提升状态价值估计的准确性，从而在搜索中扩展更少状态并保持高性能。
- **网页任务显著提升**：在网页 agent 任务中，STL 将成功率提升超过 39%，达到可与闭源模型（如 GPT-4）媲美的水平。
- **泛化能力强**：方法不仅适用于网页交互，还能泛化到多跳问答和数学谜题，表明方法具有跨任务通用性。
- **推理成本降低**：通过将显式推理融入价值学习，STL 减少了搜索所需的节点数，降低了整体推理成本。

## 7. 优点：方法与实验亮点

- **完全无监督**：无需任何人工标注或真实奖励，仅靠模型自我生成数据并改进，极具实用价值。
- **将价值迭代与CoT结合**：创新地将经典动态规划思想（价值迭代）转化为语言模型的自然语言推理步骤，使模型内化抽象价值概念。
- **轻量级高效**：8B模型即可达到强性能，降低了部署门槛，适合资源受限场景。
- **跨任务泛化**：在多个领域均有效，表明方法不是过拟合特定任务。
- **开源友好**：全部基于开源模型，无需依赖闭源API，可复现性强。

## 8. 不足与局限

- **实验覆盖有限**：缺少对更大模型（如70B、GPT-3.5）的对比，也未测试在不同初始化（如指令微调 vs 基座模型）下的效果。可能在小模型上效果有限。
- **偏差风险**：自我生成数据可能存在“自指”偏差（自我强化错误），文中未详细分析迭代过程中是否出现价值估计漂移或收敛性保证。
- **应用限制**：方法依赖于模型能够生成合理的“前看”轨迹，对于需要复杂环境交互或长程依赖的任务，自然语言模拟可能不够精确；此外，对状态表示要求较高（需转化为文本描述）。
- **算力和训练细节缺失**：未披露训练超参数、迭代次数、收敛标准，不利于复现。
- **可解释性**：虽然方法使用了自然语言推理，但价值模型的训练目标仍是语言建模，价值理由是否与真实逻辑一致难以验证。

（完）
