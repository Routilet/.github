# 并行任务交接

日期：2026-11-27。共同决策见 [ecosystem.md](../ecosystem.md)，启动台进度见 [Routilet 路线图](https://github.com/Routilet/routilet/blob/main/docs/roadmap.md)。

| 任务 | 状态 | 执行仓库 |
| --- | --- | --- |
| [Companion GUI 技术实验](companion-gui-probe.md) | 历史预研，原 TS/Node 外壳方案已不作为新版约束 | accoding-companion |
| [Companion 产品设计](companion-product.md) | 新版方向由该项目继续验证 | accoding-companion |
| [Companion 业务层审计](companion-core-audit.md) | 历史参考，既有 TS 实现迁移时可参考 | accoding-companion |
| [Routilet GUI 设计](routilet-gui-design.md) | 初版已独立发行，历史设计任务结束 | routilet |
| [公共视觉规范](visual-guidelines.md) | 参考；图标定稿见 [图标设计说明](../icon-design.md) | .github |

Routilet v0.1.0 已发行；v0.1.1 收尾及真实升级待验收。原 Launcher v2 阶段 01 [历史归档](https://github.com/Routilet/routilet/tree/archive/launcher-v2)。Observer 与 Companion 继续各自开发，真实应用接入以兼容发行包为前提。上表历史交接不覆盖最新生态决策。

## 并行边界

各应用独立开发与发行；不为未就绪的应用提前定死协作协议。正式接口随实际接入验证。未获维护者批准不合并、不发布、不修改其他项目；已批准的共同品牌资产可按组织图标说明同步。区分模拟测试、真实 npm 测试与实机验收。

暂缓：正式应用协作协议、仓库/npm 重命名、共享组件库及其他非必要抽象。
