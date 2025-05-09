# 项目功能模块分析

## 主要模块

1. **main.py**
   - 项目入口文件，负责初始化 Manus 代理并处理用户输入。

2. **README.md**
   - 提供项目的概述、安装步骤、配置方法、快速启动指南以及贡献指南。

3. **app/agent/**
   - 包含代理类及其子类，如 `Manus`、`BaseAgent`、`BrowserAgent`、`ManusAgent`、`MCPAgent` 等，负责处理不同的代理任务。

4. **app/flow/**
   - 包含流程控制类，如 `FlowFactory`、`Planning`，负责管理任务的执行流程和规划。

5. **app/mcp/**
   - 包含与 MCP（Model Context Protocol）相关的类，如 `Server`，负责与外部 MCP 服务器通信。

6. **app/prompt/**
   - 包含提示处理类，如 `BrowserPrompt`、`COTPrompt`、`ManusPrompt`、`MCPPrompt`、`PlanningPrompt`、`SWEPrompt`、`ToolCallPrompt`，负责生成和解析不同类型的提示。

7. **app/sandbox/**
   - 包含沙箱环境相关类，如 `Client`、`Core/Exceptions`、`Core/Manager`、`Core/Sandbox`、`Core/Terminal`，负责创建和管理沙箱环境。

8. **app/tool/**
   - 包含各种工具类，如 `AskHuman`、`BaseTool`、`Bash`、`BrowserUseTool`、`CreateChatCompletion`、`DeepResearch`、`FileOperators`、`MCP`、`Planning`、`PythonExecute`、`StrReplaceEditor`、`Terminate`、`ToolCollection`、`WebSearch`，提供各种功能工具。
   - 子目录 `app/tool/search/` 包含具体的搜索引擎工具，如 `BaiduSearch`、`BingSearch`、`DuckDuckGoSearch`、`GoogleSearch`。

## 模块间关系

- `main.py` 初始化 `Manus` 代理，该代理调用 `app/agent/` 中的各种代理类来执行任务。
- `app/agent/` 中的代理类可能需要调用 `app/flow/` 中的流程控制类来管理任务流程。
- `app/agent/` 和 `app/prompt/` 之间的交互用于生成和解析提示。
- `app/agent/` 和 `app/sandbox/` 之间的交互用于在沙箱环境中执行任务。
- `app/agent/` 和 `app/tool/` 之间的交互用于调用各种工具来完成特定任务。
- `app/mcp/` 与其他模块交互以处理与 MCP 服务器的通信。

## 其他支持文件

- `app/bedrock.py`: 与 Bedrock API 交互的客户端类。
- `app/config.py`: 配置加载和管理类。
- `app/exceptions.py`: 自定义异常类。
- `app/llm.py`: 大语言模型相关的类，用于计数和管理令牌。
- `app/logger.py`: 日志记录工具。
- `app/schema.py`: 定义了项目的数据结构和协议。

## 总结

项目分为多个功能模块，每个模块都有明确的职责，模块之间通过清晰的接口进行交互，确保系统的高内聚低耦合性。主模块 `main.py` 初始化代理并处理用户输入，其他模块分别负责不同的业务逻辑和功能实现。项目还提供了详细的文档和配置说明，方便用户安装和使用。

## 目录结构

```
d:\colinxu\git\AI_Project\OpenManus
│   main.py
│   README.md
│   README_zh.md
│   README_ko.md
│   README_ja.md
│
├───app
│   │   bedrock.py
│   │   config.py
│   │   exceptions.py
│   │   llm.py
│   │   logger.py
│   │   schema.py
│   │
│   ├───agent
│   │       base_agent.py
│   │       browser_agent.py
│   │       manus.py
│   │       manus_agent.py
│   │       mcp_agent.py
│   │
│   ├───flow
│   │       flow_factory.py
│   │       planning.py
│   │
│   ├───mcp
│   │       server.py
│   │
│   ├───prompt
│   │       browser_prompt.py
│   │       cot_prompt.py
│   │       manus_prompt.py
│   │       mcp_prompt.py
│   │       planning_prompt.py
│   │       sweprompt.py
│   │       tool_call_prompt.py
│   │
│   ├───sandbox
│   │       client.py
│   │       core
│   │       │   exceptions.py
│   │       │   manager.py
│   │       │   sandbox.py
│   │       │   terminal.py
│   │
│   └───tool
│       │   ask_human.py
│       │   base_tool.py
│       │   bash.py
│       │   browser_use_tool.py
│       │   create_chat_completion.py
│       │   deep_research.py
│       │   file_operators.py
│       │   mcp.py
│       │   planning.py
│       │   python_execute.py
│       │   str_replace_editor.py
│       │   terminate.py
│       │   tool_collection.py
│       │   web_search.py
│       │
│       └───search
│               baidu_search.py
│               bing_search.py
│               duckduckgo_search.py
│               google_search.py
```
