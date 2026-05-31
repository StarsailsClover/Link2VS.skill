# Link2VS Skill - AI Agent 到 Visual Studio 的桥梁

**让 AI Agent（Claude、Cursor、Cline）通过 MCP 协议连接到 Visual Studio 2026/2022。**

---

## 安装方式（单一推荐方式）

### NuGet 包（推荐）

```bash
dotnet tool install -g UniversalVSMCP
```

运行：

```bash
universal-vsmcp --stdio
```

验证：

```bash
universal-vsmcp --help
```

**NuGet：** https://www.nuget.org/packages/UniversalVSMCP/

---

## 功能特性

- **30 个 MCP 工具** 全面的 VS 自动化
- **原生 .NET 运行时** 无需 Python/Node.js 依赖
- **内置诊断工具** 便于故障排除
- **Localhost 支持** 用于本地开发
- **双语文档** 英文 + 中文

---

## VS 2026 配置

### 方法 A：直接 JSON（推荐）

1. 打开 **工具 → 选项 → 环境 → 扩展**
2. 勾选 **"将用户设置编辑为 JSON"**
3. 粘贴：

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

### 方法 B：GUI

1. **工具 → 选项 → 环境 → 扩展**
2. 在 **MCP 服务器列表** 点击 **添加**
3. 填写：
   - **名称**: `universal-vsmcp`
   - **命令**: `dotnet`
   - **参数**: `tool run --global universal-vsmcp -- --stdio`

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

## 诊断工具

服务器包含内置诊断工具：

| 工具 | 用途 |
|------|------|
| `health_check` | 验证服务器运行和 VS 连接 |
| `get_server_info` | 获取服务器能力和工具列表 |
| `get_diagnostic_logs` | 获取最近的日志条目 |

### 故障排除

```bash
# 检查安装
dotnet tool list -g

# 带日志运行
universal-vsmcp --stdio --log-file uv.log

# 验证 VS 正在运行
# health_check 工具将显示连接状态
```

---

## 相关仓库

- **Link2VS.skill**: https://github.com/StarsailsClover/Link2VS.skill
- **服务器 (UVM)**: https://github.com/StarsailsClover/UniversalVSMCP
- **NuGet**: https://www.nuget.org/packages/UniversalVSMCP/

---

## 文档

- [README.md](README.md) - English documentation
- [README.zh.md](README.zh.md) - 中文文档

---

## 许可

MIT © StarsailsClover
