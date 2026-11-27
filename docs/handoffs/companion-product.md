# 任务 D：Companion 产品与交互设计（修订）

优先级：P0。执行仓库：[Routilet/accoding-companion](https://github.com/Routilet/accoding-companion)。独立于 Routilet 阶段 01、Observer 开发；不再依赖已取消的 Node GUI 实验。

## 目标

从学生在外部编辑器编程的真实流程出发，设计文件优先、离线优先的 Companion。用户无需了解工作区或初始化项目。打开单文件自动打开父文件夹并选中；新建 C 文件默认引用 Exam Kit；已有源码不擅自修改。以本地测试、资源手册和独立提交源码准备为核心。Observer 可选协作。

## 执行与交付

- 阅读 [共同决策](../ecosystem.md)、旧版 README、架构及实际 TUI/测试代码。
- 新增 docs/companion-gui-product.md、docs/companion-next-roadmap.md 与独立可交互模拟原型；包含首次使用、目录/文件切换、新建、样例编辑、运行/差异/诊断、结果过期、手册、复制源码、Observer 可用性、设置和失败状态。
- 提交独立 PR；原型不操作真实用户文件、不运行编译器、不连接 OJ。人工审核通过后才设计正式接口和存储。
- 不修改旧版业务、依赖、发行流程，不开发 OJ 插件、插件系统、Go 后端、原生集成，不冻结跨应用协议。
