# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

ccplugins is a Claude Code plugin marketplace and collection of productivity plugins. This is a **documentation-driven** project with no compiled code - plugins are markdown specifications with YAML frontmatter that instruct Claude Code on command behavior.

## Architecture

```
ccplugins/
├── .claude-plugin/
│   └── marketplace.json       # Marketplace registry (lists all plugins)
└── plugins/
    └── <plugin-name>/
        ├── .claude-plugin/
        │   └── plugin.json    # Plugin metadata
        ├── commands/
        │   └── <cmd>.md       # Command specifications (YAML frontmatter + markdown)
        └── README.md
```

### Command Specification Format

Commands use YAML frontmatter followed by markdown instructions:

```yaml
---
name: command-name
description: Brief description
allowed-tools:
  - Read
  - Write
  - Glob
  - Bash
---
# Instructions in Markdown
```

The `allowed-tools` list explicitly declares which Claude Code tools the command can use.

## Development

### Creating a New Plugin

```bash
mkdir -p plugins/new-plugin/.claude-plugin
mkdir -p plugins/new-plugin/commands
```

Create `plugins/new-plugin/.claude-plugin/plugin.json`:
```json
{
  "name": "new-plugin",
  "version": "1.0.0",
  "description": "Your plugin description",
  "author": { "name": "Your Name" },
  "keywords": ["relevant", "keywords"]
}
```

Register in `.claude-plugin/marketplace.json` by adding to the `plugins` array.

### Installation Methods

**As marketplace (recommended):**
```
/plugin marketplace add qqpann/ccplugins
```

**Local development:**
```
/plugin marketplace add ./ccplugins
```

**Direct plugin:**
Add to `~/.claude/settings.json`:
```json
{ "plugins": ["~/workspace/ccplugins/plugins/session-wrap"] }
```

## Conventions

- Documentation and command instructions are written in Japanese (日本語)
- Session logs are stored in each project's `.claude/sessions/` directory
- Log format uses structured sections: やったこと (done), 途中のこと (in progress), 次やること (next), メモ (notes)
- Each plugin is self-contained with its own configuration and README
