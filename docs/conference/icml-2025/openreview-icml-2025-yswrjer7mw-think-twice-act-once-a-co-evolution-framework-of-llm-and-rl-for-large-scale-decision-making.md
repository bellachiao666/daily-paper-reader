---
title: "Think Twice, Act Once: A Co-Evolution Framework of LLM and RL for Large-Scale Decision Making"
title_zh: 三思而后行：LLM与RL协同进化的大规模决策框架
authors: "Xu Wan, Wenyue Xu, Chao Yang, Mingyang Sun"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ySWrJer7mW"
tags: ["query:agent-papers"]
score: 7.0
evidence: LLM与RL协同进化，通过双重角色轨迹精炼实现智能体自我改进
tldr: 该论文针对LLM和RL在大规模决策中的各自局限性，提出智能体协同进化框架ACE。在该框架中，LLM同时扮演策略执行者和价值评估者，通过多步推理和环境反馈优化RL智能体的轨迹。实验表明ACE能够有效提升RL的样本效率和决策质量，并且LLM在协作过程中也得到改善。该工作为LLM与RL的深度集成实现智能体自我改进提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1691, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 830, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1698, \"height\": 868, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1756, \"height\": 972, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1778, \"height\": 826, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1767, \"height\": 1175, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1771, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1768, \"height\": 871, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1829, \"height\": 957, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 857, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 522, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 891, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1758, \"height\": 534, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1170, \"height\": 719, \"label\": \"Table\"}]"
motivation: LLM缺乏实时决策能力，RL在大动作空间中样本效率低。
method: LLM作为Actor改进动作，作为Critic提供价值信号，协同进化RL策略。
result: 在多个大规模决策任务上显著优于单独LLM或RL。
conclusion: ACE展示了LLM与RL协同进化的潜力，实现了智能体能力的自我提升。
---

## Abstract
Recent advancements in Large Language Models (LLMs) and Reinforcement Learning (RL) have shown significant promise in decision-making tasks. Nevertheless, for large-scale industrial decision problems, both approaches face distinct challenges: LLMs lack real-time long-sequence decision-making capabilities, while RL struggles with sample efficiency in vast action spaces. To bridge this gap, we propose **A**gents **C**o-**E**volution (ACE), a synergistic framework between LLMs and RL agent for large-scale decision-making scenarios. ACE introduces a dual-role trajectory refinement mechanism where LLMs act as both Policy Actor and Value Critic during RL's training: the Actor refines suboptimal actions via multi-step reasoning and environment validation, while the Critic performs temporal credit assignment through trajectory-level reward shaping. Concurrently, RL agent enhance LLMs' task-specific decision-making via prioritized experience replay.

Through extensive experiments across multiple power grid operation challenges with action spaces exceeding 60K discrete actions, ACE demonstrates superior performance over existing RL methods and LLM-based methods.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

大规模工业决策问题（如电网控制、交通管理、多机器人协调）面临两大方法的各自局限：
- **LLM**：具备丰富的世界知识和推理能力，但缺乏实时长序列决策能力，且自回归生成导致高延迟，无法满足工业控制亚秒级响应要求。
- **RL**：可通过与环境交互学习最优策略，但在巨大动作空间中样本效率极低，且易陷入次优解。

论文提出**智能体协同进化（ACE）** 框架，将LLM的离线推理指导与RL的在线实时执行分离，在训练阶段让LLM扮演“策略执行者”和“价值评估者”双重角色，精炼RL轨迹；同时RL生成的高质量经验用于微调LLM，实现两者协同进化，从而同时解决样本效率低下和实时性不足的问题。

## 2. 论文提出的方法论

### 核心思想
“**三思而后行**”：RL负责在线实时交互（“Act Once”），LLM在离线训练阶段对RL轨迹进行双重精炼（“Think Twice”），并通过混合经验回放实现两者共同提升。

### 关键技术细节

#### （1）第一阶段：直接策略学习（RL与环境交互）
- 采用**SAC**（Soft Actor-Critic）作为RL模块，最大化期望累积奖励与策略熵。
- 将轨迹元组 `(s, a, r, s', d)` 存入回放缓冲区 `DRL`，用于更新Q函数和策略。

#### （2）第二阶段：LLM双重角色精炼
- **LLM作为策略执行者（Actor）**：从 `DRL` 中采样低奖励状态（`r < r_threshold`），将状态和动作转为自然语言，提供领域知识前缀，调用LLM生成改进动作 `ˆa_t`，并通过Grid2Op环境模拟验证，获得新轨迹存入 `DLLM`。
- **LLM作为价值评估者（Critic）**：在训练后期，对关键轨迹（高|r|）进行反事实推理，调整奖励值 `ˆr_t`（离散化为 ±K, ±2K），实现更优的时序信用分配。

#### （3）协同进化：经验收集与混合回放
- 构建**混合缓冲区** `Dmix`，以 `β` 比例混合RL和LLM缓冲区的样本。
- **基于奖励的优先采样**：对LLM精炼后的轨迹计算重要性权重 `w_r(τ)=exp(ˆr/β)/exp(r/β)`，优先采样高奖励经验。
- **加权策略更新**：RL策略梯度损失乘以权重 `w_r(τ)`，突出高质量LLM示范的学习。
- **LLM微调**：定期用 `Dmix` 对LLM进行低秩适配（LoRA）微调，提升其任务特定指导能力。

### 算法流程（文字说明）
1. RL与环境交互，收集轨迹存入 `DRL`。
2. 每隔若干步，从 `DRL` 采样低奖励/关键轨迹，调用LLM进行动作精炼（Actor）或奖励调整（Critic），模拟后存入 `DLLM`。
3. 混合采样 `pmix`，计算重要性权重，更新Q函数和策略。
4. 每生成一定数量样本，使用 `Dmix` 微调LLM。

## 3. 实验设计

### 数据集/场景
- **L2RPN WCCI 2020**: 1/3美国中西部电网，36变电站、59线路、22发电机，动作空间 >60,000，测试10个3天场景（864步）。
- **L2RPN NeurIPS 2020**: 同上电网，加入对手随机断开重载线路，测试24个周场景（2016步）。
- **L2RPN WCCI 2022**: IEEE-118系统，118变电站、186线路、91负载、62发电机，动作空间 >70,000，训练数据32年（约1.7GB）。

### 对比方法
- **Expert-guided RL**: WCCI 2020冠军方案（层次化策略+后状态表示）。
- **LLM only**: GPT-4o-0806、Qwen2-7B-Instruct直接决策。
- **LLM-guided RL**: 修改版LLM4Teach（KL散度约束策略正则化）。
- **ACE变体**: ACE (Qwen2-7B+SFT) 和 ACE (GPT-4)。

### 评估指标
- 回合奖励（Episode Rewards）
- 生存率（Survival Rate %）
- 样本需求（Sample Requirements）
- 测试时间（Test Time）

## 4. 资源与算力

论文在附录表4（Computational overhead breakdown）中给出了详细计算开销（基于NeurIPS 2020环境，Qwen2-7B+SFT）：
- ACE-RL：~40K样本，3h 4m 41s
- ACE-LLM推理：508次推断，264样本，1h 48m 0s
- ACE-LLM采样：4981次，32样本，59m 12s
- ACE-LLM训练：2次，200样本，26m 10s
- **总计**：~40K样本，6h 18m 3s

论文**未明确说明GPU型号和数量**，但可推测使用单/多GPU（如A100或V100）进行实验。整体算力需求适中，远低于纯LLM在线交互的耗时。

## 5. 实验数量与充分性

- **主实验**：在3个不同复杂度数据集上对比6种方法，每个报告5次运行均值和标准差。
- **消融实验**：对ACE组件（w/o fLLM, w/o gLLM, w/o bad case, w/o multi-round reasoning）以及超参数（激活频率、坏阈值、SFT频次、轨迹选择、奖励调整尺度）进行了系统分析，共10余组对比。
- **结果展示**：包含训练曲线、测试场景对比、案例研究可视化。

**充分性评价**：实验覆盖了多场景、多基线、多组件消融，统计量规范，结论可信。但**仅局限于电力系统领域**，未验证通用性；且所有方法均在同一平台实现，对比公平。

## 6. 论文的主要结论与发现

1. ACE在所有三个挑战上均取得**最优回合奖励和生存率**，显著超过纯RL（22%~145%提升）和纯LLM（130%+提升）。
2. **样本效率极大提升**：WCCI 2020中仅需287次LLM精炼 + 40K RL样本即达到SOTA，而基线需100K样本。
3. **实时性保持**：ACE测试时间（38.7~219s）与纯RL相当，远快于纯LLM（数千秒），满足工业部署要求。
4. **LLM单步精炼能力强但长序列弱**：LLM改进单步动作有效，但独立完成完整剧集表现差；混合缓冲区微调后可提升LLM自身决策能力（+10.9%）。
5. **选择性精炼优于策略正则化**：ACE的离线轨迹精炼比LLM4Teach的KL约束获得更高奖励和生存率。
6. SFT频率和坏阈值等超参数对性能有显著影响，需要适当配置。

## 7. 优点

- **范式创新**：提出“Think Twice, Act Once”分离离线指导与在线执行，巧妙平衡了LLM推理能力与RL实时性要求。
- **双重角色设计**：LLM同时作为动作精炼器和价值评估器，分别解决样本效率低下和次优性问题，实现互补。
- **自动高质量数据集生成**：通过奖励优先采样和加权策略更新，构建混合缓冲区，同时提升RL和LLM能力，形成正向循环。
- **工程友好**：仅需少量LLM调用（<700次）即可显著提升性能，计算开销可控。
- **实验扎实**：在三个大规模工业挑战上验证，包含充分消融和超参数分析，统计严谨。

## 8. 不足与局限

- **领域局限**：仅在电力系统（Grid2Op）上验证，未在机器人、交通等更广泛决策任务上测试，通用性存疑。
- **LLM依赖环境模拟**：动作精炼需要调用Grid2Op模拟器评估新动作，对于无法模拟的环境（如真实物理系统）应用受限。
- **超参数敏感**：激活频率、阈值、SFT频次等需手动调整，论文未提供自动调优策略。
- **未讨论安全性与鲁棒性**：在对抗性环境（NeurIPS 2020）中表现良好，但未分析极端故障或攻击下的行为。
- **LLM模型选择有限**：主要使用Qwen2-7B和GPT-4o，未对比更小或更大模型，也未分析不同基础模型对性能的影响。
- **资源评估不完全**：未明确GPU型号/数量，导致算力可复现性稍弱。

（完）
