# Routilet 生态架构与共同决策

日期：2026-11-27。状态：已确定方向，具体接口与实施由各阶段设计落实。

## 产品关系

Routilet 是轻量桌面应用管理器与统一发行入口，不是 Companion 的附属启动器，也不是承载所有业务的综合应用。Companion 和 Observer 是同级、可选、可独立启动的应用；未来应用通过本地目录接入。Exam Kit 是版本化代码与手册资源，默认作为依赖管理，不作为可启动应用展示。

| 项目 | 产品职责 | 当前仓库 / npm 包 |
| --- | --- | --- |
| Routilet | 应用发现、安装、更新、回退、启动、运行环境 | routilet / 目标 @routilet/routilet（尚未发布） |
| Companion | 课程、题目、测试与 OJ 提交 | accoding-companion / @routilet/accoding-companion |
| Observer | 直观呈现程序执行，替代 printf 调试 | c-observer / @routilet/c-observer |
| Exam Kit | 函数资源、脚手架、手册 | c-exam-kit / @routilet/c-exam-kit |

各项目独立仓库、版本、构建、测试。用户可只安装任一应用；卸载一个应用不能破坏另一个应用的必要功能。两者都安装时可通过明确的接口协作；例如 Companion 将观察会话交给 Observer，后者创建独立窗口。没有 Observer 时仍可正常使用 Companion 的本地评测等功能。管理器无需一直驻留；正在运行的应用仍须得到安装快照保护。应用间调用协议尚待设计。

## 分发与运行环境

- GitHub Release 提供首次下载的原生入口；npm 是后续应用、资源及管理器版本分发的内部基础设施。普通用户不需要手动执行 npm 命令或配置 PATH。
- Routilet 以用户选择的应用集合为根依赖；资源与平台二进制可以作为必要或平台依赖。应用之间的可选协作不应造成默认安装另一应用。保留版本化快照、候选校验、原子激活、回退、运行租约和安全清理。
- 初始 Bootstrap 与可更新 Manager 属于同一项目的两个角色；初始入口尽量稳定并能修复失效的 Manager/Node。Manager 单独管理版本，不能随应用卸载。自更新与恢复协议待专门阶段验证。
- 所有原生程序由 CI 预构建，安装不执行 npm 生命周期脚本；保留必要校验。不得在考试时自动下载依赖；日常本地功能断网可用。OJ 导入、登录、提交等联网业务除外，遵守课程规则。
- 用户数据与安装目录分离；更新、卸载、回退不能擅自删除课程源码、资源快照、账号及配置。切换已下载资源版本与修改现有课程资源是两件事。

## GUI、兼容性与签名

以 Windows 11 amd64、macOS Apple Silicon 为新桌面版本的正式支持目标。不主动适配 Windows 10、Intel Mac、Windows ARM64、Linux 或其他旧平台；这不追溯取消旧版已有支持。使用系统 WebView（Windows Evergreen WebView2、macOS WKWebView），不捆绑 Chromium、不固定或自动安装 WebView2、不维护完整 TUI 兼容回退。实际遇到缺失时提供微软官方安装说明。

Go 应用采用已通过真机实验的 Wails v3 + Web 前端方向；Companion 保留 TypeScript/Node.js 业务核心，具体窗口外壳尚待确定，不因统一界面重写后端。保留有独立价值的 CLI。统一设计语言、系统字体、深浅色、状态表达、基本操作与错误提示；不提前建设公共组件库。

Windows 不做可信或自签名；macOS 保留 Apple Silicon 所需 ad-hoc 签名，不做 Developer ID、公证及付费签名服务。未公证软件可能触发 Gatekeeper；提供可信来源的单应用授权说明，不要求用户关闭全局安全机制。只在实际分发遭遇显著障碍时重新评估。

依据：[Observer WebView 测试报告](https://github.com/Routilet/c-observer/blob/experiment/webview/experiments/webview/TEST_REPORT.md)、[签名与兼容性决策](https://github.com/Routilet/c-observer/blob/experiment/webview/experiments/webview/DECISIONS.md)。

## 命名及迁移

用户可见名称统一为 Routilet、Companion、Observer、Exam Kit。目标仓库名为 routilet、companion、observer、exam-kit，npm 目标为 @routilet/ 同名包。现有仓库与已发布包暂不重命名；待各项目迁移验收后制定兼容计划，不破坏已安装用户。Routilet 的开发不阻断 Observer 当前开发。

本文件是组织级共同决策的入口；具体实现及阶段验收以 [Routilet 路线图](https://github.com/Routilet/routilet/blob/main/docs/roadmap.md) 为准。修改共同决策应说明原因、影响及兼容策略，不在单个应用中悄然改变。
