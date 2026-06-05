---
title: "GauDP: Reinventing Multi-Agent Collaboration through Gaussian-Image Synergy in Diffusion Policies"
title_zh: GauDP：通过扩散策略中的高斯-图像协同重新发明多智能体协作
authors: "Ziye Wang, Li Kang, Yiran Qin, Jiahua Ma, zhanglin peng, LEI BAI, Ruimao Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=asS4W7Yw5e"
tags: ["query:agent-papers"]
score: 7.0
evidence: 提出GauDP使用高斯-图像协同表示进行多智能体协作
tldr: 现有方法在平衡局部控制与全局场景理解上存在困难，制约了多智能体协作的可扩展性。本文提出GauDP，通过重构全局一致性3D高斯场从局部RGB图像，实现感知感知的模仿学习。实验表明该方法在多个多智能体协作任务上显著提升协调质量和可扩展性，为多智能体系统提供了新的表示范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ass4w7yw5e/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1310, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ass4w7yw5e/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1310, \"height\": 764, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ass4w7yw5e/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1378, \"height\": 928, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ass4w7yw5e/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 661, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ass4w7yw5e/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1335, \"height\": 475, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ass4w7yw5e/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 936, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ass4w7yw5e/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1450, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ass4w7yw5e/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1208, \"height\": 438, \"label\": \"Table\"}]"
motivation: 多智能体协作中局部控制与全局场景理解难以平衡，现有方法可扩展性差。
method: 提出GauDP，从局部RGB图像重构全局3D高斯场，结合扩散策略进行模仿学习。
result: 在多个协作任务上，GauDP相比基线提高了协调质量和可扩展性。
conclusion: 高斯-图像协同表示有效融合局部与全局信息，促进了多智能体协作。
---

## Abstract
Despite significant advances in robotic policy generation, effective coordination in embodied multi-agent systems remains a fundamental challenge—particularly in scenarios where agents must balance individual perspectives with global environmental awareness.
Existing approaches often struggle to balance fine-grained local control with comprehensive scene understanding, resulting in limited scalability and compromised collaboration quality.
In this paper, we present GauDP, a novel Gaussian-image synergistic representation that facilitates scalable, perception-aware imitation learning in multi-agent collaborative systems.
Specifically, GauDP reconstructs a globally consistent 3D Gaussian field from local-view RGB images, allowing all agents to dynamically query task-relevant features from a shared scene representation. 
This design facilitates both fine-grained control and globally coherent behavior without requiring additional sensing modalities. 
We evaluate GauDP on the RoboFactory benchmark, which includes diverse multi-arm manipulation tasks. 
Our method achieves superior performance over existing image-based methods and approaches the effectiveness of point-cloud-driven methods, while maintaining strong scalability as the number of agents increases. 
Extensive ablations and visualizations further demonstrate the robustness and efficiency of our unified local-global perception framework for multi-agent embodied learning.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

多智能体具身协作（如工业装配、手术机器人、家庭辅助）面临的根本挑战是如何平衡**个体视角的精细控制**与**全局环境感知的协调**。现有方法分为两类：
- **仅使用局部观测**（各智能体独立图像）：虽保留精细操作细节，但缺乏全局空间关系，易导致碰撞或任务脱节。
- **仅使用全局观测**（全景图像或点云）：提供全局一致性，但丢失智能体特有的高分辨率局部信息，降低操控精度。

因此，核心问题是：**如何设计一种统一表示，能同时编码全局一致性与局部精度，并实现高效的多智能体协调？** 论文提出 **GauDP**，通过从多视角RGB图像重构3D高斯场，将全局场景理解与智能体个性化查询相结合，实现可扩展、感知驱动的模仿学习。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
利用**3D高斯泼溅（3D Gaussian Splatting, 3DGS）** 作为中间表示，从各智能体局部RGB观测中重建全局一致的三维高斯场，再动态分配与每个智能体视角相关的子集，实现局部-全局像素级融合，最后通过扩散策略生成动作序列。

### 关键技术细节
1. **全局上下文重建（Global Context Reconstruction）**  
   - 采用 **Noposplat**（一种无需姿态的feed-forward网络）从稀疏、无位姿的多视角RGB图像直接预测3D高斯参数。  
   - 每个RGB图像经共享权重的ViT编码器提取特征，经跨视角交叉注意力融合，再由高斯参数预测头输出每个像素对应的3D高斯（位置、缩放、旋转、不透明度、颜色等）。  
   - 微调时引入**深度监督**：在渲染过程中除了RGB损失，还计算深度图的渲染损失 \( \mathcal{L}_{depth} \)，总重建损失 \( \mathcal{L}_{rec} = \mathcal{L}_{rgb} + \alpha \mathcal{L}_{depth} \)。  
   - 深度和相机位姿仅在微调阶段使用，推理时仅依赖多视角RGB，实现轻量、无位姿的部署。

2. **全局上下文分配与像素级融合（Global Context Allocation and Pixel-level Synergy）**  
   - 重建后的3D高斯场自然与输入图像像素对齐，因此每个智能体只接收与其自身视角相关的高斯子集（这些高斯已通过跨视角融合包含了其他视角的信息）。  
   - 将选中的高斯参数重新投影回2D网格，与智能体的局部图像特征拼接，再经轻量卷积融合模块进行**像素级融合**，实现局部与全局细粒度对齐。

3. **扩散策略（Diffusion Policy）**  
   - 采用DDPM (Denoising Diffusion Probabilistic Models) 作为动作生成器，条件为局部图像特征与融合后的全局上下文，预测未来L步动作序列 \( a = \{a_1, a_2, ..., a_L\} \)。  
   - 反向扩散过程：\( p_\Phi(a_{k-1} | a_k, O, G) = \mathcal{N}(\mu_\Phi, \Sigma_\Phi) \)，通过迭代去噪生成动作。

### 公式算法流程（文字说明）
- 输入：N个视角的同步RGB图像 \( O = \{I_1,...,I_N\} \)。  
- 步骤1：每个图像经共享ViT编码，跨视角交叉注意力得到融合特征。  
- 步骤2：预测每个像素对应的3D高斯参数，形成全局高斯场 \( G \)。  
- 步骤3：对每个智能体，从G中提取与该智能体视角对应的高斯子集，映射回2D网格，与局部图像特征像素级融合。  
- 步骤4：融合特征经扩散策略的条件网络，输出动作序列 \( a \)。

## 3. 实验设计

### 数据集与基准
- **RoboFactory** 基准 [1]，包含6个多臂协作任务（2-4臂）：Lift Barrier, Place Food, Stack Cube, Align Camera, Stack Cube (3臂), Take Photo (4臂)。  
- 任务涵盖不同协调复杂度与物理交互模式。

### 对比方法
- **2D图像方法**：Diffusion Policy (DP), 2D Dense Policy。  
- **3D点云方法**：3D Diffusion Policy (DP3) 及其RGB版本（DP3 XYZ+RGB），3D Dense Policy。  
- 所有方法使用相同视觉骨干（ResNet-18用于2D，轻量MLP用于3D）。

### 评估指标
- **成功率（Success Rate）**，每100训练epoch在100个episode上评估。

## 4. 资源与算力

论文明确说明：
- 训练与评估在 **单张NVIDIA A800 GPU** 上进行。  
- 训练100 epoch，batch size=32，使用Adam优化器，初始学习率 \( 10^{-4} \)，带预热和余弦衰减。  
- 训练时间：GauDP约6.5 GPU小时（Lift Barrier任务），DP约4.8小时，DP3约2.5小时。  
- 推理速度：GauDP约1.28 FPS（NVIDIA RTX 5090 GPU），DP为1.49 FPS，DP3为1.57 FPS。  
- 算力信息充分，对比公平。

## 5. 实验数量与充分性

- **主实验**：6个任务 × 6种方法（包括GauDP），共36组成功率结果。  
- **消融实验**：3组（坐标系统、融合策略、是否使用图像/高斯），共4个变体 × 6个任务（部分任务结果为零）。  
- **真实机器人实验**：3个任务（Card Box Stacking, Card Box Handover, Grab Roller），比较DP与GauDP，每个任务30次rollout。  
- **重建质量评估**：PSNR、SSIM、LPIPS对比预训练模型与微调模型。  
- **训练/推理效率**：一张表。  
- 实验覆盖了模拟与真实场景，消融验证了各组件必要性，对比基线全面（2D、3D、点云、图像），公平性较好（相同骨干、超参数、优化设置）。但部分任务成功率较低（如Stack Cube为0%），可能反映任务难度高或方法局限性，实验充分性可接受但未提供置信区间或误差线（论文检查表提到应有，但正文表2/3/4未含误差）。

## 6. 论文的主要结论与发现

1. **GauDP显著优于所有图像基线**：平均成功率19.67%，远超DP（5.00%）和2D Dense Policy（2.33%）。  
2. **接近甚至超越点云方法**：GauDP使用纯RGB输入，平均成功率高于DP3（14.33%）和3D Dense Policy（8.83%）。  
3. **协调能力提升**：在需要全局对齐的任务（如Align Camera）中，GauDP达26%，DP3仅18%；在精细操作（如Place Food）也表现出色（15% vs 25%的DP3点云版）。  
4. **消融实验显示**：  
   - 本地坐标系统优于统一世界坐标（避免对齐误差）。  
   - 像素级融合优于粗特征拼接。  
   - 同时使用图像和高斯表示优于只使用其中一种。  
5. **重建质量**：微调后的3D高斯重建显著优于预训练模型（PSNR从17.9升至23.4，SSIM 0.58→0.78，LPIPS 0.49→0.15）。  
6. **真实世界验证**：GauDP在三个任务上均优于DP，尤其堆叠和交接任务。

## 7. 优点

- **创新性表示**：将3D高斯作为局部-全局统一的中间表示，实现无需点云或深度传感器即可获得3D结构信息。  
- **高效跨模态融合**：像素级的高斯-图像协同融合，保留了空间对齐与任务相关特征。  
- **可扩展性**：高斯表示天然支持增加智能体数量，无需改变架构。  
- **自监督重建**：利用多视角一致性自监督训练，无需额外标注。  
- **部署轻量**：推理时不需相机位姿和深度，仅需RGB。  
- **实验全面**：对比了多种主流方法（2D/3D、点云/图像），且包含真实机器人实验。

## 8. 不足与局限

- **任务覆盖有限**：仅测试了RoboFactory的6个任务，且部分任务成功率极低（如Stack Cube 0%），泛化性存疑。  
- **方法依赖微调**：Noposplat需要针对具体场景微调（使用深度图），虽然推理时无需深度，但微调阶段仍需深度数据。  
- **计算开销**：相比DP3，训练时间更长（6.5 vs 2.5 GPU小时），推理速度略慢（1.28 vs 1.57 FPS）。  
- **误差/置信区间缺失**：实验报告的平均成功率未提供置信区间或标准差，统计显著性不确定。  
- **未讨论失败案例**：未分析为何某些任务（如Stack Cube）完全失败，原因可能是任务难度或方法局限性。  
- **应用限制**：假设多视角同步观测，且相机相对位置固定（尽管无位姿），在动态场景或视角变化剧烈时可能失效。  
- **仅验证了模仿学习**：未涉及强化学习或在线学习场景。

（完）
