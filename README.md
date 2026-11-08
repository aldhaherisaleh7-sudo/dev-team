# ClickUp & GitHub Development Workflow

An AI skill for managing and executing software development workflows through ClickUp and GitHub, with human-controlled approvals at every important stage.

## Overview

This skill enables an AI development assistant to collaborate with developers throughout the software development lifecycle.

It connects:

- **ClickUp:** Project management, task tracking, sprint planning, requirements, design documents, and test cases.
- **GitHub:** Source code management, development branches, commits, and pull requests.

The AI assists with planning, designing, implementing, and testing features and bug fixes while following predefined development conventions.

**The developer remains in control of all execution activities and lifecycle transitions.**

## Core Capabilities

| Capability | Description |
|---|---|
| Project Initialization | Retrieve company, project, and task information from ClickUp. |
| Sprint Planning | Organize tasks based on priority, dependencies, and implementation order. |
| Task Analysis | Understand requirements, acceptance criteria, and technical constraints. |
| Technical Design | Collaborate on optional technical designs and save approved documents to ClickUp tasks. |
| Feature Development | Implement features after explicit authorization. |
| Bug Fixing | Investigate and resolve bugs through the same development lifecycle. |
| Git Management | Create branches and follow naming and commit conventions. |
| Pull Requests | Push authorized changes and create PRs linked to ClickUp tasks. |
| Quality Assurance | Prepare test cases, execute approved tests, and report results. |

## Development Lifecycle

Every feature and bug fix follows three phases:

```text
             DEVELOPMENT TASK
                     |
                     v
             PLANNING & DESIGN
                     |
              User Approval
                     |
                     v
                DEVELOPMENT
                     |
              User Approval
                     |
                     v
                  TESTING
                     |
              User Approval
                     |
                     v
                 COMPLETED
```

### 1. Planning & Design

- Analyze requirements and dependencies.
- Inspect the existing codebase.
- Suggest implementation approaches.
- Prepare technical designs when necessary.
- Save approved designs inside the corresponding ClickUp task.

Design documentation is optional and should only be created when needed.

### 2. Development

- Create a development branch.
- Implement authorized features or bug fixes.
- Follow existing architecture and coding conventions.
- Commit only when explicitly authorized.
- Push only when explicitly authorized.
- Open a PR after a successful authorized push.

### 3. Testing

- Prepare test scenarios.
- Review test cases with the developer.
- Save approved test cases to ClickUp.
- Execute tests only when authorized.
- Report actual and expected results.
- Iterate based on feedback.

## ClickUp Structure

The workspace follows this hierarchy:

```text
Company
└── Project
    ├── Backlog
    ├── Sprints
    └── QA
```

Each ClickUp task represents a feature, bug fix, or technical task.

The task ID and URL must remain associated with its corresponding Git branch, commits, and pull request.

## Git Conventions

### Branch Naming

```text
<type>/<ticket-id>-<description>
```

Examples:

```text
feature/123-shopping-cart
fix/323-food-doctype-issue
chore/401-update-dependencies
hotfix/450-payment-error
```

### Commit Messages

```text
<type>: <ticket title>

Summary: <brief explanation of changes>

Ticket: <ticket ID>
URL: <ticket URL>
```

Supported types:

- `feat`
- `fix`
- `chore`
- `refactor`
- `test`
- `docs`

### Branch Strategy

| Branch | Purpose |
|---|---|
| `main` | Production |
| `dev` | Integration and staging |
| `feature/*` | New features |
| `fix/*` | Bug fixes |
| `chore/*` | Maintenance |
| `hotfix/*` | Urgent production fixes |

Feature, fix, and chore branches originate from `dev`.

Hotfix branches originate from `main`.

## Pull Request Requirements

After an authorized push succeeds, the AI creates a pull request.

| Branch | Target |
|---|---|
| `feature/*` | `dev` |
| `fix/*` | `dev` |
| `chore/*` | `dev` |
| `hotfix/*` | `main` |

Every PR must include:

1. Feature or bug description.
2. Summary of changes.
3. Important technical details.
4. Testing performed and results.
5. ClickUp task ID.
6. Direct ClickUp task URL.

Direct pushes to `main` and `dev` are strictly prohibited.

PR merging always requires explicit authorization.

## Permission Model

The AI operates under a human-controlled execution model.

| Action | Permission |
|---|---|
| Retrieve ClickUp tasks | Allowed |
| Analyze requirements | Allowed |
| Inspect repository | Allowed |
| Suggest sprint plans | Allowed |
| Suggest technical designs | Allowed |
| Prepare test cases | Allowed |
| Create design documents | Upon instruction |
| Save documents to ClickUp | Upon approval and instruction |
| Change ClickUp status | Explicit instruction |
| Create branches | Explicit instruction |
| Implement features | Explicit instruction |
| Fix bugs | Explicit instruction |
| Execute tests | Explicit instruction |
| Commit changes | Explicit instruction |
| Push changes | Explicit instruction |
| Create PR | After authorized successful push |
| Merge PR | Explicit instruction |

### Critical Rules

- Implementing does not imply permission to commit.
- Committing does not imply permission to push.
- Pushing does not imply permission to merge.
- Preparing tests does not imply permission to execute them.
- Completing a phase does not imply permission to change ClickUp status.

## Skill Structure

```text
clickup-github-development-workflow/
│
├── SKILLS
├────── SKILL.md
└── README.md
```

- `SKILL.md`: Contains the detailed operational instructions, workflow rules, permissions, and execution conventions.
- `README.md`: Explains the skill's purpose, capabilities, workflow, and usage.

## Usage Examples

You can interact with the AI using natural-language instructions.

**Initialize a project:**

> We are working on the Maintenance System project for CAF. Retrieve the tasks from the backlog and help me organize them into sprints.

**Analyze a task:**

> Analyze task 123 and explain its requirements, dependencies, and possible implementation approaches.

**Prepare technical design:**

> Let's design the implementation for task 123.

**Start development:**

> Start development for task 123.

**Save approved design:**

> Save the approved design document to the ClickUp task.

**Commit changes:**

> Commit the current changes using our commit convention.

**Push and open PR:**

> Push the current branch and open a pull request.

**Prepare test cases:**

> Prepare test cases for task 123 and show them to me for review.

**Execute testing:**

> Execute the approved test cases.

**Update task status:**

> Move task 123 to Testing.

---

## Fundamental Principle

The developer controls **WHAT happens and WHEN it happens**.

The AI is responsible for understanding **HOW to do it correctly**, preparing the work, executing explicitly authorized actions, and reporting the results.
