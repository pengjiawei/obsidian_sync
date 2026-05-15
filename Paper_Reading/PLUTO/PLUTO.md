https://arxiv.org/html/2404.14327?_immersive_translate_auto_translate=1
### 1 核心创新一：横纵向感知模型架构（Longitudinal-Lateral Aware Architecture）

PLUTO 采用了一种基于 **Query** 的架构，其核心特点是**横纵向解耦与协同**：

- **解耦设计**：不同于很多模型直接输出轨迹点，PLUTO 通过专门的 Query 分别建模车辆的横向（换道、避让）和纵向（加减速、跟车）意图。
    
- **意图融合**：这种设计允许模型学习到更灵活、多样化的驾驶行为，能够更好地处理复杂的城区交通流。

#### 补充参考线的生成部分
![[Pasted image 20260515174647.png]]
#### 同时也解释一下模态部分
实际上也是根据参考线选横向，接着根据经验瞎分配一下纵向
![[Pasted image 20260515180138.png]]

#### 代码planning decoder部分
![[Pasted image 20260515173703.png]]
### 2. 核心创新二：对比模仿学习框架（Contrastive Imitation Learning, CIL）

这是该论文提升模型鲁棒性的关键。PLUTO 引入了对比学习的思想：

- **正负样本对**：模型不仅学习专家（人类驾驶员）是怎么开的（正样本），还通过数据增强生成大量的“负样本”（即不合理或危险的行为）。
    
- **学习目标**：通过 CIL 框架，模型被训练去“拉开”好行为与坏行为之间的距离，从而在交互过程中更明确地知道哪些行为是不可接受的，显著增强了闭环交互的稳定性。
    
![[Pasted image 20260515181420.png]]
### 3. 核心创新三：基于微分插值的辅助损失（Differential Interpolation Auxiliary Loss）
![[Pasted image 20260515181420.png]]
为了提高向量化（Vector-based）模型的训练效率，论文提出了一种创新的辅助损失计算方法：

- **高效计算**：通过微分插值，实现了在 Batch 维度上高效计算复杂的几何约束和动态特性约束。
    
- **引导收敛**：这种辅助损失能够引导模型满足基本的物理规则（如不碰撞、动力学可行性），加速了模型的收敛过程。
####  Regression Loss (`reg_loss`) — 自车轨迹回归
#### Classification Loss (`cls_loss`) — 参考线 + 模式分类
#### Collision Loss (`collision_loss`) — 碰撞惩罚
#### Reference Free Regression Loss (`ref_free_reg_loss`) — 无参考线轨迹回归
#### Prediction Loss (`prediction_loss`) — 其他智能体预测
#### Contrastive Loss (`contrastive_loss`) — 对比学习

这里可能值得一提的就是**差分计算和`contrastive_loss`**

这个差分看起来略微有点奇葩。
![[Pasted image 20260515175732.png]]

