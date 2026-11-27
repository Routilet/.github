# 任务 C：Companion GUI 最小技术实验

**状态：取消。** 2026-11-27 新一代 Companion 决定采用 Go 本地核心 + Wails，暂不开发 OJ 插件；本历史交接不再执行，不要求实验 PR、构建或真机验收。以下保留原任务供追溯。

原优先级：P0。执行仓库：[Routilet/accoding-companion](https://github.com/Routilet/accoding-companion)。待分配，独立于 Routilet 阶段 01 和 Companion 产品设计。

## 目标

保留现有 TypeScript/Node.js 后端，找到能与受管理 Node 运行时协作的轻量系统 WebView 原生窗口方案。不是验证完整业务，也不是重新比较所有桌面框架。

## 阅读

- [组织级共同决策](../ecosystem.md)
- [Companion README](https://github.com/Routilet/accoding-companion/blob/main/README.md)、[架构](https://github.com/Routilet/accoding-companion/blob/main/docs/architecture.md)、[现有启动器 v2](https://github.com/Routilet/accoding-companion/blob/main/docs/launcher-v2.md)
- [Observer WebView 实验](https://github.com/Routilet/c-observer/tree/experiment/webview/experiments/webview)

## 执行

从 main 创建 experiment/companion-webview（若同名已存在先协调），所有实验源码与文档放 experiments/companion-webview/，仅增加必要的隔离 CI。优先评估一条简单路线，例如 Neutralinojs 或 Wails 轻量窗口外壳与 Node 子进程/本地通信；根据官方接口确认可行性，先选一个做最小实验，不要求两种都实现。前端使用本地资源和简单页面。

- 打开独立窗口；按钮调用 Node 中一个示例函数并显示结构化返回值。必要时验证错误返回。
- 使用已有 Node 22+ 运行方式，不要求安装 Go/Rust 或前端构建工具；窗口关闭后清理进程。
- 若采用本地 HTTP，绑定回环地址、限制调用来源、使用随机凭据，不提供任意 shell/文件访问；优先使用更简单的本地 IPC（如适用）。
- CI 预编译 Windows amd64、macOS arm64；构造独立实验 npm tarball，使用隔离目录和 --ignore-scripts 安装验证原生入口定位及资源加载。不得发布 npm。
- 真机验证窗口、交互、Node 调用、离线启动与退出行为。记录产物体积和实际限制，不要求严格性能基准。

## 交付及验收

独立实验分支/PR、双平台 CI artifact、简短技术报告（方案、选择理由、构建与运行结果、已知问题、真机待验收项）。通过标准是两平台最小闭环可运行且分发、生命周期可行。不能实测的项明确标注。

## 不做

不接入真实 OJ、账号、评测、工作区、Observer；不修改现有 TUI/CLI 行为、正式 package.json 或 Launcher；不设计完整 GUI，不改多应用分发模型，不引入签名服务，不发布版本。
