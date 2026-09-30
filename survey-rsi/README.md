<p align="center"><img src="assets/cover.svg" alt="Physical AI · Self-Improvement · Research Library" width="100%"></p>

# 具身 / 机器人 RSI 研究库

面向综述写作，按 **问题 → 方法 → 结果 → 引用价值 → 证据边界** 阅读论文。持续区分任务内适应、可留存的自我改进，以及改进器自身的递归增强。

<!-- stats:start -->
**65 篇阅读卡片** · **141 项原报告条目** · **77 项待核查** · **100 条引文线索**
<!-- stats:end -->

**最近更新：2026-09-30** · [当日增量调研](daily/2026-09-30.md) · [9月29日调研](daily/2026-09-29.md) · [9月28日调研](daily/2026-09-28.md) · [历史日志](daily/)

## 收录范围

本库只收录**公开论文、作者项目/代码、可追溯行业来源，以及基于这些来源的综述分析**。每篇采用固定阅读模板，保留原图来源、指标口径和证据边界。项目方案、个人研究假设与实验进度不属于本库内容。

[四类 Physical RSI 线索对照](discussions/physical-rsi-sept24.md) · [企业系统案例](cases/README.md) · [来源边界](SCOPE.md) · [本次整理说明](daily/2026-09-26-boundary-cleanup.md)

## 从这里开始

| 我想做什么 | 阅读入口 |
| :--- | :--- |
| 找某个方向的相关工作 | **[按主题浏览](topics.md)** — 策略、世界模型、技能、记忆、持续学习等 10 个入口 |
| 判断一篇工作究竟证明了什么 | **[证据对照](evidence-map.md)** — 更新对象、保留范围、物理证据、关键限制 |
| 开始组织综述章节 | **[综述提纲与分类轴](survey-outline.md)** — 章节问题、已有支撑和还缺的证据 |
| 搜题名、短名或 arXiv ID | **[全部阅读卡片](papers/README.md)** · **[原报告 141 项](baseline.md)** |
| 接着读下一批论文 | **[候选队列](candidates.md)** · **[引文溯源](references.md)** |
| 导入文献管理器或 LaTeX | **[BibTeX](references.bib)** — 阅读卡片对应的 arXiv 元数据 |

## 本轮先读这三篇

| 工作 | 为什么值得读 | 放到综述哪里 |
| :--- | :--- | :--- |
| **[FIND](papers/find-agentic-real-world-rl.md)** | 5个独立种子、每20k步独立人评，并披露6小时运行中的30次人工恢复；是当前较完整的真机持久改进证据 | 真机在线VLA-RL、自动课程、自评可信度、复位与人工预算 |
| **[What Stops RSI in Robotics](papers/what-stops-recursive-self-improvement-robotics.md)** | 123轮持续修改仍未完成目标任务，并记录113次人工harness修复；提供少见的改进器失败审计 | 严格递归判据、长程信用分配、harness对照、负结果 |
| **[Astra Robot Manipulation](papers/robot-manipulation-gpt6-astra.md)** | 将身体知识、同步经验和可执行技能分开比较，并给出仿真与12次真机结果 | 非参数经验复用、代码技能、sim-to-real、持久更新边界 |

三篇形成“持久参数更新—冻结模型工件复用—外层改进器审计”的对照。FIND仍使用预定义可逆任务库与固定外层机制；Astra技能经过研究者重构；123轮报告是单系统仿真负结果。全部结果均为作者报告，未复现。

## 按综述主线浏览

| 能力更新 | 反馈与运行条件 | 评价与组织 |
| :--- | :--- | :--- |
| [策略 / VLA-RL](topics.md#policy) | [奖励 / 验证 / 安全](topics.md#feedback) | [持续与部署学习](topics.md#continual) |
| [世界模型](topics.md#world) | [复位 / 恢复 / 采集](topics.md#infrastructure) | [自动研究与改进器](topics.md#improvers) |
| [技能 / 代码 / harness](topics.md#skills) | [课程 / 任务 / 环境](topics.md#curriculum) | [综述 / 评价方法](topics.md#surveys) |
| [记忆 / 上下文](topics.md#memory) | | |

## 阅读时保留的三个区别

- **任务内适应**：重试、重规划或上下文更新帮助当前任务；需要说明重置边界。
- **持久自我改进**：自身执行反馈形成可留存更新，并评估后续能力；不等于完全无人参与。
- **改进器递归增强**：生成、选择或执行更新的机制本身被修改，且后续改进能力得到验证。标题出现 RSI 不足以证明这一点。

[RegenHarness](papers/regenharness.md) 当前展示的是执行案例与版本化修订协议；[LEMCA](papers/lemca.md) 演化的是控制架构。两者都不应只凭“harness / 演化 / 改进器”用词升级为严格递归实证。

<details>
<summary><strong>证据、来源与维护</strong></summary>

- 正式卡片：方法及指定实验/表格已核查，均未复现；原图注明版本和图号。
- 原报告条目：保留公开题名和链接，未逐项重新核查，不与新增卡片混算。
- 候选与引文：不等于全文已读；只读摘要时不填猜测结果。
- [来源与 awesome 入口](sources.md) · [阅读模板](templates/paper.md) · [维护规范](MAINTENANCE.md)
- [结构化目录](data/catalog.json) · [去重基线](data/baseline.json) · [候选数据](data/candidates.json) · [引文数据](data/reference-frontier.json)
- 修改数据后运行 `python survey-rsi/scripts/build_index.py`；首页正文、论文卡片与历史日志保留人工编辑。

</details>
