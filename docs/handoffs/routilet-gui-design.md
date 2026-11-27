# 任务 F：Routilet 管理器 GUI 原型

优先级：P1，可选。执行仓库：[Routilet/routilet](https://github.com/Routilet/routilet)。待分配；允许在阶段 01 进行时独立设计，不是阶段 04 正式实现。

## 目标

设计简洁统一的应用管理入口，为阶段 02 的安装模型和后续 GUI 提供用户需求依据。Companion 与 Observer 是同级可选应用，Exam Kit 是资源依赖。

## 阅读

[共同决策](../ecosystem.md)、[Routilet 架构](https://github.com/Routilet/routilet/blob/main/docs/architecture.md)、[路线图](https://github.com/Routilet/routilet/blob/main/docs/roadmap.md)、[阶段 01 边界](https://github.com/Routilet/routilet/blob/main/docs/phase-01.md)。

## 执行

以模拟数据设计：首页（全部/已安装应用、安装/打开）、安装和更新确认及进度、失败及恢复、回退、卸载和设置。首次无应用、仅安装一个、两个都安装、离线等状态应可理解。更新不得强迫用户立即退出，已安装应用离线可用；卸载与课程数据分离。无需商店服务器、账户系统、远程目录或复杂营销页面。

以最少页面表达实际流程，避免重复操作入口。记录界面所需的最小业务信息，但不冻结安装 API、manifest 或租约协议。可兼任 [公共视觉规范](visual-guidelines.md) 草案任务，避免两个设计者分别定义视觉标准。

## 交付及边界

从 main 建立独立设计分支（不要基于或改动 phase-01/launcher-v2-migration）。新增 docs/gui-product.md 及可独立浏览的原型（如需要，使用 experiments/manager-ui-design/）。提交文档/原型 PR，附关键流程及待评审项。不得接入 Go 安装内核、增加 Wails 到正式项目、修改阶段 01 文件、实现安装/自更新、发布软件。
