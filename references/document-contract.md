# 初始化文档契约

## 职责与文件

| 文件 | 初始化时写什么 | 后续如何维护 |
| --- | --- | --- |
| `AGENTS.md` | Agent 权限、工作边界、OpenSpec 入口、测试和提交规则 | 只放执行规则，不复制详细流程 |
| `docs/index.md` | 工程文档地图，并链接 OpenSpec 的规格、变更和配置位置 | 新工程文档从地图或已登记文档可达 |
| `docs/workflows/development.md` | 阅读项目、使用 OpenSpec、实现、验证和交付的协作步骤 | 与 AGENTS 及 OpenSpec 实际工作流一致 |
| `docs/documentation.md` | 工程文档和 OpenSpec 的职责边界及更新矩阵 | 不在 `docs/` 重复维护功能规格 |
| `docs/testing.md` | 目标技术栈可执行的定向测试、文档检查和构建验证 | 命令须真实存在；尚未配置的检查标为待建 |
| `docs/project-conventions.md` | 根据实际技术选型写目录、命名、模块归属与依赖方向 | 不引入未采用的框架或假想目录 |
| `docs/architecture.md` | 模块、服务、数据边界与计划架构 | 区分目标设计与已实现事实，随实现更新 |

项目 README 说明用途、环境和可执行命令；已有 README 应同步更新。工程文档文件名使用小写英文和连字符，仓库内引用使用相对链接。`docs/testing.md`、`docs/project-conventions.md` 和 `docs/architecture.md` 由目标项目的真实需求和技术选型生成，不套用来源项目内容。

## OpenSpec 接入与导航

先在目标项目运行官方 `openspec init`，选择实际使用的 AI 工具，再生成文档地图并检查链接。默认路径按[OpenSpec 入门文档](https://github.com/Fission-AI/OpenSpec/blob/main/docs/getting-started.md)：

| 内容 | 默认位置 |
| --- | --- |
| 当前功能规格 | `openspec/specs/<domain>/spec.md` |
| 进行中变更 | `openspec/changes/<change-name>/` |
| 变更提案、设计、任务 | 上述变更目录的 `proposal.md`、`design.md`、`tasks.md` |
| 规格增量 | 上述变更目录的 `specs/<domain>/spec.md` |
| 归档变更 | `openspec/changes/archive/YYYY-MM-DD-<change-name>/` |
| 项目配置 | `openspec/config.yaml` |

活动变更目录名使用 `<change-name>`，不预先加日期；日期前缀用于归档目录。文档地图使用实际存在的目录和配置文件作链接，具体文件命名以项目安装的 OpenSpec 版本和配置为准。不要创建 `docs/specs/`、`docs/changes/`、`docs/templates/spec.md` 或 `docs/templates/proposal.md`；也不自定义另一套功能 Spec 状态或提案规则。

## 文档更新矩阵

| 改动 | 同步位置 |
| --- | --- |
| 环境要求、启动、打包命令 | README、测试指南（如涉及验证） |
| 目录、命名、代码归属规则 | 项目规范 |
| 模块边界、数据流、存储、通信 | 架构；本次技术设计使用 OpenSpec 变更的 `design.md` |
| 用户可见行为和业务规则 | OpenSpec 变更文档及其当前规格；不在工程文档中复制 |
| 测试组织、命令、验证要求 | 测试指南 |
| Agent 工作规则和文档流程 | AGENTS、开发流程、文档维护规则 |

## 验收与提交

文档建立后检查链接、技术与命令真实性、OpenSpec 初始化结果，以及工程文档和功能规格没有重复。代码实现后只运行受影响测试及项目配置的文档检查；实际验证和归档按 OpenSpec 工作流处理。未配置的自动检查不能写成已通过。提交前核对相关 OpenSpec 文档与 diff，代码、测试和对应文档进入同一个本地 commit，不夹带其他改动，也不推送远程。
