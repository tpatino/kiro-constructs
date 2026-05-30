# Hooks

## What Are Kiro Hooks?

Kiro hooks are event-driven automations that execute Kiro instructions in response to development events. They trigger automatically on file saves, file creation, commits, or on-demand via manual invocation. Hooks live in your project's `.kiro/hooks/` directory.

Hooks enable you to build automated quality gates, code generation pipelines, and validation workflows that run seamlessly as part of your normal development process.

## Hook File Format

Hook definitions use a markdown file with YAML frontmatter:

```markdown
---
name: hook-name
description: A clear description of what this hook does when triggered.
event: on_file_save
filePattern: "**/*.ts"
---

Hook instructions written in markdown...
```

### Frontmatter Fields

| Field | Required | Description |
|-------|----------|-------------|
| `name` | Yes | Unique identifier for the hook (kebab-case) |
| `description` | Yes | One-line summary of what the hook does |
| `event` | Yes | The trigger event type |
| `filePattern` | Conditional | Glob pattern for file-based events (required for `on_file_save` and `on_file_create`) |

### Event Types

| Event | Trigger | Use Cases |
|-------|---------|-----------|
| `on_file_save` | Fires when a file matching `filePattern` is saved | Linting, formatting, validation, updating related files |
| `on_file_create` | Fires when a new file matching `filePattern` is created | Scaffolding, adding boilerplate, registering in indexes |
| `on_commit` | Fires when a git commit is made | Changelog updates, version checks, documentation sync |
| `manual` | Fires only when explicitly invoked by the user | Complex operations, bulk processing, one-off tasks |

### The `filePattern` Field

The `filePattern` uses glob syntax to match files:

| Pattern | Matches |
|---------|---------|
| `**/*.ts` | All TypeScript files in any directory |
| `src/**/*.tsx` | React components under `src/` |
| `**/*.test.ts` | All test files |
| `*.md` | Markdown files in the root only |
| `src/api/**/*.ts` | TypeScript files under `src/api/` |
| `**/*.{ts,tsx}` | Both `.ts` and `.tsx` files |

### Body Content

The markdown body contains the hook's instructions:

- **Purpose statement** - What the hook achieves
- **Actions to perform** - Step-by-step instructions for Kiro
- **Input expectations** - What the hook receives (the triggering file, context)
- **Output expectations** - What the hook produces (modified files, messages, validations)
- **Edge cases** - How to handle special situations

## Best Practices

### Writing Effective Hooks

1. **Keep hooks focused** - Each hook should do one thing well. Prefer multiple small hooks over one large hook that handles many concerns.

2. **Use precise file patterns** - Narrow patterns prevent hooks from triggering unnecessarily. Use `src/**/*.ts` instead of `**/*.ts` when the hook only applies to source files.

3. **Handle edge cases** - Consider empty files, malformed content, and files that do not match expected structures.

4. **Be idempotent** - Running the hook multiple times on the same file should produce the same result. Avoid appending content without checking if it already exists.

5. **Provide clear instructions** - The hook body should be explicit about what to do, what to check, and what output to produce.

6. **Consider performance** - Hooks on `on_file_save` run frequently. Keep instructions concise and avoid unnecessary file reads.

7. **Document side effects** - If a hook modifies files other than the triggering file, state this clearly.

### Common Pitfalls

- Overly broad file patterns causing hooks to fire on unintended files
- Hooks that conflict with each other (e.g., two hooks formatting the same file differently)
- Non-idempotent hooks that add duplicate content on repeated saves
- Missing edge case handling for empty or malformed files

## Available Hooks

| Hook | Event | Pattern | Description | Link |
|------|-------|---------|-------------|------|
| *None yet* | - | - | Be the first to contribute a hook! | - |

## How to Install a Hook

1. Choose a hook from the catalog above.
2. Copy the hook file to your project's `.kiro/hooks/` directory:
   ```bash
   mkdir -p your-project/.kiro/hooks
   cp kiro-constructs/hooks/example-hook.md your-project/.kiro/hooks/
   ```
3. The hook will activate automatically based on its configured event trigger.
4. Optionally adjust the `filePattern` to match your project's file structure.

## Creating Your Own Hooks

To contribute a new hook to this repository:

1. Create a markdown file following the format above
2. Test it in a real project across multiple trigger scenarios
3. Verify idempotency (trigger it multiple times, confirm consistent results)
4. Add it to the catalog table in this README
5. Submit a pull request (see [CONTRIBUTING.md](../CONTRIBUTING.md))
