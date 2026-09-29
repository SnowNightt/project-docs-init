# Agent 开发流程

工程协作规则在根目录 AGENTS 和本目录的文档中；功能规格、变更提案、设计与任务由 OpenSpec 在 `openspec/` 中维护。不要在 `docs/` 下建立第二套功能规格或变更目录。

## 1. 阅读项目上下文

先读[AGENTS](../../AGENTS.md)和[文档地图](../index.md)，再读相关[架构](../architecture.md)、[项目规范](../project-conventions.md)、OpenSpec 规格与变更文档、代码、测试和工作区未提交改动。用户只要求分析或方案时不修改文件。

## 2. 使用 OpenSpec 准备变化

功能新增、行为变化及需要记录的修复，使用项目安装的 OpenSpec 工作流创建和维护变更文档。当前规格默认位于 `openspec/specs/<domain>/spec.md`；进行中变更默认位于 `openspec/changes/<change-name>/`，其中包括 `proposal.md`、`design.md`、`tasks.md` 和 `specs/<domain>/spec.md`。以项目实际 OpenSpec 配置和命令输出为准，不手写另一套模板。

阅读并核对变更文档与用户要求。用户已明确要求的具体变化无需重复询问；Agent 提出的行为变化或影响结果的歧义须先确认，未回复不算同意。不能把当前代码行为直接认定为正确需求。

## 3. 实现与验证

按已审阅的 OpenSpec 变更文档实现，编写或更新受影响测试。实现中发现需求或设计需要调整时，回到同一 OpenSpec 变更中更新相应文档，按其工作流继续。按[更新矩阵](../documentation.md#更新矩阵)同步工程文档，不在工程文档中重复维护功能约定。

按[测试指南](../testing.md)只运行相关测试和适用的文档检查，不默认运行全量测试。记录实际命令、结果和未验证事项；按项目安装的 OpenSpec 工作流完成验证、同步与归档。

## 4. 提交与交付

检查相关 OpenSpec 文档和 diff，只提交本次代码、测试和文档，创建本地 commit，未经允许不推送。说明改动、验证结果、文档更新和 commit。修复 Bug 时说明复现、原因、预期结果、解决办法和关键代码。
