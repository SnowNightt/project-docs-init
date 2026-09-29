---
name: project-docs-init
description: Initialize a software project's agent development rules, documentation map, architecture, testing guidance, and code conventions from user requirements and chosen technologies, then set up OpenSpec for feature specs and changes. Use for new-project setup or explicit adoption in an existing project; not for routine feature work after setup.
---

# 项目规范初始化

将用户给出的功能需求和技术选择转成项目级 Agent 开发规范，并初始化 OpenSpec。功能规格、提案、设计和任务由 OpenSpec 管理，本 Skill 不生成平行的功能 Spec 或变更记录。读取[文档契约](references/document-contract.md)了解交付文件和导航规则；从 `assets/` 改写通用文件，不复制本 Skill 所在项目的业务、技术栈或命令。

## 初始化流程

1. 确认目标项目目录、功能范围、目标平台、已选技术和使用的 AI 工具。检查现有文件、Git 状态、Agent 规则及 OpenSpec 状态。用户只要分析或方案时不编辑文件；已有约定或用户改动不得直接覆盖。
2. 在目标项目按[官方初始化说明](https://github.com/Fission-AI/OpenSpec/blob/main/docs/cli.md)运行 `openspec init`，选择实际使用的 AI 工具；只用 Codex 时可使用 `--tools codex`。CLI 不可用时按官方安装说明准备后再初始化。先检查初始化会影响的现有 OpenSpec 文件或旧工具集成，发现会删除或覆盖用户内容时先说明具体影响。以 CLI 实际生成的目录为准，不手写 OpenSpec 规格或模板。
3. 建立项目级规范文档：根目录 `AGENTS.md`、README；`docs/index.md`、`docs/workflows/development.md`、`docs/documentation.md`、`docs/testing.md`、`docs/project-conventions.md`、`docs/architecture.md`。从 `assets/` 改写通用规则和导航；项目概况、架构、目录规则、测试命令根据实际需求与技术生成。已有同名文档应合并，不覆盖用户修改。
4. 在 `docs/index.md` 链接 OpenSpec 实际生成的 `openspec/specs/`、`openspec/changes/` 和 `openspec/config.yaml`，并说明默认文件命名和归档路径。核对本地链接、命令真实性及工程文档与 OpenSpec 的职责边界。初始化文档完成后，当前及后续功能开发交给 OpenSpec 的变更流程；关键行为有歧义时先澄清，不由本 Skill 写功能约定。
5. 交付前运行项目适用的文档检查和受影响测试，不默认运行全量测试。检查 diff，仅提交本次改动，创建本地 commit；未经用户明确允许不推送。说明生成的规范、OpenSpec 初始化结果、验证和 commit。

## 使用资产

- `assets/AGENTS.md`、`assets/docs/index.md`、`assets/docs/workflows/development.md` 和 `assets/docs/documentation.md` 是通用起点。导航链接在 OpenSpec 初始化后核对。
- `docs/testing.md`、`docs/project-conventions.md`、`docs/architecture.md` 必须按目标项目生成，不使用本仓库的 Electron、Vue、RSS 或其他领域细节。
- 不创建 `docs/specs/`、`docs/changes/` 或本地 Spec、提案、ADR 模板；OpenSpec 的 `openspec/` 是功能规格和变更文档的唯一位置。
