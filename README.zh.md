# Link2VS Skill - AI Agent 到 Visual Studio 的桥梁

**让 AI Agent（Claude、Cursor、Cline）通过 MCP 协议连接到 Visual Studio 2026/2022。**

---

## 什么是 Link2VS？

Link2VS 是一个 AI Agent 技能，实现 AI 助手与 Visual Studio 的无缝集成：

- **MCP Registry 一键安装** - 在 VS 2026 中直接安装
- **28 个 MCP 工具** - 全面的 VS 自动化能力
- **原生 .NET 运行时** - 无需 Python/Node.js 依赖
- **双语文档** - 英文 + 中文

---

## 安装方法

### 方式一：NuGet 包（推荐）

```bash
dotnet tool install -g UniversalVSMCP
```

运行：

```bash
universal-vsmcp --stdio
```

NuGet：https://www.nuget.org/packages/UniversalVSMCP/

### 方式二：VS 2026 用户

1. 打开 Visual Studio 2026
2. **工具** -> **选项** -> **环境** -> **扩展**
3. 在 **MCP Registry** 中点击 **添加**
4. 输入：
   - **名称**: `UniversalVSMCP Official`
   - **URL**: `https://github.com/StarsailsClover/UniversalVSMCP`
5. 选择 `universal-vsmcp` 并点击 **安装**

### AI Agent 用户（Claude Desktop / Cursor）

添加到 `claude_desktop_config.json`：

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

## 功能特性

- **解决方案管理**: 列出项目、打开/关闭解决方案
- **文件操作**: 读取、写入、搜索 VS 项目中的文件
- **构建控制**: 构建、重新构建、清理解决方案和项目
- **调试控制**: 启动/停止调试、单步执行代码
- **项目管理**: 添加文件、设置启动项目、检查属性

---

## 相关仓库

- **Link2VS.skill**: https://github.com/StarsailsClover/Link2VS.skill
- **配套服务器**: https://github.com/StarsailsClover/UniversalVSMCP

---

## 文档

- [README.md](README.md) - English documentation
- [README.zh.md](README.zh.md) - 中文文档

---

## 许可

MIT © StarsailsClover
