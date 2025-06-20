# Developer Tools Research AI Agent 🤖

A modular, research-focused AI agent designed to assist developer tooling exploration—enabling research-driven interaction with developer tools through autonomous agents.

---

## 🔍 Features

- **Modular architecture**: easily extendable to add new tools, plugins, or research experiments.
- **Tool integration**: supports language models and function-calling pipelines.
- **Meta-research**: leveraging AI to autonomously evaluate and discover trends in popular developer tools.
- **Agent orchestration**: chain multiple agents for complex, multi-step tool workflows.

---

## 📈 Architecture

A simplified overview:

```
[User Goal] → [Orchestrator Agent] → [Tool Agents] → [Tool APIs / SDKs] → [LLM Model] → [Results]
```

Each piece is highly decoupled—swap in a new tool agent or model with minimal friction.

---

## ⚙️ Getting Started

### Requirements

- Python 3.10+
- [OpenAI](https://openai.com) or [Gemini](https://aistudio.google.com/app/apikey) or any other compatible LLM API key
- [Firecrawl](https://www.firecrawl.dev/) API key
- Download [uv](https://docs.astral.sh/uv/getting-started/installation/)

### Installation

```bash
git clone https://github.com/danish0511/developer-tools-research-ai-agent.git
cd developer-tools-research-ai-agent
uv init .
uv add firecrawl-py langchain langchain-openai langchain-google-genai langgraph pydantic python-dotenv
uv run main.py
```

### Configuration

Create a `.env` file:

```
OPENAI_API_KEY=your_openai_api_key
FIRECRAWL_API_KEY=your_firecrawl_api_key
```
---

## 🧩 Extending the Agent

1. **Add a new tool agent**:  
   - Create `tools/new_tool_agent.py`  
   - Implement `class NewToolAgent(ToolAgentBase)`

2. **Register the agent** in `agent_registry.py`

3. **Invoke** via:

```bash
--agents orchestrator,new_tool_agent
```

---

## 🧪 Research Use Cases

- Compare refactoring performance
- Benchmark code generation accuracy across language models.
- Automate documentation enhancement in repositories.

---
