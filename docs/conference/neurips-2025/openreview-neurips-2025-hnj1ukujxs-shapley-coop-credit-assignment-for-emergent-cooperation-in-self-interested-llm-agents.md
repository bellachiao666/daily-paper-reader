---
title: "Shapley-Coop: Credit Assignment for Emergent Cooperation in Self-Interested LLM Agents"
title_zh: Shapley-Coop：自私大语言模型智能体中涌现合作的信用分配
authors: "Yun Hua, Haosheng Chen, Shiqin Wang, Wenhao Li, Xiangfeng Wang, Jun Luo"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=HnJ1UkuJXS"
tags: ["query:agent-papers"]
score: 8.0
evidence: 为开放环境中自私LLM智能体的涌现合作提供信用分配机制
tldr: 大语言模型智能体在开放环境中往往自私，导致社会困境和次优集体结果。受人类合作启发，论文提出Shapley-Coop框架，基于Shapley值进行信用分配，激励自私智能体自发合作。实验证明该方法在多种社交困境中有效促进协作，为多智能体系统协调提供了新机制。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: 自私的LLM智能体在无显式协调时易陷入社会困境，集体效率低下。
method: 引入Shapley值计算每个智能体对合作的贡献，并据此分配奖励。
result: 在多个社交困境游戏中，Shapley-Coop显著提升了合作率和整体收益。
conclusion: 合理的信用分配能激励自私智能体产生合作行为。
---

## Abstract
Large Language Models (LLMs) are increasingly deployed as autonomous agents in multi-agent systems, and promising coordination has been demonstrated in handling complex tasks under predefined roles and scripted workflows.
However, significant challenges remain in open-ended environments, where agents are inherently self-interested and explicit coordination guidelines are absent. 
In such scenarios, misaligned incentives frequently lead to social dilemmas and inefficient collective outcomes.
Inspired by how human societies tackle similar coordination challenges—through temporary collaborations like employment or subcontracting—a cooperative workflow \textbf{Shapley-Coop} is proposed. 
This workflow enables self-interested Large Language Model (LLM) agents to engage in emergent collaboration by using a fair credit allocation mechanism to ensure each agent’s contributions are appropriately recognized and rewarded.
Shapley-Coop introduces structured negotiation protocols and Shapley-inspired reasoning to estimate agents’ marginal contributions, thereby enabling effective task-time coordination and equitable post-task outcome redistribution. 
This results in effective coordination that fosters collaboration while preserving agent autonomy, through a rational pricing mechanism that encourages cooperative behavior.
Evaluated in two multi-agent games and a software engineering simulation, Shapley-Coop consistently enhances LLM agent collaboration and facilitates equitable outcome redistribution, accurately reflecting individual contributions during the task execution process.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：大语言模型（LLM）在多智能体系统中展现出强大的协作能力，但现有方法依赖预定义角色和脚本化流程。在开放环境中，智能体往往自私（self-interested），缺乏显式协调规则，容易陷入社会困境（social dilemma），导致集体效率低下。如何让自私LLM智能体自发涌现合作，并公平分配信用（credit assignment）成为核心挑战。
- **背景启发**：受人类社会中通过雇佣、分包等临时协作机制解决协调问题的启发，论文提出基于原则性定价和公平信用分配的方法，使自私智能体能够自发协调。

## 2. 方法论

- **核心思想**：借鉴合作博弈论中的Shapley值（Shapley Value），衡量每个智能体对团队成功的边际贡献，并据此设计定价机制（任务时定价 + 事后奖励重分配）来对齐异质目标，激励合作。
- **关键技术细节**：
  - **Shapley-Coop框架**：包含三个模块：
    1. **结构化协商协议（Structured Negotiation Protocol）**：使用标准化消息格式（如`<s>I propose to {action}</s>`）进行意图通知、定价提议和结构化回应，实现透明协商。
    2. **短期Shapley思维链（Short-Term Shapley CoT）**：在任务执行中，通过启发式推理定性评估长期奖励、判断外部性（正/负），并构建协商策略（如需要补偿或请求支付），实现任务时定价对齐。
    3. **长期Shapley思维链（Long-Term Shapley CoT）**：任务完成后，基于完整轨迹计算集体效用，估计每个智能体的边际贡献和Shapley值，通过协商达成公平奖励重分配。
  - **数学基础**：Shapley值公式为 \(\phi_i = \sum_{C \subseteq N\setminus\{i\}} \frac{|C|!(N-|C|-1)!}{N!} \left[ R(C\cup\{i\}) - R(C) \right]\)，衡量智能体在所有可能团队中的平均边际贡献。
- **算法流程**（文字说明）：
  1. 所有智能体通过结构化协议交换意图和定价提议。
  2. 每个智能体使用短期Shapley CoT评估自身行动的外部性，确定是否需要提供或请求补偿，并达成任务时协议。
  3. 任务完成后，智能体使用长期Shapley CoT计算集体奖励和自身Shapley值，并通过进一步协商调整奖励分配，直至公平。

## 3. 实验设计

- **场景**：
  1. **Escape Room（密室逃脱）**：一个双人社会困境，一人拉杆（付出-1）另一人开门（获得+10），需要合作才能成功。
  2. **Raid Battle（突袭战）**：四人协作RPG游戏，各自拥有技能（嘲讽、火球、治疗），但伤害技能的个人奖励更高，造成个体与集体利益冲突。三种难度（Boss HP=2000/2500/3000）。
  3. **ChatDEV（软件工程模拟）**：模拟软件公司角色（CEO、CTO、程序员等）协作开发应用，使用加权挣值（WEV）度量贡献。
- **Benchmark与对比方法**：
  - 对比了四种配置：LLM-only（无协商合作）、LLM+NEG（简单协商无Shapley推理）、LLM+STS（仅短期Shapley CoT）、LLM+SC（完整Shapley-Coop）。
  - 在Raid Battle中额外比较了Banzhaf值与Shapley值的差异（附录F）。

## 4. 资源与算力

- 论文明确说明：实验在小型服务器上运行，CPU为24核，32GB DRAM，**未使用GPU资源**（仅API调用）。未提及训练时长或具体GPU型号。

## 5. 实验数量与充分性

- **实验数量**：三个主要场景，每个场景包含多轮实验（如Raid Battle三个难度，每个难度多次运行；ChatDEV两个任务）。Raid Battle中展示了谈判轮次的影响（附录B表7）。消融实验对比了四个配置，并分析了不同组件贡献。
- **充分性与公平性**：实验设计较为充分，覆盖了从简单社会困境到复杂多步游戏以及真实世界软件工程任务。对比方法设置合理，消融实验清晰。但未报告多次运行的统计误差棒（仅部分图有误差线），且只用了单一基座模型（DeepSeek-v3）进行主实验，泛化性验证不足。

## 6. 主要结论与发现

- Shapley-Coop（LLM+SC）在所有场景中均显著提升了合作率和公平奖励分配，成功避免了社会困境。
- 在Escape Room中，LLM+SC达成100%成功率且奖励分配接近理论最优（4.5, 4.5），而LLM-only完全失败。
- 在Raid Battle中，LLM+SC实现了更平衡的角色分工（嘲讽、治疗比例更高），贡献分数比LLM+NEG提升56%~222%，且奖励分配偏差更小。
- 在ChatDEV中，基于Shapley值的WEV度量与人工分配奖励高度一致（调整幅度<6%），验证了现实场景的实用性。
- Shapley值比Banzhaf值更适合连续贡献场景，能更公平地反映贡献。

## 7. 优点

- **创新性**：首次将Shapley值与LLM智能体协商结合，提出完整的工作流解决信用分配问题，视角新颖。
- **实用性**：无需重新训练，通过提示工程实现零样本/少样本合作，易于部署。
- **公平性**：Shapley值提供了理论上的公平基准，实验验证其分配合理性。
- **鲁棒性**：在多个不同类型的环境中均有效，包括离散博弈和连续贡献场景。

## 8. 不足与局限

- **可扩展性**：计算Shapley值需枚举所有子集，在智能体数量增多时计算开销大；论文中的近似方法牺牲了效率公理。
- **通信开销**：协商过程消耗大量token，可能限制实时应用。
- **动态定价缺失**：当前方法无法在协作过程中动态调整定价，仅依靠事前协商和事后分配。
- **模型依赖**：主要使用DeepSeek-v3，未验证其他LLM（如GPT-4、Claude）的泛化性。
- **实验覆盖有限**：仅在三个场景中测试，缺乏更复杂或更大规模多智能体系统的验证。
- **统计显著性**：部分实验结果未提供多次运行的误差棒或显著性检验，可能不足以排除随机性影响。

（完）
