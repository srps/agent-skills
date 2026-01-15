# Agent Skills

A collection of skills for AI coding agents. Skills are packaged instructions and scripts that extend agent capabilities.

Skills follow the [Agent Skills](https://agentskills.io/) format.

## Available Skills

### agents-md-generator

Analyze repository structure and generate standardized AGENTS.md files that serve as contributor guides for AI agents. Measures LOC to determine character limits and produces 5-section documents covering overview, folder structure, patterns, conventions, and working agreements.

**Use when:**
- "Create an AGENTS.md for this repository"
- "Generate a contributor guide for AI agents"
- "Document the repository structure and patterns"
- "Analyze and document coding conventions"

**Features:**
- Measures repository size (LOC) with tokei to determine appropriate character limits (10,000-30,000)
- Analyzes folder structure and architectural patterns using read-only commands
- Documents coding conventions, patterns, and behaviors observed in code
- Generates standardized 5-section AGENTS.md files:
  1. Overview - Project description (1-2 sentences)
  2. Folder Structure - Key directories and their roles
  3. Core Behaviors & Patterns - Logging, error handling, control flow
  4. Conventions - Naming, comments, code style
  5. Working Agreements - Agent behavior rules
- Read-only analysis - no code execution or modification

**How it works:**
1. Runs `tokei` to measure repository LOC
2. Determines character limit based on repository scale
3. Analyzes directory structure with `tree` and `rg` (ripgrep)
4. Examines source files (max 800 lines per file, excluding imports)
5. Generates structured AGENTS.md following template specification

See [skills/agents-md-generator](./skills/agents-md-generator) for full documentation.

## Installation

```bash
npx add-skill srps/agent-skills
```

Or install directly from GitHub URL:

```bash
npx add-skill https://github.com/srps/agent-skills
```

### Installation Options

```bash
# List available skills without installing
npx add-skill srps/agent-skills --list

# Install specific skill only
npx add-skill srps/agent-skills --skill agents-md-generator

# Install to specific agents
npx add-skill srps/agent-skills -a claude-code -a opencode

# Install globally (available across all projects)
npx add-skill srps/agent-skills --global

# Non-interactive installation (CI/CD friendly)
npx add-skill srps/agent-skills -y -g
```

## Usage

Skills are automatically available once installed. The agent will use them when relevant tasks are detected.

**Example:**
```
Generate an AGENTS.md file for this repository
```

The agent will:
1. Measure the repository size
2. Analyze the codebase structure
3. Identify patterns and conventions
4. Generate a comprehensive AGENTS.md file

## Skill Structure

Each skill contains:
- `SKILL.md` - Instructions for the agent with YAML frontmatter
- `references/` - Supporting documentation and specifications

## Creating Your Own Skills

To create a skill compatible with this repository:

1. Create a directory under `skills/` with your skill name
2. Add a `SKILL.md` file with YAML frontmatter:

```markdown
---
name: my-skill-name
description: Brief description of what the skill does and when to use it
license: MIT
---

# My Skill Name

Detailed instructions for the agent...
```

3. (Optional) Add supporting files:
   - `references/` - Documentation and specifications
   - `scripts/` - Helper scripts for automation
   - `assets/` - Images, data files, etc.

## Compatibility

Skills are compatible with:
- OpenCode
- Claude Code
- Codex
- Cursor
- GitHub Copilot (with agent support)

## License

MIT
