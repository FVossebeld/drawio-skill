# Draw.io Skill (MCP)

> AI agent skill for creating and editing [Draw.io](https://www.drawio.com/) diagrams via the [Model Context Protocol (MCP)](https://modelcontextprotocol.io/).

This repo contains the skill assets used by AI agents to produce professional architecture diagrams — including Azure diagrams with correct icons, containers, and edge patterns — entirely through natural language.

> **Prerequisite:** The [Draw.io MCP server](https://www.npmjs.com/package/@next-ai-drawio/mcp-server) must be installed and running before using this skill.

---

## Quick Start

1. **Install and configure the MCP server** in your MCP client (e.g. VS Code, Claude Desktop):

   ```json
   {
     "servers": {
       "drawio": {
         "command": "npx",
         "args": ["@next-ai-drawio/mcp-server@latest"],
         "env": {
           "PORT": "6010"
         }
       }
     },
     "inputs": []
   }
   ```

2. **Open Draw.io** in your browser ([app.diagrams.net](https://app.diagrams.net)).

3. **Run your MCP client** and start describing the diagram you want.

---

## Skill Reference

| Document | Description |
|----------|-------------|
| [SKILL](SKILL.md) | Main skill instructions for AI agents |
| [checklist](checklist.md) | Pre-commit validation checklist for diagrams |
| [examples](examples.md) | Example diagrams and patterns |
| [reference](reference.md) | Draw.io XML reference and style guide |
| [azure-icons](azure-icons.md) | Full list of available Azure icon paths |

---

## Troubleshooting

- **Tool calls fail** — Verify the MCP server is running and the Draw.io browser extension shows a connected state.
- **Custom port** — The port configured in the MCP server and the browser extension must match.
