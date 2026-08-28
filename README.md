# Development Log Writer

一个用于 Codex 的开发日志编写 Skill。

它可以根据已有的开发对话、工作记录、调试过程和需求变更，整理出结构化的 Markdown 开发日志，适用于：

- 实习开发过程归档
- 项目开发复盘
- 日常技术日志
- 简历项目素材整理

## 功能特点

- 从已有对话或工作记录中提取事实
- 区分已完成工作、失败尝试、计划事项和待确认内容
- 按开发流程组织日志，而不是机械复述对话时间线
- 覆盖六个核心模块：
  - 需求梳理
  - 技术方案
  - 技术重点
  - 代码处理
  - Bug 修复
  - 需求更新
- 自动补充个人工作复盘
- 默认生成 `development-log.md`

## 安装

### 方法一：使用 Codex Skill Installer

如果本机已经提供 Codex 的 Skill Installer，可以执行：

```bash
python ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo xuanjiong-H/development-log-writer \
  --path . \
  --name development-log-writer
```

Windows PowerShell 示例：

```powershell
python "$HOME\.codex\skills\.system\skill-installer\scripts\install-skill-from-github.py" `
  --repo xuanjiong-H/development-log-writer `
  --path . `
  --name development-log-writer
```

安装脚本会将本 Skill 安装到：

```text
~/.codex/skills/development-log-writer
```

如果自定义了 `CODEX_HOME`，实际安装位置会是：

```text
$CODEX_HOME/skills/development-log-writer
```

### 方法二：手动安装

将本仓库完整复制到 Codex 的 Skills 目录：

```text
~/.codex/skills/development-log-writer
```

安装后的目录中应至少包含：

```text
development-log-writer/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── development-log-rules.md
    └── development-log-template.md
```

Windows 默认目录通常为：

```text
C:\Users\<用户名>\.codex\skills\development-log-writer
```

安装完成后，重新打开 Codex 或开始下一轮对话，使 Skill 生效。

## 使用方式

可以直接使用 Skill 名称调用：

```text
$development-log-writer
```

也可以在提示词中说明任务，例如：

```text
请使用 $development-log-writer，
根据当前开发对话生成一份完整的 Markdown 开发日志。
```

如果需要处理外部记录，可以同时提供文件或文本，并指定输出位置：

```text
请使用 $development-log-writer，
根据这份工作记录生成开发日志，保存到 docs/development-log.md。
```

## 默认工作流程

1. 确定日志来源、主题、日期范围和输出路径。
2. 提取需求、实际操作、错误信息、修复过程和验证结果。
3. 删除重复调试、客套话和与开发无关的内容。
4. 按六个核心模块整理开发过程。
5. 增加个人工作复盘。
6. 检查所有结论是否能够追溯到原始记录。
7. 保存 Markdown 文件并说明覆盖范围及待确认内容。

## 事实边界

本 Skill 只根据用户提供的对话、工作记录或文件生成日志，不补写没有证据支持的内容。

以下内容不会被默认虚构：

- 技术栈和接口
- 文件名和代码实现
- 性能指标
- 用户规模和业务收益
- “已完成”或“已验证”的结果

如果原始记录无法确认某项信息，日志会标记为“原始记录未明确”或将其放入待确认说明。

## 输出结构

生成的日志通常包含以下章节：

```text
1. 需求梳理
2. 技术方案
3. 技术重点
4. 代码处理
5. Bug 修复
6. 需求更新
7. 个人工作复盘
```

## 项目结构

```text
.
├── SKILL.md                              # Skill 主说明和工作流程
├── agents/openai.yaml                    # Codex 界面显示信息
└── references/
    ├── development-log-template.md       # 日志模板
    └── development-log-rules.md          # 事实边界和质量规则
```

## 许可证

当前仓库未提供单独的许可证文件，请以仓库后续发布的许可证声明为准。
