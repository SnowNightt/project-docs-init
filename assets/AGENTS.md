## 注意事项

- 只有用户明确要求修改时才编辑文件；只要求分析或方案时，不修改文件。
- 每组相关改动完成后创建对应的本地 Git commit。未经用户明确允许，不推送到远程仓库。
- 为代码行为变更和 Bug 修复编写或更新相关测试，只运行受影响的测试；交付前确保相关验证通过。
- 实现保持直接、清晰，不添加无依据的防御和兜底逻辑。
- 修复 Bug 后说明复现方式、错误原因、预期行为、解决办法、回归结果，并附关键修复代码。

## 项目规范

- 开始任务先读[文档地图](docs/index.md)，再按任务类型阅读相关文档、Spec 和测试。
- 目录、命名和代码归属遵循[项目规范](docs/project-conventions.md)；系统边界见[架构](docs/architecture.md)。

## Spec 与交付流程

- 遵循[开发流程](docs/workflows/development.md)和[文档维护规则](docs/documentation.md)。每个功能只维护一份长期有效的 Spec，使用[模板](docs/templates/spec.md)，保存在 `docs/specs/<feature-name>.md` 并登记到文档地图。
- 已确认 Spec 约束行为、限制和验收标准。AI 不得自行改变；实质变更必须有用户对具体变化的明确确认，实现困难时调整实现方案。
- 只有新增或变更功能需要按[模板](docs/templates/proposal.md)创建 `docs/changes/YYYY-MM-DD-short-name/proposal.md`，引用对应 Spec 并登记到文档地图。所有 Bug 修复都不需要提案；纯措辞修改也不需要。
- 具体变化已获用户确认时无需重复询问；关键歧义先澄清。确认后更新原功能 Spec，再实现；未确认内容留在提案。计划和任务清单按需放在本次变更目录，不写进长期 Spec。
- 修改后按[更新矩阵](docs/documentation.md#更新矩阵)同步文档，运行[测试指南](docs/testing.md)中受影响的测试与适用文档检查，不运行全量测试。
- 交付前核对 Spec 与 diff。新增或变更功能的实际验收结果记在提案或任务清单；Bug 修复的验证结果记在本次回复。功能 Spec 完成实现后仍为“已确认”；“实现中、已完成”只用于变更记录。说明测试、文档和本地 commit。
