---
name: project-docs-init
description: Initialize a software project from user requirements and chosen technologies by establishing AGENTS.md, a documentation map, feature Specs, change records, development workflow, testing guidance, architecture, and project conventions before coding. Use for new-project setup or when explicitly adopting this documentation system in an existing project; not for routine feature work after setup.
---

# 项目规范初始化

将用户给出的功能需求和技术选择转成可持续维护的工程约定，再开始实现代码。读取 [文档契约](references/document-contract.md) 了解交付文件、状态和更新规则；通用文件从 `assets/` 改写到目标项目，不把本 Skill 所在项目的业务、技术栈或命令复制过去。

## 初始化流程

1. 确认目标项目目录、功能范围、目标平台和已选技术。检查现有文件、Git 状态与已有约定。只根据用户已经明确提供的内容写“已确认”条款；影响用户可见结果的空缺先提问，其他待定项写成草案。用户只要方案时不编辑文件。
2. 先建立项目规范文档：根目录 `AGENTS.md`；`docs/index.md`、`docs/workflows/development.md`、`docs/documentation.md`、`docs/testing.md`、`docs/project-conventions.md`、`docs/architecture.md`、`docs/templates/{spec,proposal,adr}.md`。通用流程和模板以 `assets/` 为起点；项目概况、架构、目录规则、测试命令和链接根据实际需求与技术生成。已有同名文档应合并，不覆盖已确认约定或用户修改。
3. 按用户描述拆分独立功能，每个功能只建一份 `docs/specs/<feature-name>.md`。为本次准备实现的新增或变更功能建立 `docs/changes/YYYY-MM-DD-short-name/proposal.md`，引用相关 Spec。需求明确时记录确认依据；不明确的行为保持待确认，不擅自补全为已确认需求。文档地图登记所有新文件。
4. 先核对文档之间的约定、相对链接、适用命令和用户确认依据。关键约定未确认时，等待用户答复后再实现依赖它的代码；已明确的部分可继续。文档基线完成后才开始项目代码开发，按 Spec 编写针对性测试，并按文档契约维护验收记录。
5. 交付前运行目标项目适用的文档检查和受影响测试，不默认运行全量测试。检查 diff，仅提交本次改动，创建本地 commit；未经用户明确允许不推送。说明文档、实现、验证结果和 commit。Bug 修复另说明复现、原因、预期行为、解决办法和关键代码。

## 使用资产

- `assets/AGENTS.md`、`assets/docs/workflows/development.md` 和 `assets/docs/documentation.md` 是治理规则的起点。按目标项目实际命令和文件结构调整交叉引用。
- `assets/docs/templates/` 是长期 Spec、单次变更提案和 ADR 的模板。不要把模板中的提示文字当成用户已确认的需求。
- `docs/index.md`、`docs/testing.md`、`docs/project-conventions.md`、`docs/architecture.md` 必须根据目标项目生成，不使用本仓库的 Electron、Vue、RSS 或其他领域细节。
