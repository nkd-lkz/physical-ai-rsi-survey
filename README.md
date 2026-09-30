<p align="center"><img src="survey-rsi/assets/cover.svg" alt="Physical AI Self-Improvement Research Library" width="100%"></p>

# 具身智能如何从物理经验中持续改进？

这是一份面向 **Physical AI / 机器人 RSI 综述** 的开放文献库。我们追问：机器人执行后的反馈，究竟更新了什么？更新能保留多久？下一轮任务是否真的变得更好？

**[5 分钟读懂研究问题](#先分清三种改进)** · **[论文速览表](survey-rsi/papers/README.md)** · **[按主题找论文](survey-rsi/topics.md)** · **[比较证据](survey-rsi/evidence-map.md)** · **[开始写综述](survey-rsi/survey-outline.md)**

## 两条阅读路线

| 如果你想…… | 从这里进入 | 你会看到 |
| :--- | :--- | :--- |
| 快速了解领域 | [三种改进](#先分清三种改进) → [主题地图](survey-rsi/topics.md) | 哪些工作改变策略、世界模型、记忆或技能，哪些只是支持闭环运行 |
| 和我们一起写综述 | [写作工作台](survey-rsi/README.md) → [章节提纲](survey-rsi/survey-outline.md) → [证据对照](survey-rsi/evidence-map.md) | 可讨论的章节问题、跨论文对照、证据缺口与引用边界 |
| 扫读或查找论文 | [分组论文速览表](survey-rsi/papers/README.md) | 按问题分组、一句话贡献、综述定位、原文与完整卡片 |

## 先分清三种改进

| 现象 | 要问的关键问题 | 写作中的位置 |
| :--- | :--- | :--- |
| **任务内适应** | 重试、上下文或记忆是否在任务重置后消失？ | 有价值的边界案例，不能直接称为持久学习 |
| **持久自我改进** | 自身执行反馈是否留下参数、程序或记忆更新，并在后续执行中验收？ | 本综述的主要实证对象 |
| **改进器递归增强** | 产生、选择、验证更新的规则本身是否改进，且后续改进效率得到对照验证？ | 更严格的主张，目前需谨慎审查证据 |

我们按 **物理执行 → 反馈 → 更新对象 → 独立验收 → 留存与再执行** 组织文献。这是综述的分析框架，并非任何单篇论文已实现的完整系统。[查看逐篇证据矩阵](survey-rsi/evidence-map.md)。

## 代表论文速览

| 研究问题 | 工作（阅读卡片） | 一句话看点 |
| :--- | :--- | :--- |
| 真机在线策略更新 | [FIND](survey-rsi/papers/find-agentic-real-world-rl.md) | 自选弱项任务并在线更新残差策略；仍有人工场景恢复 |
| 部署后模型更新 | [OSRAM](survey-rsi/papers/osram.md) | 更新闭环模型与参考命令，底层策略保持冻结 |
| 长期经验留存 | [MessyMem](survey-rsi/papers/messymem.md) | 将交互揭示的知识写入持久 3D 场景图 |
| 可执行代码演化 | [AdaHVLA](survey-rsi/papers/adahvla.md) | 根据执行证据修订协调程序，跨任务保留修订记录 |
| 冻结模型经验复用 | [Astra Robot Manipulation](survey-rsi/papers/robot-manipulation-gpt6-astra.md) | 依靠身体知识、经验与局部程序改善操作 |
| 严格递归的证据 | [What Stops RSI](survey-rsi/papers/what-stops-recursive-self-improvement-robotics.md) | 123 轮修改的负结果审计，修改次数不等于能力增长 |
| 持续学习与遗忘 | [ContinualVLA-Real](survey-rsi/papers/continual-vla-real-world.md) | 真机顺序任务中比较遗忘、动作坐标与回放 |
| 反馈可信度 | [No Free Checker](survey-rsi/papers/no-free-checker.md) | 梳理机器人验证器的来源、成本与可信度 |

**[查看全部分组论文速览 →](survey-rsi/papers/README.md)**。上表用于找阅读入口；任务、平台与指标不同，不构成性能排行榜。跨论文对读见[证据矩阵](survey-rsi/evidence-map.md)。

## 资料状态与使用方式

[最新计数与增量日志](survey-rsi/README.md) · [论文速览表](survey-rsi/papers/README.md) · [BibTeX](survey-rsi/references.bib) · [候选队列](survey-rsi/candidates.md)

正式卡片核查了原文方法及指定实验，**结果均为作者报告，尚未独立复现**。原报告旧条目、只读摘要的候选及引文线索分别存放，不能混作已核查证据。引用前请打开卡片所列的原论文版本，核对图、表、分母与人工投入。[来源边界](survey-rsi/SCOPE.md) · [卡片模板](survey-rsi/templates/paper.md) · [维护规范](survey-rsi/MAINTENANCE.md)。
