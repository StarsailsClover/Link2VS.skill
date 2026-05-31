# Link2VS Skill - AI Agent to Visual Studio Bridge

**Connect AI Agents (Claude, Cursor, Cline) to Visual Studio 2026/2022 via MCP Protocol.**

---

## Installation (Single Method)

### NuGet Package (Recommended)

```bash
dotnet tool install -g UniversalVSMCP
```

Run:

```bash
universal-vsmcp --stdio
```

Verify:

```bash
universal-vsmcp --help
```

**NuGet:** https://www.nuget.org/packages/UniversalVSMCP/

---

## Features

- **30 MCP Tools** for comprehensive VS automation
- **Native .NET runtime** (no Python/Node.js dependencies)
- **Built-in diagnostics** for troubleshooting
- **Localhost support** for development
- **Bilingual documentation** (English + Chinese)

---

## VS 2026 Configuration

### Method A: Direct JSON (Recommended)

1. Open **Tools → Options → Environment → Extensions**
2. Check **"Edit user settings as JSON"**
3. Paste:

```json
{
  "mcpServers": {
    "universal-vsmcp": {
      "command": "dotnet",
      "args": [
        "tool",
        "run",
        "--global",
        "universal-vsmcp",
        "--",
        "--stdio"
      ],
      "env": {
        "VS_AUTO_DETECT": "true"
      }
    }
  }
}
```

### Method B: GUI

1. **Tools → Options → Environment → Extensions**
2. In **MCP Server List**, click **Add**
3. Fill in:
   - **Name**: `universal-vsmcp`
   - **Command**: `dotnet`
   - **Args**: `tool run --global universal-vsmcp -- --stdio`

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
