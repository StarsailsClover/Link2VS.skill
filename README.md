# Link2VS Skill - AI Agent to Visual Studio Bridge

**Connect AI Agents (Claude, Cursor, Cline) to Visual Studio 2026/2022 via MCP Protocol.**

---

## What is Link2VS?

Link2VS is an AI Agent skill that enables seamless integration between AI assistants and Visual Studio. It provides:

- **Multiple installation methods** (Registry, Manual, Source)
- **28 MCP tools** for comprehensive VS automation
- **Native .NET runtime** (no Python/Node.js dependencies)
- **Bilingual documentation** (English + Chinese)
- **SSE and stdio transport** support

---

## Installation

### Method 1: NuGet Package (Recommended)

Install the global .NET tool:

```bash
dotnet tool install -g UniversalVSMCP
```

Run:

```bash
universal-vsmcp --stdio
```

NuGet: https://www.nuget.org/packages/UniversalVSMCP/

### Method 2: From Source

1. Clone the repository:
   ```bash
   git clone https://github.com/StarsailsClover/UniversalVSMCP.git
   cd UniversalVSMCP/src/UniversalVSMCP
   ```

2. Build and run:
   ```bash
   dotnet build
   dotnet run -- --stdio
   ```

### Method 2: VS 2026 MCP Registry

1. Open Visual Studio 2026
2. Go to **Tools -> Options -> Environment -> Extensions**
3. In **MCP Registry**, click **Add**
4. Enter:
   - **Name**: `UniversalVSMCP Official`
   - **URL**: `https://github.com/StarsailsClover/UniversalVSMCP`
5. Select `universal-vsmcp` and click **Install**

### Method 3: Manual MCP Server

1. **Tools -> Options -> Environment -> Extensions**
2. In **MCP Server List**, click **Add**
3. Fill in:
   - **Name**: `universal-vsmcp`
   - **Command**: `dotnet`
   - **Args**: `run --project C:\path\to\UniversalVSMCP\src\UniversalVSMCP\UniversalVSMCP.csproj -- --stdio`
4. Save and restart VS

### Method 4: Claude Desktop / Cursor

Add to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "vsmcp": {
      "command": "dotnet",
      "args": ["run", "--project", "C:\\path\\to\\UniversalVSMCP\\src\\UniversalVSMCP\\UniversalVSMCP.csproj", "--", "--stdio"],
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

- **Link2VS.skill**: https://github.com/StarsailsClover/Link2VS.skill
- **Companion Server (UVM)**: https://github.com/StarsailsClover/UniversalVSMCP

---

## Documentation

- [README.md](README.md) - English documentation
- [README.zh.md](README.zh.md) - Chinese documentation

---

## License

MIT © StarsailsClover

---

## Status

- **NuGet Package**: Published! https://www.nuget.org/packages/UniversalVSMCP/
- **MCP Registry**: Compatible, requires VS 2026 restart
- **Source Install**: Fully functional
