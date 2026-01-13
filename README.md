# Buddy Plugin Marketplace

A Claude Code plugin marketplace providing MCP server integrations.

## Installation

Add this marketplace to Claude Code:

```bash
/plugin marketplace add github-username/buddy-plugin-marketplace
```

## Available Plugins

### clickup-mcp

ClickUp MCP integration for task and project management.

**Install:**
```bash
/plugin install clickup-mcp@buddy-plugins
```

**Features:**
- HTTP-based MCP server for ClickUp
- Task and project management capabilities

## Commands

```bash
/plugin marketplace update    # Update marketplace
/plugin list                  # List installed plugins
/mcp                          # Check MCP server status
```

## Structure

```
buddy-plugin-marketplace/
├── .claude-plugin/
│   └── marketplace.json
├── plugins/
│   └── clickup-mcp/
│       └── .mcp.json
└── README.md
```

## License

MIT
