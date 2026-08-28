---
name: development-log-writer
description: Turn development conversations, work records, debugging discussions, and requirement changes into accurate Markdown development logs for internship archives, project retrospectives, and resume material. Use when the user asks to generate a development completion log, internship work log, project development retrospective, daily technical log, 需求日志记录, 实习日志, 开发完成日志, 项目复盘 or resume-oriented summary from existing conversation records.
---

# Development Log Writer

根据已有对话和工作记录，还原已经完成的技术开发工作，生成适合实习归档、项目复盘和简历素材提炼的 Markdown 日志。以原始记录为唯一事实来源，优先保留真实的个人实操、问题解决和需求落地过程。

## Workflow

1. 确定日志来源、主题、日期范围和输出路径。
   - 以当前对话为来源时，使用当前对话中已经发生的工作记录。
   - 用户提供文件、聊天记录或文本时，先读取并识别有效开发信息。
   - 用户明确指定输出路径时严格使用该路径。
   - 未指定输出路径时，保存到当前项目目录的 `development-log.md`。
2. 提取事实记录，区分已完成工作、尝试过程、计划事项、失败尝试和待确认内容。
3. 过滤无效信息、重复调试、客套话、空白内容和与技术开发无关的内容。
4. 将有效信息按开发流程归入六个核心模块：
   - 需求梳理
   - 技术方案
   - 技术重点
   - 代码处理
   - Bug 修复
   - 需求更新
5. 对每项技术内容保留“问题或目标、实际操作、结果或影响”的因果关系。
6. 按 `references/development-log-template.md` 生成 Markdown，并遵守 `references/development-log-rules.md`。
7. 增加简短的个人工作复盘，概括能够从原始记录直接支持的技术积累和能力提升。
8. 生成前检查：所有事实都能回溯到原始记录；未确认内容已标注；六个核心模块和工作复盘均已存在；没有流水账段落。
9. 保存日志文件并报告输出路径、覆盖范围和未能确认的内容。

## Completion Criteria

只有满足以下条件才算完成：

- 已生成一个可打开的 Markdown 文件。
- 文件包含六个核心模块和个人工作复盘。
- 所有技术结论均来自原始对话或用户提供的记录。
- 重复和无效信息已被压缩或删除。
- 需求、方案、技术重点、代码、Bug 和迭代之间的关系清晰。
- 对话未明确的事实被放入待确认说明，而不是被写成已完成成果。

## Fact Handling

- 将“已执行、已修改、已验证、已解决”等明确动作写入完成日志。
- 将“准备、计划、可以、建议、后续”等内容保留为计划或待确认事项，不改写成已完成。
- 保留关键失败尝试，前提是它能说明排查思路或最终解决路径。
- 对原始记录没有说明的技术栈、接口、代码文件、性能数据和业务收益不做推断。
- 不直接修改业务代码；本 Skill 的交付物是日志 Markdown 文件。

## Output Requirements

- 使用正式、专业、书面化的技术表达。
- 突出个人实际操作、问题分析、技术决策和落地结果。
- 核心技术点和明确成果可以适度加粗。
- 以开发工作流程组织内容，不机械复制对话时间线。
- 不写成纯简历句子；保留足够的技术过程，确保可以用于复盘。
- 没有对应内容的模块仍然保留，并明确写“原始记录未涉及”。

## References

- 需要判断事实边界、过滤规则和日志质量时，读取 `references/development-log-rules.md`。
- 需要固定章节和输出格式时，读取 `references/development-log-template.md`。
