# Link2VS Skill - AI Agent to Visual Studio Bridge

**Connect AI Agents (Claude, Cursor, Cline) to Visual Studio 2026/2022 via MCP Protocol.**

---

## What is Link2VS?

Link2VS is an AI Agent skill that enables seamless integration between AI assistants and Visual Studio. It provides:

- **One-click installation** from MCP Registry in VS 2026
- **28 MCP tools** for comprehensive VS automation
- **Native .NET runtime** (no Python/Node.js dependencies)
- **Bilingual documentation** (English + Chinese)

---

## Installation

### For VS 2026 Users

1. Open Visual Studio 2026
2. Go to **Tools -> Options -> Environment -> Extensions**
3. In **MCP Registry**, click **Add**
4. Enter:
   - **Name**: `UniversalVSMCP Official`
   - **URL**: `https://github.com/StarsailsClover/UniversalVSMCP`
5. Select `universal-vsmcp` and click **Install**

### For AI Agent Users (Claude Desktop / Cursor)

Add to your `claude_desktop_config.json`:

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

## Features

- **Solution Management**: List projects, open/close solutions
- **File Operations**: Read, write, search files in VS projects
- **Build Control**: Build, rebuild, clean solutions and projects
- **Debug Control**: Start/stop debugging, step through code
- **Project Management**: Add files, set startup projects, inspect properties

---

## Repository

- **GitHub**: https://github.com/StarsailsClover/Link2VS.skill
- **Companion Server**: https://github.com/StarsailsClover/UniversalVSMCP

---

## Documentation

- [README.md](README.md) - English documentation
- [README.zh.md](README.zh.md) - Chinese documentation

---

## License

MIT © StarsailsClover
