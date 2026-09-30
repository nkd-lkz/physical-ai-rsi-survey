[论文速览表](papers/README.md) · [主题地图](topics.md) · [证据对照](evidence-map.md) · [综述提纲](survey-outline.md)

# 综述写作工作台

**主线：物理经验如何形成可验证、可保留的能力更新？** 每张论文卡片按“问题 → 方法 → 结果 → 引用价值 → 证据边界”阅读；章节则围绕一个问题比较多篇工作。

<!-- stats:start -->
**69 篇阅读卡片** · **141 项原报告条目** · **80 项待核查** · **102 条引文线索**
<!-- stats:end -->

**更新至 2026-09-30** · [当日追加](daily/2026-09-30-follow-up.md) · [早间增量](daily/2026-09-30.md) · [历史日志](daily/)

## 合作者：从这里动笔

| 步骤 | 打开 | 写作产物 |
| :--- | :--- | :--- |
| 定义问题 | [提纲与分类轴](survey-outline.md) | 确定章节要回答的问题、纳入范围与章节间的关系 |
| 搭建比较 | [证据矩阵](evidence-map.md) | 按更新对象、留存范围、真机证据、人工成本和限制做对照表 |
| 追到原文 | [论文速览表](papers/README.md) → [主题地图](topics.md) | 每段选择 2–4 篇，点进卡片核对图表、版本、分母和方法差别 |
| 管理引用 | [BibTeX](references.bib) · [原报告](baseline.md) · [候选](candidates.md) | 正式引用已核查的原文；把尚未逐表核查的线索留在待办区 |

**一个段落的写法：** 提出可检验的问题 → 比较机制与实验条件 → 写出证据支持到哪里、还缺什么。不要把阅读卡片直接连成论文摘要清单。

## 十个研究入口

| 更新什么 | 反馈和物理条件 | 如何评价与组织 |
| :--- | :--- | :--- |
| [策略 / VLA-RL](topics.md#policy) | [奖励 / 验证 / 安全](topics.md#feedback) | [持续与部署学习](topics.md#continual) |
| [世界模型](topics.md#world) | [复位 / 恢复 / 采集](topics.md#infrastructure) | [自动研究与改进器](topics.md#improvers) |
| [技能 / 代码 / harness](topics.md#skills) | [课程 / 任务 / 环境](topics.md#curriculum) | [综述 / 评价方法](topics.md#surveys) |
| [记忆 / 上下文](topics.md#memory) | | |

主题是检索入口，不是证据等级；一篇论文可以出现于多个主题。

## 三组可直接写成小节的对读

| 问题 | 放在一起读 | 要控制的差别 |
| :--- | :--- | :--- |
| “从经验变强”到底更新了什么？ | [FIND](papers/find-agentic-real-world-rl.md) · [Astra Robot Manipulation](papers/robot-manipulation-gpt6-astra.md) · [What Stops RSI](papers/what-stops-recursive-self-improvement-robotics.md) | 策略参数、外部工件与改进流程；各自的人工参与和验收指标 |
| 技能辅助是否变成独立能力？ | [Skill-Space Shooting](papers/skill-space-shooting.md) · [RoboSkill](papers/roboskill-explore-execute-evolve.md) | 修补片段是否写回策略、去掉技能后的成功率、多轮修订是否退化 |
| 新能力是否伴随遗忘？ | [ContinualVLA-Real](papers/continual-vla-real-world.md) · [Pretrained VLA Forgetting](papers/pretrained-vla-forgetting.md) · [FAN](papers/fan.md) | 真机/仿真、本体与动作坐标、回放规模、旧任务保持 |
| 闭环能运行，是否就证明能力增长？ | [HALTER](papers/halter.md) · [LIBERO-RECOVER](papers/libero-recover.md) · [No Free Checker](papers/no-free-checker.md) | 自动复位、恢复能力、验证器可靠性与最终任务收益 |

[更多横向对照与指标口径](evidence-map.md) · [章节可直接展开的综合论点](survey-outline.md#可以直接展开的综合论点)

## 证据使用规则

- **任务内适应**记录重置边界；**持久自我改进**需要跨尝试留存及后续验收；**改进器递归增强**还要证明更新规则自身变化带来后续改进效率。标题中的“RSI / self-evolving”不是证据。
- 正式卡片核查了方法与指定实验，**并未复现**；不同任务的成功率不可直接排名。原报告条目、摘要候选、引文线索和企业自述与正式卡片分开使用。
- 原图标明作者来源、版本与图号；引用前回到原文核对。新增卡片用[固定模板](templates/paper.md)，来源要求见[收录边界](SCOPE.md)。

<details>
<summary>维护入口：数据、生成索引与贡献</summary>

[来源与 awesome 入口](sources.md) · [引文溯源](references.md) · [企业案例](cases/README.md) · [维护规范](MAINTENANCE.md)

结构化数据：[目录](data/catalog.json) · [去重基线](data/baseline.json) · [候选](data/candidates.json) · [引文](data/reference-frontier.json) · [主题导航](data/navigation.json)。修改数据后在仓库根目录运行 `python survey-rsi/scripts/build_index.py`；脚本更新派生索引和本页统计区，不覆盖卡片正文及历史日志。

</details>
