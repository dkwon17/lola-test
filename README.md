# Lola

Example Lola module demonstrating how to distribute AI assistant skills, commands, and agents across workspaces. This module provides a Go code review checklist, a security audit command, and a dependency update agent.

## Installation

```bash
# Add to lola registry
lola mod add /path/to/lola

# Install for a specific assistant
lola install lola -a claude-code -s user

# Install for all assistants
lola install lola -s user
```

## Components

### Skills

- **review-checklist** — Code review checklist for Go changes covering tests, error handling, concurrency, and rollback safety.

### Commands

- **/security-audit** — Scan the current project for common security issues (hardcoded secrets, vulnerable dependencies, insecure configurations).

### Agents

- **dependency-updater** — Specialized agent for updating Go module dependencies, checking compatibility, and running tests.

### MCP Servers

No MCP servers configured. Add entries to `module/mcps.json` to declare remote tool servers.

## Development

This module follows the lola module structure:

```
lola/
├── README.md
└── module/
    ├── skills/
    │   └── review-checklist/
    │       └── SKILL.md
    ├── commands/
    │   └── security-audit.md
    ├── agents/
    │   └── dependency-updater.md
    ├── mcps.json
    └── AGENTS.md
```

Edit files in `module/` to customize the content that gets installed to AI assistants.

## License

Apache-2.0
