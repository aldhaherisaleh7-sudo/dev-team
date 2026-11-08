# AI Development Team

A manually supervised multi-agent development workflow built with OpenCode.

This repository defines a structured AI development team consisting of four specialized agents: Project Manager, Engineering Partner, Developer, and Tester.

Each agent has a clearly defined responsibility, dedicated skills, and approval boundaries. The objective is to use AI to support the software development lifecycle while keeping the developer in control of decisions, implementation, and delivery.

## 1. Objectives

- Organize software development into clearly defined responsibilities.
- Separate business analysis, software design, implementation, and testing.
- Maintain consistent development standards.
- Produce small, reviewable, and shippable increments.
- Prioritize maintainability, testability, and security.
- Maintain traceability between ClickUp tasks and GitHub changes.
- Keep all important decisions under human supervision.

## 2. Team Structure

| Agent | Responsibility | Main Output |
|---|---|---|
| Project Manager | Requirements and project planning | Epics, User Stories, Backlog, Sprints |
| Engineering Partner | Architecture and technical design | Architecture, Logical Design, Implementation Plan |
| Developer | Application implementation | Application code and implementation report |
| Tester | Independent verification | Test Cases, Test Results, Defect Reports |

### Project Manager

Responsible for understanding business requirements and defining WHAT the system should do.

Responsibilities:
- Analyze project requirements.
- Identify missing and ambiguous requirements.
- Define functional and non-functional requirements.
- Create Epics and User Stories.
- Define acceptance criteria.
- Organize the Product Backlog.
- Plan sprint scope and objectives.

### Engineering Partner

Responsible for defining HOW the system should be designed.

Responsibilities:
- Design system architecture.
- Evaluate architectural alternatives and trade-offs.
- Design individual features.
- Define components, responsibilities, and interactions.
- Identify technical risks.
- Prepare implementation-ready plans.
- Produce technical documentation and diagrams.

### Developer

Responsible for implementing approved designs.

Responsibilities:
- Inspect the existing codebase.
- Follow approved architecture and logical designs.
- Implement small, reviewable increments.
- Follow Clean Code and SOLID principles.
- Prioritize maintainability, testability, and security.
- Follow the established Git workflow.
- Prepare changes for code review.

### Tester

Responsible for independently verifying application behavior.

Responsibilities:
- Analyze requirements and acceptance criteria.
- Derive test scenarios and detailed test cases.
- Present proposed test cases for user approval.
- Implement approved tests.
- Execute tests after approval.
- Report defects and testing evidence.
- Verify fixes and regression behavior.

## 3. Workflow

The workflow is intentionally sequential and manually supervised.

```text
                  USER
                   |
                   v
             PROJECT MANAGER
                   |
                   v
          ENGINEERING PARTNER
                   |
                   v
               DEVELOPER
                   |
                   v
                TESTER
                   |
                   v
             USER ACCEPTANCE
```

The user manually invokes each agent and supervises every handoff.

**No agent automatically invokes another agent.**

Each stage produces an output for the user to review before proceeding.

### Stage 1: Project Planning

The Project Manager analyzes the project, identifies uncertainties, and prepares the project structure, backlog, and sprint plan.

### Stage 2: Engineering Design

The Engineering Partner works with the user to establish the architecture or feature-level design.

The design is reviewed and refined until the user approves it.

### Stage 3: Development

The Developer implements approved requirements and designs in small increments.

### Stage 4: Testing

The Tester independently derives test cases and presents them to the user.

Test implementation and execution require separate explicit approvals.

### Stage 5: Acceptance

The user reviews the implementation and testing results before accepting the work.

## 4. Approval Philosophy

The user remains the final decision-maker.

The following actions require explicit authorization:

- Creating or modifying ClickUp records.
- Approving architecture and technical decisions.
- Committing changes.
- Pushing changes.
- Opening pull requests.
- Merging pull requests.
- Deploying changes.
- Implementing test code.
- Executing tests when required by the testing workflow.

Approval of one action does not imply approval of another.

## 5. Project Management with ClickUp

ClickUp is the source of truth for project requirements, tasks, designs, priorities, sprint scope, and progress.

Current project hierarchy:

```text
CAF (Company)
└── MAINTENANCE SYSTEM (Project Folder)
    ├── Sprints (Folder)
    │   └── Sprint 1 (List)
    ├── Backlog (Folder)
    │   └── Product Backlog (List)
    └── QA (Folder)
        └── Test Scenarios & Cases Sprint 1 (List)
```

### Task Workflow

```text
To do
  |
  v
Design
  |
  v
Development
  |
  v
Testing
  |
  v
Completed
```

Developer completion does not automatically mean a task is completed. Testing and user acceptance are part of the overall delivery process.

## 6. Git and GitHub Workflow

Git is used for version control, while GitHub manages remote repositories and collaboration.

### Main Branches

| Branch | Purpose |
|---|---|
| `main` | Production-ready code |
| `dev` | Integration and staging development |

### Working Branches

- `feature/` - New functionality.
- `bugfix/` - Bug fixes.
- `hotfix/` - Urgent production fixes.
- `chore/` - Maintenance and tooling.
- `refactor/` - Code restructuring.

Example:

```text
feature/123-create-production-order
```

### Mandatory Git Rules

- Never push directly to `main`.
- Never push directly to `dev`.
- Commit only with explicit approval.
- Push only with explicit approval.
- Push only the authorized current working branch.
- Open pull requests only with explicit approval.
- Never merge or deploy without explicit approval.

Every pull request must include:

- Feature or bug description.
- Implementation summary.
- Actual testing results.
- ClickUp task ID.
- Direct ClickUp task link.

This ensures traceability between project requirements and code changes.

## 7. Engineering Principles

The team follows:

- Clean Code.
- SOLID principles.
- Separation of concerns.
- Appropriate design patterns.
- Maintainability.
- Testability.
- Security.
- Small and reversible changes.

Additional quality attributes should be considered according to the task and the user's instructions or approved requirements.

The objective is not to introduce unnecessary abstractions or overengineer solutions.

## 8. Testing Philosophy

Testing is independently managed by the Tester agent.

The testing workflow has three mandatory approval gates:

1. **Test Case Approval:** Present all proposed test cases to the user before implementing tests.
2. **Test Implementation Approval:** Present the implementation plan and obtain approval before writing or modifying test code.
3. **Test Execution Approval:** Present the execution scope and obtain approval before running tests.

Approval at one stage does not automatically authorize the next stage.

The Developer owns application implementation. The Tester owns test implementation and verification.

## 9. Repository Structure

```text
dev-team/
│
├── README.md
├── AGENTS.md
├── opencode.json
│
├── indexes/
│   ├── agents.md
│   └── skills.md
│
└── .opencode/
    │
    ├── agents/
    │   ├── project-manager.md
    │   ├── engineering-partner.md
    │   ├── developer.md
    │   └── tester.md
    │
    └── skills/
        ├── pm-project-analysis/
        │   └── SKILL.md
        ├── pm-project-building/
        │   └── SKILL.md
        │
        ├── ep-system-architecture/
        │   └── SKILL.md
        ├── ep-logical-design/
        │   └── SKILL.md
        ├── ep-implementation-planning/
        │   └── SKILL.md
        │
        ├── dev-implementation/
        │   └── SKILL.md
        ├── dev-code-quality/
        │   └── SKILL.md
        │
        ├── test-planning/
        │   └── SKILL.md
        ├── test-execution/
        │   └── SKILL.md
        │
        ├── shared-clickup-rules/
        │   └── SKILL.md
        ├── shared-git-workflow/
        │   └── SKILL.md
        └── shared-security/
            └── SKILL.md
```

## 10. Shared Skills

Shared skills define rules that apply across multiple agents.

| Skill | Purpose |
|---|---|
| `shared-clickup-rules` | ClickUp hierarchy, task conventions, and approval rules |
| `shared-git-workflow` | Git version control and GitHub collaboration |
| `shared-security` | Secure development, credentials, access control, and safe operations |

## 11. Design Philosophy

This AI development team is designed around a few important principles:

- **Human supervision:** AI agents assist rather than independently control the project.
- **Separation of responsibilities:** Each agent has a clear role.
- **Traceability:** Requirements, designs, code changes, and tests remain connected.
- **Incremental delivery:** Prefer small, independently reviewable features.
- **Reversibility:** Avoid unnecessary changes that are difficult to undo.
- **Explicit approval:** Important actions require user authorization.
- **Context efficiency:** Load only the skills and project information relevant to the current task.

## 12. Getting Started

1. Open the repository using OpenCode.
2. Allow OpenCode to discover the configured agents and skills.
3. Start with the Project Manager.
4. Review and approve the project analysis.
5. Continue manually through the Engineering Partner, Developer, and Tester.
6. Review every important handoff before proceeding.

---

**The AI development team is a supervised engineering workflow, not an autonomous development pipeline.**
