# Changelog

All notable changes to the Link2VS.skill project will be documented in this file.

## [26.0.3] - 2026-06-01

### Added
- **Phase 4-5: VS Code Extension HTTP Server**
  - Extension acts as MCP Server
  - HTTP communication between UVM and VS Code
  - Native VS Code API integration
  - ExtensionHttpServer implementation
  - Auto-start server on activation
- Multi-IDE support completed
  - Visual Studio 2022/2026 via COM/DTE
  - VS Code via Extension API with HTTP server
  - Smart routing between IDEs

### Changed
- Version sync with UniversalVSMCP v26.0.3
- Documentation updated for Extension Server
- Keywords updated: "vscode-extension-server", "http-server"

## [26.0.2] - 2026-05-31

### Added
- VS Code Extension support with hybrid architecture
- Native MCP detection for VS Code 2026+
- Connection strategy configuration (prefer-native, always-stdio, native-only)
- Automatic fallback from native to stdio mode
- Status bar connection mode indicator

### Changed
- Version sync with UniversalVSMCP v26.0.2
- Updated keywords to include "vscode" and "hybrid-architecture"
- Enhanced documentation for VS Code integration

### Security
- Security framework documentation (from UVM v26.0.0)
- Workspace Trust best practices
- User confirmation for sensitive operations

## [26.0.0] - 2026-05-31

### Added
- Initial release with UniversalVSMCP integration
- 30 MCP tools for Visual Studio automation
- NuGet package distribution
- HTTP/SSE transport support
- Bilingual documentation (EN/ZH)

### Features
- Solution management (6 tools)
- Project management (5 tools)
- File operations (5 tools)
- Build operations (6 tools)
- Debug operations (6 tools)
- Diagnostic tools (2 tools)

## [2.1.0] - 2025 (Historical)

### Added
- VS 2026/2022 MCP integration
- File operations
- Build and debug control
