# LangChain Tutorial (v1.x)

Hands-on Jupyter notebooks covering core LangChain v1.x concepts using **Groq** (`groq:qwen/qwen3.8-27b`, `groq:openai/gpt-oss-20b`) and **Google Gemini** (`google_genai:gemini-3.1-flash-lite`).

## Prerequisites

- **Python**: `>= 3.14`
- **API Keys**: A `.env` file in the project root with your provider API keys:
  ```env
  GROQ_API_KEY=your_groq_api_key
  GOOGLE_API_KEY=your_google_api_key
  ```

## Setup

Using `uv`:
```bash
uv sync
```

Or using `pip`:
```bash
pip install -r requirements.txt
```

## Tutorial Notebooks

| # | Notebook | Topics Covered |
|---|----------|----------------|
| 1 | [1-langchain-intro.ipynb](tutorial/1-langchain-intro.ipynb) | Loading `.env`, defining a Python tool function, creating an agent with `create_agent()`, and running `agent.invoke()` |
| 2 | [2-model-integration.ipynb](tutorial/2-model-integration.ipynb) | Initializing Google Gemini and Groq models via `init_chat_model()`, `ChatGoogleGenerativeAI`, and `ChatGroq`; `invoke()`, `stream()`, and `batch()` with `max_concurrency` |
| 3 | [3-tools.ipynb](tutorial/3-tools.ipynb) | Creating tools with `@tool`, binding tools with `model.bind_tools()`, inspecting `tool_calls`, and running a manual tool execution loop |
| 4 | [4-messages.ipynb](tutorial/4-messages.ipynb) | Text prompts vs message lists; `SystemMessage`, `HumanMessage`, `AIMessage`, and `ToolMessage` (`tool_call_id`), message metadata, and `usage_metadata` |
| 5 | [5-structured-output.ipynb](tutorial/5-structured-output.ipynb) | Enforcing schemas with `model.with_structured_output()` and `create_agent(..., response_format=...)` using Pydantic `BaseModel`, `TypedDict`, and `@dataclass`, plus `include_raw=True` and nested models |
| 6 | [6-middleware.ipynb](tutorial/6-middleware.ipynb) | `SummarizationMiddleware` (by messages, tokens, and context fraction) with `InMemorySaver`, `HumanInTheLoopMiddleware` (`approve`, `edit`, `reject` via `Command(resume=...)`), and an interactive mock-email chatbot |

## Project Structure

```text
langchain-tutorial/
├── main.py
├── pyproject.toml
├── requirements.txt
├── README.md
└── tutorial/
    ├── 1-langchain-intro.ipynb
    ├── 2-model-integration.ipynb
    ├── 3-tools.ipynb
    ├── 4-messages.ipynb
    ├── 5-structured-output.ipynb
    └── 6-middleware.ipynb
```
