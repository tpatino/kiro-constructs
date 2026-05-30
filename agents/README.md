# Agents

## What Are Kiro Agents?

Kiro agents are autonomous AI assistants defined in markdown files with YAML frontmatter. Each agent has a specific area of expertise, a set of tools it can access, and structured instructions that guide its behavior. Agents live in your project's `.kiro/agents/` directory and are available for invocation during your development workflow.

Think of agents as specialized team members -- each one is an expert in a particular domain (code review, testing, documentation, security analysis) and produces consistent, structured output every time.

## Agent File Format

Agent definitions use a markdown file with YAML frontmatter:

```markdown
---
name: agent-name
description: A clear, concise description of what this agent does and when to invoke it.
tools: ["tool1", "tool2", "tool3"]
model: claude-opus-4-8
---

Agent instructions written in markdown...
```

### Frontmatter Fields

| Field | Required | Description |
|-------|----------|-------------|
| `name` | Yes | Unique identifier for the agent (kebab-case) |
| `description` | Yes | One-line summary of purpose and invocation context |
| `tools` | Yes | Array of tool names the agent can access |
| `model` | Yes | The AI model to use (e.g., `claude-opus-4-8`) |

### Body Content

The markdown body contains the agent's instructions, including:

- **Role definition** - Who the agent is and what expertise it brings
- **Core responsibilities** - Numbered list of what the agent does
- **Process/methodology** - How the agent approaches its work
- **Output format** - The structure of the agent's responses
- **Guidelines** - Rules and constraints governing behavior

## Best Practices

### Writing Effective Agents

1. **Be specific about the role** - Define exactly what expertise the agent brings. "Expert code reviewer" is too vague; "Expert code reviewer focusing on security vulnerabilities and performance anti-patterns" is actionable.

2. **Define clear output structure** - Agents produce better results when they have a well-defined output format with sections, headings, and expected content types.

3. **Limit tool access** - Only grant tools the agent actually needs. An agent that only reads code should have `["read"]`, not every available tool.

4. **Include guidelines and constraints** - Tell the agent what NOT to do. This prevents common failure modes like nitpicking style, making unsupported claims, or producing overly generic advice.

5. **Use imperative instructions** - Write the body as direct instructions ("Analyze the code for...", "Produce a report with...") rather than passive descriptions.

6. **Provide prioritization criteria** - When the agent produces recommendations or findings, define how to prioritize them (by impact, severity, effort, etc.).

7. **Consider context sensitivity** - Include instructions for adapting behavior based on project size, maturity, or type.

### Common Pitfalls

- Overloading a single agent with too many responsibilities
- Vague descriptions that do not help users know when to invoke the agent
- Missing output format specification, leading to inconsistent results
- Granting excessive tool access beyond what the agent needs

## Available Agents

| Agent | Description | Tools | Link |
|-------|-------------|-------|------|
| solution-reviewer | Reviews codebases and provides actionable enhancement recommendations | `read` | [.kiro/agents/solution-reviewer.md](../.kiro/agents/solution-reviewer.md) |

## How to Install an Agent

1. Choose an agent from the catalog above.
2. Copy the agent file to your project's `.kiro/agents/` directory:
   ```bash
   cp kiro-constructs/.kiro/agents/solution-reviewer.md your-project/.kiro/agents/
   ```
3. The agent is now available in your Kiro sessions.
4. Optionally customize the agent's instructions to match your project's specific needs (e.g., adjust priorities, add project-specific guidelines).

## Creating Your Own Agents

To contribute a new agent to this repository:

1. Create a markdown file following the format above
2. Validate it in a real Kiro project
3. Add it to the catalog table in this README
4. Submit a pull request (see [CONTRIBUTING.md](../CONTRIBUTING.md))
