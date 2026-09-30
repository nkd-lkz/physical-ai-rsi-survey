[首页](../README.md) / [主题导航](../topics.md) / [全部论文](README.md)

# Generate, Track, Improve: Perceptive Multi-Skill Humanoid Locomotion with RL-Fine-Tuned Motion Generators

> **一句话：** 冻结感知跟踪器，用离策略RL和优势加权流匹配反复微调运动生成器，仿真中改善地形技能选择后部署到Unitree G1；硬件阶段仍是冻结演示，不是机器人边跑边学。

短名：Generate, Track, Improve　作者：Zachary Olkin, William D. Compton, Aaron D. Ames　首次发表：2026-09-25　采用版本：arXiv v1　发表状态：预印本

论文链接：[arXiv:2609.31577](https://arxiv.org/abs/2609.31577)　项目页：[Generate, Track, Improve](https://zolkin1.github.io/generate-track-improve/)　最后核查日期：2026-09-29

![Generate, Track, Improve 原文 Figure 3](https://arxiv.org/html/2609.31577v1/transformer_architectures.png)

*图注：采集生成器rollout、拟合critic、计算优势并以优势加权流匹配更新生成器的离策略循环。来源：原文 Figure 3，arXiv v1。*

## 解决什么问题

感知运动生成器需要从深度输入选择走、跑、跳和上下楼梯等模式，但纯模仿数据无法覆盖部署分布，也可能选择不适合地形的动作。论文希望在保持底层跟踪器的情况下，用任务反馈优化上层全身运动生成器。

## 核心方法

两层系统由规划62步、44维全身轨迹的感知flow-matching生成器，以及冻结的感知跟踪策略构成。仿真中先收集2,000个episode，此后每轮补500个，共5轮；用fitted value iteration训练critic，再以advantage-weighted regression重新训练flow-matching生成器。预训练运动数据以固定权重混入，缓解遗忘；跟踪器始终冻结。

## 主要结果

- IsaacLab中覆盖箱体、楼梯、多地形和分布内场景。作者报告成功率最高增加25个百分点、模式选择最高增加80个百分点；模式指标由每策略/地形50个样本人工标注。
- 单张H100完成5轮、每轮5个epoch约6小时。PPO残差基线在停止于2,000次迭代时已使用超过160倍数据、超过30倍墙钟时间，成功率仍约低13个百分点。
- 冻结策略部署到Unitree G1，展示六种楼梯、连续攀登15级台阶，以及走、跑和箱体跳跃；论文没有为硬件演示给出重复试验的成功率分母。

## 综述可借鉴之处

可用于讨论“改上层生成器还是底层控制器”以及生成模型后训练的预算。其保留原始预训练数据以减轻遗忘，也提示综述应同时记录新地形收益和原有技能保持，而不能只报最佳新任务成功率。

## 证据边界

反馈学习全部发生在仿真和部署之前，奖励与参考运动选择依赖手工设计；真机只运行冻结策略。定量结果主要来自仿真，硬件没有试验分母，论文也把真实硬件数据学习列为未来工作，因此不属于部署后持续改进。

## 原文定位

§§III–V；Figures 1–7；Tables I–II；Appendix。采用arXiv v1；全文RL循环、数据/算力预算、仿真结果与硬件证据边界已核查，未复现。

标签：人形机器人 / 运动生成器 / 离策略RL / flow matching / sim-to-real / 真机演示 / 离线后训练 / 边界案例。
