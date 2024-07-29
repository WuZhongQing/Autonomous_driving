# Autonomous_driving
用于记录自动驾驶学习期间的各种知识

## UniAD:Planning-oriented Autonomous Driving
｜[代码](https://github.com/OpenDriveLab/UniAD)｜[论文](https://openaccess.thecvf.com/content/CVPR2023/papers/Hu_Planning-Oriented_Autonomous_Driving_CVPR_2023_paper.pdf)｜2023年 CVPR 上交大|

**论文主要创新点**：

![论文pipeline](./images/UniAD_pipeline.png)

  该论文主要将自动驾驶模型中的感知、预测、规划等不同阶段融合到了一个pipeline中，论文中说这样可以减少错误的累计，个人理解这样确实会减少错误的累积，但是如果出现错误，会不知道是哪一步出错，增加了Debug难度。

1.感知阶段

  感知阶段没有做很多创新，主要是使用了2022年的论文[MOTR:End-to-End Multiple-Object Tracking with Transformer](https://arxiv.org/pdf/2105.03247)|[代码](https://github.com/megvii-research/MOTR)|。该论文沿用DETR的结构，将Object Query迁移到目标跟踪任务中，构造出了Track Query。主要不同点在于：（1）DTER输入为单帧，MOTR为多帧。（2）MOTR中的Track Query是可变的，根据上一帧检测到的目标数量来更新下一帧的MOTR。
