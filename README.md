![Claude Code 学习手册：17 章实战，从循环到完整 Agent](docs/assets/cover.png?v=39d053b1be45)

# Claude Code 学习手册

用 17 个递进章节，学习编程 Agent 背后的 Harness 工程：从最小循环与工具调用，到上下文管理、记忆、任务协作、MCP 扩展和目标闭环。

每章包含可运行的 Python 示例、中英日三语文档和配套图示。适合想理解 Agent 工作机制、边读边运行代码的产品经理、学生与开发者。

## 可以学到什么

- **Agent 基础**：模型如何调用工具，权限与 Hooks 如何围绕循环工作。
- **复杂任务**：计划、子 Agent、按需加载 Skills 与上下文压缩。
- **持续运行**：跨会话记忆、任务依赖、后台任务与定时调度。
- **协作与扩展**：多 Agent 协作、MCP 工具接入与机制集成。
- **编排与收口**：可恢复的 Workflow，以及由独立判断器决定何时结束的目标循环。

完整讲解见 [学习指南](学习指南.md)，项目概览见 [项目摘要](SUMMARY.md)。

## 快速开始

推荐 Python 3.11 或更新版本。

```sh
git clone https://github.com/17lijunyi/claude-code-harness-study.git
cd claude-code-harness-study

# 查看全部章节，不需要 API Key
python3 run.py list

# 启动课程菜单：首次运行自动创建 .venv、安装依赖并引导填写 Key
python3 run.py
```

默认使用 DeepSeek 的 Anthropic 兼容接口。首次提示时输入自己的 API Key；也可以复制 `.env.example` 为 `.env`，按文件说明配置。使用其他兼容服务时，调整 `ANTHROPIC_BASE_URL` 和 `MODEL_ID`。

Mac 用户也可以双击 [启动.command](启动.command)。进入菜单后输入 `s01`、`s02` 等章节编号；课程里输入 `q` 返回菜单，菜单里输入 `q` 退出。

```sh
# 直接进入指定章节
python3 run.py s03

# 修改本地保存的 Key
python3 run.py setkey

# 无需模型调用的 Workflow 演示
python3 s16_workflow_runtime/code.py demo
python3 s16_workflow_runtime/code.py resume
```

示例中的 Shell、文件写入等工具会实际执行操作，练习时请使用专门的工作目录。模型请求由你配置的服务商计费；`.env`、本地环境和运行记录均不进入版本管理。

## 章节目录

| 章节 | 主题 | 学习重点 |
| --- | --- | --- |
| [s01](s01_agent_loop/README.zh.md) | Agent Loop | 一个循环与 Bash 工具 |
| [s02](s02_tool_use/README.zh.md) | Tool Use | 工具注册与分发 |
| [s03](s03_permission/README.zh.md) | Permission | 权限判断与审批 |
| [s04](s04_hooks/README.zh.md) | Hooks | 工具调用前后的扩展点 |
| [s05](s05_todo_write/README.zh.md) | TodoWrite | 计划与进度管理 |
| [s06](s06_subagent/README.zh.md) | Subagent | 独立上下文与结果返回 |
| [s07](s07_skill_loading/README.zh.md) | Skill Loading | 技能目录与按需注入 |
| [s08](s08_context_compact/README.zh.md) | Context Compact | 上下文预算与压缩 |
| [s09](s09_memory/README.zh.md) | Memory | 记忆筛选、提取与整理 |
| [s10](s10_task_system/README.zh.md) | Task System | 持久化任务图与依赖 |
| [s11](s11_background_tasks/README.zh.md) | Background Tasks | 后台执行与完成通知 |
| [s12](s12_cron_scheduler/README.zh.md) | Cron Scheduler | 持久化定时调度 |
| [s13](s13_agent_teams/README.zh.md) | Agent Teams | 队友、消息与工作目录 |
| [s14](s14_mcp_plugin/README.zh.md) | MCP Plugin | 外部工具接入 |
| [s15](s15_integrated_harness/README.zh.md) | Integrated Harness | 多种机制接回同一循环 |
| [s16](s16_workflow_runtime/README.zh.md) | Workflow Runtime | 固定编排、日志与续跑 |
| [s17](s17_goal_loop/README.zh.md) | Goal Loop | 目标检查与结束判断 |

各章节目录中的 `README.md` 为英文文档，`README.zh.md` 为中文，`README.ja.md` 为日文；`code.py` 为该章示例。

## 运行检查

```sh
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt pytest
python -m pytest tests -q
```

仓库已配置 GitHub Actions，在提交和 Pull Request 时运行测试。

## 许可证

[MIT](LICENSE)。
