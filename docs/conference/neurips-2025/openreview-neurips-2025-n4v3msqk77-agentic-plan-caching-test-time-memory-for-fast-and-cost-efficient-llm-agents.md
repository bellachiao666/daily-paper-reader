---
title: "Agentic Plan Caching: Test-Time Memory for Fast and Cost-Efficient LLM Agents"
title_zh: 代理计划缓存：面向快速且经济的LLM代理的测试时记忆
authors: "Qizheng Zhang, Michael Wornow, Kunle Olukotun"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=n4V3MSqK77"
tags: ["query:agent-papers"]
score: 4.0
evidence: LLM代理的缓存机制，涉及代理效率
tldr: 该论文提出代理计划缓存（APC），一种测试时记忆方法，通过提取、存储和复用计划模板来降低LLM代理在复杂任务中的规划成本和延迟。虽然不直接涉及自改进，但作为提升代理效率的技术，与复杂任务中的代理主题相关。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: 现有缓存技术不适用于依赖外部上下文的代理应用，导致高昂成本和延迟。
method: 提出Agentic Plan Caching，从代理规划阶段提取结构化计划模板并在语义相似任务间复用。
result: 在保持性能的同时显著降低成本和延迟。
conclusion: APC作为测试时记忆，有效提升LLM代理的经济性，可支持复杂任务的持续执行。
---

## Abstract
LLM-based agent applications have shown increasingly remarkable capabilities in complex workflows but incur substantial costs and latency due to extensive planning and reasoning requirements. 
Existing LLM caching techniques (like context caching and semantic caching), primarily designed for serving chatbots, are insufficient for agent applications where outputs depend on external data and environmental contexts. 
We propose **Agentic Plan Caching (APC)**, a novel **test-time memory** that extracts, stores, adapts, and reuses structured plan templates from planning stages of agent applications across semantically similar tasks to reduce the cost and latency of serving. 
Unlike traditional semantic caching, our system extracts plan templates from completed agent executions at test-time, employs keyword extraction to match new requests against cached plans, and utilizes lightweight models to adapt these templates to task-specific plans with contexts. 
Evaluation across multiple real-world agent applications shows that our system can reduce costs by 50.31\% and latency by 27.28\% on average while maintaining performance, offering a more efficient solution for serving LLM-based agents that complements existing LLM serving infrastructures.

---

## 论文详细总结（自动生成）

# 论文《Agentic Plan Caching: Test-Time Memory for Fast and Cost-Efficient LLM Agents》中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：基于大语言模型（LLM）的代理应用（如数据密集型推理、网页导航等）通常采用“计划-行动”（Plan-Act）两阶段流水线，执行复杂工作流时需要大量规划和推理，导致高昂的成本和延迟。
- **现有缓存不足**：传统的上下文缓存和语义缓存主要针对聊天机器人设计，无法有效处理代理应用中输出依赖外部数据或动态环境的情况（即数据依赖输出）。它们缺乏对任务级意图的捕捉，难以复用跨语义相似任务的计划。
- **动机**：需要一种新的缓存机制，从已完成代理执行的计划阶段提取、存储、适配和重用结构化计划模板，以降低LLM代理的推理成本，同时保持性能。

## 2. 方法论：核心思想、技术细节与算法流程
- **核心思想**：提出**Agentic Plan Caching (APC)**，一种测试时记忆，将缓存粒度从查询级（适合聊天机器人）提升到任务级（针对LLM代理）。核心洞察是：大多数计算成本发生在计划阶段，且同一意图的任务往往产生相似的计划结构，可以复用。
- **关键技术细节**：
  - **关键词提取**：使用轻量级模型（如GPT-4o-mini）从输入查询中提取描述高层意图的关键词。
  - **缓存存储**：缓存中存储 (关键词, 计划模板) 对。计划模板通过两步生成：规则过滤（去除冗长推理步骤）和轻量LLM过滤（移除上下文特定信息，如公司名、数值）。
  - **缓存命中处理**：命中时，用小模型（如LLaMa-3.1-8B）根据检索到的计划模板和当前上下文适配生成具体计划，然后由演员LM执行。
  - **缓存未命中处理**：未命中时，用大模型（如GPT-4o）从头生成计划；执行成功后，从执行日志中提取计划模板并加入缓存。
- **算法流程**（文字说明）：
  1. 输入查询，提取关键词。
  2. 在缓存中精确匹配关键词。
  3. 若命中：用小LM适配模板 → 演员LM执行 → 小LM判断是否完成 → 输出结果。
  4. 若未命中：用大LM生成计划 → 演员LM执行 → 大LM判断 → 完成后从日志生成模板并缓存。

## 3. 实验设计：数据集、基准与对比方法
- **数据集/场景（共5个）**：
  - FinanceBench（长期财务推理）
  - TabMWP（表格数学推理）
  - QASPER（研究论文问答）
  - AIME 2024 / 2025（数学竞赛题）
  - GAIA（通用AI助手基准）
- **代理架构**：主要基于Minion架构（两层Plan-Act流水线），也在Open Deep Research代理上验证。
- **对比方法**：
  - Accuracy-Optimal：始终使用大规划器LM（无缓存，性能最优）。
  - Cost-Optimal：始终使用小规划器LM（成本最低）。
  - Semantic Caching：基于查询级语义相似度的缓存（设置三个阈值：80%、85%、90%）。
  - Full-History Caching：缓存完整执行日志作为上下文示例。
  - APC（本文方法）。

## 4. 资源与算力
- 论文未明确说明训练所消耗的GPU型号、数量或训练时长。
- 实验使用API调用（OpenAI、Together AI、Anthropic），计算成本按token计费，未涉及本地GPU训练。
- 原型部署在Runpod服务器（双路Intel Xeon Gold 6342 CPU，96 vCPU，503GB RAM），无GPU。

## 5. 实验数量与充分性
- **实验组数**：在5个基准数据集上进行了主实验，此外还有：
  - 消融实验：比较不同缓存方法（语义缓存、全历史缓存）。
  - 敏感性分析：更换大规划器LM（GPT-4o vs. Claude 3.5 Sonnet）、小规划器LM（LLaMa-3.1-8B vs. Qwen-2.5-7B vs. LLaMa-3.2-3B）、演员LM（多种型号）。
  - 缓存大小影响实验（1~100条）。
  - 冷启动行为分析（按查询百分位）。
  - 精确匹配 vs. 模糊匹配的延迟和准确率对比。
- **充分性评估**：实验覆盖了多种任务类型（推理、工具使用）、多种模型组合，并分析了缓存命中/未命中时的准确率差异。对比基线设置合理（语义缓存、全历史缓存），且展示了统计稳定性（多次采样？但未明确报告误差棒，只在部分分析中提及平均结果）。总体而言，实验设计较为全面，但缺少对随机性的量化误差分析（如多次运行的标准差）。

## 6. 论文的主要结论与发现
- **成本降低**：APC平均降低服务成本50.31%。
- **延迟降低**：平均降低端到端延迟27.28%。
- **性能保持**：保持最优准确率的96.61%（在FinanceBench上从91%降至85.5%，但对比语义缓存的显著下降，APC表现稳定）。
- **缓存命中/未命中准确率一致**：语义缓存和全历史缓存在命中时准确率大幅下降，而APC命中与未命中准确率接近，说明模板适配有效。
- **开销低**：关键词提取和缓存生成平均只占成本的1.04%。
- **可扩展性**：精确关键词匹配支持百万级缓存且延迟极低（微秒级），模糊匹配则慢得多且准确率有折扣。
- **冷启动影响**：初始阶段成本较高，但随着缓存增长，边际成本下降。

## 7. 优点：方法或实验设计上的亮点
- **创新点**：首次提出针对LLM代理的计划级缓存，而非查询级缓存，解决了数据依赖输出问题。
- **设计巧妙**：利用关键词提取（而非语义相似度）进行缓存检索，避免了阈值设定的困难，降低了假阳/假阴率。
- **轻量适配**：使用小模型适配模板，既利用了大模型的先验知识（通过模板），又避免了每次调用大模型的高成本。
- **兼容性好**：可与现有LLM服务引擎（如vLLM、SGLang）和代理框架（如smolagents）协同工作。
- **实验全面**：覆盖多种代理架构（Minion、Open Deep Research）、多种模型组合，并分析了缓存大小、冷启动、模糊匹配等边际条件。

## 8. 不足与局限
- **实验覆盖**：仅在两阶段Plan-Act架构上评估，未考虑更复杂的多智能体系统或非顺序规划模式。
- **任务局限性**：高度动态或一次性任务（如GAIA中许多问题仅出现一次）缓存收益有限，因为缺乏可复用的模式。
- **性能依赖关键词质量**：关键词提取依赖轻量模型，若无法准确捕捉高层意图，可能导致错误匹配。
- **未报告统计误差**：未给出多次实验的标准差或置信区间，难以判断结果的稳定性。
- **隐私与安全**：讨论了潜在风险（缓存可能包含敏感信息），但未提出具体防护机制。
- **仅关注成本优化**：未系统评估对吞吐量、系统内存等指标的权衡。

（完）
