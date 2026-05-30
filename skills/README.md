# Skills

## What Are Kiro Skills?

Kiro skills are reusable capability definitions that package prompts, tool configurations, and workflow steps into composable units. They allow agents to gain specific capabilities without duplicating instructions, enabling modular and maintainable AI-assisted workflows.

Think of skills as building blocks for agent behavior -- each skill encapsulates a well-defined capability (API integration, code analysis, data transformation) that can be composed into agents or invoked independently. Skills promote reuse: instead of writing the same instructions across multiple agents, you define the capability once as a skill and reference it wherever needed.

## Skill File Format

Skill definitions use a markdown file with YAML frontmatter:

```markdown
---
name: skill-name
description: A clear description of the capability this skill provides.
tools: ["tool1", "tool2"]
inputs:
  - name: input-name
    description: What this input provides to the skill
    required: true
outputs:
  - name: output-name
    description: What the skill produces
---

Skill instructions written in markdown...
```

### Frontmatter Fields

| Field | Required | Description |
|-------|----------|-------------|
| `name` | Yes | Unique identifier for the skill (kebab-case) |
| `description` | Yes | One-line summary of the capability this skill provides |
| `tools` | Yes | Array of tool names the skill requires |
| `inputs` | No | Array of input definitions the skill accepts |
| `outputs` | No | Array of output definitions the skill produces |

### Input and Output Definitions

| Field | Required | Description |
|-------|----------|-------------|
| `name` | Yes | Identifier for the input or output (kebab-case) |
| `description` | Yes | What the input provides or the output contains |
| `required` | No | Whether the input is required (default: `true`) |

### Body Content

The markdown body contains the skill's instructions, including:

- **Capability statement** - What the skill enables and the problem it solves
- **Prerequisites** - Any context or state required before the skill can execute
- **Steps** - Ordered workflow steps the skill performs
- **Output specification** - What the skill produces and in what format
- **Error handling** - How to handle failures or missing inputs
- **Composition notes** - How this skill interacts with other skills or agents

## How Skills Are Used

Skills can be consumed in several ways:

| Usage Pattern | Description | Example |
|---------------|-------------|---------|
| **Agent composition** | An agent references skills to gain capabilities | An agent references `parse-openapi-spec` and `generate-client-code` skills |
| **Direct invocation** | A skill is invoked standalone for a specific task | Invoking `validate-json-schema` on a configuration file |
| **Chained execution** | Multiple skills execute in sequence, outputs feeding inputs | `extract-requirements` then `generate-test-cases` then `validate-coverage` |

### Referencing Skills in Agents

Agents can reference skills to inherit their capabilities without duplicating instructions:

```markdown
---
name: api-developer
description: Builds API endpoints following project conventions.
tools: ["read", "write", "bash"]
model: claude-sonnet-4-20250514
skills: ["parse-openapi-spec", "generate-endpoint", "write-api-tests"]
---

Agent-specific instructions here...
```

## Best Practices

### Writing Effective Skills

1. **Keep skills atomic** - Each skill should provide exactly one well-defined capability. If a skill does multiple unrelated things, split it into separate skills.

2. **Define clear inputs and outputs** - Explicit inputs and outputs make skills composable. Other skills and agents need to know what to provide and what to expect back.

3. **Be tool-minimal** - Only require the tools the skill actually uses. A skill that reads files should not request write access unless it produces file output.

4. **Write for reuse** - Skills should not assume a specific project structure or technology stack unless that is their explicit domain. Keep instructions general enough to work across contexts.

5. **Handle missing context gracefully** - Skills may be invoked without all optional inputs. Include instructions for what to do when optional context is unavailable.

6. **Document composition patterns** - If a skill is designed to work with other specific skills, document the expected sequencing and data flow.

7. **Include validation steps** - Skills should verify their inputs are valid before proceeding and validate their outputs before returning results.

8. **Version your skills** - When a skill's interface changes (inputs/outputs), document the change so consumers can update their references.

### Common Pitfalls

- Skills that are too broad, combining multiple unrelated capabilities
- Missing input/output definitions that make composition difficult
- Skills that duplicate instructions already available in other skills
- Hardcoded assumptions about project structure or technology choices
- No error handling for missing or malformed inputs
- Skills that produce inconsistent output formats across invocations

## Available Skills

| Skill | Tools | Description | Link |
|-------|-------|-------------|------|
| *None yet* | - | Be the first to contribute a skill! | - |

## How to Install a Skill

1. Choose a skill from the catalog above.
2. Copy the skill file to your project's `.kiro/skills/` directory:
   ```bash
   mkdir -p your-project/.kiro/skills
   cp kiro-constructs/skills/example-skill.md your-project/.kiro/skills/
   ```
3. Reference the skill from your agents or invoke it directly.
4. Optionally adjust tools and inputs to match your project's available tooling.

## Creating Your Own Skills

To contribute a new skill to this repository:

1. Create a markdown file following the format above
2. Define clear inputs and outputs for composability
3. Test the skill in isolation and as part of an agent composition
4. Verify it produces consistent results across multiple invocations
5. Add it to the catalog table in this README
6. Submit a pull request (see [CONTRIBUTING.md](../CONTRIBUTING.md))
