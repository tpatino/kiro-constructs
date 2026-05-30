# Powers

## What Are Kiro Powers?

Kiro powers are packaged capabilities that bundle documentation, workflow guidance, and optional MCP (Model Context Protocol) server configurations into reusable modules. Powers extend Kiro with domain-specific knowledge and tooling, providing a complete capability that goes beyond what a single agent or hook can offer.

Think of powers as "skill packs" for Kiro -- they provide everything needed to work effectively in a particular domain: the knowledge (documentation), the workflow (steering files), and the tools (MCP servers).

## Power Directory Structure

Each power is a directory containing the following:

```
power-name/
├── POWER.md            # Required: Documentation and usage guide
├── steering/           # Required: Workflow guidance files
│   ├── workflow.md     # How to use the power effectively
│   └── patterns.md    # Common patterns and examples
└── mcp/               # Optional: MCP server configurations
    └── config.json    # Server connection and tool definitions
```

### POWER.md

The primary documentation file that includes:

- **Overview** - What the power provides and why it exists
- **Installation** - How to add the power to your project
- **Usage** - How to invoke and interact with the power
- **Configuration** - Available settings and customization options
- **Examples** - Real-world usage scenarios
- **Limitations** - What the power does not handle

### Steering Files

Steering files within a power provide workflow guidance:

- Define step-by-step processes for using the power
- Establish patterns and conventions specific to the domain
- Provide decision trees for common scenarios
- Include templates and examples

### MCP Server Configuration (Optional)

When a power includes MCP servers, the configuration defines:

- Server connection details (command, arguments, environment)
- Available tools and their schemas
- Authentication requirements
- Resource definitions

## Best Practices

### Creating Effective Powers

1. **Solve a complete problem** - A power should provide everything needed for a particular domain. If users need additional setup or knowledge beyond the power, it is incomplete.

2. **Document thoroughly** - The POWER.md should be self-sufficient. A developer reading it should understand what the power does, how to install it, and how to use it without external references.

3. **Provide steering, not just tools** - The real value of a power is in the workflow guidance. Tools are means to an end; steering files explain when and how to use them effectively.

4. **Keep dependencies minimal** - Powers should work with as few external dependencies as possible. Clearly document any requirements that cannot be bundled.

5. **Include practical examples** - Show the power in action with real scenarios. Abstract documentation is less useful than concrete demonstrations.

6. **Define clear boundaries** - State explicitly what the power handles and what falls outside its scope. This prevents user frustration and misuse.

7. **Version your power** - Include version information in POWER.md so users know which version they have and can track updates.

### Common Pitfalls

- Powers that are just documentation without actionable steering
- Missing installation instructions or prerequisites
- MCP configurations that assume specific environment setups
- Overly broad scope that tries to cover too much in one power

## Available Powers

| Power | Description | Includes MCP | Link |
|-------|-------------|:------------:|------|
| *None yet* | Be the first to contribute a power! | - | - |

## How to Install a Power

1. Choose a power from the catalog above.
2. Copy the power directory to your project's `.kiro/powers/` directory:
   ```bash
   cp -r kiro-constructs/powers/power-name your-project/.kiro/powers/
   ```
3. Read the power's `POWER.md` for any additional setup steps.
4. If the power includes MCP server configuration, ensure the required servers are available in your environment.
5. The power's steering files are now active and will guide Kiro's behavior in the relevant domain.

## Creating Your Own Powers

To contribute a new power to this repository:

1. Create a directory following the structure above
2. Write comprehensive POWER.md documentation
3. Include at least one steering file with workflow guidance
4. Test the power in a real project end-to-end
5. Add it to the catalog table in this README
6. Submit a pull request (see [CONTRIBUTING.md](../CONTRIBUTING.md))
