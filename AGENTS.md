# Tavon Marketplace - Agent Context

This document provides context for AI agents (Claude Code, Cowork, etc.) working with the Tavon Marketplace.

## Repository Overview

**Purpose:** A curated marketplace for Claude Code and Cowork plugins  
**Location:** https://github.com/tavon-ai/marketplace  
**Landing Page:** https://tavon-ai.github.io/marketplace/

## Structure

```
.
├── .claude-plugin/
│   └── marketplace.json      # Marketplace registry (required location)
├── plugins/
│   ├── hello-world/          # Example tutorial plugin
│   └── landing-page-builder/ # Webflow landing page automation
├── index.html               # Landing page
└── README.md                # Main documentation
```

## Marketplace Schema

The marketplace uses Anthropic's official schema:

```json
{
  "$schema": "https://anthropic.com/claude-code/marketplace.schema.json",
  "name": "tavon-marketplace",
  "description": "...",
  "owner": {
    "name": "Tavon",
    "email": "hello@tavon.ai"
  },
  "plugins": [
    {
      "name": "plugin-name",
      "description": "...",
      "version": "1.0.0",
      "author": { ... },
      "source": "./plugins/plugin-name",
      "category": "development|productivity|...",
      "strict": false
    }
  ]
}
```

## Plugin Structure

Each plugin must have:

```
plugins/plugin-name/
├── .claude-plugin/
│   └── plugin.json          # Plugin metadata
├── skills/                  # Optional: skill definitions
│   └── SKILL.md
├── agents/                  # Optional: agent definitions  
├── commands/                # Optional: slash commands
└── README.md               # Required: documentation
```

### Plugin Metadata (plugin.json)

```json
{
  "name": "plugin-name",
  "version": "1.0.0",
  "description": "What it does",
  "author": {
    "name": "Author Name",
    "url": "https://..."
  },
  "category": "development",
  "tags": ["tag1", "tag2"]
}
```

### Skill Files (skills/SKILL.md)

```markdown
---
name: skill-name
description: Brief description
---

# Skill Title

Instructions for Claude on what to do when activated.

## When to Use This Skill
Trigger conditions...

## Instructions
Step-by-step what to do...

## Examples
User: "example"
Assistant: "response"
```

## Available Plugins

### 1. hello-world
- **Category:** productivity
- **Purpose:** Tutorial/example plugin
- **Trigger:** "hello marketplace"

### 2. landing-page-builder
- **Category:** development
- **Purpose:** Automate Webflow landing page creation
- **Requirements:** Webflow MCP server configured
- **Features:**
  - Structured requirements gathering
  - Conversion-optimized layouts
  - SEO automation
  - Mobile responsiveness
  - 5-minute build time target

## Installation for Users

1. **Customize** > **Browse Plugins** > **Personal**
2. **Add Marketplace from Github URL**
3. Enter: `https://github.com/tavon-ai/marketplace.git`
4. Browse and install plugins

## Adding New Plugins

### Steps:
1. Create plugin directory: `plugins/your-plugin-name/`
2. Add `.claude-plugin/plugin.json`
3. Add `README.md`
4. Add `skills/SKILL.md` (or agents/, commands/)
5. Update `.claude-plugin/marketplace.json`
6. Test locally
7. Commit and push

### Categories:
- `development` - Code-related tools
- `productivity` - Task management, automation
- `integrations` - External service connections
- `ai-tools` - AI-powered features
- `data` - Data processing, analysis

## Critical Requirements

✅ **marketplace.json location:** MUST be in `.claude-plugin/` directory  
✅ **Schema field:** Include `$schema` URL  
✅ **Owner field:** Use `owner` not `author` at marketplace level  
✅ **Source field:** Use `source` not `path` in plugin entries  
✅ **Strict field:** Include `"strict": false` for flexibility  

## Common Issues

### "Failed to add marketplace"
- Check `.claude-plugin/marketplace.json` exists and is valid JSON
- Verify schema matches official Anthropic format
- Ensure repository is accessible

### Plugin not appearing
- Verify plugin is listed in marketplace.json
- Check plugin.json exists in plugin's `.claude-plugin/` directory
- Ensure `source` path is correct (relative to repo root)

### Plugin shows old name or version in browser
- The Claude plugin browser reads from `.claude-plugin/marketplace.json`, NOT individual plugin.json files
- Must update both files when renaming or versioning:
  1. `plugins/plugin-name/.claude-plugin/plugin.json`
  2. `.claude-plugin/marketplace.json` (update name, version, source)

## Development Workflow

1. Create plugin locally in `plugins/`
2. Test by adding local marketplace path
3. Update marketplace.json
4. Push to GitHub
5. Refresh in Claude Code/Cowork

## GitHub Pages

The landing page at `index.html` is automatically deployed via GitHub Pages:
- **Settings:** Deploy from branch "main", folder "/ (root)"
- **URL:** https://tavon-ai.github.io/marketplace/

## Version Control

- **Main branch:** Production-ready plugins
- **Commit messages:** Descriptive (e.g., "Add plugin-name plugin")
- **Testing:** Test locally before pushing

## Best Practices

### For Plugin Developers:
- ✅ Clear, descriptive names
- ✅ Complete documentation
- ✅ Working examples in README
- ✅ Test all triggers/commands
- ✅ Include prerequisites

### For Skills:
- ✅ Clear "When to Use" section
- ✅ Step-by-step instructions
- ✅ Multiple examples
- ✅ Reasonable scope (not too broad)

### For Marketplace Maintenance:
- ✅ Keep marketplace.json in sync with actual plugins
- ✅ **CRITICAL:** When renaming plugins or updating versions, update BOTH:
  - Individual plugin's `.claude-plugin/plugin.json`
  - Root `.claude-plugin/marketplace.json` (name, version, source path)
- ✅ Version bumps when updating plugins
- ✅ Test installations before releasing
- ✅ Update landing page with new plugins

## References

- **Official Schema:** https://anthropic.com/claude-code/marketplace.schema.json
- **Example Marketplace:** https://github.com/anthropics/claude-plugins-official
- **Repository:** https://github.com/tavon-ai/marketplace

---

**Last Updated:** March 9, 2026  
**Version:** 1.0  
**Maintainer:** Tavon
