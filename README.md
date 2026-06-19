# Harness Marketplace

Single-agent operating protocol for Claude Code — project scaffolding, context management, and auto-learning.

## What is Harness?

Harness is a skill+plugin ecosystem that turns Claude Code into a reliable, context-aware development agent. It provides:

- **Phase 0 Auto-Orient**: Automatic project detection, health checks, and context loading at session start
- **Skill Routing Matrix**: Smart dispatch of 50+ skills based on task type (creative, debugging, academic, etc.)
- **Context Templates**: Standardized `.claude/context/` structure (architecture, conventions, decisions, environment)
- **Memory System**: Persistent cross-session learning with auto-save
- **50% Compaction Rule**: Mandatory context health enforcement

## Install

```bash
# Add the marketplace
claude plugin marketplace add https://github.com/yyz-123-cpu/harness-yyz

# Install the harness skill
claude plugin install harness@yyz-123-cpu
```

Requires `CLAUDE_CODE_GIT_BASH_PATH` on Windows:
```bash
export CLAUDE_CODE_GIT_BASH_PATH="C:\\Program Files\\Git\\bin\\bash.exe"
```

## Quick Start

```
/harness init    # Scaffold a new project with context templates
/harness status  # Check current harness health
/harness update  # Update context from recent work
```

## What Gets Created

```
project/
├── .claude/
│   ├── context/
│   │   ├── project.md        # What, why, for whom
│   │   ├── architecture.md   # Components, data flow, dependencies
│   │   ├── conventions.md    # Naming, style, commit format
│   │   ├── decisions.md      # Key decisions with rationale
│   │   └── environment.md    # Interpreter paths, tools, pitfalls
│   ├── memory/
│   │   └── MEMORY.md         # Cross-session memory index
│   └── CLAUDE.md             # Project-level operating protocol
```

## Recommended Companion Plugins

The harness works best with these plugins (auto-install recommended):

| Plugin | Purpose |
|--------|---------|
| `superpowers` | Core skill dispatch engine |
| `caveman` | Output token saving (65% reduction) |
| `claude-code-harness` | Plan→Work→Review→Release delivery loop |
| `claude-mem` | Advanced memory compression |
| `browse` | Browser automation |

## License

MIT — see [LICENSE](LICENSE)
