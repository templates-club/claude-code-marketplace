# Claude Code Marketplace

A template repository for creating and sharing Claude Code skills following the [agentskills](https://github.com/agentskills/agentskills) standard format.

## Overview

This repository provides a structured template for building Claude Code skills that can be used in the Claude Code Marketplace. It includes a `generating-skills` skill that helps you create new skills following best practices and conventions.

## Features

- 📦 **Standard Format**: Follows the agentskills standard format
- 🎯 **Skill Generator**: Includes a `generating-skills` skill to help create new skills
- 📚 **Comprehensive Documentation**: Reference guides for YAML frontmatter, naming conventions, writing instructions, and more
- 🔧 **Development Tools**: ESLint configuration for code quality
- 📝 **Template Structure**: Ready-to-use template for new skills

## Installation

```bash
npx skills add templates-club/claude-code-marketplace-template
```

The [`skills`](https://www.npmjs.com/package/skills) CLI auto-detects your installed agents and provides an interactive picker. Use `-g` for global (user-wide) or `-y` to install all skills.

Works with Claude Code, Cursor, Codex, OpenCode, GitHub Copilot, Antigravity, Roo Code, and more.

### Claude Code Marketplace

An alternative for Claude Code users:

```bash
# Add marketplace
/plugin marketplace add templates-club/claude-code-marketplace-template

# Install individual skills
/plugin install generating-skill@claude-code-marketplace-template
```