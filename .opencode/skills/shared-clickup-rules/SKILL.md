---
name: shared-clickup-rules
description: Shared rules for all agents when reading, creating, or updating project information in ClickUp.
---

# Shared ClickUp Rules

## 1. Purpose

ClickUp is the project's source of truth for:

- Project requirements and scope.
- Epics and User Stories.
- Acceptance criteria.
- Technical design decisions and documentation.
- Backlog priorities and dependencies.
- Sprint objectives and scope.
- Task status and progress.
- QA scenarios, test cases, and test results.

GitHub is the source of truth for application code, commits, branches, and pull requests.

Agent conversations are not authoritative project records. Always verify relevant information in ClickUp and GitHub before proceeding.

## 2. Project Hierarchy

The current project follows this structure:

CAF (Company)
└── MAINTENANCE SYSTEM (Project Folder)
    ├── Sprints (Folder)
    │   └── Sprint 1 (List)
    ├── Backlog (Folder)
    │   └── Product Backlog (List)
    └── QA (Folder)
        └── Test Scenarios & Cases Sprint 1 (List)

### Structure rules

- The project is a folder under the CAF company space.
- Product Backlog contains project Epics and User Stories.
- Each sprint has its own List under the Sprints folder.
- Each sprint has a corresponding QA List under the QA folder.
- Follow the existing naming conventions when creating additional sprints and QA lists.
- Never reorganize the hierarchy without explicit user approval.

## 3. Task Naming Conventions

### Epic

Format:

`[EPIC-ID] - [Epic Name]`

Example:

`[EP-01] - Production Order Management`

### User Story

Format:

`[EPIC-ID] - [Short Action-Oriented Title]`

Example:

`[EP-01] - Create Production Order`

Rules:

- Every User Story must reference its parent Epic ID.
- Use concise, action-oriented titles.
- Do not put technical implementation details in User Story titles.
- Do not reuse existing Epic IDs.
- Inspect existing records before assigning new IDs.
- Preserve the project's existing numbering sequence.

## 4. User Story Structure

Every User Story should contain the following information:

### 4.1 User Perspective

Use:

As a [role], I want [capability], so that [business value].

### 4.2 System Perspective

Describe the expected system behavior, including relevant:

- Inputs.
- Business rules.
- Validations.
- Permissions.
- Outputs.
- Error handling.

### 4.3 Expected System Flow

Describe how the system should behave from the user's or business process perspective.

Do not prescribe technical implementation unless the task specifically requires it.

### 4.4 Acceptance Criteria

Define clear, observable, and verifiable conditions that determine whether the story meets its requirements.

### 4.5 Expected Test Scenarios

List the expected scenarios that should be verified.

The Tester is responsible for deriving detailed test cases and implementing tests under the appropriate approval gates.

### 4.6 Dependencies

Identify related stories, required functionality, external systems, or other dependencies.

### 4.7 Out of Scope

Identify behavior or functionality explicitly excluded from the User Story.

## 5. Task Statuses

Use the following project workflow:

`To do → Design → Development → Testing → Completed`

Status meanings:

- **To do:** The task is awaiting work and has not entered design.
- **Design:** The task is being analyzed or designed.
- **Development:** The approved implementation is in progress.
- **Testing:** The implementation is ready for verification.
- **Completed:** The user has accepted the task after the required verification.

Important:

- Completing implementation does not mean the task is Completed.
- A Developer must not mark a task Completed simply because the code is finished.
- A Tester may recommend a result but cannot independently grant final acceptance.
- Only move tasks according to the actual project workflow and the user's authorization.

## 6. Approval and Modification Rules

The user is the final authority over project records.

Explicit approval is required before:

- Creating or modifying project folders, Lists, Epics, or User Stories.
- Changing task scope or acceptance criteria.
- Changing priorities.
- Assigning stories to sprints.
- Creating or changing sprint scope.
- Creating or modifying QA records.
- Recording design decisions as approved.
- Changing task status when the change represents an approval or completion decision.
- Reorganizing existing ClickUp records.

Reading and analyzing existing ClickUp information does not require modification approval.

### Approval principles

- A discussion is not approval.
- A suggestion is not approval.
- Silence is not approval.
- Approval must clearly identify the action or decision being authorized.
- Approval for one action does not automatically authorize other actions.

If authorization is unclear, ask the user before making changes.

## 7. Sprint Rules

- Sprint scope must come from approved Product Backlog items.
- Each sprint should have a clear objective.
- Sprint duration and scope must be agreed with the user.
- Do not silently move unfinished stories into another sprint.
- Do not add new stories to an active sprint without approval.
- Preserve the relationship between each sprint and its corresponding QA List.

## 8. Source-of-Truth Rules

Before working on a task:

1. Locate the relevant Epic and User Story.
2. Read the latest requirements and acceptance criteria.
3. Check dependencies and related decisions.
4. Read relevant approved design documentation.
5. Verify the current task status.
6. Identify missing or conflicting information.

If information is missing or contradictory:

- Do not invent requirements.
- Do not silently choose between conflicting decisions.
- Explain the conflict and ask the user for clarification.

When a decision is approved, ensure it is recorded in the appropriate ClickUp location only when authorized.

## 9. Agent Responsibilities

| Agent | ClickUp responsibility |
|---|---|
| Project Manager | Requirements, Epics, User Stories, backlog, priorities, and sprint planning |
| Engineering Partner | Architecture, logical design, technical decisions, and implementation handoff |
| Developer | Read approved requirements and design; report implementation progress when authorized |
| Tester | QA scenarios, test cases, execution evidence, and test results under approval gates |

No agent may assume another agent's responsibilities.

## 10. General Rules

- Preserve existing project conventions.
- Keep records clear, concise, and understandable.
- Avoid duplicating information unnecessarily.
- Link related tasks and documentation where possible.
- Do not overwrite existing decisions without authorization.
- Do not treat proposed designs or assumptions as approved decisions.
- Do not create unnecessary tasks or documentation.
- Never claim a ClickUp change succeeded unless the operation actually succeeded.

## 11. Final Principle

ClickUp records what the project intends to build, why it is needed, what has been agreed, and its current progress.

All agents must respect the approved project records and the user's authority over changes.