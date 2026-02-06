# Draw.io Skill (MCP)

This repo contains the Draw.io skill assets used by AI agents to create and edit diagrams through MCP. **It requires the Draw.io MCP server to be installed and running first.**

## Prerequisites

- Draw.io MCP server (install from https://github.com/DayuanJiang/next-ai-draw-io/tree/main.
- Draw.io MCP Browser Extension (see the upstream repo for install + port configuration)
- An MCP client that can call tools (for example, Claude Desktop, Codex, or Zed)
- Draw.io (web or desktop) accessible on the same machine

## Quick start

1) Install and configure the MCP server.

```json
{
  "mcpServers": {
    "drawio": {
      "command": "npx",
      "args": ["-y", "drawio-mcp-server"]
    }
  }
}
```

2) Install the Draw.io MCP Browser Extension and confirm it is connected. If you change the extension port, pass the same port via `--extension-port` in the server args.

3) Open Draw.io in your browser, then run your MCP client and use the skill.

## Using the skill

Start here:
- [[SKILL]]
- [[checklist]]
- [[examples]]
- [[reference]]

## Troubleshooting

- If tool calls fail, verify the MCP server is running and the extension shows a connected state.
- If you use a custom port, the server and extension must match.
- For HTTP transport or advanced setups, follow the upstream docs in [lgazo/drawio-mcp-server](https://github.com/lgazo/drawio-mcp-server).
