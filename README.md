# zenith-mcp-hub
⚡ Universal Model Context Protocol (MCP) Server &amp; Agentic Tool Router for Claude Code, Cursor, and Local LLMs — Built by Sarvesh Zenith (Dayal Infotech Services)
# Zenith MCP Hub (`zenith-mcp-hub`)

> **Universal Model Context Protocol (MCP) Server & Agentic Tool Router for Claude Code, Cursor, and Local LLMs**
> Created & Maintained by **Sarvesh Zenith** at **Dayal Infotech Services**.

---

## Overview

`zenith-mcp-hub` is a high-utility, zero-latency Model Context Protocol (MCP) server and dynamic agentic tool router designed to seamlessly integrate LLMs (Claude Code, Cursor IDE, Ollama, vLLM) with external enterprise tools, local codebases, and custom agent workflows.

---

## Key Features

- **Zero-Latency Tool Routing**: Ultra-fast async dispatch of context and tool calls across multi-agent workflows.
- **Context Compression & Pruning**: Smart window management to optimize token usage for long-context tasks.
- **Multi-Agent Orchestration**: Connect Claude Code, Cursor, and local LLMs to a single unified MCP interface.
- **Enterprise Security**: Built-in permission checks and schema validation for local and remote executions.
- **Plug-and-Play Connectors**: Ready-to-use schemas for filesystem, REST APIs, databases, and terminal actions.

---

## Architecture Overview

```text
  +-------------------------------------------------------------+
  |              Clients (Claude Code / Cursor / Local LLM)      |
  +-------------------------------------------------------------+
                                |
                         [ MCP Protocol ]
                                v
  +-------------------------------------------------------------+
  |                   Zenith MCP Router Hub                     |
  |  +---------------------+  +-------------------------------+ |
  |  |  Context Compressor |  |  Dynamic Tool Dispatcher      | |
  |  +---------------------+  +-------------------------------+ |
  +-------------------------------------------------------------+
               /                |                \
              v                 v                 v
     [ Filesystem Agent ] [ REST/API Tool ]  [ Custom Scripts ]
```

---

## Quickstart Guide

### Using `uv` (Recommended)

```bash
# Install uv if you haven't already
pip install uv

# Run Zenith MCP Hub directly
uvx zenith-mcp-hub
```

### Using `pip`

```bash
# Clone the repository
git clone zenith-mcp-hub
cd zenith-mcp-hub

# Install dependencies
pip install -e .

# Start the server
python server.py
```

---

## Configuration for Cursor / Claude Code

Add the following to your `mcpServers` configuration (`claude_desktop_config.json` or Cursor settings):

```json
{
  "mcpServers": {
    "zenith-mcp-hub": {
      "command": "python",
      "args": ["/path/to/zenith-mcp-hub/server.py"]
    }
  }
}
```

---

## About the Author

Built by **Sarvesh Zenith**
* **Organization**: Dayal Infotech Services

---

## License

Distributed under the MIT License. See LICENSE for details.
