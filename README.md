# project-docs-init

用于在新项目或现有项目中建立 Agent 开发规范、工程文档导航，并初始化 OpenSpec。功能规格和变更文档由 OpenSpec 管理。

## 安装

### 1. 安装 OpenSpec CLI

此 skill 在执行时需要 `openspec` 命令。先确认 Node.js 版本不低于 20.19.0，再安装并验证 CLI：

```powershell
node --version
npm install -g @fission-ai/openspec@latest
openspec --version
```

已安装 OpenSpec CLI 时，可以跳过 `npm install`。其他包管理器的安装方式见 [OpenSpec 官方安装文档](https://openspec.dev/docs/installation)。

### 2. 安装 Codex skill

在 PowerShell 中将本仓库克隆到 Codex 的用户级 skills 目录：

```powershell
New-Item -ItemType Directory -Force "$HOME/.agents/skills" | Out-Null
git clone https://github.com/SnowNightt/project-docs-init.git "$HOME/.agents/skills/project-docs-init"
```

Codex 会从该目录发现 `project-docs-init`。如果安装后没有显示，重启 Codex。已有安装可在该目录运行 `git pull --ff-only` 更新：

```powershell
git -C "$HOME/.agents/skills/project-docs-init" pull --ff-only
```

Codex 的 skill 搜索位置和调用方式见 [OpenAI Docs](https://learn.chatgpt.com/docs/build-skills)。

## 使用

在 Codex 中打开目标项目，明确提供功能需求、目标平台和已确定的技术选型，然后调用：

```text
$project-docs-init 请根据这个项目的需求和技术选型初始化项目规范与 OpenSpec。
```

skill 会在**目标项目**运行 `openspec init --tools none`，创建 OpenSpec 项目结构，并生成或合并 `AGENTS.md`、README 和 `docs/` 下的工程文档。`--tools none` 不会在目标项目生成 `.agents/skills/openspec-*` 等 AI 工具集成文件；安装本 skill 也不会自动初始化任何项目。已有同名文档会先检查并合并，不直接覆盖用户改动。

详细流程见 [SKILL.md](SKILL.md)。
