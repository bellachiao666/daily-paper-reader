---
title: "M³HF: Multi-agent Reinforcement Learning from Multi-phase Human Feedback of Mixed Quality"
title_zh: M³HF：来自混合质量多阶段人类反馈的多智能体强化学习
authors: "Ziyan Wang, Zhicheng Zhang, Fei Fang, Yali Du"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=2Sl6Ex7Vmo"
tags: ["query:agent-papers"]
score: 7.0
evidence: 多智能体强化学习结合多阶段人类反馈
tldr: 多智能体强化学习中奖励设计困难。本文提出M3HF框架，引入多阶段、质量混合的人类反馈，利用LLM解析反馈并持续优化策略。在复杂协调环境中，M3HF使智能体行为更对齐且鲁棒。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1699, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1710, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1727, \"height\": 889, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1057, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 667, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1697, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1620, \"height\": 904, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-2sl6ex7vmo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 888, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2sl6ex7vmo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 885, \"height\": 157, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2sl6ex7vmo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2sl6ex7vmo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 884, \"height\": 492, \"label\": \"Table\"}]"
motivation: 多智能体RL中奖励函数设计困难。
method: 集成多阶段混合质量的人类反馈，使用LLM解析并更新策略。
result: 在复杂环境中提升了行为对齐和鲁棒性。
conclusion: 混合质量人类反馈可有效改善多智能体训练。
---

## Abstract
Designing effective reward functions in multi-agent reinforcement learning (MARL) is a significant challenge, often leading to suboptimal or misaligned behaviors in complex, coordinated environments. We introduce Multi-agent Reinforcement Learning from Multi-phase Human Feedback of Mixed Quality ($\text{M}^3\text{HF}$), a novel framework that integrates multi-phase human feedback of mixed quality into the MARL training process. By involving humans with diverse expertise levels to provide iterative guidance, $\text{M}^3\text{HF}$ leverages both expert and non-expert feedback to continuously refine agents' policies. During training, we strategically pause agent learning for human evaluation, parse feedback using large language models to assign it appropriately and update reward functions through predefined templates and adaptive weights by using weight decay and performance-based adjustments. Our approach enables the integration of nuanced human insights across various levels of quality, enhancing the interpretability and robustness of multi-agent cooperation. Empirical results in challenging environments demonstrate that $\text{M}^3\text{HF}$ significantly outperforms state-of-the-art methods, effectively addressing the complexities of reward design in MARL and enabling broader human participation in the training process.

---

## 论文详细总结（自动生成）

## 论文详细中文总结

### 1. 核心问题与整体含义（研究动机和背景）
- **问题**：多智能体强化学习（MARL）中，奖励函数设计是核心挑战。尤其在复杂协调任务中，环境奖励稀疏或结构复杂，导致智能体收敛慢、行为次优。
- **背景**：传统方法依赖手工设计奖励，难以覆盖复杂交互；单阶段人类反馈（如RLHF）限于单智能体或离线场景，缺乏迭代动态交互。
- **本文目标**：引入多阶段、质量混合的人类反馈（专家与非专家均可），通过LLM解析并动态调整奖励函数，提升MARL学习效率与鲁棒性，降低人类参与门槛。

### 2. 方法论
#### 核心思想
- 提出**Multi-phase Human Feedback Markov Game (MHF-MG)**，扩展标准马尔可夫博弈，加入人类反馈通道（utterances）和人类策略π^h。
- 开发**M³HF框架**，将多阶段混合质量人类反馈直接整合到在线MARL训练中。

#### 关键技术细节
1. **生成与评估**：每代训练后暂停，收集固定策略下的rollout轨迹（X条，长度H），作为人类评估依据。
   - 理论保证（命题4.1）：通过大数定律，rollout的折扣回报均值几乎必然收敛到真实期望回报。
2. **人类反馈解析**：使用LLM（如gpt-4o-2024-11-20）将人类自然语言反馈自动分配到具体智能体或全体，输出结构化指令。
3. **奖励函数生成**：预定义奖励模板（距离型、动作型、状态型、时间型等），LLM根据反馈选择并参数化模板，生成新奖励函数R_i^k(s,a)。
4. **自适应权重调整**：每个智能体维护奖励函数池，新奖励函数初始权重为1/|Pi|；使用**权重衰减**（α^(M-m)）和**性能反馈**（比较相邻代在原始奖励下的回报差）调整权重，最终加权求和得到最终奖励函数（式12）。
5. **鲁棒性分析**（命题4.2）：即使出现低质量反馈，算法性能下降有界（δ），且只会累积正贡献；证明了权重机制能有效抑制有害反馈。

#### 算法流程（Algorithm 1）
```
1. 初始化每个智能体的奖励函数池为原始奖励
2. for generation k = 0 to K-1:
   a. 使用当前奖励函数训练策略（IPPO/PAGE等）
   b. 生成rollout轨迹
   c. 人类观察并给出反馈u_k
   d. LLM解析反馈，分配至各智能体
   e. 对每个智能体，根据模板生成新奖励函数，加入池
   f. 权重衰减 + 性能调整 → 更新最终奖励函数
   g. 下一代训练继续
```

### 3. 实验设计
- **环境**：基于Overcooked的宏动作版本（三智能体协作制作沙拉）
  - 3种厨房布局：A（开阔）、B（隔开两侧）、C（狭窄）
  - 2种食谱：生菜-番茄沙拉、生菜-洋葱-番茄沙拉
  - 宏动作空间（简化版，源自Xiao et al. 2022）
- **基准方法**：
  - MAPPO（共享策略+集中值函数）
  - IPPO（独立策略）
  - Mac-Based Baseline（Mac-IAICC和Mac-CAC的平均性能）
- **实验设置**：每个Generation 200个迭代，每迭代25个episode，每episode最多200步，总训练约25k episodes。
- **消融实验**：
  - 反馈解析与权重调整（原始反馈 vs LLM解析 vs 完整M³HF）
  - 单阶段 vs 多阶段反馈
  - 与内在奖励方法IRAT比较（三种奖励变体）
  - 混合质量反馈测试（低质量反馈模拟、VLM反馈替代）
- **额外验证**：扩展到Google Football 5v5（HARD模式），对比相同baselines。

### 4. 资源与算力
- **硬件**：Ubuntu集群，CPU含多种Xeon E5系列（180核，500GB内存），GPU为3块NVIDIA A30。
- **模型**：LLM使用gpt-4o-2024-11-20，VLM使用Gemini-1.5-Pro-002。
- **训练时长**：文中未明确说明具体训练总时长，仅描述了迭代次数和episode数量（约25k episodes per experiment）。算力描述较充分，但缺少精确时间统计。

### 5. 实验数量与充分性
- **数量**：主要结果6个子图（图3：3种布局×2种食谱），混合质量反馈实验1个子图（图4c），消融实验3个表格（表1、2、3），另有Google Football扩展2个图（图5、6）。总计超过10组对比。
- **充分性**：
  - 覆盖不同难度布局和食谱，验证泛化性。
  - 消融设计合理：逐步拆解反馈解析、权重调整、多阶段、内在奖励等组件。
  - 混合质量反馈模拟了低质量、VLM和理想人类，测试鲁棒性。
  - 与SOTA（MAPPO、IPPO、Mac-Based）公平对比，每个实验使用3个随机种子报告均值和标准差。
- **客观性**：超参数调优（learning rate, batch size等）在baseline上进行了搜索，并采用最优配置；代码开源，可复现。

### 6. 主要结论与发现
- ✅ M³HF在所有Overcooked场景中**显著优于**所有基线（IPPO、MAPPO、Mac-Based），尤其在复杂布局C和复杂食谱中优势更明显（图3）。
- ✅ **多阶段反馈**优于单阶段反馈（表2），证明迭代指导的重要性。
- ✅ **对低质量反馈鲁棒**：即使收到错误或无关反馈（如“任务已完成”），性能仅轻微下降，接近IPPO基线（图4c），验证命题4.2。
- ✅ **VLM反馈效果有限**：当前VLM（Gemini 1.5 Pro）生成的反馈泛化性差，难以翻译为有效奖励，性能不佳（图4c）。
- ✅ **内在奖励方法（IRAT）** 虽能提升IPPO，但远不如M³HF，因为后者能精准定位协调失败。
- ✅ **Google Football**扩展验证了方法在更复杂多智能体场景中的可扩展性，在Win Rate、Total Move、Good Shot等指标上均领先。

### 7. 优点
- **新颖性**：首次将多阶段、质量混合人类反馈引入在线MARL训练，提出MHF-MG形式化框架。
- **实用性**：允许非专家参与，降低人类门槛；反馈只需自然语言，无需标注偏好或轨迹。
- **技术集成**：LLM自动解析反馈并生成奖励函数，预定义模板结构化，自适应权重动态管理。
- **理论支撑**：提供rollout性能估计收敛性证明（命题4.1）和低质量反馈鲁棒性界（命题4.2）。
- **实验全面**：考虑多种质量反馈、消融、大规模扩展，结果充分。

### 8. 不足与局限
- **人类反馈成本**：仍需要人类观察rollout视频并撰写反馈（虽然仅需5次），在真实部署中可能消耗人力。
- **LLM依赖**：反馈解析和奖励生成依赖LLM，可能因LLM理解偏差导致错误转化；未测试不同LLM的稳定性。
- **VLM替代不成熟**：实验表明当前VLM无法产生有效反馈，限制了完全自动化的潜力。
- **超参数敏感性**：权重调整中的衰减因子α和性能调整步长β需要人工设定，文中未进行敏感性分析。
- **场景覆盖有限**：主要Overcooked和Football，未在更多样化环境（如连续控制、通信受限场景）验证。
- **人类反馈质量假设**：假设人类策略优于当前智能体，但未严格验证；若人类水平低于智能体，可能引入偏差。

（完）
