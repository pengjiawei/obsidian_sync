https://arxiv.org/abs/2510.11083
![[Pasted image 20260508101447.png]]

## Model Architechture
### Scene Encoder
直接看上图，具体结构是MLP-Mixer.跳过

### Fine-grained Trajectory Tokenization
第 [3.1](https://arxiv.org/html/2510.11083v1#S3.SS1 "3.1 Problem Formulation ‣ 3 Method ‣ Flow Matching-Based Autonomous Driving Planning with Advanced Interactive Behavior Modeling") 节中引入的噪声轨迹 τt=(x1,x2,…,xL) （总共包含 L 个点）首先被分**割成 K 个片段，每个片段包含 Ls​e​g 个点**。此外，相邻片段之间存在长度为 Lo​v​e​r​l​a​p 的重叠，以确保相似轨迹的一致性和平滑性。接下来，使用共享的多层感知器 (MLP) 将噪声片段转换为自我轨迹标记


### Interaction-enhanced Spatiotemporal Fusion
1. 我们首先通过独立的自适应层归一化（adaLN）模块 [ [43](https://arxiv.org/html/2510.11083v1#bib.bib43) ] 处理异构特征，并将它们投影到一个共享的潜在空间中，其中时间步长条件和导航信息通过调制机制注入 [ [57](https://arxiv.org/html/2510.11083v1#bib.bib57) ] 。然后，将来自同一场景的处理后的标记（包括车道 Fl​a​n​e 、相邻代理 Fn​e​i​g​h​b​o​r 和自我规划轨迹 Fe​g​o 的特征）沿序列维度连接起来：
Fg​l​o​b​a​l=Concat​(adaLN​(Fl​a​n​e),adaLN​(Fn​e​i​g​h​b​o​r),adaLN​(Fe​g​o)).
2. ![[Pasted image 20260508171720.png]]

### Guided Trajectory Generation via Flow Matching
流匹配生成式模型的无分类器引导（Classifier-free Guidance）生成策略能够在推理时（inference-time）灵活地对模型采样的分布进行调整。利用这一机制，Flow Planner能够通过调整周车信息、道路信息等生成条件在模型采样的分布中的权重，放大其对轨迹规划与生成的影响，引导模型生成超越数据的驾驶行为与策略。同时，推理时可调的权重能够帮助模型平衡保守与激进的策略，在交互密集场景中生成更加自然、可控的驾驶行为，提升多模态驾驶行为生成能力。

### 实现细节补充
Channel→Token→Mixer→Mean
![[Pasted image 20260508174310.png]]
其中blocks的定义
![[Pasted image 20260508174407.png]]