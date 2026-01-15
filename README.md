# agent-skills

Repository for installable Agent Skills

## Available Skills

### agents-md-generator

Analyze repository structure and generate standardized AGENTS.md files that serve as contributor guides for AI agents. Measures LOC to determine character limits and produces 5-section documents covering overview, folder structure, patterns, conventions, and working agreements.

**Use when:**
- You need to create an AGENTS.md file for a repository
- You want to document repository structure for AI agents
- You need to analyze and document coding patterns and conventions

**Features:**
- Measures repository size (LOC) to determine appropriate character limits
- Analyzes folder structure and architectural patterns
- Documents coding conventions and patterns
- Generates standardized 5-section AGENTS.md files
- Read-only analysis - no code execution or modification

See [skills/agents-md-generator](./skills/agents-md-generator) for full documentation.

## Installation

Skills can be installed by including the skill's SKILL.md file in your AI agent's context.

## Skill Structure

Each skill contains:
- `SKILL.md` - Instructions for the agent
- `references/` - Supporting documentation and specifications

## License

MIT
