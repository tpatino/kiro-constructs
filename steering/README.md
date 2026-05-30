# Steering Examples

## What Are Steering Files?

Steering files are plain markdown documents that define project rules, conventions, and guidelines for Kiro to follow. They live in a project's `.kiro/steering/` directory and are automatically loaded when Kiro works in that project. Steering files shape how Kiro writes code, structures output, handles errors, and makes decisions.

Steering files are the primary mechanism for ensuring consistent, project-aligned behavior from Kiro across all interactions.

## This Directory vs. Your Project's `.kiro/steering/`

It is important to understand the distinction:

| Location | Purpose |
|----------|---------|
| **This directory** (`steering/`) | Example templates and references for you to learn from and adapt |
| **Your project's** `.kiro/steering/` | Active steering files that Kiro follows when working in your project |

The examples in this directory are **not active** -- they are templates and references. To use them, copy them to your project's `.kiro/steering/` directory and customize them for your specific needs.

## Steering File Anatomy

A well-structured steering file contains:

```markdown
# Title (Clear, Descriptive Name)

## Scope
What aspects of development this steering covers.

## Rules

- Actionable directive written as a clear instruction
- Another rule with specific, measurable criteria
- Rules should be unambiguous and testable

## Examples

### Correct
(Show what following the rules looks like)

### Incorrect
(Show what violating the rules looks like)

## Rationale
Why these rules exist and what problems they prevent.
```

### Key Principles

- **Directives, not suggestions** - Write rules as clear instructions ("Use kebab-case for file names") rather than soft guidance ("Consider using kebab-case")
- **Specific and measurable** - Rules should be unambiguous. A reviewer should be able to determine compliance objectively.
- **Scoped appropriately** - Each steering file should cover one coherent area (API conventions, testing standards, etc.)
- **Examples included** - Show correct and incorrect behavior to eliminate ambiguity

## Categories of Steering

### Project Conventions

Define how the project is structured and organized:

- File and directory naming conventions
- Module organization patterns
- Import/export rules
- Project-specific terminology

### Coding Standards

Define how code should be written:

- Error handling patterns
- Logging conventions
- Type annotation requirements
- Comment and documentation standards
- Function and variable naming

### Workflow Rules

Define how development processes work:

- Branch naming conventions
- Commit message formats
- PR description requirements
- Testing expectations before merging
- Deployment checklists

### Architecture Decisions

Capture significant technical decisions:

- Chosen patterns (repository pattern, CQRS, etc.)
- Technology choices and constraints
- Performance requirements and approaches
- Security requirements and practices
- API design principles

## Best Practices

1. **Start small and iterate** - Begin with 2-3 steering files covering your most important conventions. Add more as patterns emerge.

2. **Keep files focused** - One steering file per concern. A 200-line file covering everything is harder to maintain than four focused 50-line files.

3. **Update as conventions evolve** - Steering files are living documents. When your team changes a convention, update the steering immediately.

4. **Include the "why"** - Rules without rationale are harder to follow and maintain. Brief explanations help Kiro make better judgment calls in edge cases.

5. **Test effectiveness** - After adding a steering file, observe whether Kiro's output aligns with your expectations. Refine rules that are not producing the desired behavior.

6. **Avoid contradictions** - Review steering files as a set. Conflicting rules between files cause inconsistent behavior.

## Available Examples

| Example | Category | Description | Link |
|---------|----------|-------------|------|
| *None yet* | - | Be the first to contribute a steering example! | - |

## How to Use Steering Examples

1. Browse the examples in this directory to find ones relevant to your project.
2. Copy the example to your project's `.kiro/steering/` directory:
   ```bash
   cp kiro-constructs/steering/example-steering.md your-project/.kiro/steering/
   ```
3. Customize the rules, examples, and scope to match your project's specific conventions.
4. Remove any sections or rules that do not apply.
5. Add project-specific rules that are not covered by the template.
6. Test by using Kiro in your project and observing whether output follows the steering.
