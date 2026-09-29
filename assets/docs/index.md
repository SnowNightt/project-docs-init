# 文档地图

本页是项目工程文档入口。先读 [Agent 规则](../AGENTS.md)，再按任务阅读相关内容。

| 任务 | 入口 |
| --- | --- |
| 环境、启动和打包 | [README](../README.md) |
| 功能需求与当前行为 | [OpenSpec 当前规格](../openspec/specs/) |
| 新增、修改功能或记录修复 | [OpenSpec 进行中变更](../openspec/changes/)、[开发流程](workflows/development.md) |
| 代码结构和模块边界 | [项目规范](project-conventions.md)、[架构](architecture.md) |
| 编写测试和交付验证 | [测试指南](testing.md) |
| 工程文档变更 | [文档维护规则](documentation.md) |

## OpenSpec 文档位置

- [当前规格](../openspec/specs/)：默认命名为 `openspec/specs/<domain>/spec.md`。
- [进行中变更](../openspec/changes/)：默认目录为 `openspec/changes/<change-name>/`，其中的 `proposal.md`、`design.md`、`tasks.md` 与 `specs/<domain>/spec.md` 分别记录提案、技术设计、任务和规格增量。
- [已归档变更](../openspec/changes/archive/)：默认保存到 `openspec/changes/archive/YYYY-MM-DD-<change-name>/`。
- [项目配置](../openspec/config.yaml)：查看实际使用的 OpenSpec schema 与项目上下文；如调整过配置，以实际生成的结构为准。

功能规格和变更文档只在 OpenSpec 目录中维护。新增工程文档时，在本页登记入口。
