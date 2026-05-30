# Project Steering

## Repository Purpose

This repository is a curated collection of AWS Kiro artifacts. It serves as a reference library and distribution point for production-ready agents, hooks, powers, steering files, and specs.

## Directory Structure Rules

- **`.kiro/agents/`** - Agent definitions that this repository itself uses
- **`.kiro/steering/`** - Steering files that govern this repository
- **`agents/`** - Agent artifacts available for others to use (catalog and documentation)
- **`hooks/`** - Hook artifacts available for others to use
- **`powers/`** - Power artifacts available for others to use
- **`steering/`** - Steering file examples and templates
- **`specs/`** - Spec examples and templates
- Each top-level category directory must contain a `README.md` explaining the category

## File Naming Conventions

- Use **kebab-case** for all artifact file names (e.g., `solution-reviewer.md`, `auto-format-hook.md`)
- Use lowercase for all directory names
- Agent files: `{agent-name}.md`
- Hook files: `{hook-name}.md`
- Power directories: `{power-name}/` containing `POWER.md`
- Steering files: descriptive kebab-case names (e.g., `coding-standards.md`, `api-conventions.md`)
- Spec files: `{spec-name}.md`

## Documentation Requirements

Every artifact in this repository must include:

1. **Clear description** - What the artifact does and why it exists
2. **Usage instructions** - How to install and use the artifact
3. **Practical examples** - Real-world scenarios demonstrating the artifact in action
4. **Defined scope** - What the artifact handles and what it does not handle
5. **Prerequisites** - Any dependencies or requirements for using the artifact

## Quality Standards

- Each artifact must be **validated in a real Kiro project** before inclusion
- Artifacts must be **self-contained** -- they should work when copied to any compatible project
- Documentation must be **actionable** -- a developer should be able to use the artifact after reading the docs
- All markdown must be **well-formatted** with consistent heading levels and proper structure
- No placeholder content -- every section must contain meaningful information

## Frontmatter Format Requirements

### Agents

```yaml
---
name: agent-name
description: Clear one-line description of what the agent does
tools: ["tool1", "tool2"]
model: claude-opus-4-8
---
```

### Hooks

```yaml
---
name: hook-name
description: Clear one-line description of what the hook does
event: on_file_save | on_file_create | on_commit | manual
filePattern: "glob-pattern"
---
```

## Markdown Formatting Standards

- Use ATX-style headers (`#`, `##`, `###`)
- One blank line before and after headings
- Use fenced code blocks with language identifiers
- Use unordered lists with `-` (not `*` or `+`)
- Limit line length to improve readability in plain text editors
- Use bold for emphasis on key terms, not italics for entire phrases
- Tables must have header rows and alignment indicators

## Commit Message Conventions

- Use conventional commit prefixes: `feat:`, `fix:`, `docs:`, `chore:`, `refactor:`
- Keep the subject line under 72 characters
- Use the imperative mood ("Add agent" not "Added agent")
- Reference related artifacts in the body when applicable
