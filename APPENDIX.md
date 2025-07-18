## Additional Resources

- [Building Agents with Model Context Protocol](https://www.youtube.com/watch?v=kQmXtrmQ5Zg&t=1s&ab_channel=AIEngineer) - Full Workshop with Mahesh Murag of Anthropic
- [Mahesh Workshop Agent Example](https://github.com/maheshmurag/workshop-mcp-agent-example) (this example shows the use of MCP agent: an example of a host or LLM-based application that is MCP compatible).
- [Claude Desktop Setup](https://modelcontextprotocol.io/quickstart/user) (you may need to download [Node.js](https://nodejs.org/en), and also [uv](https://github.com/astral-sh/uv?tab=readme-ov-file#installation))
- [Testing your server with Claude Desktop](https://modelcontextprotocol.io/quickstart/server#testing-your-server-with-claude-for-desktop) - If you’re a Windows user and using uv, you may need to put the full path to the uv executable in the command field.
- [MCP core architectures](https://modelcontextprotocol.io/docs/concepts/architecture); [MCP Python SDK](https://github.com/modelcontextprotocol/python-sdk).
- If you code with Typescript, check this [MCP course](https://www.aihero.dev/mcp-prerequisites).
- [MCP server with Docker](https://github.com/daveebbelaar/ai-cookbook/tree/main/mcp/crash-course/6-run-with-docker)

   In lesson 9, you can setup the remote server using `uv` as explained in the course. Then you can create this DockerFile:
    ```
    FROM python:3.11-slim
    WORKDIR /app
    RUN pip install uv
    COPY pyproject.toml uv.lock ./
    RUN uv pip install --system .
    COPY research_server.py .
    EXPOSE 8001
    CMD ["uv", "run", "research_server.py"]
    ```
    And then create the image using  this command: `docker build -t my-server .`

    Then run the container using: `docker run -p 8001:8001 my-server`
