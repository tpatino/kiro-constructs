# kiro-constructs

> A curated collection of production-ready AWS Kiro artifacts for elite-level software development workflows.

## Purpose

**kiro-constructs** is a community-driven repository of high-quality Kiro artifacts -- agents, hooks, powers, steering files, and specs -- designed to accelerate your development workflow. Each artifact is crafted to meet elite maturity standards: comprehensive documentation, clear scope, practical examples, and validated effectiveness in real projects.

Whether you are setting up a new project or enhancing an existing workflow, this repository provides ready-to-use building blocks that you can copy directly into your `.kiro/` directory.

## Directory Structure

```
kiro-constructs/
├── .kiro/
│   ├── agents/              # Agent definitions used in this repo
│   │   └── solution-reviewer.md
│   └── steering/            # Project steering for this repo
│       ├── project.md
│       └── contributions.md
├── agents/                  # Agent artifacts (catalog & docs)
│   └── README.md
├── hooks/                   # Hook artifacts (catalog & docs)
│   └── README.md
├── powers/                  # Power artifacts (catalog & docs)
│   └── README.md
├── steering/                # Steering file examples (catalog & docs)
│   └── README.md
├── specs/                   # Spec examples (catalog & docs)
│   └── README.md
├── CONTRIBUTING.md          # How to contribute
├── LICENSE                  # MIT License
└── README.md                # This file
```

## Artifact Categories

### [Agents](agents/README.md)

Agents are autonomous AI assistants with defined expertise, tools, and behaviors. They handle specialized tasks -- code review, architecture analysis, test generation, and more -- while following structured output formats.

**When to use:** When you need a specialized AI assistant for a recurring task that benefits from consistent instructions and tool access.

### [Hooks](hooks/README.md)

Hooks are event-driven automations that trigger on file saves, file creation, commits, or manual invocation. They run Kiro instructions automatically when specific events occur in your project.

**When to use:** When you want to automate quality checks, code generation, or validation steps that should run in response to development events.

### [Powers](powers/README.md)

Powers are packaged capabilities that bundle documentation, steering files, and optional MCP server configurations into reusable modules. They extend Kiro with domain-specific knowledge and tooling.

**When to use:** When you need to add a complete capability (documentation + workflow + tools) to your project in one step.

### [Steering](steering/README.md)

Steering files define project rules, conventions, and guidelines that Kiro follows when working in your project. They establish consistent behavior across all AI-assisted development.

**When to use:** When you want to codify project conventions, coding standards, architecture decisions, or workflow rules that Kiro should always follow.

### [Specs](specs/README.md)

Specs are structured requirement documents with requirements, design, and task sections that drive implementation. They provide a systematic approach to feature development.

**When to use:** When you want to define a feature or system component with enough structure that Kiro can implement it systematically.

## Getting Started

### Using Artifacts from This Repository

1. **Browse** the category directories to find artifacts that match your needs.
2. **Copy** the artifact file(s) into your project's `.kiro/` directory:
   - Agents go in `.kiro/agents/`
   - Hooks go in `.kiro/hooks/`
   - Powers go in `.kiro/powers/`
   - Steering files go in `.kiro/steering/`
   - Specs go in `.kiro/specs/`
3. **Customize** the artifact to fit your project's specific needs (adjust tools, patterns, or rules as appropriate).
4. **Validate** by using the artifact in your workflow and iterating on it.

### Example: Installing an Agent

```bash
# Copy an agent to your project
cp kiro-constructs/.kiro/agents/solution-reviewer.md your-project/.kiro/agents/

# The agent is now available in your Kiro workflow
```

## Kiro Maturity Model

This repository targets the **elite maturity level** for Kiro adoption:

- **Complete artifact coverage** -- agents, hooks, steering, and specs working together
- **Comprehensive documentation** -- every artifact is thoroughly documented with usage examples
- **Proven patterns** -- artifacts are validated in real projects before inclusion
- **Consistent quality** -- all artifacts meet the same high standards for structure, clarity, and effectiveness

## Contributing

We welcome contributions of new artifacts and improvements to existing ones. Please read our [Contributing Guide](CONTRIBUTING.md) for details on:

- How to submit new artifacts
- Quality standards and required documentation
- Naming conventions and file format requirements
- The review and acceptance process

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
