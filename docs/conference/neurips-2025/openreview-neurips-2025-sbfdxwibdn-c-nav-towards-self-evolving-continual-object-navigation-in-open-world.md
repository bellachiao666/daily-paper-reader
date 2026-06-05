---
title: "C-NAV: Towards Self-Evolving Continual Object Navigation in Open World"
title_zh: C-NAV：面向开放世界的自进化持续目标导航
authors: "MingMing Yu, Fei Zhu, wenzhuo liu, Yirong Yang, Qunbo Wang, wenjun wu, Jing Liu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=SbfdxWibDn"
tags: ["query:agent-papers"]
score: 7.0
evidence: 具身智能体的自进化持续目标导航
tldr: 该论文提出持续目标导航基准和C-NAV框架，使具身智能体在开放世界中持续学习新物体类别导航技能，同时避免灾难性遗忘。通过双重路径抗遗忘机制（特征蒸馏与自演化方法），智能体实现自我进化，适应动态环境。该工作体现了自进化递归代理在具身场景的应用。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbfdxwibdn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1433, \"height\": 598, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbfdxwibdn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbfdxwibdn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1405, \"height\": 712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbfdxwibdn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1444, \"height\": 791, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbfdxwibdn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 919, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbfdxwibdn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 404, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbfdxwibdn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 442, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbfdxwibdn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 430, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbfdxwibdn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1458, \"height\": 729, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbfdxwibdn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1454, \"height\": 715, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbfdxwibdn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1210, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbfdxwibdn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1448, \"height\": 561, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbfdxwibdn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1468, \"height\": 753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbfdxwibdn/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1453, \"height\": 853, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbfdxwibdn/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1445, \"height\": 542, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbfdxwibdn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1406, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbfdxwibdn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 401, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbfdxwibdn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1434, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbfdxwibdn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 589, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbfdxwibdn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1440, \"height\": 666, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbfdxwibdn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1533, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbfdxwibdn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1095, \"height\": 277, \"label\": \"Table\"}]"
motivation: 现有具身导航依赖固定类别和静态轨迹，无法持续适应新场景。
method: 提出包含特征蒸馏和自演化模块的持续视觉导航框架。
result: 在持续导航基准上有效防止遗忘并保持高导航成功率。
conclusion: C-NAV为具身智能体的自进化能力提供了重要实践。
---

## Abstract
Embodied agents are expected to perform object navigation in dynamic, open-world environments. However, existing approaches typically rely on static trajectories and a fixed set of object categories during training, overlooking the real-world requirement for continual adaptation to evolving scenarios. To facilitate related studies, we introduce the continual object navigation benchmark, which requires agents to acquire navigation skills for new object categories while avoiding catastrophic forgetting of previously learned knowledge. To tackle this challenge, we propose C-Nav, a continual visual navigation framework that integrates two key innovations: (1) A dual-path anti-forgetting mechanism, which comprises feature distillation that aligns multi-modal inputs into a consistent representation space to ensure representation consistency, and feature replay that retains temporal features within the action decoder to ensure policy consistency. (2) An adaptive sampling strategy that selects diverse and informative experiences, thereby reducing redundancy and minimizing memory overhead. Extensive experiments across multiple model architectures demonstrate that C-Nav consistently outperforms existing approaches, achieving superior performance even compared to baselines with full trajectory retention, while significantly lowering memory requirements. 
The code will be publicly available at \url{https://bigtree765.github.io/C-Nav-project}.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：现有的具身目标导航方法通常假设训练时使用固定的物体类别集合和静态轨迹，这无法满足开放世界动态环境中智能体需要持续学习新物体类别导航技能的现实需求。
- **核心挑战**：当智能体按顺序学习多个任务时，会出现**灾难性遗忘**——学习新任务后，旧任务的导航能力大幅下降。同时，导航任务涉及长序列的多模态输入（RGB、深度、位姿、动作历史、文本指令），导致学习复杂度高，简单回放原始轨迹存在存储开销大、隐私风险高、相邻帧冗余等问题。
- **意义**：这是首次系统研究持续学习在目标导航领域的应用，为具身智能体在真实世界中的自适应部署奠定基础。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
提出 **C-Nav**（Continual Object Navigation）框架，通过**双路径抗遗忘机制**抑制多模态编码器和动作解码器中的表示漂移与策略退化，并借助**自适应经验选择**减少存储冗余，使智能体在学习新任务时保持对旧任务的导航能力。

### 关键技术细节
#### （1）双路径抗遗忘
- **特征蒸馏路径（表示一致性）**：冻结旧任务编码器 \(f_{k-1}\)，约束当前编码器 \(f_k\) 的输出与其在相同观测上的特征保持 \(\ell_2\) 距离最小化，防止编码器表示漂移。公式：
  \[
  \mathcal{L}_{KD} = \sum_{t=1}^{L} \| f_{k-1}(o_t) - f_k(o_t) \|_2^2
  \]
- **特征重放路径（策略一致性）**：存储旧任务的关键帧特征及其对应动作，在训练新任务时用这些特征重放，损失函数为带动作转换加权的交叉熵：
  \[
  \mathcal{L}_{FR} = \frac{1}{|L|} \sum_{t=1}^{L} -w_t \log \pi_k(a_t | h_{1:t}), \quad w_t = 1 + \gamma \cdot \mathbf{1}_{a_t \neq a_{t-1}}
  \]
  其中 \(\pi_k\) 为当前解码器，\(h_t\) 为存储在特征缓冲区中的第 \(t\) 帧特征。

#### （2）自适应经验选择
- **动机**：导航轨迹中存在大量视觉冗余帧，只有少数关键帧（如进入新区域、靠近目标、决策点）对防止遗忘最有效。
- **方法**：将关键帧选择转化为**特征空间中的离群点检测**。使用预训练的 CLIP 编码每一帧的 RGB 图像，获得特征向量 \(v_i\)，然后计算**局部离群因子（LOF）**：
  - 计算余弦距离，定义 k-距离邻域、可达距离、局部可达密度，最后 LOF = 邻域相对密度比值。
  - 选择 LOF > 1 的帧作为关键帧（视为离群点），这些帧反映了显著的语义变化。
- **存储**：这些关键帧的特征（通过多模态编码器 \(f_k\) 提取）及其对应动作被存入特征缓冲区，供后续重放使用。

#### （3）总体损失
\[
\mathcal{L} = \mathcal{L}_{curr} + \lambda_{KD} \cdot \mathcal{L}_{KD} + \lambda_{FR} \cdot \mathcal{L}_{FR}
\]
其中 \(\mathcal{L}_{curr}\) 为当前任务的行为克隆损失（也使用动作转换加权）。

## 3. 实验设计
- **数据集**：基于 Habitat 模拟器，使用 HM3D（20 个验证场景，6 个物体类别，75,488 条轨迹）和 MP3D（11 个验证场景，21 个物体类别，59,604 条轨迹）。每个数据集被划分为 4 个持续学习阶段（Stage 1~4），新物体类别逐阶段引入。
- **基准（Continual-ObjectNav Benchmark）**：智能体需顺序学习 K 个任务，每个任务引入一组互不相交的物体类别。测试时评估所有已学类别的平均成功率（SR）和路径加权成功率（SPL）。
- **对比方法**：
  - Naive Fine-tuning（无防遗忘）
  - LoRA（低秩适配）
  - LwF（无遗忘学习，知识蒸馏）
  - Model Merge（模型权重线性插值）
  - Data Replay（存储原始轨迹：每类别 80 条）
  - 零样本方法 VLFM（作为额外对比）
- **模型架构**：四种主流架构——RNN-Based、BEV-Based、Transformer-Based、LLM-Based（Qwen2-0.5B）。所有架构共享多模态编码器（CLIP-ResNet50 + 预训练深度编码器），动作解码器各异。

## 4. 资源与算力
- 文中明确说明：所有实验使用 **2 块 NVIDIA A6000 GPU**。
- **未说明训练时长**，仅给出批次大小 32、每阶段训练 25 个 epoch、学习率 3×10⁻⁴ 等超参数。总计算开销未披露。

## 5. 实验数量与充分性
- **主要对比实验**：在 HM3D 和 MP3D 两个数据集上，每种对比方法与四种架构组合，共约 2×5×4 = 40 组（不包括 LLM 和 LoRA 等特殊组合）。结果以表格和折线图展示。
- **消融实验**：四个重要消融——（1）双路径抗遗忘（去除 KD 或 FP）；（2）自适应经验选择 vs 均匀采样和全重放；（3）不同损失权重 λ；（4）阶段顺序敏感性（三种顺序）。每个消融均覆盖多种架构。
- **额外分析**：零样本方法对比（VLFM）、冻结 vs 微调编码器、旧任务 vs 新任务分阶段性能等。
- **充分性与客观性**：实验覆盖多种主流架构和持续学习策略，消融设计全面，指标（SR、SPL）为标准导航评估指标。但在 LLM 架构上，作者指出由于训练数据有限，LLM 表现不突出，说明实验设计考虑了公平性。未报告误差条或统计显著性，但论文声称使用固定种子、结果可复现。

## 6. 主要结论与发现
- C-Nav **在所有数据集和架构上均优于所有基线**，包括 Full Data Replay（全存储原始轨迹）。在 HM3D 上平均 SR 比 Data Replay 高 2.75%，在 MP3D 上高 3.35%。
- 双路径抗遗忘的两个组件**各有贡献**：去除特征蒸馏导致 SR 下降约 22%（HM3D）和 16%（MP3D）；去除特征重放导致下降约 12% 和 10%。
- 自适应经验选择在仅使用 50% 帧的情况下，性能接近使用全部帧，**显著降低存储需求**。且与均匀采样相比，SR 提升约 3.2%~3.65%。
- 对阶段顺序不敏感，证明方法稳定。
- 零样本方法 VLFM 虽能避免遗忘，但缺乏学习能力，性能上限低；C-Nav 可在持续学习过程中持续提升旧任务保留和新任务适应能力。

## 7. 优点
- **首次系统定义持续目标导航问题**并建立标准基准，填补了该领域空白。
- **创新性双路径抗遗忘机制**同时约束编码器表示漂移和解码器策略漂移，实现了比简单重放更好的稳定性-可塑性平衡。
- **自适应经验选择**将关键帧识别转化为离群点检测，理念新颖且高效，显著降低内存消耗。
- **实验广泛**：覆盖四种不同解码器架构（RNN、BEV、Transformer、LLM），验证了方法通用性。
- **性能优异**：在防遗忘的同时，新任务学习能力几乎不受损，甚至在某些情况下超越全重放基线。

## 8. 不足与局限
- **存储开销仍线性增长**：虽然自适应选择减少了每轨迹的存储量，但缓冲区大小随任务数量线性增加，未完全解决长期持续学习的存储累积问题。作者承认未来可探索生成式重放或无轨迹方法。
- **未在真实机器人验证**：实验均在 Habitat 模拟器中进行，未考虑动态光照、传感器噪声、物理交互等真实世界因素，泛化性需实际部署检验。
- **缺乏对 LLM 架构的深度适配**：实验表明 LoRA 在 LLM 模型上优于其他防遗忘方法，但 C-Nav 在 LLM 上的改进幅度相对较小，可能需针对 LLM 定制提示重放或适配技术。
- **计算资源信息不完整**：未报告训练时长、GPU 内存消耗等，不利于复现和评估实用成本。
- **未报告统计显著性检验**：虽然实验设置规范，但未给出误差条或置信区间，存在单次运行结果偏差风险。

（完）
