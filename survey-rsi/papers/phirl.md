[首页](../README.md) / [主题导航](../topics.md) / [全部论文](README.md)

# PHIRL: Aligning Learned Rewards with Task Progress for Inverse Reinforcement Learning

> **一句话：** 用少量人标任务进度约束逆强化学习奖励，减少低质示范与奖励投机造成的偏差；为自改进闭环提供更可信的反馈组件。

短名：PHIRL　作者：Hang Yu, James Staley, Cheng Xi Tsou, Xiujin Liu, Wenchang Gao, Jindan Huang, Shijie Fang, Zhegong Shangguan, Angelo Cangelosi, Reuben M. Aronson, Elaine Short　首次发表：2026-09-25　采用版本：arXiv v1　发表状态：预印本

论文链接：[arXiv:2609.31855](https://arxiv.org/abs/2609.31855)　[作者补充材料与代码](https://github.com/PHIRL2026/PHIRL_appendix)　最后核查日期：2026-09-30

![PHIRL 原文 Figure 1](https://arxiv.org/html/2609.31855v1/PHIRL_pipeline_low_res_anon.png)

*图注：示范的部分进度标注与AIRL初始奖励对齐；可选地让微调VLM标注新轨迹继续修订奖励。来源：原文 Fig. 1，arXiv v1。*

## 解决什么问题

从演示反推的奖励可能错误鼓励“反复拿起又放下”之类循环；偏好对比需要持续的人类评判。PHIRL探索用较稀疏、事先标好的任务进度对奖励函数进行约束。

## 核心方法

用AIRL从演示学习初始奖励，再在时间增量、幅值、势函数和完成状态四方面对齐0–100分的进度标注。标准版本只标20%演示；在线扩展让微调的 Gemma 3 12B 为新生成轨迹给进度标签，纳入奖励整形数据。它更新奖励估计，不包含改进器自身规则更新。

## 主要结果

- Robomimic 的 Lift、PickPlaceCan 各采用200条熟练单人示范或六名操作者各50条的混合质量示范；四个基线为AIRL、Pref、AIRL-Pref、Rank2Reward。训练500 episode、10个并行环境，仿真报告100次独立评测的环境回报。Lift 上相对最强基线提高5.6%（高质量）与17.1%（混合质量）；不能把环境回报误写为真机成功率。
- 真机为 Kinova Gen3 Lite 刷落玩偶绒球任务：六位示范者各10条演示，另两人给进度标签；10次评测每次10个绒球。原文报告标准PHIRL刷落73个、在线版84个；AIRL为39个、AIRL-Pref为62个、Pref为58个、Rank2Reward为54个（Fig. 3，按百个绒球累计计）。
- 在线版另加由VLM生成的进度标签，Lift-PH 平均回报188.12→205.08；两个展示的奖励投机情境中，整形奖励能惩罚“抬起再丢下”与“只碰不放”的行为，但这不是对所有投机模式的保证。

## 综述可借鉴之处

反馈章节可比较人工标签成本、VLM标签误差、过程进度与真实任务完成的关系，并把奖励投机作为自我训练可能走偏的具体机制。进度标签是外部监督，不能宣传成完全自主的奖励生成。

## 证据边界

真机仅一个任务、10次轨迹；结果是刷落绒球数，不是任务成功率。基线的训练和真实机器人预算不能与策略自改进论文直接比较。在线VLM标注仍依赖先前人标数据，没有验证改进器规则递归升级；归为反馈支撑组件。

## 原文定位

§§III–V；Figs. 1–4；仿真/真机数据量和基线见§IV-A、结果见§IV-B–D。采用 arXiv v1；主要方法、结果分母和局限已核查，未复现。

标签：支撑组件 / 奖励学习 / 进度监督 / 奖励投机 / 真机单任务 / 非递归。
