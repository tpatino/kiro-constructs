# Contributing to kiro-constructs

Thank you for your interest in contributing to kiro-constructs! This repository thrives on community contributions of high-quality Kiro artifacts.

## How to Contribute

### 1. Identify What to Contribute

Choose the type of artifact you want to add:

- **Agent** - An autonomous AI assistant with specific tools and expertise
- **Hook** - An event-driven automation triggered by development events
- **Power** - A bundled capability with documentation, steering, and optional MCP config
- **Skill** - A reusable capability definition with prompts, tools, and composable workflow steps
- **Steering example** - A template for project rules and conventions
- **Spec example** - A structured requirements document demonstrating the spec format

### 2. Check for Duplicates

Before creating a new artifact, review the existing catalog in the relevant category README:

- [agents/README.md](agents/README.md)
- [hooks/README.md](hooks/README.md)
- [powers/README.md](powers/README.md)
- [skills/README.md](skills/README.md)
- [steering/README.md](steering/README.md)
- [specs/README.md](specs/README.md)

If a similar artifact exists, consider improving it rather than creating a duplicate.

### 3. Create Your Artifact

Follow the format standards documented in the category README. Key requirements:

- Use kebab-case for file and directory names
- Include all required frontmatter fields (agents and hooks)
- Write comprehensive documentation
- Include practical examples

### 4. Validate in a Real Project

Before submitting, test your artifact in an actual Kiro project:

- Agents should produce useful, well-structured output when invoked
- Hooks should trigger correctly and behave idempotently
- Powers should install cleanly and provide documented capabilities
- Skills should produce consistent results in isolation and when composed into agents
- Steering files should measurably influence Kiro behavior
- Specs should be implementable by Kiro without ambiguity

### 5. Submit a Pull Request

1. Fork the repository
2. Create a branch with a descriptive name (e.g., `add-typescript-linting-hook`)
3. Add your artifact and update the relevant category README catalog table
4. Open a pull request with:
   - Clear title describing the artifact
   - Description of what the artifact does and why it is useful
   - Confirmation that you tested it in a real project

## Quality Standards Checklist

Before submitting, verify your artifact meets these standards:

- [ ] **File naming** - Uses kebab-case (e.g., `solution-reviewer.md`, not `SolutionReviewer.md`)
- [ ] **Format compliance** - Correct frontmatter (agents/hooks) or correct structure (powers/steering/specs)
- [ ] **Description** - Clear, concise explanation of purpose
- [ ] **Documentation** - All required sections present with meaningful content
- [ ] **Examples** - Practical usage examples included
- [ ] **Scope** - Clear boundaries on what the artifact handles and does not handle
- [ ] **Validation** - Tested in a real Kiro project
- [ ] **Catalog updated** - Added to the relevant category README table
- [ ] **No conflicts** - Does not duplicate or contradict existing artifacts

## Naming Conventions

| Element | Convention | Example |
|---------|-----------|---------|
| Agent files | `{agent-name}.md` | `solution-reviewer.md` |
| Hook files | `{hook-name}.md` | `format-on-save.md` |
| Power directories | `{power-name}/` | `api-design/` |
| Skill files | `{skill-name}.md` | `parse-openapi-spec.md` |
| Steering files | `{topic}.md` | `coding-standards.md` |
| Spec files | `{feature-name}.md` | `user-authentication.md` |
| Branch names | `{action}-{artifact-name}` | `add-typescript-linting-hook` |

All names should be:
- Lowercase with hyphens (kebab-case)
- Descriptive of the artifact's function
- Concise but not abbreviated (unless universally understood)

## Required Documentation by Artifact Type

### Agents

- YAML frontmatter: `name`, `description`, `tools`, `model`
- Role definition
- Core responsibilities
- Methodology/approach
- Output format
- Guidelines and constraints

### Hooks

- YAML frontmatter: `name`, `description`, `event`, `filePattern`
- Purpose statement
- Trigger conditions
- Actions performed
- Edge case handling

### Powers

- `POWER.md` with overview, installation, usage, configuration, examples
- At least one steering file
- Dependency documentation

### Skills

- YAML frontmatter: `name`, `description`, `tools`
- Capability statement
- Input and output definitions
- Ordered workflow steps
- Error handling instructions
- Composition notes

### Steering Examples

- Scope statement
- Rules as actionable directives
- Correct and incorrect examples
- Rationale

### Spec Examples

- Requirements (functional and non-functional)
- Design (architecture, data model, interfaces)
- Tasks (ordered, atomic implementation steps)

## PR Process

1. **Open a PR** against the `main` branch
2. **Describe** what the artifact does, why it is useful, and how you tested it
3. **Review** - Maintainers will review for quality, format compliance, and usefulness
4. **Iterate** - Address any feedback and update your PR
5. **Merge** - Once approved, your artifact joins the collection

## Code of Conduct

We are committed to providing a welcoming and inclusive experience for everyone. Contributors are expected to:

- Be respectful and constructive in all interactions
- Welcome newcomers and help them contribute successfully
- Focus feedback on the artifact, not the person
- Accept constructive criticism gracefully
- Prioritize what is best for the community

Unacceptable behavior includes harassment, discriminatory language, personal attacks, and trolling. Maintainers may remove content or ban contributors who violate these standards.
