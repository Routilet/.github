# 任务 E：Companion 业务层审计

优先级：P1，可选。执行仓库：[Routilet/accoding-companion](https://github.com/Routilet/accoding-companion)。待分配，可与技术实验及产品设计并行。

## 目标

找出 GUI 和 CLI 复用业务逻辑的真实障碍，提出最小、可回归验证的重构顺序。本轮仅审计，不实施重构。

## 阅读及检查

[共同决策](../ecosystem.md)、[Companion 架构](https://github.com/Routilet/accoding-companion/blob/main/docs/architecture.md)、src/standalone/workflow.ts、app.ts、tui.tsx、terminal.ts，以及 src/accoding、auth、judge、workspace、submissions、scaffold、preset-manager、observer 和现有测试。以实际代码为准，不将文件名当作职责证明。

- 区分可直接复用模块、终端相关模块、同时承担业务与交互的模块；指出具体函数/调用位置，如 ask、confirm、select、password、console.log。
- 审计测试快照与提交一致性、凭据保护、工作区/资源版本兼容、异步评测与提交状态、Observer 会话清理等不可破坏的行为。
- 评估哪些能力已有结构化接口，哪些需要参数、返回值、进度或错误事件；记录现有测试覆盖及必要增量测试。
- 提出渐进重构顺序及风险，明确产品设计确认前不冻结正式 API；尽量保留现有 Node 后端与 CLI。

## 交付及边界

独立分支新增 docs/companion-core-audit.md，包含代码引用、模块清单、耦合点、风险、推荐重构步骤与验收建议；提交文档 PR。不修改运行代码、依赖、工作区格式、凭据后端、OJ 协议或正式发行。不要建设通用 RPC 框架。
