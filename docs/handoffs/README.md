# 并行任务交接

日期：2026-11-27。以下是待维护者分配的独立任务，不代表已经开工。共同决策见 [ecosystem.md](../ecosystem.md)。已有开发继续按各自阶段执行。

| 任务 | 优先级 | 执行仓库 | 交付形式 |
| --- | --- | --- | --- |
| [Companion GUI 技术实验](companion-gui-probe.md) | P0 | accoding-companion | 隔离实验、双平台产物、报告 |
| [Companion 产品设计](companion-product.md) | P0 | accoding-companion | 设计文档、静态或交互原型 |
| [Companion 业务层审计](companion-core-audit.md) | P1，可选 | accoding-companion | 审计及渐进重构建议 |
| [Routilet GUI 设计](routilet-gui-design.md) | P1，可选 | routilet | 设计文档、原型 |
| [公共视觉规范](visual-guidelines.md) | P1，可与上一项合并 | .github | 简洁规范草案 |

已进行的工作：[Routilet 阶段 01](https://github.com/Routilet/routilet/blob/main/docs/phase-01.md)、Observer 当前正式开发（维持现有负责人及分支，不重新分派）。

## 并行边界

技术实验与产品设计独立；业务审计可同时进行，但正式接口设计应等待产品需求和实验结论。管理器 GUI 原型不依赖阶段 01 代码，也不能改动阶段 01 迁移分支。视觉规范可与界面设计同步，先草案、后协调，不阻塞既有 Observer 开发。

所有执行者在各自独立分支工作，提交 PR 供维护者审核。未获批准不合并、不发布、不修改其他项目；避免跨任务修改同一文件。原型仅使用模拟数据。交付时说明实际提交、结果、限制及待决定事项。

暂缓：多应用安装内核实现、Manager 自更新实现、正式应用协作协议、仓库/npm 重命名、旧 Launcher 退役、共享组件库。阶段 01 完成后按路线图继续。
