# 任务 D：Companion 产品与交互设计

优先级：P0。执行仓库：[Routilet/accoding-companion](https://github.com/Routilet/accoding-companion)。待分配；不依赖 GUI 技术实验或 Routilet 阶段 01。

## 目标

重新组织现有课程编程助手的功能和信息，而非逐页照搬 TUI。用户继续在外部 IDE 编写代码，Companion 提供课程管理、评测、提交和资料查阅。

## 阅读

[共同决策](../ecosystem.md)、[Companion README](https://github.com/Routilet/accoding-companion/blob/main/README.md)、[架构](https://github.com/Routilet/accoding-companion/blob/main/docs/architecture.md)。核对 src/standalone/tui.tsx、manual.tsx、sample-output.tsx 等真实能力；区分已实现、拟新增和待删除。

## 执行

- 梳理学生的核心工作流：首次配置、课程/比赛导入、题目选择、外部编辑、本地测试及差异定位、提交、查阅手册、调用 Observer。
- 提出最简信息架构及功能保留/合并/简化建议。关注导航与题目状态、题面、样例编辑与对比、编译诊断、提交状态和历史。
- 设计函数手册的搜索、浏览及代码复制；评估独立窗口。Observer 保持独立窗口；未安装时仍可使用 Companion。
- 考虑离线、失败、空状态、中文、多行文本和键盘高频操作；不把安装管理器功能放进 Companion。
- 用静态或可交互 HTML/SVG 原型（模拟数据）表现主要工作流，优先信息组织，不追求完整组件库或视觉细节。

## 交付及边界

在独立分支新增 docs/companion-gui-product.md 及独立原型（如需要），提交 PR；列出关键决策、待维护者评审的问题及与现有功能的差异。不要修改业务代码或现有 TUI，不开发编辑器、不替代 IDE、不嵌入 Observer、不冻结跨应用协议、不确定窗口技术选型。产品方案需经维护者评审，后续才进入正式实现。
