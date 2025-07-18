# MCP server and client

An example of an MCP server and client, from the DeepLearning.AI course on MCP.
https://learn.deeplearning.ai/courses/mcp-build-rich-context-ai-apps-with-anthropic

## setup

Install a virtual environment:
We use `uv` to manage the virtual environment and dependencies.

Install uv:
https://docs.astral.sh/uv/getting-started/installation/

Using curl:
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```
or using homebrew:
```bash
brew install uv
```
Or even pip in the base env:
```bash
pip install uv
```

Initiate the virtual environment:
```bash
uv init
uv venv
source .venv/bin/activate
```

Install the dependencies:
```bash
uv sync
```

## Running the server and client
Launch the inspector for the research server:
```bash
npx @modelcontextprotocol/inspector uv run research_server.py
```

Run the client locally:
```bash
uv run mcp_chatbot.py
```




In the left bar, have the following values:
* Transport type: STDIO
* Command: uv
* Arguments: run research_server.py
* Inspector Proxy Address: http://localhost:6277/
(maybe?)






# documentation

MCP architecture:
https://modelcontextprotocol.io/docs/concepts/architecture


MCP servers:
https://github.com/modelcontextprotocol/servers

MCP python SDK:
https://github.com/modelcontextprotocol/python-sdk
