# Claude Code Specs Development (ccspecdev)

A specialized development environment for transforming feature ideas into comprehensive specifications through a structured, spec-driven workflow. This project implements a three-phase methodology that takes rough concepts through requirements engineering, system design, and implementation planning.

## Overview

This project provides a Claude Code agent specialized in **Spec-Driven Agentic Development** - a methodology that ensures complex features are properly planned before implementation begins. The agent guides you through a structured workflow that transforms ideas into actionable code.

## Workflow Methodology

The development process follows a strict three-phase iterative workflow:

### Phase 1: Requirements Engineering
- Creates user stories with acceptance criteria in EARS format
- Establishes clear functional and non-functional requirements
- Requires explicit user approval before proceeding

### Phase 2: System Design
- Conducts necessary research and builds context
- Creates comprehensive design documentation with architecture, components, and data models
- Includes Mermaid diagrams for visual representations
- Requires explicit user approval before proceeding

### Phase 3: Implementation Planning
- Converts design into actionable coding tasks
- Creates test-driven development approach with incremental progress
- Generates numbered checkbox task lists with requirement traceability
- Requires explicit user approval before execution begins

## Available Slash Commands

The project includes four specialized Claude Code slash commands:

### `/add-feature {feature-idea}`
Initializes a new feature specification by creating requirements, design, and task documents in the `.claude/specs/{feature-name}/` directory structure.

**Usage:** `/add-feature user authentication system`

### `/create-steering-docs`
Analyzes your repository and creates comprehensive steering documents that give Claude persistent knowledge about your project:
- `product.md` - Product overview, features, and target audience
- `tech.md` - Technical stack, development guidelines, and best practices
- `structure.md` - Project structure, architecture patterns, and organization

### `/list-feature-names`
Lists all feature directories in the `.claude/specs/` directory, showing you what specifications have been created.

### `/start-task {feature-name}`
Executes specific tasks from a completed feature specification. The agent will:
- Read all specification files for context
- Execute ONE task at a time
- Mark tasks as in-progress (~) and completed (x)
- Wait for explicit approval before proceeding to next tasks

## Directory Structure

```
.claude/
├── CLAUDE.md                    # Main agent configuration and methodology
├── specs/                       # Feature specifications directory
│   └── {feature-name}/         # Individual feature directories
│       ├── requirements.md     # User stories and acceptance criteria
│       ├── design.md          # System design and architecture
│       └── tasks.md           # Implementation task list
├── steering/                   # Project context documents (created by command)
│   ├── product.md
│   ├── tech.md
│   └── structure.md
└── commands/                   # Slash command definitions
    ├── add-feature.md
    ├── create-steering-docs.md
    ├── list-feature-names.md
    └── start-task.md
```

## Key Features

- **Sequential Workflow**: Enforces Requirements → Design → Tasks progression
- **User Approval Gates**: Requires explicit approval between each phase
- **EARS Format**: Uses Event-driven Acceptance Requirements Specification format
- **Test-Driven Planning**: Creates implementation plans focused on testing and incremental development
- **Requirement Traceability**: Every task references specific requirements
- **Single Task Execution**: Prevents overwhelming complexity by focusing on one task at a time

## Getting Started

1. **Initialize a Feature**: Use `/add-feature your-feature-idea` to start the specification process
2. **Review & Approve**: Go through each phase, providing feedback and approval
3. **Execute Tasks**: Use `/start-task feature-name` to begin implementation
4. **Track Progress**: Tasks are marked with status indicators (not started, in-progress ~, completed x)

## Constraints & Rules

- **Never skip phases** - must complete Requirements → Design → Tasks in order
- **Always get explicit approval** - clear "yes", "approved", or "looks good" required
- **One task at a time** - no automatic progression to next tasks
- **Code focus only** - tasks involve writing, modifying, or testing code exclusively
- **Spec separation** - this workflow creates planning artifacts, not production code

## Example Workflow

```
User: /add-feature user authentication system
→ Agent creates requirements.md with user stories
→ User approves requirements
→ Agent creates design.md with architecture
→ User approves design  
→ Agent creates tasks.md with implementation plan
→ User approves tasks

User: /start-task user-authentication
→ Agent executes first task only
→ User approves implementation
→ Agent marks task complete, waits for next instruction
```

This methodology ensures that complex features are properly planned, all stakeholders understand the requirements, and implementation follows a systematic, test-driven approach.