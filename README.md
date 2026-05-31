# Link2VS Skill - AI Agent to Visual Studio Bridge

**Connect AI Agents (Claude, Cursor, Cline) and VS 2026 MCP Manager to Visual Studio 2026/2022 via MCP Protocol.**

---

## Installation (Single Method)

### NuGet Package (Recommended)

```bash
dotnet tool install -g UniversalVSMCP
```

Verify installation:

```bash
universal-vsmcp --help
```

**NuGet:** https://www.nuget.org/packages/UniversalVSMCP/

---

## Features

- **30 MCP Tools** for comprehensive VS automation
- **Dual Transport**: stdio (for AI Agents) + HTTP/SSE (for VS 2026)
- **Native .NET runtime** (no Python/Node.js dependencies)
- **Built-in diagnostics** for troubleshooting
- **Localhost support** for development
- **Bilingual documentation** (English + Chinese)

---

## VS 2026 Configuration (HTTP/SSE - Recommended)

**Method A: URL Configuration** (VS 2026 MCP Manager only supports URL)

1. Open command line, start HTTP server:

```bash
universal-vsmcp --http 5000
```

2. In VS 2026, open **Tools → Options → Environment → Extensions → MCP Servers**
3. Click **Add**
4. Fill in:
   - **Name**: `Universal VS MCP`
   - **URL**: `http://localhost:5000/sse`
   - **Transport**: `sse`

**Method B: Direct JSON (if editing settings JSON)**

```json
{
  "mcpServers": {
    "universal-vsmcp": {
      "name": "Universal VS MCP",
      "url": "http://localhost:5000/sse",
      "transport": "sse"
    }
  }
}
```

---

## Claude Desktop / Cursor

```json
{
  "mcpServers": {
    "vsmcp": {
      "command": "dotnet",
      "args": ["tool", "run", "--global", "universal-vsmcp", "--", "--stdio"],
      "env": {
        "VS_AUTO_DETECT": "true"
      }
    }
  }
}
```

---

## Diagnostic Tools

The server includes built-in diagnostic tools:

| Tool | Purpose |
|------|---------|
| `health_check` | Verify server is running and VS connection |
| `get_server_info` | Get server capabilities and tool list |
| `get_diagnostic_logs` | Get recent log entries |

### Troubleshooting

```bash
# Check installation
dotnet tool list -g

# Run with logging
universal-vsmcp --stdio --log-file uv.log

# Verify VS is running
# health_check tool will show connection status
```

---

## Repository

- **Link2VS.skill**: https://github.com/StarsailsClover/Link2VS.skill
- **Server (UVM)**: https://github.com/StarsailsClover/UniversalVSMCP
- **NuGet**: https://www.nuget.org/packages/UniversalVSMCP/

---

## Documentation

- [README.md](README.md) - English documentation
- [README.zh.md](README.zh.md) - Chinese documentation

---

## License

MIT © StarsailsClover
