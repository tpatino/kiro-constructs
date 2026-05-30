# Specs

## What Are Kiro Specs?

Kiro specs are structured requirement documents that drive implementation. They break down a feature or system component into requirements, design decisions, and actionable tasks, providing Kiro with the context needed to implement features systematically and completely.

Specs bridge the gap between a high-level idea ("build a user authentication system") and implementation-ready instructions that Kiro can execute step by step.

## Spec File Format

Specs are markdown files organized into three core sections:

```markdown
# Spec: Feature Name

## Requirements

### Functional Requirements
- FR-1: Description of a functional requirement
- FR-2: Another functional requirement with acceptance criteria

### Non-Functional Requirements
- NFR-1: Performance, security, or scalability requirement
- NFR-2: Another non-functional requirement

## Design

### Architecture
Describe the high-level approach, components involved, and how they interact.

### Data Model
Define any data structures, schemas, or state management.

### API Design
Define interfaces, endpoints, or function signatures.

### Key Decisions
Document significant technical choices and their rationale.

## Tasks

- [ ] Task 1: Specific implementation step
- [ ] Task 2: Another implementation step
- [ ] Task 3: Validation and testing step
```

### Section Breakdown

| Section | Purpose | Key Content |
|---------|---------|-------------|
| **Requirements** | Define *what* needs to be built | Functional behaviors, constraints, acceptance criteria |
| **Design** | Define *how* it will be built | Architecture, data models, interfaces, decisions |
| **Tasks** | Define the *steps* to build it | Ordered implementation steps, each completable independently |

## How Specs Drive Implementation

1. **Requirements** establish clear acceptance criteria so Kiro knows when the feature is complete.
2. **Design** provides architectural context so Kiro makes implementation choices aligned with the overall system.
3. **Tasks** break work into manageable steps that can be implemented and verified incrementally.

Kiro uses specs to:
- Understand the full scope before starting implementation
- Make design decisions consistent with the specified architecture
- Verify each task against the requirements
- Produce a complete implementation without gaps

## Best Practices

### Writing Effective Specs

1. **Be specific in requirements** - "Users can log in" is vague. "Users can authenticate with email/password, receiving a JWT token valid for 24 hours" is implementable.

2. **Number your requirements** - Use identifiers (FR-1, NFR-1) so tasks and design decisions can reference specific requirements.

3. **Include acceptance criteria** - Each requirement should have a clear condition that determines whether it is met.

4. **Make tasks atomic** - Each task should be completable in one step. "Build the authentication system" is too large; "Create the login endpoint with input validation" is appropriately scoped.

5. **Order tasks logically** - Dependencies should flow top to bottom. A task should never depend on a later task.

6. **Document design rationale** - When the design section makes a choice (e.g., JWT over sessions), explain why. This helps Kiro make aligned decisions in edge cases.

7. **Separate functional from non-functional** - Performance, security, and scalability requirements have different implementation implications and should be clearly distinguished.

8. **Keep specs focused** - One spec per feature or component. A spec covering an entire application is too broad to be actionable.

### Common Pitfalls

- Requirements without measurable acceptance criteria
- Tasks that are too large to implement atomically
- Missing design section, forcing Kiro to make architectural choices without guidance
- Specs that describe the current state rather than the desired state
- Overlapping specs that define the same functionality differently

## Available Specs

| Spec | Domain | Description | Link |
|------|--------|-------------|------|
| *None yet* | - | Be the first to contribute a spec example! | - |

## How to Use Spec Examples

1. Browse the examples in this directory to find specs similar to what you need.
2. Copy the example to your project's `.kiro/specs/` directory:
   ```bash
   mkdir -p your-project/.kiro/specs
   cp kiro-constructs/specs/example-spec.md your-project/.kiro/specs/
   ```
3. Replace the example content with your project-specific requirements:
   - Define your functional and non-functional requirements
   - Design the architecture and interfaces for your context
   - Break implementation into project-specific tasks
4. Use the spec to drive implementation with Kiro.

## Creating Your Own Specs

To contribute a new spec example to this repository:

1. Create a markdown file following the format above
2. Ensure it demonstrates a complete, realistic feature specification
3. Validate it by using it to drive implementation in a real project
4. Add it to the catalog table in this README
5. Submit a pull request (see [CONTRIBUTING.md](../CONTRIBUTING.md))
