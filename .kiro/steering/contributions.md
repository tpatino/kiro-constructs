# Contribution Steering

## Workflow for Adding New Artifacts

1. **Identify the need** - Determine which category the artifact belongs to (agent, hook, power, skill, steering, spec)
2. **Check for duplicates** - Review existing artifacts to avoid overlap
3. **Create the artifact** - Follow the format standards for the category
4. **Document thoroughly** - Include all required sections per the category standards
5. **Validate in a real project** - Test the artifact in an actual Kiro workflow
6. **Update the category README** - Add the new artifact to the catalog table
7. **Submit for review** - Open a pull request with a clear description

## Required Sections by Artifact Type

### Agents

- YAML frontmatter with `name`, `description`, `tools`, and `model`
- Role description (who the agent is)
- Core responsibilities (numbered list)
- Review/work approach methodology
- Output format specification
- Guidelines and constraints

### Hooks

- YAML frontmatter with `name`, `description`, `event`, and `filePattern`
- Purpose statement
- Trigger conditions (when the hook fires)
- Actions performed (what the hook does)
- Input/output expectations
- Edge cases and limitations

### Powers

- `POWER.md` with overview, installation, usage, and configuration
- At least one steering file providing workflow guidance
- Clear documentation of any MCP server requirements
- Dependencies and prerequisites listed

### Skills

- YAML frontmatter with `name`, `description`, and `tools`
- Capability statement (what the skill enables)
- Input and output definitions for composability
- Ordered workflow steps
- Error handling instructions
- Composition notes (how the skill interacts with agents or other skills)

### Steering Files

- Clear scope statement (what aspects of development this covers)
- Rules written as actionable directives
- Examples demonstrating correct behavior
- Rationale for non-obvious rules

### Specs

- Requirements section with clear acceptance criteria
- Design section with architectural decisions
- Tasks section with implementation steps
- Context explaining the problem being solved

## Quality Gates

Before an artifact is accepted, it must pass these checks:

1. **Format compliance** - Correct frontmatter, valid markdown, proper structure
2. **Documentation completeness** - All required sections present with meaningful content
3. **Naming convention adherence** - Kebab-case file names, descriptive and concise
4. **Scope clarity** - Clear boundaries on what the artifact does and does not do
5. **Practical utility** - Solves a real problem that others would encounter
6. **No conflicts** - Does not duplicate or contradict existing artifacts
7. **Real-world validation** - Has been tested in an actual Kiro project

## Review Criteria

Reviewers should evaluate:

- **Correctness** - Does the artifact do what it claims?
- **Completeness** - Are all necessary instructions and configurations included?
- **Clarity** - Can a developer understand and use it without additional context?
- **Consistency** - Does it follow the established patterns in this repository?
- **Quality** - Is it written to elite maturity standards?

## Testing Expectations

- Agents should be invoked in a Kiro session and produce useful output
- Hooks should trigger correctly on their specified events
- Powers should install cleanly and provide their documented capabilities
- Skills should produce consistent results in isolation and when composed into agents
- Steering files should measurably influence Kiro behavior when active
- Specs should be implementable by Kiro without ambiguity

## Naming Conventions

- **Artifact names**: Use kebab-case that describes the artifact's function (e.g., `solution-reviewer`, `auto-format-on-save`, `api-design-steering`)
- **Be specific**: Prefer `typescript-linting-hook` over `lint-hook`
- **Be concise**: Prefer `solution-reviewer` over `comprehensive-code-solution-review-agent`
- **Avoid abbreviations**: Use full words unless the abbreviation is universally understood (e.g., `api`, `url`)

## Categorization Rules

- If an artifact defines an autonomous AI assistant with specific tools and model: it is an **agent**
- If an artifact triggers on a development event (save, create, commit): it is a **hook**
- If an artifact bundles documentation, steering, and optional MCP config: it is a **power**
- If an artifact defines a reusable capability with inputs, outputs, and composable workflow steps: it is a **skill**
- If an artifact defines project rules and conventions for Kiro to follow: it is a **steering file**
- If an artifact defines requirements, design, and tasks for implementation: it is a **spec**
