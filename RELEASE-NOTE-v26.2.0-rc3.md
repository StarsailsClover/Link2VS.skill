# Link2VS.skill (LVS) v26.2.0-RC3 Release Notes

**Release Date**: 2026-06-06  
**Status**: Pre-Release  
**Tag**: v26.2.0-rc3

---

## 🎯 Highlights

StepFun Skill definition for the Link2VS Suite, enabling AI agents to control Visual Studio and VS Code through natural language commands.

---

## 📦 What's Included

This repository contains:
- ✅ Skill definition (`skill.json`)
- ✅ Metadata (`.metadata.json`)
- ✅ Documentation (`README.md`, `SKILL.md`)
- ✅ Prompt templates
- ✅ Configuration examples

---

## 🛠️ Skill Capabilities

### IDE Operations
- Open/close solutions and projects
- Build and rebuild solutions
- Debug control (start, stop, breakpoints)
- File navigation and editing

### Code Intelligence
- Get project information
- Find files and symbols
- Read and modify code
- Get build errors and warnings

### Security Features
- Trust system for workspace verification
- Permission management for operations
- Audit logging for all actions

---

## 📋 Skill Definition

```json
{
  "id": "link2vs",
  "version": "26.2.0-rc3",
  "name": "Link2VS",
  "description": "Control Visual Studio and VS Code through MCP",
  "author": "StarsailsClover",
  "license": "MIT"
}
```

---

## 🔗 Dependencies

| Component | Version | Required |
|-----------|---------|----------|
| UVM | v26.2.0-rc3 | ✅ Required |
| VUV | v26.2.0-rc3 | ⚪ Optional |

---

## 🚀 Installation

### For StepFun Users
```bash
# Install from StepFun Skill Marketplace
stepclaw skill install link2vs

# Or manually copy
cp -r Link2VS.skill ~/.stepclaw/skills/link2vs-rc3/
```

### Configuration
Add to your StepFun configuration:
```json
{
  "skills": {
    "link2vs": {
      "enabled": true,
      "version": "26.2.0-rc3"
    }
  }
}
```

---

## 💡 Usage Examples

### Natural Language Commands
```
"Open the solution file in Visual Studio"
"Build the current project"
"Set a breakpoint at line 42"
"Find all references to this method"
"Get the list of projects in the solution"
```

### Direct Tool Calls
```json
{
  "tool": "link2vs/get_solution_info",
  "params": {}
}
```

---

## 🔗 Related Components

| Component | Version | Repository |
|-----------|---------|------------|
| LVS | v26.2.0-rc3 | This repo |
| UVM | v26.2.0-rc3 | [UniversalVSMCP](https://github.com/StarsailsClover/UniversalVSMCP) |
| VUV | v26.2.0-rc3 | [VscodeUniversalVSMCP](https://github.com/StarsailsClover/VscodeUniversalVSMCP) |

---

## 📋 Changelog (RC2 → RC3)

### RC2 → RC3
- Updated version to v26.2.0-rc3
- Synchronized with UVM/VUV RC3
- Cleaned repository with .gitignore

---

## 📝 License

MIT License - See LICENSE file

---

**Full Release**: https://github.com/StarsailsClover/Link2VS.skill/releases/tag/v26.2.0-rc3
