# Mini Coding Agent

一个用 Python 逐步实现 Coding Agent 核心能力的学习项目，涵盖工具调用、权限控制、上下文管理、任务协作和工作流执行。

## 快速开始

### 1. 安装依赖

```bash
pip install -r requirements.txt
```

### 2. 配置环境变量

```bash
cp .env.example .env
```

编辑 `.env`，填写自己的 `ANTHROPIC_API_KEY`，并根据使用的服务配置 `ANTHROPIC_BASE_URL` 和 `MODEL_ID`。

### 3. 运行示例

从基础 Agent 循环开始：

```bash
python agent_loop.py
```

也可以按下面的功能目录选择其他脚本运行。

## 功能目录

### 基础能力

| 运行命令 | 功能说明 |
| --- | --- |
| `python agent_loop.py` | 实现模型调用与命令执行交替进行的基础 Agent 循环。 |
| `python tool_use.py` | 为 Agent 提供命令执行、文件读写、文本编辑和文件查找工具。 |
| `python permission.py` | 在工具执行前检查权限规则，并对需要授权的操作请求用户确认。 |
| `python hooks.py` | 通过事件钩子实现权限检查、执行日志、上下文注入和会话总结。 |
| `python todo_write.py` | 使用待办清单记录任务步骤和完成状态，帮助 Agent 跟踪执行进度。 |

### 上下文与任务管理

| 运行命令 | 功能说明 |
| --- | --- |
| `python skill_loading.py` | 加载技能说明，并按需向 Agent 提供执行任务所需的专门知识。 |
| `python context_compact.py` | 压缩对话上下文，在控制上下文长度的同时保留任务所需信息。 |
| `python background_tasks.py` | 将耗时命令放到后台运行，并把完成结果注入 Agent 对话。 |
| `python task_system.py` | 持久化管理任务及其依赖关系，支持任务创建、认领和完成。 |
| `python memory.py` | 从对话中提取并保存记忆，在后续任务中检索和加载相关信息。 |

### 协作与扩展

| 运行命令 | 功能说明 |
| --- | --- |
| `python subagent.py` | 将子任务交给独立上下文中的子 Agent 执行，并将结果返回主 Agent。 |
| `python agent_teams.py` | 通过共享任务、消息通信和 Git worktree 协调多个 Agent 协作。 |
| `python mcp_plugin.py` | 使用模拟 MCP 服务演示外部工具连接、工具池组装和动态调用。 |
| `python cron_scheduler.py` | 通过定时调度触发 Agent 任务，支持周期性自动执行。 |

### 完整运行程序

| 运行命令 | 功能说明 |
| --- | --- |
| `python integrated_harness.py` | 将工具、钩子、记忆、上下文管理和团队协作等能力整合为完整的 Agent 运行程序。 |
| `python workflow_runtime.py` | 在集成 Agent 中加入工作流执行、状态持久化和恢复能力。 |
| `python goal_loop.py` | 根据目标完成条件持续推进任务，并结合预算和停止条件控制执行。 |
